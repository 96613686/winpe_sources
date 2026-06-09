# Pca::MergeSdb::Utils::RegistrationInfo::GetMergeSdbDirectoryPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x14002acfc`
- end: `0x14002adf3`
- name: `?GetMergeSdbDirectoryPath@RegistrationInfo@Utils@MergeSdb@Pca@@SAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140027c80`
- `0x140028714`
- `0x14002a1ac`
- `0x14002ce68`

## callees

- `0x14001008c`
- `0x140020cb8`
- `0x1400248cc`
- `0x14002acfc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002ad16`
- `KERNEL32!GetLastError` at `0x14002ad16`
- `KERNEL32!GetProcessHeap` at `0x14002ad1e`
- `KERNEL32!GetProcessHeap` at `0x14002ad9d`
- `KERNEL32!GetProcessHeap` at `0x14002adcd`
- `KERNEL32!GetProcessHeap` at `0x14002ad1e`
- `KERNEL32!GetProcessHeap` at `0x14002ad9d`
- `KERNEL32!GetProcessHeap` at `0x14002adcd`
- `KERNEL32!SetLastError` at `0x14002ad34`
- `KERNEL32!SetLastError` at `0x14002ad34`
- `KERNEL32!HeapFree` at `0x14002ad2c`
- `KERNEL32!HeapFree` at `0x14002adab`
- `KERNEL32!HeapFree` at `0x14002addb`
- `KERNEL32!HeapFree` at `0x14002ad2c`
- `KERNEL32!HeapFree` at `0x14002adab`
- `KERNEL32!HeapFree` at `0x14002addb`

## string_xrefs

- `0x14002ad81`: `Pca::MergeSdb::Utils::RegistrationInfo::GetMergeSdbDirectoryPath`
- `0x14002ad74`: `Failed to create and expand merge dir path (%d)`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegistrationInfo::GetMergeSdbDirectoryPath(void **a1)
{
  void *v2; // rdi
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  int v5; // eax
  unsigned int v6; // edi
  void *v7; // rbx
  HANDLE v8; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  LPVOID lpMem; // [rsp+40h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    SetLastError(LastError);
  }
  *a1 = 0;
  lpMem = 0;
  v5 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         L"%SYSTEMROOT%\\AppPatch\\MergeSdbFiles",
         &lpMem);
  v6 = v5;
  if ( v5 >= 0 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
      a1,
      &lpMem);
    v10 = lpMem;
    if ( lpMem )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
    }
    return 0;
  }
  else
  {
    if ( (v5 & 0x1FFF0000) == 0x70000 )
      v6 = (unsigned __int16)v5;
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::GetMergeSdbDirectoryPath",
      1768,
      "Failed to create and expand merge dir path (%d)",
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
0x14002acfc  mov     [rsp+arg_8], rbx
0x14002ad01  mov     [rsp+arg_10], rsi
0x14002ad06  push    rdi
0x14002ad07  sub     rsp, 30h
0x14002ad0b  mov     rsi, rcx
0x14002ad0e  mov     rdi, [rcx]
0x14002ad11  test    rdi, rdi
0x14002ad14  jz      short loc_14002AD3A
0x14002ad16  call    cs:__imp_GetLastError
0x14002ad1c  mov     ebx, eax
0x14002ad1e  call    cs:__imp_GetProcessHeap
0x14002ad24  mov     rcx, rax; hHeap
0x14002ad27  mov     r8, rdi; lpMem
0x14002ad2a  xor     edx, edx; dwFlags
0x14002ad2c  call    cs:__imp_HeapFree
0x14002ad32  mov     ecx, ebx; dwErrCode
0x14002ad34  call    cs:__imp_SetLastError
0x14002ad3a  mov     qword ptr [rsi], 0
0x14002ad41  mov     [rsp+38h+lpMem], 0
0x14002ad4a  lea     rdx, [rsp+38h+lpMem]
0x14002ad4f  lea     rcx, aSystemrootAppp_3; "%SYSTEMROOT%\\AppPatch\\MergeSdbFiles"
0x14002ad56  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002ad5b  mov     edi, eax
0x14002ad5d  test    eax, eax
0x14002ad5f  jns     short loc_14002ADB5
0x14002ad61  and     eax, 1FFF0000h
0x14002ad66  cmp     eax, 70000h
0x14002ad6b  jnz     short loc_14002AD70
0x14002ad6d  movzx   edi, di
0x14002ad70  mov     [rsp+38h+var_18], edi
0x14002ad74  lea     r9, aFailedToCreate_12; "Failed to create and expand merge dir p"...
0x14002ad7b  mov     r8d, 6E8h
0x14002ad81  lea     rdx, aPcaMergesdbUti_16; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002ad88  mov     ecx, 1
0x14002ad8d  call    AslLogCallPrintf
0x14002ad92  nop
0x14002ad93  mov     rbx, [rsp+38h+lpMem]
0x14002ad98  test    rbx, rbx
0x14002ad9b  jz      short loc_14002ADB1
0x14002ad9d  call    cs:__imp_GetProcessHeap
0x14002ada3  mov     rcx, rax; hHeap
0x14002ada6  mov     r8, rbx; lpMem
0x14002ada9  xor     edx, edx; dwFlags
0x14002adab  call    cs:__imp_HeapFree
0x14002adb1  mov     eax, edi
0x14002adb3  jmp     short loc_14002ADE3
0x14002adb5  lea     rdx, [rsp+38h+lpMem]
0x14002adba  mov     rcx, rsi
0x14002adbd  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002adc2  nop
0x14002adc3  mov     rbx, [rsp+38h+lpMem]
0x14002adc8  test    rbx, rbx
0x14002adcb  jz      short loc_14002ADE1
0x14002adcd  call    cs:__imp_GetProcessHeap
0x14002add3  mov     rcx, rax; hHeap
0x14002add6  mov     r8, rbx; lpMem
0x14002add9  xor     edx, edx; dwFlags
0x14002addb  call    cs:__imp_HeapFree
0x14002ade1  xor     eax, eax
0x14002ade3  mov     rbx, [rsp+38h+arg_8]
0x14002ade8  mov     rsi, [rsp+38h+arg_10]
0x14002aded  add     rsp, 30h
0x14002adf1  pop     rdi
0x14002adf2  retn
```
