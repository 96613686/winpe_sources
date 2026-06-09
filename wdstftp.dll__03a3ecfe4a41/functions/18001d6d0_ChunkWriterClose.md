# ChunkWriterClose

- ea: `0x18001d6d0`
- end: `0x18001d7c2`
- name: `ChunkWriterClose`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f278`

## callees

- `0x18001d6d0`
- `0x18001d9b4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001d737`
- `KERNEL32!HeapFree` at `0x18001d792`
- `KERNEL32!HeapFree` at `0x18001d737`
- `KERNEL32!HeapFree` at `0x18001d792`
- `KERNEL32!DeleteCriticalSection` at `0x18001d700`
- `KERNEL32!DeleteCriticalSection` at `0x18001d700`
- `KERNEL32!GetProcessHeap` at `0x18001d723`
- `KERNEL32!GetProcessHeap` at `0x18001d77e`
- `KERNEL32!GetProcessHeap` at `0x18001d723`
- `KERNEL32!GetProcessHeap` at `0x18001d77e`

## pseudocode

```c
void __fastcall ChunkWriterClose(__int64 a1)
{
  _QWORD **v2; // rsi
  __int64 v3; // r14
  _QWORD *v4; // rbp
  _QWORD *v5; // rbx
  HANDLE ProcessHeap; // rax
  __int64 i; // rbx
  void *v8; // rbx
  HANDLE v9; // rax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF

  v10[0] = *(_QWORD *)(a1 + 40);
  v10[1] = *(_QWORD *)(a1 + 80);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v2 = (_QWORD **)v10;
  v3 = 2;
  do
  {
    v4 = *v2;
    if ( *v2 )
    {
      do
      {
        v5 = (_QWORD *)v4[3];
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v4);
        v4 = v5;
      }
      while ( v5 );
    }
    ++v2;
    --v3;
  }
  while ( v3 );
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 48); i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *(_DWORD *)(a1 + 72) )
      break;
    FreeChunkInfo(*(LPVOID *)(*(_QWORD *)(a1 + 56) + 8 * i));
  }
  v8 = *(void **)(a1 + 56);
  if ( v8 )
  {
    v9 = GetProcessHeap();
    if ( HeapFree(v9, 0, v8) )
      *(_QWORD *)(a1 + 56) = 0;
  }
}

```

## disassembly

```asm
0x18001d6d0  mov     r11, rsp
0x18001d6d3  mov     [r11+8], rbx
0x18001d6d7  mov     [r11+10h], rbp
0x18001d6db  mov     [r11+18h], rsi
0x18001d6df  mov     [r11+20h], rdi
0x18001d6e3  push    r14
0x18001d6e5  sub     rsp, 30h
0x18001d6e9  mov     rax, [rcx+28h]
0x18001d6ed  mov     rdi, rcx
0x18001d6f0  mov     [r11-18h], rax
0x18001d6f4  mov     rax, [rcx+50h]
0x18001d6f8  add     rcx, 58h ; 'X'; lpCriticalSection
0x18001d6fc  mov     [r11-10h], rax
0x18001d700  call    cs:__imp_DeleteCriticalSection
0x18001d707  nop     dword ptr [rax+rax+00h]
0x18001d70c  lea     rsi, [rsp+38h+var_18]
0x18001d711  mov     r14d, 2
0x18001d717  mov     rbp, [rsi]
0x18001d71a  test    rbp, rbp
0x18001d71d  jz      short loc_18001D74B
0x18001d71f  mov     rbx, [rbp+18h]
0x18001d723  call    cs:__imp_GetProcessHeap
0x18001d72a  nop     dword ptr [rax+rax+00h]
0x18001d72f  mov     r8, rbp; lpMem
0x18001d732  xor     edx, edx; dwFlags
0x18001d734  mov     rcx, rax; hHeap
0x18001d737  call    cs:__imp_HeapFree
0x18001d73e  nop     dword ptr [rax+rax+00h]
0x18001d743  mov     rbp, rbx
0x18001d746  test    rbx, rbx
0x18001d749  jnz     short loc_18001D71F
0x18001d74b  add     rsi, 8
0x18001d74f  sub     r14, 1
0x18001d753  jnz     short loc_18001D717
0x18001d755  xor     ebx, ebx
0x18001d757  cmp     [rdi+30h], ebx
0x18001d75a  jbe     short loc_18001D775
0x18001d75c  cmp     ebx, [rdi+48h]
0x18001d75f  jnb     short loc_18001D775
0x18001d761  mov     rcx, [rdi+38h]
0x18001d765  mov     rcx, [rcx+rbx*8]; lpMem
0x18001d769  call    FreeChunkInfo
0x18001d76e  inc     ebx
0x18001d770  cmp     ebx, [rdi+30h]
0x18001d773  jb      short loc_18001D75C
0x18001d775  mov     rbx, [rdi+38h]
0x18001d779  test    rbx, rbx
0x18001d77c  jz      short loc_18001D7A7
0x18001d77e  call    cs:__imp_GetProcessHeap
0x18001d785  nop     dword ptr [rax+rax+00h]
0x18001d78a  mov     r8, rbx; lpMem
0x18001d78d  xor     edx, edx; dwFlags
0x18001d78f  mov     rcx, rax; hHeap
0x18001d792  call    cs:__imp_HeapFree
0x18001d799  nop     dword ptr [rax+rax+00h]
0x18001d79e  test    eax, eax
0x18001d7a0  jz      short loc_18001D7A7
0x18001d7a2  and     qword ptr [rdi+38h], 0
0x18001d7a7  mov     rbx, [rsp+38h+arg_0]
0x18001d7ac  mov     rbp, [rsp+38h+arg_8]
0x18001d7b1  mov     rsi, [rsp+38h+arg_10]
0x18001d7b6  mov     rdi, [rsp+38h+arg_18]
0x18001d7bb  add     rsp, 30h
0x18001d7bf  pop     r14
0x18001d7c1  retn
```
