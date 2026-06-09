# DTLSCookieManager::ComputeCookie(uchar * const,ulong,uchar * const,ulong,uchar * const,ulong,uchar *)

- ea: `0x180075a8c`
- end: `0x180075b8c`
- name: `?ComputeCookie@DTLSCookieManager@@AEAAJQEAEK0K0KPEAE@Z`
- size: `256`
- prototype: `int(DTLSCookieManager *__hidden this, unsigned __int8 *const, unsigned int, unsigned __int8 *const, unsigned int, unsigned __int8 *const, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18005d974`
- `0x180075b94`

## callees

- `0x180075a8c`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180075ad7`
- `bcrypt!BCryptCreateHash` at `0x180075ad7`
- `bcrypt!BCryptHashData` at `0x180075af5`
- `bcrypt!BCryptHashData` at `0x180075b14`
- `bcrypt!BCryptHashData` at `0x180075b38`
- `bcrypt!BCryptHashData` at `0x180075af5`
- `bcrypt!BCryptHashData` at `0x180075b14`
- `bcrypt!BCryptHashData` at `0x180075b38`
- `bcrypt!BCryptFinishHash` at `0x180075b58`
- `bcrypt!BCryptFinishHash` at `0x180075b58`
- `bcrypt!BCryptDestroyHash` at `0x180075b71`
- `bcrypt!BCryptDestroyHash` at `0x180075b71`

## pseudocode

```c
__int64 __fastcall DTLSCookieManager::ComputeCookie(
        DTLSCookieManager *this,
        unsigned __int8 *const a2,
        ULONG a3,
        unsigned __int8 *const a4,
        ULONG cbInput,
        unsigned __int8 *const pbInput,
        ULONG a7,
        unsigned __int8 *pbOutput)
{
  void *v12; // rcx
  NTSTATUS v13; // ebx
  UCHAR *v15; // [rsp+20h] [rbp-38h]
  ULONG cbSecret; // [rsp+28h] [rbp-30h]
  BCRYPT_HASH_HANDLE hHash; // [rsp+60h] [rbp+8h] BYREF

  cbSecret = *(_DWORD *)this;
  v15 = (UCHAR *)*((_QWORD *)this + 1);
  v12 = (void *)*((_QWORD *)this + 3);
  hHash = 0;
  v13 = BCryptCreateHash(v12, &hHash, 0, 0, v15, cbSecret, 0);
  if ( v13 >= 0 )
  {
    v13 = BCryptHashData(hHash, a2, a3, 0);
    if ( v13 >= 0 )
    {
      v13 = BCryptHashData(hHash, a4, cbInput, 0);
      if ( v13 >= 0 )
      {
        v13 = BCryptHashData(hHash, pbInput, a7, 0);
        if ( v13 >= 0 )
        {
          v13 = BCryptFinishHash(hHash, pbOutput, *((_DWORD *)this + 8), 0);
          if ( v13 >= 0 )
            v13 = 0;
        }
      }
    }
  }
  if ( hHash )
    BCryptDestroyHash(hHash);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180075a8c  mov     r11, rsp
0x180075a8f  mov     [r11+10h], rbx
0x180075a93  mov     [r11+18h], rbp
0x180075a97  push    rsi
0x180075a98  push    rdi
0x180075a99  push    r14
0x180075a9b  sub     rsp, 40h
0x180075a9f  mov     eax, [rcx]
0x180075aa1  mov     rsi, r9
0x180075aa4  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180075aac  mov     ebp, r8d
0x180075aaf  mov     [rsp+58h+cbSecret], eax; cbSecret
0x180075ab3  mov     r14, rdx
0x180075ab6  mov     rax, [rcx+8]
0x180075aba  lea     rdx, [r11+8]; phHash
0x180075abe  mov     rdi, rcx
0x180075ac1  mov     [r11-38h], rax
0x180075ac5  mov     rcx, [rcx+18h]; hAlgorithm
0x180075ac9  xor     r9d, r9d; cbHashObject
0x180075acc  xor     r8d, r8d; pbHashObject
0x180075acf  mov     qword ptr [r11+8], 0
0x180075ad7  call    cs:__imp_BCryptCreateHash
0x180075add  mov     ebx, eax
0x180075adf  test    eax, eax
0x180075ae1  js      loc_180075B67
0x180075ae7  mov     rcx, [rsp+58h+hHash]; hHash
0x180075aec  xor     r9d, r9d; dwFlags
0x180075aef  mov     r8d, ebp; cbInput
0x180075af2  mov     rdx, r14; pbInput
0x180075af5  call    cs:__imp_BCryptHashData
0x180075afb  mov     ebx, eax
0x180075afd  test    eax, eax
0x180075aff  js      short loc_180075B67
0x180075b01  mov     r8d, [rsp+58h+cbInput]; cbInput
0x180075b09  xor     r9d, r9d; dwFlags
0x180075b0c  mov     rcx, [rsp+58h+hHash]; hHash
0x180075b11  mov     rdx, rsi; pbInput
0x180075b14  call    cs:__imp_BCryptHashData
0x180075b1a  mov     ebx, eax
0x180075b1c  test    eax, eax
0x180075b1e  js      short loc_180075B67
0x180075b20  mov     r8d, [rsp+58h+arg_30]; cbInput
0x180075b28  xor     r9d, r9d; dwFlags
0x180075b2b  mov     rdx, [rsp+58h+pbInput]; pbInput
0x180075b33  mov     rcx, [rsp+58h+hHash]; hHash
0x180075b38  call    cs:__imp_BCryptHashData
0x180075b3e  mov     ebx, eax
0x180075b40  test    eax, eax
0x180075b42  js      short loc_180075B67
0x180075b44  mov     r8d, [rdi+20h]; cbOutput
0x180075b48  xor     r9d, r9d; dwFlags
0x180075b4b  mov     rdx, [rsp+58h+pbOutput]; pbOutput
0x180075b53  mov     rcx, [rsp+58h+hHash]; hHash
0x180075b58  call    cs:__imp_BCryptFinishHash
0x180075b5e  mov     ebx, eax
0x180075b60  xor     eax, eax
0x180075b62  test    ebx, ebx
0x180075b64  cmovns  ebx, eax
0x180075b67  mov     rcx, [rsp+58h+hHash]; hHash
0x180075b6c  test    rcx, rcx
0x180075b6f  jz      short loc_180075B77
0x180075b71  call    cs:__imp_BCryptDestroyHash
0x180075b77  mov     rbp, [rsp+58h+arg_10]
0x180075b7c  mov     eax, ebx
0x180075b7e  mov     rbx, [rsp+58h+arg_8]
0x180075b83  add     rsp, 40h
0x180075b87  pop     r14
0x180075b89  pop     rdi
0x180075b8a  pop     rsi
0x180075b8b  retn
```
