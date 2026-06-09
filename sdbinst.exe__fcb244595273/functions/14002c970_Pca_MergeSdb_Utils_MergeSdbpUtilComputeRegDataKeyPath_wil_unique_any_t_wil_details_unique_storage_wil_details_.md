# Pca::MergeSdb::Utils::MergeSdbpUtilComputeRegDataKeyPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,Pca::MergeSdb::Utils::TimeValue &)

- ea: `0x14002c970`
- end: `0x14002caff`
- name: `?MergeSdbpUtilComputeRegDataKeyPath@Utils@MergeSdb@Pca@@YAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGAEAVTimeValue@123@@Z`
- size: `399`
- prototype: `__int64 __fastcall(void **, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002c36c`

## callees

- `0x14001008c`
- `0x1400248cc`
- `0x1400281a0`
- `0x140029c80`
- `0x14002c970`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002c999`
- `KERNEL32!GetLastError` at `0x14002c999`
- `KERNEL32!GetProcessHeap` at `0x14002c9a1`
- `KERNEL32!GetProcessHeap` at `0x14002ca0d`
- `KERNEL32!GetProcessHeap` at `0x14002ca8b`
- `KERNEL32!GetProcessHeap` at `0x14002caba`
- `KERNEL32!GetProcessHeap` at `0x14002cad8`
- `KERNEL32!GetProcessHeap` at `0x14002c9a1`
- `KERNEL32!GetProcessHeap` at `0x14002ca0d`
- `KERNEL32!GetProcessHeap` at `0x14002ca8b`
- `KERNEL32!GetProcessHeap` at `0x14002caba`
- `KERNEL32!GetProcessHeap` at `0x14002cad8`
- `KERNEL32!SetLastError` at `0x14002c9b7`
- `KERNEL32!SetLastError` at `0x14002c9b7`
- `KERNEL32!HeapFree` at `0x14002c9af`
- `KERNEL32!HeapFree` at `0x14002ca1b`
- `KERNEL32!HeapFree` at `0x14002ca99`
- `KERNEL32!HeapFree` at `0x14002cac8`
- `KERNEL32!HeapFree` at `0x14002cae6`
- `KERNEL32!HeapFree` at `0x14002c9af`
- `KERNEL32!HeapFree` at `0x14002ca1b`
- `KERNEL32!HeapFree` at `0x14002ca99`
- `KERNEL32!HeapFree` at `0x14002cac8`
- `KERNEL32!HeapFree` at `0x14002cae6`

## string_xrefs

- `0x14002c9e5`: `Failed to compute the registered file name (%d)`
- `0x14002ca5f`: `Failed to construct the sdb registry path (%d)`
- `0x14002c9f2`: `Pca::MergeSdb::Utils::MergeSdbpUtilComputeRegDataKeyPath`
- `0x14002ca6c`: `Pca::MergeSdb::Utils::MergeSdbpUtilComputeRegDataKeyPath`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::MergeSdbpUtilComputeRegDataKeyPath(void **a1, __int64 a2, unsigned int *a3)
{
  void *v6; // r14
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // edi
  void *v13; // rbx
  HANDLE v14; // rax
  int v16; // eax
  void *v17; // rbx
  HANDLE v18; // rax
  void *v19; // rbx
  HANDLE v20; // rax
  void *v21; // rbx
  HANDLE v22; // rax
  int v23; // [rsp+20h] [rbp-10h]
  LPVOID lpMem; // [rsp+60h] [rbp+30h] BYREF
  __int64 v25; // [rsp+68h] [rbp+38h] BYREF
  LPVOID v26; // [rsp+78h] [rbp+48h] BYREF

  v25 = a2;
  v6 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
    SetLastError(LastError);
  }
  *a1 = 0;
  lpMem = 0;
  v9 = Pca::MergeSdb::Utils::SdbFileData::ComputeRegisteredFileName(&lpMem, a2, a3);
  v12 = v9;
  if ( v9 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::MergeSdbpUtilComputeRegDataKeyPath",
      628,
      "Failed to compute the registered file name (%d)",
      v9);
LABEL_5:
    v13 = lpMem;
    if ( lpMem )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v13);
    }
    return v12;
  }
  v26 = 0;
  v16 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [71],unsigned short [2],unsigned short const *,unsigned short [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          (int *)&v26,
          v10,
          v11,
          &v25,
          v23,
          (__int64 *)&lpMem);
  v12 = v16;
  if ( v16 < 0 )
  {
    if ( (v16 & 0x1FFF0000) == 0x70000 )
      v12 = (unsigned __int16)v16;
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::MergeSdbpUtilComputeRegDataKeyPath",
      639,
      "Failed to construct the sdb registry path (%d)",
      v12);
    v17 = v26;
    if ( v26 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v17);
    }
    goto LABEL_5;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
    a1,
    &v26);
  v19 = v26;
  if ( v26 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v19);
  }
  v21 = lpMem;
  if ( lpMem )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
  }
  return 0;
}

```

## disassembly

```asm
0x14002c970  mov     [rsp-28h+arg_10], rbx
0x14002c975  mov     [rsp-28h+arg_8], rdx
0x14002c97a  push    rbp
0x14002c97b  push    rsi
0x14002c97c  push    rdi
0x14002c97d  push    r14
0x14002c97f  push    r15
0x14002c981  mov     rbp, rsp
0x14002c984  sub     rsp, 30h
0x14002c988  mov     r15, r8
0x14002c98b  mov     rdi, rdx
0x14002c98e  mov     rsi, rcx
0x14002c991  mov     r14, [rcx]
0x14002c994  test    r14, r14
0x14002c997  jz      short loc_14002C9BD
0x14002c999  call    cs:__imp_GetLastError
0x14002c99f  mov     ebx, eax
0x14002c9a1  call    cs:__imp_GetProcessHeap
0x14002c9a7  mov     rcx, rax; hHeap
0x14002c9aa  mov     r8, r14; lpMem
0x14002c9ad  xor     edx, edx; dwFlags
0x14002c9af  call    cs:__imp_HeapFree
0x14002c9b5  mov     ecx, ebx; dwErrCode
0x14002c9b7  call    cs:__imp_SetLastError
0x14002c9bd  mov     qword ptr [rsi], 0
0x14002c9c4  mov     [rbp+lpMem], 0
0x14002c9cc  mov     r8, r15
0x14002c9cf  mov     rdx, rdi
0x14002c9d2  lea     rcx, [rbp+lpMem]
0x14002c9d6  call    ?ComputeRegisteredFileName@SdbFileData@Utils@MergeSdb@Pca@@SAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGAEBVTimeValue@234@@Z; Pca::MergeSdb::Utils::SdbFileData::ComputeRegisteredFileName(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,Pca::MergeSdb::Utils::TimeValue const &)
0x14002c9db  mov     edi, eax
0x14002c9dd  test    eax, eax
0x14002c9df  jz      short loc_14002CA28
0x14002c9e1  mov     [rsp+30h+var_10], eax
0x14002c9e5  lea     r9, aFailedToComput; "Failed to compute the registered file n"...
0x14002c9ec  mov     r8d, 274h
0x14002c9f2  lea     rdx, aPcaMergesdbUti_10; "Pca::MergeSdb::Utils::MergeSdbpUtilComp"...
0x14002c9f9  mov     ecx, 1
0x14002c9fe  call    AslLogCallPrintf
0x14002ca03  nop
0x14002ca04  mov     rbx, [rbp+lpMem]
0x14002ca08  test    rbx, rbx
0x14002ca0b  jz      short loc_14002CA21
0x14002ca0d  call    cs:__imp_GetProcessHeap
0x14002ca13  mov     rcx, rax; hHeap
0x14002ca16  mov     r8, rbx; lpMem
0x14002ca19  xor     edx, edx; dwFlags
0x14002ca1b  call    cs:__imp_HeapFree
0x14002ca21  mov     eax, edi
0x14002ca23  jmp     loc_14002CAEE
0x14002ca28  mov     [rbp+arg_18], 0
0x14002ca30  lea     rax, [rbp+lpMem]
0x14002ca34  mov     [rsp+30h+var_8], rax
0x14002ca39  lea     r9, [rbp+arg_8]
0x14002ca3d  lea     rcx, [rbp+arg_18]
0x14002ca41  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY0EH@G$$BY01GPEBG$$BY01GV12@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0EH@$$CBGAEAY01$$CBGAEBQEBG2AEBV10@@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [71],ushort [2],ushort const *,ushort [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[71],ushort const (&)[2],ushort const * const &,ushort const (&)[2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x14002ca46  mov     edi, eax
0x14002ca48  test    eax, eax
0x14002ca4a  jns     short loc_14002CAA4
0x14002ca4c  and     eax, 1FFF0000h
0x14002ca51  cmp     eax, 70000h
0x14002ca56  jnz     short loc_14002CA5B
0x14002ca58  movzx   edi, di
0x14002ca5b  mov     [rsp+30h+var_10], edi
0x14002ca5f  lea     r9, aFailedToConstr; "Failed to construct the sdb registry pa"...
0x14002ca66  mov     r8d, 27Fh
0x14002ca6c  lea     rdx, aPcaMergesdbUti_10; "Pca::MergeSdb::Utils::MergeSdbpUtilComp"...
0x14002ca73  mov     ecx, 1
0x14002ca78  call    AslLogCallPrintf
0x14002ca7d  nop
0x14002ca7e  mov     rbx, [rbp+arg_18]
0x14002ca82  test    rbx, rbx
0x14002ca85  jz      loc_14002CA04
0x14002ca8b  call    cs:__imp_GetProcessHeap
0x14002ca91  mov     rcx, rax; hHeap
0x14002ca94  mov     r8, rbx; lpMem
0x14002ca97  xor     edx, edx; dwFlags
0x14002ca99  call    cs:__imp_HeapFree
0x14002ca9f  jmp     loc_14002CA04
0x14002caa4  lea     rdx, [rbp+arg_18]
0x14002caa8  mov     rcx, rsi
0x14002caab  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002cab0  nop
0x14002cab1  mov     rbx, [rbp+arg_18]
0x14002cab5  test    rbx, rbx
0x14002cab8  jz      short loc_14002CACF
0x14002caba  call    cs:__imp_GetProcessHeap
0x14002cac0  mov     rcx, rax; hHeap
0x14002cac3  mov     r8, rbx; lpMem
0x14002cac6  xor     edx, edx; dwFlags
0x14002cac8  call    cs:__imp_HeapFree
0x14002cace  nop
0x14002cacf  mov     rbx, [rbp+lpMem]
0x14002cad3  test    rbx, rbx
0x14002cad6  jz      short loc_14002CAEC
0x14002cad8  call    cs:__imp_GetProcessHeap
0x14002cade  mov     rcx, rax; hHeap
0x14002cae1  mov     r8, rbx; lpMem
0x14002cae4  xor     edx, edx; dwFlags
0x14002cae6  call    cs:__imp_HeapFree
0x14002caec  xor     eax, eax
0x14002caee  mov     rbx, [rsp+30h+arg_10]
0x14002caf3  add     rsp, 30h
0x14002caf7  pop     r15
0x14002caf9  pop     r14
0x14002cafb  pop     rdi
0x14002cafc  pop     rsi
0x14002cafd  pop     rbp
0x14002cafe  retn
```
