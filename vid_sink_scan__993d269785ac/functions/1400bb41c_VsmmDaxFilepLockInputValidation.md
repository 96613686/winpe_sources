# VsmmDaxFilepLockInputValidation

- ea: `0x1400bb41c`
- end: `0x1400bba63`
- name: `VsmmDaxFilepLockInputValidation`
- size: `1607`
- prototype: `__int64 __fastcall(__int64, void *, unsigned __int64, __int64, _QWORD *, char *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400ba1d0`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140020dfc`
- `0x140020f70`
- `0x140021650`
- `0x140021800`
- `0x140038630`
- `0x1400ba160`
- `0x1400baab4`
- `0x1400bb41c`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bb4d1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bb4d1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bb8bf`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bb8bf`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400bb53b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400bb53b`
- `ntoskrnl!IoFileObjectType` at `0x1400bb4a8`
- `ntoskrnl!IoFileObjectType` at `0x1400bb51f`
- `ntoskrnl!ZwClose` at `0x1400bb8ab`
- `ntoskrnl!ZwClose` at `0x1400bb8ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb8e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb8e5`
- `ntoskrnl!FsRtlQueryCachedVdl` at `0x1400bb655`
- `ntoskrnl!FsRtlQueryCachedVdl` at `0x1400bb655`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1400bb5e7`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1400bb5e7`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400bb57e`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400bb57e`

## pseudocode

```c
__int64 __fastcall VsmmDaxFilepLockInputValidation(
        __int64 a1,
        void *a2,
        unsigned __int64 a3,
        __int64 a4,
        _QWORD *a5,
        char *a6)
{
  NTSTATUS v9; // eax
  PVOID v10; // r12
  int v11; // edi
  int v12; // eax
  __int64 v13; // r9
  unsigned __int8 v14; // dl
  unsigned __int8 v15; // r8
  int *v16; // rdx
  unsigned __int64 v17; // rsi
  __int64 v18; // rbx
  unsigned __int64 v19; // r14
  __int64 v20; // r13
  HANDLE v21; // rax
  _QWORD *AllNodes; // rax
  _QWORD *v23; // rbx
  int Object; // [rsp+20h] [rbp-E0h]
  char v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v33; // [rsp+70h] [rbp-90h] BYREF
  char *v34; // [rsp+78h] [rbp-88h] BYREF
  __int64 v35; // [rsp+80h] [rbp-80h] BYREF
  __int128 v36; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-68h] BYREF
  _DWORD FsInformation[136]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v39[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v40[16]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v41[16]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int64 *v42; // [rsp+310h] [rbp+210h]
  __int64 v43; // [rsp+318h] [rbp+218h]
  char *v44; // [rsp+320h] [rbp+220h]
  __int64 v45; // [rsp+328h] [rbp+228h]
  char **v46; // [rsp+330h] [rbp+230h]
  __int64 v47; // [rsp+338h] [rbp+238h]
  _QWORD **v48; // [rsp+340h] [rbp+240h]
  __int64 v49; // [rsp+348h] [rbp+248h]
  PVOID *v50; // [rsp+350h] [rbp+250h]
  __int64 v51; // [rsp+358h] [rbp+258h]
  __int64 *v52; // [rsp+360h] [rbp+260h]
  __int64 v53; // [rsp+368h] [rbp+268h]

  v33 = a5;
  v28 = a3;
  v34 = a6;
  v29 = a4;
  v35 = 0;
  v36 = 0;
  IoStatusBlock = 0;
  memset(FsInformation, 0, 0x218u);
  FileHandle = 0;
  DvIntervalInitializeTree(&v36);
  v31 = 0;
  v9 = ObReferenceObjectByHandle(a2, 0x12019Fu, (POBJECT_TYPE)IoFileObjectType, 1, &v31, 0);
  v10 = v31;
  v11 = v9;
  if ( v9 < 0 )
  {
    VidTraceErrorInternal0("VsmmDaxFilepLockInputValidation", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 2491);
    goto LABEL_30;
  }
  v11 = ObOpenObjectByPointer(v31, 0x200u, 0, 0x12019Fu, (POBJECT_TYPE)IoFileObjectType, 0, &FileHandle);
  if ( v11 < 0 )
  {
    VidTraceErrorInternal0("VsmmDaxFilepLockInputValidation", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 2510);
    goto LABEL_30;
  }
  v11 = ZwQueryVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0x218u, FileFsAttributeInformation);
  if ( v11 < 0 )
  {
    VidTraceErrorInternal0("VsmmDaxFilepLockInputValidation", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 2522);
    goto LABEL_30;
  }
  if ( (FsInformation[0] & 0x20000000) != 0 )
  {
    v27 = 0;
    LODWORD(v32) = 0;
    v11 = FsRtlKernelFsControlFile(v10, 590804, 0, 0, &v27, 4, &v32);
    if ( v11 < 0 )
    {
      VidTraceErrorInternal0("VsmmDaxFilepLockInputValidation", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 2557);
      goto LABEL_30;
    }
    v12 = *(unsigned __int8 *)(a1 + 240);
    v26 = 1;
    if ( v27 != v12 )
    {
      v13 = *(_QWORD *)(a1 + 8);
      v14 = 0;
      v15 = *(_BYTE *)(v13 + 2040);
      if ( v15 )
      {
        while ( *(unsigned __int8 *)(v14 + v13 + 2041) != v27 )
        {
          if ( ++v14 >= v15 )
            goto LABEL_14;
        }
        v11 = -1073741811;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v40, "VsmmDaxFilepLockInputValidation");
          tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c");
          LODWORD(v28) = 2575;
          v42 = &v28;
          v16 = &dword_14005042C;
          v26 = *(_BYTE *)(a1 + 240);
          v44 = &v26;
          LODWORD(v29) = v27;
          v46 = (char **)&v29;
          Object = 7;
          v45 = 1;
          v47 = 4;
LABEL_19:
          v43 = 4;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v16, 0, 0, Object, v39);
          goto LABEL_30;
        }
        goto LABEL_30;
      }
    }
  }
  else
  {
    v26 = 0;
    if ( !(unsigned __int8)VsmmDaxFileQueryRegistryIsRegularFileEnabled() )
    {
      v11 = -1073741811;
      VidTraceErrorInternal0("VsmmDaxFilepLockInputValidation", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 2586);
      goto LABEL_30;
    }
  }
LABEL_14:
  v11 = FsRtlQueryCachedVdl(v10, &v35);
  if ( v11 < 0 )
  {
    VidTraceErrorInternal0("VsmmDaxFilepLockInputValidation", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 2599);
    goto LABEL_30;
  }
  v17 = 0;
  v18 = 0;
  v19 = v35 >> 12;
  if ( a3 )
  {
    while ( 1 )
    {
      v20 = v29 + 24 * v18;
      v11 = VsmmDaxFilepFilePageRangeValidate(v19, v20, (__int64)&v36);
      if ( v11 < 0 )
        break;
      v17 += *(_QWORD *)(v20 + 8);
      if ( ++v18 >= v28 )
        goto LABEL_25;
    }
  }
  else
  {
LABEL_25:
    if ( v17 == *(_QWORD *)(a1 + 48) )
    {
      v21 = FileHandle;
      v11 = 0;
      FileHandle = 0;
      *v33 = v21;
      *v34 = v26;
    }
    else
    {
      v11 = -1073741811;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v40, "VsmmDaxFilepLockInputValidation");
        tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c");
        LODWORD(v29) = 2628;
        v42 = (unsigned __int64 *)&v29;
        v16 = (int *)byte_140050329;
        v28 = v17;
        v44 = (char *)&v28;
        Object = 6;
        v45 = 8;
        goto LABEL_19;
      }
    }
  }
LABEL_30:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v10 )
    ObfDereferenceObject(v10);
  AllNodes = (_QWORD *)DvIntervalGetAllNodes(&v36);
  if ( AllNodes )
  {
    do
    {
      v23 = (_QWORD *)AllNodes[6];
      ExFreePoolWithTag(AllNodes, 0x6D4D6456u);
      AllNodes = v23;
    }
    while ( v23 );
  }
  if ( v11 < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v40, "VsmmDaxFilepLockInputValidation");
    tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c");
    LODWORD(v29) = 2659;
    v42 = (unsigned __int64 *)&v29;
    v43 = 4;
    v44 = (char *)&v28;
    v34 = *(char **)(a1 + 24);
    LODWORD(v28) = v11;
    v46 = &v34;
    v33 = *(_QWORD **)(a1 + 40);
    v48 = &v33;
    v31 = *(PVOID *)(a1 + 48);
    v50 = &v31;
    v32 = *(int *)(a1 + 20);
    v52 = &v32;
    v45 = 4;
    v47 = 8;
    v49 = 8;
    v51 = 8;
    v53 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &word_14005036E, 0, 0, 10, v39);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400bb41c  mov     [rsp-8+arg_0], rbx
0x1400bb421  push    rbp
0x1400bb422  push    rsi
0x1400bb423  push    rdi
0x1400bb424  push    r12
0x1400bb426  push    r13
0x1400bb428  push    r14
0x1400bb42a  push    r15
0x1400bb42c  lea     rbp, [rsp-280h]
0x1400bb434  sub     rsp, 380h
0x1400bb43b  mov     rax, cs:__security_cookie
0x1400bb442  xor     rax, rsp
0x1400bb445  mov     [rbp+2B0h+var_40], rax
0x1400bb44c  mov     rax, [rbp+2B0h+arg_20]
0x1400bb453  xorps   xmm0, xmm0
0x1400bb456  mov     [rsp+3B0h+var_340], rax
0x1400bb45b  mov     r13, r8
0x1400bb45e  mov     rax, [rbp+2B0h+arg_28]
0x1400bb465  mov     rbx, rdx
0x1400bb468  mov     [rsp+3B0h+var_368], r8
0x1400bb46d  mov     r15, rcx
0x1400bb470  xor     r14d, r14d
0x1400bb473  mov     [rsp+3B0h+var_338], rax
0x1400bb478  xor     edx, edx; Val
0x1400bb47a  mov     [rsp+3B0h+var_360], r9
0x1400bb47f  mov     r8d, 218h; Size
0x1400bb485  mov     [rbp+2B0h+var_330], r14
0x1400bb489  lea     rcx, [rbp+2B0h+FsInformation]; void *
0x1400bb48d  movups  [rbp+2B0h+var_328], xmm0
0x1400bb491  movups  xmmword ptr [rbp+2B0h+IoStatusBlock], xmm0
0x1400bb495  call    memset
0x1400bb49a  lea     rcx, [rbp+2B0h+var_328]
0x1400bb49e  mov     [rsp+3B0h+FileHandle], r14
0x1400bb4a3  call    DvIntervalInitializeTree
0x1400bb4a8  mov     r8, cs:__imp_IoFileObjectType
0x1400bb4af  lea     rax, [rsp+3B0h+var_350]
0x1400bb4b4  mov     [rsp+3B0h+HandleInformation], r14; HandleInformation
0x1400bb4b9  mov     r9b, 1; AccessMode
0x1400bb4bc  mov     edx, 12019Fh; DesiredAccess
0x1400bb4c1  mov     [rsp+3B0h+var_350], r14
0x1400bb4c6  mov     rcx, rbx; Handle
0x1400bb4c9  mov     [rsp+3B0h+Object], rax; Object
0x1400bb4ce  mov     r8, [r8]; ObjectType
0x1400bb4d1  call    cs:__imp_ObReferenceObjectByHandle
0x1400bb4d8  nop     dword ptr [rax+rax+00h]
0x1400bb4dd  mov     r12, [rsp+3B0h+var_350]
0x1400bb4e2  lea     rbx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bb4e9  lea     rsi, aVsmmdaxfileplo_1; "VsmmDaxFilepLockInputValidation"
0x1400bb4f0  mov     edi, eax
0x1400bb4f2  test    eax, eax
0x1400bb4f4  jns     short loc_1400BB50C
0x1400bb4f6  mov     r8d, 9BBh
0x1400bb4fc  mov     rdx, rbx
0x1400bb4ff  mov     rcx, rsi
0x1400bb502  call    VidTraceErrorInternal0
0x1400bb507  jmp     loc_1400BB8A1
0x1400bb50c  lea     rax, [rsp+3B0h+FileHandle]
0x1400bb511  mov     r9d, 12019Fh; DesiredAccess
0x1400bb517  mov     [rsp+3B0h+Handle], rax; Handle
0x1400bb51c  xor     r8d, r8d; PassedAccessState
0x1400bb51f  mov     rax, cs:__imp_IoFileObjectType
0x1400bb526  mov     edx, 200h; HandleAttributes
0x1400bb52b  mov     byte ptr [rsp+3B0h+HandleInformation], r14b; AccessMode
0x1400bb530  mov     rcx, [rax]
0x1400bb533  mov     [rsp+3B0h+Object], rcx; ObjectType
0x1400bb538  mov     rcx, r12; Object
0x1400bb53b  call    cs:__imp_ObOpenObjectByPointer
0x1400bb542  nop     dword ptr [rax+rax+00h]
0x1400bb547  mov     edi, eax
0x1400bb549  test    eax, eax
0x1400bb54b  jns     short loc_1400BB563
0x1400bb54d  mov     r8d, 9CEh
0x1400bb553  mov     rdx, rbx
0x1400bb556  mov     rcx, rsi
0x1400bb559  call    VidTraceErrorInternal0
0x1400bb55e  jmp     loc_1400BB8A1
0x1400bb563  mov     rcx, [rsp+3B0h+FileHandle]; FileHandle
0x1400bb568  lea     r8, [rbp+2B0h+FsInformation]; FsInformation
0x1400bb56c  mov     r9d, 218h; Length
0x1400bb572  mov     dword ptr [rsp+3B0h+Object], 5; FsInformationClass
0x1400bb57a  lea     rdx, [rbp+2B0h+IoStatusBlock]; IoStatusBlock
0x1400bb57e  call    cs:__imp_ZwQueryVolumeInformationFile
0x1400bb585  nop     dword ptr [rax+rax+00h]
0x1400bb58a  mov     edi, eax
0x1400bb58c  test    eax, eax
0x1400bb58e  jns     short loc_1400BB5A6
0x1400bb590  mov     r8d, 9DAh
0x1400bb596  mov     rdx, rbx
0x1400bb599  mov     rcx, rsi
0x1400bb59c  call    VidTraceErrorInternal0
0x1400bb5a1  jmp     loc_1400BB8A1
0x1400bb5a6  test    [rbp+2B0h+FsInformation], 20000000h
0x1400bb5ad  jz      loc_1400BB75E
0x1400bb5b3  lea     rax, [rsp+3B0h+var_348]
0x1400bb5b8  mov     [rsp+3B0h+var_36C], r14d
0x1400bb5bd  mov     [rsp+3B0h+Handle], rax
0x1400bb5c2  xor     r9d, r9d
0x1400bb5c5  lea     rax, [rsp+3B0h+var_36C]
0x1400bb5ca  mov     dword ptr [rsp+3B0h+HandleInformation], 4
0x1400bb5d2  xor     r8d, r8d
0x1400bb5d5  mov     [rsp+3B0h+Object], rax
0x1400bb5da  mov     edx, 903D4h
0x1400bb5df  mov     dword ptr [rsp+3B0h+var_348], r14d
0x1400bb5e4  mov     rcx, r12
0x1400bb5e7  call    cs:__imp_FsRtlKernelFsControlFile
0x1400bb5ee  nop     dword ptr [rax+rax+00h]
0x1400bb5f3  mov     edi, eax
0x1400bb5f5  test    eax, eax
0x1400bb5f7  jns     short loc_1400BB60F
0x1400bb5f9  mov     r8d, 9FDh
0x1400bb5ff  mov     rdx, rbx
0x1400bb602  mov     rcx, rsi
0x1400bb605  call    VidTraceErrorInternal0
0x1400bb60a  jmp     loc_1400BB8A1
0x1400bb60f  movzx   eax, byte ptr [r15+0F0h]
0x1400bb617  mov     [rsp+3B0h+var_370], 1
0x1400bb61c  cmp     [rsp+3B0h+var_36C], eax
0x1400bb620  jz      short loc_1400BB64E
0x1400bb622  mov     r9, [r15+8]
0x1400bb626  mov     dl, r14b
0x1400bb629  mov     r8b, [r9+7F8h]
0x1400bb630  test    r8b, r8b
0x1400bb633  jz      short loc_1400BB64E
0x1400bb635  movzx   eax, dl
0x1400bb638  movzx   ecx, byte ptr [rax+r9+7F9h]
0x1400bb641  cmp     ecx, [rsp+3B0h+var_36C]
0x1400bb645  jz      short loc_1400BB681
0x1400bb647  inc     dl
0x1400bb649  cmp     dl, r8b
0x1400bb64c  jb      short loc_1400BB635
0x1400bb64e  lea     rdx, [rbp+2B0h+var_330]
0x1400bb652  mov     rcx, r12
0x1400bb655  call    cs:__imp_FsRtlQueryCachedVdl
0x1400bb65c  nop     dword ptr [rax+rax+00h]
0x1400bb661  mov     edi, eax
0x1400bb663  test    eax, eax
0x1400bb665  jns     loc_1400BB78B
0x1400bb66b  mov     r8d, 0A27h
0x1400bb671  mov     rdx, rbx
0x1400bb674  mov     rcx, rsi
0x1400bb677  call    VidTraceErrorInternal0
0x1400bb67c  jmp     loc_1400BB8A1
0x1400bb681  mov     eax, cs:dword_140064110
0x1400bb687  mov     edi, 0C000000Dh
0x1400bb68c  cmp     eax, 2
0x1400bb68f  jbe     loc_1400BB8A1
0x1400bb695  mov     edx, 100h
0x1400bb69a  lea     rcx, dword_140064110
0x1400bb6a1  call    _tlgKeywordOn
0x1400bb6a6  test    al, al
0x1400bb6a8  jz      loc_1400BB8A1
0x1400bb6ae  mov     rdx, rsi
0x1400bb6b1  lea     rcx, [rbp+2B0h+var_C0]
0x1400bb6b8  call    _tlgCreate1Sz_char
0x1400bb6bd  mov     rdx, rbx
0x1400bb6c0  lea     rcx, [rbp+2B0h+var_B0]
0x1400bb6c7  call    _tlgCreate1Sz_char
0x1400bb6cc  lea     rax, [rsp+3B0h+var_368]
0x1400bb6d1  mov     dword ptr [rsp+3B0h+var_368], 0A0Fh
0x1400bb6d9  mov     [rbp+2B0h+var_A0], rax
0x1400bb6e0  lea     rdx, dword_14005042C
0x1400bb6e7  mov     al, [r15+0F0h]
0x1400bb6ee  mov     [rsp+3B0h+var_370], al
0x1400bb6f2  lea     rax, [rsp+3B0h+var_370]
0x1400bb6f7  mov     [rbp+2B0h+var_90], rax
0x1400bb6fe  mov     eax, [rsp+3B0h+var_36C]
0x1400bb702  mov     dword ptr [rsp+3B0h+var_360], eax
0x1400bb706  lea     rax, [rsp+3B0h+var_360]
0x1400bb70b  mov     [rbp+2B0h+var_80], rax
0x1400bb712  lea     rax, [rbp+2B0h+var_E0]
0x1400bb719  mov     [rsp+3B0h+HandleInformation], rax
0x1400bb71e  mov     dword ptr [rsp+3B0h+Object], 7
0x1400bb726  mov     [rbp+2B0h+var_88], 1
0x1400bb731  mov     [rbp+2B0h+var_78], 4
0x1400bb73c  xor     r9d, r9d
0x1400bb73f  mov     [rbp+2B0h+var_98], 4
0x1400bb74a  xor     r8d, r8d
0x1400bb74d  lea     rcx, dword_140064110
0x1400bb754  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400bb759  jmp     loc_1400BB8A1
0x1400bb75e  mov     [rsp+3B0h+var_370], r14b
0x1400bb763  call    VsmmDaxFileQueryRegistryIsRegularFileEnabled
0x1400bb768  test    al, al
0x1400bb76a  jnz     loc_1400BB64E
0x1400bb770  mov     edi, 0C000000Dh
0x1400bb775  mov     r8d, 0A1Ah
0x1400bb77b  mov     rdx, rbx
0x1400bb77e  mov     rcx, rsi
0x1400bb781  call    VidTraceErrorInternal0
0x1400bb786  jmp     loc_1400BB8A1
0x1400bb78b  mov     rsi, r14
0x1400bb78e  xor     ebx, ebx
0x1400bb790  mov     r14, [rbp+2B0h+var_330]
0x1400bb794  sar     r14, 0Ch
0x1400bb798  test    r13, r13
0x1400bb79b  jz      short loc_1400BB7D1
0x1400bb79d  mov     rcx, [rsp+3B0h+var_360]
0x1400bb7a2  lea     rax, [rbx+rbx*2]
0x1400bb7a6  lea     r8, [rbp+2B0h+var_328]
0x1400bb7aa  lea     r13, [rcx+rax*8]
0x1400bb7ae  mov     rcx, r14
0x1400bb7b1  mov     rdx, r13
0x1400bb7b4  call    VsmmDaxFilepFilePageRangeValidate
0x1400bb7b9  mov     edi, eax
0x1400bb7bb  test    eax, eax
0x1400bb7bd  js      loc_1400BB8A1
0x1400bb7c3  add     rsi, [r13+8]
0x1400bb7c7  inc     rbx
0x1400bb7ca  cmp     rbx, [rsp+3B0h+var_368]
0x1400bb7cf  jb      short loc_1400BB79D
0x1400bb7d1  cmp     rsi, [r15+30h]
0x1400bb7d5  jz      loc_1400BB87E
0x1400bb7db  mov     eax, cs:dword_140064110
0x1400bb7e1  mov     edi, 0C000000Dh
0x1400bb7e6  cmp     eax, 2
0x1400bb7e9  jbe     loc_1400BB8A1
0x1400bb7ef  mov     edx, 100h
0x1400bb7f4  lea     rcx, dword_140064110
0x1400bb7fb  call    _tlgKeywordOn
0x1400bb800  test    al, al
0x1400bb802  jz      loc_1400BB8A1
0x1400bb808  lea     rdx, aVsmmdaxfileplo_1; "VsmmDaxFilepLockInputValidation"
0x1400bb80f  lea     rcx, [rbp+2B0h+var_C0]
0x1400bb816  call    _tlgCreate1Sz_char
0x1400bb81b  lea     rdx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bb822  lea     rcx, [rbp+2B0h+var_B0]
0x1400bb829  call    _tlgCreate1Sz_char
0x1400bb82e  lea     rax, [rsp+3B0h+var_360]
0x1400bb833  mov     dword ptr [rsp+3B0h+var_360], 0A44h
0x1400bb83b  mov     [rbp+2B0h+var_A0], rax
0x1400bb842  lea     rdx, byte_140050329
0x1400bb849  lea     rax, [rsp+3B0h+var_368]
0x1400bb84e  mov     [rsp+3B0h+var_368], rsi
0x1400bb853  mov     [rbp+2B0h+var_90], rax
0x1400bb85a  lea     rax, [rbp+2B0h+var_E0]
0x1400bb861  mov     [rsp+3B0h+HandleInformation], rax
0x1400bb866  mov     dword ptr [rsp+3B0h+Object], 6
0x1400bb86e  mov     [rbp+2B0h+var_88], 8
0x1400bb879  jmp     loc_1400BB73C
0x1400bb87e  mov     rax, [rsp+3B0h+FileHandle]
0x1400bb883  xor     r14d, r14d
0x1400bb886  mov     rcx, [rsp+3B0h+var_340]
0x1400bb88b  mov     edi, r14d
0x1400bb88e  mov     [rsp+3B0h+FileHandle], r14
0x1400bb893  mov     [rcx], rax
0x1400bb896  mov     rcx, [rsp+3B0h+var_338]
0x1400bb89b  mov     al, [rsp+3B0h+var_370]
0x1400bb89f  mov     [rcx], al
0x1400bb8a1  mov     rcx, [rsp+3B0h+FileHandle]; Handle
0x1400bb8a6  test    rcx, rcx
0x1400bb8a9  jz      short loc_1400BB8B7
0x1400bb8ab  call    cs:__imp_ZwClose
0x1400bb8b2  nop     dword ptr [rax+rax+00h]
0x1400bb8b7  test    r12, r12
0x1400bb8ba  jz      short loc_1400BB8CB
0x1400bb8bc  mov     rcx, r12; Object
0x1400bb8bf  call    cs:__imp_ObfDereferenceObject
0x1400bb8c6  nop     dword ptr [rax+rax+00h]
0x1400bb8cb  lea     rcx, [rbp+2B0h+var_328]
0x1400bb8cf  call    DvIntervalGetAllNodes
0x1400bb8d4  test    rax, rax
0x1400bb8d7  jz      short loc_1400BB8F9
0x1400bb8d9  mov     rbx, [rax+30h]
0x1400bb8dd  mov     edx, 6D4D6456h; Tag
0x1400bb8e2  mov     rcx, rax; P
0x1400bb8e5  call    cs:__imp_ExFreePoolWithTag
0x1400bb8ec  nop     dword ptr [rax+rax+00h]
0x1400bb8f1  mov     rax, rbx
0x1400bb8f4  test    rbx, rbx
0x1400bb8f7  jnz     short loc_1400BB8D9
0x1400bb8f9  test    edi, edi
0x1400bb8fb  jns     loc_1400BBA36
0x1400bb901  mov     eax, cs:dword_140064110
0x1400bb907  cmp     eax, 2
0x1400bb90a  jbe     loc_1400BBA36
0x1400bb910  mov     edx, 100h
0x1400bb915  lea     rcx, dword_140064110
0x1400bb91c  call    _tlgKeywordOn
0x1400bb921  test    al, al
0x1400bb923  jz      loc_1400BBA36
0x1400bb929  lea     rdx, aVsmmdaxfileplo_1; "VsmmDaxFilepLockInputValidation"
0x1400bb930  lea     rcx, [rbp+2B0h+var_C0]
0x1400bb937  call    _tlgCreate1Sz_char
0x1400bb93c  lea     rdx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bb943  lea     rcx, [rbp+2B0h+var_B0]
0x1400bb94a  call    _tlgCreate1Sz_char
0x1400bb94f  lea     rax, [rsp+3B0h+var_360]
0x1400bb954  mov     dword ptr [rsp+3B0h+var_360], 0A63h
0x1400bb95c  mov     [rbp+2B0h+var_A0], rax
0x1400bb963  lea     rdx, word_14005036E
0x1400bb96a  lea     rax, [rsp+3B0h+var_368]
0x1400bb96f  mov     [rbp+2B0h+var_98], 4
0x1400bb97a  mov     [rbp+2B0h+var_90], rax
0x1400bb981  lea     rcx, dword_140064110
0x1400bb988  mov     rax, [r15+18h]
0x1400bb98c  xor     r9d, r9d
0x1400bb98f  mov     [rsp+3B0h+var_338], rax
0x1400bb994  xor     r8d, r8d
0x1400bb997  lea     rax, [rsp+3B0h+var_338]
0x1400bb99c  mov     dword ptr [rsp+3B0h+var_368], edi
  ... truncated ...
```
