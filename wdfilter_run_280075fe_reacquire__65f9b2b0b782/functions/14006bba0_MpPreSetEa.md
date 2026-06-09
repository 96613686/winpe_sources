# MpPreSetEa

- ea: `0x14006bba0`
- end: `0x14006bfaf`
- name: `MpPreSetEa`
- size: `1039`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x1400018a4`
- `0x140002450`
- `0x1400026c0`
- `0x140003460`
- `0x1400034e0`
- `0x1400051bc`
- `0x14000aa0c`
- `0x1400118d0`
- `0x140011900`
- `0x14006bba0`

## import_xrefs

- `ntoskrnl!_stricmp` at `0x14006bcc9`
- `ntoskrnl!_stricmp` at `0x14006bd65`
- `ntoskrnl!_stricmp` at `0x14006bd7f`
- `ntoskrnl!_stricmp` at `0x14006bcc9`
- `ntoskrnl!_stricmp` at `0x14006bd65`
- `ntoskrnl!_stricmp` at `0x14006bd7f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006be70`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006be70`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bf88`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ce93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bf88`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ce93`
- `FLTMGR!FltGetFileSystemType` at `0x14006bc6e`
- `FLTMGR!FltGetFileSystemType` at `0x14006bc6e`
- `FLTMGR!FltSupportsStreamContexts` at `0x14006bc0e`
- `FLTMGR!FltSupportsStreamContexts` at `0x14006bc0e`

## pseudocode

```c
__int64 __fastcall MpPreSetEa(struct _FLT_CALLBACK_DATA *a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v5; // rdi
  const char *v6; // r15
  NTSTATUS v8; // eax
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  const char *EaList; // rsi
  LARGE_INTEGER ByteOffset; // rcx
  unsigned int v12; // ebx
  unsigned int Length; // r14d
  __int64 v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // rdx
  void *PoolWithTag; // rcx
  void *v18; // rcx
  char v19; // [rsp+30h] [rbp-78h]
  char v20; // [rsp+31h] [rbp-77h]
  char v21; // [rsp+32h] [rbp-76h]
  enum _FLT_FILESYSTEM_TYPE FileSystemType; // [rsp+60h] [rbp-48h] BYREF

  v5 = 0;
  v21 = 0;
  v19 = 0;
  FileSystemType = FLT_FSTYPE_UNKNOWN;
  v6 = 0;
  if ( !*((_BYTE *)MpDlpData + 32)
    || a1->Iopb->MinorFunction != 4
    || !MpGetRequestorProcess(a1)
    || !FltSupportsStreamContexts(*(PFILE_OBJECT *)(a2 + 32))
    || a1->Iopb->Parameters.Read.Length < 0xC )
  {
    return 1;
  }
  if ( MpDlpData )
    v20 = *((_BYTE *)MpDlpData + 266);
  else
    v20 = 0;
  v8 = FltGetFileSystemType(*(PVOID *)(a2 + 24), &FileSystemType);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      _mm_lfence();
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        44,
        WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
        (unsigned int)v8);
    }
    FileSystemType = FLT_FSTYPE_UNKNOWN;
  }
  Iopb = a1->Iopb;
  EaList = (const char *)Iopb->Parameters.QueryEa.EaList;
  ByteOffset = Iopb->Parameters.Read.ByteOffset;
  v12 = 1;
  if ( ByteOffset.QuadPart )
  {
    EaList = (*(_BYTE *)(ByteOffset.QuadPart + 10) & 5) != 0
           ? *(const char **)(ByteOffset.QuadPart + 24)
           : (const char *)MmMapLockedPagesSpecifyCache(
                             (PMDL)ByteOffset.QuadPart,
                             0,
                             MmCached,
                             0,
                             0,
                             ExDefaultMdlProtection | 0x40000010u);
    if ( !EaList )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          45,
          (unsigned int)WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
          (unsigned int)KeGetCurrentThread(),
          a1->Iopb->Parameters.Read.ByteOffset.QuadPart);
      goto LABEL_45;
    }
  }
  Length = a1->Iopb->Parameters.Read.Length;
  while ( Length >= 0xC )
  {
    if ( !_stricmp(EaList + 8, "$Kernel.SEC.EndpointDlp") )
    {
      v21 = 1;
      v6 = EaList;
    }
    if ( v20
      && (!_stricmp(EaList + 8, "$Kernel.SEC.MarkOfWeb") || !_stricmp(EaList + 8, "$Kernel.SEC.ApplicationSource")) )
    {
      v19 = 1;
    }
    v14 = *(unsigned int *)EaList;
    if ( !(_DWORD)v14 )
      break;
    Length -= v14;
    EaList += v14;
  }
  if ( !v21 && !v19 || !*((_WORD *)EaList + 3) )
    goto LABEL_45;
  v15 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 1280));
  v5 = v15;
  if ( !v15 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_45;
    v16 = 46;
    goto LABEL_40;
  }
  v15[3] = 0;
  *((_DWORD *)v15 + 9) = FileSystemType;
  *((_BYTE *)v15 + 32) = v19;
  *((_BYTE *)v15 + 33) = v21;
  if ( v21 && v6 )
  {
    *((_DWORD *)v15 + 4) = *((unsigned __int16 *)v6 + 3);
    PoolWithTag = (void *)MpAllocatePoolWithTag(1, *((unsigned __int16 *)v6 + 3), 1634029645);
    v5[3] = PoolWithTag;
    if ( !PoolWithTag )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_45;
      v16 = 47;
LABEL_40:
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v16,
        WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
        KeGetCurrentThread(),
        -1073741670);
      goto LABEL_45;
    }
    memmove(PoolWithTag, &v6[*((unsigned __int8 *)v6 + 5) + 9], *((unsigned __int16 *)v6 + 3));
  }
  *a3 = v5;
  v5 = 0;
  v12 = 5;
LABEL_45:
  if ( v5 )
  {
    v18 = (void *)v5[3];
    if ( v18 )
      ExFreePoolWithTag(v18, 0x6165504Du);
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(MpData + 1280), v5);
  }
  return v12;
}

```

## disassembly

```asm
0x14006bba0  mov     r11, rsp
0x14006bba3  push    rbx
0x14006bba4  push    rsi
0x14006bba5  push    rdi
0x14006bba6  push    r12
0x14006bba8  push    r13
0x14006bbaa  push    r14
0x14006bbac  push    r15
0x14006bbae  sub     rsp, 70h
0x14006bbb2  mov     rax, cs:__security_cookie
0x14006bbb9  xor     rax, rsp
0x14006bbbc  mov     [rsp+0A8h+var_40], rax
0x14006bbc1  mov     [rsp+0A8h+var_58], r8
0x14006bbc6  mov     rbx, rdx
0x14006bbc9  mov     r14, rcx
0x14006bbcc  xor     r13d, r13d
0x14006bbcf  mov     edi, r13d
0x14006bbd2  mov     [r11-68h], r13
0x14006bbd6  mov     [r11-76h], r13b
0x14006bbda  mov     [r11-78h], r13b
0x14006bbde  mov     [r11-48h], r13d
0x14006bbe2  mov     r15d, r13d
0x14006bbe5  mov     rax, cs:MpDlpData
0x14006bbec  mov     cl, [rax+20h]
0x14006bbef  test    cl, cl
0x14006bbf1  jz      short loc_14006BC28
0x14006bbf3  mov     rax, [r14+10h]
0x14006bbf7  cmp     byte ptr [rax+5], 4
0x14006bbfb  jnz     short loc_14006BC28
0x14006bbfd  mov     rcx, r14
0x14006bc00  call    MpGetRequestorProcess
0x14006bc05  test    rax, rax
0x14006bc08  jz      short loc_14006BC28
0x14006bc0a  mov     rcx, [rbx+20h]; FileObject
0x14006bc0e  call    cs:__imp_FltSupportsStreamContexts
0x14006bc15  nop     dword ptr [rax+rax+00h]
0x14006bc1a  test    al, al
0x14006bc1c  jz      short loc_14006BC28
0x14006bc1e  mov     rax, [r14+10h]
0x14006bc22  cmp     dword ptr [rax+18h], 0Ch
0x14006bc26  jnb     short loc_14006BC4B
0x14006bc28  mov     eax, 1
0x14006bc2d  mov     rcx, [rsp+0A8h+var_40]
0x14006bc32  xor     rcx, rsp; StackCookie
0x14006bc35  call    __security_check_cookie
0x14006bc3a  add     rsp, 70h
0x14006bc3e  pop     r15
0x14006bc40  pop     r14
0x14006bc42  pop     r13
0x14006bc44  pop     r12
0x14006bc46  pop     rdi
0x14006bc47  pop     rsi
0x14006bc48  pop     rbx
0x14006bc49  retn
0x14006bc4b  mov     rax, cs:MpDlpData
0x14006bc52  test    rax, rax
0x14006bc55  jz      loc_14006BF29
0x14006bc5b  mov     al, [rax+10Ah]
0x14006bc61  mov     [rsp+0A8h+var_77], al
0x14006bc65  lea     rdx, [rsp+0A8h+FileSystemType]; FileSystemType
0x14006bc6a  mov     rcx, [rbx+18h]; FltObject
0x14006bc6e  call    cs:__imp_FltGetFileSystemType
0x14006bc75  nop     dword ptr [rax+rax+00h]
0x14006bc7a  test    eax, eax
0x14006bc7c  js      loc_14006BF33
0x14006bc82  lea     r12, WPP_GLOBAL_Control
0x14006bc89  mov     rax, [r14+10h]
0x14006bc8d  mov     rsi, [rax+20h]
0x14006bc91  mov     rcx, [rax+28h]; MemoryDescriptorList
0x14006bc95  mov     ebx, 1
0x14006bc9a  test    rcx, rcx
0x14006bc9d  jnz     loc_14006BE48
0x14006bca3  mov     rax, [r14+10h]
0x14006bca7  mov     r14d, [rax+18h]
0x14006bcab  mov     [rsp+0A8h+var_70], r14d
0x14006bcb0  mov     [rsp+0A8h+var_60], rsi
0x14006bcb5  cmp     r14d, 0Ch
0x14006bcb9  jb      short loc_14006BCEE
0x14006bcbb  lea     r13, [rsi+8]
0x14006bcbf  lea     rdx, aKernelSecEndpo; "$Kernel.SEC.EndpointDlp"
0x14006bcc6  mov     rcx, r13; Str1
0x14006bcc9  call    cs:__imp__stricmp
0x14006bcd0  nop     dword ptr [rax+rax+00h]
0x14006bcd5  test    eax, eax
0x14006bcd7  jz      loc_14006BDB5
0x14006bcdd  cmp     [rsp+0A8h+var_77], 0
0x14006bce2  jnz     short loc_14006BD5B
0x14006bce4  mov     eax, [rsi]
0x14006bce6  test    eax, eax
0x14006bce8  jnz     loc_14006BDA0
0x14006bcee  mov     r13b, [rsp+0A8h+var_76]
0x14006bcf3  xor     eax, eax
0x14006bcf5  mov     r14b, [rsp+0A8h+var_78]
0x14006bcfa  test    r13b, r13b
0x14006bcfd  jnz     short loc_14006BD08
0x14006bcff  test    r14b, r14b
0x14006bd02  jz      loc_14006BF1D
0x14006bd08  cmp     ax, [rsi+6]
0x14006bd0c  jz      loc_14006BF1D
0x14006bd12  mov     rcx, cs:MpData
0x14006bd19  add     rcx, 500h; Lookaside
0x14006bd20  call    ExAllocateFromPagedLookasideList
0x14006bd25  mov     rdi, rax
0x14006bd28  mov     [rsp+0A8h+var_68], rax
0x14006bd2d  xor     ecx, ecx
0x14006bd2f  test    rax, rax
0x14006bd32  jnz     loc_14006BDCA
0x14006bd38  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bd3f  cmp     rcx, r12
0x14006bd42  jz      loc_14006BF1D
0x14006bd48  mov     ecx, [rcx+2Ch]
0x14006bd4b  test    bl, cl
0x14006bd4d  jz      loc_14006BF1D
0x14006bd53  lea     edx, [rax+2Eh]
0x14006bd56  jmp     loc_14006BED6
0x14006bd5b  lea     rdx, Str2; "$Kernel.SEC.MarkOfWeb"
0x14006bd62  mov     rcx, r13; Str1
0x14006bd65  call    cs:__imp__stricmp
0x14006bd6c  nop     dword ptr [rax+rax+00h]
0x14006bd71  test    eax, eax
0x14006bd73  jz      short loc_14006BD93
0x14006bd75  lea     rdx, aKernelSecAppli; "$Kernel.SEC.ApplicationSource"
0x14006bd7c  mov     rcx, r13; Str1
0x14006bd7f  call    cs:__imp__stricmp
0x14006bd86  nop     dword ptr [rax+rax+00h]
0x14006bd8b  test    eax, eax
0x14006bd8d  jnz     loc_14006BCE4
0x14006bd93  mov     [rsp+0A8h+var_78], bl
0x14006bd97  mov     [rsp+0A8h+var_74], bl
0x14006bd9b  jmp     loc_14006BCE4
0x14006bda0  sub     r14d, eax
0x14006bda3  mov     [rsp+0A8h+var_70], r14d
0x14006bda8  add     rsi, rax
0x14006bdab  mov     [rsp+0A8h+var_60], rsi
0x14006bdb0  jmp     loc_14006BCB5
0x14006bdb5  mov     [rsp+0A8h+var_76], bl
0x14006bdb9  mov     [rsp+0A8h+var_75], bl
0x14006bdbd  mov     r15, rsi
0x14006bdc0  mov     [rsp+0A8h+var_50], rsi
0x14006bdc5  jmp     loc_14006BCDD
0x14006bdca  mov     [rax+18h], rcx
0x14006bdce  mov     eax, [rsp+0A8h+FileSystemType]
0x14006bdd2  mov     [rdi+24h], eax
0x14006bdd5  mov     [rdi+20h], r14b
0x14006bdd9  mov     [rdi+21h], r13b
0x14006bddd  test    r13b, r13b
0x14006bde0  jz      loc_14006BF15
0x14006bde6  xor     r13d, r13d
0x14006bde9  test    r15, r15
0x14006bdec  jz      short loc_14006BE2E
0x14006bdee  movzx   eax, word ptr [r15+6]
0x14006bdf3  mov     [rdi+10h], eax
0x14006bdf6  movzx   edx, word ptr [r15+6]
0x14006bdfb  mov     r8d, 6165504Dh
0x14006be01  mov     ecx, ebx
0x14006be03  call    MpAllocatePoolWithTag
0x14006be08  mov     rcx, rax; void *
0x14006be0b  mov     [rdi+18h], rax
0x14006be0f  test    rax, rax
0x14006be12  jz      loc_14006BF00
0x14006be18  movzx   r8d, word ptr [r15+6]; Size
0x14006be1d  movzx   edx, byte ptr [r15+5]
0x14006be22  add     rdx, 9
0x14006be26  add     rdx, r15; Src
0x14006be29  call    memmove
0x14006be2e  mov     rax, [rsp+0A8h+var_58]
0x14006be33  mov     [rax], rdi
0x14006be36  mov     rdi, r13
0x14006be39  mov     [rsp+0A8h+var_68], r13
0x14006be3e  mov     ebx, 5
0x14006be43  jmp     loc_14006BF1D
0x14006be48  test    byte ptr [rcx+0Ah], 5
0x14006be4c  jz      short loc_14006BE54
0x14006be4e  mov     rsi, [rcx+18h]
0x14006be52  jmp     short loc_14006BE7F
0x14006be54  mov     eax, cs:ExDefaultMdlProtection
0x14006be5a  or      eax, 40000010h
0x14006be5f  mov     [rsp+0A8h+Priority], eax; Priority
0x14006be63  mov     [rsp+0A8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14006be68  xor     r9d, r9d; RequestedAddress
0x14006be6b  mov     r8d, ebx; CacheType
0x14006be6e  xor     edx, edx; AccessMode
0x14006be70  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006be77  nop     dword ptr [rax+rax+00h]
0x14006be7c  mov     rsi, rax
0x14006be7f  test    rsi, rsi
0x14006be82  jnz     loc_14006BCA3
0x14006be88  mov     rax, cs:WPP_GLOBAL_Control
0x14006be8f  cmp     rax, r12
0x14006be92  jz      loc_14006BF1D
0x14006be98  mov     eax, [rax+2Ch]
0x14006be9b  test    bl, al
0x14006be9d  jz      short loc_14006BF1D
0x14006be9f  mov     r9, gs:188h
0x14006bea8  mov     rax, [r14+10h]
0x14006beac  lea     edx, [rsi+2Dh]
0x14006beaf  mov     rax, [rax+28h]
0x14006beb3  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rax
0x14006beb8  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x14006bebf  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bec6  mov     rcx, [rcx+18h]
0x14006beca  call    WPP_SF_qq
0x14006becf  jmp     short loc_14006BF1D
0x14006bed1  mov     edx, 2Fh ; '/'
0x14006bed6  mov     r9, gs:188h
0x14006bedf  mov     [rsp+0A8h+BugCheckOnFailure], 0C000009Ah
0x14006bee7  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x14006beee  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bef5  mov     rcx, [rcx+18h]
0x14006bef9  call    WPP_SF_qD
0x14006befe  jmp     short loc_14006BF1D
0x14006bf00  mov     rax, cs:WPP_GLOBAL_Control
0x14006bf07  cmp     rax, r12
0x14006bf0a  jz      short loc_14006BF1D
0x14006bf0c  mov     eax, [rax+2Ch]
0x14006bf0f  test    bl, al
0x14006bf11  jz      short loc_14006BF1D
0x14006bf13  jmp     short loc_14006BED1
0x14006bf15  xor     r13d, r13d
0x14006bf18  jmp     loc_14006BE2E
0x14006bf1d  test    rdi, rdi
0x14006bf20  jnz     short loc_14006BF7A
0x14006bf22  mov     eax, ebx
0x14006bf24  jmp     loc_14006BC2D
0x14006bf29  mov     [rsp+0A8h+var_77], r13b
0x14006bf2e  jmp     loc_14006BC65
0x14006bf33  lea     r12, WPP_GLOBAL_Control
0x14006bf3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bf41  cmp     rcx, r12
0x14006bf44  jz      short loc_14006BF70
0x14006bf46  mov     ecx, [rcx+2Ch]
0x14006bf49  test    cl, 2
0x14006bf4c  jz      short loc_14006BF70
0x14006bf4e  lfence
0x14006bf51  mov     edx, 2Ch ; ','
0x14006bf56  mov     r9d, eax
0x14006bf59  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x14006bf60  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bf67  mov     rcx, [rcx+18h]
0x14006bf6b  call    WPP_SF_d
0x14006bf70  mov     [rsp+0A8h+FileSystemType], r13d
0x14006bf75  jmp     loc_14006BC89
0x14006bf7a  mov     rcx, [rdi+18h]; P
0x14006bf7e  test    rcx, rcx
0x14006bf81  jz      short loc_14006BF94
0x14006bf83  mov     edx, 6165504Dh; Tag
0x14006bf88  call    cs:__imp_ExFreePoolWithTag
0x14006bf8f  nop     dword ptr [rax+rax+00h]
0x14006bf94  mov     rcx, cs:MpData
0x14006bf9b  add     rcx, 500h; Lookaside
0x14006bfa2  mov     rdx, rdi; Entry
0x14006bfa5  call    ExFreeToNPagedLookasideList
0x14006bfaa  jmp     loc_14006BF22
0x14008ce70  push    rbx
0x14008ce72  push    rbp
0x14008ce73  sub     rsp, 38h
0x14008ce77  mov     rbp, rdx
0x14008ce7a  mov     rbx, [rbp+40h]
0x14008ce7e  test    rbx, rbx
0x14008ce81  jz      short loc_14008CEB7
0x14008ce83  cmp     qword ptr [rbx+18h], 0
0x14008ce88  jz      short loc_14008CEA0
0x14008ce8a  mov     edx, 6165504Dh; Tag
0x14008ce8f  mov     rcx, [rbx+18h]; P
0x14008ce93  call    cs:__imp_ExFreePoolWithTag
0x14008ce9a  nop     dword ptr [rax+rax+00h]
0x14008ce9f  nop
0x14008cea0  mov     rcx, cs:MpData
0x14008cea7  add     rcx, 500h; Lookaside
0x14008ceae  mov     rdx, rbx; Entry
0x14008ceb1  call    ExFreeToNPagedLookasideList
0x14008ceb6  nop
0x14008ceb7  add     rsp, 38h
0x14008cebb  pop     rbp
0x14008cebc  pop     rbx
0x14008cebd  retn
```
