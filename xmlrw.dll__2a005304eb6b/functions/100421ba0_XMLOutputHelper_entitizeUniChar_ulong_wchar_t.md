# XMLOutputHelper::entitizeUniChar(ulong,wchar_t *)

- ea: `0x100421ba0`
- end: `0x100421c8d`
- name: `?entitizeUniChar@XMLOutputHelper@@SAHKPEA_W@Z`
- size: `237`
- prototype: `__int64 __fastcall(unsigned int, wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x100421d00`

## callees

- `0x100421ba0`
- `0x100426580`

## pseudocode

```c
__int64 __fastcall XMLOutputHelper::entitizeUniChar(int a1, wchar_t *a2)
{
  unsigned int v2; // r10d
  wchar_t *v3; // r9
  _WORD *v4; // r8
  unsigned int v6; // edx
  unsigned int v7; // r10d
  __int16 v8; // ax
  __int16 v9; // ax
  wchar_t v10; // ax
  __int64 v11; // rcx
  _WORD v13[16]; // [rsp+0h] [rbp-38h] BYREF

  *(_DWORD *)a2 = 2293798;
  v2 = -a1;
  v3 = a2 + 2;
  v4 = v13;
  if ( a1 >= 0 )
    v2 = a1;
  do
  {
    v6 = v2 / 0xA;
    v7 = v2 % 0xA;
    v8 = 48;
    if ( v7 >= 0xA )
      v8 = 55;
    v9 = v7 + v8;
    v2 = v6;
    *v4++ = v9;
  }
  while ( v6 );
  if ( a1 < 0 )
    *v4++ = 45;
  for ( ; v4 > v13; ++v3 )
  {
    v10 = *--v4;
    *v3 = v10;
  }
  v11 = -1;
  *v3 = 0;
  do
    ++v11;
  while ( a2[v11 + 2] );
  *(_DWORD *)&a2[(int)v11 + 2] = 59;
  return (unsigned int)(v11 + 3);
}

```

## disassembly

```asm
0x100421ba0  push    rbx
0x100421ba2  sub     rsp, 30h
0x100421ba6  mov     rax, cs:__security_cookie
0x100421bad  xor     rax, rsp
0x100421bb0  mov     [rsp+38h+var_18], rax
0x100421bb5  mov     ebx, ecx
0x100421bb7  mov     dword ptr [rdx], 230026h
0x100421bbd  mov     r10d, ecx
0x100421bc0  shr     ebx, 1Fh
0x100421bc3  neg     r10d
0x100421bc6  lea     r9, [rdx+4]
0x100421bca  test    bl, bl
0x100421bcc  lea     r8, [rsp+38h+var_38]
0x100421bd0  mov     r11, rdx
0x100421bd3  cmovz   r10d, ecx
0x100421bd7  mov     ecx, 37h ; '7'
0x100421bdc  nop     dword ptr [rax+00h]
0x100421be0  mov     eax, 0CCCCCCCDh
0x100421be5  mul     r10d
0x100421be8  shr     edx, 3
0x100421beb  lea     eax, [rdx+rdx*4]
0x100421bee  add     eax, eax
0x100421bf0  sub     r10d, eax
0x100421bf3  mov     eax, 30h ; '0'
0x100421bf8  cmp     r10d, 0Ah
0x100421bfc  cmovnb  ax, cx
0x100421c00  add     ax, r10w
0x100421c04  mov     r10d, edx
0x100421c07  mov     [r8], ax
0x100421c0b  add     r8, 2
0x100421c0f  test    edx, edx
0x100421c11  jnz     short loc_100421BE0
0x100421c13  test    bl, bl
0x100421c15  jz      short loc_100421C24
0x100421c17  mov     eax, 2Dh ; '-'
0x100421c1c  mov     [r8], ax
0x100421c20  add     r8, 2
0x100421c24  lea     rax, [rsp+38h+var_38]
0x100421c28  cmp     r8, rax
0x100421c2b  jbe     short loc_100421C4A
0x100421c2d  nop     dword ptr [rax]
0x100421c30  movzx   eax, word ptr [r8-2]
0x100421c35  sub     r8, 2
0x100421c39  mov     [r9], ax
0x100421c3d  add     r9, 2
0x100421c41  lea     rax, [rsp+38h+var_38]
0x100421c45  cmp     r8, rax
0x100421c48  ja      short loc_100421C30
0x100421c4a  xor     r8d, r8d
0x100421c4d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100421c54  mov     [r9], r8w
0x100421c58  nop     dword ptr [rax+rax+00000000h]
0x100421c60  inc     rcx
0x100421c63  cmp     [r11+rcx*2+4], r8w
0x100421c69  jnz     short loc_100421C60
0x100421c6b  movsxd  rax, ecx
0x100421c6e  mov     dword ptr [r11+rax*2+4], 3Bh ; ';'
0x100421c77  lea     eax, [rcx+3]
0x100421c7a  mov     rcx, [rsp+38h+var_18]
0x100421c7f  xor     rcx, rsp; StackCookie
0x100421c82  call    __security_check_cookie
0x100421c87  add     rsp, 30h
0x100421c8b  pop     rbx
0x100421c8c  retn
```
