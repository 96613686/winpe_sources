# SamiEncryptPasswordWithOldPasswordAES(_UNICODE_STRING *,_UNICODE_STRING *,_SAMPR_ENCRYPTED_PASSWORD_AES *)

- ea: `0x1800079c8`
- end: `0x180007c42`
- name: `?SamiEncryptPasswordWithOldPasswordAES@@YAJPEAU_UNICODE_STRING@@0PEAU_SAMPR_ENCRYPTED_PASSWORD_AES@@@Z`
- size: `634`
- prototype: `int(struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _SAMPR_ENCRYPTED_PASSWORD_AES *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180013490`

## callees

- `0x180006620`
- `0x1800078c0`
- `0x1800079c8`
- `0x18000807c`
- `0x1800080bc`
- `0x180009b38`
- `0x1800176b0`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180007bf5`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180007bf5`
- `bcrypt!BCryptGenRandom` at `0x180007ae1`
- `bcrypt!BCryptGenRandom` at `0x180007ae1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180007aa4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180007aa4`
- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x180007b70`
- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x180007b70`
- `CRYPTSP!SystemFunction007` at `0x180007a50`
- `CRYPTSP!SystemFunction007` at `0x180007a50`

## pseudocode

```c
__int64 __fastcall SamiEncryptPasswordWithOldPasswordAES(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        struct _SAMPR_ENCRYPTED_PASSWORD_AES *a3)
{
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r8
  ULONGLONG cIterations; // rdi
  unsigned int v13; // edx
  unsigned int v14; // r9d
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-29h] BYREF
  ULONGLONG v17; // [rsp+58h] [rbp-21h] BYREF
  UCHAR pbPassword[16]; // [rsp+60h] [rbp-19h] BYREF
  UCHAR pbBuffer[16]; // [rsp+70h] [rbp-9h] BYREF
  UCHAR pbDerivedKey[16]; // [rsp+80h] [rbp+7h] BYREF

  phAlgorithm = 0;
  v17 = 0;
  *(_OWORD *)pbBuffer = 0;
  *(_OWORD *)pbDerivedKey = 0;
  *(_OWORD *)pbPassword = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_2fc01e8881f838e633c794a14c3714b3_Traceguids);
  v6 = SystemFunction007(a1, pbPassword);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA512", 0, 8u);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v6 = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
      v7 = v6;
      if ( v6 >= 0 )
      {
        KEGetSamRpcPwdChangePBKDF2Iterations(&v17);
        cIterations = v17;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, v17);
        v6 = BCryptDeriveKeyPBKDF2(phAlgorithm, pbPassword, 0x10u, pbBuffer, 0x10u, cIterations, pbDerivedKey, 0x10u, 0);
        v7 = v6;
        if ( v6 >= 0 )
        {
          v6 = SampEncryptClearPasswordAESWorker(pbDerivedKey, v13, pbBuffer, v14, phAlgorithm, a2, a3);
          v7 = v6;
          if ( v6 >= 0 )
          {
            *((_QWORD *)a3 + 12) = cIterations;
            goto LABEL_29;
          }
          v8 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v9 = 16;
            goto LABEL_8;
          }
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v9 = 15;
            goto LABEL_8;
          }
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 13;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 12;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 11;
LABEL_8:
      WPP_SF_D(v8[2], v9, &WPP_2fc01e8881f838e633c794a14c3714b3_Traceguids, (unsigned int)v6);
LABEL_29:
      v8 = WPP_GLOBAL_Control;
    }
  }
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    v8 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    WPP_SF_D(v8[2], 17, &WPP_2fc01e8881f838e633c794a14c3714b3_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x1800079c8  push    rbp
0x1800079ca  push    rbx
0x1800079cb  push    rsi
0x1800079cc  push    rdi
0x1800079cd  push    r12
0x1800079cf  push    r14
0x1800079d1  push    r15
0x1800079d3  lea     rbp, [rsp-27h]
0x1800079d8  sub     rsp, 0A0h
0x1800079df  mov     rax, cs:__security_cookie
0x1800079e6  xor     rax, rsp
0x1800079e9  mov     [rbp+57h+var_40], rax
0x1800079ed  xorps   xmm0, xmm0
0x1800079f0  mov     [rbp+57h+phAlgorithm], 0
0x1800079f8  xorps   xmm1, xmm1
0x1800079fb  mov     [rbp+57h+var_78], 0
0x180007a03  movups  xmmword ptr [rbp+57h+pbBuffer], xmm0
0x180007a07  mov     rsi, r8
0x180007a0a  mov     r14, rdx
0x180007a0d  movups  xmmword ptr [rbp+57h+var_50], xmm1
0x180007a11  mov     rbx, rcx
0x180007a14  movdqu  xmmword ptr [rbp+57h+pbPassword], xmm0
0x180007a19  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a20  lea     r12, WPP_2fc01e8881f838e633c794a14c3714b3_Traceguids
0x180007a27  mov     r15d, 2
0x180007a2d  test    [rcx+1Ch], r15b
0x180007a31  jz      short loc_180007A49
0x180007a33  cmp     byte ptr [rcx+19h], 4
0x180007a37  jb      short loc_180007A49
0x180007a39  mov     rcx, [rcx+10h]
0x180007a3d  lea     edx, [r15+8]
0x180007a41  mov     r8, r12
0x180007a44  call    WPP_SF_
0x180007a49  lea     rdx, [rbp+57h+pbPassword]
0x180007a4d  mov     rcx, rbx
0x180007a50  call    cs:__imp_SystemFunction007
0x180007a56  mov     ebx, eax
0x180007a58  test    eax, eax
0x180007a5a  jns     short loc_180007A90
0x180007a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a63  test    [rcx+1Ch], r15b
0x180007a67  jz      loc_180007BE7
0x180007a6d  cmp     [rcx+19h], r15b
0x180007a71  jb      loc_180007BE7
0x180007a77  mov     edx, 0Bh
0x180007a7c  mov     rcx, [rcx+10h]
0x180007a80  mov     r9d, eax
0x180007a83  mov     r8, r12
0x180007a86  call    WPP_SF_D
0x180007a8b  jmp     loc_180007BE0
0x180007a90  mov     r9d, 8; dwFlags
0x180007a96  lea     rdx, pszAlgId; "SHA512"
0x180007a9d  xor     r8d, r8d; pszImplementation
0x180007aa0  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x180007aa4  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180007aaa  mov     ebx, eax
0x180007aac  test    eax, eax
0x180007aae  jns     short loc_180007AD2
0x180007ab0  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ab7  test    [rcx+1Ch], r15b
0x180007abb  jz      loc_180007BE7
0x180007ac1  cmp     [rcx+19h], r15b
0x180007ac5  jb      loc_180007BE7
0x180007acb  mov     edx, 0Ch
0x180007ad0  jmp     short loc_180007A7C
0x180007ad2  mov     r9d, r15d; dwFlags
0x180007ad5  lea     rdx, [rbp+57h+pbBuffer]; pbBuffer
0x180007ad9  mov     r8d, 10h; cbBuffer
0x180007adf  xor     ecx, ecx; hAlgorithm
0x180007ae1  call    cs:__imp_BCryptGenRandom
0x180007ae7  mov     ebx, eax
0x180007ae9  test    eax, eax
0x180007aeb  jns     short loc_180007B12
0x180007aed  mov     rcx, cs:WPP_GLOBAL_Control
0x180007af4  test    [rcx+1Ch], r15b
0x180007af8  jz      loc_180007BE7
0x180007afe  cmp     [rcx+19h], r15b
0x180007b02  jb      loc_180007BE7
0x180007b08  mov     edx, 0Dh
0x180007b0d  jmp     loc_180007A7C
0x180007b12  lea     rcx, [rbp+57h+var_78]
0x180007b16  call    KEGetSamRpcPwdChangePBKDF2Iterations
0x180007b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b22  mov     rdi, [rbp+57h+var_78]
0x180007b26  test    [rcx+1Ch], r15b
0x180007b2a  jz      short loc_180007B3E
0x180007b2c  cmp     byte ptr [rcx+19h], 4
0x180007b30  jb      short loc_180007B3E
0x180007b32  mov     rcx, [rcx+10h]
0x180007b36  mov     r9, rdi
0x180007b39  call    WPP_SF_i
0x180007b3e  mov     ecx, 10h
0x180007b43  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x180007b4b  mov     [rsp+0D0h+cbDerivedKey], ecx; cbDerivedKey
0x180007b4f  lea     rax, [rbp+57h+var_50]
0x180007b53  mov     [rsp+0D0h+pbDerivedKey], rax; pbDerivedKey
0x180007b58  lea     r9, [rbp+57h+pbBuffer]; pbSalt
0x180007b5c  mov     r8d, ecx; cbPassword
0x180007b5f  mov     [rsp+0D0h+cIterations], rdi; cIterations
0x180007b64  mov     [rsp+0D0h+cbSalt], ecx; cbSalt
0x180007b68  lea     rdx, [rbp+57h+pbPassword]; pbPassword
0x180007b6c  mov     rcx, [rbp+57h+phAlgorithm]; hPrf
0x180007b70  call    cs:__imp_BCryptDeriveKeyPBKDF2
0x180007b76  mov     ebx, eax
0x180007b78  test    eax, eax
0x180007b7a  jns     short loc_180007B99
0x180007b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b83  test    [rcx+1Ch], r15b
0x180007b87  jz      short loc_180007BE7
0x180007b89  cmp     [rcx+19h], r15b
0x180007b8d  jb      short loc_180007BE7
0x180007b8f  mov     edx, 0Fh
0x180007b94  jmp     loc_180007A7C
0x180007b99  mov     rax, [rbp+57h+phAlgorithm]
0x180007b9d  lea     r8, [rbp+57h+pbBuffer]; unsigned __int8 *
0x180007ba1  mov     [rsp+0D0h+pbDerivedKey], rsi; struct _SAMPR_ENCRYPTED_PASSWORD_AES *
0x180007ba6  lea     rcx, [rbp+57h+var_50]; unsigned __int8 *
0x180007baa  mov     [rsp+0D0h+cIterations], r14; struct _UNICODE_STRING *
0x180007baf  mov     qword ptr [rsp+0D0h+cbSalt], rax; hAlgorithm
0x180007bb4  call    ?SampEncryptClearPasswordAESWorker@@YAJPEAEK0KPEAXPEAU_UNICODE_STRING@@PEAU_SAMPR_ENCRYPTED_PASSWORD_AES@@@Z; SampEncryptClearPasswordAESWorker(uchar *,ulong,uchar *,ulong,void *,_UNICODE_STRING *,_SAMPR_ENCRYPTED_PASSWORD_AES *)
0x180007bb9  mov     ebx, eax
0x180007bbb  test    eax, eax
0x180007bbd  jns     short loc_180007BDC
0x180007bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bc6  test    [rcx+1Ch], r15b
0x180007bca  jz      short loc_180007BE7
0x180007bcc  cmp     [rcx+19h], r15b
0x180007bd0  jb      short loc_180007BE7
0x180007bd2  mov     edx, 10h
0x180007bd7  jmp     loc_180007A7C
0x180007bdc  mov     [rsi+60h], rdi
0x180007be0  mov     rcx, cs:WPP_GLOBAL_Control
0x180007be7  mov     rax, [rbp+57h+phAlgorithm]
0x180007beb  test    rax, rax
0x180007bee  jz      short loc_180007C02
0x180007bf0  xor     edx, edx; dwFlags
0x180007bf2  mov     rcx, rax; hAlgorithm
0x180007bf5  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180007bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c02  test    [rcx+1Ch], r15b
0x180007c06  jz      short loc_180007C22
0x180007c08  cmp     byte ptr [rcx+19h], 4
0x180007c0c  jb      short loc_180007C22
0x180007c0e  mov     rcx, [rcx+10h]
0x180007c12  mov     edx, 11h
0x180007c17  mov     r9d, ebx
0x180007c1a  mov     r8, r12
0x180007c1d  call    WPP_SF_D
0x180007c22  mov     eax, ebx
0x180007c24  mov     rcx, [rbp+57h+var_40]
0x180007c28  xor     rcx, rsp; StackCookie
0x180007c2b  call    __security_check_cookie
0x180007c30  add     rsp, 0A0h
0x180007c37  pop     r15
0x180007c39  pop     r14
0x180007c3b  pop     r12
0x180007c3d  pop     rdi
0x180007c3e  pop     rsi
0x180007c3f  pop     rbx
0x180007c40  pop     rbp
0x180007c41  retn
```
