# SystemStoreLite::IsConnectedSID(IExecutionContextLite *,ushort const *,int *,ushort * *)

- ea: `0x180052a18`
- end: `0x180052b9a`
- name: `?IsConnectedSID@SystemStoreLite@@SAJPEAVIExecutionContextLite@@PEBGPEAHPEAPEAG@Z`
- size: `386`
- prototype: `__int64 __fastcall(struct IExecutionContextLite *, const unsigned __int16 *, int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180051ad0`
- `0x1800528b4`

## callees

- `0x18000cc9c`
- `0x18000e870`
- `0x180021a64`
- `0x180051250`
- `0x1800512f8`
- `0x180051fd4`
- `0x180052a18`
- `0x180053890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180052b1e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180052b1e`

## string_xrefs

- `0x180052a58`: `SystemStoreLite::IsConnectedSID`
- `0x180052b3b`: `pContext != nullptr && pIsConnected != nullptr && pCurrentUserSidString != nullptr`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemStoreLite::IsConnectedSID(
        struct IExecutionContextLite *a1,
        const unsigned __int16 *a2,
        int *a3,
        unsigned __int16 **a4)
{
  int StoredIdentityProperty; // eax
  unsigned __int16 **v10; // [rsp+20h] [rbp-49h]
  wchar_t *Str[3]; // [rsp+30h] [rbp-39h] BYREF
  int *v12[4]; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v13[11]; // [rsp+68h] [rbp-1h] BYREF
  int v14; // [rsp+D0h] [rbp+67h] BYREF

  memset(Str, 0, sizeof(Str));
  v14 = 0;
  v13[0] = "SystemStoreLite::IsConnectedSID";
  v13[1] = &v14;
  v13[2] = 0;
  v13[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
    "SystemStoreLite::IsConnectedSID",
    (const char *)0x44,
    0,
    (const unsigned __int16 *)v10);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v12, "SystemStoreLite::IsConnectedSID", &v14, 1u, &byte_1800819F0);
  if ( a1 && a3 && a2 )
  {
    *a3 = 0;
    StoredIdentityProperty = SystemStoreLite::GetStoredIdentityProperty(a1, a2, L"Keywords", Str, a4);
    v14 = StoredIdentityProperty;
    if ( StoredIdentityProperty == -2147023728 )
    {
      v14 = 0;
    }
    else if ( StoredIdentityProperty >= 0 )
    {
      if ( wcsstr(Str[0], L"Connected") )
        *a3 = 1;
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
        "SystemStoreLite::IsConnectedSID",
        0x5Fu,
        StoredIdentityProperty,
        "hr");
    }
  }
  else
  {
    v14 = -2147024809;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::IsConnectedSID",
      0x49u,
      -2147024809,
      "pContext != nullptr && pIsConnected != nullptr && pCurrentUserSidString != nullptr");
  }
  ErrorVerifier::CheckAgainstList((const char *)v12[3], *v12[2], (unsigned __int64)v12[1], v12[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v13);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
  return 0;
}

```

## disassembly

```asm
0x180052a18  push    rbp
0x180052a1a  push    rbx
0x180052a1b  push    rsi
0x180052a1c  push    rdi
0x180052a1d  push    r12
0x180052a1f  push    r14
0x180052a21  lea     rbp, [rsp-2Fh]
0x180052a26  sub     rsp, 98h
0x180052a2d  mov     r14, r9
0x180052a30  mov     rbx, r8
0x180052a33  mov     rdi, rdx
0x180052a36  mov     rsi, rcx
0x180052a39  mov     [rbp+57h+Str], 0
0x180052a41  mov     [rbp+57h+var_80], 0
0x180052a49  mov     [rbp+57h+var_88], 0
0x180052a51  mov     [rbp+57h+arg_0], 0
0x180052a58  lea     r12, aSystemstorelit; "SystemStoreLite::IsConnectedSID"
0x180052a5f  mov     [rbp+57h+var_58], r12
0x180052a63  lea     rax, [rbp+57h+arg_0]
0x180052a67  mov     [rbp+57h+var_50], rax
0x180052a6b  mov     [rbp+57h+var_48], 0
0x180052a73  mov     [rbp+57h+var_40], 0
0x180052a7b  xor     r9d, r9d; unsigned int
0x180052a7e  lea     r8d, [r9+44h]; char *
0x180052a82  mov     rdx, r12; char *
0x180052a85  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180052a8c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180052a91  nop
0x180052a92  lea     rax, byte_1800819F0
0x180052a99  mov     [rsp+0C0h+var_A0], rax; int *
0x180052a9e  mov     r9d, 1; unsigned __int64
0x180052aa4  lea     r8, [rbp+57h+arg_0]; int *
0x180052aa8  mov     rdx, r12; char *
0x180052aab  lea     rcx, [rbp+57h+var_78]; this
0x180052aaf  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x180052ab4  nop
0x180052ab5  test    rsi, rsi
0x180052ab8  jz      short loc_180052B31
0x180052aba  test    rbx, rbx
0x180052abd  jz      short loc_180052B31
0x180052abf  test    rdi, rdi
0x180052ac2  jz      short loc_180052B31
0x180052ac4  mov     dword ptr [rbx], 0
0x180052aca  mov     [rsp+0C0h+var_A0], r14; unsigned __int16 **
0x180052acf  lea     r9, [rbp+57h+Str]; unsigned __int16 **
0x180052ad3  lea     r8, aKeywords; "Keywords"
0x180052ada  mov     rdx, rdi; unsigned __int16 *
0x180052add  mov     rcx, rsi; struct IExecutionContextLite *
0x180052ae0  call    ?GetStoredIdentityProperty@SystemStoreLite@@SAJPEAVIExecutionContextLite@@PEBG1PEAPEAG2@Z; SystemStoreLite::GetStoredIdentityProperty(IExecutionContextLite *,ushort const *,ushort const *,ushort * *,ushort * *)
0x180052ae5  mov     [rbp+57h+arg_0], eax
0x180052ae8  cmp     eax, 80070490h
0x180052aed  jnz     short loc_180052AF8
0x180052aef  mov     [rbp+57h+arg_0], 0
0x180052af6  jmp     short loc_180052B5D
0x180052af8  test    eax, eax
0x180052afa  jns     short loc_180052B13
0x180052afc  lea     r8, aHr; "hr"
0x180052b03  mov     [rsp+0C0h+var_A0], r8
0x180052b08  mov     r9d, eax
0x180052b0b  mov     r8d, 5Fh ; '_'
0x180052b11  jmp     short loc_180052B4D
0x180052b13  lea     rdx, aConnected; "Connected"
0x180052b1a  mov     rcx, [rbp+57h+Str]; Str
0x180052b1e  call    cs:__imp_wcsstr
0x180052b24  test    rax, rax
0x180052b27  jz      short loc_180052B5D
0x180052b29  mov     dword ptr [rbx], 1
0x180052b2f  jmp     short loc_180052B5D
0x180052b31  mov     r9d, 80070057h; int
0x180052b37  mov     [rbp+57h+arg_0], r9d
0x180052b3b  lea     rax, aPcontextNullpt_2; "pContext != nullptr && pIsConnected != "...
0x180052b42  mov     [rsp+0C0h+var_A0], rax; char *
0x180052b47  mov     r8d, 49h ; 'I'; unsigned int
0x180052b4d  mov     rdx, r12; char *
0x180052b50  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180052b57  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180052b5c  nop
0x180052b5d  mov     r9, [rbp+57h+var_78]; int *
0x180052b61  mov     r8, [rbp+57h+var_70]; unsigned __int64
0x180052b65  mov     rdx, [rbp+57h+var_68]
0x180052b69  mov     edx, [rdx]; int
0x180052b6b  mov     rcx, [rbp+57h+var_60]; char *
0x180052b6f  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x180052b74  nop
0x180052b75  lea     rcx, [rbp+57h+var_58]
0x180052b79  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180052b7e  nop
0x180052b7f  lea     rcx, [rbp+57h+Str]
0x180052b83  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180052b88  xor     eax, eax
0x180052b8a  add     rsp, 98h
0x180052b91  pop     r14
0x180052b93  pop     r12
0x180052b95  pop     rdi
0x180052b96  pop     rsi
0x180052b97  pop     rbx
0x180052b98  pop     rbp
0x180052b99  retn
```
