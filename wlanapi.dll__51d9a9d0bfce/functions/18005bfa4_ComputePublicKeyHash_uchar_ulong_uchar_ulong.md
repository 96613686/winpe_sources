# ComputePublicKeyHash(uchar *,ulong,uchar *,ulong)

- ea: `0x18005bfa4`
- end: `0x18005c2ee`
- name: `?ComputePublicKeyHash@@YAJPEAEK0K@Z`
- size: `842`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, ULONG cbOutput)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005c2f4`

## callees

- `0x180005330`
- `0x180005610`
- `0x1800063a0`
- `0x180006934`
- `0x18005bfa4`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18005c2ca`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18005c2ca`
- `bcrypt!BCryptCreateHash` at `0x18005c1cb`
- `bcrypt!BCryptCreateHash` at `0x18005c1cb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005bffa`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005bffa`
- `bcrypt!BCryptHashData` at `0x18005c220`
- `bcrypt!BCryptHashData` at `0x18005c220`
- `bcrypt!BCryptGetProperty` at `0x18005c062`
- `bcrypt!BCryptGetProperty` at `0x18005c10f`
- `bcrypt!BCryptGetProperty` at `0x18005c062`
- `bcrypt!BCryptGetProperty` at `0x18005c10f`
- `bcrypt!BCryptFinishHash` at `0x18005c269`
- `bcrypt!BCryptFinishHash` at `0x18005c269`
- `bcrypt!BCryptDestroyHash` at `0x18005c2b9`
- `bcrypt!BCryptDestroyHash` at `0x18005c2b9`

## pseudocode

```c
__int64 __fastcall ComputePublicKeyHash(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, ULONG cbOutput)
{
  UCHAR *v8; // rdi
  unsigned int Property; // ebx
  union DOT11_OUI_HEADER *v10; // rcx
  __int64 v11; // rdx
  UCHAR *Memory; // rax
  UCHAR v14[4]; // [rsp+40h] [rbp-20h] BYREF
  UCHAR pbOutputa[4]; // [rsp+44h] [rbp-1Ch] BYREF
  ULONG pcbResult; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-10h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-8h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  pcbResult = 0;
  *(_DWORD *)pbOutputa = 0;
  *(_DWORD *)v14 = 0;
  v8 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( (Property & 0xC0000000) == 0xC0000000 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      v11 = 10;
LABEL_43:
      WPP_SF_d(*((_QWORD *)v10 + 12), v11, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids, Property);
    }
  }
  else
  {
    Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutputa, 4u, &pcbResult, 0);
    if ( (Property & 0xC0000000) == 0xC0000000 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        v11 = 11;
        goto LABEL_43;
      }
    }
    else if ( cbOutput == *(_DWORD *)pbOutputa )
    {
      Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", v14, 4u, &pcbResult, 0);
      if ( (Property & 0xC0000000) == 0xC0000000 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
        {
          v11 = 13;
          goto LABEL_43;
        }
      }
      else
      {
        Memory = (UCHAR *)WlanAllocateMemory(*(DWORD *)v14);
        v8 = Memory;
        if ( Memory )
        {
          Property = BCryptCreateHash(phAlgorithm, &phHash, Memory, *(ULONG *)v14, 0, 0, 0);
          if ( (Property & 0xC0000000) == 0xC0000000 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105)
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
            {
              v11 = 15;
              goto LABEL_43;
            }
          }
          else
          {
            Property = BCryptHashData(phHash, pbInput, cbInput, 0);
            if ( (Property & 0xC0000000) == 0xC0000000 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 105)
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
              {
                v11 = 16;
                goto LABEL_43;
              }
            }
            else
            {
              Property = BCryptFinishHash(phHash, pbOutput, cbOutput, 0);
              if ( (Property & 0xC0000000) == 0xC0000000 )
              {
                v10 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
                  && *((_BYTE *)WPP_GLOBAL_Control + 105)
                  && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
                {
                  v11 = 17;
                  goto LABEL_43;
                }
              }
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105)
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids);
          }
          Property = -1073741801;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids);
      }
      Property = -1073741811;
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v8 )
    FreeWLMem(v8);
  return Property;
}

```

## disassembly

```asm
0x18005bfa4  push    rbp
0x18005bfa6  push    rbx
0x18005bfa7  push    rsi
0x18005bfa8  push    rdi
0x18005bfa9  push    r12
0x18005bfab  push    r14
0x18005bfad  push    r15
0x18005bfaf  mov     rbp, rsp
0x18005bfb2  sub     rsp, 60h
0x18005bfb6  mov     esi, r9d
0x18005bfb9  mov     [rbp+phAlgorithm], 0
0x18005bfc1  mov     r14, r8
0x18005bfc4  mov     [rbp+phHash], 0
0x18005bfcc  mov     r15d, edx
0x18005bfcf  mov     [rbp+var_18], 0
0x18005bfd6  mov     r12, rcx
0x18005bfd9  mov     dword ptr [rbp+pbOutput], 0
0x18005bfe0  xor     r9d, r9d; dwFlags
0x18005bfe3  mov     dword ptr [rbp+var_20], 0
0x18005bfea  xor     r8d, r8d; pszImplementation
0x18005bfed  lea     rdx, pszAlgId; "SHA256"
0x18005bff4  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18005bff8  xor     edi, edi
0x18005bffa  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18005c000  mov     ecx, 0C0000000h
0x18005c005  mov     ebx, eax
0x18005c007  and     eax, ecx
0x18005c009  cmp     eax, ecx
0x18005c00b  jnz     short loc_18005C040
0x18005c00d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c014  lea     rax, WPP_GLOBAL_Control
0x18005c01b  cmp     rcx, rax
0x18005c01e  jz      loc_18005C2B0
0x18005c024  cmp     byte ptr [rcx+69h], 1
0x18005c028  jb      loc_18005C2B0
0x18005c02e  test    byte ptr [rcx+6Ch], 2
0x18005c032  jz      loc_18005C2B0
0x18005c038  lea     edx, [rdi+0Ah]
0x18005c03b  jmp     loc_18005C29D
0x18005c040  mov     rcx, [rbp+phAlgorithm]; hObject
0x18005c044  lea     rax, [rbp+var_18]
0x18005c048  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18005c04c  lea     r8, [rbp+pbOutput]; pbOutput
0x18005c050  mov     r9d, 4; cbOutput
0x18005c056  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18005c05b  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18005c062  call    cs:__imp_BCryptGetProperty
0x18005c068  mov     ecx, 0C0000000h
0x18005c06d  mov     ebx, eax
0x18005c06f  and     eax, ecx
0x18005c071  cmp     eax, ecx
0x18005c073  jnz     short loc_18005C0AA
0x18005c075  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c07c  lea     rax, WPP_GLOBAL_Control
0x18005c083  cmp     rcx, rax
0x18005c086  jz      loc_18005C2B0
0x18005c08c  cmp     byte ptr [rcx+69h], 1
0x18005c090  jb      loc_18005C2B0
0x18005c096  test    byte ptr [rcx+6Ch], 2
0x18005c09a  jz      loc_18005C2B0
0x18005c0a0  mov     edx, 0Bh
0x18005c0a5  jmp     loc_18005C29D
0x18005c0aa  cmp     esi, dword ptr [rbp+pbOutput]
0x18005c0ad  jz      short loc_18005C0ED
0x18005c0af  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c0b6  lea     rax, WPP_GLOBAL_Control
0x18005c0bd  cmp     rcx, rax
0x18005c0c0  jz      short loc_18005C0E3
0x18005c0c2  cmp     byte ptr [rcx+69h], 1
0x18005c0c6  jb      short loc_18005C0E3
0x18005c0c8  test    byte ptr [rcx+6Ch], 2
0x18005c0cc  jz      short loc_18005C0E3
0x18005c0ce  mov     rcx, [rcx+60h]
0x18005c0d2  lea     r8, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids
0x18005c0d9  mov     edx, 0Ch
0x18005c0de  call    WPP_SF_
0x18005c0e3  mov     ebx, 0C000000Dh
0x18005c0e8  jmp     loc_18005C2B0
0x18005c0ed  mov     rcx, [rbp+phAlgorithm]; hObject
0x18005c0f1  lea     rax, [rbp+var_18]
0x18005c0f5  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18005c0f9  lea     r8, [rbp+var_20]; pbOutput
0x18005c0fd  mov     r9d, 4; cbOutput
0x18005c103  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18005c108  lea     rdx, pszProperty; "ObjectLength"
0x18005c10f  call    cs:__imp_BCryptGetProperty
0x18005c115  mov     ecx, 0C0000000h
0x18005c11a  mov     ebx, eax
0x18005c11c  and     eax, ecx
0x18005c11e  cmp     eax, ecx
0x18005c120  jnz     short loc_18005C157
0x18005c122  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c129  lea     rax, WPP_GLOBAL_Control
0x18005c130  cmp     rcx, rax
0x18005c133  jz      loc_18005C2B0
0x18005c139  cmp     byte ptr [rcx+69h], 1
0x18005c13d  jb      loc_18005C2B0
0x18005c143  test    byte ptr [rcx+6Ch], 2
0x18005c147  jz      loc_18005C2B0
0x18005c14d  mov     edx, 0Dh
0x18005c152  jmp     loc_18005C29D
0x18005c157  mov     ecx, dword ptr [rbp+var_20]; dwMemorySize
0x18005c15a  call    WlanAllocateMemory
0x18005c15f  mov     rdi, rax
0x18005c162  test    rax, rax
0x18005c165  jnz     short loc_18005C1A3
0x18005c167  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c16e  lea     rax, WPP_GLOBAL_Control
0x18005c175  cmp     rcx, rax
0x18005c178  jz      short loc_18005C199
0x18005c17a  cmp     byte ptr [rcx+69h], 1
0x18005c17e  jb      short loc_18005C199
0x18005c180  test    byte ptr [rcx+6Ch], 2
0x18005c184  jz      short loc_18005C199
0x18005c186  mov     rcx, [rcx+60h]
0x18005c18a  lea     edx, [rdi+0Eh]
0x18005c18d  lea     r8, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids
0x18005c194  call    WPP_SF_
0x18005c199  mov     ebx, 0C0000017h
0x18005c19e  jmp     loc_18005C2B0
0x18005c1a3  mov     r9d, dword ptr [rbp+var_20]; cbHashObject
0x18005c1a7  lea     rdx, [rbp+phHash]; phHash
0x18005c1ab  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18005c1af  mov     r8, rax; pbHashObject
0x18005c1b2  mov     [rsp+60h+var_30], 0; dwFlags
0x18005c1ba  mov     [rsp+60h+dwFlags], 0; cbSecret
0x18005c1c2  mov     [rsp+60h+pcbResult], 0; pbSecret
0x18005c1cb  call    cs:__imp_BCryptCreateHash
0x18005c1d1  mov     ecx, 0C0000000h
0x18005c1d6  mov     ebx, eax
0x18005c1d8  and     eax, ecx
0x18005c1da  cmp     eax, ecx
0x18005c1dc  jnz     short loc_18005C213
0x18005c1de  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c1e5  lea     rax, WPP_GLOBAL_Control
0x18005c1ec  cmp     rcx, rax
0x18005c1ef  jz      loc_18005C2B0
0x18005c1f5  cmp     byte ptr [rcx+69h], 1
0x18005c1f9  jb      loc_18005C2B0
0x18005c1ff  test    byte ptr [rcx+6Ch], 2
0x18005c203  jz      loc_18005C2B0
0x18005c209  mov     edx, 0Fh
0x18005c20e  jmp     loc_18005C29D
0x18005c213  mov     rcx, [rbp+phHash]; hHash
0x18005c217  xor     r9d, r9d; dwFlags
0x18005c21a  mov     r8d, r15d; cbInput
0x18005c21d  mov     rdx, r12; pbInput
0x18005c220  call    cs:__imp_BCryptHashData
0x18005c226  mov     r15d, 0C0000000h
0x18005c22c  mov     ebx, eax
0x18005c22e  and     eax, r15d
0x18005c231  cmp     eax, r15d
0x18005c234  jnz     short loc_18005C25C
0x18005c236  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c23d  lea     rax, WPP_GLOBAL_Control
0x18005c244  cmp     rcx, rax
0x18005c247  jz      short loc_18005C2B0
0x18005c249  cmp     byte ptr [rcx+69h], 1
0x18005c24d  jb      short loc_18005C2B0
0x18005c24f  test    byte ptr [rcx+6Ch], 2
0x18005c253  jz      short loc_18005C2B0
0x18005c255  mov     edx, 10h
0x18005c25a  jmp     short loc_18005C29D
0x18005c25c  mov     rcx, [rbp+phHash]; hHash
0x18005c260  xor     r9d, r9d; dwFlags
0x18005c263  mov     r8d, esi; cbOutput
0x18005c266  mov     rdx, r14; pbOutput
0x18005c269  call    cs:__imp_BCryptFinishHash
0x18005c26f  mov     ebx, eax
0x18005c271  and     eax, r15d
0x18005c274  cmp     eax, r15d
0x18005c277  jnz     short loc_18005C2B0
0x18005c279  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c280  lea     rax, WPP_GLOBAL_Control
0x18005c287  cmp     rcx, rax
0x18005c28a  jz      short loc_18005C2B0
0x18005c28c  cmp     byte ptr [rcx+69h], 1
0x18005c290  jb      short loc_18005C2B0
0x18005c292  test    byte ptr [rcx+6Ch], 2
0x18005c296  jz      short loc_18005C2B0
0x18005c298  mov     edx, 11h
0x18005c29d  mov     rcx, [rcx+60h]
0x18005c2a1  lea     r8, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids
0x18005c2a8  mov     r9d, ebx
0x18005c2ab  call    WPP_SF_d
0x18005c2b0  mov     rcx, [rbp+phHash]; hHash
0x18005c2b4  test    rcx, rcx
0x18005c2b7  jz      short loc_18005C2BF
0x18005c2b9  call    cs:__imp_BCryptDestroyHash
0x18005c2bf  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18005c2c3  test    rcx, rcx
0x18005c2c6  jz      short loc_18005C2D0
0x18005c2c8  xor     edx, edx; dwFlags
0x18005c2ca  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18005c2d0  test    rdi, rdi
0x18005c2d3  jz      short loc_18005C2DD
0x18005c2d5  mov     rcx, rdi
0x18005c2d8  call    FreeWLMem
0x18005c2dd  mov     eax, ebx
0x18005c2df  add     rsp, 60h
0x18005c2e3  pop     r15
0x18005c2e5  pop     r14
0x18005c2e7  pop     r12
0x18005c2e9  pop     rdi
0x18005c2ea  pop     rsi
0x18005c2eb  pop     rbx
0x18005c2ec  pop     rbp
0x18005c2ed  retn
```
