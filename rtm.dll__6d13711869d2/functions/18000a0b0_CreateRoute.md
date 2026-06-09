# CreateRoute

- ea: `0x18000a0b0`
- end: `0x18000a1b3`
- name: `CreateRoute`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b440`

## callees

- `0x18000a0b0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000a0f3`
- `KERNEL32!HeapAlloc` at `0x18000a0f3`
- `KERNEL32!GetProcessHeap` at `0x18000a0e0`
- `KERNEL32!GetProcessHeap` at `0x18000a0e0`

## pseudocode

```c
__int64 __fastcall CreateRoute(__int64 a1, __int64 a2, volatile signed __int32 **a3)
{
  __int64 v3; // rax
  unsigned int v7; // ebp
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v9; // rax
  volatile signed __int32 *v10; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rax
  unsigned int v14; // r9d
  __int64 v15; // r8
  __int64 v16; // rcx

  v3 = *(_QWORD *)(a1 + 16);
  *a3 = 0;
  v7 = *(_DWORD *)(v3 + 308);
  ProcessHeap = GetProcessHeap();
  v9 = (volatile signed __int32 *)HeapAlloc(ProcessHeap, 8u, 8LL * (v7 - 1) + 112);
  v10 = v9;
  if ( !v9 )
    return 8;
  _InterlockedIncrement(v9);
  v12 = v9 + 2;
  v12[1] = v12;
  *v12 = v12;
  *((_QWORD *)v10 + 4) = v10 + 6;
  *((_QWORD *)v10 + 3) = v10 + 6;
  *((_QWORD *)v10 + 7) = a1 ^ 0x7754DF32;
  _InterlockedIncrement((volatile signed __int32 *)a1);
  v13 = *(_QWORD *)(a2 + 16);
  if ( v13 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v13 ^ 0x7754DF32));
    *((_QWORD *)v10 + 8) = *(_QWORD *)(a2 + 16);
  }
  *((_BYTE *)v10 + 72) = 0;
  *((_BYTE *)v10 + 73) = *(_BYTE *)(a2 + 25);
  *((_WORD *)v10 + 37) = *(_WORD *)(a2 + 26);
  *(_QWORD *)(v10 + 19) = *(_QWORD *)(a2 + 28);
  *((_DWORD *)v10 + 21) = *(_DWORD *)(a2 + 36);
  *((_QWORD *)v10 + 11) = *(_QWORD *)(a2 + 40);
  v14 = *(unsigned __int16 *)(a2 + 48);
  if ( v7 <= v14 )
    v14 = v7;
  v15 = 0;
  for ( *((_WORD *)v10 + 48) = v14; (unsigned int)v15 < v14; v15 = (unsigned int)(v15 + 1) )
  {
    v16 = *(_QWORD *)(a2 + 8 * v15 + 56);
    *(_QWORD *)&v10[2 * v15 + 26] = v16;
    _InterlockedIncrement((volatile signed __int32 *)(v16 ^ 0x7754DF32));
  }
  *a3 = v10;
  return 0;
}

```

## disassembly

```asm
0x18000a0b0  push    rbx
0x18000a0b2  push    rbp
0x18000a0b3  push    rsi
0x18000a0b4  push    rdi
0x18000a0b5  push    r14
0x18000a0b7  sub     rsp, 20h
0x18000a0bb  mov     rax, [rcx+10h]
0x18000a0bf  mov     r14, r8
0x18000a0c2  mov     rdi, rdx
0x18000a0c5  mov     qword ptr [r8], 0
0x18000a0cc  mov     rsi, rcx
0x18000a0cf  mov     ebp, [rax+134h]
0x18000a0d5  lea     eax, [rbp-1]
0x18000a0d8  lea     rbx, ds:70h[rax*8]
0x18000a0e0  call    cs:__imp_GetProcessHeap
0x18000a0e6  mov     r8, rbx; dwBytes
0x18000a0e9  mov     ebx, 8
0x18000a0ee  mov     edx, ebx; dwFlags
0x18000a0f0  mov     rcx, rax; hHeap
0x18000a0f3  call    cs:__imp_HeapAlloc
0x18000a0f9  mov     rdx, rax
0x18000a0fc  test    rax, rax
0x18000a0ff  jnz     short loc_18000A108
0x18000a101  mov     eax, ebx
0x18000a103  jmp     loc_18000A1A8
0x18000a108  lock inc dword ptr [rax]
0x18000a10b  add     rax, rbx
0x18000a10e  mov     r10d, 7754DF32h
0x18000a114  mov     [rax+8], rax
0x18000a118  mov     [rax], rax
0x18000a11b  lea     rax, [rdx+18h]
0x18000a11f  mov     [rax+8], rax
0x18000a123  mov     [rax], rax
0x18000a126  mov     rax, rsi
0x18000a129  xor     rax, r10
0x18000a12c  mov     [rdx+38h], rax
0x18000a130  lock inc dword ptr [rsi]
0x18000a133  mov     rax, [rdi+10h]
0x18000a137  test    rax, rax
0x18000a13a  jz      short loc_18000A14A
0x18000a13c  xor     rax, r10
0x18000a13f  lock inc dword ptr [rax]
0x18000a142  mov     rax, [rdi+10h]
0x18000a146  mov     [rdx+40h], rax
0x18000a14a  mov     byte ptr [rdx+48h], 0
0x18000a14e  mov     al, [rdi+19h]
0x18000a151  mov     [rdx+49h], al
0x18000a154  movzx   eax, word ptr [rdi+1Ah]
0x18000a158  mov     [rdx+4Ah], ax
0x18000a15c  mov     rax, [rdi+1Ch]
0x18000a160  mov     [rdx+4Ch], rax
0x18000a164  mov     eax, [rdi+24h]
0x18000a167  mov     [rdx+54h], eax
0x18000a16a  mov     rax, [rdi+28h]
0x18000a16e  mov     [rdx+58h], rax
0x18000a172  movzx   r9d, word ptr [rdi+30h]
0x18000a177  cmp     ebp, r9d
0x18000a17a  cmovbe  r9d, ebp
0x18000a17e  xor     r8d, r8d
0x18000a181  mov     [rdx+60h], r9w
0x18000a186  test    r9d, r9d
0x18000a189  jz      short loc_18000A1A3
0x18000a18b  mov     rcx, [rdi+r8*8+38h]
0x18000a190  mov     [rdx+r8*8+68h], rcx
0x18000a195  xor     rcx, r10
0x18000a198  lock inc dword ptr [rcx]
0x18000a19b  inc     r8d
0x18000a19e  cmp     r8d, r9d
0x18000a1a1  jb      short loc_18000A18B
0x18000a1a3  mov     [r14], rdx
0x18000a1a6  xor     eax, eax
0x18000a1a8  add     rsp, 20h
0x18000a1ac  pop     r14
0x18000a1ae  pop     rdi
0x18000a1af  pop     rsi
0x18000a1b0  pop     rbp
0x18000a1b1  pop     rbx
0x18000a1b2  retn
```
