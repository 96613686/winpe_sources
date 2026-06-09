# WkstGenerateHMACWithSHA512

- ea: `0x180032748`
- end: `0x18003293c`
- name: `WkstGenerateHMACWithSHA512`
- size: `500`
- prototype: `__int64 __usercall@<rax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, ULONG cbInput, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180032430`

## callees

- `0x180032748`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800327e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003284f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800327e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003284f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032906`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032915`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032906`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032915`
- `bcrypt!BCryptHashData` at `0x1800328a8`
- `bcrypt!BCryptHashData` at `0x1800328a8`
- `bcrypt!BCryptFinishHash` at `0x1800328c8`
- `bcrypt!BCryptFinishHash` at `0x1800328c8`
- `bcrypt!BCryptCreateHash` at `0x180032887`
- `bcrypt!BCryptCreateHash` at `0x180032887`
- `bcrypt!BCryptDestroyHash` at `0x1800328f7`
- `bcrypt!BCryptDestroyHash` at `0x1800328f7`
- `bcrypt!BCryptGetProperty` at `0x1800327c2`
- `bcrypt!BCryptGetProperty` at `0x180032827`
- `bcrypt!BCryptGetProperty` at `0x1800327c2`
- `bcrypt!BCryptGetProperty` at `0x180032827`

## pseudocode

```c
__int64 __fastcall WkstGenerateHMACWithSHA512(
        BCRYPT_ALG_HANDLE hAlgorithm,
        UCHAR *a2,
        ULONG a3,
        UCHAR *a4,
        ULONG cbInput,
        UCHAR **a6,
        _DWORD *a7)
{
  UCHAR *v9; // rsi
  UCHAR *v10; // rdi
  NTSTATUS Property; // ebx
  int v12; // eax
  ULONG pcbResult; // [rsp+40h] [rbp-20h] BYREF
  UCHAR v15[4]; // [rsp+44h] [rbp-1Ch] BYREF
  UCHAR pbOutput[4]; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF

  phHash = 0;
  v9 = 0;
  *(_DWORD *)pbOutput = 0;
  v10 = 0;
  *a6 = 0;
  *a7 = 0;
  *(_DWORD *)v15 = 0;
  pcbResult = 0;
  if ( !cbInput || !a3 )
    goto LABEL_14;
  Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_15;
  if ( pcbResult != 4 )
    goto LABEL_14;
  v9 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)pbOutput);
  if ( !v9 )
  {
LABEL_6:
    Property = -1073741670;
    goto LABEL_15;
  }
  Property = BCryptGetProperty(hAlgorithm, L"HashDigestLength", v15, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    if ( pcbResult == 4 )
    {
      v10 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)v15);
      if ( !v10 )
        goto LABEL_6;
      Property = BCryptCreateHash(hAlgorithm, &phHash, v9, *(ULONG *)pbOutput, a2, a3, 0);
      if ( Property >= 0 )
      {
        Property = BCryptHashData(phHash, a4, cbInput, 0);
        if ( Property >= 0 )
        {
          Property = BCryptFinishHash(phHash, v10, *(ULONG *)v15, 0);
          if ( Property >= 0 )
          {
            v12 = *(_DWORD *)v15;
            *a6 = v10;
            v10 = 0;
            *a7 = v12;
          }
        }
      }
      goto LABEL_15;
    }
LABEL_14:
    Property = -1073741811;
  }
LABEL_15:
  if ( phHash )
    BCryptDestroyHash(phHash);
  LocalFree(v9);
  LocalFree(v10);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180032748  mov     rax, rsp
0x18003274b  mov     [rax+8], rbx
0x18003274f  mov     [rax+20h], r9
0x180032753  mov     [rax+10h], rdx
0x180032757  push    rbp
0x180032758  push    rsi
0x180032759  push    rdi
0x18003275a  push    r12
0x18003275c  push    r13
0x18003275e  push    r14
0x180032760  push    r15
0x180032762  mov     rbp, rsp
0x180032765  sub     rsp, 60h
0x180032769  mov     r12, [rbp+arg_28]
0x18003276d  mov     r15, rcx
0x180032770  mov     r13, [rbp+arg_30]
0x180032774  xor     ecx, ecx
0x180032776  mov     r14d, r8d
0x180032779  mov     [rbp+phHash], rcx
0x18003277d  mov     esi, ecx
0x18003277f  mov     dword ptr [rbp+pbOutput], ecx
0x180032782  mov     edi, ecx
0x180032784  mov     [r12], rcx
0x180032788  mov     [r13+0], ecx
0x18003278c  mov     dword ptr [rbp+var_1C], ecx
0x18003278f  mov     [rbp+var_20], ecx
0x180032792  cmp     [rbp+cbInput], ecx
0x180032795  jz      loc_1800328E9
0x18003279b  test    r8d, r8d
0x18003279e  jz      loc_1800328E9
0x1800327a4  mov     [rax-70h], ecx
0x1800327a7  lea     r9d, [rcx+4]; cbOutput
0x1800327ab  lea     rax, [rbp+var_20]
0x1800327af  mov     rcx, r15; hObject
0x1800327b2  lea     r8, [rbp+pbOutput]; pbOutput
0x1800327b6  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1800327bb  lea     rdx, aObjectlength; "ObjectLength"
0x1800327c2  call    cs:__imp_BCryptGetProperty
0x1800327c9  nop     dword ptr [rax+rax+00h]
0x1800327ce  mov     ebx, eax
0x1800327d0  test    eax, eax
0x1800327d2  js      loc_1800328EE
0x1800327d8  cmp     [rbp+var_20], 4
0x1800327dc  jnz     loc_1800328E9
0x1800327e2  mov     edx, dword ptr [rbp+pbOutput]; uBytes
0x1800327e5  lea     ecx, [rdi+40h]; uFlags
0x1800327e8  call    cs:__imp_LocalAlloc
0x1800327ef  nop     dword ptr [rax+rax+00h]
0x1800327f4  mov     rsi, rax
0x1800327f7  test    rax, rax
0x1800327fa  jnz     short loc_180032806
0x1800327fc  mov     ebx, 0C000009Ah
0x180032801  jmp     loc_1800328EE
0x180032806  lea     rax, [rbp+var_20]
0x18003280a  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18003280e  mov     r9d, 4; cbOutput
0x180032814  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180032819  lea     r8, [rbp+var_1C]; pbOutput
0x18003281d  mov     rcx, r15; hObject
0x180032820  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180032827  call    cs:__imp_BCryptGetProperty
0x18003282e  nop     dword ptr [rax+rax+00h]
0x180032833  mov     ebx, eax
0x180032835  test    eax, eax
0x180032837  js      loc_1800328EE
0x18003283d  cmp     [rbp+var_20], 4
0x180032841  jnz     loc_1800328E9
0x180032847  mov     edx, dword ptr [rbp+var_1C]; uBytes
0x18003284a  mov     ecx, 40h ; '@'; uFlags
0x18003284f  call    cs:__imp_LocalAlloc
0x180032856  nop     dword ptr [rax+rax+00h]
0x18003285b  mov     rdi, rax
0x18003285e  test    rax, rax
0x180032861  jz      short loc_1800327FC
0x180032863  mov     rax, [rbp+pbSecret]
0x180032867  lea     rdx, [rbp+phHash]; phHash
0x18003286b  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x18003286f  mov     r8, rsi; pbHashObject
0x180032872  mov     [rsp+60h+var_30], 0; dwFlags
0x18003287a  mov     rcx, r15; hAlgorithm
0x18003287d  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x180032882  mov     [rsp+60h+pcbResult], rax; pbSecret
0x180032887  call    cs:__imp_BCryptCreateHash
0x18003288e  nop     dword ptr [rax+rax+00h]
0x180032893  mov     ebx, eax
0x180032895  test    eax, eax
0x180032897  js      short loc_1800328EE
0x180032899  mov     r8d, [rbp+cbInput]; cbInput
0x18003289d  xor     r9d, r9d; dwFlags
0x1800328a0  mov     rdx, [rbp+pbInput]; pbInput
0x1800328a4  mov     rcx, [rbp+phHash]; hHash
0x1800328a8  call    cs:__imp_BCryptHashData
0x1800328af  nop     dword ptr [rax+rax+00h]
0x1800328b4  mov     ebx, eax
0x1800328b6  test    eax, eax
0x1800328b8  js      short loc_1800328EE
0x1800328ba  mov     r8d, dword ptr [rbp+var_1C]; cbOutput
0x1800328be  xor     r9d, r9d; dwFlags
0x1800328c1  mov     rcx, [rbp+phHash]; hHash
0x1800328c5  mov     rdx, rdi; pbOutput
0x1800328c8  call    cs:__imp_BCryptFinishHash
0x1800328cf  nop     dword ptr [rax+rax+00h]
0x1800328d4  mov     ebx, eax
0x1800328d6  test    eax, eax
0x1800328d8  js      short loc_1800328EE
0x1800328da  mov     eax, dword ptr [rbp+var_1C]
0x1800328dd  mov     [r12], rdi
0x1800328e1  xor     edi, edi
0x1800328e3  mov     [r13+0], eax
0x1800328e7  jmp     short loc_1800328EE
0x1800328e9  mov     ebx, 0C000000Dh
0x1800328ee  mov     rcx, [rbp+phHash]; hHash
0x1800328f2  test    rcx, rcx
0x1800328f5  jz      short loc_180032903
0x1800328f7  call    cs:__imp_BCryptDestroyHash
0x1800328fe  nop     dword ptr [rax+rax+00h]
0x180032903  mov     rcx, rsi; hMem
0x180032906  call    cs:__imp_LocalFree
0x18003290d  nop     dword ptr [rax+rax+00h]
0x180032912  mov     rcx, rdi; hMem
0x180032915  call    cs:__imp_LocalFree
0x18003291c  nop     dword ptr [rax+rax+00h]
0x180032921  mov     eax, ebx
0x180032923  mov     rbx, [rsp+60h+arg_0]
0x18003292b  add     rsp, 60h
0x18003292f  pop     r15
0x180032931  pop     r14
0x180032933  pop     r13
0x180032935  pop     r12
0x180032937  pop     rdi
0x180032938  pop     rsi
0x180032939  pop     rbp
0x18003293a  retn
```
