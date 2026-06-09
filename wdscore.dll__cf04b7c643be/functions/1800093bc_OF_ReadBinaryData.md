# OF_ReadBinaryData

- ea: `0x1800093bc`
- end: `0x1800094da`
- name: `OF_ReadBinaryData`
- size: `286`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004830`
- `0x180007a1c`
- `0x180007c60`
- `0x180007f40`
- `0x1800080e0`
- `0x180008380`
- `0x1800094e0`
- `0x180009b98`
- `0x18000b1f0`

## callees

- `0x1800093bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009454`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000943d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000943d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094a2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180009402`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180009481`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180009402`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180009481`

## pseudocode

```c
__int64 __fastcall OF_ReadBinaryData(HANDLE *a1, void **a2, DWORD *a3)
{
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp+8h] BYREF
  SIZE_T dwBytes; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  LODWORD(dwBytes) = 0;
  NumberOfBytesRead = 0;
  if ( ReadFile(*a1, &dwBytes, 4u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 4 )
  {
    if ( !(_DWORD)dwBytes )
    {
      *a2 = 0;
      return 1;
    }
    v7 = (unsigned int)dwBytes;
    ProcessHeap = GetProcessHeap();
    v9 = HeapAlloc(ProcessHeap, 8u, v7);
    *a2 = v9;
    if ( v9 )
    {
      if ( ReadFile(*a1, v9, dwBytes, &NumberOfBytesRead, 0) && NumberOfBytesRead == (_DWORD)dwBytes )
      {
        *a3 = NumberOfBytesRead;
        return 1;
      }
      v10 = *a2;
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      *a2 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800093bc  mov     rax, rsp
0x1800093bf  mov     [rax+10h], rbx
0x1800093c3  push    rsi
0x1800093c4  push    rdi
0x1800093c5  push    r14
0x1800093c7  sub     rsp, 30h
0x1800093cb  mov     dword ptr [r8], 0
0x1800093d2  lea     r9, [rax+8]; lpNumberOfBytesRead
0x1800093d6  mov     rsi, r8
0x1800093d9  mov     dword ptr [rax+18h], 0
0x1800093e0  mov     rdi, rdx
0x1800093e3  mov     dword ptr [rax+8], 0
0x1800093ea  mov     r14, rcx
0x1800093ed  mov     qword ptr [rax-28h], 0
0x1800093f5  mov     rcx, [rcx]; hFile
0x1800093f8  lea     rdx, [rax+18h]; lpBuffer
0x1800093fc  mov     r8d, 4; nNumberOfBytesToRead
0x180009402  call    cs:__imp_ReadFile
0x180009409  nop     dword ptr [rax+rax+00h]
0x18000940e  test    eax, eax
0x180009410  jz      loc_1800094C9
0x180009416  cmp     [rsp+48h+NumberOfBytesRead], 4
0x18000941b  jnz     loc_1800094C9
0x180009421  mov     eax, dword ptr [rsp+48h+dwBytes]
0x180009425  test    eax, eax
0x180009427  jnz     short loc_18000943A
0x180009429  mov     qword ptr [rdi], 0
0x180009430  mov     eax, 1
0x180009435  jmp     loc_1800094CB
0x18000943a  mov     rbx, rax
0x18000943d  call    cs:__imp_GetProcessHeap
0x180009444  nop     dword ptr [rax+rax+00h]
0x180009449  mov     r8, rbx; dwBytes
0x18000944c  mov     edx, 8; dwFlags
0x180009451  mov     rcx, rax; hHeap
0x180009454  call    cs:__imp_HeapAlloc
0x18000945b  nop     dword ptr [rax+rax+00h]
0x180009460  mov     [rdi], rax
0x180009463  test    rax, rax
0x180009466  jz      short loc_1800094C9
0x180009468  mov     r8d, dword ptr [rsp+48h+dwBytes]; nNumberOfBytesToRead
0x18000946d  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180009472  mov     rcx, [r14]; hFile
0x180009475  mov     rdx, rax; lpBuffer
0x180009478  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180009481  call    cs:__imp_ReadFile
0x180009488  nop     dword ptr [rax+rax+00h]
0x18000948d  test    eax, eax
0x18000948f  jz      short loc_18000949F
0x180009491  mov     eax, [rsp+48h+NumberOfBytesRead]
0x180009495  cmp     eax, dword ptr [rsp+48h+dwBytes]
0x180009499  jnz     short loc_18000949F
0x18000949b  mov     [rsi], eax
0x18000949d  jmp     short loc_180009430
0x18000949f  mov     rbx, [rdi]
0x1800094a2  call    cs:__imp_GetProcessHeap
0x1800094a9  nop     dword ptr [rax+rax+00h]
0x1800094ae  mov     r8, rbx; lpMem
0x1800094b1  xor     edx, edx; dwFlags
0x1800094b3  mov     rcx, rax; hHeap
0x1800094b6  call    cs:__imp_HeapFree
0x1800094bd  nop     dword ptr [rax+rax+00h]
0x1800094c2  mov     qword ptr [rdi], 0
0x1800094c9  xor     eax, eax
0x1800094cb  mov     rbx, [rsp+48h+arg_8]
0x1800094d0  add     rsp, 30h
0x1800094d4  pop     r14
0x1800094d6  pop     rdi
0x1800094d7  pop     rsi
0x1800094d8  retn
```
