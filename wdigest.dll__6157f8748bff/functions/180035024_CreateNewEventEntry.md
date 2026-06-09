# CreateNewEventEntry

- ea: `0x180035024`
- end: `0x18003522d`
- name: `CreateNewEventEntry`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010290`

## callees

- `0x180034f94`
- `0x180035024`
- `0x1800377bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800350cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800350cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800350bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800350bf`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(__int128 *a1, unsigned __int8 a2, __int64 a3, char a4, int a5, __int64 *a6)
{
  __int64 v6; // r10
  __int64 v7; // r14
  unsigned __int8 v8; // r11
  __int64 v9; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  SIZE_T v15; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int8 v17; // si
  __int64 NextOffset; // r13
  bool v19; // zf
  __int64 v20; // rbp
  unsigned __int8 v21; // r15
  __int64 v22; // r15
  unsigned int v23; // edx
  void *v24; // rbx
  __int64 v25; // rsi
  __int128 v26; // xmm0
  __int64 v27; // rdi
  unsigned int v28; // edx
  void *v29; // rbx
  _QWORD v30[9]; // [rsp+20h] [rbp-48h] BYREF

  v6 = 0;
  v7 = a2;
  v8 = 0;
  v9 = 0;
  *a6 = 0;
  if ( (_BYTE)v7 )
  {
    do
    {
      v12 = *(unsigned int *)(a3 + 16LL * v8 + 8);
      if ( v8 >= 2u )
        v6 += v12;
      v13 = v12 + v9;
      if ( v8 >= 2u )
        v13 = v9;
      ++v8;
      v9 = v13;
    }
    while ( v8 < (unsigned __int8)v7 );
    if ( (unsigned __int64)(v6 + v13) > 0xFFFF )
      return 534;
  }
  v15 = v6 + 16 * v7 + 46;
  if ( !v15 )
    return 8;
  ProcessHeap = GetProcessHeap();
  v30[0] = HeapAlloc(ProcessHeap, 8u, v15);
  if ( !v30[0] )
    return 8;
  v30[1] = v15;
  v17 = 0;
  NextOffset = CBufferGetNextOffset(v30, 16 * v7);
  v19 = a4 == -2;
  LOBYTE(v20) = a4 + 2;
  v21 = v20;
  if ( !v19 )
  {
    v22 = 0;
    do
    {
      if ( v17 >= 2u )
      {
        v24 = (void *)CBufferGetNextOffset(v30, *(unsigned int *)(a3 + 16 * v22 + 8));
        memcpy_0(v24, *(const void **)(a3 + 16 * v22), v23);
        *(_QWORD *)(NextOffset + 16 * v22) = v24;
        *(_DWORD *)(NextOffset + 16 * v22 + 12) = *(_DWORD *)(a3 + 16 * v22 + 12);
        *(_DWORD *)(NextOffset + 16 * v22 + 8) = *(_DWORD *)(a3 + 16 * v22 + 8);
      }
      else
      {
        *(_OWORD *)(NextOffset + 16 * v22) = *(_OWORD *)(a3 + 16 * v22);
      }
      ++v17;
      ++v22;
    }
    while ( v17 < (unsigned __int8)v20 );
    v21 = v20;
  }
  v25 = CBufferGetNextOffset(v30, 46);
  *(_QWORD *)(v25 + 16) = NextOffset;
  v26 = *a1;
  *(_BYTE *)(v25 + 45) = a4;
  *(_DWORD *)(v25 + 40) = a5;
  *(_BYTE *)(v25 + 44) = v7;
  *(_OWORD *)v25 = v26;
  if ( v21 < (unsigned __int8)v7 )
  {
    v20 = (unsigned __int8)v20;
    do
    {
      v27 = 2 * v20;
      v29 = (void *)CBufferGetNextOffset(v30, *(unsigned int *)(a3 + 16 * v20 + 8));
      memcpy_0(v29, *(const void **)(a3 + 16 * v20), v28);
      ++v21;
      ++v20;
      *(_QWORD *)(*(_QWORD *)(v25 + 16) + 8 * v27) = v29;
      *(_DWORD *)(*(_QWORD *)(v25 + 16) + 8 * v27 + 12) = *(_DWORD *)(a3 + 8 * v27 + 12);
      *(_DWORD *)(*(_QWORD *)(v25 + 16) + 8 * v27 + 8) = *(_DWORD *)(a3 + 8 * v27 + 8);
    }
    while ( v21 < (unsigned __int8)v7 );
  }
  *a6 = v25;
  return 0;
}

```

## disassembly

```asm
0x180035024  mov     [rsp+arg_10], rbx
0x180035029  mov     [rsp+arg_18], r9b
0x18003502e  mov     [rsp+arg_0], rcx
0x180035033  push    rbp
0x180035034  push    rsi
0x180035035  push    rdi
0x180035036  push    r12
0x180035038  push    r13
0x18003503a  push    r14
0x18003503c  push    r15
0x18003503e  sub     rsp, 30h
0x180035042  mov     rax, [rsp+68h+arg_28]
0x18003504a  xor     r10d, r10d
0x18003504d  movzx   r14d, dl
0x180035051  xor     r11b, r11b
0x180035054  xor     edx, edx
0x180035056  mov     bpl, r9b
0x180035059  mov     r12, r8
0x18003505c  mov     r15b, 2
0x18003505f  mov     [rax], rdx
0x180035062  test    r14b, r14b
0x180035065  jz      short loc_1800350A6
0x180035067  movzx   eax, r11b
0x18003506b  add     rax, rax
0x18003506e  cmp     r11b, r15b
0x180035071  mov     ecx, [r8+rax*8+8]
0x180035076  lea     rax, [rcx+r10]
0x18003507a  cmovnb  r10, rax
0x18003507e  lea     rax, [rcx+rdx]
0x180035082  cmovnb  rax, rdx
0x180035086  inc     r11b
0x180035089  mov     rdx, rax
0x18003508c  cmp     r11b, r14b
0x18003508f  jb      short loc_180035067
0x180035091  add     rax, r10
0x180035094  cmp     rax, 0FFFFh
0x18003509a  jbe     short loc_1800350A6
0x18003509c  mov     eax, 216h
0x1800350a1  jmp     loc_180035215
0x1800350a6  mov     rbx, r14
0x1800350a9  mov     esi, 8
0x1800350ae  shl     rbx, 4
0x1800350b2  lea     rdi, [rbx+2Eh]
0x1800350b6  add     rdi, r10
0x1800350b9  jz      loc_180035213
0x1800350bf  call    cs:__imp_GetProcessHeap
0x1800350c5  mov     r8, rdi; dwBytes
0x1800350c8  mov     edx, esi; dwFlags
0x1800350ca  mov     rcx, rax; hHeap
0x1800350cd  call    cs:__imp_HeapAlloc
0x1800350d3  mov     [rsp+68h+var_48], rax
0x1800350d8  test    rax, rax
0x1800350db  jz      loc_180035213
0x1800350e1  mov     rdx, rbx
0x1800350e4  mov     [rsp+68h+var_40], rdi
0x1800350e9  lea     rcx, [rsp+68h+var_48]
0x1800350ee  call    CBufferGetNextOffset
0x1800350f3  xor     sil, sil
0x1800350f6  mov     r13, rax
0x1800350f9  add     bpl, r15b
0x1800350fc  mov     r15b, bpl
0x1800350ff  mov     [rsp+68h+arg_8], r15d
0x180035104  jz      short loc_18003516D
0x180035106  xor     r15d, r15d
0x180035109  mov     rdi, r15
0x18003510c  add     rdi, rdi
0x18003510f  cmp     sil, 2
0x180035113  jnb     short loc_180035123
0x180035115  movups  xmm0, xmmword ptr [r12+rdi*8]
0x18003511a  movdqu  xmmword ptr [r13+rdi*8+0], xmm0
0x180035121  jmp     short loc_18003515D
0x180035123  mov     edx, [r12+rdi*8+8]
0x180035128  lea     rcx, [rsp+68h+var_48]
0x18003512d  call    CBufferGetNextOffset
0x180035132  mov     r8d, edx; Size
0x180035135  mov     rcx, rax; void *
0x180035138  mov     rdx, [r12+rdi*8]; Src
0x18003513c  mov     rbx, rax
0x18003513f  call    memcpy_0
0x180035144  mov     [r13+rdi*8+0], rbx
0x180035149  mov     eax, [r12+rdi*8+0Ch]
0x18003514e  mov     [r13+rdi*8+0Ch], eax
0x180035153  mov     eax, [r12+rdi*8+8]
0x180035158  mov     [r13+rdi*8+8], eax
0x18003515d  inc     sil
0x180035160  inc     r15
0x180035163  cmp     sil, bpl
0x180035166  jb      short loc_180035109
0x180035168  mov     r15d, [rsp+68h+arg_8]
0x18003516d  mov     edx, 2Eh ; '.'
0x180035172  lea     rcx, [rsp+68h+var_48]
0x180035177  call    CBufferGetNextOffset
0x18003517c  mov     rsi, rax
0x18003517f  mov     [rax+10h], r13
0x180035183  mov     rax, [rsp+68h+arg_0]
0x180035188  movups  xmm0, xmmword ptr [rax]
0x18003518b  mov     al, [rsp+68h+arg_18]
0x180035192  mov     [rsi+2Dh], al
0x180035195  mov     eax, [rsp+68h+arg_20]
0x18003519c  mov     [rsi+28h], eax
0x18003519f  mov     [rsi+2Ch], r14b
0x1800351a3  movdqu  xmmword ptr [rsi], xmm0
0x1800351a7  cmp     r15b, r14b
0x1800351aa  jnb     short loc_180035204
0x1800351ac  movzx   ebp, bpl
0x1800351b0  mov     rdi, rbp
0x1800351b3  lea     rcx, [rsp+68h+var_48]
0x1800351b8  add     rdi, rdi
0x1800351bb  mov     edx, [r12+rdi*8+8]
0x1800351c0  call    CBufferGetNextOffset
0x1800351c5  mov     r8d, edx; Size
0x1800351c8  mov     rcx, rax; void *
0x1800351cb  mov     rdx, [r12+rdi*8]; Src
0x1800351cf  mov     rbx, rax
0x1800351d2  call    memcpy_0
0x1800351d7  mov     rax, [rsi+10h]
0x1800351db  inc     r15b
0x1800351de  inc     rbp
0x1800351e1  mov     [rax+rdi*8], rbx
0x1800351e5  mov     rcx, [rsi+10h]
0x1800351e9  mov     eax, [r12+rdi*8+0Ch]
0x1800351ee  mov     [rcx+rdi*8+0Ch], eax
0x1800351f2  mov     rcx, [rsi+10h]
0x1800351f6  mov     eax, [r12+rdi*8+8]
0x1800351fb  mov     [rcx+rdi*8+8], eax
0x1800351ff  cmp     r15b, r14b
0x180035202  jb      short loc_1800351B0
0x180035204  mov     rax, [rsp+68h+arg_28]
0x18003520c  mov     [rax], rsi
0x18003520f  xor     eax, eax
0x180035211  jmp     short loc_180035215
0x180035213  mov     eax, esi
0x180035215  mov     rbx, [rsp+68h+arg_10]
0x18003521d  add     rsp, 30h
0x180035221  pop     r15
0x180035223  pop     r14
0x180035225  pop     r13
0x180035227  pop     r12
0x180035229  pop     rdi
0x18003522a  pop     rsi
0x18003522b  pop     rbp
0x18003522c  retn
```
