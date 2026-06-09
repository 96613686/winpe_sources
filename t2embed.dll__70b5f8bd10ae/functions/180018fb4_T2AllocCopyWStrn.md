# T2AllocCopyWStrn

- ea: `0x180018fb4`
- end: `0x18001900c`
- name: `T2AllocCopyWStrn`
- size: `88`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001862c`
- `0x1800190a4`
- `0x180021020`

## callees

- `0x180018fb4`
- `0x18002a54e`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180018fd8`
- `KERNEL32!HeapAlloc` at `0x180018fd8`
- `KERNEL32!GetProcessHeap` at `0x180018fca`
- `KERNEL32!GetProcessHeap` at `0x180018fca`

## pseudocode

```c
_WORD *__fastcall T2AllocCopyWStrn(void *Src, unsigned __int16 a2)
{
  __int64 v2; // rsi
  unsigned int v4; // ebx
  HANDLE ProcessHeap; // rax
  _WORD *result; // rax
  _WORD *v7; // rdi

  v2 = a2;
  v4 = 2 * a2 + 2;
  ProcessHeap = GetProcessHeap();
  result = HeapAlloc(ProcessHeap, 0, v4);
  v7 = result;
  if ( result )
  {
    memcpy_0(result, Src, 2 * v2);
    v7[v2] = 0;
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180018fb4  push    rbx
0x180018fb6  push    rbp
0x180018fb7  push    rsi
0x180018fb8  push    rdi
0x180018fb9  sub     rsp, 28h
0x180018fbd  movzx   esi, dx
0x180018fc0  mov     rbp, rcx
0x180018fc3  lea     ebx, ds:2[rsi*2]
0x180018fca  call    cs:__imp_GetProcessHeap
0x180018fd0  mov     r8d, ebx; dwBytes
0x180018fd3  xor     edx, edx; dwFlags
0x180018fd5  mov     rcx, rax; hHeap
0x180018fd8  call    cs:__imp_HeapAlloc
0x180018fde  mov     rdi, rax
0x180018fe1  test    rax, rax
0x180018fe4  jz      short loc_18001900A
0x180018fe6  lea     rbx, [rsi+rsi]
0x180018fea  mov     rdx, rbp; Src
0x180018fed  mov     r8, rbx; Size
0x180018ff0  mov     rcx, rax; void *
0x180018ff3  call    memcpy_0
0x180018ff8  xor     eax, eax
0x180018ffa  mov     [rbx+rdi], ax
0x180018ffe  mov     rax, rdi
0x180019001  add     rsp, 28h
0x180019005  pop     rdi
0x180019006  pop     rsi
0x180019007  pop     rbp
0x180019008  pop     rbx
0x180019009  retn
0x18001900a  jmp     short loc_180019001
```
