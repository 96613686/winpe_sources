# WldpSendSmartAppControlBlockToast2(ushort const *,ushort const *,long)

- ea: `0x180030ff0`
- end: `0x180031043`
- name: `?WldpSendSmartAppControlBlockToast2@@YAJPEBG0J@Z`
- size: `83`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180030b0c`
- `0x180030ff0`

## string_xrefs

- `0x180031026`: `<toast launch="https://go.microsoft.com/fwlink/?linkid=2193834" activationType="protocol"> <visual>  <binding template="ToastGeneric">   <text id="2000"></text>   <text id="3000"></text>  </binding> </visual> <actions>  <action id="4000" activationType="protocol" arguments="https://go.microsoft.com/fwlink/?linkid=2193834"/> </actions></toast>`
- `0x18003100c`: `<toast launch="https://go.microsoft.com/fwlink/?linkid=2197194" activationType="protocol"> <visual>  <binding template="ToastGeneric">   <text id="2002"></text>   <text id="3002"></text>  </binding> </visual> <actions>  <action id="4002" activationType="protocol" arguments="https://go.microsoft.com/fwlink/?linkid=2193834"/> </actions></toast>`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WldpSendSmartAppControlBlockToast2(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
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
    v3 = 2000;
    v4 = L"<toast launch=\"https://go.microsoft.com/fwlink/?linkid=2193834\" activationType=\"protocol\"> <visual>  <bindi"
          "ng template=\"ToastGeneric\">   <text id=\"2000\"></text>   <text id=\"3000\"></text>  </binding> </visual> <a"
          "ctions>  <action id=\"4000\" activationType=\"protocol\" arguments=\"https://go.microsoft.com/fwlink/?linkid=2"
          "193834\"/> </actions></toast>";
    v5 = 4000;
    v6 = 3000;
  }
  return ToastHelper::MakeSmartAppControlBlockToast(v4, v3, v6, v5, a1, a2);
}

```

## disassembly

```asm
0x180030ff0  sub     rsp, 38h
0x180030ff4  mov     [rsp+38h+var_10], rdx; unsigned __int16 *
0x180030ff9  mov     [rsp+38h+var_18], rcx; unsigned __int16 *
0x180030ffe  cmp     r8d, 0C0E9000Dh
0x180031005  jnz     short loc_180031021
0x180031007  mov     edx, 7D2h
0x18003100c  lea     rcx, aToastLaunchHtt; "<toast launch=\"https://go.microsoft.co"...
0x180031013  mov     r9d, 0FA2h
0x180031019  mov     r8d, 0BBAh
0x18003101f  jmp     short loc_180031039
0x180031021  mov     edx, 7D0h; unsigned int
0x180031026  lea     rcx, aToastLaunchHtt_3; "<toast launch=\"https://go.microsoft.co"...
0x18003102d  mov     r9d, 0FA0h; unsigned int
0x180031033  mov     r8d, 0BB8h; unsigned int
0x180031039  call    ?MakeSmartAppControlBlockToast@ToastHelper@@SAJPEAGIIIPEBG1@Z; ToastHelper::MakeSmartAppControlBlockToast(ushort *,uint,uint,uint,ushort const *,ushort const *)
0x18003103e  add     rsp, 38h
0x180031042  retn
```
