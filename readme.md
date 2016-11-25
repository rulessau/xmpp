# XmppClient instance

```
XmppClient xmpp = new XmppClient();
xmpp.params_.host = "xx.xx.xx.x";
xmpp.params_.port = 5222;
xmpp.params_.domain = "domain";
xmpp.params_.resource = "win10";
xmpp.params_.user = "xxxx";
xmpp.params_.pwd = "xxxx";

xmpp.OnLoginOk += OnLoginOk;
xmpp.OnLoginFail += OnLoginFail;
xmpp.OnConnectionClose += OnConnectionClose;
xmpp.OnXmppInput += OnXmppInput;
xmpp.OnXmppOutput += OnXmppOutput;
xmpp.OnRecvIQ += OnRecvIQ;
xmpp.OnRecvMessage += OnRecvMessage;
xmpp.OnRecvPresence += OnRecvPresence;

xmpp.Login();
```

# callback handle

```
public void OnXmppInput(object sender, string s)
{
	textBlock.Text += string.Format("[   recv   ] {0} {1} \n", sender.GetHashCode(),
		DateTime.Now.ToString());
	
	textBlock.Text += s;
	textBlock.Text += "\n\n";
}

public void OnXmppOutput(object sender, string s)
{
	textBlock.Text += string.Format("[   send   ] {0} {1} \n", sender.GetHashCode(),
		DateTime.Now.ToString());

	textBlock.Text += s;
	textBlock.Text += "\n\n";
}
```