# CProfileTask_OnDelete::Execute(void)

- ea: `0x180006b50`
- end: `0x180006cfc`
- name: `?Execute@CProfileTask_OnDelete@@UEAAJXZ`
- size: `428`
- prototype: `__int64 __fastcall(const wchar_t **this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001794`
- `0x180001b9c`
- `0x180003714`
- `0x180006040`
- `0x180006b50`
- `0x18000b388`
- `0x18000cde4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006b7a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006b7a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006bcd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006bcd`

## string_xrefs

- `0x180006cb4`: `SOFTWARE\Microsoft\Windows Search\UninstalledStoreApps`
- `0x180006c6b`: `SOFTWARE\Microsoft\Windows Search\UninstalledStoreApps\%s`
- `0x180006c91`: `Deleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProfileTask_OnDelete::Execute(const wchar_t **this)
{
  int v2; // esi
  __int64 v3; // rcx
  __int64 v4; // rax
  unsigned __int64 v5; // r14
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // kr00_8
  wchar_t *v8; // rax
  wchar_t *v9; // rdi
  HKEY v10; // rcx
  unsigned int v11; // r9d
  HKEY v12; // rcx
  unsigned int v13; // r9d
  LPVOID v14; // rcx
  unsigned int v16; // [rsp+28h] [rbp-8h]
  unsigned int v17; // [rsp+28h] [rbp-8h]
  __int64 v18; // [rsp+68h] [rbp+38h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+40h] BYREF
  wchar_t *v20; // [rsp+78h] [rbp+48h]

  InitOnceExecuteOnce(
    &g_initOnceOnCDPLOverrideCheck,
    _lambda_0c3966be9d17dfc0a588dbf2a008d6d4_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( !g_isCDplSupported || (v2 = CProfileTask_OnDelete::_CleanupCDPLCatalog((CProfileTask_OnDelete *)this), v2 >= 0) )
    v2 = CProfileTask::DeletePerUserSearchRootsAndScopeRules((CProfileTask *)this, this[2], this[3]);
  ppv = 0;
  if ( CoCreateInstance(
         &GUID_b52d54bb_4818_4eb9_aa80_f9eacd371df8,
         0,
         4u,
         &GUID_993eceb0_6f1b_49fe_8ba2_21b6a5317de1,
         &ppv) < 0 )
  {
    v4 = -1;
    do
      ++v4;
    while ( this[2][v4] );
    v5 = v4 + 56;
    v7 = v4 + 56;
    v6 = 2 * (v4 + 56);
    if ( !is_mul_ok(v7, 2u) )
      v6 = -1;
    v8 = (wchar_t *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    v20 = v8;
    if ( v8 )
    {
      if ( (int)StringCchPrintfW(v8, v5, L"SOFTWARE\\Microsoft\\Windows Search\\UninstalledStoreApps\\%s", this[2]) >= 0 )
      {
        LODWORD(v18) = 1;
        if ( !WSearchRegSetKeyValue(v10, v9, L"Deleted", v11, &v18, v16) )
          WSearchRegSetKeyValue(
            v12,
            L"SOFTWARE\\Microsoft\\Windows Search\\UninstalledStoreApps",
            L"CheckOnStartup",
            v13,
            &v18,
            v17);
      }
    }
    if ( v9 )
      operator delete(v9);
  }
  else
  {
    v18 = 0;
    if ( (*(int (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, &v18) >= 0 )
      (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v18 + 40LL))(v18, this[2]);
    v3 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    }
  }
  v14 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180006b50  mov     [rsp-28h+arg_0], rbx
0x180006b55  push    rbp
0x180006b56  push    rsi
0x180006b57  push    rdi
0x180006b58  push    r14
0x180006b5a  push    r15
0x180006b5c  mov     rbp, rsp
0x180006b5f  sub     rsp, 30h
0x180006b63  mov     rbx, rcx
0x180006b66  xor     r9d, r9d; Context
0x180006b69  xor     r8d, r8d; Parameter
0x180006b6c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_0c3966be9d17dfc0a588dbf2a008d6d4_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180006b73  lea     rcx, ?g_initOnceOnCDPLOverrideCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180006b7a  call    cs:__imp_InitOnceExecuteOnce
0x180006b80  xor     r15d, r15d
0x180006b83  cmp     cs:?g_isCDplSupported@@3_NA, r15b; bool g_isCDplSupported
0x180006b8a  jz      short loc_180006B9A
0x180006b8c  mov     rcx, rbx; this
0x180006b8f  call    ?_CleanupCDPLCatalog@CProfileTask_OnDelete@@AEAAJXZ; CProfileTask_OnDelete::_CleanupCDPLCatalog(void)
0x180006b94  mov     esi, eax
0x180006b96  test    eax, eax
0x180006b98  js      short loc_180006BAC
0x180006b9a  mov     r8, [rbx+18h]; wchar_t *
0x180006b9e  mov     rdx, [rbx+10h]; wchar_t *
0x180006ba2  mov     rcx, rbx; this
0x180006ba5  call    ?DeletePerUserSearchRootsAndScopeRules@CProfileTask@@QEAAJPEB_W0@Z; CProfileTask::DeletePerUserSearchRootsAndScopeRules(wchar_t const *,wchar_t const *)
0x180006baa  mov     esi, eax
0x180006bac  mov     [rbp+arg_10], r15
0x180006bb0  lea     rax, [rbp+arg_10]
0x180006bb4  mov     [rsp+30h+ppv], rax; ppv
0x180006bb9  lea     r9, _GUID_993eceb0_6f1b_49fe_8ba2_21b6a5317de1; riid
0x180006bc0  xor     edx, edx; pUnkOuter
0x180006bc2  lea     r8d, [rdx+4]; dwClsContext
0x180006bc6  lea     rcx, _GUID_b52d54bb_4818_4eb9_aa80_f9eacd371df8; rclsid
0x180006bcd  call    cs:__imp_CoCreateInstance
0x180006bd3  test    eax, eax
0x180006bd5  js      short loc_180006C27
0x180006bd7  mov     [rbp+arg_8], r15
0x180006bdb  mov     rcx, [rbp+arg_10]
0x180006bdf  mov     rax, [rcx]
0x180006be2  lea     rdx, [rbp+arg_8]
0x180006be6  mov     rax, [rax+20h]
0x180006bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bef  test    eax, eax
0x180006bf1  js      short loc_180006C08
0x180006bf3  mov     rcx, [rbp+arg_8]
0x180006bf7  mov     rax, [rcx]
0x180006bfa  mov     rdx, [rbx+10h]
0x180006bfe  mov     rax, [rax+28h]
0x180006c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c07  nop
0x180006c08  mov     rcx, [rbp+arg_8]
0x180006c0c  test    rcx, rcx
0x180006c0f  jz      short loc_180006C22
0x180006c11  mov     [rbp+arg_8], r15
0x180006c15  mov     rax, [rcx]
0x180006c18  mov     rax, [rax+10h]
0x180006c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c21  nop
0x180006c22  jmp     loc_180006CCF
0x180006c27  mov     rcx, [rbx+10h]
0x180006c2b  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006c2f  mov     rax, r8
0x180006c32  inc     rax
0x180006c35  cmp     [rcx+rax*2], r15w
0x180006c3a  jnz     short loc_180006C32
0x180006c3c  lea     r14, [rax+38h]
0x180006c40  mov     eax, 2
0x180006c45  mul     r14
0x180006c48  cmovb   rax, r8
0x180006c4c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006c53  mov     rcx, rax; unsigned __int64
0x180006c56  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006c5b  mov     rdi, rax
0x180006c5e  mov     [rbp+arg_18], rax
0x180006c62  test    rax, rax
0x180006c65  jz      short loc_180006CC1
0x180006c67  mov     r9, [rbx+10h]
0x180006c6b  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows Search\\Un"...
0x180006c72  mov     rdx, r14; unsigned __int64
0x180006c75  mov     rcx, rax; wchar_t *
0x180006c78  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180006c7d  test    eax, eax
0x180006c7f  js      short loc_180006CC1
0x180006c81  mov     dword ptr [rbp+arg_8], 1
0x180006c88  lea     rax, [rbp+arg_8]
0x180006c8c  mov     [rsp+30h+ppv], rax; void *
0x180006c91  lea     r8, aDeleted; "Deleted"
0x180006c98  mov     rdx, rdi; wchar_t *
0x180006c9b  call    ?WSearchRegSetKeyValue@@YAJPEAUHKEY__@@PEB_W1KPEBXK@Z; WSearchRegSetKeyValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong,void const *,ulong)
0x180006ca0  test    eax, eax
0x180006ca2  jnz     short loc_180006CC1
0x180006ca4  lea     rax, [rbp+arg_8]
0x180006ca8  mov     [rsp+30h+ppv], rax; void *
0x180006cad  lea     r8, aCheckonstartup; "CheckOnStartup"
0x180006cb4  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows Search\\Un"...
0x180006cbb  call    ?WSearchRegSetKeyValue@@YAJPEAUHKEY__@@PEB_W1KPEBXK@Z; WSearchRegSetKeyValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong,void const *,ulong)
0x180006cc0  nop
0x180006cc1  test    rdi, rdi
0x180006cc4  jz      short loc_180006CCF
0x180006cc6  mov     rcx, rdi; Block
0x180006cc9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006cce  nop
0x180006ccf  mov     rcx, [rbp+arg_10]
0x180006cd3  test    rcx, rcx
0x180006cd6  jz      short loc_180006CE9
0x180006cd8  mov     [rbp+arg_10], r15
0x180006cdc  mov     rax, [rcx]
0x180006cdf  mov     rax, [rax+10h]
0x180006ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ce8  nop
0x180006ce9  mov     eax, esi
0x180006ceb  mov     rbx, [rsp+30h+arg_0]
0x180006cf0  add     rsp, 30h
0x180006cf4  pop     r15
0x180006cf6  pop     r14
0x180006cf8  pop     rdi
0x180006cf9  pop     rsi
0x180006cfa  pop     rbp
0x180006cfb  retn
```
