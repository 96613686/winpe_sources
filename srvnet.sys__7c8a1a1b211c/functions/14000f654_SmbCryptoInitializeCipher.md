# SmbCryptoInitializeCipher

- ea: `0x14000f654`
- end: `0x14000f779`
- name: `SmbCryptoInitializeCipher`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140041218`

## callees

- `0x14000f654`
- `0x14002a3e0`

## import_xrefs

- `ksecdd!BCryptSetProperty` at `0x14000f6c3`
- `ksecdd!BCryptSetProperty` at `0x14000f6c3`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000f694`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000f694`
- `ksecdd!BCryptGetProperty` at `0x14000f6fe`
- `ksecdd!BCryptGetProperty` at `0x14000f6fe`

## pseudocode

```c
NTSTATUS __fastcall SmbCryptoInitializeCipher(__int64 a1, __int64 a2, UCHAR *a3, __int64 a4, int a5, int a6)
{
  NTSTATUS result; // eax
  ULONG pcbResult; // [rsp+30h] [rbp-28h] BYREF
  UCHAR pbOutput[8]; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v11; // [rsp+40h] [rbp-18h]

  pcbResult = 0;
  *(_QWORD *)pbOutput = 0;
  v11 = 0;
  result = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)a1, L"AES", 0, 1u);
  if ( result >= 0 )
  {
    result = BCryptSetProperty(*(BCRYPT_HANDLE *)a1, L"ChainingMode", a3, 0x20u, 0);
    if ( result >= 0 )
    {
      result = BCryptGetProperty(*(BCRYPT_HANDLE *)a1, L"AuthTagLength", pbOutput, 0xCu, &pcbResult, 0);
      if ( result >= 0 )
      {
        if ( *(_DWORD *)pbOutput <= 0x10u )
        {
          if ( *(_DWORD *)&pbOutput[4] > 0x10u )
            *(_DWORD *)(a1 + 12) = 16 - (16 - (unsigned __int64)*(unsigned int *)pbOutput) % v11;
          else
            *(_DWORD *)(a1 + 12) = *(_DWORD *)&pbOutput[4];
          *(_DWORD *)(a1 + 8) = a5;
          *(_DWORD *)(a1 + 16) = a6;
          return 0;
        }
        else
        {
          return -1073741637;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000f654  mov     [rsp+arg_8], rbx
0x14000f659  push    rdi
0x14000f65a  sub     rsp, 50h
0x14000f65e  mov     rax, cs:__security_cookie
0x14000f665  xor     rax, rsp
0x14000f668  mov     [rsp+58h+var_10], rax
0x14000f66d  xor     eax, eax
0x14000f66f  mov     [rsp+58h+pcbResult], 0
0x14000f677  mov     rdi, r8
0x14000f67a  mov     qword ptr [rsp+58h+pbOutput], rax
0x14000f67f  xor     r8d, r8d; pszImplementation
0x14000f682  mov     [rsp+58h+var_18], eax
0x14000f686  lea     rdx, pszAlgId; "AES"
0x14000f68d  mov     rbx, rcx
0x14000f690  lea     r9d, [rax+1]; dwFlags
0x14000f694  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000f69b  nop     dword ptr [rax+rax+00h]
0x14000f6a0  test    eax, eax
0x14000f6a2  js      loc_14000F760
0x14000f6a8  mov     rcx, [rbx]; hObject
0x14000f6ab  lea     rdx, aChainingmode; "ChainingMode"
0x14000f6b2  mov     r9d, 20h ; ' '; cbInput
0x14000f6b8  mov     [rsp+58h+dwFlags], 0; dwFlags
0x14000f6c0  mov     r8, rdi; pbInput
0x14000f6c3  call    cs:__imp_BCryptSetProperty
0x14000f6ca  nop     dword ptr [rax+rax+00h]
0x14000f6cf  test    eax, eax
0x14000f6d1  js      loc_14000F760
0x14000f6d7  mov     rcx, [rbx]; hObject
0x14000f6da  lea     rax, [rsp+58h+pcbResult]
0x14000f6df  mov     [rsp+58h+var_30], 0; dwFlags
0x14000f6e7  lea     r8, [rsp+58h+pbOutput]; pbOutput
0x14000f6ec  mov     r9d, 0Ch; cbOutput
0x14000f6f2  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x14000f6f7  lea     rdx, aAuthtaglength; "AuthTagLength"
0x14000f6fe  call    cs:__imp_BCryptGetProperty
0x14000f705  nop     dword ptr [rax+rax+00h]
0x14000f70a  test    eax, eax
0x14000f70c  js      short loc_14000F760
0x14000f70e  mov     r8d, 10h
0x14000f714  cmp     dword ptr [rsp+58h+pbOutput], r8d
0x14000f719  jbe     short loc_14000F722
0x14000f71b  mov     eax, 0C00000BBh
0x14000f720  jmp     short loc_14000F760
0x14000f722  mov     eax, dword ptr [rsp+58h+pbOutput+4]
0x14000f726  cmp     eax, r8d
0x14000f729  ja      short loc_14000F730
0x14000f72b  mov     [rbx+0Ch], eax
0x14000f72e  jmp     short loc_14000F74A
0x14000f730  mov     ecx, dword ptr [rsp+58h+pbOutput]
0x14000f734  mov     rax, r8
0x14000f737  sub     rax, rcx
0x14000f73a  xor     edx, edx
0x14000f73c  mov     ecx, [rsp+58h+var_18]
0x14000f740  div     rcx
0x14000f743  sub     r8d, edx
0x14000f746  mov     [rbx+0Ch], r8d
0x14000f74a  mov     eax, [rsp+58h+arg_20]
0x14000f751  mov     [rbx+8], eax
0x14000f754  mov     eax, [rsp+58h+arg_28]
0x14000f75b  mov     [rbx+10h], eax
0x14000f75e  xor     eax, eax
0x14000f760  mov     rcx, [rsp+58h+var_10]
0x14000f765  xor     rcx, rsp; StackCookie
0x14000f768  call    __security_check_cookie
0x14000f76d  mov     rbx, [rsp+58h+arg_8]
0x14000f772  add     rsp, 50h
0x14000f776  pop     rdi
0x14000f777  retn
```
