# CompareAuthIdentity(void *,void *)

- ea: `0x1800a00d0`
- end: `0x1800a01e8`
- name: `?CompareAuthIdentity@@YAHPEAX0@Z`
- size: `280`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800a00d0`
- `0x1800a01f0`
- `0x1800a8be0`
- `0x1800ba8f0`
- `0x1800bb8a0`

## import_xrefs

- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x1800a00fe`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x1800a013e`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x1800a00fe`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x1800a013e`
- `SspiCli!SspiCompareAuthIdentities` at `0x1800a0184`
- `SspiCli!SspiCompareAuthIdentities` at `0x1800a0184`

## pseudocode

```c
_BOOL8 __fastcall CompareAuthIdentity(void *a1, void *a2)
{
  void *v2; // rbx
  void *v3; // rbp
  void *v4; // rsi
  void *v5; // rdi
  void *v6; // rax
  SECURITY_STATUS v7; // ebx
  void *v8; // rax
  unsigned __int8 SameSuppliedUser; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int8 SameSuppliedIdentity; // [rsp+48h] [rbp+10h] BYREF

  SameSuppliedUser = 0;
  v2 = a2;
  SameSuppliedIdentity = 0;
  v3 = a1;
  if ( a1 != a2 )
  {
    v4 = 0;
    v5 = 0;
    if ( a1 && SspiIsAuthIdentityEncrypted(a1) )
    {
      v6 = DuplicateAuthIdentity(v3);
      v4 = v6;
      if ( !v6 )
        return 0;
      if ( (unsigned int)DecryptAuthIdentity(v6) )
      {
        v7 = 14;
LABEL_16:
        WipeOutAuthIdentity(v4);
        FreeAuthIdentity(v4);
LABEL_17:
        if ( v5 )
        {
          WipeOutAuthIdentity(v5);
          FreeAuthIdentity(v5);
        }
        if ( !v7 && SameSuppliedUser )
          return SameSuppliedIdentity != 0;
        return 0;
      }
      v3 = v4;
    }
    if ( v2 && SspiIsAuthIdentityEncrypted(v2) )
    {
      v8 = DuplicateAuthIdentity(v2);
      v5 = v8;
      if ( !v8 || (unsigned int)DecryptAuthIdentity(v8) )
      {
        v7 = 14;
        goto LABEL_15;
      }
      v2 = v5;
    }
    v7 = SspiCompareAuthIdentities(v3, v2, &SameSuppliedUser, &SameSuppliedIdentity);
LABEL_15:
    if ( !v4 )
      goto LABEL_17;
    goto LABEL_16;
  }
  return 1;
}

```

## disassembly

```asm
0x1800a00d0  mov     [rsp+arg_10], rbx
0x1800a00d5  push    rbp
0x1800a00d6  push    rsi
0x1800a00d7  push    rdi
0x1800a00d8  sub     rsp, 20h
0x1800a00dc  mov     [rsp+38h+SameSuppliedUser], 0
0x1800a00e1  mov     rbx, rdx
0x1800a00e4  mov     [rsp+38h+SameSuppliedIdentity], 0
0x1800a00e9  mov     rbp, rcx
0x1800a00ec  cmp     rcx, rdx
0x1800a00ef  jz      loc_1800A01D5
0x1800a00f5  xor     esi, esi
0x1800a00f7  xor     edi, edi
0x1800a00f9  test    rcx, rcx
0x1800a00fc  jz      short loc_1800A0136
0x1800a00fe  call    cs:__imp_SspiIsAuthIdentityEncrypted
0x1800a0105  nop     dword ptr [rax+rax+00h]
0x1800a010a  test    al, al
0x1800a010c  jz      short loc_1800A0136
0x1800a010e  mov     rcx, rbp; void *
0x1800a0111  call    ?DuplicateAuthIdentity@@YAPEAXPEAX@Z; DuplicateAuthIdentity(void *)
0x1800a0116  mov     rsi, rax
0x1800a0119  test    rax, rax
0x1800a011c  jz      loc_1800A01D1
0x1800a0122  mov     rcx, rax; void *
0x1800a0125  call    ?DecryptAuthIdentity@@YAJPEAX@Z; DecryptAuthIdentity(void *)
0x1800a012a  test    eax, eax
0x1800a012c  jz      short loc_1800A0133
0x1800a012e  lea     ebx, [rdi+0Eh]
0x1800a0131  jmp     short loc_1800A0197
0x1800a0133  mov     rbp, rsi
0x1800a0136  test    rbx, rbx
0x1800a0139  jz      short loc_1800A0174
0x1800a013b  mov     rcx, rbx; EncryptedAuthData
0x1800a013e  call    cs:__imp_SspiIsAuthIdentityEncrypted
0x1800a0145  nop     dword ptr [rax+rax+00h]
0x1800a014a  test    al, al
0x1800a014c  jz      short loc_1800A0174
0x1800a014e  mov     rcx, rbx; void *
0x1800a0151  call    ?DuplicateAuthIdentity@@YAPEAXPEAX@Z; DuplicateAuthIdentity(void *)
0x1800a0156  mov     rdi, rax
0x1800a0159  test    rax, rax
0x1800a015c  jnz     short loc_1800A0165
0x1800a015e  mov     ebx, 0Eh
0x1800a0163  jmp     short loc_1800A0192
0x1800a0165  mov     rcx, rdi; void *
0x1800a0168  call    ?DecryptAuthIdentity@@YAJPEAX@Z; DecryptAuthIdentity(void *)
0x1800a016d  test    eax, eax
0x1800a016f  jnz     short loc_1800A015E
0x1800a0171  mov     rbx, rdi
0x1800a0174  lea     r9, [rsp+38h+SameSuppliedIdentity]; SameSuppliedIdentity
0x1800a0179  mov     rdx, rbx; AuthIdentity2
0x1800a017c  lea     r8, [rsp+38h+SameSuppliedUser]; SameSuppliedUser
0x1800a0181  mov     rcx, rbp; AuthIdentity1
0x1800a0184  call    cs:__imp_SspiCompareAuthIdentities
0x1800a018b  nop     dword ptr [rax+rax+00h]
0x1800a0190  mov     ebx, eax
0x1800a0192  test    rsi, rsi
0x1800a0195  jz      short loc_1800A01A7
0x1800a0197  mov     rcx, rsi; void *
0x1800a019a  call    ?WipeOutAuthIdentity@@YAXPEAX@Z; WipeOutAuthIdentity(void *)
0x1800a019f  mov     rcx, rsi; void *
0x1800a01a2  call    ?FreeAuthIdentity@@YAXPEAX@Z; FreeAuthIdentity(void *)
0x1800a01a7  test    rdi, rdi
0x1800a01aa  jz      short loc_1800A01BC
0x1800a01ac  mov     rcx, rdi; void *
0x1800a01af  call    ?WipeOutAuthIdentity@@YAXPEAX@Z; WipeOutAuthIdentity(void *)
0x1800a01b4  mov     rcx, rdi; void *
0x1800a01b7  call    ?FreeAuthIdentity@@YAXPEAX@Z; FreeAuthIdentity(void *)
0x1800a01bc  test    ebx, ebx
0x1800a01be  jnz     short loc_1800A01D1
0x1800a01c0  cmp     [rsp+38h+SameSuppliedUser], bl
0x1800a01c4  jz      short loc_1800A01D1
0x1800a01c6  xor     eax, eax
0x1800a01c8  cmp     [rsp+38h+SameSuppliedIdentity], al
0x1800a01cc  setnz   al
0x1800a01cf  jmp     short loc_1800A01DA
0x1800a01d1  xor     eax, eax
0x1800a01d3  jmp     short loc_1800A01DA
0x1800a01d5  mov     eax, 1
0x1800a01da  mov     rbx, [rsp+38h+arg_10]
0x1800a01df  add     rsp, 20h
0x1800a01e3  pop     rdi
0x1800a01e4  pop     rsi
0x1800a01e5  pop     rbp
0x1800a01e6  retn
```
