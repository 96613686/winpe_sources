# SspiHelperConstructAuthEx2FromStrings

- ea: `0x18001bc64`
- end: `0x18001bd9e`
- name: `SspiHelperConstructAuthEx2FromStrings`
- size: `314`
- prototype: `__int64 __fastcall(const void **, const void **, int, unsigned __int16, void *Src, PSEC_WINNT_AUTH_IDENTITY_OPAQUE *AuthDataCopy)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009db4`
- `0x180016b38`

## callees

- `0x18001bc64`
- `0x18001c63c`

## import_xrefs

- `SspiCli!SspiFreeAuthIdentity` at `0x18001bd87`
- `SspiCli!SspiFreeAuthIdentity` at `0x18001bd87`
- `SspiCli!SspiCopyAuthIdentity` at `0x18001bd56`
- `SspiCli!SspiCopyAuthIdentity` at `0x18001bd56`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bca8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bca8`

## pseudocode

```c
__int64 __fastcall SspiHelperConstructAuthEx2FromStrings(
        const void **a1,
        const void **a2,
        int a3,
        unsigned __int16 a4,
        void *Src,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE *AuthDataCopy)
{
  size_t v6; // rbp
  int v11; // r13d
  char *v12; // rax
  char *v13; // rdi
  SECURITY_STATUS v14; // ebx
  char *v15; // rbx
  unsigned int v16; // ecx
  size_t v17; // r8
  char *v18; // rbx
  char *v19; // rcx
  int v20; // eax
  char *v21; // rax

  v6 = a4;
  if ( (a3 & 0x10) != 0 )
    return 3221225485LL;
  v11 = *(unsigned __int16 *)a2 + *(unsigned __int16 *)a1 + a4 + 52;
  v12 = (char *)LocalAlloc(0x40u, (unsigned int)(v11 + 8));
  v13 = v12;
  if ( v12 )
  {
    *(_DWORD *)v12 = 513;
    v15 = v12 + 48;
    *((_WORD *)v12 + 2) = 48;
    *((_DWORD *)v12 + 2) = v11;
    v16 = *(unsigned __int16 *)a1;
    *((_WORD *)v12 + 8) = v16;
    *((_DWORD *)v12 + 3) = 48;
    memcpy_0(v12 + 48, a1[1], v16);
    v17 = *(unsigned __int16 *)a2;
    v18 = &v15[*((unsigned __int16 *)v13 + 8)];
    *((_WORD *)v13 + 12) = v17;
    *((_DWORD *)v13 + 5) = (_DWORD)v18 + 2 - (_DWORD)v13;
    memcpy_0(v18 + 2, a2[1], v17);
    v19 = &v18[*((unsigned __int16 *)v13 + 12) + 4];
    v20 = *((unsigned __int16 *)v13 + 12) + (_DWORD)v18 + 4;
    *((_WORD *)v13 + 16) = v6;
    *((_DWORD *)v13 + 7) = v20 - (_DWORD)v13;
    memcpy_0(v19, Src, v6);
    *((_DWORD *)v13 + 9) = a3;
    if ( (a3 & 0x10000) != 0 )
    {
      v14 = SspiCopyAuthIdentity(v13, AuthDataCopy);
      v21 = v13;
      if ( v14 < 0 )
      {
        *AuthDataCopy = 0;
        goto LABEL_10;
      }
    }
    else
    {
      *AuthDataCopy = v13;
      v13 = 0;
      v21 = 0;
    }
    v14 = 0;
LABEL_10:
    if ( v21 )
      SspiFreeAuthIdentity(v13);
    return (unsigned int)v14;
  }
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x18001bc64  push    rbx
0x18001bc66  push    rbp
0x18001bc67  push    rsi
0x18001bc68  push    rdi
0x18001bc69  push    r13
0x18001bc6b  push    r14
0x18001bc6d  push    r15
0x18001bc6f  sub     rsp, 20h
0x18001bc73  movzx   ebp, r9w
0x18001bc77  mov     esi, r8d
0x18001bc7a  mov     r14, rdx
0x18001bc7d  mov     r15, rcx
0x18001bc80  test    r8b, 10h
0x18001bc84  jz      short loc_18001BC90
0x18001bc86  mov     eax, 0C000000Dh
0x18001bc8b  jmp     loc_18001BD8F
0x18001bc90  movzx   ecx, word ptr [rcx]
0x18001bc93  lea     r13d, [rbp+34h]
0x18001bc97  movzx   eax, word ptr [rdx]
0x18001bc9a  add     ecx, eax
0x18001bc9c  add     r13d, ecx
0x18001bc9f  mov     ecx, 40h ; '@'; uFlags
0x18001bca4  lea     edx, [r13+8]; uBytes
0x18001bca8  call    cs:__imp_LocalAlloc
0x18001bcae  mov     rdi, rax
0x18001bcb1  test    rax, rax
0x18001bcb4  jnz     short loc_18001BCC0
0x18001bcb6  mov     ebx, 0C0000017h
0x18001bcbb  jmp     loc_18001BD8D
0x18001bcc0  mov     dword ptr [rax], 201h
0x18001bcc6  lea     rbx, [rax+30h]
0x18001bcca  mov     word ptr [rax+4], 30h ; '0'
0x18001bcd0  mov     [rax+8], r13d
0x18001bcd4  movzx   ecx, word ptr [r15]
0x18001bcd8  mov     [rax+10h], cx
0x18001bcdc  mov     r8d, ecx; Size
0x18001bcdf  mov     eax, ebx
0x18001bce1  mov     rcx, rbx; void *
0x18001bce4  sub     eax, edi
0x18001bce6  mov     [rdi+0Ch], eax
0x18001bce9  mov     rdx, [r15+8]; Src
0x18001bced  call    memcpy_0
0x18001bcf2  movzx   ecx, word ptr [r14]
0x18001bcf6  movzx   eax, word ptr [rdi+10h]
0x18001bcfa  mov     r8d, ecx; Size
0x18001bcfd  add     rbx, rax
0x18001bd00  mov     [rdi+18h], cx
0x18001bd04  lea     eax, [rbx+2]
0x18001bd07  sub     eax, edi
0x18001bd09  lea     rcx, [rbx+2]; void *
0x18001bd0d  mov     [rdi+14h], eax
0x18001bd10  mov     rdx, [r14+8]; Src
0x18001bd14  call    memcpy_0
0x18001bd19  movzx   eax, word ptr [rdi+18h]
0x18001bd1d  lea     rcx, [rbx+4]
0x18001bd21  mov     rdx, [rsp+58h+Src]; Src
0x18001bd29  add     rcx, rax; void *
0x18001bd2c  mov     eax, ecx
0x18001bd2e  mov     [rdi+20h], bp
0x18001bd32  sub     eax, edi
0x18001bd34  mov     r8, rbp; Size
0x18001bd37  mov     [rdi+1Ch], eax
0x18001bd3a  call    memcpy_0
0x18001bd3f  mov     [rdi+24h], esi
0x18001bd42  bt      esi, 10h
0x18001bd46  jnb     short loc_18001BD6E
0x18001bd48  mov     rsi, [rsp+58h+AuthDataCopy]
0x18001bd50  mov     rcx, rdi; AuthData
0x18001bd53  mov     rdx, rsi; AuthDataCopy
0x18001bd56  call    cs:__imp_SspiCopyAuthIdentity
0x18001bd5c  mov     ebx, eax
0x18001bd5e  test    eax, eax
0x18001bd60  mov     rax, rdi
0x18001bd63  jns     short loc_18001BD7D
0x18001bd65  mov     qword ptr [rsi], 0
0x18001bd6c  jmp     short loc_18001BD7F
0x18001bd6e  mov     rax, [rsp+58h+AuthDataCopy]
0x18001bd76  mov     [rax], rdi
0x18001bd79  xor     edi, edi
0x18001bd7b  xor     eax, eax
0x18001bd7d  xor     ebx, ebx
0x18001bd7f  test    rax, rax
0x18001bd82  jz      short loc_18001BD8D
0x18001bd84  mov     rcx, rdi; AuthData
0x18001bd87  call    cs:__imp_SspiFreeAuthIdentity
0x18001bd8d  mov     eax, ebx
0x18001bd8f  add     rsp, 20h
0x18001bd93  pop     r15
0x18001bd95  pop     r14
0x18001bd97  pop     r13
0x18001bd99  pop     rdi
0x18001bd9a  pop     rsi
0x18001bd9b  pop     rbp
0x18001bd9c  pop     rbx
0x18001bd9d  retn
```
