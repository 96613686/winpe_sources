# MD5::Transform(void *,uint,uchar * const)

- ea: `0x18001eb70`
- end: `0x18001ec4c`
- name: `?Transform@MD5@@SAXPEAXIQEAE@Z`
- size: `220`
- prototype: `void __fastcall(PUCHAR pbInput, ULONG cbInput, unsigned __int8 *const)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e990`

## callees

- `0x18001eb70`
- `0x180044310`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18001ebbc`
- `bcrypt!BCryptCreateHash` at `0x18001ebbc`
- `bcrypt!BCryptDestroyHash` at `0x18001ec03`
- `bcrypt!BCryptDestroyHash` at `0x18001ec03`
- `bcrypt!BCryptFinishHash` at `0x18001ebf4`
- `bcrypt!BCryptFinishHash` at `0x18001ebf4`
- `bcrypt!BCryptHashData` at `0x18001ebd9`
- `bcrypt!BCryptHashData` at `0x18001ebd9`

## pseudocode

```c
void __fastcall MD5::Transform(PUCHAR pbInput, ULONG cbInput, unsigned __int8 *const a3)
{
  BCRYPT_HASH_HANDLE hHash[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v7; // [rsp+50h] [rbp-28h]

  *(_OWORD *)hHash = 0;
  v7 = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, hHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  if ( BCryptHashData(hHash[0], pbInput, cbInput, 0) < 0 )
    __fastfail(7u);
  if ( BCryptFinishHash(hHash[0], (PUCHAR)&hHash[1], 0x10u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(hHash[0]);
  *(BCRYPT_HASH_HANDLE *)a3 = hHash[1];
  *((_QWORD *)a3 + 1) = v7;
}

```

## disassembly

```asm
0x18001eb70  mov     r11, rsp
0x18001eb73  mov     [r11+20h], rbx
0x18001eb77  push    rbp
0x18001eb78  push    rsi
0x18001eb79  push    rdi
0x18001eb7a  sub     rsp, 60h
0x18001eb7e  mov     rax, cs:__security_cookie
0x18001eb85  xor     rax, rsp
0x18001eb88  mov     [rsp+78h+var_20], rax
0x18001eb8d  xor     eax, eax
0x18001eb8f  xorps   xmm0, xmm0
0x18001eb92  mov     [rsp+78h+dwFlags], eax; dwFlags
0x18001eb96  mov     rbx, r8
0x18001eb99  mov     esi, edx
0x18001eb9b  mov     [rsp+78h+cbSecret], eax; cbSecret
0x18001eb9f  mov     rdi, rcx
0x18001eba2  mov     [r11-58h], rax
0x18001eba6  movups  xmmword ptr [rsp+78h+hHash], xmm0
0x18001ebab  lea     ecx, [rax+21h]; hAlgorithm
0x18001ebae  mov     [r11-28h], rax
0x18001ebb2  xor     r9d, r9d; cbHashObject
0x18001ebb5  lea     rdx, [r11-38h]; phHash
0x18001ebb9  xor     r8d, r8d; pbHashObject
0x18001ebbc  call    cs:__imp_BCryptCreateHash
0x18001ebc2  mov     ebp, 7
0x18001ebc7  test    eax, eax
0x18001ebc9  js      short loc_18001EC37
0x18001ebcb  mov     rcx, [rsp+78h+hHash]; hHash
0x18001ebd0  xor     r9d, r9d; dwFlags
0x18001ebd3  mov     r8d, esi; cbInput
0x18001ebd6  mov     rdx, rdi; pbInput
0x18001ebd9  call    cs:__imp_BCryptHashData
0x18001ebdf  test    eax, eax
0x18001ebe1  js      short loc_18001EC3E
0x18001ebe3  mov     rcx, [rsp+78h+hHash]; hHash
0x18001ebe8  lea     rdx, [rsp+78h+hHash+8]; pbOutput
0x18001ebed  xor     r9d, r9d; dwFlags
0x18001ebf0  lea     r8d, [r9+10h]; cbOutput
0x18001ebf4  call    cs:__imp_BCryptFinishHash
0x18001ebfa  test    eax, eax
0x18001ebfc  js      short loc_18001EC45
0x18001ebfe  mov     rcx, [rsp+78h+hHash]; hHash
0x18001ec03  call    cs:__imp_BCryptDestroyHash
0x18001ec09  mov     rax, [rsp+78h+hHash+8]
0x18001ec0e  mov     [rbx], rax
0x18001ec11  mov     rax, [rsp+78h+var_28]
0x18001ec16  mov     [rbx+8], rax
0x18001ec1a  mov     rcx, [rsp+78h+var_20]
0x18001ec1f  xor     rcx, rsp; StackCookie
0x18001ec22  call    __security_check_cookie
0x18001ec27  mov     rbx, [rsp+78h+arg_18]
0x18001ec2f  add     rsp, 60h
0x18001ec33  pop     rdi
0x18001ec34  pop     rsi
0x18001ec35  pop     rbp
0x18001ec36  retn
0x18001ec37  mov     rcx, rbp
0x18001ec3a  int     29h; Win8: RtlFailFast(ecx)
0x18001ec3c  jmp     short loc_18001EBCB
0x18001ec3e  mov     rcx, rbp
0x18001ec41  int     29h; Win8: RtlFailFast(ecx)
0x18001ec43  jmp     short loc_18001EBE3
0x18001ec45  mov     rcx, rbp
0x18001ec48  int     29h; Win8: RtlFailFast(ecx)
0x18001ec4a  jmp     short loc_18001EBFE
```
