# SmbCryptoKeyedHashInitialize

- ea: `0x14004b350`
- end: `0x14004b465`
- name: `SmbCryptoKeyedHashInitialize`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14004b350`
- `0x14004b470`

## import_xrefs

- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14004b396`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14004b396`
- `ksecdd!BCryptGetProperty` at `0x14004b3d2`
- `ksecdd!BCryptGetProperty` at `0x14004b412`
- `ksecdd!BCryptGetProperty` at `0x14004b3d2`
- `ksecdd!BCryptGetProperty` at `0x14004b412`

## pseudocode

```c
__int64 SmbCryptoKeyedHashInitialize()
{
  __int64 v0; // rbx
  __int64 *v1; // rsi
  NTSTATUS Property; // edi
  bool v3; // cc
  ULONG pcbResult; // [rsp+70h] [rbp+8h] BYREF

  v0 = 0;
  pcbResult = 0;
  while ( 1 )
  {
    v1 = &qword_140036780[3 * v0];
    Property = BCryptOpenAlgorithmProvider(
                 (BCRYPT_ALG_HANDLE *)v1,
                 (&Smb2HashAlgorithmDescriptors)[2 * (unsigned int)v0],
                 0,
                 dword_14002F138[4 * (unsigned int)v0]);
    if ( Property < 0 )
      break;
    Property = BCryptGetProperty((BCRYPT_HANDLE)*v1, L"HashDigestLength", (PUCHAR)v1 + 8, 4u, &pcbResult, 0);
    if ( Property < 0 )
      break;
    Property = BCryptGetProperty(
                 (BCRYPT_HANDLE)*v1,
                 L"ObjectLength",
                 (PUCHAR)&dword_14003678C[6 * v0],
                 4u,
                 &pcbResult,
                 0);
    if ( Property < 0 )
      break;
    v3 = (unsigned int)dword_140036788[6 * v0] <= 0x20;
    word_140036790[12 * v0] = word_14002F13C[8 * (unsigned int)v0];
    if ( !v3 )
      __int2c();
    v0 = (unsigned int)(v0 + 1);
    if ( (unsigned int)v0 >= 3 )
      return (unsigned int)Property;
  }
  SmbCryptoKeyedHashUninitialize();
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14004b350  push    rbx
0x14004b352  push    rbp
0x14004b353  push    rsi
0x14004b354  push    rdi
0x14004b355  push    r12
0x14004b357  push    r14
0x14004b359  sub     rsp, 38h
0x14004b35d  xor     ebx, ebx
0x14004b35f  lea     r12, cs:140000000h
0x14004b366  mov     [rsp+68h+arg_0], ebx
0x14004b36a  mov     r14d, ebx
0x14004b36d  lea     rbp, [rbx+rbx*2]
0x14004b371  add     r14, r14
0x14004b374  lea     rsi, rva qword_140036780[r12]
0x14004b37c  lea     rsi, [rsi+rbp*8]
0x14004b380  xor     r8d, r8d; pszImplementation
0x14004b383  mov     rcx, rsi; phAlgorithm
0x14004b386  mov     r9d, ds:rva dword_14002F138[r12+r14*8]; dwFlags
0x14004b38e  mov     rdx, ds:rva Smb2HashAlgorithmDescriptors[r12+r14*8]; pszAlgId
0x14004b396  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14004b39d  nop     dword ptr [rax+rax+00h]
0x14004b3a2  mov     edi, eax
0x14004b3a4  test    eax, eax
0x14004b3a6  js      loc_14004B450
0x14004b3ac  mov     rcx, [rsi]; hObject
0x14004b3af  lea     rax, [rsp+68h+arg_0]
0x14004b3b4  lea     r8, [rsi+8]; pbOutput
0x14004b3b8  mov     [rsp+68h+dwFlags], 0; dwFlags
0x14004b3c0  mov     r9d, 4; cbOutput
0x14004b3c6  mov     [rsp+68h+pcbResult], rax; pcbResult
0x14004b3cb  lea     rdx, aHashdigestleng; "HashDigestLength"
0x14004b3d2  call    cs:__imp_BCryptGetProperty
0x14004b3d9  nop     dword ptr [rax+rax+00h]
0x14004b3de  mov     edi, eax
0x14004b3e0  test    eax, eax
0x14004b3e2  js      short loc_14004B450
0x14004b3e4  mov     rcx, [rsi]; hObject
0x14004b3e7  lea     rax, [rsp+68h+arg_0]
0x14004b3ec  lea     r8, rva dword_14003678C[r12]
0x14004b3f4  mov     [rsp+68h+dwFlags], 0; dwFlags
0x14004b3fc  lea     r8, [r8+rbp*8]; pbOutput
0x14004b400  mov     [rsp+68h+pcbResult], rax; pcbResult
0x14004b405  mov     r9d, 4; cbOutput
0x14004b40b  lea     rdx, aObjectlength; "ObjectLength"
0x14004b412  call    cs:__imp_BCryptGetProperty
0x14004b419  nop     dword ptr [rax+rax+00h]
0x14004b41e  mov     edi, eax
0x14004b420  test    eax, eax
0x14004b422  js      short loc_14004B450
0x14004b424  cmp     rva dword_140036788[r12+rbp*8], 20h ; ' '
0x14004b42d  movzx   eax, ds:rva word_14002F13C[r12+r14*8]
0x14004b436  mov     rva word_140036790[r12+rbp*8], ax
0x14004b43f  jbe     short loc_14004B443
0x14004b441  int     2Ch; Windows NT - assertion failure
0x14004b443  inc     ebx
0x14004b445  cmp     ebx, 3
0x14004b448  jb      loc_14004B36A
0x14004b44e  jmp     short loc_14004B455
0x14004b450  call    SmbCryptoKeyedHashUninitialize
0x14004b455  mov     eax, edi
0x14004b457  add     rsp, 38h
0x14004b45b  pop     r14
0x14004b45d  pop     r12
0x14004b45f  pop     rdi
0x14004b460  pop     rsi
0x14004b461  pop     rbp
0x14004b462  pop     rbx
0x14004b463  retn
```
