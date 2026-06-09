# BuildCommandOptions

- ea: `0x140004a30`
- end: `0x140004c60`
- name: `BuildCommandOptions`
- size: `560`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001970`

## callees

- `0x140004a30`
- `0x140007488`
- `0x140008cc9`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140004a80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140004a80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004c34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004c34`

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
0x140004a30  push    rbx
0x140004a32  sub     rsp, 20h
0x140004a36  mov     rbx, rcx
0x140004a39  test    rcx, rcx
0x140004a3c  jnz     short loc_140004A47
0x140004a3e  xor     eax, eax
0x140004a40  add     rsp, 20h
0x140004a44  pop     rbx
0x140004a45  retn
0x140004a47  mov     [rsp+28h+arg_8], rsi
0x140004a4c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140004a53  mov     [rsp+28h+arg_10], rdi
0x140004a58  cmp     word ptr [rcx+rax*2+2], 0
0x140004a5e  lea     rax, [rax+1]
0x140004a62  jnz     short loc_140004A58
0x140004a64  mov     rcx, cs:g_hHeap; hHeap
0x140004a6b  lea     eax, ds:2[rax*2]
0x140004a72  lea     r8, [rax+0A0h]; dwBytes
0x140004a79  mov     esi, eax
0x140004a7b  mov     edx, 8; dwFlags
0x140004a80  call    cs:__imp_HeapAlloc
0x140004a87  nop     dword ptr [rax+rax+00h]
0x140004a8c  mov     rdi, rax
0x140004a8f  test    rax, rax
0x140004a92  jz      loc_140004C42
0x140004a98  lea     rcx, [rax+0A0h]; void *
0x140004a9f  mov     [rsp+28h+arg_0], rbp
0x140004aa4  mov     [rsp+28h+arg_18], r14
0x140004aa9  mov     r8d, esi; Size
0x140004aac  mov     rdx, rbx; Src
0x140004aaf  mov     [rax], rcx
0x140004ab2  xor     r14d, r14d
0x140004ab5  call    memcpy_0
0x140004aba  mov     rbx, [rdi]
0x140004abd  mov     esi, 20h ; ' '
0x140004ac2  mov     [rdi+8], rbx
0x140004ac6  mov     ebp, 9
0x140004acb  movzx   eax, word ptr [rbx]
0x140004ace  test    ax, ax
0x140004ad1  jz      short loc_140004AF9
0x140004ad3  cmp     si, ax
0x140004ad6  jz      short loc_140004AEA
0x140004ad8  cmp     bp, ax
0x140004adb  jz      short loc_140004AEA
0x140004add  movzx   eax, word ptr [rbx+2]
0x140004ae1  add     rbx, 2
0x140004ae5  test    ax, ax
0x140004ae8  jnz     short loc_140004AD3
0x140004aea  cmp     [rbx], r14w
0x140004aee  jz      short loc_140004AF9
0x140004af0  xor     eax, eax
0x140004af2  mov     [rbx], ax
0x140004af5  add     rbx, 2
0x140004af9  mov     rcx, [rdi+8]; lpSrcStr
0x140004afd  call    SvchostCharLowerW
0x140004b02  mov     r10d, 0FFFDh
0x140004b08  mov     r9d, 22h ; '"'
0x140004b0e  mov     r8d, 0FFDFh
0x140004b14  movzx   eax, word ptr [rbx]
0x140004b17  test    ax, ax
0x140004b1a  jz      short loc_140004B33
0x140004b1c  cmp     si, ax
0x140004b1f  jz      short loc_140004B26
0x140004b21  cmp     bp, ax
0x140004b24  jnz     short loc_140004B33
0x140004b26  movzx   eax, word ptr [rbx+2]
0x140004b2a  add     rbx, 2
0x140004b2e  test    ax, ax
0x140004b31  jnz     short loc_140004B1C
0x140004b33  movzx   ecx, word ptr [rbx]
0x140004b36  test    cx, cx
0x140004b39  jz      loc_140004C07
0x140004b3f  lea     eax, [rcx-2Dh]
0x140004b42  test    r10w, ax
0x140004b46  jz      short loc_140004B76
0x140004b48  mov     rdx, rbx
0x140004b4b  cmp     r9w, cx
0x140004b4f  jnz     short loc_140004BC5
0x140004b51  movzx   eax, word ptr [rbx+2]
0x140004b55  add     rbx, 2
0x140004b59  test    ax, ax
0x140004b5c  jz      short loc_140004BC5
0x140004b5e  mov     rdx, rbx
0x140004b61  cmp     r9w, ax
0x140004b65  jz      short loc_140004BE4
0x140004b67  movzx   eax, word ptr [rbx+2]
0x140004b6b  add     rbx, 2
0x140004b6f  test    ax, ax
0x140004b72  jnz     short loc_140004B61
0x140004b74  jmp     short loc_140004BE4
0x140004b76  movzx   ecx, word ptr [rbx+2]
0x140004b7a  add     rbx, 2
0x140004b7e  mov     rdx, rbx
0x140004b81  test    cx, cx
0x140004b84  jz      short loc_140004BC5
0x140004b86  lea     eax, [rcx-4Bh]
0x140004b89  test    r8w, ax
0x140004b8d  jz      short loc_140004BB1
0x140004b8f  lea     eax, [rcx-53h]
0x140004b92  test    r8w, ax
0x140004b96  jz      short loc_140004BAB
0x140004b98  sub     cx, 50h ; 'P'
0x140004b9c  test    r8w, cx
0x140004ba0  jnz     short loc_140004BBC
0x140004ba2  mov     dword ptr [rdi+5Ch], 1
0x140004ba9  jmp     short loc_140004BBC
0x140004bab  lea     r14, [rdi+20h]
0x140004baf  jmp     short loc_140004BBC
0x140004bb1  mov     dword ptr [rdi+10h], 1
0x140004bb8  lea     r14, [rdi+18h]
0x140004bbc  add     rbx, 2
0x140004bc0  jmp     loc_140004B14
0x140004bc5  movzx   eax, word ptr [rbx]
0x140004bc8  test    ax, ax
0x140004bcb  jz      short loc_140004BE4
0x140004bcd  cmp     si, ax
0x140004bd0  jz      short loc_140004BE4
0x140004bd2  cmp     bp, ax
0x140004bd5  jz      short loc_140004BE4
0x140004bd7  movzx   eax, word ptr [rbx+2]
0x140004bdb  add     rbx, 2
0x140004bdf  test    ax, ax
0x140004be2  jnz     short loc_140004BCD
0x140004be4  cmp     word ptr [rbx], 0
0x140004be8  jz      short loc_140004BF3
0x140004bea  xor     eax, eax
0x140004bec  mov     [rbx], ax
0x140004bef  add     rbx, 2
0x140004bf3  test    r14, r14
0x140004bf6  jz      loc_140004B14
0x140004bfc  mov     [r14], rdx
0x140004bff  xor     r14d, r14d
0x140004c02  jmp     loc_140004B14
0x140004c07  cmp     qword ptr [rdi+18h], 0
0x140004c0c  mov     r14, [rsp+28h+arg_18]
0x140004c11  mov     rbp, [rsp+28h+arg_0]
0x140004c16  jz      short loc_140004C21
0x140004c18  mov     dword ptr [rdi+10h], 1
0x140004c1f  jmp     short loc_140004C42
0x140004c21  mov     rcx, cs:g_hHeap; hHeap
0x140004c28  mov     r8, rdi; lpMem
0x140004c2b  xor     edx, edx; dwFlags
0x140004c2d  mov     dword ptr [rdi+10h], 0
0x140004c34  call    cs:__imp_HeapFree
0x140004c3b  nop     dword ptr [rax+rax+00h]
0x140004c40  xor     edi, edi
0x140004c42  mov     rsi, [rsp+28h+arg_8]
0x140004c47  mov     rax, rdi
0x140004c4a  mov     rdi, [rsp+28h+arg_10]
0x140004c4f  add     rsp, 20h
0x140004c53  pop     rbx
0x140004c54  retn
```
