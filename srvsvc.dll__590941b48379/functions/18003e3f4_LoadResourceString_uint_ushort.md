# LoadResourceString(uint,ushort * *)

- ea: `0x18003e3f4`
- end: `0x18003e4cd`
- name: `?LoadResourceString@@YAKIPEAPEAG@Z`
- size: `217`
- prototype: `__int64 __fastcall(UINT uID, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004121c`

## callees

- `0x18003e3f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e41c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e49e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e41c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e49e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003e40e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003e40e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003e486`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003e486`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e445`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e45e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e4aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e445`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e45e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e4aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e453`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e4b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e453`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e4b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003e46c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003e46c`

## string_xrefs

- `0x18003e407`: `SRVSVC.DLL`

## pseudocode

```c
__int64 __fastcall LoadResourceString(UINT uID, unsigned __int16 **a2)
{
  HMODULE ModuleHandleA; // rbp
  DWORD LastError; // edi
  WCHAR *v6; // rbx
  unsigned int v7; // esi
  HANDLE ProcessHeap; // rax
  HANDLE v9; // rax
  WCHAR *v10; // rax
  int StringW; // eax
  HANDLE v12; // rax

  ModuleHandleA = GetModuleHandleA("SRVSVC.DLL");
  if ( ModuleHandleA )
  {
    v6 = 0;
    v7 = 256;
    LastError = 8;
    while ( 1 )
    {
      if ( v6 )
      {
        v7 *= 2;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v6);
      }
      v9 = GetProcessHeap();
      v10 = (WCHAR *)HeapAlloc(v9, 8u, 2LL * v7);
      v6 = v10;
      if ( !v10 )
        break;
      StringW = LoadStringW(ModuleHandleA, uID, v10, v7);
      if ( !StringW )
      {
        LastError = GetLastError();
        if ( LastError )
        {
          v12 = GetProcessHeap();
          HeapFree(v12, 0, v6);
        }
        return LastError;
      }
      if ( StringW != v7 - 1 )
      {
        LastError = 0;
        *a2 = v6;
        return LastError;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      return 6;
  }
  return LastError;
}

```

## disassembly

```asm
0x18003e3f4  push    rbx
0x18003e3f6  push    rbp
0x18003e3f7  push    rsi
0x18003e3f8  push    rdi
0x18003e3f9  push    r14
0x18003e3fb  push    r15
0x18003e3fd  sub     rsp, 28h
0x18003e401  mov     r15d, ecx
0x18003e404  mov     r14, rdx
0x18003e407  lea     rcx, aSrvsvcDll_0; "SRVSVC.DLL"
0x18003e40e  call    cs:__imp_GetModuleHandleA
0x18003e414  mov     rbp, rax
0x18003e417  test    rax, rax
0x18003e41a  jnz     short loc_18003E434
0x18003e41c  call    cs:__imp_GetLastError
0x18003e422  mov     edi, eax
0x18003e424  test    eax, eax
0x18003e426  jnz     loc_18003E4BE
0x18003e42c  lea     edi, [rbp+6]
0x18003e42f  jmp     loc_18003E4BE
0x18003e434  xor     ebx, ebx
0x18003e436  mov     esi, 100h
0x18003e43b  lea     edi, [rbx+8]
0x18003e43e  test    rbx, rbx
0x18003e441  jz      short loc_18003E459
0x18003e443  add     esi, esi
0x18003e445  call    cs:__imp_GetProcessHeap
0x18003e44b  mov     r8, rbx; lpMem
0x18003e44e  xor     edx, edx; dwFlags
0x18003e450  mov     rcx, rax; hHeap
0x18003e453  call    cs:__imp_HeapFree
0x18003e459  mov     ebx, esi
0x18003e45b  add     rbx, rbx
0x18003e45e  call    cs:__imp_GetProcessHeap
0x18003e464  mov     r8, rbx; dwBytes
0x18003e467  mov     edx, edi; dwFlags
0x18003e469  mov     rcx, rax; hHeap
0x18003e46c  call    cs:__imp_HeapAlloc
0x18003e472  mov     rbx, rax
0x18003e475  test    rax, rax
0x18003e478  jz      short loc_18003E4BE
0x18003e47a  mov     r9d, esi; cchBufferMax
0x18003e47d  mov     r8, rax; lpBuffer
0x18003e480  mov     edx, r15d; uID
0x18003e483  mov     rcx, rbp; hInstance
0x18003e486  call    cs:__imp_LoadStringW
0x18003e48c  test    eax, eax
0x18003e48e  jz      short loc_18003E49E
0x18003e490  lea     ecx, [rsi-1]
0x18003e493  cmp     eax, ecx
0x18003e495  jz      short loc_18003E43E
0x18003e497  xor     edi, edi
0x18003e499  mov     [r14], rbx
0x18003e49c  jmp     short loc_18003E4BE
0x18003e49e  call    cs:__imp_GetLastError
0x18003e4a4  mov     edi, eax
0x18003e4a6  test    eax, eax
0x18003e4a8  jz      short loc_18003E4BE
0x18003e4aa  call    cs:__imp_GetProcessHeap
0x18003e4b0  mov     r8, rbx; lpMem
0x18003e4b3  xor     edx, edx; dwFlags
0x18003e4b5  mov     rcx, rax; hHeap
0x18003e4b8  call    cs:__imp_HeapFree
0x18003e4be  mov     eax, edi
0x18003e4c0  add     rsp, 28h
0x18003e4c4  pop     r15
0x18003e4c6  pop     r14
0x18003e4c8  pop     rdi
0x18003e4c9  pop     rsi
0x18003e4ca  pop     rbp
0x18003e4cb  pop     rbx
0x18003e4cc  retn
```
