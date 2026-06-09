# MpFreeGlobals

- ea: `0x14007bca4`
- end: `0x14007be87`
- name: `MpFreeGlobals`
- size: `483`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14007bef0`
- `0x14008f314`

## callees

- `0x140066180`
- `0x14007bb64`
- `0x14007bca4`
- `0x140083fb8`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14007be1c`
- `ntoskrnl!ExDeleteResourceLite` at `0x14007be36`
- `ntoskrnl!ExDeleteResourceLite` at `0x14007be50`
- `ntoskrnl!ExDeleteResourceLite` at `0x14007be1c`
- `ntoskrnl!ExDeleteResourceLite` at `0x14007be36`
- `ntoskrnl!ExDeleteResourceLite` at `0x14007be50`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bcc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bcfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bd1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bd3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bd5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bd7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bda0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bdc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bde5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007be74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bcc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bcfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bd1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bd3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bd5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bd7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bda0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bdc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bde5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007be74`

## pseudocode

```c
void MpFreeGlobals()
{
  void *v0; // rcx
  void *v1; // rcx
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  void *v10; // rcx

  v0 = *(void **)(MpData + 3264);
  if ( v0 )
    ExFreePoolWithTag(v0, 0x6E76504Du);
  MpFreeCsrssHookData(*(PVOID *)(MpData + 2480));
  v1 = *(void **)(MpData + 2424);
  if ( v1 )
    ExFreePoolWithTag(v1, 0x6473504Du);
  v2 = *(void **)(MpData + 2376);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x6473504Du);
  v3 = *(void **)(MpData + 2384);
  if ( v3 )
    ExFreePoolWithTag(v3, 0x6473504Du);
  v4 = *(void **)(MpData + 2400);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x6473504Du);
  v5 = *(void **)(MpData + 2408);
  if ( v5 )
    ExFreePoolWithTag(v5, 0x6473504Du);
  v6 = *(void **)(MpData + 2392);
  if ( v6 )
    ExFreePoolWithTag(v6, 0x6473504Du);
  v7 = *(void **)(MpData + 2416);
  if ( v7 )
    ExFreePoolWithTag(v7, 0x6473504Du);
  v8 = *(void **)(MpData + 584);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x6772504Du);
  v9 = *(_QWORD *)(MpData + 4016);
  if ( v9 )
    MpFreeString(v9);
  MpDeleteLookasideLists();
  ExDeleteResourceLite((PERESOURCE)(MpData + 3048));
  ExDeleteResourceLite((PERESOURCE)(MpData + 3152));
  ExDeleteResourceLite((PERESOURCE)(MpData + 752));
  v10 = *(void **)(MpData + 3936);
  if ( v10 )
    ExFreePoolWithTag(v10, 0x6E76504Du);
}

```

## disassembly

```asm
0x14007bca4  push    rbx
0x14007bca6  sub     rsp, 20h
0x14007bcaa  mov     rax, cs:MpData
0x14007bcb1  mov     rcx, [rax+0CC0h]; P
0x14007bcb8  test    rcx, rcx
0x14007bcbb  jz      short loc_14007BCCE
0x14007bcbd  mov     edx, 6E76504Dh; Tag
0x14007bcc2  call    cs:__imp_ExFreePoolWithTag
0x14007bcc9  nop     dword ptr [rax+rax+00h]
0x14007bcce  mov     rcx, cs:MpData
0x14007bcd5  mov     rcx, [rcx+9B0h]; P
0x14007bcdc  call    MpFreeCsrssHookData
0x14007bce1  mov     rax, cs:MpData
0x14007bce8  mov     ebx, 6473504Dh
0x14007bced  mov     rcx, [rax+978h]; P
0x14007bcf4  test    rcx, rcx
0x14007bcf7  jz      short loc_14007BD07
0x14007bcf9  mov     edx, ebx; Tag
0x14007bcfb  call    cs:__imp_ExFreePoolWithTag
0x14007bd02  nop     dword ptr [rax+rax+00h]
0x14007bd07  mov     rax, cs:MpData
0x14007bd0e  mov     rcx, [rax+948h]; P
0x14007bd15  test    rcx, rcx
0x14007bd18  jz      short loc_14007BD28
0x14007bd1a  mov     edx, ebx; Tag
0x14007bd1c  call    cs:__imp_ExFreePoolWithTag
0x14007bd23  nop     dword ptr [rax+rax+00h]
0x14007bd28  mov     rax, cs:MpData
0x14007bd2f  mov     rcx, [rax+950h]; P
0x14007bd36  test    rcx, rcx
0x14007bd39  jz      short loc_14007BD49
0x14007bd3b  mov     edx, ebx; Tag
0x14007bd3d  call    cs:__imp_ExFreePoolWithTag
0x14007bd44  nop     dword ptr [rax+rax+00h]
0x14007bd49  mov     rax, cs:MpData
0x14007bd50  mov     rcx, [rax+960h]; P
0x14007bd57  test    rcx, rcx
0x14007bd5a  jz      short loc_14007BD6A
0x14007bd5c  mov     edx, ebx; Tag
0x14007bd5e  call    cs:__imp_ExFreePoolWithTag
0x14007bd65  nop     dword ptr [rax+rax+00h]
0x14007bd6a  mov     rax, cs:MpData
0x14007bd71  mov     rcx, [rax+968h]; P
0x14007bd78  test    rcx, rcx
0x14007bd7b  jz      short loc_14007BD8B
0x14007bd7d  mov     edx, ebx; Tag
0x14007bd7f  call    cs:__imp_ExFreePoolWithTag
0x14007bd86  nop     dword ptr [rax+rax+00h]
0x14007bd8b  mov     rax, cs:MpData
0x14007bd92  mov     rcx, [rax+958h]; P
0x14007bd99  test    rcx, rcx
0x14007bd9c  jz      short loc_14007BDAC
0x14007bd9e  mov     edx, ebx; Tag
0x14007bda0  call    cs:__imp_ExFreePoolWithTag
0x14007bda7  nop     dword ptr [rax+rax+00h]
0x14007bdac  mov     rax, cs:MpData
0x14007bdb3  mov     rcx, [rax+970h]; P
0x14007bdba  test    rcx, rcx
0x14007bdbd  jz      short loc_14007BDCD
0x14007bdbf  mov     edx, ebx; Tag
0x14007bdc1  call    cs:__imp_ExFreePoolWithTag
0x14007bdc8  nop     dword ptr [rax+rax+00h]
0x14007bdcd  mov     rax, cs:MpData
0x14007bdd4  mov     rcx, [rax+248h]; P
0x14007bddb  test    rcx, rcx
0x14007bdde  jz      short loc_14007BDF1
0x14007bde0  mov     edx, 6772504Dh; Tag
0x14007bde5  call    cs:__imp_ExFreePoolWithTag
0x14007bdec  nop     dword ptr [rax+rax+00h]
0x14007bdf1  mov     rax, cs:MpData
0x14007bdf8  mov     rcx, [rax+0FB0h]
0x14007bdff  test    rcx, rcx
0x14007be02  jz      short loc_14007BE09
0x14007be04  call    MpFreeString
0x14007be09  call    MpDeleteLookasideLists
0x14007be0e  mov     rcx, cs:MpData
0x14007be15  add     rcx, 0BE8h; Resource
0x14007be1c  call    cs:__imp_ExDeleteResourceLite
0x14007be23  nop     dword ptr [rax+rax+00h]
0x14007be28  mov     rcx, cs:MpData
0x14007be2f  add     rcx, 0C50h; Resource
0x14007be36  call    cs:__imp_ExDeleteResourceLite
0x14007be3d  nop     dword ptr [rax+rax+00h]
0x14007be42  mov     rcx, cs:MpData
0x14007be49  add     rcx, 2F0h; Resource
0x14007be50  call    cs:__imp_ExDeleteResourceLite
0x14007be57  nop     dword ptr [rax+rax+00h]
0x14007be5c  mov     rax, cs:MpData
0x14007be63  mov     rcx, [rax+0F60h]; P
0x14007be6a  test    rcx, rcx
0x14007be6d  jz      short loc_14007BE80
0x14007be6f  mov     edx, 6E76504Dh; Tag
0x14007be74  call    cs:__imp_ExFreePoolWithTag
0x14007be7b  nop     dword ptr [rax+rax+00h]
0x14007be80  add     rsp, 20h
0x14007be84  pop     rbx
0x14007be85  retn
```
