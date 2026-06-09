# CPxeProviderHandler::SaveProvidersOrder(void)

- ea: `0x1800065b4`
- end: `0x180006769`
- name: `?SaveProvidersOrder@CPxeProviderHandler@@AEAAKXZ`
- size: `437`
- prototype: `unsigned int __fastcall(CPxeProviderHandler *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005e44`
- `0x180006d2c`

## callees

- `0x180001acc`
- `0x1800065b4`
- `0x1800070c8`
- `0x180011a62`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800065dd`
- `KERNEL32!EnterCriticalSection` at `0x180006633`
- `KERNEL32!EnterCriticalSection` at `0x1800065dd`
- `KERNEL32!EnterCriticalSection` at `0x180006633`
- `KERNEL32!LeaveCriticalSection` at `0x180006647`
- `KERNEL32!LeaveCriticalSection` at `0x18000672d`
- `KERNEL32!LeaveCriticalSection` at `0x180006647`
- `KERNEL32!LeaveCriticalSection` at `0x18000672d`
- `ADVAPI32!RegCloseKey` at `0x1800066a0`
- `ADVAPI32!RegCloseKey` at `0x180006743`
- `ADVAPI32!RegCloseKey` at `0x1800066a0`
- `ADVAPI32!RegCloseKey` at `0x180006743`
- `ADVAPI32!RegOpenKeyExW` at `0x1800066cd`
- `ADVAPI32!RegOpenKeyExW` at `0x1800066cd`
- `WdsCommonLib!?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z` at `0x18000671e`
- `WdsCommonLib!?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z` at `0x18000671e`
- `WdsCommonLib!?WcsDup@@YAPEAGPEBG@Z` at `0x180006675`
- `WdsCommonLib!?WcsDup@@YAPEAGPEBG@Z` at `0x180006675`
- `WdsCommonLib!?SetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEBGK@Z` at `0x1800066fe`
- `WdsCommonLib!?SetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEBGK@Z` at `0x1800066fe`

## string_xrefs

- `0x1800066bf`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE`

## pseudocode

```c
__int64 __fastcall CPxeProviderHandler::SaveProvidersOrder(CPxeProviderHandler *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r12
  unsigned __int64 v3; // rbp
  unsigned int v4; // esi
  unsigned __int64 v5; // rax
  const unsigned __int16 **v6; // rax
  const unsigned __int16 **v7; // r15
  __int64 v8; // rbx
  unsigned int v9; // edi
  _QWORD *v10; // r14
  const unsigned __int16 *v11; // rcx
  unsigned __int16 *v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 336);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  v3 = *((unsigned int *)this + 32);
  v4 = 8;
  v5 = 8 * v3;
  if ( !is_mul_ok(v3, 8u) )
    v5 = -1;
  v6 = (const unsigned __int16 **)operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    memset_0(v6, 0, 8 * v3);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    v8 = *((_QWORD *)this + 9);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    if ( v8 )
      v8 = *((_QWORD *)this + 9);
    v9 = 0;
    if ( (_DWORD)v3 )
    {
      v10 = v7;
      do
      {
        if ( !v8 )
          break;
        v11 = *(const unsigned __int16 **)(v8 + 8);
        v8 = *(_QWORD *)(v8 + 32);
        v12 = WcsDup(v11);
        *v10 = v12;
        if ( !v12 )
          goto LABEL_15;
        ++v9;
        ++v10;
      }
      while ( v9 < (unsigned int)v3 );
    }
    if ( hKey )
      RegCloseKey(hKey);
    v13 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE",
            0,
            0x20106u,
            &hKey);
    v4 = ElValidateWin32_2(v13, v14, v15, 163);
    if ( !v4 )
    {
      v16 = CRegKey::SetValueMultiSz((CRegKey *)&hKey, L"ProvidersOrder", v7, v3);
      v4 = ElValidateWin32_2(v16, v17, v18, 170);
    }
LABEL_15:
    CRegKey::FreeMultiSz((unsigned __int16 **)v7, v3);
  }
  LeaveCriticalSection(v1);
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x1800065b4  mov     [rsp+arg_8], rbx
0x1800065b9  mov     [rsp+arg_10], rbp
0x1800065be  push    rsi
0x1800065bf  push    rdi
0x1800065c0  push    r12
0x1800065c2  push    r14
0x1800065c4  push    r15
0x1800065c6  sub     rsp, 30h
0x1800065ca  and     [rsp+58h+hKey], 0
0x1800065d0  lea     r12, [rcx+150h]
0x1800065d7  mov     r14, rcx
0x1800065da  mov     rcx, r12; lpCriticalSection
0x1800065dd  call    cs:__imp_EnterCriticalSection
0x1800065e4  nop     dword ptr [rax+rax+00h]
0x1800065e9  mov     ebp, [r14+80h]
0x1800065f0  mov     esi, 8
0x1800065f5  mov     eax, esi
0x1800065f7  mul     rbp
0x1800065fa  lea     rcx, [rsi-9]
0x1800065fe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006605  cmovo   rax, rcx
0x180006609  mov     rcx, rax; unsigned __int64
0x18000660c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006611  mov     r15, rax
0x180006614  test    rax, rax
0x180006617  jz      loc_18000672A
0x18000661d  lea     r8, ds:0[rbp*8]; Size
0x180006625  xor     edx, edx; Val
0x180006627  mov     rcx, rax; void *
0x18000662a  call    memset_0
0x18000662f  lea     rcx, [r14+58h]; lpCriticalSection
0x180006633  call    cs:__imp_EnterCriticalSection
0x18000663a  nop     dword ptr [rax+rax+00h]
0x18000663f  mov     rbx, [r14+48h]
0x180006643  lea     rcx, [r14+58h]; lpCriticalSection
0x180006647  call    cs:__imp_LeaveCriticalSection
0x18000664e  nop     dword ptr [rax+rax+00h]
0x180006653  test    rbx, rbx
0x180006656  jz      short loc_18000665C
0x180006658  mov     rbx, [r14+48h]
0x18000665c  xor     edi, edi
0x18000665e  test    ebp, ebp
0x180006660  jz      short loc_180006696
0x180006662  mov     r14, r15
0x180006665  mov     rcx, rbx
0x180006668  test    rbx, rbx
0x18000666b  jz      short loc_180006696
0x18000666d  mov     rcx, [rcx+8]
0x180006671  mov     rbx, [rbx+20h]
0x180006675  call    cs:__imp_?WcsDup@@YAPEAGPEBG@Z; WcsDup(ushort const *)
0x18000667c  nop     dword ptr [rax+rax+00h]
0x180006681  mov     [r14], rax
0x180006684  test    rax, rax
0x180006687  jz      loc_180006719
0x18000668d  inc     edi
0x18000668f  add     r14, rsi
0x180006692  cmp     edi, ebp
0x180006694  jb      short loc_180006665
0x180006696  mov     rcx, [rsp+58h+hKey]; hKey
0x18000669b  test    rcx, rcx
0x18000669e  jz      short loc_1800066AC
0x1800066a0  call    cs:__imp_RegCloseKey
0x1800066a7  nop     dword ptr [rax+rax+00h]
0x1800066ac  lea     rax, [rsp+58h+hKey]
0x1800066b1  mov     r9d, 20106h; samDesired
0x1800066b7  xor     r8d, r8d; ulOptions
0x1800066ba  mov     [rsp+58h+phkResult], rax; phkResult
0x1800066bf  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x1800066c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800066cd  call    cs:__imp_RegOpenKeyExW
0x1800066d4  nop     dword ptr [rax+rax+00h]
0x1800066d9  mov     ecx, eax
0x1800066db  mov     r9d, 0A3h
0x1800066e1  call    ElValidateWin32_2
0x1800066e6  mov     esi, eax
0x1800066e8  test    eax, eax
0x1800066ea  jnz     short loc_180006719
0x1800066ec  mov     r9d, ebp
0x1800066ef  lea     rdx, aProvidersorder; "ProvidersOrder"
0x1800066f6  mov     r8, r15
0x1800066f9  lea     rcx, [rsp+58h+hKey]
0x1800066fe  call    cs:__imp_?SetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEBGK@Z; CRegKey::SetValueMultiSz(ushort const *,ushort const * *,ulong)
0x180006705  nop     dword ptr [rax+rax+00h]
0x18000670a  mov     ecx, eax
0x18000670c  mov     r9d, 0AAh
0x180006712  call    ElValidateWin32_2
0x180006717  mov     esi, eax
0x180006719  mov     edx, ebp
0x18000671b  mov     rcx, r15
0x18000671e  call    cs:__imp_?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z; CRegKey::FreeMultiSz(ushort * *,ulong)
0x180006725  nop     dword ptr [rax+rax+00h]
0x18000672a  mov     rcx, r12; lpCriticalSection
0x18000672d  call    cs:__imp_LeaveCriticalSection
0x180006734  nop     dword ptr [rax+rax+00h]
0x180006739  mov     rcx, [rsp+58h+hKey]; hKey
0x18000673e  test    rcx, rcx
0x180006741  jz      short loc_18000674F
0x180006743  call    cs:__imp_RegCloseKey
0x18000674a  nop     dword ptr [rax+rax+00h]
0x18000674f  mov     rbx, [rsp+58h+arg_8]
0x180006754  mov     eax, esi
0x180006756  mov     rbp, [rsp+58h+arg_10]
0x18000675b  add     rsp, 30h
0x18000675f  pop     r15
0x180006761  pop     r14
0x180006763  pop     r12
0x180006765  pop     rdi
0x180006766  pop     rsi
0x180006767  retn
```
