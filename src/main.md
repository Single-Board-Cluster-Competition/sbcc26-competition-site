# Welcome to the Single Board Cluster Competition 2026.

This site will contain all relevant info for competitors in terms of submissions and other logistics. For time-based announcements this site will reflect it when the time rolls over according to PST -- teams in forward time zones will be notified of specifics according to their local timezone.

The _Single-Board Cluster Competition (SBCC)_ is a competition where teams from all around the world compete using _single-board_ devices, and other similarly simple hardware, to create miniature supercomputing clusters. SBCC26 is the fourth competition. 

## Schedule <a id="schedule"></a>

*Agenda:*

| DAY | START | END | ACTIVITY |
| ---- | ---- | ---- | ---- | 
| Thursday | 8:00 am | 8:00 am (Friday) | Setup |
| Friday | 8:00 am | **1:00 pm PST** | Benchmarking |
| Friday | 12:00 pm | 5:00 pm PST | Competition Begins - Applications |
| Saturday | 8:00 am | 3:00 pm PST | Final Submissions Due |
| Saturday | 5:00 pm | 6:00 pm | Awards Ceremony |

Notice that you can submit benchmarks one hour after application details are revealed. Here is the [FULL schedule](./schedule.md)

## FAQ <a id="faq"></a>

### What is the price limit for the hardware?
- 6000 USD, Use american MSRP for hardware cost when possible.

### What is the power limit for the cluster?
- 250 Watts

### Are eGPUs allowed?
- Yes

### Does a DHCP server count as part of the cluster?
- No, given that it is only used for managing the cluster network / accessing the cluster.


### Can we use LLMs during the competition?
- Yes. Only sharing information and getting advice from with mentors and individuals outside the competition should be avoided/not done. Communication in between teams and judges is allowed. Teams may also access the internet on their own computers, but not speak about the competition to others.


## Join our Discord!
<script>
    document.addEventListener("DOMContentLoaded", function () {
        const mdContainer = document.querySelector("#mdbook-content > main");
        if (!mdContainer) return;

        const mediaQuery = window.matchMedia("(prefers-color-scheme: dark)");

        function createIframe(theme) {
            const iframe = document.createElement("iframe");
            iframe.src = `https://discord.com/widget?id=1462340210120720386&theme=${theme}`;
            iframe.setAttribute("allowtransparency", "true");
            iframe.setAttribute("frameborder", "0");
            iframe.setAttribute(
                "sandbox",
                "allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts"
            );

            iframe.style.width = "50vw";
            iframe.style.height = "45vh";
            iframe.style.border = "0";

            return iframe;
        }

        let iframe = createIframe(mediaQuery.matches ? "dark" : "light");

        // Append iframe to the end of #discord
        mdContainer.appendChild(iframe);

        mediaQuery.addEventListener("change", function (e) {
            const newTheme = e.matches ? "dark" : "light";
            const newIframe = createIframe(newTheme);
            iframe.replaceWith(newIframe);
            iframe = newIframe;
        });
    });
</script>