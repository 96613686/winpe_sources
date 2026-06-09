# WaAuthSetCredentials

- ea: `0x18006af94`
- end: `0x18006b253`
- name: `WaAuthSetCredentials`
- size: `703`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18006af64`
- `0x180076b64`

## callees

- `0x180013820`
- `0x1800391c0`
- `0x1800692f8`
- `0x18006af94`
- `0x18006b25c`
- `0x1800722f0`
- `0x18008c180`
- `0x180092c08`
- `0x180095e2c`
- `0x1800971ec`

## import_xrefs

- `SspiCli!SspiEncryptAuthIdentity` at `0x18006b14c`
- `SspiCli!SspiEncryptAuthIdentity` at `0x18006b14c`
- `SspiCli!SspiZeroAuthIdentity` at `0x18006b0d9`
- `SspiCli!SspiZeroAuthIdentity` at `0x18006b213`
- `SspiCli!SspiZeroAuthIdentity` at `0x18006b0d9`
- `SspiCli!SspiZeroAuthIdentity` at `0x18006b213`
- `SspiCli!SspiCopyAuthIdentity` at `0x18006b183`
- `SspiCli!SspiCopyAuthIdentity` at `0x18006b183`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x18006b138`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x18006b138`
- `SspiCli!SspiValidateAuthIdentity` at `0x18006b058`
- `SspiCli!SspiValidateAuthIdentity` at `0x18006b058`
- `SspiCli!SspiFreeAuthIdentity` at `0x18006b0e9`
- `SspiCli!SspiFreeAuthIdentity` at `0x18006b223`
- `SspiCli!SspiFreeAuthIdentity` at `0x18006b0e9`
- `SspiCli!SspiFreeAuthIdentity` at `0x18006b223`

## pseudocode

```c
__int64 __fastcall WaAuthSetCredentials(__int64 *a1, __int64 a2)
{
  _DWORD *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // ebx
  SECURITY_STATUS v9; // eax
  __int64 v10; // rcx
  char v11; // di
  __int64 v12; // rdi
  void *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 Heap; // rax
  __int64 v17; // r9
  __int64 v18; // rax
  __int64 v19; // r8
  _BYTE v21[8]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+58h] [rbp-18h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData; // [rsp+60h] [rbp-10h] BYREF

  AuthData = 0;
  if ( (BYTE1(xmmword_1800AD720) & 4) != 0 )
  {
    v4 = (_DWORD *)*a1;
    if ( *a1 )
    {
      v5 = *((_QWORD *)v4 + 2);
      if ( v5 )
        v5 = *(_QWORD *)(v5 + 80);
      v6 = *((_QWORD *)v4 + 1);
      v7 = *((_QWORD *)v4 + 2);
    }
    else
    {
      v6 = 0;
      v7 = 0;
      v5 = 0;
    }
    WPP_SF_DSSqqqq(v5, v6, v7, *(_DWORD *)(a2 + 4), *(_QWORD *)(a2 + 8), *(_QWORD *)(a2 + 16), (__int64)v4, v6, v7, v5);
  }
  if ( *(_DWORD *)a2 )
  {
    if ( *(_DWORD *)a2 != 1 )
    {
      v8 = 87;
      goto LABEL_33;
    }
    v8 = 0;
    v9 = SspiCopyAuthIdentity(*(PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)(a2 + 8), &AuthData);
    if ( v9 )
      goto LABEL_30;
  }
  else
  {
    v8 = WapAuthCreateAuthIdentity(
           *(_DWORD *)(a2 + 4),
           *(const WCHAR **)(a2 + 8),
           *(const WCHAR **)(a2 + 16),
           0,
           &AuthData);
    if ( v8 )
      goto LABEL_33;
  }
  v9 = SspiValidateAuthIdentity(AuthData);
  if ( v9 )
    goto LABEL_30;
  if ( !*a1 )
  {
LABEL_24:
    if ( SspiIsAuthIdentityEncrypted(AuthData) || (v9 = SspiEncryptAuthIdentity(AuthData)) == 0 )
    {
      Heap = WxAllocateHeapEx(v15, 24);
      *a1 = Heap;
      if ( Heap )
      {
        *(_OWORD *)Heap = 0;
        *(_QWORD *)(Heap + 16) = 0;
        *(_DWORD *)*a1 = *(_DWORD *)(a2 + 4);
        *(_QWORD *)(*a1 + 8) = AuthData;
        AuthData = 0;
      }
      else
      {
        v8 = 8;
      }
      goto LABEL_33;
    }
LABEL_30:
    v8 = v9;
    goto LABEL_33;
  }
  v10 = *(_QWORD *)(*a1 + 16);
  if ( !v10 )
    goto LABEL_17;
  v21[0] = 0;
  v8 = WapAuthCompareIdentities(*(_QWORD *)(v10 + 80), AuthData, v21);
  if ( !v8 )
  {
    v11 = v21[0];
    if ( (BYTE1(xmmword_1800AD720) & 4) != 0 )
      WPP_SF_d(1034, 11, WPP_1089ada74f78334b297476e5568764d1_Traceguids, v21[0]);
    if ( !v11 )
    {
LABEL_17:
      v12 = *a1;
      v13 = *(void **)(*a1 + 8);
      if ( v13 )
      {
        SspiZeroAuthIdentity(v13);
        SspiFreeAuthIdentity(*(PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)(v12 + 8));
        *(_QWORD *)(v12 + 8) = 0;
      }
      v14 = *(_QWORD *)(v12 + 16);
      if ( v14 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 4), 0xFFFFFFFF) == 1 )
          WaAuthDestroyCredentials(v14);
        *(_QWORD *)(v12 + 16) = 0;
      }
      v22 = v12;
      WxFreeHeapEx(&v22);
      *a1 = 0;
      goto LABEL_24;
    }
  }
LABEL_33:
  if ( (BYTE1(xmmword_1800AD720) & 4) != 0 )
  {
    v17 = *a1;
    if ( *a1 )
    {
      v18 = *(_QWORD *)(v17 + 8);
      v19 = *(_QWORD *)(v17 + 16);
    }
    else
    {
      v18 = 0;
      v19 = 0;
    }
    WPP_SF_qqq(1034, 12, (unsigned int)WPP_1089ada74f78334b297476e5568764d1_Traceguids, v17, v18, v19);
  }
  if ( AuthData )
  {
    SspiZeroAuthIdentity(AuthData);
    SspiFreeAuthIdentity(AuthData);
  }
  return v8;
}

```

## disassembly

```asm
0x18006af94  mov     [rsp-18h+arg_10], rbx
0x18006af99  mov     [rsp-18h+arg_18], rsi
0x18006af9e  push    rbp
0x18006af9f  push    rdi
0x18006afa0  push    r14
0x18006afa2  mov     rbp, rsp
0x18006afa5  sub     rsp, 70h
0x18006afa9  mov     rax, cs:__security_cookie
0x18006afb0  xor     rax, rsp
0x18006afb3  mov     [rbp+var_8], rax
0x18006afb7  mov     r14, rdx
0x18006afba  mov     [rbp+AuthData], 0
0x18006afc2  mov     rsi, rcx
0x18006afc5  test    byte ptr cs:xmmword_1800AD720+1, 4
0x18006afcc  jz      short loc_18006B023
0x18006afce  mov     rax, [rcx]
0x18006afd1  test    rax, rax
0x18006afd4  jz      short loc_18006AFED
0x18006afd6  mov     rcx, [rax+10h]
0x18006afda  test    rcx, rcx
0x18006afdd  jz      short loc_18006AFE3
0x18006afdf  mov     rcx, [rcx+50h]
0x18006afe3  mov     rdx, [rax+8]
0x18006afe7  mov     r8, [rax+10h]
0x18006afeb  jmp     short loc_18006AFF4
0x18006afed  xor     edx, edx
0x18006afef  xor     r8d, r8d
0x18006aff2  xor     ecx, ecx
0x18006aff4  mov     r9d, [r14+4]
0x18006aff8  mov     [rsp+70h+var_28], rcx
0x18006affd  mov     [rsp+70h+var_30], r8
0x18006b002  mov     [rsp+70h+var_38], rdx
0x18006b007  mov     [rsp+70h+var_40], rax
0x18006b00c  mov     rax, [r14+10h]
0x18006b010  mov     [rsp+70h+var_48], rax
0x18006b015  mov     rax, [r14+8]
0x18006b019  mov     [rsp+70h+var_50], rax
0x18006b01e  call    WPP_SF_DSSqqqq
0x18006b023  cmp     dword ptr [r14], 0
0x18006b027  jnz     loc_18006B173
0x18006b02d  mov     r8, [r14+10h]
0x18006b031  lea     rax, [rbp+AuthData]
0x18006b035  mov     rdx, [r14+8]
0x18006b039  xor     r9d, r9d
0x18006b03c  mov     ecx, [r14+4]
0x18006b040  mov     [rsp+70h+var_50], rax
0x18006b045  call    WapAuthCreateAuthIdentity
0x18006b04a  mov     ebx, eax
0x18006b04c  test    eax, eax
0x18006b04e  jnz     loc_18006B1CA
0x18006b054  mov     rcx, [rbp+AuthData]; AuthData
0x18006b058  call    cs:__imp_SspiValidateAuthIdentity
0x18006b05f  nop     dword ptr [rax+rax+00h]
0x18006b064  test    eax, eax
0x18006b066  jnz     loc_18006B197
0x18006b06c  mov     rax, [rsi]
0x18006b06f  test    rax, rax
0x18006b072  jz      loc_18006B134
0x18006b078  mov     rcx, [rax+10h]
0x18006b07c  test    rcx, rcx
0x18006b07f  jz      short loc_18006B0CD
0x18006b081  mov     [rbp+var_20], 0
0x18006b085  mov     rdx, [rbp+AuthData]
0x18006b089  lea     r8, [rbp+var_20]
0x18006b08d  mov     rcx, [rcx+50h]
0x18006b091  call    WapAuthCompareIdentities
0x18006b096  mov     ebx, eax
0x18006b098  test    eax, eax
0x18006b09a  jnz     loc_18006B1CA
0x18006b0a0  test    byte ptr cs:xmmword_1800AD720+1, 4
0x18006b0a7  movzx   edi, [rbp+var_20]
0x18006b0ab  jz      short loc_18006B0C4
0x18006b0ad  mov     r9d, edi
0x18006b0b0  lea     edx, [rax+0Bh]
0x18006b0b3  mov     ecx, 40Ah
0x18006b0b8  lea     r8, WPP_1089ada74f78334b297476e5568764d1_Traceguids
0x18006b0bf  call    WPP_SF_d
0x18006b0c4  test    dil, dil
0x18006b0c7  jnz     loc_18006B1CA
0x18006b0cd  mov     rdi, [rsi]
0x18006b0d0  mov     rcx, [rdi+8]; AuthData
0x18006b0d4  test    rcx, rcx
0x18006b0d7  jz      short loc_18006B0FD
0x18006b0d9  call    cs:__imp_SspiZeroAuthIdentity
0x18006b0e0  nop     dword ptr [rax+rax+00h]
0x18006b0e5  mov     rcx, [rdi+8]; AuthData
0x18006b0e9  call    cs:__imp_SspiFreeAuthIdentity
0x18006b0f0  nop     dword ptr [rax+rax+00h]
0x18006b0f5  mov     qword ptr [rdi+8], 0
0x18006b0fd  mov     rcx, [rdi+10h]
0x18006b101  test    rcx, rcx
0x18006b104  jz      short loc_18006B120
0x18006b106  or      eax, 0FFFFFFFFh
0x18006b109  lock xadd [rcx+4], eax
0x18006b10e  cmp     eax, 1
0x18006b111  jnz     short loc_18006B118
0x18006b113  call    WaAuthDestroyCredentials
0x18006b118  mov     qword ptr [rdi+10h], 0
0x18006b120  lea     rcx, [rbp+var_18]
0x18006b124  mov     [rbp+var_18], rdi
0x18006b128  call    WxFreeHeapEx
0x18006b12d  mov     qword ptr [rsi], 0
0x18006b134  mov     rcx, [rbp+AuthData]; EncryptedAuthData
0x18006b138  call    cs:__imp_SspiIsAuthIdentityEncrypted
0x18006b13f  nop     dword ptr [rax+rax+00h]
0x18006b144  test    al, al
0x18006b146  jnz     short loc_18006B15C
0x18006b148  mov     rcx, [rbp+AuthData]; AuthData
0x18006b14c  call    cs:__imp_SspiEncryptAuthIdentity
0x18006b153  nop     dword ptr [rax+rax+00h]
0x18006b158  test    eax, eax
0x18006b15a  jnz     short loc_18006B197
0x18006b15c  mov     edx, 18h
0x18006b161  call    WxAllocateHeapEx
0x18006b166  mov     [rsi], rax
0x18006b169  test    rax, rax
0x18006b16c  jnz     short loc_18006B19B
0x18006b16e  lea     ebx, [rax+8]
0x18006b171  jmp     short loc_18006B1CA
0x18006b173  cmp     dword ptr [r14], 1
0x18006b177  jnz     short loc_18006B1C5
0x18006b179  mov     rcx, [r14+8]; AuthData
0x18006b17d  lea     rdx, [rbp+AuthData]; AuthDataCopy
0x18006b181  xor     ebx, ebx
0x18006b183  call    cs:__imp_SspiCopyAuthIdentity
0x18006b18a  nop     dword ptr [rax+rax+00h]
0x18006b18f  test    eax, eax
0x18006b191  jz      loc_18006B054
0x18006b197  mov     ebx, eax
0x18006b199  jmp     short loc_18006B1CA
0x18006b19b  xor     ecx, ecx
0x18006b19d  xorps   xmm0, xmm0
0x18006b1a0  movups  xmmword ptr [rax], xmm0
0x18006b1a3  mov     [rax+10h], rcx
0x18006b1a7  mov     rcx, [rsi]
0x18006b1aa  mov     eax, [r14+4]
0x18006b1ae  mov     [rcx], eax
0x18006b1b0  mov     rax, [rbp+AuthData]
0x18006b1b4  mov     rcx, [rsi]
0x18006b1b7  mov     [rcx+8], rax
0x18006b1bb  mov     [rbp+AuthData], 0
0x18006b1c3  jmp     short loc_18006B1CA
0x18006b1c5  mov     ebx, 57h ; 'W'
0x18006b1ca  test    byte ptr cs:xmmword_1800AD720+1, 4
0x18006b1d1  jz      short loc_18006B20A
0x18006b1d3  mov     r9, [rsi]
0x18006b1d6  test    r9, r9
0x18006b1d9  jz      short loc_18006B1E5
0x18006b1db  mov     rax, [r9+8]
0x18006b1df  mov     r8, [r9+10h]
0x18006b1e3  jmp     short loc_18006B1EA
0x18006b1e5  xor     eax, eax
0x18006b1e7  xor     r8d, r8d
0x18006b1ea  mov     [rsp+70h+var_48], r8
0x18006b1ef  mov     edx, 0Ch
0x18006b1f4  lea     r8, WPP_1089ada74f78334b297476e5568764d1_Traceguids
0x18006b1fb  mov     [rsp+70h+var_50], rax
0x18006b200  mov     ecx, 40Ah
0x18006b205  call    WPP_SF_qqq
0x18006b20a  mov     rcx, [rbp+AuthData]; AuthData
0x18006b20e  test    rcx, rcx
0x18006b211  jz      short loc_18006B22F
0x18006b213  call    cs:__imp_SspiZeroAuthIdentity
0x18006b21a  nop     dword ptr [rax+rax+00h]
0x18006b21f  mov     rcx, [rbp+AuthData]; AuthData
0x18006b223  call    cs:__imp_SspiFreeAuthIdentity
0x18006b22a  nop     dword ptr [rax+rax+00h]
0x18006b22f  mov     eax, ebx
0x18006b231  mov     rcx, [rbp+var_8]
0x18006b235  xor     rcx, rsp; StackCookie
0x18006b238  call    __security_check_cookie
0x18006b23d  lea     r11, [rsp+70h+var_s0]
0x18006b242  mov     rbx, [r11+30h]
0x18006b246  mov     rsi, [r11+38h]
0x18006b24a  mov     rsp, r11
0x18006b24d  pop     r14
0x18006b24f  pop     rdi
0x18006b250  pop     rbp
0x18006b251  retn
```
