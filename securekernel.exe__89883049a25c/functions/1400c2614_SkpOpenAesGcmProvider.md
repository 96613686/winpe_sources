# SkpOpenAesGcmProvider

- ea: `0x1400c2614`
- end: `0x1400c2701`
- name: `SkpOpenAesGcmProvider`
- size: `237`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400bfa88`
- `0x1400c2504`
- `0x1400c3b48`

## callees

- `0x1400c2614`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x1400c2641`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400c2641`
- `cng!BCryptSetProperty` at `0x1400c2676`
- `cng!BCryptSetProperty` at `0x1400c2676`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c26db`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c26db`
- `cng!BCryptGetProperty` at `0x1400c26b8`
- `cng!BCryptGetProperty` at `0x1400c26b8`

## pseudocode

```c
__int64 __fastcall SkpOpenAesGcmProvider(BCRYPT_ALG_HANDLE *a1)
{
  NTSTATUS Property; // ebx
  ULONG pcbResult; // [rsp+48h] [rbp+10h] BYREF
  ULONG pbOutput; // [rsp+50h] [rbp+18h] BYREF

  pbOutput = 0;
  pcbResult = 0;
  Property = BCryptOpenAlgorithmProvider(a1, L"AES", 0, 1u);
  if ( Property >= 0 )
  {
    Property = BCryptSetProperty(*a1, L"ChainingMode", (PUCHAR)L"ChainingModeGCM", 0x20u, 0);
    if ( Property < 0 )
    {
LABEL_7:
      BCryptCloseAlgorithmProvider(*a1, 0);
      return (unsigned int)Property;
    }
    if ( !ObjectLengthAesGcm )
    {
      Property = BCryptGetProperty(*a1, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
      if ( Property >= 0 )
      {
        if ( pcbResult == 4 )
        {
          ObjectLengthAesGcm = pbOutput;
          return (unsigned int)Property;
        }
        Property = -1073741595;
      }
      goto LABEL_7;
    }
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1400c2614  mov     [rsp+arg_0], rbx
0x1400c2619  push    rdi
0x1400c261a  sub     rsp, 30h
0x1400c261e  mov     r9d, 1; dwFlags
0x1400c2624  mov     [rsp+38h+pbOutput], 0
0x1400c262c  xor     r8d, r8d; pszImplementation
0x1400c262f  mov     [rsp+38h+pcbResult], 0
0x1400c2637  lea     rdx, aAes; "AES"
0x1400c263e  mov     rdi, rcx
0x1400c2641  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400c2648  nop     dword ptr [rax+rax+00h]
0x1400c264d  mov     ebx, eax
0x1400c264f  test    eax, eax
0x1400c2651  js      loc_1400C26E7
0x1400c2657  mov     rcx, [rdi]; hObject
0x1400c265a  lea     r8, pbInput; "ChainingModeGCM"
0x1400c2661  mov     r9d, 20h ; ' '; cbInput
0x1400c2667  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1400c266f  lea     rdx, aChainingmode; "ChainingMode"
0x1400c2676  call    cs:__imp_BCryptSetProperty
0x1400c267d  nop     dword ptr [rax+rax+00h]
0x1400c2682  mov     ebx, eax
0x1400c2684  test    eax, eax
0x1400c2686  js      short loc_1400C26D6
0x1400c2688  cmp     cs:ObjectLengthAesGcm, 0
0x1400c268f  jnz     short loc_1400C26E7
0x1400c2691  mov     rcx, [rdi]; hObject
0x1400c2694  lea     rax, [rsp+38h+pcbResult]
0x1400c2699  mov     [rsp+38h+var_10], 0; dwFlags
0x1400c26a1  lea     r8, [rsp+38h+pbOutput]; pbOutput
0x1400c26a6  mov     r9d, 4; cbOutput
0x1400c26ac  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x1400c26b1  lea     rdx, pszProperty; "ObjectLength"
0x1400c26b8  call    cs:__imp_BCryptGetProperty
0x1400c26bf  nop     dword ptr [rax+rax+00h]
0x1400c26c4  mov     ebx, eax
0x1400c26c6  test    eax, eax
0x1400c26c8  js      short loc_1400C26D6
0x1400c26ca  cmp     [rsp+38h+pcbResult], 4
0x1400c26cf  jz      short loc_1400C26F5
0x1400c26d1  mov     ebx, 0C00000E5h
0x1400c26d6  mov     rcx, [rdi]; hAlgorithm
0x1400c26d9  xor     edx, edx; dwFlags
0x1400c26db  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400c26e2  nop     dword ptr [rax+rax+00h]
0x1400c26e7  mov     eax, ebx
0x1400c26e9  mov     rbx, [rsp+38h+arg_0]
0x1400c26ee  add     rsp, 30h
0x1400c26f2  pop     rdi
0x1400c26f3  retn
0x1400c26f5  mov     eax, [rsp+38h+pbOutput]
0x1400c26f9  mov     cs:ObjectLengthAesGcm, eax
0x1400c26ff  jmp     short loc_1400C26E7
```
