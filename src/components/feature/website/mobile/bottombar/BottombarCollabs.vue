<template>
  <StyledWrapper>
    <StyledImageWrapper
      v-for="collab in collabs"
      :key="collab.collab"
      :content="`@${collab.collab}`"
      v-tippy
    >
      <a target="_blank" :href="`https://www.instagram.com/${collab.collab}`">
        <StyledImage :src="collab.image" />
      </a>
    </StyledImageWrapper>
  </StyledWrapper>
</template>

<script>
import styled from "vue-styled-components";

const StyledWrapper = styled.div`
  position: relative;
  width: 200px;
  height: 56px;
  display: flex;
  justify-content: flex-end;
  align-items: center;
`;

const StyledImageWrapper = styled.div`
  width: 34px;
  height: 34px;
  display: flex;
  align-items: center;
  transform: translateX(-33%);
  cursor: pointer;

  &:first-child {
    transform: translateX(0);
  }

  &:hover {
    z-index: 2;
  }
`;

const StyledImage = styled.img`
  width: 34px;
  height: 34px;
  border: 3px solid white;
  border-radius: 50%;
  position: absolute;
  top: 0;
  left: 0;
`;

export default {
  props: {
    collabs: Array
  },
  components: {
    StyledWrapper,
    StyledImageWrapper,
    StyledImage
  },
  data: function() {
    return {
      danImage: require("@/assets/images/dan.png"),
      liaImage: require("@/assets/images/lia.png"),
      mikeImage: require("@/assets/images/mike.png")
    };
  }
};
</script>
