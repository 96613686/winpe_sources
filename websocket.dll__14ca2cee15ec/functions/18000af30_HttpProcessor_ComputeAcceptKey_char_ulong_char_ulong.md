# HttpProcessor::ComputeAcceptKey(char *,ulong,char * *,ulong *)

- ea: `0x18000af30`
- end: `0x18000b0c1`
- name: `?ComputeAcceptKey@HttpProcessor@@SAJPEADKPEAPEADPEAK@Z`
- size: `401`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, char **, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800097e0`
- `0x18000a8a0`

## callees

- `0x180001234`
- `0x180001274`
- `0x180001670`
- `0x18000af30`
- `0x18000d3b8`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000afdb`
- `bcrypt!BCryptHashData` at `0x18000affe`
- `bcrypt!BCryptHashData` at `0x18000afdb`
- `bcrypt!BCryptHashData` at `0x18000affe`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000b09b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000b09b`
- `bcrypt!BCryptFinishHash` at `0x18000b01d`
- `bcrypt!BCryptFinishHash` at `0x18000b01d`
- `bcrypt!BCryptDestroyHash` at `0x18000b082`
- `bcrypt!BCryptDestroyHash` at `0x18000b082`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000af7f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000af7f`
- `bcrypt!BCryptCreateHash` at `0x18000afbd`
- `bcrypt!BCryptCreateHash` at `0x18000afbd`

## pseudocode

```c
__int64 __fastcall HttpProcessor::ComputeAcceptKey(PUCHAR pbInput, ULONG cbInput, char **a3, unsigned int *a4)
{
  NTSTATUS v8; // eax
  int Chars; // ebx
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  NTSTATUS v13; // eax
  unsigned __int8 *v14; // rdi
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v17; // [rsp+48h] [rbp-38h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-30h] BYREF
  UCHAR pbOutput[24]; // [rsp+58h] [rbp-28h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", 0, 0);
  Chars = v8 | 0x10000000;
  if ( v8 >= 0 )
  {
    v10 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
    Chars = v10 | 0x10000000;
    if ( v10 >= 0 )
    {
      v11 = BCryptHashData(phHash, pbInput, cbInput, 0);
      Chars = v11 | 0x10000000;
      if ( v11 >= 0 )
      {
        v12 = BCryptHashData(phHash, (PUCHAR)"258EAFA5-E914-47DA-95CA-C5AB0DC85B11", 0x24u, 0);
        Chars = v12 | 0x10000000;
        if ( v12 >= 0 )
        {
          v13 = BCryptFinishHash(phHash, pbOutput, 0x14u, 0);
          Chars = v13 | 0x10000000;
          if ( v13 >= 0 )
          {
            v17 = 28;
            v14 = (unsigned __int8 *)operator new(0x1Cu);
            if ( v14 )
            {
              Chars = Base64Encoding::GetChars(pbOutput, 0x14u, v14, 0x1Cu, &v17);
              if ( Chars < 0 )
              {
                operator delete(v14);
              }
              else
              {
                *a4 = v17;
                *a3 = (char *)v14;
              }
            }
            else
            {
              Chars = -2147024882;
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
  return (unsigned int)Chars;
}

```

## disassembly

```asm
0x18000af30  push    rbp
0x18000af32  push    rbx
0x18000af33  push    rsi
0x18000af34  push    rdi
0x18000af35  push    r13
0x18000af37  push    r14
0x18000af39  push    r15
0x18000af3b  mov     rbp, rsp
0x18000af3e  sub     rsp, 80h
0x18000af45  mov     rax, cs:__security_cookie
0x18000af4c  xor     rax, rsp
0x18000af4f  mov     [rbp+var_10], rax
0x18000af53  mov     r15, r9
0x18000af56  mov     [rbp+phAlgorithm], 0
0x18000af5e  mov     r14, r8
0x18000af61  mov     [rbp+phHash], 0
0x18000af69  mov     esi, edx
0x18000af6b  mov     rdi, rcx
0x18000af6e  xor     r9d, r9d; dwFlags
0x18000af71  lea     rdx, pszAlgId; "SHA1"
0x18000af78  xor     r8d, r8d; pszImplementation
0x18000af7b  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18000af7f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000af85  mov     ebx, eax
0x18000af87  mov     r13d, 10000000h
0x18000af8d  or      ebx, r13d
0x18000af90  jl      loc_18000B079
0x18000af96  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000af9a  lea     rdx, [rbp+phHash]; phHash
0x18000af9e  mov     [rsp+80h+dwFlags], 0; dwFlags
0x18000afa6  xor     r9d, r9d; cbHashObject
0x18000afa9  mov     [rsp+80h+cbSecret], 0; cbSecret
0x18000afb1  xor     r8d, r8d; pbHashObject
0x18000afb4  mov     [rsp+80h+pbSecret], 0; pbSecret
0x18000afbd  call    cs:__imp_BCryptCreateHash
0x18000afc3  mov     ebx, eax
0x18000afc5  or      ebx, r13d
0x18000afc8  jl      loc_18000B079
0x18000afce  mov     rcx, [rbp+phHash]; hHash
0x18000afd2  xor     r9d, r9d; dwFlags
0x18000afd5  mov     r8d, esi; cbInput
0x18000afd8  mov     rdx, rdi; pbInput
0x18000afdb  call    cs:__imp_BCryptHashData
0x18000afe1  mov     ebx, eax
0x18000afe3  or      ebx, r13d
0x18000afe6  jl      loc_18000B079
0x18000afec  mov     rcx, [rbp+phHash]; hHash
0x18000aff0  lea     rdx, pbInput; "258EAFA5-E914-47DA-95CA-C5AB0DC85B11"
0x18000aff7  xor     r9d, r9d; dwFlags
0x18000affa  lea     r8d, [r9+24h]; cbInput
0x18000affe  call    cs:__imp_BCryptHashData
0x18000b004  mov     ebx, eax
0x18000b006  or      ebx, r13d
0x18000b009  jl      short loc_18000B079
0x18000b00b  mov     rcx, [rbp+phHash]; hHash
0x18000b00f  lea     rdx, [rbp+pbOutput]; pbOutput
0x18000b013  xor     r9d, r9d; dwFlags
0x18000b016  lea     esi, [r9+14h]
0x18000b01a  mov     r8d, esi; cbOutput
0x18000b01d  call    cs:__imp_BCryptFinishHash
0x18000b023  mov     ebx, eax
0x18000b025  or      ebx, r13d
0x18000b028  jl      short loc_18000B079
0x18000b02a  lea     ebx, [rsi+8]
0x18000b02d  mov     ecx, ebx; Size
0x18000b02f  mov     [rbp+var_38], ebx
0x18000b032  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b037  mov     rdi, rax
0x18000b03a  test    rax, rax
0x18000b03d  jnz     short loc_18000B046
0x18000b03f  mov     ebx, 8007000Eh
0x18000b044  jmp     short loc_18000B079
0x18000b046  lea     rax, [rbp+var_38]
0x18000b04a  mov     r9d, ebx; unsigned int
0x18000b04d  mov     r8, rdi; unsigned __int8 *
0x18000b050  mov     [rsp+80h+pbSecret], rax; unsigned int *
0x18000b055  mov     edx, esi; unsigned int
0x18000b057  lea     rcx, [rbp+pbOutput]; unsigned __int8 *
0x18000b05b  call    ?GetChars@Base64Encoding@@SAJPEBEKPEAEKPEAK@Z; Base64Encoding::GetChars(uchar const *,ulong,uchar *,ulong,ulong *)
0x18000b060  mov     ebx, eax
0x18000b062  test    eax, eax
0x18000b064  js      short loc_18000B071
0x18000b066  mov     ecx, [rbp+var_38]
0x18000b069  mov     [r15], ecx
0x18000b06c  mov     [r14], rdi
0x18000b06f  jmp     short loc_18000B079
0x18000b071  mov     rcx, rdi; Block
0x18000b074  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b079  mov     rcx, [rbp+phHash]; hHash
0x18000b07d  test    rcx, rcx
0x18000b080  jz      short loc_18000B090
0x18000b082  call    cs:__imp_BCryptDestroyHash
0x18000b088  mov     [rbp+phHash], 0
0x18000b090  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000b094  test    rcx, rcx
0x18000b097  jz      short loc_18000B0A1
0x18000b099  xor     edx, edx; dwFlags
0x18000b09b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000b0a1  mov     eax, ebx
0x18000b0a3  mov     rcx, [rbp+var_10]
0x18000b0a7  xor     rcx, rsp; StackCookie
0x18000b0aa  call    __security_check_cookie
0x18000b0af  add     rsp, 80h
0x18000b0b6  pop     r15
0x18000b0b8  pop     r14
0x18000b0ba  pop     r13
0x18000b0bc  pop     rdi
0x18000b0bd  pop     rsi
0x18000b0be  pop     rbx
0x18000b0bf  pop     rbp
0x18000b0c0  retn
```
