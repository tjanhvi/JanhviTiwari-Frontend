### Q. What problems / warnings are there with code?

Answer =  

Here the list problems / warnings that are present in the code:

# 1- 
# error in code
onClick={onClickHandler(index)}

this is not the right way of calling in here.
It should pass as a callback function

# corrected code
the corrected code is :
onClick={() => onClickHandler(index)}

Use of arrow function for calling it.


# 2-
# error in code
const [setSelectedIndex, selectedIndex] = useState();

It is not properly initialized. 
It should be initialized to a default value like "-1" or "null"

# corrected code
const [setSelectedIndex, selectedIndex] = useState(null);
"OR"
const [setSelectedIndex, selectedIndex] = useState(-1);


# 3-
# error in code
<SingleListItem
  onClickHandler={() => handleClick(index)}
  text={item.text}
  index={index}
  isSelected={selectedIndex}
/>

Mapping through the array, there should be unique key from which the items are highlighted as per their unique key. 

# corrected code
<SingleListItem
  key = {index}
  onClickHandler={() => handleClick(index)}
  text={item.text}
  index={index}
  isSelected={selectedIndex}
/>


# 4-
# error in code
WrappedListComponent.propTypes = {
  items: PropTypes.array(PropTypes.shapeOf({
    text: PropTypes.string.isRequired,
  })),
};

The propTypes validation for the items prop in 'WrappedListComponent' is incorrect.  
Instead of array(PropTypes.shapeOf(...)), it should be PropTypes.arrayOf(PropTypes.shape({...})). 

# corrected code
WrappedListComponent.propTypes = {
  items: PropTypes.arrayOf(
    PropTypes.shape({
      text: PropTypes.string.isRequired,
    })
  )
};
