# PinCacheFlush

- ea: `0x1800395f4`
- end: `0x180039669`
- name: `PinCacheFlush`
- size: `117`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18002e034`
- `0x18002e52c`
- `0x18003a1a4`

## callees

- `0x180038fdc`
- `0x1800395f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003964f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003964f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039641`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039641`

## pseudocode

```c
__int64 __fastcall PinCacheFlush(_QWORD *a1, int a2, int a3)
{
  __int64 v4; // rcx
  unsigned int i; // ebx
  void *v7; // rbx
  HANDLE ProcessHeap; // rax

  if ( a1 )
  {
    v4 = *a1;
    if ( v4 )
    {
      if ( a3 )
      {
        for ( i = 0; i < 8; ++i )
          I_PinCacheFlush(*a1, i);
        v7 = (void *)*a1;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v7);
        *a1 = 0;
      }
      else
      {
        if ( (unsigned int)(a2 - 1) > 7 )
          return 160;
        I_PinCacheFlush(v4, (unsigned int)(a2 - 1));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800395f4  mov     [rsp+arg_0], rbx
0x1800395f9  push    rdi
0x1800395fa  sub     rsp, 20h
0x1800395fe  mov     rdi, rcx
0x180039601  test    rcx, rcx
0x180039604  jz      short loc_18003965C
0x180039606  mov     rcx, [rcx]
0x180039609  test    rcx, rcx
0x18003960c  jz      short loc_18003965C
0x18003960e  test    r8d, r8d
0x180039611  jnz     short loc_18003962B
0x180039613  lea     eax, [rdx-1]
0x180039616  cmp     eax, 7
0x180039619  ja      short loc_180039624
0x18003961b  dec     edx
0x18003961d  call    I_PinCacheFlush
0x180039622  jmp     short loc_18003965C
0x180039624  mov     eax, 0A0h
0x180039629  jmp     short loc_18003965E
0x18003962b  xor     ebx, ebx
0x18003962d  mov     rcx, [rdi]
0x180039630  mov     edx, ebx
0x180039632  call    I_PinCacheFlush
0x180039637  inc     ebx
0x180039639  cmp     ebx, 8
0x18003963c  jb      short loc_18003962D
0x18003963e  mov     rbx, [rdi]
0x180039641  call    cs:__imp_GetProcessHeap
0x180039647  mov     r8, rbx; lpMem
0x18003964a  xor     edx, edx; dwFlags
0x18003964c  mov     rcx, rax; hHeap
0x18003964f  call    cs:__imp_HeapFree
0x180039655  mov     qword ptr [rdi], 0
0x18003965c  xor     eax, eax
0x18003965e  mov     rbx, [rsp+28h+arg_0]
0x180039663  add     rsp, 20h
0x180039667  pop     rdi
0x180039668  retn
```
