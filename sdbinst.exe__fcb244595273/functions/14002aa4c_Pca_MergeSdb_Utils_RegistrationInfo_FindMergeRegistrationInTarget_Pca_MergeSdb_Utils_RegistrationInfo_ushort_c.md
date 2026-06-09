# Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget(Pca::MergeSdb::Utils::RegistrationInfo &,ushort const *,ulong (*)(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,bool &),void *)

- ea: `0x14002aa4c`
- end: `0x14002ab59`
- name: `?FindMergeRegistrationInTarget@RegistrationInfo@Utils@MergeSdb@Pca@@SAKAEAV1234@PEBGP6AKPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEA_N@Z2@Z`
- size: `269`
- prototype: `__int64 __fastcall(Pca::MergeSdb::Utils::RegistrationInfo *this, __int64, __int64 (__fastcall *)(__int64, HKEY *, char *), __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140003ff4`
- `0x140004c74`

## callees

- `0x14001008c`
- `0x14002a7a0`
- `0x14002aa4c`
- `0x14002adfc`
- `0x14002df00`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14002aacf`
- `ADVAPI32!RegOpenKeyExW` at `0x14002aacf`
- `ADVAPI32!RegCloseKey` at `0x14002ab28`
- `ADVAPI32!RegCloseKey` at `0x14002ab28`
- `KERNEL32!GetProcessHeap` at `0x14002ab37`
- `KERNEL32!GetProcessHeap` at `0x14002ab37`
- `KERNEL32!HeapFree` at `0x14002ab47`
- `KERNEL32!HeapFree` at `0x14002ab47`

## string_xrefs

- `0x14002aa84`: `Failed to get registry key path for target name (%d)`
- `0x14002aaec`: `Failed to open merge target key (%d)`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget(
        Pca::MergeSdb::Utils::RegistrationInfo *this,
        __int64 a2,
        __int64 (__fastcall *a3)(__int64, HKEY *, char *),
        __int64 a4)
{
  unsigned int MergeTargetRegistryKeyPathForTarget; // edi
  HANDLE ProcessHeap; // rax
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF

  lpSubKey = 0;
  MergeTargetRegistryKeyPathForTarget = Pca::MergeSdb::Utils::SdbFileData::GetMergeTargetRegistryKeyPathForTarget(
                                          (__int64)&lpSubKey,
                                          a2,
                                          (__int64)a3);
  if ( MergeTargetRegistryKeyPathForTarget )
  {
    Pca::MergeSdb::Utils::RegistrationInfo::Reset(this);
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget",
      986,
      "Failed to get registry key path for target name (%d)",
      MergeTargetRegistryKeyPathForTarget);
  }
  else
  {
    hKey = 0;
    MergeTargetRegistryKeyPathForTarget = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
    if ( MergeTargetRegistryKeyPathForTarget )
    {
      Pca::MergeSdb::Utils::RegistrationInfo::Reset(this);
      if ( MergeTargetRegistryKeyPathForTarget != 2 )
        AslLogCallPrintf(
          1,
          "Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget",
          999,
          "Failed to open merge target key (%d)",
          MergeTargetRegistryKeyPathForTarget);
    }
    else
    {
      MergeTargetRegistryKeyPathForTarget = Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget(
                                              this,
                                              hKey,
                                              a3,
                                              a4);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  if ( lpSubKey )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)lpSubKey);
  }
  return MergeTargetRegistryKeyPathForTarget;
}

```

## disassembly

```asm
0x14002aa4c  push    rbp
0x14002aa4e  push    rsi
0x14002aa4f  push    rdi
0x14002aa50  push    r14
0x14002aa52  sub     rsp, 48h
0x14002aa56  mov     rbp, r9
0x14002aa59  mov     r14, r8
0x14002aa5c  mov     rsi, rcx
0x14002aa5f  mov     [rsp+68h+lpSubKey], 0
0x14002aa68  lea     rcx, [rsp+68h+lpSubKey]
0x14002aa6d  call    ?GetMergeTargetRegistryKeyPathForTarget@SdbFileData@Utils@MergeSdb@Pca@@SAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; Pca::MergeSdb::Utils::SdbFileData::GetMergeTargetRegistryKeyPathForTarget(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x14002aa72  mov     edi, eax
0x14002aa74  test    eax, eax
0x14002aa76  jz      short loc_14002AAA7
0x14002aa78  mov     rcx, rsi; this
0x14002aa7b  call    ?Reset@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAXXZ; Pca::MergeSdb::Utils::RegistrationInfo::Reset(void)
0x14002aa80  mov     dword ptr [rsp+68h+phkResult], edi
0x14002aa84  lea     r9, aFailedToGetReg; "Failed to get registry key path for tar"...
0x14002aa8b  mov     r8d, 3DAh
0x14002aa91  lea     rdx, aPcaMergesdbUti_7; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002aa98  mov     ecx, 1
0x14002aa9d  call    AslLogCallPrintf
0x14002aaa2  jmp     loc_14002AB2F
0x14002aaa7  mov     [rsp+68h+hKey], 0
0x14002aab0  lea     rax, [rsp+68h+hKey]
0x14002aab5  mov     [rsp+68h+phkResult], rax; phkResult
0x14002aaba  mov     r9d, 20019h; samDesired
0x14002aac0  xor     r8d, r8d; ulOptions
0x14002aac3  mov     rdx, [rsp+68h+lpSubKey]; lpSubKey
0x14002aac8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002aacf  call    cs:__imp_RegOpenKeyExW
0x14002aad5  mov     edi, eax
0x14002aad7  mov     rcx, rsi; this
0x14002aada  test    eax, eax
0x14002aadc  jz      short loc_14002AB0C
0x14002aade  call    ?Reset@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAXXZ; Pca::MergeSdb::Utils::RegistrationInfo::Reset(void)
0x14002aae3  cmp     edi, 2
0x14002aae6  jz      short loc_14002AB1E
0x14002aae8  mov     dword ptr [rsp+68h+phkResult], edi
0x14002aaec  lea     r9, aFailedToOpenMe_1; "Failed to open merge target key (%d)"
0x14002aaf3  mov     r8d, 3E7h
0x14002aaf9  lea     rdx, aPcaMergesdbUti_7; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002ab00  mov     ecx, 1
0x14002ab05  call    AslLogCallPrintf
0x14002ab0a  jmp     short loc_14002AB1E
0x14002ab0c  mov     r9, rbp
0x14002ab0f  mov     r8, r14
0x14002ab12  mov     rdx, [rsp+68h+hKey]; hKey
0x14002ab17  call    ?FindMergeRegistrationInTarget@RegistrationInfo@Utils@MergeSdb@Pca@@SAKAEAV1234@PEAUHKEY__@@P6AKPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEA_N@Z2@Z; Pca::MergeSdb::Utils::RegistrationInfo::FindMergeRegistrationInTarget(Pca::MergeSdb::Utils::RegistrationInfo &,HKEY__ *,ulong (*)(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,bool &),void *)
0x14002ab1c  mov     edi, eax
0x14002ab1e  mov     rcx, [rsp+68h+hKey]; hKey
0x14002ab23  test    rcx, rcx
0x14002ab26  jz      short loc_14002AB2F
0x14002ab28  call    cs:__imp_RegCloseKey
0x14002ab2e  nop
0x14002ab2f  cmp     [rsp+68h+lpSubKey], 0
0x14002ab35  jz      short loc_14002AB4D
0x14002ab37  call    cs:__imp_GetProcessHeap
0x14002ab3d  mov     r8, [rsp+68h+lpSubKey]; lpMem
0x14002ab42  xor     edx, edx; dwFlags
0x14002ab44  mov     rcx, rax; hHeap
0x14002ab47  call    cs:__imp_HeapFree
0x14002ab4d  mov     eax, edi
0x14002ab4f  add     rsp, 48h
0x14002ab53  pop     r14
0x14002ab55  pop     rdi
0x14002ab56  pop     rsi
0x14002ab57  pop     rbp
0x14002ab58  retn
```
