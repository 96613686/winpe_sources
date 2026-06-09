# ScGetServiceTagsReferencingModule(ushort *,ulong *,ulong * *)

- ea: `0x18003a764`
- end: `0x18003a844`
- name: `?ScGetServiceTagsReferencingModule@@YAKPEAGPEAKPEAPEAK@Z`
- size: `224`
- prototype: `unsigned int __fastcall(LPCWSTR lpModuleName, unsigned int *, unsigned int **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bfb0`

## callees

- `0x18003a764`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!qsort_s` at `0x18003a80a`
- `api-ms-win-core-crt-l1-1-0!qsort_s` at `0x18003a80a`
- `ntdll!RtlNtStatusToDosError` at `0x18003a7d8`
- `ntdll!RtlNtStatusToDosError` at `0x18003a7d8`
- `ntdll!LdrQueryModuleServiceTags` at `0x18003a7cc`
- `ntdll!LdrQueryModuleServiceTags` at `0x18003a7cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003a78e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003a78e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a829`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a79a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a79a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a7ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a7ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a832`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a832`

## pseudocode

```c
__int64 __fastcall ScGetServiceTagsReferencingModule(LPCWSTR lpModuleName, unsigned int *a2, unsigned int **a3)
{
  void *v5; // rdi
  DWORD LastError; // eax
  unsigned int v7; // ebx
  HLOCAL v8; // rax
  NTSTATUS v9; // eax
  unsigned int v10; // eax
  HMODULE hLibModule; // [rsp+30h] [rbp-38h] BYREF
  rsize_t NumOfElements; // [rsp+88h] [rbp+20h] BYREF

  hLibModule = 0;
  LODWORD(NumOfElements) = 128;
  if ( !GetModuleHandleExW(0, lpModuleName, &hLibModule) )
  {
    v5 = 0;
LABEL_3:
    LastError = GetLastError();
LABEL_4:
    v7 = LastError;
    goto LABEL_11;
  }
  v8 = LocalAlloc(0x40u, 0x200u);
  v5 = v8;
  if ( !v8 )
    goto LABEL_3;
  v9 = LdrQueryModuleServiceTags(hLibModule, v8, &NumOfElements);
  if ( v9 )
  {
    LastError = RtlNtStatusToDosError(v9);
    goto LABEL_4;
  }
  if ( (_DWORD)NumOfElements )
  {
    v7 = 0;
    qsort_s(v5, (unsigned int)NumOfElements, 4u, ScCompareServiceTags, 0);
    v10 = NumOfElements;
    *a3 = (unsigned int *)v5;
    v5 = 0;
    *a2 = v10;
  }
  else
  {
    v7 = 259;
  }
LABEL_11:
  if ( hLibModule )
    FreeLibrary(hLibModule);
  LocalFree(v5);
  return v7;
}

```

## disassembly

```asm
0x18003a764  mov     rax, rsp
0x18003a767  push    rbx
0x18003a768  push    rsi
0x18003a769  push    rdi
0x18003a76a  push    r14
0x18003a76c  sub     rsp, 48h
0x18003a770  mov     r14, rdx
0x18003a773  mov     qword ptr [rax-38h], 0
0x18003a77b  mov     rdx, rcx; lpModuleName
0x18003a77e  mov     dword ptr [rax+20h], 80h
0x18003a785  mov     rsi, r8
0x18003a788  xor     ecx, ecx; dwFlags
0x18003a78a  lea     r8, [rax-38h]; phModule
0x18003a78e  call    cs:__imp_GetModuleHandleExW
0x18003a794  test    eax, eax
0x18003a796  jnz     short loc_18003A7A4
0x18003a798  xor     edi, edi
0x18003a79a  call    cs:__imp_GetLastError
0x18003a7a0  mov     ebx, eax
0x18003a7a2  jmp     short loc_18003A81F
0x18003a7a4  mov     edx, 200h; uBytes
0x18003a7a9  mov     ecx, 40h ; '@'; uFlags
0x18003a7ae  call    cs:__imp_LocalAlloc
0x18003a7b4  mov     rdi, rax
0x18003a7b7  test    rax, rax
0x18003a7ba  jz      short loc_18003A79A
0x18003a7bc  mov     rcx, [rsp+68h+hLibModule]
0x18003a7c1  lea     r8, [rsp+68h+NumOfElements]
0x18003a7c9  mov     rdx, rax
0x18003a7cc  call    cs:__imp_LdrQueryModuleServiceTags
0x18003a7d2  test    eax, eax
0x18003a7d4  jz      short loc_18003A7E0
0x18003a7d6  mov     ecx, eax; Status
0x18003a7d8  call    cs:__imp_RtlNtStatusToDosError
0x18003a7de  jmp     short loc_18003A7A0
0x18003a7e0  mov     eax, dword ptr [rsp+68h+NumOfElements]
0x18003a7e7  test    eax, eax
0x18003a7e9  jnz     short loc_18003A7F2
0x18003a7eb  mov     ebx, 103h
0x18003a7f0  jmp     short loc_18003A81F
0x18003a7f2  xor     ebx, ebx
0x18003a7f4  lea     r9, ?ScCompareServiceTags@@YAHPEAXPEBX1@Z; CompareFunction
0x18003a7fb  mov     rdx, rax; NumOfElements
0x18003a7fe  mov     [rsp+68h+Context], rbx; Context
0x18003a803  mov     rcx, rdi; Base
0x18003a806  lea     r8d, [rbx+4]; SizeOfElements
0x18003a80a  call    cs:__imp_qsort_s
0x18003a810  mov     eax, dword ptr [rsp+68h+NumOfElements]
0x18003a817  mov     [rsi], rdi
0x18003a81a  xor     edi, edi
0x18003a81c  mov     [r14], eax
0x18003a81f  mov     rcx, [rsp+68h+hLibModule]; hLibModule
0x18003a824  test    rcx, rcx
0x18003a827  jz      short loc_18003A82F
0x18003a829  call    cs:__imp_FreeLibrary
0x18003a82f  mov     rcx, rdi; hMem
0x18003a832  call    cs:__imp_LocalFree
0x18003a838  mov     eax, ebx
0x18003a83a  add     rsp, 48h
0x18003a83e  pop     r14
0x18003a840  pop     rdi
0x18003a841  pop     rsi
0x18003a842  pop     rbx
0x18003a843  retn
```
