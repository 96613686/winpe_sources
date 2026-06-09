# WldpSendSmartAppControlBlockToastWldp(ushort const *,ushort const *,long)

- ea: `0x18003104c`
- end: `0x1800310a6`
- name: `?WldpSendSmartAppControlBlockToastWldp@@YAJPEBG0J@Z`
- size: `90`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800175fc`

## callees

- `0x180030b0c`
- `0x18003104c`

## string_xrefs

- `0x180031055`: `msiexec.exe`
- `0x18003106f`: `<toast launch="https://go.microsoft.com/fwlink/?linkid=2197194" activationType="protocol"> <visual>  <binding template="ToastGeneric">   <text id="2002"></text>   <text id="3002"></text>  </binding> </visual> <actions>  <action id="4002" activationType="protocol" arguments="https://go.microsoft.com/fwlink/?linkid=2193834"/> </actions></toast>`
- `0x180031089`: `<toast launch="https://go.microsoft.com/fwlink/?linkid=2193834" activationType="protocol"> <visual>  <binding template="ToastGeneric">   <text id="2003"></text>   <text id="3003"></text>  </binding> </visual> <actions>  <action id="4003" activationType="protocol" arguments="https://go.microsoft.com/fwlink/?linkid=2193834"/> </actions></toast>`

## pseudocode

```c
__int64 __fastcall WldpSendSmartAppControlBlockToastWldp(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3)
{
  unsigned int v3; // edx
  unsigned __int16 *v4; // rcx
  unsigned int v5; // r9d
  unsigned int v6; // r8d

  if ( a3 == -1058471923 )
  {
    v3 = 2002;
    v4 = L"<toast launch=\"https://go.microsoft.com/fwlink/?linkid=2197194\" activationType=\"protocol\"> <visual>  <bindi"
          "ng template=\"ToastGeneric\">   <text id=\"2002\"></text>   <text id=\"3002\"></text>  </binding> </visual> <a"
          "ctions>  <action id=\"4002\" activationType=\"protocol\" arguments=\"https://go.microsoft.com/fwlink/?linkid=2"
          "193834\"/> </actions></toast>";
    v5 = 4002;
    v6 = 3002;
  }
  else
  {
    v3 = 2003;
    v4 = L"<toast launch=\"https://go.microsoft.com/fwlink/?linkid=2193834\" activationType=\"protocol\"> <visual>  <bindi"
          "ng template=\"ToastGeneric\">   <text id=\"2003\"></text>   <text id=\"3003\"></text>  </binding> </visual> <a"
          "ctions>  <action id=\"4003\" activationType=\"protocol\" arguments=\"https://go.microsoft.com/fwlink/?linkid=2"
          "193834\"/> </actions></toast>";
    v5 = 4003;
    v6 = 3003;
  }
  return ToastHelper::MakeSmartAppControlBlockToast(v4, v3, v6, v5, L"msiexec.exe", a2);
}

```

## disassembly

```asm
0x18003104c  sub     rsp, 38h
0x180031050  mov     [rsp+38h+var_10], rdx; unsigned __int16 *
0x180031055  lea     rax, aMsiexecExe; "msiexec.exe"
0x18003105c  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x180031061  cmp     r8d, 0C0E9000Dh
0x180031068  jnz     short loc_180031084
0x18003106a  mov     edx, 7D2h
0x18003106f  lea     rcx, aToastLaunchHtt; "<toast launch=\"https://go.microsoft.co"...
0x180031076  mov     r9d, 0FA2h
0x18003107c  mov     r8d, 0BBAh
0x180031082  jmp     short loc_18003109C
0x180031084  mov     edx, 7D3h; unsigned int
0x180031089  lea     rcx, aToastLaunchHtt_0; "<toast launch=\"https://go.microsoft.co"...
0x180031090  mov     r9d, 0FA3h; unsigned int
0x180031096  mov     r8d, 0BBBh; unsigned int
0x18003109c  call    ?MakeSmartAppControlBlockToast@ToastHelper@@SAJPEAGIIIPEBG1@Z; ToastHelper::MakeSmartAppControlBlockToast(ushort *,uint,uint,uint,ushort const *,ushort const *)
0x1800310a1  add     rsp, 38h
0x1800310a5  retn
```
