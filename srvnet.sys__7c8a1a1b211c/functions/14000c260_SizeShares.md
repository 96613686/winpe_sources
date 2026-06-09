# SizeShares

- ea: `0x14000c260`
- end: `0x14000c473`
- name: `SizeShares`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a654`

## callees

- `0x14000c260`
- `0x14000c480`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000c397`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000c3f4`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000c397`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000c3f4`

## pseudocode

```c
__int64 __fastcall SizeShares(__int64 a1, __int64 a2)
{
  unsigned int v2; // eax
  ULONG v3; // ebx
  __int64 v6; // rax
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rcx
  int v10; // ecx
  void *v11; // rcx
  void *v12; // rcx

  v2 = *(_DWORD *)(a1 + 64);
  v3 = 0;
  if ( v2 == 505 )
  {
    if ( (*(_DWORD *)(a1 + 72) & 0x80u) != 0 )
      goto LABEL_15;
LABEL_30:
    if ( v2 != 503 )
    {
      if ( v2 != 505 )
        goto LABEL_26;
      v12 = *(void **)(a2 + 184);
      if ( v12 )
        v3 = RtlLengthSecurityDescriptor(v12) + 4;
    }
    v3 += SvcLengthOfStringInApiBuffer(a2 + 24);
    goto LABEL_32;
  }
  if ( v2 == 2 )
    goto LABEL_3;
  if ( v2 > 0x1F6 )
    goto LABEL_30;
  if ( v2 == 502 )
  {
LABEL_32:
    v11 = *(void **)(a2 + 192);
    if ( v11 )
      v3 += RtlLengthSecurityDescriptor(v11) + 4;
LABEL_3:
    if ( (*(_DWORD *)(a2 + 124) & 0x100000) != 0 )
    {
      v6 = a2 + 200;
      if ( a2 == -200 )
        goto LABEL_14;
    }
    else
    {
      v6 = a2 + 72;
      if ( a2 == -72 )
        goto LABEL_14;
    }
    LODWORD(v6) = *(unsigned __int16 *)v6 + 2;
LABEL_14:
    v3 += v6;
LABEL_15:
    v7 = (unsigned __int16 *)(a2 + 88);
    if ( a2 != -88 )
      LODWORD(v7) = *v7 + 2;
    v3 += (unsigned int)v7;
    v2 = *(_DWORD *)(a1 + 64);
    goto LABEL_18;
  }
  if ( v2 )
  {
    if ( v2 != 1 && v2 != 501 )
      goto LABEL_21;
    goto LABEL_15;
  }
LABEL_18:
  v8 = (unsigned __int16 *)(a2 + 8);
  if ( a2 != -8 )
    LODWORD(v8) = *v8 + 2;
  v3 += (unsigned int)v8;
LABEL_21:
  switch ( v2 )
  {
    case 0u:
      v10 = 8;
      return v10 + v3;
    case 1u:
      return v3 + 24;
    case 2u:
      return v3 + 56;
    case 0x1F5u:
      return v3 + 32;
  }
  if ( v2 != 502 )
  {
LABEL_26:
    if ( v2 == 503 )
      return v3 + 80;
    v10 = 4;
    if ( v2 == 505 )
      v10 = 120;
    return v10 + v3;
  }
  return v3 + 72;
}

```

## disassembly

```asm
0x14000c260  mov     [rsp+arg_0], rbx
0x14000c265  mov     [rsp+arg_8], rsi
0x14000c26a  push    rdi
0x14000c26b  sub     rsp, 20h
0x14000c26f  mov     eax, [rcx+40h]
0x14000c272  xor     ebx, ebx
0x14000c274  mov     rdi, rdx
0x14000c277  mov     rsi, rcx
0x14000c27a  cmp     eax, 1F9h
0x14000c27f  jz      loc_14000C451
0x14000c285  cmp     eax, 2
0x14000c288  jnz     short loc_14000C29E
0x14000c28a  test    dword ptr [rdi+7Ch], 100000h
0x14000c291  jnz     short loc_14000C2C4
0x14000c293  lea     rax, [rdi+48h]
0x14000c297  test    rax, rax
0x14000c29a  jnz     short loc_14000C2D4
0x14000c29c  jmp     short loc_14000C2DA
0x14000c29e  cmp     eax, 1F6h
0x14000c2a3  ja      loc_14000C372
0x14000c2a9  jz      loc_14000C387
0x14000c2af  mov     ecx, eax
0x14000c2b1  test    eax, eax
0x14000c2b3  jz      short loc_14000C2F4
0x14000c2b5  sub     ecx, 1
0x14000c2b8  jz      short loc_14000C2DC
0x14000c2ba  cmp     ecx, 1F4h
0x14000c2c0  jnz     short loc_14000C309
0x14000c2c2  jmp     short loc_14000C2DC
0x14000c2c4  lea     rax, [rdi+0C8h]
0x14000c2cb  test    rax, rax
0x14000c2ce  jz      loc_14000C464
0x14000c2d4  movzx   eax, word ptr [rax]
0x14000c2d7  add     eax, 2
0x14000c2da  add     ebx, eax
0x14000c2dc  lea     rax, [rdi+58h]
0x14000c2e0  test    rax, rax
0x14000c2e3  jz      loc_14000C469
0x14000c2e9  movzx   eax, word ptr [rax]
0x14000c2ec  add     eax, 2
0x14000c2ef  add     ebx, eax
0x14000c2f1  mov     eax, [rsi+40h]
0x14000c2f4  lea     rcx, [rdi+8]
0x14000c2f8  test    rcx, rcx
0x14000c2fb  jz      loc_14000C46E
0x14000c301  movzx   ecx, word ptr [rcx]
0x14000c304  add     ecx, 2
0x14000c307  add     ebx, ecx
0x14000c309  test    eax, eax
0x14000c30b  jz      short loc_14000C359
0x14000c30d  cmp     eax, 1
0x14000c310  jz      loc_14000C3AD
0x14000c316  cmp     eax, 2
0x14000c319  jz      loc_14000C3C6
0x14000c31f  cmp     eax, 1F5h
0x14000c324  jz      loc_14000C421
0x14000c32a  cmp     eax, 1F6h
0x14000c32f  jz      loc_14000C408
0x14000c335  cmp     eax, 1F7h
0x14000c33a  jnz     loc_14000C43A
0x14000c340  mov     ecx, 50h ; 'P'
0x14000c345  lea     eax, [rcx+rbx]
0x14000c348  mov     rbx, [rsp+28h+arg_0]
0x14000c34d  mov     rsi, [rsp+28h+arg_8]
0x14000c352  add     rsp, 20h
0x14000c356  pop     rdi
0x14000c357  retn
0x14000c359  mov     ecx, 8
0x14000c35e  lea     eax, [rcx+rbx]
0x14000c361  mov     rbx, [rsp+28h+arg_0]
0x14000c366  mov     rsi, [rsp+28h+arg_8]
0x14000c36b  add     rsp, 20h
0x14000c36f  pop     rdi
0x14000c370  retn
0x14000c372  mov     ecx, eax
0x14000c374  sub     ecx, 1F7h
0x14000c37a  jnz     short loc_14000C3DF
0x14000c37c  lea     rcx, [rdi+18h]
0x14000c380  call    SvcLengthOfStringInApiBuffer
0x14000c385  add     ebx, eax
0x14000c387  mov     rcx, [rdi+0C0h]; SecurityDescriptor
0x14000c38e  test    rcx, rcx
0x14000c391  jz      loc_14000C28A
0x14000c397  call    cs:__imp_RtlLengthSecurityDescriptor
0x14000c39e  nop     dword ptr [rax+rax+00h]
0x14000c3a3  add     eax, 4
0x14000c3a6  add     ebx, eax
0x14000c3a8  jmp     loc_14000C28A
0x14000c3ad  mov     ecx, 18h
0x14000c3b2  lea     eax, [rcx+rbx]
0x14000c3b5  mov     rbx, [rsp+28h+arg_0]
0x14000c3ba  mov     rsi, [rsp+28h+arg_8]
0x14000c3bf  add     rsp, 20h
0x14000c3c3  pop     rdi
0x14000c3c4  retn
0x14000c3c6  mov     ecx, 38h ; '8'
0x14000c3cb  lea     eax, [rcx+rbx]
0x14000c3ce  mov     rbx, [rsp+28h+arg_0]
0x14000c3d3  mov     rsi, [rsp+28h+arg_8]
0x14000c3d8  add     rsp, 20h
0x14000c3dc  pop     rdi
0x14000c3dd  retn
0x14000c3df  cmp     ecx, 2
0x14000c3e2  jnz     loc_14000C335
0x14000c3e8  mov     rcx, [rdx+0B8h]; SecurityDescriptor
0x14000c3ef  test    rcx, rcx
0x14000c3f2  jz      short loc_14000C37C
0x14000c3f4  call    cs:__imp_RtlLengthSecurityDescriptor
0x14000c3fb  nop     dword ptr [rax+rax+00h]
0x14000c400  lea     ebx, [rax+4]
0x14000c403  jmp     loc_14000C37C
0x14000c408  mov     ecx, 48h ; 'H'
0x14000c40d  lea     eax, [rcx+rbx]
0x14000c410  mov     rbx, [rsp+28h+arg_0]
0x14000c415  mov     rsi, [rsp+28h+arg_8]
0x14000c41a  add     rsp, 20h
0x14000c41e  pop     rdi
0x14000c41f  retn
0x14000c421  mov     rsi, [rsp+28h+arg_8]
0x14000c426  mov     ecx, 20h ; ' '
0x14000c42b  lea     eax, [rcx+rbx]
0x14000c42e  mov     rbx, [rsp+28h+arg_0]
0x14000c433  add     rsp, 20h
0x14000c437  pop     rdi
0x14000c438  retn
0x14000c43a  cmp     eax, 1F9h
0x14000c43f  mov     ecx, 4
0x14000c444  mov     edx, 78h ; 'x'
0x14000c449  cmovz   ecx, edx
0x14000c44c  jmp     loc_14000C35E
0x14000c451  mov     r8d, [rcx+48h]
0x14000c455  test    r8b, 80h
0x14000c459  jz      loc_14000C372
0x14000c45f  jmp     loc_14000C2DC
0x14000c464  jmp     loc_14000C2DA
0x14000c469  jmp     loc_14000C2EF
0x14000c46e  jmp     loc_14000C307
```
