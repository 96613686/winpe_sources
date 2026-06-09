# MyBuiltInHashing(uchar *,ulong)

- ea: `0x18002caf0`
- end: `0x18002cbda`
- name: `?MyBuiltInHashing@@YA_KPEAEK@Z`
- size: `234`
- prototype: `BCRYPT_HASH_HANDLE __fastcall(PUCHAR pbInput, ULONG cbInput)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d464`
- `0x18004b640`

## callees

- `0x18002caf0`
- `0x18003d270`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18002cb5e`
- `bcrypt!BCryptHashData` at `0x18002cb5e`
- `bcrypt!BCryptDestroyHash` at `0x18002cb94`
- `bcrypt!BCryptDestroyHash` at `0x18002cb94`
- `bcrypt!BCryptFinishHash` at `0x18002cb7f`
- `bcrypt!BCryptFinishHash` at `0x18002cb7f`
- `bcrypt!BCryptCreateHash` at `0x18002cb3b`
- `bcrypt!BCryptCreateHash` at `0x18002cb3b`

## pseudocode

```c
BCRYPT_HASH_HANDLE __fastcall MyBuiltInHashing(PUCHAR pbInput, ULONG cbInput)
{
  BCRYPT_HASH_HANDLE hHash[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v6; // [rsp+50h] [rbp-18h]

  *(_OWORD *)hHash = 0;
  v6 = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, hHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  if ( BCryptHashData(hHash[0], pbInput, cbInput, 0) < 0 )
    __fastfail(7u);
  if ( BCryptFinishHash(hHash[0], (PUCHAR)&hHash[1], 0x10u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(hHash[0]);
  return hHash[1];
}

```

## disassembly

```asm
0x18002caf0  mov     r11, rsp
0x18002caf3  mov     [r11+18h], rbx
0x18002caf7  mov     [r11+20h], rsi
0x18002cafb  push    rdi
0x18002cafc  sub     rsp, 60h
0x18002cb00  mov     rax, cs:__security_cookie
0x18002cb07  xor     rax, rsp
0x18002cb0a  mov     [rsp+68h+var_10], rax
0x18002cb0f  xor     eax, eax
0x18002cb11  xorps   xmm0, xmm0
0x18002cb14  mov     [rsp+68h+dwFlags], eax; dwFlags
0x18002cb18  mov     edi, edx
0x18002cb1a  mov     rbx, rcx
0x18002cb1d  mov     [rsp+68h+cbSecret], eax; cbSecret
0x18002cb21  movups  xmmword ptr [rsp+68h+hHash], xmm0
0x18002cb26  lea     ecx, [rax+21h]; hAlgorithm
0x18002cb29  mov     [r11-18h], rax
0x18002cb2d  xor     r9d, r9d; cbHashObject
0x18002cb30  mov     [r11-48h], rax
0x18002cb34  xor     r8d, r8d; pbHashObject
0x18002cb37  lea     rdx, [r11-28h]; phHash
0x18002cb3b  call    cs:__imp_BCryptCreateHash
0x18002cb42  nop     dword ptr [rax+rax+00h]
0x18002cb47  mov     esi, 7
0x18002cb4c  test    eax, eax
0x18002cb4e  js      short loc_18002CBC5
0x18002cb50  mov     rcx, [rsp+68h+hHash]; hHash
0x18002cb55  xor     r9d, r9d; dwFlags
0x18002cb58  mov     r8d, edi; cbInput
0x18002cb5b  mov     rdx, rbx; pbInput
0x18002cb5e  call    cs:__imp_BCryptHashData
0x18002cb65  nop     dword ptr [rax+rax+00h]
0x18002cb6a  test    eax, eax
0x18002cb6c  js      short loc_18002CBCC
0x18002cb6e  mov     rcx, [rsp+68h+hHash]; hHash
0x18002cb73  lea     rdx, [rsp+68h+hHash+8]; pbOutput
0x18002cb78  xor     r9d, r9d; dwFlags
0x18002cb7b  lea     r8d, [r9+10h]; cbOutput
0x18002cb7f  call    cs:__imp_BCryptFinishHash
0x18002cb86  nop     dword ptr [rax+rax+00h]
0x18002cb8b  test    eax, eax
0x18002cb8d  js      short loc_18002CBD3
0x18002cb8f  mov     rcx, [rsp+68h+hHash]; hHash
0x18002cb94  call    cs:__imp_BCryptDestroyHash
0x18002cb9b  nop     dword ptr [rax+rax+00h]
0x18002cba0  mov     rax, [rsp+68h+hHash+8]
0x18002cba5  mov     rcx, [rsp+68h+var_10]
0x18002cbaa  xor     rcx, rsp; StackCookie
0x18002cbad  call    __security_check_cookie
0x18002cbb2  lea     r11, [rsp+68h+var_8]
0x18002cbb7  mov     rbx, [r11+20h]
0x18002cbbb  mov     rsi, [r11+28h]
0x18002cbbf  mov     rsp, r11
0x18002cbc2  pop     rdi
0x18002cbc3  retn
0x18002cbc5  mov     rcx, rsi
0x18002cbc8  int     29h; Win8: RtlFailFast(ecx)
0x18002cbca  jmp     short loc_18002CB50
0x18002cbcc  mov     rcx, rsi
0x18002cbcf  int     29h; Win8: RtlFailFast(ecx)
0x18002cbd1  jmp     short loc_18002CB6E
0x18002cbd3  mov     rcx, rsi
0x18002cbd6  int     29h; Win8: RtlFailFast(ecx)
0x18002cbd8  jmp     short loc_18002CB8F
```
