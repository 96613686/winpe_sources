# MgLibpOpenLdapConnection(ushort const *,CLdap *,ushort * *)

- ea: `0x180011574`
- end: `0x18001175c`
- name: `?MgLibpOpenLdapConnection@@YAKPEBGPEAVCLdap@@PEAPEAG@Z`
- size: `488`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, struct CLdap *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800111a0`

## callees

- `0x180011574`
- `0x180011764`
- `0x180017010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800116df`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800116f9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011713`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800116df`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800116f9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011713`
- `WdsCommonLib!?GetDSInfo@@YAKHPEBGPEAPEAG1@Z` at `0x1800115e8`
- `WdsCommonLib!?GetDSInfo@@YAKHPEBGPEAPEAG1@Z` at `0x1800115e8`
- `WdsCommonLib!?Open@CLdap@@QEAAKPEBGKPEBUl_timeval@@00K@Z` at `0x1800116aa`
- `WdsCommonLib!?Open@CLdap@@QEAAKPEBGKPEBUl_timeval@@00K@Z` at `0x1800116aa`
- `WdsCommonLib!?GetDefaultContext@CLdap@@SAKPEBGPEAPEAG0K@Z` at `0x180011658`
- `WdsCommonLib!?GetDefaultContext@CLdap@@SAKPEBGPEAPEAG0K@Z` at `0x180011658`
- `WdsCommonLib!?GetConnectTimeout@CLdap@@SAPEBUl_timeval@@XZ` at `0x18001167b`
- `WdsCommonLib!?GetConnectTimeout@CLdap@@SAPEBUl_timeval@@XZ` at `0x18001167b`

## string_xrefs

- `0x1800115af`: `-> MgLibpOpenLdapConnection`
- `0x1800115cf`: `MgLibpOpenLdapConnection: Domain=%s`
- `0x18001161b`: `MgLibpOpenLdapConnection: Domain FQDN=%s`
- `0x180011637`: `MgLibpOpenLdapConnection: Domain Controller=%s`
- `0x180011733`: `<- MgLibpOpenLdapConnection=%x`

## pseudocode

```c
__int64 __fastcall MgLibpOpenLdapConnection(const unsigned __int16 *a1, struct CLdap *a2, unsigned __int16 **a3)
{
  __int64 DSInfo; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  const unsigned __int16 *v11; // rbx
  const struct l_timeval *ConnectTimeout; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned __int16 *v15; // rcx
  unsigned __int16 *v17; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v18; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int16 *v19; // [rsp+78h] [rbp+28h] BYREF

  v17 = 0;
  v19 = 0;
  v18 = 0;
  if ( g_ErrLibTraceFunctionEx )
    g_ErrLibTraceFunctionEx(0x10000u, L"-> MgLibpOpenLdapConnection");
  if ( g_ErrLibTraceFunction )
    g_ErrLibTraceFunction(L"MgLibpOpenLdapConnection: Domain=%s", a1);
  DSInfo = GetDSInfo(0, a1, &v18, &v17);
  if ( (unsigned int)ElValidateWin32_4(DSInfo, v7, v8, 122) )
    goto LABEL_12;
  if ( g_ErrLibTraceFunction )
  {
    g_ErrLibTraceFunction(L"MgLibpOpenLdapConnection: Domain FQDN=%s", v17);
    if ( g_ErrLibTraceFunction )
      g_ErrLibTraceFunction(L"MgLibpOpenLdapConnection: Domain Controller=%s", v18);
  }
  DSInfo = CLdap::GetDefaultContext(L"DefaultNamingContext", &v19, v17, 0x185u);
  if ( (unsigned int)ElValidateWin32_4(DSInfo, v9, v10, 134)
    || (v11 = v19,
        ConnectTimeout = (const struct l_timeval *)CLdap::GetConnectTimeout(),
        DSInfo = CLdap::Open(a2, v18, 0x185u, ConnectTimeout, v11, 0, 0x486u),
        (unsigned int)ElValidateWin32_4(DSInfo, v13, v14, 145)) )
  {
LABEL_12:
    v15 = v19;
  }
  else
  {
    v15 = v19;
    *a3 = v19;
  }
  if ( (_DWORD)DSInfo && v15 )
  {
    operator delete(v15);
    v19 = 0;
  }
  if ( v17 )
  {
    operator delete(v17);
    v17 = 0;
  }
  if ( v18 )
  {
    operator delete(v18);
    v18 = 0;
  }
  if ( g_ErrLibTraceFunctionEx )
    g_ErrLibTraceFunctionEx(0x10000u, L"<- MgLibpOpenLdapConnection=%x", (unsigned int)DSInfo);
  return (unsigned int)DSInfo;
}

```

## disassembly

```asm
0x180011574  mov     [rsp-8+arg_0], rbx
0x180011579  mov     [rsp-8+arg_8], rsi
0x18001157e  mov     [rsp-8+arg_10], rdi
0x180011583  push    rbp
0x180011584  mov     rbp, rsp
0x180011587  sub     rsp, 50h
0x18001158b  and     [rbp+var_10], 0
0x180011590  mov     rdi, r8
0x180011593  and     [rbp+arg_18], 0
0x180011598  mov     rsi, rdx
0x18001159b  and     [rbp+var_8], 0
0x1800115a0  mov     rbx, rcx
0x1800115a3  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800115aa  test    rax, rax
0x1800115ad  jz      short loc_1800115C0
0x1800115af  lea     rdx, aMglibpopenldap_0; "-> MgLibpOpenLdapConnection"
0x1800115b6  mov     ecx, 10000h
0x1800115bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115c0  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800115c7  test    rax, rax
0x1800115ca  jz      short loc_1800115DB
0x1800115cc  mov     rdx, rbx
0x1800115cf  lea     rcx, aMglibpopenldap_1; "MgLibpOpenLdapConnection: Domain=%s"
0x1800115d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115db  lea     r9, [rbp+var_10]
0x1800115df  mov     rdx, rbx
0x1800115e2  lea     r8, [rbp+var_8]
0x1800115e6  xor     ecx, ecx
0x1800115e8  call    cs:__imp_?GetDSInfo@@YAKHPEBGPEAPEAG1@Z; GetDSInfo(int,ushort const *,ushort * *,ushort * *)
0x1800115ef  nop     dword ptr [rax+rax+00h]
0x1800115f4  mov     ecx, eax
0x1800115f6  mov     r9d, 7Ah ; 'z'
0x1800115fc  mov     ebx, eax
0x1800115fe  call    ElValidateWin32_4
0x180011603  test    eax, eax
0x180011605  jnz     loc_1800116D2
0x18001160b  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180011612  test    rax, rax
0x180011615  jz      short loc_180011643
0x180011617  mov     rdx, [rbp+var_10]
0x18001161b  lea     rcx, aMglibpopenldap; "MgLibpOpenLdapConnection: Domain FQDN=%"...
0x180011622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011627  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001162e  test    rax, rax
0x180011631  jz      short loc_180011643
0x180011633  mov     rdx, [rbp+var_8]
0x180011637  lea     rcx, aMglibpopenldap_3; "MgLibpOpenLdapConnection: Domain Contro"...
0x18001163e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011643  mov     r8, [rbp+var_10]
0x180011647  lea     rdx, [rbp+arg_18]
0x18001164b  mov     r9d, 185h
0x180011651  lea     rcx, aDefaultnamingc; "DefaultNamingContext"
0x180011658  call    cs:__imp_?GetDefaultContext@CLdap@@SAKPEBGPEAPEAG0K@Z; CLdap::GetDefaultContext(ushort const *,ushort * *,ushort const *,ulong)
0x18001165f  nop     dword ptr [rax+rax+00h]
0x180011664  mov     ecx, eax
0x180011666  mov     r9d, 86h
0x18001166c  mov     ebx, eax
0x18001166e  call    ElValidateWin32_4
0x180011673  test    eax, eax
0x180011675  jnz     short loc_1800116D2
0x180011677  mov     rbx, [rbp+arg_18]
0x18001167b  call    cs:__imp_?GetConnectTimeout@CLdap@@SAPEBUl_timeval@@XZ; CLdap::GetConnectTimeout(void)
0x180011682  nop     dword ptr [rax+rax+00h]
0x180011687  mov     rdx, [rbp+var_8]
0x18001168b  mov     r8d, 185h
0x180011691  mov     [rsp+50h+var_20], 486h
0x180011699  mov     r9, rax
0x18001169c  and     [rsp+50h+var_28], 0
0x1800116a2  mov     rcx, rsi
0x1800116a5  mov     [rsp+50h+var_30], rbx
0x1800116aa  call    cs:__imp_?Open@CLdap@@QEAAKPEBGKPEBUl_timeval@@00K@Z; CLdap::Open(ushort const *,ulong,l_timeval const *,ushort const *,ushort const *,ulong)
0x1800116b1  nop     dword ptr [rax+rax+00h]
0x1800116b6  mov     ecx, eax
0x1800116b8  mov     r9d, 91h
0x1800116be  mov     ebx, eax
0x1800116c0  call    ElValidateWin32_4
0x1800116c5  test    eax, eax
0x1800116c7  jnz     short loc_1800116D2
0x1800116c9  mov     rcx, [rbp+arg_18]
0x1800116cd  mov     [rdi], rcx
0x1800116d0  jmp     short loc_1800116D6
0x1800116d2  mov     rcx, [rbp+arg_18]
0x1800116d6  test    ebx, ebx
0x1800116d8  jz      short loc_1800116F0
0x1800116da  test    rcx, rcx
0x1800116dd  jz      short loc_1800116F0
0x1800116df  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800116e6  nop     dword ptr [rax+rax+00h]
0x1800116eb  and     [rbp+arg_18], 0
0x1800116f0  mov     rcx, [rbp+var_10]
0x1800116f4  test    rcx, rcx
0x1800116f7  jz      short loc_18001170A
0x1800116f9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011700  nop     dword ptr [rax+rax+00h]
0x180011705  and     [rbp+var_10], 0
0x18001170a  mov     rcx, [rbp+var_8]
0x18001170e  test    rcx, rcx
0x180011711  jz      short loc_180011724
0x180011713  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001171a  nop     dword ptr [rax+rax+00h]
0x18001171f  and     [rbp+var_8], 0
0x180011724  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001172b  test    rax, rax
0x18001172e  jz      short loc_180011744
0x180011730  mov     r8d, ebx
0x180011733  lea     rdx, aMglibpopenldap_2; "<- MgLibpOpenLdapConnection=%x"
0x18001173a  mov     ecx, 10000h
0x18001173f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011744  mov     rsi, [rsp+50h+arg_8]
0x180011749  mov     eax, ebx
0x18001174b  mov     rbx, [rsp+50h+arg_0]
0x180011750  mov     rdi, [rsp+50h+arg_10]
0x180011755  add     rsp, 50h
0x180011759  pop     rbp
0x18001175a  retn
```
