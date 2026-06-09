# USBD_ValidateExtendedPropertyDescriptor

- ea: `0x140013b88`
- end: `0x140013ca4`
- name: `USBD_ValidateExtendedPropertyDescriptor`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400242a4`

## callees

- `0x140013b88`

## pseudocode

```c
__int64 __fastcall USBD_ValidateExtendedPropertyDescriptor(unsigned int *a1, unsigned int a2)
{
  __int64 v2; // r8
  int v3; // eax
  __int64 result; // rax
  int v5; // r9d
  unsigned int *v6; // rdx
  unsigned __int64 v7; // r10
  int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // rcx
  unsigned int v11; // r11d
  int v12; // r11d

  if ( a2 < 0xA )
    return 3221225485LL;
  if ( !a1 )
    return 3221225485LL;
  v2 = *a1;
  if ( (unsigned int)v2 > a2 || (unsigned int)(v2 - 10) > 0xFF6 || *((_WORD *)a1 + 3) != 5 )
    return 3221225485LL;
  v3 = *((unsigned __int16 *)a1 + 4);
  if ( !(_WORD)v3 )
    return 0;
  v5 = 0;
  v6 = (unsigned int *)((char *)a1 + 10);
  v7 = (unsigned __int64)a1 + v2;
  v8 = *((unsigned __int16 *)a1 + 4);
  while ( (unsigned __int64)v6 < v7 )
  {
    if ( (unsigned __int64)v6 + 14 > v7 )
      return 3221225485LL;
    v9 = *v6;
    if ( (unsigned int)v9 > 0x7FFFFFFF )
      return 3221225485LL;
    if ( (__int64)(v7 - (_QWORD)v6) < (int)v9 )
      return 3221225485LL;
    if ( (unsigned int)v9 < 0xE )
      return 3221225485LL;
    if ( v6[1] - 1 > 6 )
      return 3221225485LL;
    v10 = *((unsigned __int16 *)v6 + 4);
    if ( (int)v10 + 14 > (unsigned int)v9 )
      return 3221225485LL;
    if ( !*((_WORD *)v6 + 4) )
      return 3221225485LL;
    if ( (v10 & 1) != 0 )
      return 3221225485LL;
    if ( !*((_WORD *)v6 + 5) )
      return 3221225485LL;
    if ( *((_WORD *)v6 + ((unsigned __int64)*((unsigned __int16 *)v6 + 4) >> 1) + 4) )
      return 3221225485LL;
    v11 = *(unsigned int *)((char *)v6 + v10 + 10);
    if ( ~(_DWORD)v10 < v11 )
      return 3221225485LL;
    v12 = v10 + v11;
    if ( (unsigned int)~v12 < 0xE || v12 + 14 > (unsigned int)v9 )
      return 3221225485LL;
    if ( ++v5 == v3 )
      return 0;
    v6 = (unsigned int *)((char *)v6 + v9);
  }
  result = 0;
  if ( v5 != v8 )
    return 3221225485LL;
  return result;
}

```

## disassembly

```asm
0x140013b88  mov     [rsp+arg_0], rbx
0x140013b8d  mov     [rsp+arg_8], rdi
0x140013b92  cmp     edx, 0Ah
0x140013b95  jb      loc_140013C93
0x140013b9b  xor     edi, edi
0x140013b9d  test    rcx, rcx
0x140013ba0  jz      loc_140013C93
0x140013ba6  mov     r8d, [rcx]
0x140013ba9  cmp     r8d, edx
0x140013bac  ja      loc_140013C93
0x140013bb2  lea     eax, [r8-0Ah]
0x140013bb6  cmp     eax, 0FF6h
0x140013bbb  ja      loc_140013C93
0x140013bc1  cmp     word ptr [rcx+6], 5
0x140013bc6  jnz     loc_140013C93
0x140013bcc  movzx   eax, word ptr [rcx+8]
0x140013bd0  test    ax, ax
0x140013bd3  jnz     short loc_140013BDC
0x140013bd5  mov     eax, edi
0x140013bd7  jmp     loc_140013C98
0x140013bdc  mov     r9d, edi
0x140013bdf  lea     rdx, [rcx+0Ah]
0x140013be3  lea     r10, [rcx+r8]
0x140013be7  mov     ebx, eax
0x140013be9  cmp     rdx, r10
0x140013bec  jnb     loc_140013C8C
0x140013bf2  lea     rax, [rdx+0Eh]
0x140013bf6  cmp     rax, r10
0x140013bf9  ja      loc_140013C93
0x140013bff  mov     r8d, [rdx]
0x140013c02  cmp     r8d, 7FFFFFFFh
0x140013c09  ja      loc_140013C93
0x140013c0f  mov     rcx, r10
0x140013c12  movsxd  rax, r8d
0x140013c15  sub     rcx, rdx
0x140013c18  cmp     rcx, rax
0x140013c1b  jl      short loc_140013C93
0x140013c1d  cmp     r8d, 0Eh
0x140013c21  jb      short loc_140013C93
0x140013c23  mov     eax, [rdx+4]
0x140013c26  dec     eax
0x140013c28  cmp     eax, 6
0x140013c2b  ja      short loc_140013C93
0x140013c2d  movzx   ecx, word ptr [rdx+8]
0x140013c31  lea     eax, [rcx+0Eh]
0x140013c34  cmp     eax, r8d
0x140013c37  ja      short loc_140013C93
0x140013c39  test    ecx, ecx
0x140013c3b  jz      short loc_140013C93
0x140013c3d  test    cl, 1
0x140013c40  jnz     short loc_140013C93
0x140013c42  cmp     [rdx+0Ah], di
0x140013c46  jz      short loc_140013C93
0x140013c48  mov     eax, ecx
0x140013c4a  shr     rax, 1
0x140013c4d  cmp     [rdx+rax*2+8], di
0x140013c52  jnz     short loc_140013C93
0x140013c54  mov     r11d, [rcx+rdx+0Ah]
0x140013c59  mov     eax, ecx
0x140013c5b  not     eax
0x140013c5d  cmp     eax, r11d
0x140013c60  jb      short loc_140013C93
0x140013c62  add     r11d, ecx
0x140013c65  mov     eax, r11d
0x140013c68  not     eax
0x140013c6a  cmp     eax, 0Eh
0x140013c6d  jb      short loc_140013C93
0x140013c6f  lea     eax, [r11+0Eh]
0x140013c73  cmp     eax, r8d
0x140013c76  ja      short loc_140013C93
0x140013c78  inc     r9d
0x140013c7b  cmp     r9d, ebx
0x140013c7e  jz      loc_140013BD5
0x140013c84  add     rdx, r8
0x140013c87  jmp     loc_140013BE9
0x140013c8c  mov     eax, edi
0x140013c8e  cmp     r9d, ebx
0x140013c91  jz      short loc_140013C98
0x140013c93  mov     eax, 0C000000Dh
0x140013c98  mov     rbx, [rsp+arg_0]
0x140013c9d  mov     rdi, [rsp+arg_8]
0x140013ca2  retn
```
