# WimpFSFSetupCng

- ea: `0x14002e8cc`
- end: `0x14002e9e4`
- name: `WimpFSFSetupCng`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140029880`

## callees

- `0x140029708`
- `0x14002e8cc`

## import_xrefs

- `cng!BCryptCloseAlgorithmProvider` at `0x14002e9ce`
- `cng!BCryptCloseAlgorithmProvider` at `0x14002e9ce`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002e917`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002e917`
- `cng!BCryptGetProperty` at `0x14002e953`
- `cng!BCryptGetProperty` at `0x14002e98b`
- `cng!BCryptGetProperty` at `0x14002e953`
- `cng!BCryptGetProperty` at `0x14002e98b`

## pseudocode

```c
__int64 WimpFSFSetupCng()
{
  NTSTATUS Property; // ebx
  BCRYPT_ALG_HANDLE v1; // r8
  ULONG pcbResult; // [rsp+50h] [rbp+18h] BYREF
  int pbOutput; // [rsp+58h] [rbp+20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp+28h] BYREF
  __int64 v6; // [rsp+68h] [rbp+30h] BYREF

  pcbResult = 0;
  phAlgorithm = 0;
  pbOutput = 0;
  v6 = 0;
  Property = WimpFSFGetCngExtensions();
  if ( Property < 0
    || (Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0x60u), Property < 0)
    || (Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0),
        Property < 0)
    || (Property = BCryptGetProperty(phAlgorithm, L"MultiObjectLength", (PUCHAR)&v6, 8u, &pcbResult, 0), Property < 0) )
  {
    v1 = phAlgorithm;
  }
  else
  {
    v1 = 0;
    g_WimIntegrityHashAlgorithmHandle = (__int64)phAlgorithm;
    phAlgorithm = 0;
    g_WimIntegrityMultiHashObjectLength = v6 + 4 * HIDWORD(v6);
  }
  if ( v1 )
    BCryptCloseAlgorithmProvider(v1, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14002e8cc  push    rbp
0x14002e8ce  push    rbx
0x14002e8cf  mov     rbp, rsp
0x14002e8d2  sub     rsp, 38h
0x14002e8d6  mov     [rbp+arg_0], 0
0x14002e8dd  mov     [rbp+phAlgorithm], 0
0x14002e8e5  mov     [rbp+pbOutput], 0
0x14002e8ec  mov     [rbp+arg_18], 0
0x14002e8f4  call    WimpFSFGetCngExtensions
0x14002e8f9  mov     ebx, eax
0x14002e8fb  test    eax, eax
0x14002e8fd  js      loc_14002E9C0
0x14002e903  mov     r9d, 60h ; '`'; dwFlags
0x14002e909  lea     rdx, pszAlgId; "SHA256"
0x14002e910  xor     r8d, r8d; pszImplementation
0x14002e913  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14002e917  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14002e91e  nop     dword ptr [rax+rax+00h]
0x14002e923  mov     ebx, eax
0x14002e925  test    eax, eax
0x14002e927  js      loc_14002E9C0
0x14002e92d  mov     rcx, [rbp+phAlgorithm]; hObject
0x14002e931  lea     rax, [rbp+arg_0]
0x14002e935  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14002e93d  lea     r8, [rbp+pbOutput]; pbOutput
0x14002e941  mov     r9d, 4; cbOutput
0x14002e947  mov     [rsp+38h+pcbResult], rax; pcbResult
0x14002e94c  lea     rdx, pszProperty; "HashDigestLength"
0x14002e953  call    cs:__imp_BCryptGetProperty
0x14002e95a  nop     dword ptr [rax+rax+00h]
0x14002e95f  mov     ebx, eax
0x14002e961  test    eax, eax
0x14002e963  js      short loc_14002E9C0
0x14002e965  mov     rcx, [rbp+phAlgorithm]; hObject
0x14002e969  lea     rax, [rbp+arg_0]
0x14002e96d  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14002e975  lea     r8, [rbp+arg_18]; pbOutput
0x14002e979  mov     r9d, 8; cbOutput
0x14002e97f  mov     [rsp+38h+pcbResult], rax; pcbResult
0x14002e984  lea     rdx, aMultiobjectlen; "MultiObjectLength"
0x14002e98b  call    cs:__imp_BCryptGetProperty
0x14002e992  nop     dword ptr [rax+rax+00h]
0x14002e997  mov     ebx, eax
0x14002e999  test    eax, eax
0x14002e99b  js      short loc_14002E9C0
0x14002e99d  mov     rax, [rbp+phAlgorithm]
0x14002e9a1  xor     r8d, r8d
0x14002e9a4  mov     ecx, dword ptr [rbp+arg_18]
0x14002e9a7  mov     cs:g_WimIntegrityHashAlgorithmHandle, rax
0x14002e9ae  mov     eax, dword ptr [rbp+arg_18+4]
0x14002e9b1  mov     [rbp+phAlgorithm], r8
0x14002e9b5  lea     ecx, [rcx+rax*4]
0x14002e9b8  mov     cs:g_WimIntegrityMultiHashObjectLength, ecx
0x14002e9be  jmp     short loc_14002E9C4
0x14002e9c0  mov     r8, [rbp+phAlgorithm]
0x14002e9c4  test    r8, r8
0x14002e9c7  jz      short loc_14002E9DA
0x14002e9c9  xor     edx, edx; dwFlags
0x14002e9cb  mov     rcx, r8; hAlgorithm
0x14002e9ce  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14002e9d5  nop     dword ptr [rax+rax+00h]
0x14002e9da  mov     eax, ebx
0x14002e9dc  add     rsp, 38h
0x14002e9e0  pop     rbx
0x14002e9e1  pop     rbp
0x14002e9e2  retn
```
