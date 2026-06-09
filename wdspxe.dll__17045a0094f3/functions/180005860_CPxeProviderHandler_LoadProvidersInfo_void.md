# CPxeProviderHandler::LoadProvidersInfo(void)

- ea: `0x180005860`
- end: `0x1800059a5`
- name: `?LoadProvidersInfo@CPxeProviderHandler@@AEAAKXZ`
- size: `325`
- prototype: `unsigned int __fastcall(CPxeProviderHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800050e4`

## callees

- `0x1800054e4`
- `0x180005860`
- `0x1800070c8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180005889`
- `KERNEL32!EnterCriticalSection` at `0x180005889`
- `KERNEL32!LeaveCriticalSection` at `0x18000595a`
- `KERNEL32!LeaveCriticalSection` at `0x18000595a`
- `ADVAPI32!RegCloseKey` at `0x18000589e`
- `ADVAPI32!RegCloseKey` at `0x18000598b`
- `ADVAPI32!RegCloseKey` at `0x18000589e`
- `ADVAPI32!RegCloseKey` at `0x18000598b`
- `ADVAPI32!RegOpenKeyExW` at `0x1800058ca`
- `ADVAPI32!RegOpenKeyExW` at `0x1800058ca`
- `WdsCommonLib!?GetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEAPEAGPEAK@Z` at `0x1800058fc`
- `WdsCommonLib!?GetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEAPEAGPEAK@Z` at `0x1800058fc`
- `WdsCommonLib!?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z` at `0x180005976`
- `WdsCommonLib!?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z` at `0x180005976`

## string_xrefs

- `0x1800058bc`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE`

## pseudocode

```c
__int64 __fastcall CPxeProviderHandler::LoadProvidersInfo(CPxeProviderHandler *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // ebx
  unsigned int ValueMultiSz; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // eax
  __int64 i; // rdi
  unsigned int ProviderInfo; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v16; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int16 **v18; // [rsp+70h] [rbp+40h] BYREF

  hKey = 0;
  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 336);
  v18 = 0;
  v16 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  if ( hKey )
    RegCloseKey(hKey);
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE",
         0,
         0x20119u,
         &hKey);
  v6 = ElValidateWin32_2(v3, v4, v5, 371);
  if ( !v6 )
  {
    ValueMultiSz = CRegKey::GetValueMultiSz((CRegKey *)&hKey, L"ProvidersOrder", &v18, &v16);
    v10 = ElValidateWin32_2(ValueMultiSz, v8, v9, 378);
    v6 = v10;
    if ( v10 == 2 )
    {
      v6 = 0;
    }
    else if ( !v10 )
    {
      for ( i = 0; (unsigned int)i < v16; i = (unsigned int)(i + 1) )
      {
        ProviderInfo = CPxeProviderHandler::LoadProviderInfo(this, i, v18[i]);
        v6 = ElValidateWin32_2(ProviderInfo, v13, v14, 396);
        if ( v6 )
          break;
      }
    }
  }
  LeaveCriticalSection(v1);
  if ( v18 && v16 )
    CRegKey::FreeMultiSz(v18, v16);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180005860  push    rbp
0x180005862  push    rbx
0x180005863  push    rsi
0x180005864  push    rdi
0x180005865  push    r14
0x180005867  mov     rbp, rsp
0x18000586a  sub     rsp, 30h
0x18000586e  and     [rbp+hKey], 0
0x180005873  lea     rsi, [rcx+150h]
0x18000587a  and     [rbp+arg_10], 0
0x18000587f  mov     r14, rcx
0x180005882  and     [rbp+arg_0], 0
0x180005886  mov     rcx, rsi; lpCriticalSection
0x180005889  call    cs:__imp_EnterCriticalSection
0x180005890  nop     dword ptr [rax+rax+00h]
0x180005895  mov     rcx, [rbp+hKey]; hKey
0x180005899  test    rcx, rcx
0x18000589c  jz      short loc_1800058AA
0x18000589e  call    cs:__imp_RegCloseKey
0x1800058a5  nop     dword ptr [rax+rax+00h]
0x1800058aa  lea     rax, [rbp+hKey]
0x1800058ae  mov     r9d, 20119h; samDesired
0x1800058b4  xor     r8d, r8d; ulOptions
0x1800058b7  mov     [rsp+30h+phkResult], rax; phkResult
0x1800058bc  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x1800058c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800058ca  call    cs:__imp_RegOpenKeyExW
0x1800058d1  nop     dword ptr [rax+rax+00h]
0x1800058d6  mov     ecx, eax
0x1800058d8  mov     r9d, 173h
0x1800058de  call    ElValidateWin32_2
0x1800058e3  mov     ebx, eax
0x1800058e5  test    eax, eax
0x1800058e7  jnz     short loc_180005957
0x1800058e9  lea     r9, [rbp+arg_0]
0x1800058ed  lea     r8, [rbp+arg_10]
0x1800058f1  lea     rdx, aProvidersorder; "ProvidersOrder"
0x1800058f8  lea     rcx, [rbp+hKey]
0x1800058fc  call    cs:__imp_?GetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEAPEAGPEAK@Z; CRegKey::GetValueMultiSz(ushort const *,ushort * * *,ulong *)
0x180005903  nop     dword ptr [rax+rax+00h]
0x180005908  mov     ecx, eax
0x18000590a  mov     r9d, 17Ah
0x180005910  call    ElValidateWin32_2
0x180005915  mov     ebx, eax
0x180005917  cmp     eax, 2
0x18000591a  jnz     short loc_180005920
0x18000591c  xor     ebx, ebx
0x18000591e  jmp     short loc_180005957
0x180005920  test    eax, eax
0x180005922  jnz     short loc_180005957
0x180005924  xor     edi, edi
0x180005926  cmp     [rbp+arg_0], edi
0x180005929  jbe     short loc_180005957
0x18000592b  mov     r8, [rbp+arg_10]
0x18000592f  mov     edx, edi; unsigned int
0x180005931  mov     rcx, r14; this
0x180005934  mov     r8, [r8+rdi*8]; unsigned __int16 *
0x180005938  call    ?LoadProviderInfo@CPxeProviderHandler@@AEAAKKPEBG@Z; CPxeProviderHandler::LoadProviderInfo(ulong,ushort const *)
0x18000593d  mov     ecx, eax
0x18000593f  mov     r9d, 18Ch
0x180005945  call    ElValidateWin32_2
0x18000594a  mov     ebx, eax
0x18000594c  test    eax, eax
0x18000594e  jnz     short loc_180005957
0x180005950  inc     edi
0x180005952  cmp     edi, [rbp+arg_0]
0x180005955  jb      short loc_18000592B
0x180005957  mov     rcx, rsi; lpCriticalSection
0x18000595a  call    cs:__imp_LeaveCriticalSection
0x180005961  nop     dword ptr [rax+rax+00h]
0x180005966  mov     rcx, [rbp+arg_10]
0x18000596a  test    rcx, rcx
0x18000596d  jz      short loc_180005982
0x18000596f  mov     edx, [rbp+arg_0]
0x180005972  test    edx, edx
0x180005974  jz      short loc_180005982
0x180005976  call    cs:__imp_?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z; CRegKey::FreeMultiSz(ushort * *,ulong)
0x18000597d  nop     dword ptr [rax+rax+00h]
0x180005982  mov     rcx, [rbp+hKey]; hKey
0x180005986  test    rcx, rcx
0x180005989  jz      short loc_180005997
0x18000598b  call    cs:__imp_RegCloseKey
0x180005992  nop     dword ptr [rax+rax+00h]
0x180005997  mov     eax, ebx
0x180005999  add     rsp, 30h
0x18000599d  pop     r14
0x18000599f  pop     rdi
0x1800059a0  pop     rsi
0x1800059a1  pop     rbx
0x1800059a2  pop     rbp
0x1800059a3  retn
```
