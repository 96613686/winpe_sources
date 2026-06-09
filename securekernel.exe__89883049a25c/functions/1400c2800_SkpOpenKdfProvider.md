# SkpOpenKdfProvider

- ea: `0x1400c2800`
- end: `0x1400c28b8`
- name: `SkpOpenKdfProvider`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400bfa88`
- `0x1400c2504`

## callees

- `0x1400c2800`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x1400c282d`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400c282d`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c2892`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c2892`
- `cng!BCryptGetProperty` at `0x1400c286f`
- `cng!BCryptGetProperty` at `0x1400c286f`

## pseudocode

```c
__int64 __fastcall SkpOpenKdfProvider(BCRYPT_ALG_HANDLE *a1)
{
  NTSTATUS Property; // ebx
  ULONG pcbResult; // [rsp+48h] [rbp+10h] BYREF
  ULONG pbOutput; // [rsp+50h] [rbp+18h] BYREF

  pbOutput = 0;
  pcbResult = 0;
  Property = BCryptOpenAlgorithmProvider(a1, L"SP800_108_CTR_HMAC", 0, 1u);
  if ( Property >= 0 && !ObjectLengthSP800108 )
  {
    Property = BCryptGetProperty(*a1, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      if ( pcbResult == 4 )
      {
        ObjectLengthSP800108 = pbOutput;
        return (unsigned int)Property;
      }
      Property = -1073741595;
    }
    BCryptCloseAlgorithmProvider(*a1, 0);
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1400c2800  mov     [rsp+arg_0], rbx
0x1400c2805  push    rdi
0x1400c2806  sub     rsp, 30h
0x1400c280a  mov     r9d, 1; dwFlags
0x1400c2810  mov     [rsp+38h+pbOutput], 0
0x1400c2818  xor     r8d, r8d; pszImplementation
0x1400c281b  mov     [rsp+38h+arg_8], 0
0x1400c2823  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x1400c282a  mov     rdi, rcx
0x1400c282d  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400c2834  nop     dword ptr [rax+rax+00h]
0x1400c2839  mov     ebx, eax
0x1400c283b  test    eax, eax
0x1400c283d  js      short loc_1400C289E
0x1400c283f  cmp     cs:ObjectLengthSP800108, 0
0x1400c2846  jnz     short loc_1400C289E
0x1400c2848  mov     rcx, [rdi]; hObject
0x1400c284b  lea     rax, [rsp+38h+arg_8]
0x1400c2850  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1400c2858  lea     r8, [rsp+38h+pbOutput]; pbOutput
0x1400c285d  mov     r9d, 4; cbOutput
0x1400c2863  mov     [rsp+38h+pcbResult], rax; pcbResult
0x1400c2868  lea     rdx, pszProperty; "ObjectLength"
0x1400c286f  call    cs:__imp_BCryptGetProperty
0x1400c2876  nop     dword ptr [rax+rax+00h]
0x1400c287b  mov     ebx, eax
0x1400c287d  test    eax, eax
0x1400c287f  js      short loc_1400C288D
0x1400c2881  cmp     [rsp+38h+arg_8], 4
0x1400c2886  jz      short loc_1400C28AC
0x1400c2888  mov     ebx, 0C00000E5h
0x1400c288d  mov     rcx, [rdi]; hAlgorithm
0x1400c2890  xor     edx, edx; dwFlags
0x1400c2892  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400c2899  nop     dword ptr [rax+rax+00h]
0x1400c289e  mov     eax, ebx
0x1400c28a0  mov     rbx, [rsp+38h+arg_0]
0x1400c28a5  add     rsp, 30h
0x1400c28a9  pop     rdi
0x1400c28aa  retn
0x1400c28ac  mov     eax, [rsp+38h+pbOutput]
0x1400c28b0  mov     cs:ObjectLengthSP800108, eax
0x1400c28b6  jmp     short loc_1400C289E
```
