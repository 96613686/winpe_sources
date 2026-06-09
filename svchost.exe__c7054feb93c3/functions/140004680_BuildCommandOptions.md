# BuildCommandOptions

- ea: `0x140004680`
- end: `0x140004898`
- name: `BuildCommandOptions`
- size: `536`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400018d0`

## callees

- `0x140004680`
- `0x140006f58`
- `0x140008679`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400046cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400046cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000487d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000487d`

## pseudocode

```c
_QWORD *__fastcall BuildCommandOptions(_WORD *Src)
{
  __int64 v3; // rax
  __int64 v5; // rax
  unsigned int v6; // esi
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  _QWORD *v9; // r14
  _WORD *v10; // rbx
  __int16 v11; // ax
  __int16 i; // ax
  __int16 v13; // cx
  _WORD *v14; // rdx
  __int16 v15; // ax
  __int16 v16; // cx
  __int16 j; // ax
  HANDLE v18; // rcx

  if ( !Src )
    return 0;
  v3 = -1;
  while ( Src[++v3] != 0 )
    ;
  v5 = (unsigned int)(2 * v3 + 2);
  v6 = v5;
  v7 = HeapAlloc(g_hHeap, 8u, v5 + 160);
  v8 = v7;
  if ( v7 )
  {
    *v7 = v7 + 20;
    v9 = 0;
    memcpy_0(v7 + 20, Src, v6);
    v10 = (_WORD *)*v8;
    v8[1] = *v8;
    v11 = *v10;
    if ( *v10 )
    {
      do
      {
        if ( v11 == 32 )
          break;
        if ( v11 == 9 )
          break;
        v11 = v10[1];
        ++v10;
      }
      while ( v11 );
      if ( *v10 )
        *v10++ = 0;
    }
    SvchostCharLowerW((LPCWSTR)v8[1]);
    while ( 1 )
    {
      for ( i = *v10; i; ++v10 )
      {
        if ( i != 32 && i != 9 )
          break;
        i = v10[1];
      }
      v13 = *v10;
      if ( !*v10 )
      {
        if ( v8[3] )
        {
          *((_DWORD *)v8 + 4) = 1;
        }
        else
        {
          v18 = g_hHeap;
          *((_DWORD *)v8 + 4) = 0;
          HeapFree(v18, 0, v8);
          return 0;
        }
        return v8;
      }
      if ( ((v13 - 45) & 0xFFFD) != 0 )
      {
        v14 = v10;
        if ( v13 == 34 )
        {
          v15 = v10[1];
          ++v10;
          if ( v15 )
          {
            v14 = v10;
            do
            {
              if ( v15 == 34 )
                break;
              v15 = v10[1];
              ++v10;
            }
            while ( v15 );
            goto LABEL_37;
          }
        }
LABEL_33:
        for ( j = *v10; j; ++v10 )
        {
          if ( j == 32 )
            break;
          if ( j == 9 )
            break;
          j = v10[1];
        }
LABEL_37:
        if ( *v10 )
          *v10++ = 0;
        if ( v9 )
        {
          *v9 = v14;
          v9 = 0;
        }
      }
      else
      {
        v16 = v10[1];
        v14 = ++v10;
        if ( !v16 )
          goto LABEL_33;
        if ( ((v16 - 75) & 0xFFDF) != 0 )
        {
          if ( ((v16 - 83) & 0xFFDF) != 0 )
          {
            if ( ((v16 - 80) & 0xFFDF) == 0 )
              *((_DWORD *)v8 + 23) = 1;
          }
          else
          {
            v9 = v8 + 4;
          }
        }
        else
        {
          *((_DWORD *)v8 + 4) = 1;
          v9 = v8 + 3;
        }
        ++v10;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x140004680  push    rbx
0x140004682  sub     rsp, 20h
0x140004686  mov     rbx, rcx
0x140004689  test    rcx, rcx
0x14000468c  jnz     short loc_140004696
0x14000468e  xor     eax, eax
0x140004690  add     rsp, 20h
0x140004694  pop     rbx
0x140004695  retn
0x140004696  mov     [rsp+28h+arg_8], rsi
0x14000469b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400046a2  mov     [rsp+28h+arg_10], rdi
0x1400046a7  cmp     word ptr [rcx+rax*2+2], 0
0x1400046ad  lea     rax, [rax+1]
0x1400046b1  jnz     short loc_1400046A7
0x1400046b3  mov     rcx, cs:g_hHeap; hHeap
0x1400046ba  lea     eax, ds:2[rax*2]
0x1400046c1  lea     r8, [rax+0A0h]; dwBytes
0x1400046c8  mov     esi, eax
0x1400046ca  mov     edx, 8; dwFlags
0x1400046cf  call    cs:__imp_HeapAlloc
0x1400046d5  mov     rdi, rax
0x1400046d8  test    rax, rax
0x1400046db  jz      loc_140004885
0x1400046e1  lea     rcx, [rax+0A0h]; void *
0x1400046e8  mov     [rsp+28h+arg_0], rbp
0x1400046ed  mov     [rsp+28h+arg_18], r14
0x1400046f2  mov     r8d, esi; Size
0x1400046f5  mov     rdx, rbx; Src
0x1400046f8  mov     [rax], rcx
0x1400046fb  xor     r14d, r14d
0x1400046fe  call    memcpy_0
0x140004703  mov     rbx, [rdi]
0x140004706  mov     esi, 20h ; ' '
0x14000470b  mov     [rdi+8], rbx
0x14000470f  mov     ebp, 9
0x140004714  movzx   eax, word ptr [rbx]
0x140004717  test    ax, ax
0x14000471a  jz      short loc_140004742
0x14000471c  cmp     si, ax
0x14000471f  jz      short loc_140004733
0x140004721  cmp     bp, ax
0x140004724  jz      short loc_140004733
0x140004726  movzx   eax, word ptr [rbx+2]
0x14000472a  add     rbx, 2
0x14000472e  test    ax, ax
0x140004731  jnz     short loc_14000471C
0x140004733  cmp     [rbx], r14w
0x140004737  jz      short loc_140004742
0x140004739  xor     eax, eax
0x14000473b  mov     [rbx], ax
0x14000473e  add     rbx, 2
0x140004742  mov     rcx, [rdi+8]; lpSrcStr
0x140004746  call    SvchostCharLowerW
0x14000474b  mov     r10d, 0FFFDh
0x140004751  mov     r9d, 22h ; '"'
0x140004757  mov     r8d, 0FFDFh
0x14000475d  movzx   eax, word ptr [rbx]
0x140004760  test    ax, ax
0x140004763  jz      short loc_14000477C
0x140004765  cmp     si, ax
0x140004768  jz      short loc_14000476F
0x14000476a  cmp     bp, ax
0x14000476d  jnz     short loc_14000477C
0x14000476f  movzx   eax, word ptr [rbx+2]
0x140004773  add     rbx, 2
0x140004777  test    ax, ax
0x14000477a  jnz     short loc_140004765
0x14000477c  movzx   ecx, word ptr [rbx]
0x14000477f  test    cx, cx
0x140004782  jz      loc_140004850
0x140004788  lea     eax, [rcx-2Dh]
0x14000478b  test    r10w, ax
0x14000478f  jz      short loc_1400047BF
0x140004791  mov     rdx, rbx
0x140004794  cmp     r9w, cx
0x140004798  jnz     short loc_14000480E
0x14000479a  movzx   eax, word ptr [rbx+2]
0x14000479e  add     rbx, 2
0x1400047a2  test    ax, ax
0x1400047a5  jz      short loc_14000480E
0x1400047a7  mov     rdx, rbx
0x1400047aa  cmp     r9w, ax
0x1400047ae  jz      short loc_14000482D
0x1400047b0  movzx   eax, word ptr [rbx+2]
0x1400047b4  add     rbx, 2
0x1400047b8  test    ax, ax
0x1400047bb  jnz     short loc_1400047AA
0x1400047bd  jmp     short loc_14000482D
0x1400047bf  movzx   ecx, word ptr [rbx+2]
0x1400047c3  add     rbx, 2
0x1400047c7  mov     rdx, rbx
0x1400047ca  test    cx, cx
0x1400047cd  jz      short loc_14000480E
0x1400047cf  lea     eax, [rcx-4Bh]
0x1400047d2  test    r8w, ax
0x1400047d6  jz      short loc_1400047FA
0x1400047d8  lea     eax, [rcx-53h]
0x1400047db  test    r8w, ax
0x1400047df  jz      short loc_1400047F4
0x1400047e1  sub     cx, 50h ; 'P'
0x1400047e5  test    r8w, cx
0x1400047e9  jnz     short loc_140004805
0x1400047eb  mov     dword ptr [rdi+5Ch], 1
0x1400047f2  jmp     short loc_140004805
0x1400047f4  lea     r14, [rdi+20h]
0x1400047f8  jmp     short loc_140004805
0x1400047fa  mov     dword ptr [rdi+10h], 1
0x140004801  lea     r14, [rdi+18h]
0x140004805  add     rbx, 2
0x140004809  jmp     loc_14000475D
0x14000480e  movzx   eax, word ptr [rbx]
0x140004811  test    ax, ax
0x140004814  jz      short loc_14000482D
0x140004816  cmp     si, ax
0x140004819  jz      short loc_14000482D
0x14000481b  cmp     bp, ax
0x14000481e  jz      short loc_14000482D
0x140004820  movzx   eax, word ptr [rbx+2]
0x140004824  add     rbx, 2
0x140004828  test    ax, ax
0x14000482b  jnz     short loc_140004816
0x14000482d  cmp     word ptr [rbx], 0
0x140004831  jz      short loc_14000483C
0x140004833  xor     eax, eax
0x140004835  mov     [rbx], ax
0x140004838  add     rbx, 2
0x14000483c  test    r14, r14
0x14000483f  jz      loc_14000475D
0x140004845  mov     [r14], rdx
0x140004848  xor     r14d, r14d
0x14000484b  jmp     loc_14000475D
0x140004850  cmp     qword ptr [rdi+18h], 0
0x140004855  mov     r14, [rsp+28h+arg_18]
0x14000485a  mov     rbp, [rsp+28h+arg_0]
0x14000485f  jz      short loc_14000486A
0x140004861  mov     dword ptr [rdi+10h], 1
0x140004868  jmp     short loc_140004885
0x14000486a  mov     rcx, cs:g_hHeap; hHeap
0x140004871  mov     r8, rdi; lpMem
0x140004874  xor     edx, edx; dwFlags
0x140004876  mov     dword ptr [rdi+10h], 0
0x14000487d  call    cs:__imp_HeapFree
0x140004883  xor     edi, edi
0x140004885  mov     rsi, [rsp+28h+arg_8]
0x14000488a  mov     rax, rdi
0x14000488d  mov     rdi, [rsp+28h+arg_10]
0x140004892  add     rsp, 20h
0x140004896  pop     rbx
0x140004897  retn
```
