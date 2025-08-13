<template>
  <li class="list-group-item d-flex justify-content-between ">
    <span class="list-group-item-label">Omar</span>
    <input type="number" class="list-group-item-input" defaultValue="999" />

    <div class="d-flex justify-content-center align-iteam-center">
      <button type="button" class="btn-cookie btn-sm">
        <i class="fa fa-cookie"></i>
      </button>
      <button type="button" class="btn-trash btn-sm">
        <i class="fa fa-trash"></i>
      </button>
      <i class="fa fa-star"></i>
    </div>
  </li>
</template>
<script>
export default {};
</script>
<style scoped>
.list-group-item {
  padding: 15px 20px;
  border-bottom: 1px solid #3d5a80;
}
.list-group-item:last-child {
  border-bottom: 1px solid black;
}
.list-group-item span {
  line-height: 35px;
  font-size: 20px;
  cursor: pointer;
  width: 550px;
}

.list-group-item input {
  line-height: 35px;
  font-size: 28px;
  outline: none;
  text-align: center;
  border: 0;
}
.list-group-item button {
  width: 35px;
  height: 35px;
  margin: 3px;
  font-size: 17px;
  cursor: pointer;
  border: none;
}
.list-group-item .btn-cookie {
    color: #e09f3e;
}
.list-group-item .btn-trash{
    color: #e5383b;
}

.list-group-item .fa-star{
    width: 35px;
    height: 35px;
    text-align: center;
    line-height: 35px;
    font-size: 16px;
    color: #ffd780;
    transition: 0.3s linear all;
    transform: translateX(30px);
    opacity: 0;

}

.list-group-item.like .fa-star{
 opacity: 1;
 transform: translateX(0);


}
.list-group-item.favourite .list-group-item-label,
.list-group-item.favourite .list-group-item-input{
    color: #e09f3e;
}


</style>
