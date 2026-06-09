# CodePageCharacterSource::Read(void *,ulong,ulong *)

- ea: `0x10041b0a0`
- end: `0x10041b378`
- name: `?Read@CodePageCharacterSource@@UEAAJPEAXKPEAK@Z`
- size: `728`
- prototype: `__int64 __fastcall(CodePageCharacterSource *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x100401780`
- `0x10041b0a0`
- `0x100425d50`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x10041b142`
- `KERNEL32!HeapAlloc` at `0x10041b269`
- `KERNEL32!HeapAlloc` at `0x10041b142`
- `KERNEL32!HeapAlloc` at `0x10041b269`
- `KERNEL32!HeapFree` at `0x10041b1bd`
- `KERNEL32!HeapFree` at `0x10041b1bd`

## pseudocode

```c
__int64 __fastcall CodePageCharacterSource::Read(
        CodePageCharacterSource *this,
        void *a2,
        unsigned int a3,
        unsigned int *a4)
{
  unsigned int v4; // eax
  __int64 v9; // r10
  signed __int64 v10; // rcx
  unsigned int v11; // esi
  struct IMalloc *v12; // rcx
  _BYTE *v13; // rax
  _BYTE *v14; // rdi
  _BYTE *v15; // r8
  struct IMalloc *v16; // rcx
  int v17; // r9d
  char *v18; // r11
  __int64 v19; // rcx
  __int64 v20; // rax
  struct IMalloc *v21; // rcx
  char *v22; // rax
  __int64 result; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // [rsp+30h] [rbp-28h] BYREF
  int v29[9]; // [rsp+34h] [rbp-24h] BYREF
  unsigned int v30; // [rsp+60h] [rbp+8h] BYREF

  v4 = *((_DWORD *)this + 56);
  if ( v4 >= 0x40 )
    goto LABEL_27;
  v9 = *((_QWORD *)this + 26);
  if ( v9 )
  {
    if ( *((_BYTE *)this + 25) )
    {
      v10 = *((unsigned int *)this + 50);
      if ( v4 + *((_QWORD *)this + 27) - v9 >= v10 )
      {
        v11 = 2 * v10;
        v12 = (struct IMalloc *)*((_QWORD *)this + 1);
        if ( v12 || (v12 = g_pMalloc) != 0 )
          v13 = (_BYTE *)((__int64 (__fastcall *)(struct IMalloc *, _QWORD))v12->lpVtbl->Alloc)(v12, v11);
        else
          v13 = HeapAlloc(g_hHeap, 0, v11);
        v14 = v13;
        if ( v13 )
        {
          memmove(
            v13,
            *((const void **)this + 26),
            *((_QWORD *)this + 27) + *((unsigned int *)this + 56) - *((_QWORD *)this + 26));
          v15 = (_BYTE *)*((_QWORD *)this + 26);
          v16 = (struct IMalloc *)*((_QWORD *)this + 1);
          *((_QWORD *)this + 27) += v14 - v15;
          if ( v15 )
          {
            if ( v16 || (v16 = g_pMalloc) != 0 )
              ((void (__fastcall *)(struct IMalloc *, _BYTE *))v16->lpVtbl->Free)(v16, v15);
            else
              HeapFree(g_hHeap, 0, v15);
          }
          v17 = *((_DWORD *)this + 54);
          LODWORD(v9) = (_DWORD)v14;
          v18 = (char *)*((_QWORD *)this + 27);
          *((_QWORD *)this + 26) = v14;
          *((_DWORD *)this + 50) = v11;
          goto LABEL_24;
        }
LABEL_30:
        MXRRaiseException(-2147024882);
        JUMPOUT(0x10041B377LL);
      }
    }
    else
    {
      memmove(*((void **)this + 26), *((const void **)this + 27), v4);
      v19 = *((_QWORD *)this + 26);
      LODWORD(v9) = v19;
      v20 = *((_QWORD *)this + 27) - v19;
      *((_QWORD *)this + 27) = v19;
      *((_QWORD *)this + 29) += v20;
    }
    v17 = *((_DWORD *)this + 54);
    v18 = (char *)*((_QWORD *)this + 27);
  }
  else
  {
    *((_DWORD *)this + 50) = 2048;
    v21 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v21 || (v21 = g_pMalloc) != 0 )
      v22 = (char *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v21->lpVtbl->Alloc)(v21, 2048);
    else
      v22 = (char *)HeapAlloc(g_hHeap, 0, 0x800u);
    v17 = (int)v22;
    if ( !v22 )
      goto LABEL_30;
    *((_QWORD *)this + 26) = v22;
    LODWORD(v9) = (_DWORD)v22;
    *((_QWORD *)this + 27) = v22;
    v18 = v22;
    *((_QWORD *)this + 29) = 0;
  }
LABEL_24:
  result = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, int *))(**((_QWORD **)this + 24) + 56LL))(
             *((_QWORD *)this + 24),
             &v18[*((unsigned int *)this + 56)],
             (unsigned int)(v9 + *((_DWORD *)this + 50) - *((_DWORD *)this + 56) - v17),
             v29);
  if ( (int)result < 0 )
  {
    _mm_lfence();
    return result;
  }
  *((_DWORD *)this + 56) += v29[0];
  v4 = *((_DWORD *)this + 56);
LABEL_27:
  v24 = *((_QWORD *)this + 27);
  v30 = v4;
  v25 = *(_QWORD *)this;
  v28 = a3 >> 1;
  result = (*(__int64 (__fastcall **)(CodePageCharacterSource *, __int64, unsigned int *, void *, unsigned int *))(v25 + 208))(
             this,
             v24,
             &v30,
             a2,
             &v28);
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    v26 = *((_QWORD *)this + 27);
    v27 = v30;
    *((_DWORD *)this + 56) -= v30;
    *((_QWORD *)this + 30) = v26;
    *((_QWORD *)this + 27) = v26 + v27;
    *a4 = 2 * v28;
    return (unsigned int)result;
  }
  return result;
}

```

## disassembly

```asm
0x10041b0a0  mov     [rsp+arg_8], rbx
0x10041b0a5  mov     [rsp+arg_10], rbp
0x10041b0aa  mov     [rsp+arg_18], rsi
0x10041b0af  push    rdi
0x10041b0b0  push    r14
0x10041b0b2  push    r15
0x10041b0b4  sub     rsp, 40h
0x10041b0b8  mov     eax, [rcx+0E0h]
0x10041b0be  mov     r14, r9
0x10041b0c1  mov     ebp, r8d
0x10041b0c4  mov     r15, rdx
0x10041b0c7  mov     rbx, rcx
0x10041b0ca  cmp     eax, 40h ; '@'
0x10041b0cd  jnb     loc_10041B2E5
0x10041b0d3  mov     r10, [rcx+0D0h]
0x10041b0da  test    r10, r10
0x10041b0dd  jz      loc_10041B227
0x10041b0e3  cmp     byte ptr [rcx+19h], 0
0x10041b0e7  mov     r8d, eax; Size
0x10041b0ea  jz      loc_10041B1E6
0x10041b0f0  mov     rax, [rbx+0D8h]
0x10041b0f7  mov     ecx, [rcx+0C8h]
0x10041b0fd  sub     rax, r10
0x10041b100  add     rax, r8
0x10041b103  cmp     rax, rcx
0x10041b106  jl      loc_10041B217
0x10041b10c  lea     esi, [rcx+rcx]
0x10041b10f  mov     rcx, [rbx+8]
0x10041b113  mov     r8d, esi; dwBytes
0x10041b116  test    rcx, rcx
0x10041b119  jz      short loc_10041B12D
0x10041b11b  mov     rax, [rcx]
0x10041b11e  mov     rdx, r8
0x10041b121  mov     rax, [rax+18h]
0x10041b125  call    cs:__guard_dispatch_icall_fptr
0x10041b12b  jmp     short loc_10041B148
0x10041b12d  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041b134  test    rcx, rcx
0x10041b137  jnz     short loc_10041B11B
0x10041b139  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041b140  xor     edx, edx; dwFlags
0x10041b142  call    cs:__imp_HeapAlloc
0x10041b148  mov     rdi, rax
0x10041b14b  test    rax, rax
0x10041b14e  jz      loc_10041B36D
0x10041b154  mov     rdx, [rbx+0D0h]; Src
0x10041b15b  mov     rcx, rax; void *
0x10041b15e  mov     r8d, [rbx+0E0h]
0x10041b165  sub     r8, rdx
0x10041b168  add     r8, [rbx+0D8h]; Size
0x10041b16f  call    memmove
0x10041b174  mov     r8, [rbx+0D0h]; lpMem
0x10041b17b  mov     rax, rdi
0x10041b17e  mov     rcx, [rbx+8]
0x10041b182  sub     rax, r8
0x10041b185  add     [rbx+0D8h], rax
0x10041b18c  test    r8, r8
0x10041b18f  jz      short loc_10041B1C3
0x10041b191  test    rcx, rcx
0x10041b194  jnz     short loc_10041B1A2
0x10041b196  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041b19d  test    rcx, rcx
0x10041b1a0  jz      short loc_10041B1B4
0x10041b1a2  mov     rax, [rcx]
0x10041b1a5  mov     rdx, r8
0x10041b1a8  mov     rax, [rax+28h]
0x10041b1ac  call    cs:__guard_dispatch_icall_fptr
0x10041b1b2  jmp     short loc_10041B1C3
0x10041b1b4  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041b1bb  xor     edx, edx; dwFlags
0x10041b1bd  call    cs:__imp_HeapFree
0x10041b1c3  mov     r9d, [rbx+0D8h]
0x10041b1ca  mov     r10d, edi
0x10041b1cd  mov     r11, [rbx+0D8h]
0x10041b1d4  mov     [rbx+0D0h], rdi
0x10041b1db  mov     [rbx+0C8h], esi
0x10041b1e1  jmp     loc_10041B29A
0x10041b1e6  mov     rdx, [rcx+0D8h]; Src
0x10041b1ed  mov     rcx, r10; void *
0x10041b1f0  call    memmove
0x10041b1f5  mov     rcx, [rbx+0D0h]
0x10041b1fc  mov     rax, [rbx+0D8h]
0x10041b203  mov     r10d, ecx
0x10041b206  sub     rax, rcx
0x10041b209  mov     [rbx+0D8h], rcx
0x10041b210  add     [rbx+0E8h], rax
0x10041b217  mov     r9d, [rbx+0D8h]
0x10041b21e  mov     r11, [rbx+0D8h]
0x10041b225  jmp     short loc_10041B29A
0x10041b227  mov     dword ptr [rcx+0C8h], 800h
0x10041b231  mov     rcx, [rcx+8]
0x10041b235  test    rcx, rcx
0x10041b238  jz      short loc_10041B24E
0x10041b23a  mov     rax, [rcx]
0x10041b23d  mov     edx, 800h
0x10041b242  mov     rax, [rax+18h]
0x10041b246  call    cs:__guard_dispatch_icall_fptr
0x10041b24c  jmp     short loc_10041B26F
0x10041b24e  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041b255  test    rcx, rcx
0x10041b258  jnz     short loc_10041B23A
0x10041b25a  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041b261  xor     edx, edx; dwFlags
0x10041b263  mov     r8d, 800h; dwBytes
0x10041b269  call    cs:__imp_HeapAlloc
0x10041b26f  mov     r9, rax
0x10041b272  test    rax, rax
0x10041b275  jz      loc_10041B36D
0x10041b27b  mov     [rbx+0D0h], rax
0x10041b282  mov     r10d, r9d
0x10041b285  mov     [rbx+0D8h], rax
0x10041b28c  mov     r11, rax
0x10041b28f  mov     qword ptr [rbx+0E8h], 0
0x10041b29a  mov     edx, [rbx+0E0h]
0x10041b2a0  mov     rcx, [rbx+0C0h]
0x10041b2a7  mov     r8d, [rbx+0C8h]
0x10041b2ae  sub     r8d, edx
0x10041b2b1  add     rdx, r11
0x10041b2b4  sub     r8d, r9d
0x10041b2b7  lea     r9, [rsp+58h+var_24]
0x10041b2bc  mov     rax, [rcx]
0x10041b2bf  add     r8d, r10d
0x10041b2c2  mov     rax, [rax+38h]
0x10041b2c6  call    cs:__guard_dispatch_icall_fptr
0x10041b2cc  test    eax, eax
0x10041b2ce  jns     short loc_10041B2D5
0x10041b2d0  lfence
0x10041b2d3  jmp     short loc_10041B354
0x10041b2d5  mov     eax, [rsp+58h+var_24]
0x10041b2d9  add     [rbx+0E0h], eax
0x10041b2df  mov     eax, [rbx+0E0h]
0x10041b2e5  mov     rdx, [rbx+0D8h]
0x10041b2ec  lea     rcx, [rsp+58h+var_28]
0x10041b2f1  mov     [rsp+58h+arg_0], eax
0x10041b2f5  lea     r8, [rsp+58h+arg_0]
0x10041b2fa  mov     rax, [rbx]
0x10041b2fd  mov     r9, r15
0x10041b300  shr     ebp, 1
0x10041b302  mov     [rsp+58h+var_38], rcx
0x10041b307  mov     rcx, rbx
0x10041b30a  mov     [rsp+58h+var_28], ebp
0x10041b30e  mov     rax, [rax+0D0h]
0x10041b315  call    cs:__guard_dispatch_icall_fptr
0x10041b31b  mov     r8d, eax
0x10041b31e  lfence
0x10041b321  test    eax, eax
0x10041b323  js      short loc_10041B354
0x10041b325  mov     rcx, [rbx+0D8h]
0x10041b32c  mov     edx, [rsp+58h+arg_0]
0x10041b330  sub     [rbx+0E0h], edx
0x10041b336  mov     [rbx+0F0h], rcx
0x10041b33d  lea     rax, [rcx+rdx]
0x10041b341  mov     [rbx+0D8h], rax
0x10041b348  mov     eax, [rsp+58h+var_28]
0x10041b34c  add     eax, eax
0x10041b34e  mov     [r14], eax
0x10041b351  mov     eax, r8d
0x10041b354  mov     rbx, [rsp+58h+arg_8]
0x10041b359  mov     rbp, [rsp+58h+arg_10]
0x10041b35e  mov     rsi, [rsp+58h+arg_18]
0x10041b363  add     rsp, 40h
0x10041b367  pop     r15
0x10041b369  pop     r14
0x10041b36b  pop     rdi
0x10041b36c  retn
0x10041b36d  mov     ecx, 8007000Eh; int
0x10041b372  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
