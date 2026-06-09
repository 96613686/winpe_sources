# SkpOpenAesXtsProvider

- ea: `0x1400c2708`
- end: `0x1400c27fa`
- name: `SkpOpenAesXtsProvider`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400bfa88`

## callees

- `0x1400c2708`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x1400c273c`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400c273c`
- `cng!BCryptSetProperty` at `0x1400c276f`
- `cng!BCryptSetProperty` at `0x1400c276f`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c27d4`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c27d4`
- `cng!BCryptGetProperty` at `0x1400c27b1`
- `cng!BCryptGetProperty` at `0x1400c27b1`

## pseudocode

```c
__int64 __fastcall SkpOpenAesXtsProvider(BCRYPT_ALG_HANDLE *a1)
{
  NTSTATUS Property; // ebx
  ULONG pcbResult; // [rsp+48h] [rbp+10h] BYREF
  int pbOutput; // [rsp+50h] [rbp+18h] BYREF
  int pbInput; // [rsp+58h] [rbp+20h] BYREF

  pbInput = 4096;
  pbOutput = 0;
  pcbResult = 0;
  Property = BCryptOpenAlgorithmProvider(a1, L"XTS-AES", 0, 1u);
  if ( Property >= 0 )
  {
    Property = BCryptSetProperty(*a1, L"MessageBlockLength", (PUCHAR)&pbInput, 4u, 0);
    if ( Property < 0 )
    {
LABEL_7:
      BCryptCloseAlgorithmProvider(*a1, 0);
      return (unsigned int)Property;
    }
    if ( !ObjectLengthAesXts )
    {
      Property = BCryptGetProperty(*a1, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
      if ( Property >= 0 )
      {
        if ( pcbResult == 4 )
        {
          ObjectLengthAesXts = pbOutput;
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
0x1400c2708  mov     rax, rsp
0x1400c270b  mov     [rax+8], rbx
0x1400c270f  push    rdi
0x1400c2710  sub     rsp, 30h
0x1400c2714  mov     r9d, 1; dwFlags
0x1400c271a  mov     dword ptr [rax+20h], 1000h
0x1400c2721  xor     r8d, r8d; pszImplementation
0x1400c2724  mov     dword ptr [rax+18h], 0
0x1400c272b  lea     rdx, aXtsAes; "XTS-AES"
0x1400c2732  mov     dword ptr [rax+10h], 0
0x1400c2739  mov     rdi, rcx
0x1400c273c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400c2743  nop     dword ptr [rax+rax+00h]
0x1400c2748  mov     ebx, eax
0x1400c274a  test    eax, eax
0x1400c274c  js      loc_1400C27E0
0x1400c2752  mov     rcx, [rdi]; hObject
0x1400c2755  lea     r8, [rsp+38h+pbInput]; pbInput
0x1400c275a  mov     r9d, 4; cbInput
0x1400c2760  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1400c2768  lea     rdx, aMessageblockle; "MessageBlockLength"
0x1400c276f  call    cs:__imp_BCryptSetProperty
0x1400c2776  nop     dword ptr [rax+rax+00h]
0x1400c277b  mov     ebx, eax
0x1400c277d  test    eax, eax
0x1400c277f  js      short loc_1400C27CF
0x1400c2781  cmp     cs:ObjectLengthAesXts, 0
0x1400c2788  jnz     short loc_1400C27E0
0x1400c278a  mov     rcx, [rdi]; hObject
0x1400c278d  lea     rax, [rsp+38h+pcbResult]
0x1400c2792  mov     [rsp+38h+var_10], 0; dwFlags
0x1400c279a  lea     r8, [rsp+38h+pbOutput]; pbOutput
0x1400c279f  mov     r9d, 4; cbOutput
0x1400c27a5  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x1400c27aa  lea     rdx, pszProperty; "ObjectLength"
0x1400c27b1  call    cs:__imp_BCryptGetProperty
0x1400c27b8  nop     dword ptr [rax+rax+00h]
0x1400c27bd  mov     ebx, eax
0x1400c27bf  test    eax, eax
0x1400c27c1  js      short loc_1400C27CF
0x1400c27c3  cmp     [rsp+38h+pcbResult], 4
0x1400c27c8  jz      short loc_1400C27EE
0x1400c27ca  mov     ebx, 0C00000E5h
0x1400c27cf  mov     rcx, [rdi]; hAlgorithm
0x1400c27d2  xor     edx, edx; dwFlags
0x1400c27d4  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400c27db  nop     dword ptr [rax+rax+00h]
0x1400c27e0  mov     eax, ebx
0x1400c27e2  mov     rbx, [rsp+38h+arg_0]
0x1400c27e7  add     rsp, 30h
0x1400c27eb  pop     rdi
0x1400c27ec  retn
0x1400c27ee  mov     eax, [rsp+38h+pbOutput]
0x1400c27f2  mov     cs:ObjectLengthAesXts, eax
0x1400c27f8  jmp     short loc_1400C27E0
```
