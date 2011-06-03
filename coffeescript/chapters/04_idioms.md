
##Each

JS:

<span class="noconvert"></span>

    array.forEach(function(item, i){
      myFunction(item)
    });
    
    for (var i=0; i < array.length; i++)
      myFunction(array[i]);

CS:
      
    myFunction(item) for item in array
    
    array.forEach (item) -> myFunction(item)
    
##Map

JS:

<span class="noconvert"></span>

    var result = array.map(function(item, i){
      return item.name;
    });
    
CS:
      
    result = (item.name for item in array)

##Select

JS:

<span class="noconvert"></span>

    result = array.filter(function(item, i){
      return item.name == "test"
    });

CS

    result = (myFunction(item) for item in array when item.name is "test")

    passed = []
    failed = []
    (if score > 60 then passed else failed).push score for score in [49, 58, 76, 82, 88, 90]
    
    passed = (score for score in scores when score > 60)
    
##Reduce

    [1..1000].reduce (t, s) -> t + s
    
##Includes

JS:

<span class="noconvert"></span>

    var included = (array.indexOf("test") != -1)

CS:
    
    included = "test" in array
    
    included = ~"a long test string".indexOf "test"
    
##Min/Max

    Math.max.apply Math, [14, 35, -7, 46, 98] # 98
    Math.min.apply Math, [14, 35, -7, 46, 98]
    
##jQuery

    jQuery ($) ->
      
      
    someObject = { a: 'value for a', b: 'value for b' }
    { a, b } = someObject
    console.log "a is '#{a}', b is '#{b}'"
    
> CoffeeScript uses a straight source-to-source compiler. No type checking is performed, and we can't work out if a variable even exists or not. This means that we can't implement features that other languages can build in natively without costly runtime checks. As a result, any feature which relies on this kind of analysis won't be considered.
    
Use `or` instead of ||
Use `and` instead of &&

    if @attributes then makeArray(@attributes)    # Multi-line if/elses should probably use indentation.
    else @attributes = []

    for key, value of obj    # Again, you can use a `when` if you like.
      unless key in moduleKeywords 
        @::[key] = value
        
    for key, value of obj when key not in moduleKeywords 
        @::[key] = value
        
    return if typeof console is "undefined"
    
    for name in evs
      @_callbacks[name] ?= []
      @_callbacks[name].push(callback)
      
    for name in evs
      @_callbacks[name] or= []
      @_callbacks[name].push(callback)
      
      
    unless typeof exports is "undefined"    # `unless ... else` reads poorly in English. Better to stick to `if ... else`.
      Spine = exports
    else
      Spine = @Spine = {}

    if typeof exports is not "undefined"    # `unless ... else` reads poorly in English. Better to stick to `if ... else`.
      Spine = exports
    else
      Spine = @Spine = {}
    