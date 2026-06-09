# SmbCryptoCreateCipherKeys

- ea: `0x14001fc04`
- end: `0x14001ff82`
- name: `SmbCryptoCreateCipherKeys`
- size: `894`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001ff90`

## callees

- `0x14000dd14`
- `0x14001fc04`
- `0x14002a3e0`
- `0x14002a540`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001fce2`
- `ntoskrnl!ExAllocatePool2` at `0x14001fe19`
- `ntoskrnl!ExAllocatePool2` at `0x14001fec3`
- `ntoskrnl!ExAllocatePool2` at `0x14001fce2`
- `ntoskrnl!ExAllocatePool2` at `0x14001fe19`
- `ntoskrnl!ExAllocatePool2` at `0x14001fec3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fd4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fd8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fdc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fd4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fd8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fdc5`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x14001fe9f`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x14001ff54`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x14001fe9f`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x14001ff54`
- `ksecdd!BCryptDestroyKey` at `0x14001fd79`
- `ksecdd!BCryptDestroyKey` at `0x14001fdb1`
- `ksecdd!BCryptDestroyKey` at `0x14001fd79`
- `ksecdd!BCryptDestroyKey` at `0x14001fdb1`

## pseudocode

```c
__int64 __fastcall SmbCryptoCreateCipherKeys(
        int a1,
        UCHAR *a2,
        ULONG a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 *a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        int a12,
        __int64 *a13)
{
  __int64 v13; // rsi
  __int64 *v14; // r14
  __int64 v15; // rdi
  __int64 v18; // r12
  size_t v19; // r8
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  UCHAR *pbSecret; // rbp
  NTSTATUS SymmetricKey; // ebx
  ULONG cbSecret; // r15d
  __int64 *v26; // r14
  __int64 *v27; // r13
  __int128 *v28; // rax
  __int64 v29; // rcx
  UCHAR *v30; // rax
  __int64 Pool2; // rax
  __int64 v33; // rax
  NTSTATUS v34; // eax
  UCHAR *v35; // [rsp+50h] [rbp-68h]
  __int128 v36; // [rsp+60h] [rbp-58h] BYREF

  v13 = 0;
  v14 = a8;
  v15 = 0;
  v35 = a2;
  v18 = 16;
  if ( (unsigned int)(a1 - 1) <= 1 )
  {
    v19 = 16;
    if ( a3 <= 0x10 )
      v19 = a3;
    v36 = 0;
    memmove(&v36, a2, v19);
    a3 = 16;
    v35 = (UCHAR *)&v36;
  }
  v20 = a1 - 1;
  if ( v20 )
  {
    v21 = v20 - 1;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        if ( v22 != 1 )
        {
          pbSecret = 0;
          SymmetricKey = -1073741811;
          cbSecret = 0;
LABEL_17:
          v27 = a13;
          goto LABEL_18;
        }
        v26 = qword_140040188;
      }
      else
      {
        v26 = qword_140040170;
      }
    }
    else
    {
      v26 = qword_140040158;
    }
  }
  else
  {
    v26 = SmbCryptoCiphers;
  }
  cbSecret = *((_DWORD *)v26 + 4);
  pbSecret = (UCHAR *)ExAllocatePool2(66, cbSecret, 590500684);
  if ( !pbSecret )
    goto LABEL_15;
  Pool2 = ExAllocatePool2(66, 24, 590500684);
  v13 = Pool2;
  if ( !Pool2 )
    goto LABEL_15;
  *(_QWORD *)Pool2 = 0;
  *(_QWORD *)(Pool2 + 8) = v26;
  *(_DWORD *)(Pool2 + 16) = 1;
  SymmetricKey = SmbCryptoSp800108CtrHmacSha256DeriveKey(v35, a3, a6, a7, (__int64)pbSecret, cbSecret);
  if ( SymmetricKey < 0 )
    goto LABEL_16;
  SymmetricKey = BCryptGenerateSymmetricKey(
                   (BCRYPT_ALG_HANDLE)*v26,
                   (BCRYPT_KEY_HANDLE *)v13,
                   0,
                   0,
                   pbSecret,
                   cbSecret,
                   0);
  if ( SymmetricKey < 0 )
    goto LABEL_16;
  v33 = ExAllocatePool2(66, 24, 590500684);
  v15 = v33;
  if ( !v33 )
  {
LABEL_15:
    SymmetricKey = -1073741670;
LABEL_16:
    v14 = a8;
    goto LABEL_17;
  }
  *(_QWORD *)v33 = 0;
  *(_QWORD *)(v33 + 8) = v26;
  *(_DWORD *)(v33 + 16) = 1;
  SymmetricKey = SmbCryptoSp800108CtrHmacSha256DeriveKey(v35, a3, a11, a12, (__int64)pbSecret, cbSecret);
  if ( SymmetricKey < 0 )
    goto LABEL_16;
  v34 = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)*v26, (BCRYPT_KEY_HANDLE *)v15, 0, 0, pbSecret, cbSecret, 0);
  v14 = a8;
  SymmetricKey = v34;
  v27 = a13;
  if ( v34 >= 0 )
  {
    *a8 = v13;
    SymmetricKey = 0;
    *a13 = v15;
  }
LABEL_18:
  if ( v35 == (UCHAR *)&v36 )
  {
    v28 = &v36;
    do
    {
      *(_BYTE *)v28 = 0;
      v28 = (__int128 *)((char *)v28 + 1);
      --v18;
    }
    while ( v18 );
  }
  if ( pbSecret )
  {
    v29 = cbSecret;
    v30 = pbSecret;
    if ( cbSecret )
    {
      do
      {
        *v30++ = 0;
        --v29;
      }
      while ( v29 );
    }
    ExFreePoolWithTag(pbSecret, 0x2332534Cu);
  }
  if ( SymmetricKey < 0 )
  {
    if ( v13 && _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v13 )
        BCryptDestroyKey(*(BCRYPT_KEY_HANDLE *)v13);
      ExFreePoolWithTag((PVOID)v13, 0x2332534Cu);
    }
    if ( v15 && _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v15 )
        BCryptDestroyKey(*(BCRYPT_KEY_HANDLE *)v15);
      ExFreePoolWithTag((PVOID)v15, 0x2332534Cu);
    }
    *v14 = 0;
    *v27 = 0;
  }
  return (unsigned int)SymmetricKey;
}

```

## disassembly

```asm
0x14001fc04  mov     [rsp+arg_0], rbx
0x14001fc09  push    rbp
0x14001fc0a  push    rsi
0x14001fc0b  push    rdi
0x14001fc0c  push    r12
0x14001fc0e  push    r13
0x14001fc10  push    r14
0x14001fc12  push    r15
0x14001fc14  sub     rsp, 80h
0x14001fc1b  mov     rax, cs:__security_cookie
0x14001fc22  xor     rax, rsp
0x14001fc25  mov     [rsp+0B8h+var_48], rax
0x14001fc2a  mov     rax, [rsp+0B8h+arg_60]
0x14001fc32  xor     esi, esi
0x14001fc34  mov     r14, [rsp+0B8h+arg_38]
0x14001fc3c  xor     edi, edi
0x14001fc3e  mov     [rsp+0B8h+var_78], rax
0x14001fc43  mov     r13d, r8d
0x14001fc46  lea     eax, [rcx-1]
0x14001fc49  mov     [rsp+0B8h+var_60], r9
0x14001fc4e  mov     [rsp+0B8h+var_68], rdx
0x14001fc53  mov     ebx, ecx
0x14001fc55  mov     [rsp+0B8h+var_70], r14
0x14001fc5a  lea     r12d, [rsi+10h]
0x14001fc5e  cmp     eax, 1
0x14001fc61  ja      short loc_14001FC8C
0x14001fc63  cmp     r13d, r12d
0x14001fc66  lea     rcx, [rsp+0B8h+var_58]; void *
0x14001fc6b  mov     r8d, r12d
0x14001fc6e  xorps   xmm0, xmm0
0x14001fc71  cmovbe  r8d, r13d; Size
0x14001fc75  movups  [rsp+0B8h+var_58], xmm0
0x14001fc7a  call    memmove
0x14001fc7f  lea     rax, [rsp+0B8h+var_58]
0x14001fc84  mov     r13d, r12d
0x14001fc87  mov     [rsp+0B8h+var_68], rax
0x14001fc8c  sub     ebx, 1
0x14001fc8f  jz      short loc_14001FCC7
0x14001fc91  sub     ebx, 1
0x14001fc94  jz      short loc_14001FCBE
0x14001fc96  sub     ebx, 1
0x14001fc99  jz      short loc_14001FCB5
0x14001fc9b  cmp     ebx, 1
0x14001fc9e  jz      short loc_14001FCAC
0x14001fca0  xor     ebp, ebp
0x14001fca2  mov     ebx, 0C000000Dh
0x14001fca7  xor     r15d, r15d
0x14001fcaa  jmp     short loc_14001FD04
0x14001fcac  lea     r14, qword_140040188
0x14001fcb3  jmp     short loc_14001FCCE
0x14001fcb5  lea     r14, qword_140040170
0x14001fcbc  jmp     short loc_14001FCCE
0x14001fcbe  lea     r14, qword_140040158
0x14001fcc5  jmp     short loc_14001FCCE
0x14001fcc7  lea     r14, SmbCryptoCiphers
0x14001fcce  mov     r15d, [r14+10h]
0x14001fcd2  mov     ebx, 42h ; 'B'
0x14001fcd7  mov     edx, r15d
0x14001fcda  mov     ecx, ebx
0x14001fcdc  mov     r8d, 2332534Ch
0x14001fce2  call    cs:__imp_ExAllocatePool2
0x14001fce9  nop     dword ptr [rax+rax+00h]
0x14001fcee  mov     rbp, rax
0x14001fcf1  test    rax, rax
0x14001fcf4  jnz     loc_14001FE0B
0x14001fcfa  mov     ebx, 0C000009Ah
0x14001fcff  mov     r14, [rsp+0B8h+var_70]
0x14001fd04  mov     r13, [rsp+0B8h+var_78]
0x14001fd09  lea     rax, [rsp+0B8h+var_58]
0x14001fd0e  cmp     [rsp+0B8h+var_68], rax
0x14001fd13  jnz     short loc_14001FD26
0x14001fd15  lea     rax, [rsp+0B8h+var_58]
0x14001fd1a  mov     byte ptr [rax], 0
0x14001fd1d  inc     rax
0x14001fd20  sub     r12, 1
0x14001fd24  jnz     short loc_14001FD1A
0x14001fd26  test    rbp, rbp
0x14001fd29  jz      short loc_14001FD56
0x14001fd2b  mov     ecx, r15d
0x14001fd2e  mov     rax, rbp
0x14001fd31  test    r15d, r15d
0x14001fd34  jz      short loc_14001FD42
0x14001fd36  mov     byte ptr [rax], 0
0x14001fd39  inc     rax
0x14001fd3c  sub     rcx, 1
0x14001fd40  jnz     short loc_14001FD36
0x14001fd42  mov     edx, 2332534Ch; Tag
0x14001fd47  mov     rcx, rbp; P
0x14001fd4a  call    cs:__imp_ExFreePoolWithTag
0x14001fd51  nop     dword ptr [rax+rax+00h]
0x14001fd56  test    ebx, ebx
0x14001fd58  jns     loc_14001FDE0
0x14001fd5e  or      ebp, 0FFFFFFFFh
0x14001fd61  test    rsi, rsi
0x14001fd64  jz      short loc_14001FD99
0x14001fd66  mov     eax, ebp
0x14001fd68  lock xadd [rsi+10h], eax
0x14001fd6d  add     eax, ebp
0x14001fd6f  jnz     short loc_14001FD99
0x14001fd71  mov     rcx, [rsi]; hKey
0x14001fd74  test    rcx, rcx
0x14001fd77  jz      short loc_14001FD85
0x14001fd79  call    cs:__imp_BCryptDestroyKey
0x14001fd80  nop     dword ptr [rax+rax+00h]
0x14001fd85  mov     edx, 2332534Ch; Tag
0x14001fd8a  mov     rcx, rsi; P
0x14001fd8d  call    cs:__imp_ExFreePoolWithTag
0x14001fd94  nop     dword ptr [rax+rax+00h]
0x14001fd99  test    rdi, rdi
0x14001fd9c  jz      short loc_14001FDD1
0x14001fd9e  mov     eax, ebp
0x14001fda0  lock xadd [rdi+10h], eax
0x14001fda5  add     eax, ebp
0x14001fda7  jnz     short loc_14001FDD1
0x14001fda9  mov     rcx, [rdi]; hKey
0x14001fdac  test    rcx, rcx
0x14001fdaf  jz      short loc_14001FDBD
0x14001fdb1  call    cs:__imp_BCryptDestroyKey
0x14001fdb8  nop     dword ptr [rax+rax+00h]
0x14001fdbd  mov     edx, 2332534Ch; Tag
0x14001fdc2  mov     rcx, rdi; P
0x14001fdc5  call    cs:__imp_ExFreePoolWithTag
0x14001fdcc  nop     dword ptr [rax+rax+00h]
0x14001fdd1  mov     qword ptr [r14], 0
0x14001fdd8  mov     qword ptr [r13+0], 0
0x14001fde0  mov     eax, ebx
0x14001fde2  mov     rcx, [rsp+0B8h+var_48]
0x14001fde7  xor     rcx, rsp; StackCookie
0x14001fdea  call    __security_check_cookie
0x14001fdef  mov     rbx, [rsp+0B8h+arg_0]
0x14001fdf7  add     rsp, 80h
0x14001fdfe  pop     r15
0x14001fe00  pop     r14
0x14001fe02  pop     r13
0x14001fe04  pop     r12
0x14001fe06  pop     rdi
0x14001fe07  pop     rsi
0x14001fe08  pop     rbp
0x14001fe09  retn
0x14001fe0b  mov     edx, 18h
0x14001fe10  mov     r8d, 2332534Ch
0x14001fe16  mov     rcx, rbx
0x14001fe19  call    cs:__imp_ExAllocatePool2
0x14001fe20  nop     dword ptr [rax+rax+00h]
0x14001fe25  mov     rsi, rax
0x14001fe28  test    rax, rax
0x14001fe2b  jz      loc_14001FCFA
0x14001fe31  mov     r9d, [rsp+0B8h+arg_20]
0x14001fe39  mov     edx, r13d; cbSecret
0x14001fe3c  mov     r8, [rsp+0B8h+var_60]
0x14001fe41  mov     rcx, [rsp+0B8h+var_68]; pbSecret
0x14001fe46  mov     [rax], rdi
0x14001fe49  mov     [rax+8], r14
0x14001fe4d  mov     dword ptr [rax+10h], 1
0x14001fe54  mov     eax, [rsp+0B8h+arg_30]
0x14001fe5b  mov     [rsp+0B8h+var_80], r15d; int
0x14001fe60  mov     qword ptr [rsp+0B8h+dwFlags], rbp; __int64
0x14001fe65  mov     [rsp+0B8h+cbSecret], eax; int
0x14001fe69  mov     rax, [rsp+0B8h+arg_28]
0x14001fe71  mov     [rsp+0B8h+pbSecret], rax; __int64
0x14001fe76  call    SmbCryptoSp800108CtrHmacSha256DeriveKey
0x14001fe7b  mov     ebx, eax
0x14001fe7d  test    eax, eax
0x14001fe7f  js      loc_14001FCFF
0x14001fe85  mov     rcx, [r14]; hAlgorithm
0x14001fe88  xor     r9d, r9d; cbKeyObject
0x14001fe8b  mov     [rsp+0B8h+dwFlags], edi; dwFlags
0x14001fe8f  xor     r8d, r8d; pbKeyObject
0x14001fe92  mov     [rsp+0B8h+cbSecret], r15d; cbSecret
0x14001fe97  mov     rdx, rsi; phKey
0x14001fe9a  mov     [rsp+0B8h+pbSecret], rbp; pbSecret
0x14001fe9f  call    cs:__imp_BCryptGenerateSymmetricKey
0x14001fea6  nop     dword ptr [rax+rax+00h]
0x14001feab  mov     ebx, eax
0x14001fead  test    eax, eax
0x14001feaf  js      loc_14001FCFF
0x14001feb5  mov     edx, 18h
0x14001feba  mov     r8d, 2332534Ch
0x14001fec0  lea     ecx, [rdx+2Ah]
0x14001fec3  call    cs:__imp_ExAllocatePool2
0x14001feca  nop     dword ptr [rax+rax+00h]
0x14001fecf  mov     rdi, rax
0x14001fed2  test    rax, rax
0x14001fed5  jz      loc_14001FCFA
0x14001fedb  mov     r9d, [rsp+0B8h+arg_48]
0x14001fee3  mov     edx, r13d; cbSecret
0x14001fee6  mov     r8, [rsp+0B8h+arg_40]
0x14001feee  mov     rcx, [rsp+0B8h+var_68]; pbSecret
0x14001fef3  mov     qword ptr [rax], 0
0x14001fefa  mov     [rax+8], r14
0x14001fefe  mov     dword ptr [rax+10h], 1
0x14001ff05  mov     eax, [rsp+0B8h+arg_58]
0x14001ff0c  mov     [rsp+0B8h+var_80], r15d; int
0x14001ff11  mov     qword ptr [rsp+0B8h+dwFlags], rbp; __int64
0x14001ff16  mov     [rsp+0B8h+cbSecret], eax; int
0x14001ff1a  mov     rax, [rsp+0B8h+arg_50]
0x14001ff22  mov     [rsp+0B8h+pbSecret], rax; __int64
0x14001ff27  call    SmbCryptoSp800108CtrHmacSha256DeriveKey
0x14001ff2c  mov     ebx, eax
0x14001ff2e  test    eax, eax
0x14001ff30  js      loc_14001FCFF
0x14001ff36  mov     rcx, [r14]; hAlgorithm
0x14001ff39  xor     r9d, r9d; cbKeyObject
0x14001ff3c  mov     [rsp+0B8h+dwFlags], 0; dwFlags
0x14001ff44  xor     r8d, r8d; pbKeyObject
0x14001ff47  mov     [rsp+0B8h+cbSecret], r15d; cbSecret
0x14001ff4c  mov     rdx, rdi; phKey
0x14001ff4f  mov     [rsp+0B8h+pbSecret], rbp; pbSecret
0x14001ff54  call    cs:__imp_BCryptGenerateSymmetricKey
0x14001ff5b  nop     dword ptr [rax+rax+00h]
0x14001ff60  mov     r14, [rsp+0B8h+var_70]
0x14001ff65  mov     ebx, eax
0x14001ff67  mov     r13, [rsp+0B8h+var_78]
0x14001ff6c  test    eax, eax
0x14001ff6e  js      loc_14001FD09
0x14001ff74  mov     [r14], rsi
0x14001ff77  xor     ebx, ebx
0x14001ff79  mov     [r13+0], rdi
0x14001ff7d  jmp     loc_14001FD09
```
