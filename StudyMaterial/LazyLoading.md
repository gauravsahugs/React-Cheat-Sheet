lazy loading means that a component or a part of code must get loaded when it is required. It is also referred to as code splitting and data fetching.

lazyloading on the basis of condition if a user is admin or customer will load that component only to reduce bandwith usuage and performance otimization

import React, { Suspense } from "react";
const Customer = React.lazy(() => import("./Customer.js"));
const Admin = React.lazy(() => import("./Admin.js"));

//Instead of regular import statements, we will use the above approach for lazy loading

export default (props) => {
if (props.user === "admin") {
return (
// fallback component is rendered until our main component is loaded
<Suspense fallback={<div>Loading</div>}>
<Admin />
</Suspense>
);
} else if (props.user === "customer") {
return (
<Suspense fallback={<div>Loading</div>}>
<Customer />
</Suspense>
);
} else {
return <div> Invalid User </div>;
}
};

lazyload image using react lazyload image library

import Image from "../images/bird.jpg";
import PlaceholderImage from "../images/placeholder.jpg";
import { LazyLoadImage } from 'react-lazy-load-image-component';
import 'react-lazy-load-image-component/src/effects/blur.css';

<LazyLoadImage src={Image}
    width={600} height={400}
    PlaceholderSrc={PlaceholderImage}
    effect="blur"
/>
