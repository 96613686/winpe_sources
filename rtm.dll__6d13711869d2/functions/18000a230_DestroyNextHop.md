# DestroyNextHop

- ea: `0x18000a230`
- end: `0x18000a292`
- name: `DestroyNextHop`
- size: `98`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180006d00`
- `0x180007350`
- `0x180008910`
- `0x180008ba0`
- `0x18000a298`
- `0x18000b440`

## callees

- `0x180009adc`
- `0x18000a1bc`
- `0x18000a230`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000a276`
- `KERNEL32!GetProcessHeap` at `0x18000a276`
- `KERNEL32!HeapFree` at `0x18000a284`
- `KERNEL32!HeapFree` at `0x18000a284`

## pseudocode

```c
__int64 __fastcall DestroyNextHop(_QWORD *lpMem)
{
  __int64 v2; // rcx
  LPVOID *v3; // rcx
  char *v4; // rcx
  HANDLE ProcessHeap; // rax

  v2 = lpMem[9];
  if ( v2 )
  {
    v3 = (LPVOID *)(v2 ^ 0x7754DF32);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3, 0xFFFFFFFF) == 1 )
      DestroyDest(v3);
  }
  v4 = (char *)(lpMem[6] ^ 0x7754DF32LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4, 0xFFFFFFFF) == 1 )
    DestroyEntity(v4);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, lpMem);
  return 0;
}

```

## disassembly

```asm
0x18000a230  push    rbx
0x18000a232  sub     rsp, 20h
0x18000a236  mov     rbx, rcx
0x18000a239  mov     rcx, [rcx+48h]
0x18000a23d  test    rcx, rcx
0x18000a240  jz      short loc_18000A25A
0x18000a242  xor     rcx, 7754DF32h; lpMem
0x18000a249  or      eax, 0FFFFFFFFh
0x18000a24c  lock xadd [rcx], eax
0x18000a250  cmp     eax, 1
0x18000a253  jnz     short loc_18000A25A
0x18000a255  call    DestroyDest
0x18000a25a  mov     rcx, [rbx+30h]
0x18000a25e  xor     rcx, 7754DF32h; lpMem
0x18000a265  or      eax, 0FFFFFFFFh
0x18000a268  lock xadd [rcx], eax
0x18000a26c  cmp     eax, 1
0x18000a26f  jnz     short loc_18000A276
0x18000a271  call    DestroyEntity
0x18000a276  call    cs:__imp_GetProcessHeap
0x18000a27c  mov     r8, rbx; lpMem
0x18000a27f  xor     edx, edx; dwFlags
0x18000a281  mov     rcx, rax; hHeap
0x18000a284  call    cs:__imp_HeapFree
0x18000a28a  xor     eax, eax
0x18000a28c  add     rsp, 20h
0x18000a290  pop     rbx
0x18000a291  retn
```
