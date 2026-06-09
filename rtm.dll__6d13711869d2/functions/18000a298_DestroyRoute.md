# DestroyRoute

- ea: `0x18000a298`
- end: `0x18000a35f`
- name: `DestroyRoute`
- size: `199`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x1800060a0`
- `0x180006d70`
- `0x180007220`
- `0x180007530`
- `0x180007740`
- `0x180008ebc`
- `0x18000b440`
- `0x18000c560`
- `0x18000cf90`
- `0x18000d8c0`
- `0x18000d9d0`

## callees

- `0x180009adc`
- `0x18000a1bc`
- `0x18000a230`
- `0x18000a298`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000a32c`
- `KERNEL32!GetProcessHeap` at `0x18000a340`
- `KERNEL32!GetProcessHeap` at `0x18000a32c`
- `KERNEL32!GetProcessHeap` at `0x18000a340`
- `KERNEL32!HeapFree` at `0x18000a33a`
- `KERNEL32!HeapFree` at `0x18000a34e`
- `KERNEL32!HeapFree` at `0x18000a33a`
- `KERNEL32!HeapFree` at `0x18000a34e`

## pseudocode

```c
__int64 __fastcall DestroyRoute(_QWORD *lpMem)
{
  __int64 i; // rdi
  void *v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx
  char *v6; // rcx
  __int64 v7; // rcx
  void *v8; // rcx
  void *v9; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v11; // rax

  for ( i = 0; (unsigned int)i < *((unsigned __int16 *)lpMem + 48); i = (unsigned int)(i + 1) )
  {
    v3 = (void *)(lpMem[i + 13] ^ 0x7754DF32LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3, 0xFFFFFFFF) == 1 )
      DestroyNextHop(v3);
  }
  v4 = lpMem[8];
  if ( v4 )
  {
    v5 = (void *)(v4 ^ 0x7754DF32);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5, 0xFFFFFFFF) == 1 )
      DestroyNextHop(v5);
  }
  v6 = (char *)(lpMem[7] ^ 0x7754DF32LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
    DestroyEntity(v6);
  v7 = lpMem[6];
  if ( v7 )
  {
    v8 = (void *)(v7 ^ 0x7754DF32);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
      DestroyDest(v8);
  }
  v9 = (void *)lpMem[5];
  if ( v9 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
  }
  v11 = GetProcessHeap();
  HeapFree(v11, 0, lpMem);
  return 0;
}

```

## disassembly

```asm
0x18000a298  push    rbx
0x18000a29a  push    rbp
0x18000a29b  push    rsi
0x18000a29c  push    rdi
0x18000a29d  sub     rsp, 28h
0x18000a2a1  xor     edi, edi
0x18000a2a3  xor     eax, eax
0x18000a2a5  or      esi, 0FFFFFFFFh
0x18000a2a8  mov     rbx, rcx
0x18000a2ab  mov     ebp, 7754DF32h
0x18000a2b0  cmp     ax, [rcx+60h]
0x18000a2b4  jnb     short loc_18000A2D7
0x18000a2b6  mov     rcx, [rbx+rdi*8+68h]
0x18000a2bb  mov     eax, esi
0x18000a2bd  xor     rcx, rbp; lpMem
0x18000a2c0  lock xadd [rcx], eax
0x18000a2c4  add     eax, esi
0x18000a2c6  jnz     short loc_18000A2CD
0x18000a2c8  call    DestroyNextHop
0x18000a2cd  movzx   eax, word ptr [rbx+60h]
0x18000a2d1  inc     edi
0x18000a2d3  cmp     edi, eax
0x18000a2d5  jb      short loc_18000A2B6
0x18000a2d7  mov     rcx, [rbx+40h]
0x18000a2db  test    rcx, rcx
0x18000a2de  jz      short loc_18000A2F2
0x18000a2e0  xor     rcx, rbp; lpMem
0x18000a2e3  mov     eax, esi
0x18000a2e5  lock xadd [rcx], eax
0x18000a2e9  add     eax, esi
0x18000a2eb  jnz     short loc_18000A2F2
0x18000a2ed  call    DestroyNextHop
0x18000a2f2  mov     rcx, [rbx+38h]
0x18000a2f6  mov     eax, esi
0x18000a2f8  xor     rcx, rbp; lpMem
0x18000a2fb  lock xadd [rcx], eax
0x18000a2ff  add     eax, esi
0x18000a301  jnz     short loc_18000A308
0x18000a303  call    DestroyEntity
0x18000a308  mov     rcx, [rbx+30h]
0x18000a30c  test    rcx, rcx
0x18000a30f  jz      short loc_18000A323
0x18000a311  xor     rcx, rbp; lpMem
0x18000a314  mov     eax, esi
0x18000a316  lock xadd [rcx], eax
0x18000a31a  add     eax, esi
0x18000a31c  jnz     short loc_18000A323
0x18000a31e  call    DestroyDest
0x18000a323  mov     rdi, [rbx+28h]
0x18000a327  test    rdi, rdi
0x18000a32a  jz      short loc_18000A340
0x18000a32c  call    cs:__imp_GetProcessHeap
0x18000a332  mov     r8, rdi; lpMem
0x18000a335  xor     edx, edx; dwFlags
0x18000a337  mov     rcx, rax; hHeap
0x18000a33a  call    cs:__imp_HeapFree
0x18000a340  call    cs:__imp_GetProcessHeap
0x18000a346  mov     r8, rbx; lpMem
0x18000a349  xor     edx, edx; dwFlags
0x18000a34b  mov     rcx, rax; hHeap
0x18000a34e  call    cs:__imp_HeapFree
0x18000a354  xor     eax, eax
0x18000a356  add     rsp, 28h
0x18000a35a  pop     rdi
0x18000a35b  pop     rsi
0x18000a35c  pop     rbp
0x18000a35d  pop     rbx
0x18000a35e  retn
```
