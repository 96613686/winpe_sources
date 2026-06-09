# WdipDeleteParameterCollection

- ea: `0x1800079a0`
- end: `0x180007a3a`
- name: `WdipDeleteParameterCollection`
- size: `154`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002720`
- `0x1800063d0`
- `0x180006b40`
- `0x180006f10`

## callees

- `0x180007900`
- `0x1800079a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a1d`

## pseudocode

```c
void __fastcall WdipDeleteParameterCollection(_QWORD *a1)
{
  _QWORD *v2; // rdi
  __int64 i; // rbx
  _QWORD *v4; // rcx
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v7; // rbx
  HANDLE v8; // rax

  if ( a1 )
  {
    v2 = (_QWORD *)*a1;
    if ( *a1 && v2[1] )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)v2 + 1); i = (unsigned int)(i + 1) )
      {
        v4 = (_QWORD *)(v2[1] + 8 * i);
        if ( *v4 )
          WdipDeleteParameter(v4);
      }
      v5 = (void *)v2[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      v2[1] = 0;
    }
    v7 = (_QWORD *)*a1;
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v7);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x1800079a0  test    rcx, rcx
0x1800079a3  jz      locret_180007A39
0x1800079a9  push    rsi
0x1800079aa  sub     rsp, 20h
0x1800079ae  mov     [rsp+28h+arg_0], rbx
0x1800079b3  mov     rsi, rcx
0x1800079b6  mov     [rsp+28h+arg_8], rdi
0x1800079bb  mov     rdi, [rcx]
0x1800079be  test    rdi, rdi
0x1800079c1  jz      short loc_180007A0C
0x1800079c3  cmp     qword ptr [rdi+8], 0
0x1800079c8  jz      short loc_180007A0C
0x1800079ca  xor     ebx, ebx
0x1800079cc  cmp     [rdi+4], ebx
0x1800079cf  jbe     short loc_1800079EC
0x1800079d1  mov     rax, [rdi+8]
0x1800079d5  cmp     qword ptr [rax+rbx*8], 0
0x1800079da  lea     rcx, [rax+rbx*8]
0x1800079de  jz      short loc_1800079E5
0x1800079e0  call    WdipDeleteParameter
0x1800079e5  inc     ebx
0x1800079e7  cmp     ebx, [rdi+4]
0x1800079ea  jb      short loc_1800079D1
0x1800079ec  mov     rbx, [rdi+8]
0x1800079f0  call    cs:__imp_GetProcessHeap
0x1800079f6  mov     r8, rbx; lpMem
0x1800079f9  xor     edx, edx; dwFlags
0x1800079fb  mov     rcx, rax; hHeap
0x1800079fe  call    cs:__imp_HeapFree
0x180007a04  mov     qword ptr [rdi+8], 0
0x180007a0c  mov     rbx, [rsi]
0x180007a0f  call    cs:__imp_GetProcessHeap
0x180007a15  mov     r8, rbx; lpMem
0x180007a18  xor     edx, edx; dwFlags
0x180007a1a  mov     rcx, rax; hHeap
0x180007a1d  call    cs:__imp_HeapFree
0x180007a23  mov     rdi, [rsp+28h+arg_8]
0x180007a28  mov     rbx, [rsp+28h+arg_0]
0x180007a2d  mov     qword ptr [rsi], 0
0x180007a34  add     rsp, 20h
0x180007a38  pop     rsi
0x180007a39  retn
```
