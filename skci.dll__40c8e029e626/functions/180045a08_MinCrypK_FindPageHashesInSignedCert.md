# MinCrypK_FindPageHashesInSignedCert

- ea: `0x180045a08`
- end: `0x180045bd9`
- name: `MinCrypK_FindPageHashesInSignedCert`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b2f4`

## callees

- `0x180014614`
- `0x1800162b4`
- `0x1800162e4`
- `0x18001671c`
- `0x18003392c`
- `0x180033980`
- `0x180044500`
- `0x1800457dc`
- `0x180045a08`
- `0x18004e1f4`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x180045b4f`
- `securekernel!RtlCompareMemory` at `0x180045b4f`

## pseudocode

```c
__int64 __fastcall MinCrypK_FindPageHashesInSignedCert(
        void *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        void *a9)
{
  size_t v11; // rdi
  int IsFileRevoked; // ebx
  __int64 *v13; // rdx
  __int64 v14; // rsi
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h]
  void *Source1; // [rsp+50h] [rbp-B0h]
  _QWORD *v21; // [rsp+58h] [rbp-A8h]
  _BYTE v22[64]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v23[48]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v24[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v25[16]; // [rsp+E0h] [rbp-20h] BYREF
  int v26; // [rsp+F0h] [rbp-10h]
  void *Src; // [rsp+F8h] [rbp-8h]

  v21 = a5;
  v11 = a2;
  Source1 = a1;
  LODWORD(v19) = 0;
  v18 = 0;
  v17 = 0;
  v16 = 0;
  IsFileRevoked = MinCryptIsFileRevoked(a3, a1, a2);
  if ( IsFileRevoked < 0 )
    goto LABEL_17;
  v13 = qword_180035A70;
  if ( (g_CiPolicyState & 0x10000) == 0 )
    v13 = (__int64 *)&qword_1800359F0;
  IsFileRevoked = MinCryptVerifySignedFileKMode(a4, v13, a6, v23, a7, 0);
  if ( IsFileRevoked < 0 )
    goto LABEL_17;
  v14 = (unsigned int)MinCryptDecodeHashAlgorithmIdentifier(v25);
  IsFileRevoked = MinCrypK_GetHashLength(v14, &v16);
  if ( IsFileRevoked < 0 )
    goto LABEL_17;
  if ( v16 != (_DWORD)v11
    || v26 != (_DWORD)v11
    || a3 != (_DWORD)v14
    || !(unsigned __int8)MinAsn1FindPageHashesAttribute(v24, v22)
    || !I_ValidatePageHashesBlob((__int64)v22, *(_QWORD *)a4, *(_DWORD *)(a4 + 8), v11, (unsigned int *)&v18) )
  {
    IsFileRevoked = -1073740760;
    goto LABEL_17;
  }
  if ( RtlCompareMemory(Source1, (const void *)(v19 + 4), (unsigned int)v11) != v11 )
  {
    IsFileRevoked = -1073741275;
LABEL_17:
    *(_DWORD *)(a6 + 8) |= 0x100000u;
    return (unsigned int)IsFileRevoked;
  }
  IsFileRevoked = I_AllocatePageHashes(&v18, (unsigned int)v14, 0, &v17);
  if ( IsFileRevoked < 0 )
    goto LABEL_17;
  *v21 = v17;
  if ( a9 )
    memcpy_0(a9, Src, v11);
  return (unsigned int)IsFileRevoked;
}

```

## disassembly

```asm
0x180045a08  mov     [rsp-8+arg_10], rbx
0x180045a0d  push    rbp
0x180045a0e  push    rsi
0x180045a0f  push    rdi
0x180045a10  push    r12
0x180045a12  push    r13
0x180045a14  push    r14
0x180045a16  push    r15
0x180045a18  lea     rbp, [rsp-10h]
0x180045a1d  sub     rsp, 110h
0x180045a24  mov     rax, cs:__security_cookie
0x180045a2b  xor     rax, rsp
0x180045a2e  mov     [rbp+40h+var_40], rax
0x180045a32  mov     rax, [rbp+40h+arg_20]
0x180045a36  mov     r13d, r8d
0x180045a39  mov     r14, [rbp+40h+arg_28]
0x180045a3d  mov     r8d, edx
0x180045a40  mov     rsi, [rbp+40h+arg_30]
0x180045a47  mov     r12, r9
0x180045a4a  mov     r15, [rbp+40h+arg_40]
0x180045a51  mov     [rsp+140h+var_E8], rax
0x180045a56  xor     eax, eax
0x180045a58  mov     edi, edx
0x180045a5a  mov     rdx, rcx
0x180045a5d  mov     [rsp+140h+Source1], rcx
0x180045a62  mov     ecx, r13d
0x180045a65  mov     qword ptr [rsp+140h+var_FC], rax
0x180045a6a  mov     [rsp+40h], rax
0x180045a6f  mov     [rsp+140h+var_108], rax
0x180045a74  mov     [rsp+140h+var_110], eax
0x180045a78  call    MinCryptIsFileRevoked
0x180045a7d  mov     ebx, eax
0x180045a7f  test    eax, eax
0x180045a81  js      loc_180045BA9
0x180045a87  test    byte ptr cs:g_CiPolicyState+2, 1
0x180045a8e  lea     rax, qword_1800359F0
0x180045a95  lea     rdx, qword_180035A70
0x180045a9c  mov     [rsp+140h+var_118], 0
0x180045aa5  cmovz   rdx, rax
0x180045aa9  mov     [rsp+140h+var_120], rsi
0x180045aae  lea     r9, [rbp+40h+var_A0]
0x180045ab2  mov     r8, r14
0x180045ab5  mov     rcx, r12
0x180045ab8  call    MinCryptVerifySignedFileKMode
0x180045abd  mov     ebx, eax
0x180045abf  test    eax, eax
0x180045ac1  js      loc_180045BA9
0x180045ac7  lea     rcx, [rbp+40h+var_60]
0x180045acb  call    MinCryptDecodeHashAlgorithmIdentifier
0x180045ad0  lea     rdx, [rsp+140h+var_110]
0x180045ad5  mov     ecx, eax
0x180045ad7  mov     esi, eax
0x180045ad9  call    MinCrypK_GetHashLength
0x180045ade  mov     ebx, eax
0x180045ae0  test    eax, eax
0x180045ae2  js      loc_180045BA9
0x180045ae8  cmp     [rsp+140h+var_110], edi
0x180045aec  jnz     loc_180045BA4
0x180045af2  cmp     [rbp+40h+var_50], edi
0x180045af5  jnz     loc_180045BA4
0x180045afb  cmp     r13d, esi
0x180045afe  jnz     loc_180045BA4
0x180045b04  lea     rdx, [rsp+140h+var_E0]
0x180045b09  lea     rcx, [rbp+40h+var_70]
0x180045b0d  call    MinAsn1FindPageHashesAttribute
0x180045b12  test    al, al
0x180045b14  jz      loc_180045BA4
0x180045b1a  mov     r8d, [r12+8]
0x180045b1f  lea     rax, [rsp+140h+var_100]
0x180045b24  mov     rdx, [r12]
0x180045b28  lea     rcx, [rsp+140h+var_E0]
0x180045b2d  mov     r9d, edi
0x180045b30  mov     [rsp+140h+var_120], rax
0x180045b35  call    I_ValidatePageHashesBlob
0x180045b3a  test    eax, eax
0x180045b3c  jz      short loc_180045BA4
0x180045b3e  mov     rdx, qword ptr [rsp+140h+var_FC+4]
0x180045b43  mov     r8d, edi; Length
0x180045b46  mov     rcx, [rsp+140h+Source1]; Source1
0x180045b4b  add     rdx, 4; Source2
0x180045b4f  call    cs:__imp_RtlCompareMemory
0x180045b56  nop     dword ptr [rax+rax+00h]
0x180045b5b  cmp     rax, rdi
0x180045b5e  jz      short loc_180045B67
0x180045b60  mov     ebx, 0C0000225h
0x180045b65  jmp     short loc_180045BA9
0x180045b67  lea     r9, [rsp+140h+var_108]
0x180045b6c  xor     r8d, r8d
0x180045b6f  mov     edx, esi
0x180045b71  lea     rcx, [rsp+140h+var_100]
0x180045b76  call    I_AllocatePageHashes
0x180045b7b  mov     ebx, eax
0x180045b7d  test    eax, eax
0x180045b7f  js      short loc_180045BA9
0x180045b81  mov     rcx, [rsp+140h+var_E8]
0x180045b86  mov     rax, [rsp+140h+var_108]
0x180045b8b  mov     [rcx], rax
0x180045b8e  test    r15, r15
0x180045b91  jz      short loc_180045BAF
0x180045b93  mov     rdx, [rbp+40h+Src]; Src
0x180045b97  mov     r8, rdi; MaxCount
0x180045b9a  mov     rcx, r15; void *
0x180045b9d  call    memcpy_0
0x180045ba2  jmp     short loc_180045BAF
0x180045ba4  mov     ebx, 0C0000428h
0x180045ba9  bts     dword ptr [r14+8], 14h
0x180045baf  mov     eax, ebx
0x180045bb1  mov     rcx, [rbp+40h+var_40]
0x180045bb5  xor     rcx, rsp; StackCookie
0x180045bb8  call    __security_check_cookie
0x180045bbd  mov     rbx, [rsp+140h+arg_10]
0x180045bc5  add     rsp, 110h
0x180045bcc  pop     r15
0x180045bce  pop     r14
0x180045bd0  pop     r13
0x180045bd2  pop     r12
0x180045bd4  pop     rdi
0x180045bd5  pop     rsi
0x180045bd6  pop     rbp
0x180045bd7  retn
```
