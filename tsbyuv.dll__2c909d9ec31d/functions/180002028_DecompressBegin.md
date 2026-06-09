# DecompressBegin

- ea: `0x180002028`
- end: `0x1800022c2`
- name: `DecompressBegin`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001cc0`

## callees

- `0x180002028`
- `0x1800022c8`
- `0x180002310`
- `0x18000263c`
- `0x1800026d4`
- `0x1800032fc`
- `0x1800033e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800020c0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180002137`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800021bd`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000222c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800020c0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180002137`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800021bd`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000222c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800020d2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002149`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800021cf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000223a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800020d2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002149`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800021cf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000223a`

## pseudocode

```c
__int64 __fastcall DecompressBegin(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  int v5; // eax
  __int64 v6; // rax
  _WORD *v7; // rbx
  HGLOBAL v8; // rax
  _WORD *v9; // rax
  _WORD *v10; // r12
  unsigned __int16 k; // r14
  __int16 v12; // ax
  HGLOBAL v13; // rax
  _WORD *v14; // rax
  _WORD *v15; // r12
  unsigned __int16 m; // r14
  __int16 v17; // ax
  HGLOBAL v18; // rax
  _WORD *v19; // rax
  _WORD *v20; // r12
  unsigned __int16 i; // r14
  __int16 v22; // ax
  HGLOBAL v23; // rax
  _WORD *v24; // rax
  _WORD *v25; // r12
  unsigned __int16 j; // r14
  __int16 v27; // ax

  result = DecompressQuery();
  if ( !(_DWORD)result )
  {
    if ( *(_DWORD *)(a2 + 16) != *(_DWORD *)(a1 + 4) )
    {
      if ( !*(_QWORD *)(a1 + 8) )
        goto LABEL_6;
      DecompressEnd(a1);
    }
    if ( *(_QWORD *)(a1 + 8) )
      return 0;
LABEL_6:
    v5 = *(_DWORD *)(a2 + 16);
    if ( v5 != 808596564 )
    {
      if ( v5 == 825308249 )
      {
        v7 = 0;
        if ( *(_DWORD *)(a1 + 16) )
        {
          v18 = GlobalAlloc(0x40u, 0x10000u);
          if ( v18 )
          {
            v19 = GlobalLock(v18);
            v7 = v19;
            if ( v19 )
            {
              v20 = v19;
              for ( i = 0; i < 0x8000u; ++i )
              {
                v22 = YUVToRGB565((i >> 7) & 0xF8, (char)(i >> 2) & 0xFFFFFFF8, (unsigned int)(char)(8 * i));
                *v20++ = v22;
              }
            }
          }
        }
        else
        {
          v23 = GlobalAlloc(0x40u, 0x10000u);
          if ( v23 )
          {
            v24 = GlobalLock(v23);
            v7 = v24;
            if ( v24 )
            {
              v25 = v24;
              for ( j = 0; j < 0x8000u; ++j )
              {
                v27 = YUVToRGB555((j >> 7) & 0xF8, (char)(j >> 2) & 0xFFFFFFF8, (unsigned int)(char)(8 * j));
                *v25++ = v27;
              }
            }
          }
        }
        goto LABEL_37;
      }
      if ( v5 == 842150995 )
      {
        v7 = 0;
        if ( *(_DWORD *)(a1 + 16) )
        {
          v8 = GlobalAlloc(0x40u, 0x10000u);
          if ( v8 )
          {
            v9 = GlobalLock(v8);
            v7 = v9;
            if ( v9 )
            {
              v10 = v9;
              for ( k = 0; k < 0x8000u; ++k )
              {
                v12 = YUVToRGB565((k >> 7) & 0xF8, ((k >> 2) & 0xF8u) - 128, 8 * (k & 0x1Fu) - 128);
                *v10++ = v12;
              }
            }
          }
        }
        else
        {
          v13 = GlobalAlloc(0x40u, 0x10000u);
          if ( v13 )
          {
            v14 = GlobalLock(v13);
            v7 = v14;
            if ( v14 )
            {
              v15 = v14;
              for ( m = 0; m < 0x8000u; ++m )
              {
                v17 = YUVToRGB555((m >> 7) & 0xF8, ((m >> 2) & 0xF8u) - 128, 8 * (m & 0x1Fu) - 128);
                *v15++ = v17;
              }
            }
          }
        }
        goto LABEL_37;
      }
      if ( v5 != 961893977 )
        return 4294967294LL;
    }
    if ( *(_DWORD *)(a1 + 16) )
      v6 = BuildYUV12ToRGB565(a1);
    else
      v6 = BuildYUV12ToRGB555(a1);
    v7 = (_WORD *)v6;
LABEL_37:
    *(_QWORD *)(a1 + 8) = v7;
    if ( !v7 )
      return 4294967293LL;
    *(_DWORD *)(a1 + 4) = *(_DWORD *)(a2 + 16);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002028  push    rbx
0x18000202a  push    rbp
0x18000202b  push    rdi
0x18000202c  push    r12
0x18000202e  push    r14
0x180002030  push    r15
0x180002032  sub     rsp, 28h
0x180002036  mov     r15, rdx
0x180002039  mov     rdi, rcx
0x18000203c  call    DecompressQuery
0x180002041  test    eax, eax
0x180002043  jnz     loc_1800022B4
0x180002049  mov     eax, [rdi+4]
0x18000204c  cmp     [r15+10h], eax
0x180002050  jz      short loc_180002061
0x180002052  cmp     qword ptr [rdi+8], 0
0x180002057  jz      short loc_18000206C
0x180002059  mov     rcx, rdi
0x18000205c  call    DecompressEnd
0x180002061  cmp     qword ptr [rdi+8], 0
0x180002066  jnz     loc_1800022B2
0x18000206c  mov     eax, [r15+10h]
0x180002070  cmp     eax, 30323454h
0x180002075  jz      short loc_18000209A
0x180002077  cmp     eax, 31313459h
0x18000207c  jz      loc_1800021AE
0x180002082  cmp     eax, 32323453h
0x180002087  jz      short loc_1800020B1
0x180002089  cmp     eax, 39555659h
0x18000208e  jz      short loc_18000209A
0x180002090  mov     eax, 0FFFFFFFEh
0x180002095  jmp     loc_1800022B4
0x18000209a  cmp     dword ptr [rdi+10h], 0
0x18000209e  mov     rcx, rdi
0x1800020a1  jz      loc_180002293
0x1800020a7  call    BuildYUV12ToRGB565
0x1800020ac  jmp     loc_180002298
0x1800020b1  xor     ebx, ebx
0x1800020b3  mov     edx, 10000h; dwBytes
0x1800020b8  lea     ecx, [rbx+40h]; uFlags
0x1800020bb  cmp     [rdi+10h], ebx
0x1800020be  jz      short loc_180002137
0x1800020c0  call    cs:__imp_GlobalAlloc
0x1800020c6  test    rax, rax
0x1800020c9  jz      loc_18000229B
0x1800020cf  mov     rcx, rax; hMem
0x1800020d2  call    cs:__imp_GlobalLock
0x1800020d8  mov     rbx, rax
0x1800020db  test    rax, rax
0x1800020de  jz      loc_18000229B
0x1800020e4  mov     r12, rax
0x1800020e7  xor     r14d, r14d
0x1800020ea  mov     ebp, 8000h
0x1800020ef  movzx   ecx, r14w
0x1800020f3  mov     r8d, ecx
0x1800020f6  mov     edx, ecx
0x1800020f8  shr     edx, 2
0x1800020fb  and     r8d, 1Fh
0x1800020ff  and     edx, 0F8h
0x180002105  shr     ecx, 7
0x180002108  add     edx, 0FFFFFF80h
0x18000210b  and     ecx, 0F8h
0x180002111  lea     r8d, ds:0FFFFFFFFFFFFFF80h[r8*8]
0x180002119  call    YUVToRGB565
0x18000211e  inc     r14w
0x180002122  mov     [r12], ax
0x180002127  lea     r12, [r12+2]
0x18000212c  cmp     r14w, bp
0x180002130  jb      short loc_1800020EF
0x180002132  jmp     loc_18000229B
0x180002137  call    cs:__imp_GlobalAlloc
0x18000213d  test    rax, rax
0x180002140  jz      loc_18000229B
0x180002146  mov     rcx, rax; hMem
0x180002149  call    cs:__imp_GlobalLock
0x18000214f  mov     rbx, rax
0x180002152  test    rax, rax
0x180002155  jz      loc_18000229B
0x18000215b  mov     r12, rax
0x18000215e  xor     r14d, r14d
0x180002161  mov     ebp, 8000h
0x180002166  movzx   ecx, r14w
0x18000216a  mov     r8d, ecx
0x18000216d  mov     edx, ecx
0x18000216f  shr     edx, 2
0x180002172  and     r8d, 1Fh
0x180002176  and     edx, 0F8h
0x18000217c  shr     ecx, 7
0x18000217f  add     edx, 0FFFFFF80h
0x180002182  and     ecx, 0F8h
0x180002188  lea     r8d, ds:0FFFFFFFFFFFFFF80h[r8*8]
0x180002190  call    YUVToRGB555
0x180002195  inc     r14w
0x180002199  mov     [r12], ax
0x18000219e  lea     r12, [r12+2]
0x1800021a3  cmp     r14w, bp
0x1800021a7  jb      short loc_180002166
0x1800021a9  jmp     loc_18000229B
0x1800021ae  xor     ebx, ebx
0x1800021b0  mov     edx, 10000h; dwBytes
0x1800021b5  lea     ecx, [rbx+40h]; uFlags
0x1800021b8  cmp     [rdi+10h], ebx
0x1800021bb  jz      short loc_18000222C
0x1800021bd  call    cs:__imp_GlobalAlloc
0x1800021c3  test    rax, rax
0x1800021c6  jz      loc_18000229B
0x1800021cc  mov     rcx, rax; hMem
0x1800021cf  call    cs:__imp_GlobalLock
0x1800021d5  mov     rbx, rax
0x1800021d8  test    rax, rax
0x1800021db  jz      loc_18000229B
0x1800021e1  mov     r12, rax
0x1800021e4  xor     r14d, r14d
0x1800021e7  mov     ebp, 8000h
0x1800021ec  mov     al, r14b
0x1800021ef  movzx   ecx, r14w
0x1800021f3  shl     al, 3
0x1800021f6  movsx   r8d, al
0x1800021fa  movzx   eax, r14w
0x1800021fe  shr     ax, 2
0x180002202  movsx   edx, al
0x180002205  shr     ecx, 7
0x180002208  and     edx, 0FFFFFFF8h
0x18000220b  and     ecx, 0F8h
0x180002211  call    YUVToRGB565
0x180002216  inc     r14w
0x18000221a  mov     [r12], ax
0x18000221f  lea     r12, [r12+2]
0x180002224  cmp     r14w, bp
0x180002228  jb      short loc_1800021EC
0x18000222a  jmp     short loc_18000229B
0x18000222c  call    cs:__imp_GlobalAlloc
0x180002232  test    rax, rax
0x180002235  jz      short loc_18000229B
0x180002237  mov     rcx, rax; hMem
0x18000223a  call    cs:__imp_GlobalLock
0x180002240  mov     rbx, rax
0x180002243  test    rax, rax
0x180002246  jz      short loc_18000229B
0x180002248  mov     r12, rax
0x18000224b  xor     r14d, r14d
0x18000224e  mov     ebp, 8000h
0x180002253  mov     al, r14b
0x180002256  movzx   ecx, r14w
0x18000225a  shl     al, 3
0x18000225d  movsx   r8d, al
0x180002261  movzx   eax, r14w
0x180002265  shr     ax, 2
0x180002269  movsx   edx, al
0x18000226c  shr     ecx, 7
0x18000226f  and     edx, 0FFFFFFF8h
0x180002272  and     ecx, 0F8h
0x180002278  call    YUVToRGB555
0x18000227d  inc     r14w
0x180002281  mov     [r12], ax
0x180002286  lea     r12, [r12+2]
0x18000228b  cmp     r14w, bp
0x18000228f  jb      short loc_180002253
0x180002291  jmp     short loc_18000229B
0x180002293  call    BuildYUV12ToRGB555
0x180002298  mov     rbx, rax
0x18000229b  mov     [rdi+8], rbx
0x18000229f  test    rbx, rbx
0x1800022a2  jnz     short loc_1800022AB
0x1800022a4  mov     eax, 0FFFFFFFDh
0x1800022a9  jmp     short loc_1800022B4
0x1800022ab  mov     eax, [r15+10h]
0x1800022af  mov     [rdi+4], eax
0x1800022b2  xor     eax, eax
0x1800022b4  add     rsp, 28h
0x1800022b8  pop     r15
0x1800022ba  pop     r14
0x1800022bc  pop     r12
0x1800022be  pop     rdi
0x1800022bf  pop     rbp
0x1800022c0  pop     rbx
0x1800022c1  retn
```
