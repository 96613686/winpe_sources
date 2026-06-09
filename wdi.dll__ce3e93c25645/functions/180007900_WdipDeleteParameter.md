# WdipDeleteParameter

- ea: `0x180007900`
- end: `0x180007991`
- name: `WdipDeleteParameter`
- size: `145`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800077e0`
- `0x1800079a0`
- `0x180007b00`
- `0x18000cc8c`
- `0x18000e9e0`
- `0x18000f08c`

## callees

- `0x180007900`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007927`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007947`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007966`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007927`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007947`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007966`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007935`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007955`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007974`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007935`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007955`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007974`

## pseudocode

```c
void __fastcall WdipDeleteParameter(_QWORD *a1)
{
  _QWORD *v2; // rsi
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  void *v5; // rbx
  HANDLE v6; // rax
  _QWORD *v7; // rbx
  HANDLE v8; // rax

  if ( a1 )
  {
    v2 = (_QWORD *)*a1;
    if ( *a1 )
    {
      v3 = (void *)v2[6];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
      v5 = (void *)v2[7];
      v2[6] = 0;
      v6 = GetProcessHeap();
      HeapFree(v6, 0, v5);
      v2[7] = 0;
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
0x180007900  test    rcx, rcx
0x180007903  jz      locret_180007990
0x180007909  push    rdi
0x18000790a  sub     rsp, 20h
0x18000790e  mov     [rsp+28h+arg_0], rbx
0x180007913  mov     rdi, rcx
0x180007916  mov     [rsp+28h+arg_8], rsi
0x18000791b  mov     rsi, [rcx]
0x18000791e  test    rsi, rsi
0x180007921  jz      short loc_180007963
0x180007923  mov     rbx, [rsi+30h]
0x180007927  call    cs:__imp_GetProcessHeap
0x18000792d  mov     r8, rbx; lpMem
0x180007930  xor     edx, edx; dwFlags
0x180007932  mov     rcx, rax; hHeap
0x180007935  call    cs:__imp_HeapFree
0x18000793b  mov     rbx, [rsi+38h]
0x18000793f  mov     qword ptr [rsi+30h], 0
0x180007947  call    cs:__imp_GetProcessHeap
0x18000794d  mov     r8, rbx; lpMem
0x180007950  xor     edx, edx; dwFlags
0x180007952  mov     rcx, rax; hHeap
0x180007955  call    cs:__imp_HeapFree
0x18000795b  mov     qword ptr [rsi+38h], 0
0x180007963  mov     rbx, [rdi]
0x180007966  call    cs:__imp_GetProcessHeap
0x18000796c  mov     r8, rbx; lpMem
0x18000796f  xor     edx, edx; dwFlags
0x180007971  mov     rcx, rax; hHeap
0x180007974  call    cs:__imp_HeapFree
0x18000797a  mov     rsi, [rsp+28h+arg_8]
0x18000797f  mov     rbx, [rsp+28h+arg_0]
0x180007984  mov     qword ptr [rdi], 0
0x18000798b  add     rsp, 20h
0x18000798f  pop     rdi
0x180007990  retn
```
