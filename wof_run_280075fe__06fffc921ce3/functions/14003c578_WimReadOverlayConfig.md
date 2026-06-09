# WimReadOverlayConfig

- ea: `0x14003c578`
- end: `0x14003ca5a`
- name: `WimReadOverlayConfig`
- size: `1250`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1400227a0`
- `0x14002ad28`
- `0x14002b77c`
- `0x14002ba8c`
- `0x14002d3d4`

## callees

- `0x14000d3b8`
- `0x14000fb90`
- `0x140010010`
- `0x140010078`
- `0x140011560`
- `0x14002b028`
- `0x14002b9c0`
- `0x14002c270`
- `0x14003c578`
- `0x14003ca60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003c725`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c9c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c725`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c9c5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c693`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c8a5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c693`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c8a5`
- `ntoskrnl!ObfDereferenceObject` at `0x14003ca0f`
- `ntoskrnl!ObfDereferenceObject` at `0x14003ca0f`
- `FLTMGR!FltReadFile` at `0x14003c912`
- `FLTMGR!FltReadFile` at `0x14003c912`
- `FLTMGR!FltQueryInformationFile` at `0x14003c7d5`
- `FLTMGR!FltQueryInformationFile` at `0x14003c7d5`
- `FLTMGR!FltClose` at `0x14003ca24`
- `FLTMGR!FltClose` at `0x14003ca24`

## string_xrefs

- `0x14003c5d2`: `WimOverlay.dat`
- `0x14003c6fb`: `WimOverlay.dat`
- `0x14003c61a`: `WimOverlay.new`

## pseudocode

```c
__int64 __fastcall WimReadOverlayConfig(__int64 a1, char a2, HANDLE *a3, PFILE_OBJECT *a4, _QWORD *a5, __int64 a6)
{
  int v10; // eax
  NTSTATUS EmptyOverlayConfig; // ebx
  int v12; // eax
  char *PoolWithTag; // rax
  void *v14; // rdi
  __int64 v15; // r9
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  ULONG v18; // edi
  PVOID v19; // rsi
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  _DWORD *v23; // rax
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-29h] BYREF
  ULONG BytesRead; // [rsp+58h] [rbp-21h] BYREF
  HANDLE FileHandle; // [rsp+60h] [rbp-19h] BYREF
  __int64 v28; // [rsp+68h] [rbp-11h]
  __int128 FileInformation; // [rsp+70h] [rbp-9h] BYREF
  __int64 v30; // [rsp+80h] [rbp+7h]

  v30 = 0;
  BytesRead = 0;
  FileHandle = 0;
  FileObject = 0;
  v28 = a6;
  FileInformation = 0;
  v10 = WimOpenOverlayConfig(a1, L"WimOverlay.dat", 0, &FileHandle, &FileObject);
  EmptyOverlayConfig = v10;
  if ( v10 >= 0 )
    goto LABEL_29;
  if ( v10 != -1073741772 && v10 != -1073741766 )
  {
LABEL_24:
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
      goto LABEL_65;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_Sld(WPP_GLOBAL_Control->AttachedDevice);
LABEL_27:
    if ( EmptyOverlayConfig < 0 )
      goto LABEL_65;
    goto LABEL_61;
  }
  v12 = WimOpenOverlayConfig(a1, L"WimOverlay.new", 0, &FileHandle, &FileObject);
  EmptyOverlayConfig = v12;
  if ( a2 && (v12 == -1073741772 || v12 == -1073741766) )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, a1 + 64);
    EmptyOverlayConfig = WimAllocateEmptyOverlayConfig(a5, a6);
    goto LABEL_27;
  }
  if ( v12 < 0 )
  {
    if ( v12 == -1073741772 )
    {
      EmptyOverlayConfig = -1073741809;
      goto LABEL_65;
    }
    goto LABEL_24;
  }
  PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, 0x30u, 0x66637077u);
  v14 = PoolWithTag;
  if ( !PoolWithTag )
  {
    v15 = 3221225626LL;
    EmptyOverlayConfig = -1073741670;
    v16 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_65;
    v17 = 29;
    goto LABEL_16;
  }
  *PoolWithTag = 1;
  *((_QWORD *)PoolWithTag + 1) = 0;
  *((_DWORD *)PoolWithTag + 4) = 28;
  *(_OWORD *)(PoolWithTag + 20) = *(_OWORD *)L"WimOverlay.dat";
  *((_OWORD *)PoolWithTag + 2) = *(_OWORD *)L"rlay.dat";
  EmptyOverlayConfig = WimRenameOnSystemThread(*(_QWORD *)(a1 + 120), FileObject, PoolWithTag);
  ExFreePoolWithTag(v14, 0);
  if ( (int)(EmptyOverlayConfig + 0x80000000) >= 0 && EmptyOverlayConfig != -1073741662 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_65;
    v17 = 30;
LABEL_33:
    v15 = (unsigned int)EmptyOverlayConfig;
    goto LABEL_16;
  }
LABEL_29:
  EmptyOverlayConfig = FltQueryInformationFile(
                         *(PFLT_INSTANCE *)(a1 + 120),
                         FileObject,
                         &FileInformation,
                         0x18u,
                         FileStandardInformation,
                         0);
  if ( EmptyOverlayConfig < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_65;
    v17 = 32;
    goto LABEL_33;
  }
  v18 = DWORD2(FileInformation);
  if ( *((__int64 *)&FileInformation + 1) > 0x200000 )
  {
    v15 = 3221226180LL;
    EmptyOverlayConfig = -1073741116;
    v16 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_65;
    v17 = 33;
    goto LABEL_16;
  }
  if ( DWORD2(FileInformation) >= 0x18 )
  {
    v19 = ExAllocatePoolWithTag(PagedPool, DWORD2(FileInformation), 0x66637077u);
    if ( !v19 )
    {
      v15 = 3221225626LL;
      EmptyOverlayConfig = -1073741670;
      v16 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_65;
      v17 = 35;
LABEL_16:
      WPP_SF_d(v16->AttachedDevice, v17, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, v15);
      goto LABEL_65;
    }
    EmptyOverlayConfig = FltReadFile(*(PFLT_INSTANCE *)(a1 + 120), FileObject, 0, v18, v19, 0, &BytesRead, 0, 0);
    if ( EmptyOverlayConfig >= 0 )
    {
      if ( BytesRead == v18 )
      {
        EmptyOverlayConfig = WimpValidateOverlayConfig(v19, v18);
        if ( EmptyOverlayConfig >= 0 )
        {
          v23 = (_DWORD *)v28;
          *a5 = v19;
          *v23 = v18;
LABEL_61:
          if ( a3 )
          {
            *a3 = FileHandle;
            FileHandle = 0;
          }
          if ( a4 )
          {
            *a4 = FileObject;
            FileObject = 0;
          }
          goto LABEL_65;
        }
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, a1 + 64);
LABEL_59:
        ExFreePoolWithTag(v19, 0);
        goto LABEL_65;
      }
      v22 = 3221226180LL;
      EmptyOverlayConfig = -1073741116;
      v20 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_59;
      v21 = 37;
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_59;
      v21 = 36;
      v22 = (unsigned int)EmptyOverlayConfig;
    }
    WPP_SF_d(v20->AttachedDevice, v21, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, v22);
    goto LABEL_59;
  }
  EmptyOverlayConfig = -1073741116;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_dd(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
      DWORD2(FileInformation),
      -1073741116);
LABEL_65:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)EmptyOverlayConfig;
}

```

## disassembly

```asm
0x14003c578  mov     [rsp-8+arg_8], rbx
0x14003c57d  push    rbp
0x14003c57e  push    rsi
0x14003c57f  push    rdi
0x14003c580  push    r12
0x14003c582  push    r13
0x14003c584  push    r14
0x14003c586  push    r15
0x14003c588  lea     rbp, [rsp-17h]
0x14003c58d  sub     rsp, 90h
0x14003c594  mov     rax, cs:__security_cookie
0x14003c59b  xor     rax, rsp
0x14003c59e  mov     [rbp+47h+var_38], rax
0x14003c5a2  mov     rsi, [rbp+47h+arg_28]
0x14003c5a6  xor     eax, eax
0x14003c5a8  mov     r13, [rbp+47h+arg_20]
0x14003c5ac  mov     r15, r9
0x14003c5af  mov     [rbp+47h+var_40], rax
0x14003c5b3  lea     r9, [rbp+47h+FileHandle]
0x14003c5b7  mov     [rbp+47h+var_68], eax
0x14003c5ba  mov     r12, r8
0x14003c5bd  mov     [rbp+47h+FileHandle], rax
0x14003c5c1  xorps   xmm0, xmm0
0x14003c5c4  mov     [rbp+47h+FileObject], rax
0x14003c5c8  xor     r8d, r8d
0x14003c5cb  lea     rax, [rbp+47h+FileObject]
0x14003c5cf  movzx   edi, dl
0x14003c5d2  lea     rdx, aWimoverlayDat; "WimOverlay.dat"
0x14003c5d9  mov     qword ptr [rsp+0C0h+FileInformationClass], rax
0x14003c5de  mov     r14, rcx
0x14003c5e1  mov     [rbp+47h+var_58], rsi
0x14003c5e5  movups  [rbp+47h+FileInformation], xmm0
0x14003c5e9  call    WimOpenOverlayConfig
0x14003c5ee  mov     ebx, eax
0x14003c5f0  test    eax, eax
0x14003c5f2  jns     loc_14003C7B2
0x14003c5f8  cmp     eax, 0C0000034h
0x14003c5fd  jz      short loc_14003C60A
0x14003c5ff  cmp     eax, 0C000003Ah
0x14003c604  jnz     loc_14003C77C
0x14003c60a  lea     rax, [rbp+47h+FileObject]
0x14003c60e  xor     r8d, r8d
0x14003c611  lea     r9, [rbp+47h+FileHandle]
0x14003c615  mov     qword ptr [rsp+0C0h+FileInformationClass], rax
0x14003c61a  lea     rdx, aWimoverlayNew; "WimOverlay.new"
0x14003c621  mov     rcx, r14
0x14003c624  call    WimOpenOverlayConfig
0x14003c629  mov     ebx, eax
0x14003c62b  test    dil, dil
0x14003c62e  jz      short loc_14003C67D
0x14003c630  cmp     eax, 0C0000034h
0x14003c635  jz      short loc_14003C63E
0x14003c637  cmp     eax, 0C000003Ah
0x14003c63c  jnz     short loc_14003C67D
0x14003c63e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c645  mov     eax, [rcx+2Ch]
0x14003c648  test    al, 8
0x14003c64a  jz      short loc_14003C66B
0x14003c64c  cmp     byte ptr [rcx+29h], 4
0x14003c650  jb      short loc_14003C66B
0x14003c652  mov     rcx, [rcx+18h]
0x14003c656  lea     r9, [r14+40h]
0x14003c65a  mov     edx, 1Ch
0x14003c65f  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003c666  call    WPP_SF_Z
0x14003c66b  mov     rdx, rsi
0x14003c66e  mov     rcx, r13
0x14003c671  call    WimAllocateEmptyOverlayConfig
0x14003c676  mov     ebx, eax
0x14003c678  jmp     loc_14003C7A5
0x14003c67d  test    eax, eax
0x14003c67f  js      loc_14003C76D
0x14003c685  mov     edx, 30h ; '0'; NumberOfBytes
0x14003c68a  mov     r8d, 66637077h; Tag
0x14003c690  lea     ecx, [rdx-2Fh]; PoolType
0x14003c693  call    cs:__imp_ExAllocatePoolWithTag
0x14003c69a  nop     dword ptr [rax+rax+00h]
0x14003c69f  mov     rdi, rax
0x14003c6a2  test    rax, rax
0x14003c6a5  jnz     short loc_14003C6E6
0x14003c6a7  mov     r9d, 0C000009Ah
0x14003c6ad  mov     ebx, r9d
0x14003c6b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c6b7  test    dword ptr [rcx+2Ch], 400h
0x14003c6be  jz      loc_14003CA06
0x14003c6c4  cmp     byte ptr [rcx+29h], 2
0x14003c6c8  jb      loc_14003CA06
0x14003c6ce  lea     edx, [rax+1Dh]
0x14003c6d1  mov     rcx, [rcx+18h]
0x14003c6d5  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003c6dc  call    WPP_SF_d
0x14003c6e1  jmp     loc_14003CA06
0x14003c6e6  mov     byte ptr [rax], 1
0x14003c6e9  mov     r8, rdi
0x14003c6ec  mov     qword ptr [rax+8], 0
0x14003c6f4  mov     dword ptr [rax+10h], 1Ch
0x14003c6fb  movups  xmm0, xmmword ptr cs:aWimoverlayDat; "WimOverlay.dat"
0x14003c702  movups  xmmword ptr [rax+14h], xmm0
0x14003c706  movups  xmm1, xmmword ptr cs:aWimoverlayDat+0Ch; "rlay.dat"
0x14003c70d  movups  xmmword ptr [rax+20h], xmm1
0x14003c711  mov     rdx, [rbp+47h+FileObject]
0x14003c715  mov     rcx, [r14+78h]
0x14003c719  call    WimRenameOnSystemThread
0x14003c71e  xor     edx, edx; Tag
0x14003c720  mov     rcx, rdi; P
0x14003c723  mov     ebx, eax
0x14003c725  call    cs:__imp_ExFreePoolWithTag
0x14003c72c  nop     dword ptr [rax+rax+00h]
0x14003c731  mov     ecx, 80000000h
0x14003c736  lea     eax, [rbx+rcx]
0x14003c739  test    ecx, eax
0x14003c73b  jnz     short loc_14003C7B2
0x14003c73d  cmp     ebx, 0C00000A2h
0x14003c743  jz      short loc_14003C7B2
0x14003c745  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c74c  test    dword ptr [rcx+2Ch], 400h
0x14003c753  jz      loc_14003CA06
0x14003c759  cmp     byte ptr [rcx+29h], 2
0x14003c75d  jb      loc_14003CA06
0x14003c763  mov     edx, 1Eh
0x14003c768  jmp     loc_14003C808
0x14003c76d  cmp     eax, 0C0000034h
0x14003c772  jnz     short loc_14003C77C
0x14003c774  lea     ebx, [rax-25h]
0x14003c777  jmp     loc_14003CA06
0x14003c77c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c783  mov     eax, [rcx+2Ch]
0x14003c786  test    al, 8
0x14003c788  jz      loc_14003CA06
0x14003c78e  cmp     byte ptr [rcx+29h], 2
0x14003c792  jb      short loc_14003C7A5
0x14003c794  mov     rcx, [rcx+18h]
0x14003c798  mov     dword ptr [rsp+0C0h+LengthReturned], ebx
0x14003c79c  mov     [rsp+0C0h+FileInformationClass], edi
0x14003c7a0  call    WPP_SF_Sld
0x14003c7a5  test    ebx, ebx
0x14003c7a7  jns     loc_14003C9DD
0x14003c7ad  jmp     loc_14003CA06
0x14003c7b2  mov     rdx, [rbp+47h+FileObject]; FileObject
0x14003c7b6  lea     r8, [rbp+47h+FileInformation]; FileInformation
0x14003c7ba  mov     rcx, [r14+78h]; Instance
0x14003c7be  mov     r9d, 18h; Length
0x14003c7c4  mov     [rsp+0C0h+LengthReturned], 0; LengthReturned
0x14003c7cd  mov     [rsp+0C0h+FileInformationClass], 5; FileInformationClass
0x14003c7d5  call    cs:__imp_FltQueryInformationFile
0x14003c7dc  nop     dword ptr [rax+rax+00h]
0x14003c7e1  mov     ebx, eax
0x14003c7e3  test    eax, eax
0x14003c7e5  jns     short loc_14003C810
0x14003c7e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c7ee  mov     eax, [rcx+2Ch]
0x14003c7f1  test    al, 8
0x14003c7f3  jz      loc_14003CA06
0x14003c7f9  cmp     byte ptr [rcx+29h], 2
0x14003c7fd  jb      loc_14003CA06
0x14003c803  mov     edx, 20h ; ' '
0x14003c808  mov     r9d, ebx
0x14003c80b  jmp     loc_14003C6D1
0x14003c810  mov     rdi, qword ptr [rbp+47h+FileInformation+8]
0x14003c814  cmp     rdi, 200000h
0x14003c81b  jle     short loc_14003C84C
0x14003c81d  mov     r9d, 0C00002C4h
0x14003c823  mov     ebx, r9d
0x14003c826  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c82d  mov     eax, [rcx+2Ch]
0x14003c830  test    al, 8
0x14003c832  jz      loc_14003CA06
0x14003c838  cmp     byte ptr [rcx+29h], 2
0x14003c83c  jb      loc_14003CA06
0x14003c842  mov     edx, 21h ; '!'
0x14003c847  jmp     loc_14003C6D1
0x14003c84c  cmp     edi, 18h
0x14003c84f  jnb     short loc_14003C898
0x14003c851  mov     r9d, 0C00002C4h
0x14003c857  mov     ebx, r9d
0x14003c85a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c861  mov     eax, [rcx+2Ch]
0x14003c864  test    al, 8
0x14003c866  jz      loc_14003CA06
0x14003c86c  cmp     byte ptr [rcx+29h], 2
0x14003c870  jb      loc_14003CA06
0x14003c876  mov     rcx, [rcx+18h]
0x14003c87a  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003c881  mov     [rsp+0C0h+FileInformationClass], r9d
0x14003c886  mov     edx, 22h ; '"'
0x14003c88b  mov     r9d, edi
0x14003c88e  call    WPP_SF_dd
0x14003c893  jmp     loc_14003CA06
0x14003c898  mov     edx, edi; NumberOfBytes
0x14003c89a  mov     ecx, 1; PoolType
0x14003c89f  mov     r8d, 66637077h; Tag
0x14003c8a5  call    cs:__imp_ExAllocatePoolWithTag
0x14003c8ac  nop     dword ptr [rax+rax+00h]
0x14003c8b1  xor     ecx, ecx
0x14003c8b3  mov     rsi, rax
0x14003c8b6  test    rax, rax
0x14003c8b9  jnz     short loc_14003C8E8
0x14003c8bb  mov     r9d, 0C000009Ah
0x14003c8c1  mov     ebx, r9d
0x14003c8c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c8cb  mov     eax, [rcx+2Ch]
0x14003c8ce  test    al, 8
0x14003c8d0  jz      loc_14003CA06
0x14003c8d6  cmp     byte ptr [rcx+29h], 2
0x14003c8da  jb      loc_14003CA06
0x14003c8e0  lea     edx, [rsi+23h]
0x14003c8e3  jmp     loc_14003C6D1
0x14003c8e8  mov     rdx, [rbp+47h+FileObject]; FileObject
0x14003c8ec  lea     rax, [rbp+47h+var_68]
0x14003c8f0  mov     [rsp+0C0h+CallbackContext], rcx; CallbackContext
0x14003c8f5  mov     r9d, edi; Length
0x14003c8f8  mov     [rsp+0C0h+CallbackRoutine], rcx; CallbackRoutine
0x14003c8fd  xor     r8d, r8d; ByteOffset
0x14003c900  mov     [rsp+0C0h+BytesRead], rax; BytesRead
0x14003c905  mov     dword ptr [rsp+0C0h+LengthReturned], ecx; Flags
0x14003c909  mov     rcx, [r14+78h]; InitiatingInstance
0x14003c90d  mov     qword ptr [rsp+0C0h+FileInformationClass], rsi; Buffer
0x14003c912  call    cs:__imp_FltReadFile
0x14003c919  nop     dword ptr [rax+rax+00h]
0x14003c91e  mov     ebx, eax
0x14003c920  test    eax, eax
0x14003c922  jns     short loc_14003C94A
0x14003c924  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c92b  mov     eax, [rcx+2Ch]
0x14003c92e  test    al, 8
0x14003c930  jz      loc_14003C9C0
0x14003c936  cmp     byte ptr [rcx+29h], 2
0x14003c93a  jb      loc_14003C9C0
0x14003c940  mov     edx, 24h ; '$'
0x14003c945  mov     r9d, ebx
0x14003c948  jmp     short loc_14003C971
0x14003c94a  cmp     [rbp+47h+var_68], edi
0x14003c94d  jz      short loc_14003C983
0x14003c94f  mov     r9d, 0C00002C4h
0x14003c955  mov     ebx, r9d
0x14003c958  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c95f  mov     eax, [rcx+2Ch]
0x14003c962  test    al, 8
0x14003c964  jz      short loc_14003C9C0
0x14003c966  cmp     byte ptr [rcx+29h], 2
0x14003c96a  jb      short loc_14003C9C0
0x14003c96c  mov     edx, 25h ; '%'
0x14003c971  mov     rcx, [rcx+18h]
0x14003c975  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003c97c  call    WPP_SF_d
0x14003c981  jmp     short loc_14003C9C0
0x14003c983  mov     edx, edi
0x14003c985  mov     rcx, rsi
0x14003c988  call    WimpValidateOverlayConfig
0x14003c98d  mov     ebx, eax
0x14003c98f  test    eax, eax
0x14003c991  jns     short loc_14003C9D3
0x14003c993  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c99a  mov     eax, [rcx+2Ch]
0x14003c99d  test    al, 8
0x14003c99f  jz      short loc_14003C9C0
0x14003c9a1  cmp     byte ptr [rcx+29h], 2
0x14003c9a5  jb      short loc_14003C9C0
0x14003c9a7  mov     rcx, [rcx+18h]
0x14003c9ab  lea     r9, [r14+40h]
0x14003c9af  mov     edx, 26h ; '&'
0x14003c9b4  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003c9bb  call    WPP_SF_Z
0x14003c9c0  xor     edx, edx; Tag
0x14003c9c2  mov     rcx, rsi; P
0x14003c9c5  call    cs:__imp_ExFreePoolWithTag
0x14003c9cc  nop     dword ptr [rax+rax+00h]
0x14003c9d1  jmp     short loc_14003CA06
0x14003c9d3  mov     rax, [rbp+47h+var_58]
0x14003c9d7  mov     [r13+0], rsi
0x14003c9db  mov     [rax], edi
0x14003c9dd  test    r12, r12
0x14003c9e0  jz      short loc_14003C9F2
0x14003c9e2  mov     rax, [rbp+47h+FileHandle]
0x14003c9e6  mov     [r12], rax
0x14003c9ea  mov     [rbp+47h+FileHandle], 0
0x14003c9f2  test    r15, r15
0x14003c9f5  jz      short loc_14003CA06
0x14003c9f7  mov     rax, [rbp+47h+FileObject]
0x14003c9fb  mov     [r15], rax
0x14003c9fe  mov     [rbp+47h+FileObject], 0
0x14003ca06  mov     rcx, [rbp+47h+FileObject]; Object
0x14003ca0a  test    rcx, rcx
0x14003ca0d  jz      short loc_14003CA1B
0x14003ca0f  call    cs:__imp_ObfDereferenceObject
0x14003ca16  nop     dword ptr [rax+rax+00h]
0x14003ca1b  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x14003ca1f  test    rcx, rcx
0x14003ca22  jz      short loc_14003CA30
0x14003ca24  call    cs:__imp_FltClose
0x14003ca2b  nop     dword ptr [rax+rax+00h]
0x14003ca30  mov     eax, ebx
0x14003ca32  mov     rcx, [rbp+47h+var_38]
0x14003ca36  xor     rcx, rsp; StackCookie
0x14003ca39  call    __security_check_cookie
0x14003ca3e  mov     rbx, [rsp+0C0h+arg_8]
0x14003ca46  add     rsp, 90h
0x14003ca4d  pop     r15
0x14003ca4f  pop     r14
0x14003ca51  pop     r13
  ... truncated ...
```
