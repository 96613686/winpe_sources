# NvmeFabricControllerQueueComputeCtrlResponse

- ea: `0x1401173e4`
- end: `0x1401177fd`
- name: `NvmeFabricControllerQueueComputeCtrlResponse`
- size: `1049`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140118604`

## callees

- `0x14005285c`
- `0x1401173e4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1401177bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401177bc`
- `ntoskrnl!ExAllocatePool2` at `0x1401174ce`
- `ntoskrnl!ExAllocatePool2` at `0x1401174ce`
- `ksecdd!BCryptCreateHash` at `0x140117568`
- `ksecdd!BCryptCreateHash` at `0x140117568`
- `ksecdd!BCryptHashData` at `0x14011758c`
- `ksecdd!BCryptHashData` at `0x1401175b5`
- `ksecdd!BCryptHashData` at `0x1401175da`
- `ksecdd!BCryptHashData` at `0x140117603`
- `ksecdd!BCryptHashData` at `0x14011762b`
- `ksecdd!BCryptHashData` at `0x14011765e`
- `ksecdd!BCryptHashData` at `0x14011767f`
- `ksecdd!BCryptHashData` at `0x1401176af`
- `ksecdd!BCryptHashData` at `0x14011758c`
- `ksecdd!BCryptHashData` at `0x1401175b5`
- `ksecdd!BCryptHashData` at `0x1401175da`
- `ksecdd!BCryptHashData` at `0x140117603`
- `ksecdd!BCryptHashData` at `0x14011762b`
- `ksecdd!BCryptHashData` at `0x14011765e`
- `ksecdd!BCryptHashData` at `0x14011767f`
- `ksecdd!BCryptHashData` at `0x1401176af`
- `ksecdd!BCryptDestroyHash` at `0x1401177a3`
- `ksecdd!BCryptDestroyHash` at `0x1401177a3`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1401177d3`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1401177d3`
- `ksecdd!BCryptFinishHash` at `0x1401176d0`
- `ksecdd!BCryptFinishHash` at `0x1401176d0`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140117472`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140117472`
- `ksecdd!BCryptGetProperty` at `0x1401174aa`
- `ksecdd!BCryptGetProperty` at `0x140117512`
- `ksecdd!BCryptGetProperty` at `0x1401174aa`
- `ksecdd!BCryptGetProperty` at `0x140117512`

## string_xrefs

- `0x140117772`: `Computing controller response failed`

## pseudocode

```c
__int64 __fastcall NvmeFabricControllerQueueComputeCtrlResponse(__int64 a1, unsigned __int16 a2, UCHAR *a3, UCHAR *a4)
{
  _QWORD *v4; // r13
  UCHAR *Pool2; // rsi
  __int64 v8; // r12
  int v9; // edi
  char v10; // cl
  const WCHAR *v11; // rdx
  NTSTATUS Property; // ebx
  __int64 v13; // rdi
  UCHAR *v14; // rdx
  __int64 v15; // r8
  UCHAR *v16; // rdx
  UCHAR v18[4]; // [rsp+A0h] [rbp+7h] BYREF
  UCHAR pbOutput[4]; // [rsp+A4h] [rbp+Bh] BYREF
  ULONG pcbResult; // [rsp+A8h] [rbp+Fh] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+B0h] [rbp+17h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+B8h] [rbp+1Fh] BYREF
  UCHAR pbInput; // [rsp+100h] [rbp+67h] BYREF
  PUCHAR v24; // [rsp+118h] [rbp+7Fh]

  v24 = a4;
  v4 = *(_QWORD **)(a1 + 88);
  phAlgorithm = 0;
  Pool2 = 0;
  phHash = 0;
  *(_DWORD *)v18 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  pbInput = 0;
  v8 = v4[12];
  v9 = a2;
  v10 = *(_BYTE *)(*(_QWORD *)(a1 + 96) + 3LL);
  switch ( v10 )
  {
    case 1:
      v11 = L"SHA256";
      break;
    case 2:
      v11 = L"SHA384";
      break;
    case 3:
      v11 = L"SHA512";
      break;
    default:
      Property = -1073741811;
      goto LABEL_30;
  }
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, v11, L"Microsoft Primitive Provider", 8u);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Pool2 = (UCHAR *)ExAllocatePool2(256, *(unsigned int *)pbOutput, 1095655762);
  if ( !Pool2 )
  {
    Property = -1073741801;
LABEL_30:
    StorEtwNvmeControllerEvent(
      (_DWORD)v4,
      1,
      2,
      (unsigned int)L"Computing controller response failed",
      (__int64)L"Status",
      Property,
      (__int64)L"HashID",
      *(_BYTE *)(*(_QWORD *)(a1 + 96) + 3LL),
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0);
    goto LABEL_31;
  }
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v18, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_30;
  if ( *(_DWORD *)v18 != v9 )
  {
    Property = -1073741820;
    goto LABEL_30;
  }
  Property = BCryptCreateHash(
               phAlgorithm,
               &phHash,
               Pool2,
               *(ULONG *)pbOutput,
               (PUCHAR)(v4[209] + 532LL),
               *(unsigned __int16 *)(v4[209] + 14LL),
               0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptHashData(phHash, a3, *(ULONG *)v18, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptHashData(phHash, (PUCHAR)(*(_QWORD *)(a1 + 96) + 12LL), 4u, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptHashData(phHash, *(PUCHAR *)(a1 + 96), 2u, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptHashData(phHash, (PUCHAR)(*(_QWORD *)(a1 + 96) + 2LL), 1u, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptHashData(phHash, (PUCHAR)"Controller", 0xAu, 0);
  if ( Property < 0 )
    goto LABEL_30;
  v13 = -1;
  v14 = (UCHAR *)(v8 + 60);
  v15 = -1;
  do
    ++v15;
  while ( v14[v15] );
  Property = BCryptHashData(phHash, v14, v15, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptHashData(phHash, &pbInput, 1u, 0);
  if ( Property < 0 )
    goto LABEL_30;
  v16 = (UCHAR *)(v4[208] + 20LL);
  do
    ++v13;
  while ( v16[v13] );
  Property = BCryptHashData(phHash, v16, v13, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptFinishHash(phHash, v24, *(ULONG *)v18, 0);
  if ( Property < 0 )
    goto LABEL_30;
LABEL_31:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x414E6152u);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1401173e4  mov     [rsp-8+arg_8], rbx
0x1401173e9  mov     [rsp-8+arg_18], r9
0x1401173ee  push    rbp
0x1401173ef  push    rsi
0x1401173f0  push    rdi
0x1401173f1  push    r12
0x1401173f3  push    r13
0x1401173f5  push    r14
0x1401173f7  push    r15
0x1401173f9  lea     rbp, [rsp-27h]
0x1401173fe  sub     rsp, 0C0h
0x140117405  mov     r13, [rcx+58h]
0x140117409  xor     eax, eax
0x14011740b  mov     [rbp+57h+phAlgorithm], rax
0x14011740f  mov     esi, eax
0x140117411  mov     [rbp+57h+phHash], rax
0x140117415  mov     r14, rcx
0x140117418  mov     dword ptr [rbp+57h+var_50], eax
0x14011741b  mov     r15, r8
0x14011741e  mov     dword ptr [rbp+57h+pbOutput], eax
0x140117421  mov     [rbp+57h+var_48], eax
0x140117424  mov     [rbp+57h+pbInput], al
0x140117427  mov     rax, [rcx+60h]
0x14011742b  mov     r12, [r13+60h]
0x14011742f  movzx   edi, dx
0x140117432  mov     cl, [rax+3]
0x140117435  cmp     cl, 1
0x140117438  jnz     short loc_140117443
0x14011743a  lea     rdx, aSha256; "SHA256"
0x140117441  jmp     short loc_140117461
0x140117443  cmp     cl, 2
0x140117446  jnz     short loc_140117451
0x140117448  lea     rdx, aSha384; "SHA384"
0x14011744f  jmp     short loc_140117461
0x140117451  cmp     cl, 3
0x140117454  jnz     loc_1401176E8
0x14011745a  lea     rdx, pszAlgId; "SHA512"
0x140117461  mov     r9d, 8; dwFlags
0x140117467  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x14011746e  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x140117472  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140117479  nop     dword ptr [rax+rax+00h]
0x14011747e  mov     ebx, eax
0x140117480  test    eax, eax
0x140117482  js      loc_1401176ED
0x140117488  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x14011748c  lea     rax, [rbp+57h+var_48]
0x140117490  mov     [rsp+0F0h+dwFlags], esi; dwFlags
0x140117494  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x140117498  mov     r9d, 4; cbOutput
0x14011749e  mov     [rsp+0F0h+pcbResult], rax; pcbResult
0x1401174a3  lea     rdx, pszProperty; "ObjectLength"
0x1401174aa  call    cs:__imp_BCryptGetProperty
0x1401174b1  nop     dword ptr [rax+rax+00h]
0x1401174b6  mov     ebx, eax
0x1401174b8  test    eax, eax
0x1401174ba  js      loc_1401176ED
0x1401174c0  mov     edx, dword ptr [rbp+57h+pbOutput]
0x1401174c3  mov     ecx, 100h
0x1401174c8  mov     r8d, 414E6152h
0x1401174ce  call    cs:__imp_ExAllocatePool2
0x1401174d5  nop     dword ptr [rax+rax+00h]
0x1401174da  mov     rsi, rax
0x1401174dd  test    rax, rax
0x1401174e0  jnz     short loc_1401174EC
0x1401174e2  mov     ebx, 0C0000017h
0x1401174e7  jmp     loc_1401176ED
0x1401174ec  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x1401174f0  lea     rax, [rbp+57h+var_48]
0x1401174f4  mov     [rsp+0F0h+dwFlags], 0; dwFlags
0x1401174fc  lea     r8, [rbp+57h+var_50]; pbOutput
0x140117500  mov     r9d, 4; cbOutput
0x140117506  mov     [rsp+0F0h+pcbResult], rax; pcbResult
0x14011750b  lea     rdx, aHashdigestleng; "HashDigestLength"
0x140117512  call    cs:__imp_BCryptGetProperty
0x140117519  nop     dword ptr [rax+rax+00h]
0x14011751e  mov     ebx, eax
0x140117520  test    eax, eax
0x140117522  js      loc_1401176ED
0x140117528  cmp     dword ptr [rbp+57h+var_50], edi
0x14011752b  jz      short loc_140117537
0x14011752d  mov     ebx, 0C0000004h
0x140117532  jmp     loc_1401176ED
0x140117537  mov     rax, [r13+688h]
0x14011753e  lea     rdx, [rbp+57h+phHash]; phHash
0x140117542  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x140117546  mov     r8, rsi; pbHashObject
0x140117549  mov     [rsp+0F0h+var_C0], 0; dwFlags
0x140117551  movzx   ecx, word ptr [rax+0Eh]
0x140117555  add     rax, 214h
0x14011755b  mov     [rsp+0F0h+dwFlags], ecx; cbSecret
0x14011755f  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x140117563  mov     [rsp+0F0h+pcbResult], rax; pbSecret
0x140117568  call    cs:__imp_BCryptCreateHash
0x14011756f  nop     dword ptr [rax+rax+00h]
0x140117574  mov     ebx, eax
0x140117576  test    eax, eax
0x140117578  js      loc_1401176ED
0x14011757e  mov     r8d, dword ptr [rbp+57h+var_50]; cbInput
0x140117582  xor     r9d, r9d; dwFlags
0x140117585  mov     rcx, [rbp+57h+phHash]; hHash
0x140117589  mov     rdx, r15; pbInput
0x14011758c  call    cs:__imp_BCryptHashData
0x140117593  nop     dword ptr [rax+rax+00h]
0x140117598  mov     ebx, eax
0x14011759a  test    eax, eax
0x14011759c  js      loc_1401176ED
0x1401175a2  mov     rdx, [r14+60h]
0x1401175a6  xor     r9d, r9d; dwFlags
0x1401175a9  mov     rcx, [rbp+57h+phHash]; hHash
0x1401175ad  add     rdx, 0Ch; pbInput
0x1401175b1  lea     r8d, [r9+4]; cbInput
0x1401175b5  call    cs:__imp_BCryptHashData
0x1401175bc  nop     dword ptr [rax+rax+00h]
0x1401175c1  mov     ebx, eax
0x1401175c3  test    eax, eax
0x1401175c5  js      loc_1401176ED
0x1401175cb  mov     rdx, [r14+60h]; pbInput
0x1401175cf  xor     r9d, r9d; dwFlags
0x1401175d2  mov     rcx, [rbp+57h+phHash]; hHash
0x1401175d6  lea     r8d, [r9+2]; cbInput
0x1401175da  call    cs:__imp_BCryptHashData
0x1401175e1  nop     dword ptr [rax+rax+00h]
0x1401175e6  mov     ebx, eax
0x1401175e8  test    eax, eax
0x1401175ea  js      loc_1401176ED
0x1401175f0  mov     rdx, [r14+60h]
0x1401175f4  xor     r9d, r9d; dwFlags
0x1401175f7  mov     rcx, [rbp+57h+phHash]; hHash
0x1401175fb  add     rdx, 2; pbInput
0x1401175ff  lea     r8d, [r9+1]; cbInput
0x140117603  call    cs:__imp_BCryptHashData
0x14011760a  nop     dword ptr [rax+rax+00h]
0x14011760f  mov     ebx, eax
0x140117611  test    eax, eax
0x140117613  js      loc_1401176ED
0x140117619  mov     rcx, [rbp+57h+phHash]; hHash
0x14011761d  lea     rdx, aController; "Controller"
0x140117624  xor     r9d, r9d; dwFlags
0x140117627  lea     r8d, [r9+0Ah]; cbInput
0x14011762b  call    cs:__imp_BCryptHashData
0x140117632  nop     dword ptr [rax+rax+00h]
0x140117637  mov     ebx, eax
0x140117639  test    eax, eax
0x14011763b  js      loc_1401176ED
0x140117641  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140117645  lea     rdx, [r12+3Ch]; pbInput
0x14011764a  mov     r8, rdi
0x14011764d  inc     r8; cbInput
0x140117650  cmp     byte ptr [rdx+r8], 0
0x140117655  jnz     short loc_14011764D
0x140117657  mov     rcx, [rbp+57h+phHash]; hHash
0x14011765b  xor     r9d, r9d; dwFlags
0x14011765e  call    cs:__imp_BCryptHashData
0x140117665  nop     dword ptr [rax+rax+00h]
0x14011766a  mov     ebx, eax
0x14011766c  test    eax, eax
0x14011766e  js      short loc_1401176ED
0x140117670  mov     rcx, [rbp+57h+phHash]; hHash
0x140117674  lea     rdx, [rbp+57h+pbInput]; pbInput
0x140117678  xor     r9d, r9d; dwFlags
0x14011767b  lea     r8d, [r9+1]; cbInput
0x14011767f  call    cs:__imp_BCryptHashData
0x140117686  nop     dword ptr [rax+rax+00h]
0x14011768b  mov     ebx, eax
0x14011768d  test    eax, eax
0x14011768f  js      short loc_1401176ED
0x140117691  mov     rdx, [r13+680h]
0x140117698  add     rdx, 14h; pbInput
0x14011769c  inc     rdi
0x14011769f  cmp     byte ptr [rdx+rdi], 0
0x1401176a3  jnz     short loc_14011769C
0x1401176a5  mov     rcx, [rbp+57h+phHash]; hHash
0x1401176a9  xor     r9d, r9d; dwFlags
0x1401176ac  mov     r8d, edi; cbInput
0x1401176af  call    cs:__imp_BCryptHashData
0x1401176b6  nop     dword ptr [rax+rax+00h]
0x1401176bb  mov     ebx, eax
0x1401176bd  test    eax, eax
0x1401176bf  js      short loc_1401176ED
0x1401176c1  mov     r8d, dword ptr [rbp+57h+var_50]; cbOutput
0x1401176c5  xor     r9d, r9d; dwFlags
0x1401176c8  mov     rdx, [rbp+57h+arg_18]; pbOutput
0x1401176cc  mov     rcx, [rbp+57h+phHash]; hHash
0x1401176d0  call    cs:__imp_BCryptFinishHash
0x1401176d7  nop     dword ptr [rax+rax+00h]
0x1401176dc  mov     ebx, eax
0x1401176de  test    eax, eax
0x1401176e0  jns     loc_14011779A
0x1401176e6  jmp     short loc_1401176ED
0x1401176e8  mov     ebx, 0C000000Dh
0x1401176ed  mov     rax, [r14+60h]
0x1401176f1  lea     rcx, word_140155F3C
0x1401176f8  mov     [rsp+0F0h+var_58], 0
0x140117704  mov     edx, 1
0x140117709  mov     [rsp+0F0h+var_60], rcx
0x140117711  mov     [rsp+0F0h+var_68], 0
0x14011771d  movzx   r9d, byte ptr [rax+3]
0x140117722  mov     [rsp+0F0h+var_70], rcx
0x14011772a  lea     r8d, [rdx+1]
0x14011772e  mov     [rsp+0F0h+var_78], 0
0x140117737  mov     [rsp+0F0h+var_80], rcx
0x14011773c  mov     [rsp+0F0h+var_88], 0
0x140117745  mov     [rsp+0F0h+var_90], rcx
0x14011774a  mov     [rsp+0F0h+var_98], 0
0x140117753  mov     [rsp+0F0h+var_A0], rcx
0x140117758  mov     [rsp+0F0h+var_A8], 0
0x140117761  mov     [rsp+0F0h+var_B0], rcx
0x140117766  lea     rcx, aHashid; "HashID"
0x14011776d  mov     [rsp+0F0h+var_B8], r9
0x140117772  lea     r9, aComputingContr_0; "Computing controller response failed"
0x140117779  mov     qword ptr [rsp+0F0h+var_C0], rcx
0x14011777e  mov     rcx, r13
0x140117781  movsxd  rax, ebx
0x140117784  mov     qword ptr [rsp+0F0h+dwFlags], rax
0x140117789  lea     rax, aStatus; "Status"
0x140117790  mov     [rsp+0F0h+pcbResult], rax
0x140117795  call    StorEtwNvmeControllerEvent
0x14011779a  mov     rcx, [rbp+57h+phHash]; hHash
0x14011779e  test    rcx, rcx
0x1401177a1  jz      short loc_1401177AF
0x1401177a3  call    cs:__imp_BCryptDestroyHash
0x1401177aa  nop     dword ptr [rax+rax+00h]
0x1401177af  test    rsi, rsi
0x1401177b2  jz      short loc_1401177C8
0x1401177b4  mov     edx, 414E6152h; Tag
0x1401177b9  mov     rcx, rsi; P
0x1401177bc  call    cs:__imp_ExFreePoolWithTag
0x1401177c3  nop     dword ptr [rax+rax+00h]
0x1401177c8  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1401177cc  test    rcx, rcx
0x1401177cf  jz      short loc_1401177DF
0x1401177d1  xor     edx, edx; dwFlags
0x1401177d3  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1401177da  nop     dword ptr [rax+rax+00h]
0x1401177df  mov     eax, ebx
0x1401177e1  mov     rbx, [rsp+0F0h+arg_8]
0x1401177e9  add     rsp, 0C0h
0x1401177f0  pop     r15
0x1401177f2  pop     r14
0x1401177f4  pop     r13
0x1401177f6  pop     r12
0x1401177f8  pop     rdi
0x1401177f9  pop     rsi
0x1401177fa  pop     rbp
0x1401177fb  retn
```
