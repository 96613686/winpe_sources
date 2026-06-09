# Pca::MergeSdb::Utils::RegistrationInfo::CheckRegisteredState(void)

- ea: `0x14002955c`
- end: `0x140029709`
- name: `?CheckRegisteredState@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAKXZ`
- size: `429`
- prototype: `__int64 __fastcall(Pca::MergeSdb::Utils::RegistrationInfo *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002d660`

## callees

- `0x14001008c`
- `0x140028298`
- `0x14002955c`
- `0x14002d61c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140029621`
- `ADVAPI32!RegOpenKeyExW` at `0x1400296ad`
- `ADVAPI32!RegOpenKeyExW` at `0x140029621`
- `ADVAPI32!RegOpenKeyExW` at `0x1400296ad`
- `ADVAPI32!RegCloseKey` at `0x140029672`
- `ADVAPI32!RegCloseKey` at `0x1400296cc`
- `ADVAPI32!RegCloseKey` at `0x1400296dc`
- `ADVAPI32!RegCloseKey` at `0x140029672`
- `ADVAPI32!RegCloseKey` at `0x1400296cc`
- `ADVAPI32!RegCloseKey` at `0x1400296dc`
- `KERNEL32!GetLastError` at `0x140029667`
- `KERNEL32!GetLastError` at `0x140029667`
- `KERNEL32!GetProcessHeap` at `0x1400295de`
- `KERNEL32!GetProcessHeap` at `0x1400296e8`
- `KERNEL32!GetProcessHeap` at `0x1400295de`
- `KERNEL32!GetProcessHeap` at `0x1400296e8`
- `KERNEL32!SetLastError` at `0x14002967a`
- `KERNEL32!SetLastError` at `0x14002967a`
- `KERNEL32!HeapFree` at `0x1400295ec`
- `KERNEL32!HeapFree` at `0x1400296f6`
- `KERNEL32!HeapFree` at `0x1400295ec`
- `KERNEL32!HeapFree` at `0x1400296f6`

## string_xrefs

- `0x1400295b6`: `Failed to format the reg key path for sdb merge target key (%d)`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegistrationInfo::CheckRegisteredState(
        Pca::MergeSdb::Utils::RegistrationInfo *this,
        __int64 a2,
        __int64 a3)
{
  int v5; // eax
  unsigned int v6; // edi
  void *v7; // rbx
  HANDLE v8; // rax
  void *v9; // rbx
  HKEY v10; // r14
  DWORD LastError; // edi
  HANDLE ProcessHeap; // rax
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+40h] BYREF
  __int64 v16; // [rsp+78h] [rbp+48h] BYREF

  *((_DWORD *)this + 36) = 0;
  if ( !*((_QWORD *)this + 14) )
    return 5023;
  lpMem = 0;
  v5 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [71],unsigned short [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         &lpMem,
         a2,
         a3,
         (char *)this + 96);
  v6 = v5;
  if ( v5 >= 0 )
  {
    hKey = 0;
    v9 = lpMem;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)lpMem, 0, 0x20019u, &hKey) )
    {
      *((_DWORD *)this + 36) |= 3u;
    }
    else
    {
      v16 = 0;
      *((_DWORD *)this + 36) |= Pca::MergeSdb::Utils::RegUtil::ReadRegValue(
                                  hKey,
                                  *((const unsigned __int16 **)this + 13),
                                  (struct Pca::MergeSdb::Utils::TimeValue *)&v16) != 0
                              ? 2
                              : 10;
      v10 = hKey;
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(v10);
        SetLastError(LastError);
      }
      hKey = 0;
      phkResult = 0;
      *((_DWORD *)this + 36) |= RegOpenKeyExW(HKEY_LOCAL_MACHINE, *((LPCWSTR *)this + 14), 0, 0x20019u, &phkResult) != 0
                              ? 1
                              : 5;
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v9 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
    }
    return 0;
  }
  else
  {
    if ( (v5 & 0x1FFF0000) == 0x70000 )
      v6 = (unsigned __int16)v5;
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::CheckRegisteredState",
      1462,
      "Failed to format the reg key path for sdb merge target key (%d)",
      v6);
    v7 = lpMem;
    if ( lpMem )
    {
      v8 = GetProcessHeap();
      HeapFree(v8, 0, v7);
    }
    return v6;
  }
}

```

## disassembly

```asm
0x14002955c  push    rbp
0x14002955e  push    rbx
0x14002955f  push    rsi
0x140029560  push    rdi
0x140029561  push    r14
0x140029563  mov     rbp, rsp
0x140029566  sub     rsp, 30h
0x14002956a  mov     rsi, rcx
0x14002956d  mov     dword ptr [rcx+90h], 0
0x140029577  cmp     qword ptr [rcx+70h], 0
0x14002957c  jnz     short loc_140029588
0x14002957e  mov     eax, 139Fh
0x140029583  jmp     loc_1400296FE
0x140029588  mov     [rbp+lpMem], 0
0x140029590  lea     r9, [rcx+60h]
0x140029594  lea     rcx, [rbp+lpMem]
0x140029598  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY0EH@G$$BY01GV12@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0EH@$$CBGAEAY01$$CBGAEBV10@@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [71],ushort [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[71],ushort const (&)[2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x14002959d  mov     edi, eax
0x14002959f  test    eax, eax
0x1400295a1  jns     short loc_1400295F9
0x1400295a3  and     eax, 1FFF0000h
0x1400295a8  cmp     eax, 70000h
0x1400295ad  jnz     short loc_1400295B2
0x1400295af  movzx   edi, di
0x1400295b2  mov     dword ptr [rsp+30h+phkResult], edi
0x1400295b6  lea     r9, aFailedToFormat; "Failed to format the reg key path for s"...
0x1400295bd  mov     r8d, 5B6h
0x1400295c3  lea     rdx, aPcaMergesdbUti_9; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x1400295ca  mov     ecx, 1
0x1400295cf  call    AslLogCallPrintf
0x1400295d4  nop
0x1400295d5  mov     rbx, [rbp+lpMem]
0x1400295d9  test    rbx, rbx
0x1400295dc  jz      short loc_1400295F2
0x1400295de  call    cs:__imp_GetProcessHeap
0x1400295e4  mov     rcx, rax; hHeap
0x1400295e7  mov     r8, rbx; lpMem
0x1400295ea  xor     edx, edx; dwFlags
0x1400295ec  call    cs:__imp_HeapFree
0x1400295f2  mov     eax, edi
0x1400295f4  jmp     loc_1400296FE
0x1400295f9  mov     [rbp+hKey], 0
0x140029601  lea     rax, [rbp+hKey]
0x140029605  mov     [rsp+30h+phkResult], rax; phkResult
0x14002960a  mov     r9d, 20019h; samDesired
0x140029610  xor     r8d, r8d; ulOptions
0x140029613  mov     rbx, [rbp+lpMem]
0x140029617  mov     rdx, rbx; lpSubKey
0x14002961a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140029621  call    cs:__imp_RegOpenKeyExW
0x140029627  test    eax, eax
0x140029629  jz      short loc_140029637
0x14002962b  or      dword ptr [rsi+90h], 3
0x140029632  jmp     loc_1400296D3
0x140029637  xor     eax, eax
0x140029639  mov     [rbp+arg_18], rax
0x14002963d  lea     r8, [rbp+arg_18]; struct Pca::MergeSdb::Utils::TimeValue *
0x140029641  mov     rdx, [rsi+68h]; unsigned __int16 *
0x140029645  mov     rcx, [rbp+hKey]; HKEY
0x140029649  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAVTimeValue@234@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,Pca::MergeSdb::Utils::TimeValue &)
0x14002964e  neg     eax
0x140029650  sbb     ecx, ecx
0x140029652  and     ecx, 0FFFFFFF8h
0x140029655  add     ecx, 0Ah
0x140029658  or      [rsi+90h], ecx
0x14002965e  mov     r14, [rbp+hKey]
0x140029662  test    r14, r14
0x140029665  jz      short loc_140029680
0x140029667  call    cs:__imp_GetLastError
0x14002966d  mov     edi, eax
0x14002966f  mov     rcx, r14; hKey
0x140029672  call    cs:__imp_RegCloseKey
0x140029678  mov     ecx, edi; dwErrCode
0x14002967a  call    cs:__imp_SetLastError
0x140029680  mov     [rbp+hKey], 0
0x140029688  mov     [rbp+arg_10], 0
0x140029690  lea     rax, [rbp+arg_10]
0x140029694  mov     [rsp+30h+phkResult], rax; phkResult
0x140029699  mov     r9d, 20019h; samDesired
0x14002969f  xor     r8d, r8d; ulOptions
0x1400296a2  mov     rdx, [rsi+70h]; lpSubKey
0x1400296a6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400296ad  call    cs:__imp_RegOpenKeyExW
0x1400296b3  neg     eax
0x1400296b5  sbb     ecx, ecx
0x1400296b7  and     ecx, 0FFFFFFFCh
0x1400296ba  add     ecx, 5
0x1400296bd  or      [rsi+90h], ecx
0x1400296c3  mov     rcx, [rbp+arg_10]; hKey
0x1400296c7  test    rcx, rcx
0x1400296ca  jz      short loc_1400296D3
0x1400296cc  call    cs:__imp_RegCloseKey
0x1400296d2  nop
0x1400296d3  mov     rcx, [rbp+hKey]; hKey
0x1400296d7  test    rcx, rcx
0x1400296da  jz      short loc_1400296E3
0x1400296dc  call    cs:__imp_RegCloseKey
0x1400296e2  nop
0x1400296e3  test    rbx, rbx
0x1400296e6  jz      short loc_1400296FC
0x1400296e8  call    cs:__imp_GetProcessHeap
0x1400296ee  mov     r8, rbx; lpMem
0x1400296f1  xor     edx, edx; dwFlags
0x1400296f3  mov     rcx, rax; hHeap
0x1400296f6  call    cs:__imp_HeapFree
0x1400296fc  xor     eax, eax
0x1400296fe  add     rsp, 30h
0x140029702  pop     r14
0x140029704  pop     rdi
0x140029705  pop     rsi
0x140029706  pop     rbx
0x140029707  pop     rbp
0x140029708  retn
```
