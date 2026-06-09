# Smb2GetHashFileHandle

- ea: `0x140071168`
- end: `0x140071617`
- name: `Smb2GetHashFileHandle`
- size: `1199`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140071f88`

## callees

- `0x140022958`
- `0x140028dbc`
- `0x1400379f8`
- `0x140038490`
- `0x140038980`
- `0x140070d98`
- `0x140071168`
- `0x1400721a8`
- `0x14008edb4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140071500`
- `ntoskrnl!ZwClose` at `0x140071511`
- `ntoskrnl!ZwClose` at `0x140071500`
- `ntoskrnl!ZwClose` at `0x140071511`
- `ntoskrnl!ZwCreateFile` at `0x1400714cf`
- `ntoskrnl!ZwCreateFile` at `0x1400714cf`
- `ntoskrnl!IoReuseIrp` at `0x1400713bb`
- `ntoskrnl!IoReuseIrp` at `0x1400713bb`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007126b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007132d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007126b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007132d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400712d7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400712d7`
- `srvnet!SrvNotifyGroveler` at `0x140071538`
- `srvnet!SrvNotifyGroveler` at `0x1400715af`
- `srvnet!SrvNotifyGroveler` at `0x140071538`
- `srvnet!SrvNotifyGroveler` at `0x1400715af`

## pseudocode

```c
__int64 __fastcall Smb2GetHashFileHandle(__int64 a1, void **a2, struct _UNICODE_STRING *a3)
{
  __int64 v6; // rsi
  __int64 v7; // r12
  bool v8; // zf
  unsigned int v9; // ecx
  int v10; // eax
  unsigned int v11; // r15d
  unsigned int v12; // eax
  __int64 v13; // rcx
  unsigned int VolumeName; // ebx
  NTSTATUS appended; // eax
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  NTSTATUS FileObjectID; // ebx
  unsigned int v19; // eax
  int v20; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v23[2]; // [rsp+68h] [rbp-98h] BYREF
  char *v24; // [rsp+70h] [rbp-90h]
  __int64 v25; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING *v26; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING v27; // [rsp+88h] [rbp-78h] BYREF
  __int128 v28; // [rsp+98h] [rbp-68h] BYREF
  void **v29; // [rsp+B0h] [rbp-50h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int8 v32[64]; // [rsp+100h] [rbp+0h] BYREF
  char v33; // [rsp+140h] [rbp+40h] BYREF

  v26 = a3;
  v29 = a2;
  v23[1] = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v27 = 0;
  v28 = 0;
  memset(v32, 0, sizeof(v32));
  v6 = *(_QWORD *)(a1 + 560);
  v7 = *(_QWORD *)(v6 + 216);
  FileHandle = 0;
  *a2 = 0;
  v8 = *(_DWORD *)(v7 + 8) == 2;
  v9 = *(_DWORD *)(v7 + 12);
  v25 = *(_QWORD *)(v7 + 16);
  v10 = *(_DWORD *)(v6 + 200);
  if ( v8 )
  {
    v11 = v10 - 24;
    if ( v10 - 24 >= v9 )
      v11 = v9;
  }
  else
  {
    v12 = v10 - 16;
    v11 = v9;
    if ( v12 < v9 )
      v11 = v12;
  }
  v13 = *(_QWORD *)(v6 + 80);
  v24 = &v33;
  v23[0] = 34078720;
  VolumeName = Smb2GetVolumeName(*(_QWORD *)(v13 + 96), v23);
  if ( (VolumeName & 0x80000000) != 0 )
    return VolumeName;
  appended = RtlAppendUnicodeStringToString(a3, (PCUNICODE_STRING)(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 96LL) + 152LL));
  VolumeName = appended;
  if ( appended < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v17 = 30;
LABEL_13:
      WPP_SF_qD(v16->AttachedDevice, v17, WPP_8e7cd37454fb33500a68697303cffebe_Traceguids, a1, appended);
      return VolumeName;
    }
    return VolumeName;
  }
  appended = RtlAppendUnicodeToString(a3, L"\\");
  VolumeName = appended;
  if ( appended >= 0 )
  {
    appended = RtlAppendUnicodeStringToString(a3, (PCUNICODE_STRING)(*(_QWORD *)(v6 + 72) + 208LL));
    VolumeName = appended;
    if ( appended < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v17 = 32;
        goto LABEL_13;
      }
      return VolumeName;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        33,
        (unsigned int)WPP_8e7cd37454fb33500a68697303cffebe_Traceguids,
        a1,
        (__int64)a3);
    }
    IoReuseIrp(*(PIRP *)(a1 + 120), 0);
    FileObjectID = Smb2GetFileObjectID(a1, *(_QWORD *)(*(_QWORD *)(v6 + 80) + 96LL), v32);
    if ( FileObjectID < 0 )
      goto LABEL_53;
    v27.Buffer = (PWSTR)&v24[2 * ((unsigned __int64)LOWORD(v23[0]) >> 1)];
    v27.Length = 0;
    v27.MaximumLength = 518 - LOWORD(v23[0]);
    VolumeName = I_ObjectIdToHashPath(&v27, v32);
    if ( (VolumeName & 0x80000000) != 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        appended = *(_DWORD *)(v7 + 4);
        v17 = 34;
        goto LABEL_13;
      }
      return VolumeName;
    }
    *((_QWORD *)&v28 + 1) = v24;
    LOWORD(v28) = LOWORD(v23[0]) + v27.Length;
    WORD1(v28) = LOWORD(v23[0]) + v27.Length;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v28;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 512;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    FileObjectID = ZwCreateFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0, 0, 0);
    if ( FileObjectID < 0 )
    {
LABEL_53:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          35,
          WPP_8e7cd37454fb33500a68697303cffebe_Traceguids,
          a1,
          FileObjectID);
      }
      if ( FileObjectID == -1073741757 )
        return (unsigned int)-1073700607;
    }
    else
    {
      v19 = Smb2ValidateHashFile(a1, FileHandle);
      VolumeName = v19;
      if ( !v19 )
      {
        SrvNotifyGroveler(v26, 1, *(unsigned int *)(v7 + 4), v25, v11, 1);
        *v29 = FileHandle;
        return VolumeName;
      }
      if ( v19 != -1073741802 )
      {
        ZwClose(FileHandle);
        return VolumeName;
      }
      ZwClose(FileHandle);
    }
    SrvNotifyGroveler(v26, 1, *(unsigned int *)(v7 + 4), v25, v11, 2);
    v20 = *(_DWORD *)(v7 + 4);
    if ( v20 == 1 )
    {
      ++*(_DWORD *)(Srv2Statistics + 148);
    }
    else if ( v20 == 2 )
    {
      ++*(_DWORD *)(Srv2Statistics + 188);
    }
    return (unsigned int)-1073700607;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v17 = 31;
    goto LABEL_13;
  }
  return VolumeName;
}

```

## disassembly

```asm
0x140071168  mov     [rsp-8+arg_18], rbx
0x14007116d  push    rbp
0x14007116e  push    rsi
0x14007116f  push    rdi
0x140071170  push    r12
0x140071172  push    r13
0x140071174  push    r14
0x140071176  push    r15
0x140071178  lea     rbp, [rsp-260h]
0x140071180  sub     rsp, 360h
0x140071187  mov     rax, cs:__security_cookie
0x14007118e  xor     rax, rsp
0x140071191  mov     [rbp+290h+var_40], rax
0x140071198  xorps   xmm0, xmm0
0x14007119b  mov     [rbp+290h+var_310], r8
0x14007119f  xor     eax, eax
0x1400711a1  mov     [rbp+290h+var_2E0], rdx
0x1400711a5  mov     rdi, r8
0x1400711a8  mov     rbx, rdx
0x1400711ab  mov     r13, rcx
0x1400711ae  xorps   xmm1, xmm1
0x1400711b1  movups  xmmword ptr [rbp+290h+ObjectAttributes.ObjectName], xmm0
0x1400711b5  xor     r14d, r14d
0x1400711b8  lea     r8d, [rax+40h]; Size
0x1400711bc  xor     edx, edx; Val
0x1400711be  mov     [rsp+390h+var_324], r14d
0x1400711c3  lea     rcx, [rbp+290h+var_290]; void *
0x1400711c7  movups  xmmword ptr [rbp+290h+ObjectAttributes.Length], xmm0
0x1400711cb  movups  xmmword ptr [rbp+290h+ObjectAttributes+1Ch], xmm0
0x1400711cf  movups  xmmword ptr [rbp+290h+IoStatusBlock], xmm0
0x1400711d3  movups  xmmword ptr [rbp+290h+var_308.Length], xmm0
0x1400711d7  movups  [rbp+290h+var_2F8], xmm1
0x1400711db  call    memset
0x1400711e0  mov     rsi, [r13+230h]
0x1400711e7  mov     r12, [rsi+0D8h]
0x1400711ee  mov     [rsp+390h+FileHandle], r14
0x1400711f3  mov     [rbx], r14
0x1400711f6  cmp     dword ptr [r12+8], 2
0x1400711fc  mov     rax, [r12+10h]
0x140071201  mov     ecx, [r12+0Ch]
0x140071206  mov     [rsp+390h+var_318], rax
0x14007120b  mov     eax, [rsi+0C8h]
0x140071211  jnz     short loc_140071220
0x140071213  lea     r15d, [rax-18h]
0x140071217  cmp     r15d, ecx
0x14007121a  cmovnb  r15d, ecx
0x14007121e  jmp     short loc_14007122C
0x140071220  add     eax, 0FFFFFFF0h
0x140071223  mov     r15d, ecx
0x140071226  cmp     eax, ecx
0x140071228  cmovb   r15d, eax
0x14007122c  mov     rcx, [rsi+50h]
0x140071230  lea     rax, [rbp+290h+var_250]
0x140071234  lea     rdx, [rsp+390h+var_328]
0x140071239  mov     [rsp+390h+var_320], rax
0x14007123e  mov     [rsp+390h+var_328], 2080000h
0x140071246  mov     rcx, [rcx+60h]
0x14007124a  call    Smb2GetVolumeName
0x14007124f  mov     ebx, eax
0x140071251  test    eax, eax
0x140071253  js      loc_1400715EA
0x140071259  mov     rax, [rsi+38h]
0x14007125d  mov     rcx, rdi; Destination
0x140071260  mov     rdx, [rax+60h]
0x140071264  add     rdx, 98h; Source
0x14007126b  call    cs:__imp_RtlAppendUnicodeStringToString
0x140071272  nop     dword ptr [rax+rax+00h]
0x140071277  mov     ebx, eax
0x140071279  test    eax, eax
0x14007127b  jns     short loc_1400712CD
0x14007127d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140071284  lea     r14, WPP_GLOBAL_Control
0x14007128b  cmp     rcx, r14
0x14007128e  jz      loc_1400715EA
0x140071294  bt      dword ptr [rcx+2Ch], 1Dh
0x140071299  jnb     loc_1400715EA
0x14007129f  mov     edi, 1
0x1400712a4  cmp     [rcx+29h], dil
0x1400712a8  jb      loc_1400715EA
0x1400712ae  lea     edx, [rdi+1Dh]
0x1400712b1  mov     rcx, [rcx+18h]
0x1400712b5  lea     r8, WPP_8e7cd37454fb33500a68697303cffebe_Traceguids
0x1400712bc  mov     r9, r13
0x1400712bf  mov     dword ptr [rsp+390h+AllocationSize], eax
0x1400712c3  call    WPP_SF_qD
0x1400712c8  jmp     loc_1400715EA
0x1400712cd  lea     rdx, Source; "\\"
0x1400712d4  mov     rcx, rdi; Destination
0x1400712d7  call    cs:__imp_RtlAppendUnicodeToString
0x1400712de  nop     dword ptr [rax+rax+00h]
0x1400712e3  mov     ebx, eax
0x1400712e5  test    eax, eax
0x1400712e7  jns     short loc_14007131F
0x1400712e9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400712f0  lea     r14, WPP_GLOBAL_Control
0x1400712f7  cmp     rcx, r14
0x1400712fa  jz      loc_1400715EA
0x140071300  bt      dword ptr [rcx+2Ch], 1Dh
0x140071305  jnb     loc_1400715EA
0x14007130b  mov     edi, 1
0x140071310  cmp     [rcx+29h], dil
0x140071314  jb      loc_1400715EA
0x14007131a  lea     edx, [rdi+1Eh]
0x14007131d  jmp     short loc_1400712B1
0x14007131f  mov     rdx, [rsi+48h]
0x140071323  mov     rcx, rdi; Destination
0x140071326  add     rdx, 0D0h; Source
0x14007132d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140071334  nop     dword ptr [rax+rax+00h]
0x140071339  mov     ebx, eax
0x14007133b  test    eax, eax
0x14007133d  jns     short loc_140071378
0x14007133f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140071346  lea     r14, WPP_GLOBAL_Control
0x14007134d  cmp     rcx, r14
0x140071350  jz      loc_1400715EA
0x140071356  bt      dword ptr [rcx+2Ch], 1Dh
0x14007135b  jnb     loc_1400715EA
0x140071361  mov     edi, 1
0x140071366  cmp     [rcx+29h], dil
0x14007136a  jb      loc_1400715EA
0x140071370  lea     edx, [rdi+1Fh]
0x140071373  jmp     loc_1400712B1
0x140071378  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007137f  lea     r14, WPP_GLOBAL_Control
0x140071386  cmp     rcx, r14
0x140071389  jz      short loc_1400713B5
0x14007138b  bt      dword ptr [rcx+2Ch], 1Dh
0x140071390  jnb     short loc_1400713B5
0x140071392  cmp     byte ptr [rcx+29h], 2
0x140071396  jb      short loc_1400713B5
0x140071398  mov     rcx, [rcx+18h]
0x14007139c  lea     r8, WPP_8e7cd37454fb33500a68697303cffebe_Traceguids
0x1400713a3  mov     edx, 21h ; '!'
0x1400713a8  mov     [rsp+390h+AllocationSize], rdi
0x1400713ad  mov     r9, r13
0x1400713b0  call    WPP_SF_qZ
0x1400713b5  mov     rcx, [r13+78h]; Irp
0x1400713b9  xor     edx, edx; Iostatus
0x1400713bb  call    cs:__imp_IoReuseIrp
0x1400713c2  nop     dword ptr [rax+rax+00h]
0x1400713c7  mov     rdx, [rsi+50h]
0x1400713cb  lea     r8, [rbp+290h+var_290]
0x1400713cf  mov     rcx, r13
0x1400713d2  mov     rdx, [rdx+60h]
0x1400713d6  call    Smb2GetFileObjectID
0x1400713db  mov     ebx, eax
0x1400713dd  mov     edi, 1
0x1400713e2  test    eax, eax
0x1400713e4  js      loc_140071555
0x1400713ea  mov     rcx, [rsp+390h+var_320]
0x1400713ef  lea     rdx, [rbp+290h+var_290]; unsigned __int8 *
0x1400713f3  movzx   eax, word ptr [rsp+390h+var_328]
0x1400713f8  shr     rax, 1
0x1400713fb  lea     rax, [rcx+rax*2]
0x1400713ff  mov     [rbp+290h+var_308.Buffer], rax
0x140071403  lea     rcx, [rbp+290h+var_308]; struct _UNICODE_STRING *
0x140071407  xor     eax, eax
0x140071409  mov     [rbp+290h+var_308.Length], ax
0x14007140d  mov     eax, 206h
0x140071412  sub     ax, word ptr [rsp+390h+var_328]
0x140071417  mov     [rbp+290h+var_308.MaximumLength], ax
0x14007141b  mov     r9d, [r12+4]
0x140071420  call    I_ObjectIdToHashPath
0x140071425  xor     ecx, ecx
0x140071427  mov     ebx, eax
0x140071429  test    eax, eax
0x14007142b  jns     short loc_14007145F
0x14007142d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140071434  cmp     rcx, r14
0x140071437  jz      loc_1400715EA
0x14007143d  bt      dword ptr [rcx+2Ch], 1Dh
0x140071442  jnb     loc_1400715EA
0x140071448  cmp     [rcx+29h], dil
0x14007144c  jb      loc_1400715EA
0x140071452  mov     eax, [r12+4]
0x140071457  lea     edx, [rdi+21h]
0x14007145a  jmp     loc_1400712B1
0x14007145f  mov     rax, [rsp+390h+var_320]
0x140071464  lea     r9, [rbp+290h+IoStatusBlock]; IoStatusBlock
0x140071468  mov     [rsp+390h+EaLength], ecx; EaLength
0x14007146c  lea     r8, [rbp+290h+ObjectAttributes]; ObjectAttributes
0x140071470  mov     [rsp+390h+EaBuffer], rcx; EaBuffer
0x140071475  xorps   xmm0, xmm0
0x140071478  mov     [rsp+390h+CreateOptions], ecx; CreateOptions
0x14007147c  mov     edx, 80000000h; DesiredAccess
0x140071481  mov     qword ptr [rbp+290h+var_2F8+8], rax
0x140071485  movzx   eax, [rbp+290h+var_308.Length]
0x140071489  add     ax, word ptr [rsp+390h+var_328]
0x14007148e  mov     [rsp+390h+CreateDisposition], edi; CreateDisposition
0x140071492  mov     [rsp+390h+ShareAccess], edi; ShareAccess
0x140071496  mov     word ptr [rbp+290h+var_2F8], ax
0x14007149a  mov     word ptr [rbp+290h+var_2F8+2], ax
0x14007149e  lea     rax, [rbp+290h+var_2F8]
0x1400714a2  mov     [rbp+290h+ObjectAttributes.RootDirectory], rcx
0x1400714a6  mov     [rsp+390h+FileAttributes], 80h; FileAttributes
0x1400714ae  mov     [rsp+390h+AllocationSize], rcx; AllocationSize
0x1400714b3  lea     rcx, [rsp+390h+FileHandle]; FileHandle
0x1400714b8  mov     [rbp+290h+ObjectAttributes.ObjectName], rax
0x1400714bc  mov     [rbp+290h+ObjectAttributes.Length], 30h ; '0'
0x1400714c3  mov     [rbp+290h+ObjectAttributes.Attributes], 200h
0x1400714ca  movdqu  xmmword ptr [rbp+290h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400714cf  call    cs:__imp_ZwCreateFile
0x1400714d6  nop     dword ptr [rax+rax+00h]
0x1400714db  mov     ebx, eax
0x1400714dd  test    eax, eax
0x1400714df  js      short loc_140071555
0x1400714e1  mov     rdx, [rsp+390h+FileHandle]
0x1400714e6  mov     rcx, r13
0x1400714e9  call    Smb2ValidateHashFile
0x1400714ee  mov     ebx, eax
0x1400714f0  test    eax, eax
0x1400714f2  jz      short loc_14007151F
0x1400714f4  mov     rcx, [rsp+390h+FileHandle]; Handle
0x1400714f9  cmp     eax, 0C0000016h
0x1400714fe  jz      short loc_140071511
0x140071500  call    cs:__imp_ZwClose
0x140071507  nop     dword ptr [rax+rax+00h]
0x14007150c  jmp     loc_1400715EA
0x140071511  call    cs:__imp_ZwClose
0x140071518  nop     dword ptr [rax+rax+00h]
0x14007151d  jmp     short loc_140071592
0x14007151f  mov     r9, [rsp+390h+var_318]
0x140071524  mov     edx, edi
0x140071526  mov     r8d, [r12+4]
0x14007152b  mov     rcx, [rbp+290h+var_310]
0x14007152f  mov     [rsp+390h+FileAttributes], edi
0x140071533  mov     dword ptr [rsp+390h+AllocationSize], r15d
0x140071538  call    cs:__imp_SrvNotifyGroveler
0x14007153f  nop     dword ptr [rax+rax+00h]
0x140071544  mov     rcx, [rbp+290h+var_2E0]
0x140071548  mov     rax, [rsp+390h+FileHandle]
0x14007154d  mov     [rcx], rax
0x140071550  jmp     loc_1400715EA
0x140071555  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007155c  cmp     rcx, r14
0x14007155f  jz      short loc_14007158A
0x140071561  bt      dword ptr [rcx+2Ch], 1Dh
0x140071566  jnb     short loc_14007158A
0x140071568  cmp     [rcx+29h], dil
0x14007156c  jb      short loc_14007158A
0x14007156e  mov     rcx, [rcx+18h]
0x140071572  lea     r8, WPP_8e7cd37454fb33500a68697303cffebe_Traceguids
0x140071579  mov     edx, 23h ; '#'
0x14007157e  mov     dword ptr [rsp+390h+AllocationSize], ebx
0x140071582  mov     r9, r13
0x140071585  call    WPP_SF_qD
0x14007158a  cmp     ebx, 0C0000043h
0x140071590  jz      short loc_1400715E5
0x140071592  mov     r9, [rsp+390h+var_318]
0x140071597  mov     edx, edi
0x140071599  mov     r8d, [r12+4]
0x14007159e  mov     rcx, [rbp+290h+var_310]
0x1400715a2  mov     [rsp+390h+FileAttributes], 2
0x1400715aa  mov     dword ptr [rsp+390h+AllocationSize], r15d
0x1400715af  call    cs:__imp_SrvNotifyGroveler
0x1400715b6  nop     dword ptr [rax+rax+00h]
0x1400715bb  mov     eax, [r12+4]
0x1400715c0  cmp     eax, edi
0x1400715c2  jnz     short loc_1400715D3
0x1400715c4  mov     rax, cs:Srv2Statistics
0x1400715cb  add     [rax+94h], edi
0x1400715d1  jmp     short loc_1400715E5
0x1400715d3  cmp     eax, 2
0x1400715d6  jnz     short loc_1400715E5
0x1400715d8  mov     rax, cs:Srv2Statistics
0x1400715df  add     [rax+0BCh], edi
0x1400715e5  mov     ebx, 0C000A101h
0x1400715ea  mov     eax, ebx
0x1400715ec  mov     rcx, [rbp+290h+var_40]
0x1400715f3  xor     rcx, rsp; StackCookie
0x1400715f6  call    __security_check_cookie
0x1400715fb  mov     rbx, [rsp+390h+arg_18]
0x140071603  add     rsp, 360h
0x14007160a  pop     r15
0x14007160c  pop     r14
0x14007160e  pop     r13
0x140071610  pop     r12
0x140071612  pop     rdi
0x140071613  pop     rsi
0x140071614  pop     rbp
0x140071615  retn
```
