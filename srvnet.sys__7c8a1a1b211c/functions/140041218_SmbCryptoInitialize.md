# SmbCryptoInitialize

- ea: `0x140041218`
- end: `0x14004139a`
- name: `SmbCryptoInitialize`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14005b3c8`

## callees

- `0x14000f654`
- `0x140041218`
- `0x140056f58`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004124a`
- `ntoskrnl!ExAllocatePool2` at `0x14004124a`
- `ntoskrnl!RtlRunOnceInitialize` at `0x140041387`
- `ntoskrnl!RtlRunOnceInitialize` at `0x140041387`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14004122c`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14004122c`
- `ksecdd!BCryptGenRandom` at `0x14004129c`
- `ksecdd!BCryptGenRandom` at `0x14004129c`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14004136a`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14004136a`

## pseudocode

```c
__int64 SmbCryptoInitialize()
{
  ULONG MaximumProcessorCount; // esi
  __int64 v1; // rdx
  NTSTATUS v2; // ebx
  ULONG i; // edi
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx

  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  SmbCryptoNonceCounter = (PVOID)ExAllocatePool2(74, MaximumProcessorCount << 6, 590500684);
  if ( !SmbCryptoNonceCounter )
  {
    v2 = -1073741670;
LABEL_3:
    SmbCryptoDeinitialize();
    return (unsigned int)v2;
  }
  for ( i = 0; i < MaximumProcessorCount; ++i )
  {
    v2 = BCryptGenRandom(0, (PUCHAR)SmbCryptoNonceCounter + 64 * (unsigned __int64)i, 8u, 2u);
    if ( v2 < 0 )
      goto LABEL_3;
  }
  v2 = SmbCryptoInitializeCipher(SmbCryptoCiphers, v1, L"ChainingModeCCM");
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = SmbCryptoInitializeCipher(qword_140040158, v5, L"ChainingModeGCM");
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = SmbCryptoInitializeCipher(qword_140040170, v6, L"ChainingModeCCM");
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = SmbCryptoInitializeCipher(qword_140040188, v7, L"ChainingModeGCM");
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = BCryptOpenAlgorithmProvider(&SmbCryptoSp800108CtrHmacAlgHandle, L"SP800_108_CTR_HMAC", 0, 1u);
  if ( v2 < 0 )
    goto LABEL_3;
  RtlRunOnceInitialize(&RunOnce);
  return 0;
}

```

## disassembly

```asm
0x140041218  mov     [rsp+arg_0], rbx
0x14004121d  mov     [rsp+arg_8], rsi
0x140041222  push    rdi
0x140041223  sub     rsp, 30h
0x140041227  mov     ecx, 0FFFFh; GroupNumber
0x14004122c  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x140041233  nop     dword ptr [rax+rax+00h]
0x140041238  mov     ecx, 4Ah ; 'J'
0x14004123d  mov     r8d, 2332534Ch
0x140041243  mov     edx, eax
0x140041245  mov     esi, eax
0x140041247  shl     edx, 6
0x14004124a  call    cs:__imp_ExAllocatePool2
0x140041251  nop     dword ptr [rax+rax+00h]
0x140041256  mov     cs:SmbCryptoNonceCounter, rax
0x14004125d  test    rax, rax
0x140041260  jnz     short loc_14004127F
0x140041262  mov     ebx, 0C000009Ah
0x140041267  call    SmbCryptoDeinitialize
0x14004126c  mov     eax, ebx
0x14004126e  mov     rbx, [rsp+38h+arg_0]
0x140041273  mov     rsi, [rsp+38h+arg_8]
0x140041278  add     rsp, 30h
0x14004127c  pop     rdi
0x14004127d  retn
0x14004127f  xor     edi, edi
0x140041281  cmp     edi, esi
0x140041283  jnb     short loc_1400412B2
0x140041285  xor     ecx, ecx; hAlgorithm
0x140041287  mov     edx, edi
0x140041289  shl     rdx, 6
0x14004128d  add     rdx, cs:SmbCryptoNonceCounter; pbBuffer
0x140041294  lea     r9d, [rcx+2]; dwFlags
0x140041298  lea     r8d, [rcx+8]; cbBuffer
0x14004129c  call    cs:__imp_BCryptGenRandom
0x1400412a3  nop     dword ptr [rax+rax+00h]
0x1400412a8  mov     ebx, eax
0x1400412aa  test    eax, eax
0x1400412ac  js      short loc_140041267
0x1400412ae  inc     edi
0x1400412b0  jmp     short loc_140041281
0x1400412b2  mov     edi, 10h
0x1400412b7  lea     r8, aChainingmodecc; "ChainingModeCCM"
0x1400412be  mov     [rsp+38h+var_10], edi
0x1400412c2  lea     rcx, SmbCryptoCiphers
0x1400412c9  lea     esi, [rdi-5]
0x1400412cc  mov     [rsp+38h+var_18], esi
0x1400412d0  call    SmbCryptoInitializeCipher
0x1400412d5  mov     ebx, eax
0x1400412d7  test    eax, eax
0x1400412d9  js      short loc_140041267
0x1400412db  mov     [rsp+38h+var_10], edi
0x1400412df  lea     r8, aChainingmodegc; "ChainingModeGCM"
0x1400412e6  lea     rcx, qword_140040158
0x1400412ed  mov     [rsp+38h+var_18], 0Ch
0x1400412f5  call    SmbCryptoInitializeCipher
0x1400412fa  mov     ebx, eax
0x1400412fc  test    eax, eax
0x1400412fe  js      loc_140041267
0x140041304  lea     edi, [rsi+15h]
0x140041307  mov     [rsp+38h+var_10], edi
0x14004130b  lea     r8, aChainingmodecc; "ChainingModeCCM"
0x140041312  lea     rcx, qword_140040170
0x140041319  mov     [rsp+38h+var_18], esi
0x14004131d  call    SmbCryptoInitializeCipher
0x140041322  mov     ebx, eax
0x140041324  test    eax, eax
0x140041326  js      loc_140041267
0x14004132c  mov     [rsp+38h+var_10], edi
0x140041330  lea     r8, aChainingmodegc; "ChainingModeGCM"
0x140041337  lea     rcx, qword_140040188
0x14004133e  mov     [rsp+38h+var_18], 0Ch
0x140041346  call    SmbCryptoInitializeCipher
0x14004134b  mov     ebx, eax
0x14004134d  test    eax, eax
0x14004134f  js      loc_140041267
0x140041355  lea     r9d, [rsi-0Ah]; dwFlags
0x140041359  xor     r8d, r8d; pszImplementation
0x14004135c  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x140041363  lea     rcx, SmbCryptoSp800108CtrHmacAlgHandle; phAlgorithm
0x14004136a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140041371  nop     dword ptr [rax+rax+00h]
0x140041376  mov     ebx, eax
0x140041378  test    eax, eax
0x14004137a  js      loc_140041267
0x140041380  lea     rcx, RunOnce; RunOnce
0x140041387  call    cs:__imp_RtlRunOnceInitialize
0x14004138e  nop     dword ptr [rax+rax+00h]
0x140041393  xor     eax, eax
0x140041395  jmp     loc_14004126E
```
