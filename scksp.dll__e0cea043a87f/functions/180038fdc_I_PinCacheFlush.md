# I_PinCacheFlush

- ea: `0x180038fdc`
- end: `0x180039060`
- name: `I_PinCacheFlush`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800395f4`

## callees

- `0x180038fdc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039004`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039021`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039049`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039004`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039021`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039049`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038ff6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039013`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003903b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038ff6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039013`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003903b`

## pseudocode

```c
void __fastcall I_PinCacheFlush(__int64 a1, unsigned int a2)
{
  __int64 v2; // rbp
  _QWORD *v4; // rdi
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  void *v7; // rbx
  HANDLE v8; // rax
  __int64 v9; // rcx
  _BYTE *v10; // rax
  HANDLE v11; // rax

  v2 = a2;
  v4 = *(_QWORD **)(a1 + 8LL * a2);
  if ( v4 )
  {
    v5 = (void *)*v4;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
    v7 = (void *)v4[2];
    if ( v7 )
    {
      v8 = GetProcessHeap();
      HeapFree(v8, 0, v7);
    }
    v9 = 56;
    v10 = v4;
    do
    {
      *v10++ = 0;
      --v9;
    }
    while ( v9 );
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v4);
    *(_QWORD *)(a1 + 8 * v2) = 0;
  }
}

```

## disassembly

```asm
0x180038fdc  push    rbx
0x180038fde  push    rbp
0x180038fdf  push    rsi
0x180038fe0  push    rdi
0x180038fe1  sub     rsp, 28h
0x180038fe5  mov     ebp, edx
0x180038fe7  mov     rsi, rcx
0x180038fea  mov     rdi, [rcx+rbp*8]
0x180038fee  test    rdi, rdi
0x180038ff1  jz      short loc_180039057
0x180038ff3  mov     rbx, [rdi]
0x180038ff6  call    cs:__imp_GetProcessHeap
0x180038ffc  mov     r8, rbx; lpMem
0x180038fff  xor     edx, edx; dwFlags
0x180039001  mov     rcx, rax; hHeap
0x180039004  call    cs:__imp_HeapFree
0x18003900a  mov     rbx, [rdi+10h]
0x18003900e  test    rbx, rbx
0x180039011  jz      short loc_180039027
0x180039013  call    cs:__imp_GetProcessHeap
0x180039019  mov     r8, rbx; lpMem
0x18003901c  xor     edx, edx; dwFlags
0x18003901e  mov     rcx, rax; hHeap
0x180039021  call    cs:__imp_HeapFree
0x180039027  mov     ecx, 38h ; '8'
0x18003902c  mov     rax, rdi
0x18003902f  mov     byte ptr [rax], 0
0x180039032  inc     rax
0x180039035  sub     rcx, 1
0x180039039  jnz     short loc_18003902F
0x18003903b  call    cs:__imp_GetProcessHeap
0x180039041  mov     r8, rdi; lpMem
0x180039044  xor     edx, edx; dwFlags
0x180039046  mov     rcx, rax; hHeap
0x180039049  call    cs:__imp_HeapFree
0x18003904f  mov     qword ptr [rsi+rbp*8], 0
0x180039057  add     rsp, 28h
0x18003905b  pop     rdi
0x18003905c  pop     rsi
0x18003905d  pop     rbp
0x18003905e  pop     rbx
0x18003905f  retn
```
