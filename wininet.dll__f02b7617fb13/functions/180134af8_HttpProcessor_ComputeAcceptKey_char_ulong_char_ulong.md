# HttpProcessor::ComputeAcceptKey(char *,ulong,char * *,ulong *)

- ea: `0x180134af8`
- end: `0x180134cab`
- name: `?ComputeAcceptKey@HttpProcessor@@SAJPEADKPEAPEADPEAK@Z`
- size: `435`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, char **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801b2280`

## callees

- `0x18003e350`
- `0x18012e008`
- `0x180131f34`
- `0x180134af8`
- `0x18014a7a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180134c5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180134c5d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180134b4e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180134b4e`
- `bcrypt!BCryptCreateHash` at `0x180134b8c`
- `bcrypt!BCryptCreateHash` at `0x180134b8c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180134c85`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180134c85`
- `bcrypt!BCryptHashData` at `0x180134baa`
- `bcrypt!BCryptHashData` at `0x180134bcd`
- `bcrypt!BCryptHashData` at `0x180134baa`
- `bcrypt!BCryptHashData` at `0x180134bcd`
- `bcrypt!BCryptFinishHash` at `0x180134bf0`
- `bcrypt!BCryptFinishHash` at `0x180134bf0`
- `bcrypt!BCryptDestroyHash` at `0x180134c6c`
- `bcrypt!BCryptDestroyHash` at `0x180134c6c`

## pseudocode

```c
__int64 __fastcall HttpProcessor::ComputeAcceptKey(PUCHAR pbInput, ULONG cbInput, char **a3, unsigned int *a4)
{
  NTSTATUS v8; // eax
  int CharCount; // ebx
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  NTSTATUS v13; // eax
  unsigned __int8 *v14; // rdi
  unsigned int v16[2]; // [rsp+40h] [rbp-40h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-38h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-30h] BYREF
  UCHAR pbOutput[24]; // [rsp+58h] [rbp-28h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  v16[0] = 0;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", 0, 0);
  CharCount = v8 | 0x10000000;
  if ( v8 >= 0 )
  {
    v10 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
    CharCount = v10 | 0x10000000;
    if ( v10 >= 0 )
    {
      v11 = BCryptHashData(phHash, pbInput, cbInput, 0);
      CharCount = v11 | 0x10000000;
      if ( v11 >= 0 )
      {
        v12 = BCryptHashData(phHash, (PUCHAR)"258EAFA5-E914-47DA-95CA-C5AB0DC85B11", 0x24u, 0);
        CharCount = v12 | 0x10000000;
        if ( v12 >= 0 )
        {
          v13 = BCryptFinishHash(phHash, pbOutput, 0x14u, 0);
          CharCount = v13 | 0x10000000;
          if ( v13 >= 0 )
          {
            CharCount = Base64Encoding::GetCharCount(0x14u, v16);
            if ( CharCount >= 0 )
            {
              v14 = (unsigned __int8 *)operator new(v16[0]);
              if ( v14 )
              {
                CharCount = Base64Encoding::GetChars(pbOutput, 0x14u, v14, v16[0], v16);
                if ( CharCount < 0 )
                {
                  HeapFree(g_hWxProcessHeap, 0, v14);
                }
                else
                {
                  *a4 = v16[0];
                  *a3 = (char *)v14;
                }
              }
              else
              {
                CharCount = -2147024882;
              }
            }
          }
        }
      }
    }
  }
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)CharCount;
}

```

## disassembly

```asm
0x180134af8  push    rbp
0x180134afa  push    rbx
0x180134afb  push    rsi
0x180134afc  push    rdi
0x180134afd  push    r13
0x180134aff  push    r14
0x180134b01  push    r15
0x180134b03  mov     rbp, rsp
0x180134b06  sub     rsp, 80h
0x180134b0d  mov     rax, cs:__security_cookie
0x180134b14  xor     rax, rsp
0x180134b17  mov     [rbp+var_10], rax
0x180134b1b  mov     r15, r9
0x180134b1e  mov     [rbp+phAlgorithm], 0
0x180134b26  mov     r14, r8
0x180134b29  mov     [rbp+phHash], 0
0x180134b31  mov     esi, edx
0x180134b33  mov     [rbp+var_40], 0
0x180134b3a  mov     rdi, rcx
0x180134b3d  lea     rdx, pszAlgId; "SHA1"
0x180134b44  xor     r9d, r9d; dwFlags
0x180134b47  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180134b4b  xor     r8d, r8d; pszImplementation
0x180134b4e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180134b54  mov     ebx, eax
0x180134b56  mov     r13d, 10000000h
0x180134b5c  or      ebx, r13d
0x180134b5f  jl      loc_180134C63
0x180134b65  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180134b69  lea     rdx, [rbp+phHash]; phHash
0x180134b6d  mov     [rsp+80h+dwFlags], 0; dwFlags
0x180134b75  xor     r9d, r9d; cbHashObject
0x180134b78  mov     [rsp+80h+cbSecret], 0; cbSecret
0x180134b80  xor     r8d, r8d; pbHashObject
0x180134b83  mov     [rsp+80h+pbSecret], 0; pbSecret
0x180134b8c  call    cs:__imp_BCryptCreateHash
0x180134b92  mov     ebx, eax
0x180134b94  or      ebx, r13d
0x180134b97  jl      loc_180134C63
0x180134b9d  mov     rcx, [rbp+phHash]; hHash
0x180134ba1  xor     r9d, r9d; dwFlags
0x180134ba4  mov     r8d, esi; cbInput
0x180134ba7  mov     rdx, rdi; pbInput
0x180134baa  call    cs:__imp_BCryptHashData
0x180134bb0  mov     ebx, eax
0x180134bb2  or      ebx, r13d
0x180134bb5  jl      loc_180134C63
0x180134bbb  mov     rcx, [rbp+phHash]; hHash
0x180134bbf  lea     rdx, pbInput; "258EAFA5-E914-47DA-95CA-C5AB0DC85B11"
0x180134bc6  xor     r9d, r9d; dwFlags
0x180134bc9  lea     r8d, [r9+24h]; cbInput
0x180134bcd  call    cs:__imp_BCryptHashData
0x180134bd3  mov     ebx, eax
0x180134bd5  or      ebx, r13d
0x180134bd8  jl      loc_180134C63
0x180134bde  mov     rcx, [rbp+phHash]; hHash
0x180134be2  lea     rdx, [rbp+pbOutput]; pbOutput
0x180134be6  xor     r9d, r9d; dwFlags
0x180134be9  lea     esi, [r9+14h]
0x180134bed  mov     r8d, esi; cbOutput
0x180134bf0  call    cs:__imp_BCryptFinishHash
0x180134bf6  mov     ebx, eax
0x180134bf8  or      ebx, r13d
0x180134bfb  jl      short loc_180134C63
0x180134bfd  lea     rdx, [rbp+var_40]; unsigned int *
0x180134c01  mov     ecx, esi; unsigned int
0x180134c03  call    ?GetCharCount@Base64Encoding@@SAJKPEAK@Z; Base64Encoding::GetCharCount(ulong,ulong *)
0x180134c08  mov     ebx, eax
0x180134c0a  test    eax, eax
0x180134c0c  js      short loc_180134C63
0x180134c0e  mov     ecx, [rbp+var_40]; unsigned __int64
0x180134c11  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180134c16  mov     rdi, rax
0x180134c19  test    rax, rax
0x180134c1c  jnz     short loc_180134C25
0x180134c1e  mov     ebx, 8007000Eh
0x180134c23  jmp     short loc_180134C63
0x180134c25  mov     r9d, [rbp+var_40]; unsigned int
0x180134c29  lea     rax, [rbp+var_40]
0x180134c2d  mov     r8, rdi; unsigned __int8 *
0x180134c30  mov     [rsp+80h+pbSecret], rax; unsigned int *
0x180134c35  mov     edx, esi; unsigned int
0x180134c37  lea     rcx, [rbp+pbOutput]; unsigned __int8 *
0x180134c3b  call    ?GetChars@Base64Encoding@@SAJPEBEKPEAEKPEAK@Z; Base64Encoding::GetChars(uchar const *,ulong,uchar *,ulong,ulong *)
0x180134c40  mov     ebx, eax
0x180134c42  test    eax, eax
0x180134c44  js      short loc_180134C51
0x180134c46  mov     eax, [rbp+var_40]
0x180134c49  mov     [r15], eax
0x180134c4c  mov     [r14], rdi
0x180134c4f  jmp     short loc_180134C63
0x180134c51  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180134c58  mov     r8, rdi; lpMem
0x180134c5b  xor     edx, edx; dwFlags
0x180134c5d  call    cs:__imp_HeapFree
0x180134c63  mov     rcx, [rbp+phHash]; hHash
0x180134c67  test    rcx, rcx
0x180134c6a  jz      short loc_180134C7A
0x180134c6c  call    cs:__imp_BCryptDestroyHash
0x180134c72  mov     [rbp+phHash], 0
0x180134c7a  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180134c7e  test    rcx, rcx
0x180134c81  jz      short loc_180134C8B
0x180134c83  xor     edx, edx; dwFlags
0x180134c85  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180134c8b  mov     eax, ebx
0x180134c8d  mov     rcx, [rbp+var_10]
0x180134c91  xor     rcx, rsp; StackCookie
0x180134c94  call    __security_check_cookie
0x180134c99  add     rsp, 80h
0x180134ca0  pop     r15
0x180134ca2  pop     r14
0x180134ca4  pop     r13
0x180134ca6  pop     rdi
0x180134ca7  pop     rsi
0x180134ca8  pop     rbx
0x180134ca9  pop     rbp
0x180134caa  retn
```
