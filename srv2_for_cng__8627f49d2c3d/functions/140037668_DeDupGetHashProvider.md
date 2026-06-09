# DeDupGetHashProvider

- ea: `0x140037668`
- end: `0x140037741`
- name: `DeDupGetHashProvider`
- size: `217`
- prototype: `__int64 __fastcall(int, BCRYPT_ALG_HANDLE *, UCHAR *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140035cec`
- `0x140036850`

## callees

- `0x140037668`

## import_xrefs

- `ksecdd!BCryptGetProperty` at `0x1400376f5`
- `ksecdd!BCryptGetProperty` at `0x1400376f5`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400376b0`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400376b0`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140037728`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140037728`

## pseudocode

```c
__int64 __fastcall DeDupGetHashProvider(int a1, BCRYPT_ALG_HANDLE *a2, UCHAR *a3, int a4)
{
  unsigned int Property; // ebx
  BCRYPT_ALG_HANDLE v8; // rcx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+30h] [rbp-38h] BYREF
  ULONG pcbResult; // [rsp+70h] [rbp+8h] BYREF

  pcbResult = 0;
  phAlgorithm = 0;
  if ( a1 )
    return 3221225485LL;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA512", 0, a4 != 0 ? 8 : 0);
  if ( (Property & 0xC0000000) == 0xC0000000
    || (Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", a3, 4u, &pcbResult, 0),
        (Property & 0xC0000000) == 0xC0000000) )
  {
    v8 = phAlgorithm;
  }
  else
  {
    v8 = 0;
    *a2 = phAlgorithm;
    phAlgorithm = 0;
  }
  if ( v8 )
    BCryptCloseAlgorithmProvider(v8, 0);
  return Property;
}

```

## disassembly

```asm
0x140037668  push    rbx
0x14003766a  push    rsi
0x14003766b  push    rdi
0x14003766c  push    r14
0x14003766e  sub     rsp, 48h
0x140037672  mov     [rsp+68h+arg_0], 0
0x14003767a  mov     rsi, r8
0x14003767d  mov     [rsp+68h+phAlgorithm], 0
0x140037686  mov     rdi, rdx
0x140037689  test    ecx, ecx
0x14003768b  jz      short loc_140037697
0x14003768d  mov     eax, 0C000000Dh
0x140037692  jmp     loc_140037736
0x140037697  neg     r9d
0x14003769a  lea     rdx, pszAlgId; "SHA512"
0x1400376a1  lea     rcx, [rsp+68h+phAlgorithm]; phAlgorithm
0x1400376a6  sbb     r9d, r9d
0x1400376a9  xor     r8d, r8d; pszImplementation
0x1400376ac  and     r9d, 8; dwFlags
0x1400376b0  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400376b7  nop     dword ptr [rax+rax+00h]
0x1400376bc  mov     r14d, 0C0000000h
0x1400376c2  mov     ecx, eax
0x1400376c4  and     ecx, r14d
0x1400376c7  mov     ebx, eax
0x1400376c9  cmp     ecx, r14d
0x1400376cc  jz      short loc_14003771C
0x1400376ce  mov     rcx, [rsp+68h+phAlgorithm]; hObject
0x1400376d3  lea     rax, [rsp+68h+arg_0]
0x1400376d8  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1400376e0  lea     rdx, aObjectlength; "ObjectLength"
0x1400376e7  mov     r9d, 4; cbOutput
0x1400376ed  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1400376f2  mov     r8, rsi; pbOutput
0x1400376f5  call    cs:__imp_BCryptGetProperty
0x1400376fc  nop     dword ptr [rax+rax+00h]
0x140037701  mov     ebx, eax
0x140037703  and     eax, r14d
0x140037706  cmp     eax, r14d
0x140037709  jz      short loc_14003771C
0x14003770b  mov     rax, [rsp+68h+phAlgorithm]
0x140037710  xor     ecx, ecx
0x140037712  mov     [rdi], rax
0x140037715  mov     [rsp+68h+phAlgorithm], rcx
0x14003771a  jmp     short loc_140037721
0x14003771c  mov     rcx, [rsp+68h+phAlgorithm]; hAlgorithm
0x140037721  test    rcx, rcx
0x140037724  jz      short loc_140037734
0x140037726  xor     edx, edx; dwFlags
0x140037728  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14003772f  nop     dword ptr [rax+rax+00h]
0x140037734  mov     eax, ebx
0x140037736  add     rsp, 48h
0x14003773a  pop     r14
0x14003773c  pop     rdi
0x14003773d  pop     rsi
0x14003773e  pop     rbx
0x14003773f  retn
```
