# W3WP_HOST::RequestCounters(void)

- ea: `0x1800066c4`
- end: `0x180006829`
- name: `?RequestCounters@W3WP_HOST@@QEAAXXZ`
- size: `357`
- prototype: `void __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007480`

## callees

- `0x1800066c4`
- `0x180007c18`
- `0x180009630`
- `0x18000d010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006729`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006729`
- `iisutil!PuDbgPrint` at `0x18000670a`
- `iisutil!PuDbgPrint` at `0x180006802`
- `iisutil!PuDbgPrint` at `0x18000670a`
- `iisutil!PuDbgPrint` at `0x180006802`

## string_xrefs

- `0x180006703`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x1800067f6`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180006746`: `GetProtocolManager`
- `0x1800067b0`: `Could not get interface IProtocolManagerIisCoreCounters from iiscore.dll.  Error = 0x%x\n`

## pseudocode

```c
void __fastcall W3WP_HOST::RequestCounters(W3WP_HOST *this)
{
  W3WP_HOST *v1; // rbx
  const unsigned __int16 *Str; // rax
  int ProtocolManagerEntry; // edi
  __int64 v4; // r8
  const char *v5; // rax
  W3WP_HOST *v6; // [rsp+40h] [rbp+8h] BYREF
  struct PROTOCOL_MANAGER_ENTRY *v7; // [rsp+48h] [rbp+10h] BYREF

  v6 = this;
  v1 = g_pW3WPHost;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      3627,
      "W3WP_HOST::RequestCounters",
      "Process Model Request Counters called\n");
  v7 = 0;
  v6 = 0;
  Str = STRU::QueryStr((W3WP_HOST *)((char *)v1 + 400));
  ProtocolManagerEntry = PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(
                           (PROTOCOL_MANAGER_LIST ***)v1 + 40,
                           Str,
                           L"GetProtocolManager",
                           &v7,
                           0);
  if ( ProtocolManagerEntry >= 0
    || (WP_IPM::ReportCounters(*((WP_IPM **)v1 + 11), (unsigned __int8 *)&qword_180010090, 0),
        ProtocolManagerEntry != -2147023728) )
  {
    if ( (*(int (__fastcall **)(_QWORD, __int64, W3WP_HOST **))(**((_QWORD **)v7 + 32) + 24LL))(
           *((_QWORD *)v7 + 32),
           100,
           &v6) >= 0 )
    {
      if ( (*(int (__fastcall **)(W3WP_HOST *))(*(_QWORD *)v6 + 16LL))(v6) >= 0 || (g_dwDebugFlags & 3) == 0 )
        goto LABEL_12;
      v4 = 3703;
      v5 = "RequestCounters() failed with 0x%x \n";
    }
    else
    {
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_12;
      v4 = 3687;
      v5 = "Could not get interface IProtocolManagerIisCoreCounters from iiscore.dll.  Error = 0x%x\n";
    }
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      v4,
      "W3WP_HOST::RequestCounters",
      v5);
LABEL_12:
    if ( v6 )
      (*(void (__fastcall **)(W3WP_HOST *))(*(_QWORD *)v6 + 8LL))(v6);
  }
}

```

## disassembly

```asm
0x1800066c4  mov     [rsp+arg_10], rbx
0x1800066c9  mov     [rsp+arg_0], rcx
0x1800066ce  push    rdi
0x1800066cf  sub     rsp, 30h
0x1800066d3  test    byte ptr cs:g_dwDebugFlags, 3
0x1800066da  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800066e1  jz      short loc_180006710
0x1800066e3  mov     rcx, cs:g_pDebug
0x1800066ea  lea     rax, aProcessModelRe_0; "Process Model Request Counters called\n"
0x1800066f1  lea     r9, aW3wpHostReques_0; "W3WP_HOST::RequestCounters"
0x1800066f8  mov     qword ptr [rsp+38h+var_18], rax
0x1800066fd  mov     r8d, 0E2Bh
0x180006703  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000670a  call    cs:__imp_PuDbgPrint
0x180006710  lea     rcx, [rbx+190h]
0x180006717  mov     [rsp+38h+arg_8], 0
0x180006720  mov     [rsp+38h+arg_0], 0
0x180006729  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000672f  lea     rcx, [rbx+140h]; this
0x180006736  mov     [rsp+38h+var_18], 0; int
0x18000673e  mov     rdx, rax; unsigned __int16 *
0x180006741  lea     r9, [rsp+38h+arg_8]; struct PROTOCOL_MANAGER_ENTRY **
0x180006746  lea     r8, aGetprotocolman; "GetProtocolManager"
0x18000674d  call    ?GetProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@H@Z; PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *,int)
0x180006752  mov     edi, eax
0x180006754  test    eax, eax
0x180006756  jns     short loc_180006777
0x180006758  mov     rcx, [rbx+58h]; this
0x18000675c  lea     rdx, qword_180010090; unsigned __int8 *
0x180006763  xor     r8d, r8d; unsigned int
0x180006766  call    ?ReportCounters@WP_IPM@@QEAAXPEAEK@Z; WP_IPM::ReportCounters(uchar *,ulong)
0x18000676b  cmp     edi, 80070490h
0x180006771  jz      loc_18000681E
0x180006777  mov     rax, [rsp+38h+arg_8]
0x18000677c  lea     r8, [rsp+38h+arg_0]
0x180006781  mov     edx, 64h ; 'd'
0x180006786  mov     rcx, [rax+100h]
0x18000678d  mov     rax, [rcx]
0x180006790  mov     rax, [rax+18h]
0x180006794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006799  test    eax, eax
0x18000679b  jns     short loc_1800067B9
0x18000679d  test    byte ptr cs:g_dwDebugFlags, 3
0x1800067a4  jz      short loc_180006808
0x1800067a6  mov     [rsp+38h+var_10], eax
0x1800067aa  mov     r8d, 0E67h
0x1800067b0  lea     rax, aCouldNotGetInt_0; "Could not get interface IProtocolManage"...
0x1800067b7  jmp     short loc_1800067E8
0x1800067b9  mov     rcx, [rsp+38h+arg_0]
0x1800067be  mov     rax, [rcx]
0x1800067c1  mov     rax, [rax+10h]
0x1800067c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067ca  test    eax, eax
0x1800067cc  jns     short loc_180006808
0x1800067ce  test    byte ptr cs:g_dwDebugFlags, 3
0x1800067d5  jz      short loc_180006808
0x1800067d7  mov     [rsp+38h+var_10], eax
0x1800067db  mov     r8d, 0E77h
0x1800067e1  lea     rax, aRequestcounter; "RequestCounters() failed with 0x%x \n"
0x1800067e8  mov     rcx, cs:g_pDebug
0x1800067ef  lea     r9, aW3wpHostReques_0; "W3WP_HOST::RequestCounters"
0x1800067f6  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800067fd  mov     qword ptr [rsp+38h+var_18], rax
0x180006802  call    cs:__imp_PuDbgPrint
0x180006808  mov     rcx, [rsp+38h+arg_0]
0x18000680d  test    rcx, rcx
0x180006810  jz      short loc_18000681E
0x180006812  mov     rax, [rcx]
0x180006815  mov     rax, [rax+8]
0x180006819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000681e  mov     rbx, [rsp+38h+arg_10]
0x180006823  add     rsp, 30h
0x180006827  pop     rdi
0x180006828  retn
```
