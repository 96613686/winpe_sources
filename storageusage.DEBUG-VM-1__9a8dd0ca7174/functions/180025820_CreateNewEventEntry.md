# CreateNewEventEntry

- ea: `0x180025820`
- end: `0x180025a29`
- name: `CreateNewEventEntry`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180025d50`

## callees

- `0x1800256fc`
- `0x180025820`
- `0x18002af90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800258bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800258bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800258c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800258c9`

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
0x180025820  mov     [rsp+arg_10], rbx
0x180025825  mov     [rsp+arg_18], r9b
0x18002582a  mov     [rsp+arg_0], rcx
0x18002582f  push    rbp
0x180025830  push    rsi
0x180025831  push    rdi
0x180025832  push    r12
0x180025834  push    r13
0x180025836  push    r14
0x180025838  push    r15
0x18002583a  sub     rsp, 30h
0x18002583e  mov     rax, [rsp+68h+arg_28]
0x180025846  xor     r10d, r10d
0x180025849  movzx   r14d, dl
0x18002584d  xor     r11b, r11b
0x180025850  xor     edx, edx
0x180025852  mov     bpl, r9b
0x180025855  mov     r12, r8
0x180025858  mov     r15b, 2
0x18002585b  mov     [rax], rdx
0x18002585e  test    r14b, r14b
0x180025861  jz      short loc_1800258A2
0x180025863  movzx   eax, r11b
0x180025867  add     rax, rax
0x18002586a  cmp     r11b, r15b
0x18002586d  mov     ecx, [r8+rax*8+8]
0x180025872  lea     rax, [rcx+r10]
0x180025876  cmovnb  r10, rax
0x18002587a  lea     rax, [rcx+rdx]
0x18002587e  cmovnb  rax, rdx
0x180025882  inc     r11b
0x180025885  mov     rdx, rax
0x180025888  cmp     r11b, r14b
0x18002588b  jb      short loc_180025863
0x18002588d  add     rax, r10
0x180025890  cmp     rax, 0FFFFh
0x180025896  jbe     short loc_1800258A2
0x180025898  mov     eax, 216h
0x18002589d  jmp     loc_180025A11
0x1800258a2  mov     rbx, r14
0x1800258a5  mov     esi, 8
0x1800258aa  shl     rbx, 4
0x1800258ae  lea     rdi, [rbx+2Eh]
0x1800258b2  add     rdi, r10
0x1800258b5  jz      loc_180025A0F
0x1800258bb  call    cs:__imp_GetProcessHeap
0x1800258c1  mov     r8, rdi; dwBytes
0x1800258c4  mov     edx, esi; dwFlags
0x1800258c6  mov     rcx, rax; hHeap
0x1800258c9  call    cs:__imp_HeapAlloc
0x1800258cf  mov     [rsp+68h+var_48], rax
0x1800258d4  test    rax, rax
0x1800258d7  jz      loc_180025A0F
0x1800258dd  mov     rdx, rbx
0x1800258e0  mov     [rsp+68h+var_40], rdi
0x1800258e5  lea     rcx, [rsp+68h+var_48]
0x1800258ea  call    CBufferGetNextOffset
0x1800258ef  xor     sil, sil
0x1800258f2  mov     r13, rax
0x1800258f5  add     bpl, r15b
0x1800258f8  mov     r15b, bpl
0x1800258fb  mov     [rsp+68h+arg_8], r15d
0x180025900  jz      short loc_180025969
0x180025902  xor     r15d, r15d
0x180025905  mov     rdi, r15
0x180025908  add     rdi, rdi
0x18002590b  cmp     sil, 2
0x18002590f  jnb     short loc_18002591F
0x180025911  movups  xmm0, xmmword ptr [r12+rdi*8]
0x180025916  movdqu  xmmword ptr [r13+rdi*8+0], xmm0
0x18002591d  jmp     short loc_180025959
0x18002591f  mov     edx, [r12+rdi*8+8]
0x180025924  lea     rcx, [rsp+68h+var_48]
0x180025929  call    CBufferGetNextOffset
0x18002592e  mov     r8d, edx; Size
0x180025931  mov     rcx, rax; void *
0x180025934  mov     rdx, [r12+rdi*8]; Src
0x180025938  mov     rbx, rax
0x18002593b  call    memcpy_0
0x180025940  mov     [r13+rdi*8+0], rbx
0x180025945  mov     eax, [r12+rdi*8+0Ch]
0x18002594a  mov     [r13+rdi*8+0Ch], eax
0x18002594f  mov     eax, [r12+rdi*8+8]
0x180025954  mov     [r13+rdi*8+8], eax
0x180025959  inc     sil
0x18002595c  inc     r15
0x18002595f  cmp     sil, bpl
0x180025962  jb      short loc_180025905
0x180025964  mov     r15d, [rsp+68h+arg_8]
0x180025969  mov     edx, 2Eh ; '.'
0x18002596e  lea     rcx, [rsp+68h+var_48]
0x180025973  call    CBufferGetNextOffset
0x180025978  mov     rsi, rax
0x18002597b  mov     [rax+10h], r13
0x18002597f  mov     rax, [rsp+68h+arg_0]
0x180025984  movups  xmm0, xmmword ptr [rax]
0x180025987  mov     al, [rsp+68h+arg_18]
0x18002598e  mov     [rsi+2Dh], al
0x180025991  mov     eax, [rsp+68h+arg_20]
0x180025998  mov     [rsi+28h], eax
0x18002599b  mov     [rsi+2Ch], r14b
0x18002599f  movdqu  xmmword ptr [rsi], xmm0
0x1800259a3  cmp     r15b, r14b
0x1800259a6  jnb     short loc_180025A00
0x1800259a8  movzx   ebp, bpl
0x1800259ac  mov     rdi, rbp
0x1800259af  lea     rcx, [rsp+68h+var_48]
0x1800259b4  add     rdi, rdi
0x1800259b7  mov     edx, [r12+rdi*8+8]
0x1800259bc  call    CBufferGetNextOffset
0x1800259c1  mov     r8d, edx; Size
0x1800259c4  mov     rcx, rax; void *
0x1800259c7  mov     rdx, [r12+rdi*8]; Src
0x1800259cb  mov     rbx, rax
0x1800259ce  call    memcpy_0
0x1800259d3  mov     rax, [rsi+10h]
0x1800259d7  inc     r15b
0x1800259da  inc     rbp
0x1800259dd  mov     [rax+rdi*8], rbx
0x1800259e1  mov     rcx, [rsi+10h]
0x1800259e5  mov     eax, [r12+rdi*8+0Ch]
0x1800259ea  mov     [rcx+rdi*8+0Ch], eax
0x1800259ee  mov     rcx, [rsi+10h]
0x1800259f2  mov     eax, [r12+rdi*8+8]
0x1800259f7  mov     [rcx+rdi*8+8], eax
0x1800259fb  cmp     r15b, r14b
0x1800259fe  jb      short loc_1800259AC
0x180025a00  mov     rax, [rsp+68h+arg_28]
0x180025a08  mov     [rax], rsi
0x180025a0b  xor     eax, eax
0x180025a0d  jmp     short loc_180025A11
0x180025a0f  mov     eax, esi
0x180025a11  mov     rbx, [rsp+68h+arg_10]
0x180025a19  add     rsp, 30h
0x180025a1d  pop     r15
0x180025a1f  pop     r14
0x180025a21  pop     r13
0x180025a23  pop     r12
0x180025a25  pop     rdi
0x180025a26  pop     rsi
0x180025a27  pop     rbp
0x180025a28  retn
```
