# Pca::MergeSdb::Utils::SdbFileData::ComputeRegisteredFileName(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,Pca::MergeSdb::Utils::TimeValue const &)

- ea: `0x140029c80`
- end: `0x140029d8f`
- name: `?ComputeRegisteredFileName@SdbFileData@Utils@MergeSdb@Pca@@SAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGAEBVTimeValue@234@@Z`
- size: `271`
- prototype: `__int64 __fastcall(void **, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002b138`
- `0x14002c970`

## callees

- `0x14001008c`
- `0x1400248cc`
- `0x140028538`
- `0x140029c80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140029ca3`
- `KERNEL32!GetLastError` at `0x140029ca3`
- `KERNEL32!GetProcessHeap` at `0x140029cab`
- `KERNEL32!GetProcessHeap` at `0x140029d36`
- `KERNEL32!GetProcessHeap` at `0x140029d66`
- `KERNEL32!GetProcessHeap` at `0x140029cab`
- `KERNEL32!GetProcessHeap` at `0x140029d36`
- `KERNEL32!GetProcessHeap` at `0x140029d66`
- `KERNEL32!SetLastError` at `0x140029cc1`
- `KERNEL32!SetLastError` at `0x140029cc1`
- `KERNEL32!HeapFree` at `0x140029cb9`
- `KERNEL32!HeapFree` at `0x140029d44`
- `KERNEL32!HeapFree` at `0x140029d74`
- `KERNEL32!HeapFree` at `0x140029cb9`
- `KERNEL32!HeapFree` at `0x140029d44`
- `KERNEL32!HeapFree` at `0x140029d74`

## string_xrefs

- `0x140029d1a`: `Pca::MergeSdb::Utils::SdbFileData::ComputeRegisteredFileName`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::SdbFileData::ComputeRegisteredFileName(
        void **a1,
        __int64 a2,
        unsigned int *a3)
{
  void *v6; // rdi
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  int v9; // eax
  unsigned int v10; // edi
  void *v11; // rbx
  HANDLE v12; // rax
  void *v14; // rbx
  HANDLE v15; // rax
  LPVOID lpMem; // [rsp+50h] [rbp+8h] BYREF

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
  v9 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         (char *)&lpMem,
         L"%08X%08X.%s",
         a3[1],
         *a3,
         a2);
  v10 = v9;
  if ( v9 >= 0 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
      a1,
      &lpMem);
    v14 = lpMem;
    if ( lpMem )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v14);
    }
    return 0;
  }
  else
  {
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      v10 = (unsigned __int16)v9;
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::SdbFileData::ComputeRegisteredFileName",
      2357,
      "wil::str_printf_nothrow failed to format registered file name (%d)",
      v10);
    v11 = lpMem;
    if ( lpMem )
    {
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v11);
    }
    return v10;
  }
}

```

## disassembly

```asm
0x140029c80  mov     [rsp+arg_8], rbx
0x140029c85  mov     [rsp+arg_10], rbp
0x140029c8a  push    rsi
0x140029c8b  push    rdi
0x140029c8c  push    r14
0x140029c8e  sub     rsp, 30h
0x140029c92  mov     r14, r8
0x140029c95  mov     rbp, rdx
0x140029c98  mov     rsi, rcx
0x140029c9b  mov     rdi, [rcx]
0x140029c9e  test    rdi, rdi
0x140029ca1  jz      short loc_140029CC7
0x140029ca3  call    cs:__imp_GetLastError
0x140029ca9  mov     ebx, eax
0x140029cab  call    cs:__imp_GetProcessHeap
0x140029cb1  mov     rcx, rax; hHeap
0x140029cb4  mov     r8, rdi; lpMem
0x140029cb7  xor     edx, edx; dwFlags
0x140029cb9  call    cs:__imp_HeapFree
0x140029cbf  mov     ecx, ebx; dwErrCode
0x140029cc1  call    cs:__imp_SetLastError
0x140029cc7  mov     qword ptr [rsi], 0
0x140029cce  mov     [rsp+48h+lpMem], 0
0x140029cd7  mov     [rsp+48h+var_28], rbp
0x140029cdc  mov     r9d, [r14]
0x140029cdf  mov     r8d, [r14+4]
0x140029ce3  lea     rdx, a08x08xS; "%08X%08X.%s"
0x140029cea  lea     rcx, [rsp+48h+lpMem]
0x140029cef  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x140029cf4  mov     edi, eax
0x140029cf6  test    eax, eax
0x140029cf8  jns     short loc_140029D4E
0x140029cfa  and     eax, 1FFF0000h
0x140029cff  cmp     eax, 70000h
0x140029d04  jnz     short loc_140029D09
0x140029d06  movzx   edi, di
0x140029d09  mov     dword ptr [rsp+48h+var_28], edi
0x140029d0d  lea     r9, aWilStrPrintfNo; "wil::str_printf_nothrow failed to forma"...
0x140029d14  mov     r8d, 935h
0x140029d1a  lea     rdx, aPcaMergesdbUti_22; "Pca::MergeSdb::Utils::SdbFileData::Comp"...
0x140029d21  mov     ecx, 1
0x140029d26  call    AslLogCallPrintf
0x140029d2b  nop
0x140029d2c  mov     rbx, [rsp+48h+lpMem]
0x140029d31  test    rbx, rbx
0x140029d34  jz      short loc_140029D4A
0x140029d36  call    cs:__imp_GetProcessHeap
0x140029d3c  mov     rcx, rax; hHeap
0x140029d3f  mov     r8, rbx; lpMem
0x140029d42  xor     edx, edx; dwFlags
0x140029d44  call    cs:__imp_HeapFree
0x140029d4a  mov     eax, edi
0x140029d4c  jmp     short loc_140029D7C
0x140029d4e  lea     rdx, [rsp+48h+lpMem]
0x140029d53  mov     rcx, rsi
0x140029d56  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x140029d5b  nop
0x140029d5c  mov     rbx, [rsp+48h+lpMem]
0x140029d61  test    rbx, rbx
0x140029d64  jz      short loc_140029D7A
0x140029d66  call    cs:__imp_GetProcessHeap
0x140029d6c  mov     rcx, rax; hHeap
0x140029d6f  mov     r8, rbx; lpMem
0x140029d72  xor     edx, edx; dwFlags
0x140029d74  call    cs:__imp_HeapFree
0x140029d7a  xor     eax, eax
0x140029d7c  mov     rbx, [rsp+48h+arg_8]
0x140029d81  mov     rbp, [rsp+48h+arg_10]
0x140029d86  add     rsp, 30h
0x140029d8a  pop     r14
0x140029d8c  pop     rdi
0x140029d8d  pop     rsi
0x140029d8e  retn
```
