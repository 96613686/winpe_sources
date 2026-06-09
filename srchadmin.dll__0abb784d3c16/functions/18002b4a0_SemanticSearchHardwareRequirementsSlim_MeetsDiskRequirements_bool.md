# SemanticSearchHardwareRequirementsSlim::MeetsDiskRequirements(bool)

- ea: `0x18002b4a0`
- end: `0x18002b558`
- name: `?MeetsDiskRequirements@SemanticSearchHardwareRequirementsSlim@@CA_N_N@Z`
- size: `184`
- prototype: `bool __fastcall(bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b2a4`

## callees

- `0x180003f50`
- `0x180028f40`
- `0x18002b4a0`
- `0x18002c164`
- `0x18002c32c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18002b4df`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18002b4df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b536`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b536`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b545`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall SemanticSearchHardwareRequirementsSlim::MeetsDiskRequirements(char a1)
{
  const char *v2; // r9
  _ULARGE_INTEGER v3; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  LPCWSTR lpDirectoryName; // [rsp+38h] [rbp+18h] BYREF
  _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+40h] [rbp+20h] BYREF

  TotalNumberOfBytes.QuadPart = 0;
  wil::GetSystemDirectoryW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(&lpDirectoryName);
  if ( SemanticSearchHardwareRequirementsSlim::GetPhysicalDiskSize((WCHAR *)lpDirectoryName, &TotalNumberOfBytes) < 0
    && !GetDiskFreeSpaceExW(lpDirectoryName, 0, &TotalNumberOfBytes, 0) )
  {
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xF3,
      (unsigned int)"onecoreuap\\internal\\base\\inc\\SemanticSearchHardwareRequirementsSlim.h",
      v2);
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60250342>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60250342>::GetImpl'::`2'::impl)
    || (v3.QuadPart = 0x1F40000000LL, !a1) )
  {
    v3.QuadPart = 0x3840000000LL;
  }
  if ( TotalNumberOfBytes.QuadPart >= v3.QuadPart )
  {
    if ( lpDirectoryName )
      CoTaskMemFree((LPVOID)lpDirectoryName);
    return 1;
  }
  else
  {
    if ( lpDirectoryName )
      CoTaskMemFree((LPVOID)lpDirectoryName);
    return 0;
  }
}

```

## disassembly

```asm
0x18002b4a0  mov     [rsp-8+arg_0], rbx
0x18002b4a5  push    rbp
0x18002b4a6  mov     rbp, rsp
0x18002b4a9  sub     rsp, 20h
0x18002b4ad  mov     bl, cl
0x18002b4af  mov     qword ptr [rbp+TotalNumberOfBytes], 0
0x18002b4b7  lea     rcx, [rbp+lpDirectoryName]
0x18002b4bb  call    ??$GetSystemDirectoryW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@XZ; wil::GetSystemDirectoryW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(void)
0x18002b4c0  nop
0x18002b4c1  lea     rdx, [rbp+TotalNumberOfBytes]; union _ULARGE_INTEGER *
0x18002b4c5  mov     rcx, [rbp+lpDirectoryName]; lpszFileName
0x18002b4c9  call    ?GetPhysicalDiskSize@SemanticSearchHardwareRequirementsSlim@@CAJPEBGPEAT_ULARGE_INTEGER@@@Z; SemanticSearchHardwareRequirementsSlim::GetPhysicalDiskSize(ushort const *,_ULARGE_INTEGER *)
0x18002b4ce  test    eax, eax
0x18002b4d0  jns     short loc_18002B4FF
0x18002b4d2  xor     r9d, r9d; lpTotalNumberOfFreeBytes
0x18002b4d5  lea     r8, [rbp+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x18002b4d9  xor     edx, edx; lpFreeBytesAvailableToCaller
0x18002b4db  mov     rcx, [rbp+lpDirectoryName]; lpDirectoryName
0x18002b4df  call    cs:__imp_GetDiskFreeSpaceExW
0x18002b4e5  mov     rcx, [rbp+8]; this
0x18002b4e9  test    eax, eax
0x18002b4eb  jnz     short loc_18002B4FF
0x18002b4ed  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\Semant"...
0x18002b4f4  mov     edx, 0F3h; void *
0x18002b4f9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002b4ff  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60250342@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60250342@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60250342> `wil::Feature<__WilFeatureTraits_Feature_60250342>::GetImpl(void)'::`2'::impl
0x18002b506  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60250342@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60250342>::__private_IsEnabled(void)
0x18002b50b  test    al, al
0x18002b50d  jz      short loc_18002B51D
0x18002b50f  test    bl, bl
0x18002b511  mov     rax, 1F40000000h
0x18002b51b  jnz     short loc_18002B527
0x18002b51d  mov     rax, 3840000000h
0x18002b527  mov     rcx, [rbp+lpDirectoryName]; pv
0x18002b52b  cmp     qword ptr [rbp+TotalNumberOfBytes], rax
0x18002b52f  jnb     short loc_18002B540
0x18002b531  test    rcx, rcx
0x18002b534  jz      short loc_18002B53C
0x18002b536  call    cs:__imp_CoTaskMemFree
0x18002b53c  xor     al, al
0x18002b53e  jmp     short loc_18002B54D
0x18002b540  test    rcx, rcx
0x18002b543  jz      short loc_18002B54B
0x18002b545  call    cs:__imp_CoTaskMemFree
0x18002b54b  mov     al, 1
0x18002b54d  mov     rbx, [rsp+20h+arg_0]
0x18002b552  add     rsp, 20h
0x18002b556  pop     rbp
0x18002b557  retn
```
