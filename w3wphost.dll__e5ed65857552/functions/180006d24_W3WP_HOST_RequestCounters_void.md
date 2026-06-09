# W3WP_HOST::RequestCounters(void)

- ea: `0x180006d24`
- end: `0x180006e9c`
- name: `?RequestCounters@W3WP_HOST@@QEAAXXZ`
- size: `376`
- prototype: `void __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007c20`

## callees

- `0x180006d24`
- `0x180008438`
- `0x18000a0f4`
- `0x18000e010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006d8f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006d8f`
- `iisutil!PuDbgPrint` at `0x180006d6a`
- `iisutil!PuDbgPrint` at `0x180006e6e`
- `iisutil!PuDbgPrint` at `0x180006d6a`
- `iisutil!PuDbgPrint` at `0x180006e6e`

## string_xrefs

- `0x180006d63`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180006e62`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180006db2`: `GetProtocolManager`
- `0x180006e1c`: `Could not get interface IProtocolManagerIisCoreCounters from iiscore.dll.  Error = 0x%x\n`

## pseudocode

```c
void __fastcall W3WP_HOST::RequestCounters(W3WP_HOST *this)
{
  W3WP_HOST *v1; // rbx
  const unsigned __int16 *Str; // rax
  int ProtocolManagerEntry; // edi
  int v4; // eax
  int v5; // eax
  int v6; // [rsp+28h] [rbp-10h]
  int v7; // [rsp+28h] [rbp-10h]
  W3WP_HOST *v8; // [rsp+40h] [rbp+8h] BYREF
  struct PROTOCOL_MANAGER_ENTRY *v9; // [rsp+48h] [rbp+10h] BYREF

  v8 = this;
  v1 = g_pW3WPHost;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      3627,
      "W3WP_HOST::RequestCounters",
      "Process Model Request Counters called\n");
  v9 = 0;
  v8 = 0;
  Str = STRU::QueryStr((W3WP_HOST *)((char *)v1 + 400));
  ProtocolManagerEntry = PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(
                           (PROTOCOL_MANAGER_LIST ***)v1 + 40,
                           Str,
                           L"GetProtocolManager",
                           &v9,
                           0);
  if ( ProtocolManagerEntry >= 0
    || (WP_IPM::ReportCounters(*((WP_IPM **)v1 + 11), (unsigned __int8 *)&qword_1800110A0, 0),
        ProtocolManagerEntry != -2147023728) )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, W3WP_HOST **))(**((_QWORD **)v9 + 32) + 24LL))(
           *((_QWORD *)v9 + 32),
           100,
           &v8);
    if ( v4 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(W3WP_HOST *))(*(_QWORD *)v8 + 16LL))(v8);
      if ( v5 < 0 && (g_dwDebugFlags & 3) != 0 )
      {
        v7 = v5;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
          3703,
          "W3WP_HOST::RequestCounters",
          "RequestCounters() failed with 0x%x \n",
          v7);
      }
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      v6 = v4;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        3687,
        "W3WP_HOST::RequestCounters",
        "Could not get interface IProtocolManagerIisCoreCounters from iiscore.dll.  Error = 0x%x\n",
        v6);
    }
    if ( v8 )
      (*(void (__fastcall **)(W3WP_HOST *))(*(_QWORD *)v8 + 8LL))(v8);
  }
}

```

## disassembly

```asm
0x180006d24  mov     [rsp+arg_10], rbx
0x180006d29  mov     [rsp+arg_0], rcx
0x180006d2e  push    rdi
0x180006d2f  sub     rsp, 30h
0x180006d33  test    byte ptr cs:g_dwDebugFlags, 3
0x180006d3a  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180006d41  jz      short loc_180006D76
0x180006d43  mov     rcx, cs:g_pDebug
0x180006d4a  lea     rax, aProcessModelRe_0; "Process Model Request Counters called\n"
0x180006d51  lea     r9, aW3wpHostReques_0; "W3WP_HOST::RequestCounters"
0x180006d58  mov     qword ptr [rsp+38h+var_18], rax
0x180006d5d  mov     r8d, 0E2Bh
0x180006d63  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006d6a  call    cs:__imp_PuDbgPrint
0x180006d71  nop     dword ptr [rax+rax+00h]
0x180006d76  lea     rcx, [rbx+190h]
0x180006d7d  mov     [rsp+38h+arg_8], 0
0x180006d86  mov     [rsp+38h+arg_0], 0
0x180006d8f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006d96  nop     dword ptr [rax+rax+00h]
0x180006d9b  lea     rcx, [rbx+140h]; this
0x180006da2  mov     [rsp+38h+var_18], 0; int
0x180006daa  mov     rdx, rax; unsigned __int16 *
0x180006dad  lea     r9, [rsp+38h+arg_8]; struct PROTOCOL_MANAGER_ENTRY **
0x180006db2  lea     r8, aGetprotocolman; "GetProtocolManager"
0x180006db9  call    ?GetProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@H@Z; PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *,int)
0x180006dbe  mov     edi, eax
0x180006dc0  test    eax, eax
0x180006dc2  jns     short loc_180006DE3
0x180006dc4  mov     rcx, [rbx+58h]; this
0x180006dc8  lea     rdx, qword_1800110A0; unsigned __int8 *
0x180006dcf  xor     r8d, r8d; unsigned int
0x180006dd2  call    ?ReportCounters@WP_IPM@@QEAAXPEAEK@Z; WP_IPM::ReportCounters(uchar *,ulong)
0x180006dd7  cmp     edi, 80070490h
0x180006ddd  jz      loc_180006E90
0x180006de3  mov     rax, [rsp+38h+arg_8]
0x180006de8  lea     r8, [rsp+38h+arg_0]
0x180006ded  mov     edx, 64h ; 'd'
0x180006df2  mov     rcx, [rax+100h]
0x180006df9  mov     rax, [rcx]
0x180006dfc  mov     rax, [rax+18h]
0x180006e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e05  test    eax, eax
0x180006e07  jns     short loc_180006E25
0x180006e09  test    byte ptr cs:g_dwDebugFlags, 3
0x180006e10  jz      short loc_180006E7A
0x180006e12  mov     [rsp+38h+var_10], eax
0x180006e16  mov     r8d, 0E67h
0x180006e1c  lea     rax, aCouldNotGetInt_0; "Could not get interface IProtocolManage"...
0x180006e23  jmp     short loc_180006E54
0x180006e25  mov     rcx, [rsp+38h+arg_0]
0x180006e2a  mov     rax, [rcx]
0x180006e2d  mov     rax, [rax+10h]
0x180006e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e36  test    eax, eax
0x180006e38  jns     short loc_180006E7A
0x180006e3a  test    byte ptr cs:g_dwDebugFlags, 3
0x180006e41  jz      short loc_180006E7A
0x180006e43  mov     [rsp+38h+var_10], eax
0x180006e47  mov     r8d, 0E77h
0x180006e4d  lea     rax, aRequestcounter; "RequestCounters() failed with 0x%x \n"
0x180006e54  mov     rcx, cs:g_pDebug
0x180006e5b  lea     r9, aW3wpHostReques_0; "W3WP_HOST::RequestCounters"
0x180006e62  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006e69  mov     qword ptr [rsp+38h+var_18], rax
0x180006e6e  call    cs:__imp_PuDbgPrint
0x180006e75  nop     dword ptr [rax+rax+00h]
0x180006e7a  mov     rcx, [rsp+38h+arg_0]
0x180006e7f  test    rcx, rcx
0x180006e82  jz      short loc_180006E90
0x180006e84  mov     rax, [rcx]
0x180006e87  mov     rax, [rax+8]
0x180006e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e90  mov     rbx, [rsp+38h+arg_10]
0x180006e95  add     rsp, 30h
0x180006e99  pop     rdi
0x180006e9a  retn
```
