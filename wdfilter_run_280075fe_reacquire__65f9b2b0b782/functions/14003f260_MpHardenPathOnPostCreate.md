# MpHardenPathOnPostCreate

- ea: `0x14003f260`
- end: `0x14003f700`
- name: `MpHardenPathOnPostCreate`
- size: `1184`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002e850`

## callees

- `0x1400051bc`
- `0x14000b5d4`
- `0x14000fcfc`
- `0x1400118d0`
- `0x14003ee80`
- `0x14003f260`
- `0x140040388`
- `0x140040680`
- `0x1400471ac`
- `0x1400704f8`
- `0x1400777a8`
- `0x14008ab44`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14003f653`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003f6ba`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003f653`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003f6ba`
- `FLTMGR!FltGetFileNameInformation` at `0x14003f3b8`
- `FLTMGR!FltGetFileNameInformation` at `0x14003f3b8`
- `FLTMGR!FltGetFileSystemType` at `0x14003f38d`
- `FLTMGR!FltGetFileSystemType` at `0x14003f38d`
- `FLTMGR!FltIsDirectory` at `0x14003f3f5`
- `FLTMGR!FltIsDirectory` at `0x14003f3f5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003f340`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003f340`

## string_xrefs

- `0x14003f6d9`: `[Mini-filter] Denied access to file [%wZ] from process [%wZ][Pid:%u] on Post-Create. Reason: %ws.`

## pseudocode

```c
__int64 __fastcall MpHardenPathOnPostCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v4; // r14
  PFLT_CALLBACK_DATA v5; // r13
  unsigned __int8 v6; // si
  int v9; // r15d
  NTSTATUS v11; // ebx
  const UNICODE_STRING *v12; // r12
  struct _FLT_INSTANCE *v13; // rdx
  struct _FILE_OBJECT *v14; // rcx
  unsigned __int8 v15; // al
  struct _FLT_FILE_NAME_INFORMATION *v16; // r15
  unsigned __int8 v17; // al
  char IsAMPath; // si
  int v19; // ecx
  __int64 v20; // r12
  char v21; // di
  const wchar_t *v22; // rsi
  const wchar_t *v23; // rbp
  int v24; // r9d
  __int64 v25; // r15
  char CurrentProcessId; // al
  int v27; // r8d
  unsigned int v28; // eax
  int v29; // [rsp+28h] [rbp-A0h]
  char v30; // [rsp+40h] [rbp-88h]
  _DWORD Data[3]; // [rsp+44h] [rbp-84h] BYREF
  int v32; // [rsp+50h] [rbp-78h]
  __int64 v33; // [rsp+58h] [rbp-70h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int8 IsDirectory[4]; // [rsp+68h] [rbp-60h] BYREF
  enum _FLT_FILESYSTEM_TYPE FileSystemType; // [rsp+6Ch] [rbp-5Ch] BYREF

  v4 = 0;
  FileNameInformation = 0;
  v5 = CallbackData;
  *(_QWORD *)&Data[1] = CallbackData;
  v6 = 0;
  v33 = a3;
  v9 = *(_DWORD *)(MpData + 868) & 0x4000;
  FileSystemType = FLT_FSTYPE_UNKNOWN;
  v32 = v9;
  if ( (*(_DWORD *)(MpData + 3912) & 1) != 0 )
    *a4 &= ~0x10uLL;
  if ( (*(_DWORD *)a4 & 0x8010LL) == 0 )
    return 0;
  v11 = MpCheckLoopbackOnPostCreate(CallbackData);
  if ( v11 < 0 )
    goto LABEL_5;
  _mm_lfence();
  v12 = (const UNICODE_STRING *)a4[1];
  FltGetFileSystemType(*(PVOID *)(a2 + 24), &FileSystemType);
  if ( v12 )
    goto LABEL_14;
  if ( FileSystemType != FLT_FSTYPE_MUP
    || (*(_DWORD *)a4 & 0x8000LL) != 0 && (unsigned __int8)MpFgIsProtectingRemoteFolders() )
  {
    v11 = FltGetFileNameInformation(*(PFLT_CALLBACK_DATA *)&Data[1], 0x101u, &FileNameInformation);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          106,
          WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
          KeGetCurrentThread(),
          v11);
      }
      goto LABEL_28;
    }
LABEL_14:
    if ( (*(_BYTE *)a4 & 0x10) == 0 )
      goto LABEL_27;
    if ( v9 )
    {
      _mm_lfence();
      v13 = *(struct _FLT_INSTANCE **)(a2 + 24);
      v14 = *(struct _FILE_OBJECT **)(a2 + 32);
      IsDirectory[0] = 0;
      v11 = FltIsDirectory(v14, v13, IsDirectory);
      if ( v11 < 0 )
      {
        v15 = 0;
        IsDirectory[0] = 0;
      }
      else
      {
        v15 = IsDirectory[0];
      }
      v30 = v15;
      if ( v12 )
        v16 = 0;
      else
        v16 = FileNameInformation;
      if ( MpFsHardeningData && v33 && (v16 || v12) )
      {
        Data[0] = 0;
        v17 = FsHardeningMatch(v16, v12, 0, v29, (__int64)Data);
        if ( v17 )
        {
          v19 = Data[0];
          v6 = 0;
          if ( (Data[0] & 1) != 0 )
            v6 = v17;
          if ( (Data[0] & 2) != 0 )
          {
            LOBYTE(v19) = 1;
            MpTraceFsHardeningNotification(v19, v6, *(_QWORD *)(v33 + 128), (_DWORD)v16, (__int64)v12, v30);
          }
        }
        else
        {
          v6 = 1;
        }
      }
      v9 = v32;
      IsAMPath = v6 == 0;
    }
    else
    {
      IsAMPath = MpIsAMPath(v33, FileNameInformation);
    }
    if ( IsAMPath )
    {
      v5 = *(PFLT_CALLBACK_DATA *)&Data[1];
      v11 = 1835009;
      v20 = v33;
      v21 = 0;
      *(_DWORD *)(*(_QWORD *)&Data[1] + 24LL) = -1073741790;
      v5->IoStatus.Information = 0;
    }
    else
    {
LABEL_27:
      if ( (*(_DWORD *)a4 & 0x8000LL) == 0 )
      {
LABEL_28:
        v5 = *(PFLT_CALLBACK_DATA *)&Data[1];
LABEL_5:
        if ( v11 == -1073741536 || v11 == -1073741749 )
        {
          v5->IoStatus.Status = v11;
          v11 = 1835009;
          v5->IoStatus.Information = 0;
        }
        goto LABEL_7;
      }
      _mm_lfence();
      if ( !v12 )
        LODWORD(v12) = (_DWORD)FileNameInformation + 8;
      v5 = *(PFLT_CALLBACK_DATA *)&Data[1];
      v24 = (int)v12;
      v20 = v33;
      v21 = MpApplyFolderGuard(Data[1], a2, v33, v24, 0);
      if ( !v21 )
        goto LABEL_5;
      _mm_lfence();
      MpRemoveWriteAccess(v5);
    }
    v22 = L"CFA";
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      if ( v21 )
      {
        v23 = L"CFA";
      }
      else
      {
        v23 = L"DynamicFsHardening";
        if ( !v9 )
          v23 = L"FsHardening";
      }
      if ( v20 )
        v25 = *(_QWORD *)(v20 + 128);
      else
        v25 = 0;
      CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
      WPP_SF_ZZDS(
        WPP_GLOBAL_Control->AttachedDevice,
        107,
        v27,
        &v5->Iopb->TargetFileObject->FileName,
        v25,
        CurrentProcessId,
        (__int64)v23);
      v9 = v32;
    }
    if ( !v21 )
    {
      v22 = L"DynamicFsHardening";
      if ( !v9 )
        v22 = L"FsHardening";
    }
    if ( v20 )
      v4 = *(_QWORD *)(v20 + 128);
    v28 = (unsigned int)PsGetCurrentProcessId();
    MpLogPrintfW(
      L"[Mini-filter] Denied access to file [%wZ] from process [%wZ][Pid:%u] on Post-Create. Reason: %ws.",
      &v5->Iopb->TargetFileObject->FileName,
      v4,
      v28,
      v22);
  }
LABEL_7:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14003f260  push    rbp
0x14003f262  push    rsi
0x14003f263  push    rdi
0x14003f264  push    r13
0x14003f266  push    r14
0x14003f268  push    r15
0x14003f26a  sub     rsp, 98h
0x14003f271  mov     rax, cs:__security_cookie
0x14003f278  xor     rax, rsp
0x14003f27b  mov     [rsp+0C8h+var_58], rax
0x14003f280  mov     rax, cs:MpData
0x14003f287  xor     r14d, r14d
0x14003f28a  mov     [rsp+0C8h+FileNameInformation], r14
0x14003f28f  mov     r13, rcx
0x14003f292  mov     qword ptr [rsp+0C8h+Data+4], rcx
0x14003f297  xor     sil, sil
0x14003f29a  mov     rdi, r9
0x14003f29d  mov     [rsp+0C8h+var_70], r8
0x14003f2a2  mov     r15d, [rax+364h]
0x14003f2a9  mov     rbp, rdx
0x14003f2ac  mov     rax, cs:MpData
0x14003f2b3  and     r15d, 4000h
0x14003f2ba  mov     [rsp+0C8h+FileSystemType], r14d
0x14003f2bf  mov     [rsp+0C8h+var_78], r15d
0x14003f2c4  mov     ecx, [rax+0F48h]
0x14003f2ca  test    cl, 1
0x14003f2cd  jnz     loc_14003F4F0
0x14003f2d3  mov     eax, [r9]
0x14003f2d6  test    rax, 8010h
0x14003f2dc  jnz     short loc_14003F358
0x14003f2de  mov     eax, r14d
0x14003f2e1  mov     rcx, [rsp+0C8h+var_58]
0x14003f2e6  xor     rcx, rsp; StackCookie
0x14003f2e9  call    __security_check_cookie
0x14003f2ee  add     rsp, 98h
0x14003f2f5  pop     r15
0x14003f2f7  pop     r14
0x14003f2f9  pop     r13
0x14003f2fb  pop     rdi
0x14003f2fc  pop     rsi
0x14003f2fd  pop     rbp
0x14003f2fe  retn
0x14003f300  movzx   ecx, dil
0x14003f304  test    sil, sil
0x14003f307  jnz     loc_14003F5AD
0x14003f30d  test    cl, cl
0x14003f30f  jnz     loc_14003F5AD
0x14003f315  mov     eax, ebx
0x14003f317  cmp     ebx, 0C0000120h
0x14003f31d  jz      loc_14003F6EE
0x14003f323  cmp     eax, 0C000004Bh
0x14003f328  jz      loc_14003F6EE
0x14003f32e  mov     rcx, [rsp+0C8h+FileNameInformation]; FileNameInformation
0x14003f333  mov     r12, [rsp+0C8h+var_40]
0x14003f33b  test    rcx, rcx
0x14003f33e  jz      short loc_14003F34C
0x14003f340  call    cs:__imp_FltReleaseFileNameInformation
0x14003f347  nop     dword ptr [rax+rax+00h]
0x14003f34c  mov     eax, ebx
0x14003f34e  mov     rbx, [rsp+0C8h+var_38]
0x14003f356  jmp     short loc_14003F2E1
0x14003f358  mov     [rsp+0C8h+var_38], rbx
0x14003f360  mov     r8, rdi
0x14003f363  mov     rcx, r13; CallbackData
0x14003f366  mov     [rsp+0C8h+var_40], r12
0x14003f36e  call    MpCheckLoopbackOnPostCreate
0x14003f373  mov     ebx, eax
0x14003f375  test    eax, eax
0x14003f377  js      short loc_14003F315
0x14003f379  lfence
0x14003f37c  mov     rcx, [rbp+18h]; FltObject
0x14003f380  lea     rdx, [rsp+0C8h+FileSystemType]; FileSystemType
0x14003f385  mov     r12, [rdi+8]
0x14003f389  mov     r13, [rdi+10h]
0x14003f38d  call    cs:__imp_FltGetFileSystemType
0x14003f394  nop     dword ptr [rax+rax+00h]
0x14003f399  test    r12, r12
0x14003f39c  jnz     short loc_14003F3CE
0x14003f39e  cmp     [rsp+0C8h+FileSystemType], 0Dh
0x14003f3a3  jz      loc_14003F4F9
0x14003f3a9  mov     rcx, qword ptr [rsp+0C8h+Data+4]; CallbackData
0x14003f3ae  lea     r8, [rsp+0C8h+FileNameInformation]; FileNameInformation
0x14003f3b3  mov     edx, 101h; NameOptions
0x14003f3b8  call    cs:__imp_FltGetFileNameInformation
0x14003f3bf  nop     dword ptr [rax+rax+00h]
0x14003f3c4  mov     ebx, eax
0x14003f3c6  test    eax, eax
0x14003f3c8  js      loc_14003F518
0x14003f3ce  test    byte ptr [rdi], 10h
0x14003f3d1  jz      loc_14003F480
0x14003f3d7  test    r15d, r15d
0x14003f3da  jz      loc_14003F497
0x14003f3e0  lfence
0x14003f3e3  mov     rdx, [rbp+18h]; Instance
0x14003f3e7  lea     r8, [rsp+0C8h+IsDirectory]; IsDirectory
0x14003f3ec  mov     rcx, [rbp+20h]; FileObject
0x14003f3f0  mov     [rsp+0C8h+IsDirectory], sil
0x14003f3f5  call    cs:__imp_FltIsDirectory
0x14003f3fc  nop     dword ptr [rax+rax+00h]
0x14003f401  mov     ebx, eax
0x14003f403  test    eax, eax
0x14003f405  js      loc_14003F56B
0x14003f40b  movzx   eax, [rsp+0C8h+IsDirectory]
0x14003f410  mov     [rsp+0C8h+var_88], al
0x14003f414  test    r12, r12
0x14003f417  jnz     loc_14003F576
0x14003f41d  mov     r9, [rbp+18h]
0x14003f421  mov     r13, r14
0x14003f424  mov     r15, [rsp+0C8h+FileNameInformation]
0x14003f429  cmp     cs:MpFsHardeningData, r14
0x14003f430  jz      short loc_14003F46B
0x14003f432  cmp     [rsp+0C8h+var_70], r14
0x14003f437  jz      short loc_14003F46B
0x14003f439  test    r15, r15
0x14003f43c  jz      loc_14003F581
0x14003f442  lea     rax, [rsp+0C8h+Data]
0x14003f447  mov     dword ptr [rsp+0C8h+Data], r14d
0x14003f44c  mov     [rsp+0C8h+var_98], rax; __int64
0x14003f451  mov     r8, r13
0x14003f454  mov     rdx, r12; String2
0x14003f457  mov     [rsp+0C8h+var_A8], r14; __int64
0x14003f45c  mov     rcx, r15; FileNameInformation
0x14003f45f  call    FsHardeningMatch
0x14003f464  test    al, al
0x14003f466  jnz     short loc_14003F4AE
0x14003f468  mov     sil, 1
0x14003f46b  mov     r15d, [rsp+0C8h+var_78]
0x14003f470  test    sil, sil
0x14003f473  setz    sil
0x14003f477  test    sil, sil
0x14003f47a  jnz     loc_14003F58F
0x14003f480  mov     eax, [rdi]
0x14003f482  bt      rax, 0Fh
0x14003f487  jb      loc_14003F5E7
0x14003f48d  mov     r13, qword ptr [rsp+0C8h+Data+4]
0x14003f492  jmp     loc_14003F315
0x14003f497  mov     rdx, [rsp+0C8h+FileNameInformation]
0x14003f49c  mov     r8, r12
0x14003f49f  mov     rcx, [rsp+0C8h+var_70]
0x14003f4a4  call    MpIsAMPath
0x14003f4a9  movzx   esi, al
0x14003f4ac  jmp     short loc_14003F477
0x14003f4ae  mov     ecx, dword ptr [rsp+0C8h+Data]
0x14003f4b2  mov     esi, r14d
0x14003f4b5  test    cl, 1
0x14003f4b8  movzx   eax, al
0x14003f4bb  cmovnz  esi, eax
0x14003f4be  test    cl, 2
0x14003f4c1  jz      short loc_14003F46B
0x14003f4c3  movzx   eax, [rsp+0C8h+var_88]
0x14003f4c8  mov     r9, r15
0x14003f4cb  mov     byte ptr [rsp+0C8h+var_A0], al
0x14003f4cf  movzx   edx, sil
0x14003f4d3  mov     rax, [rsp+0C8h+var_70]
0x14003f4d8  mov     cl, 1
0x14003f4da  mov     [rsp+0C8h+var_A8], r12
0x14003f4df  mov     r8, [rax+80h]
0x14003f4e6  call    MpTraceFsHardeningNotification
0x14003f4eb  jmp     loc_14003F46B
0x14003f4f0  and     qword ptr [r9], 0FFFFFFFFFFFFFFEFh
0x14003f4f4  jmp     loc_14003F2D3
0x14003f4f9  mov     eax, [rdi]
0x14003f4fb  bt      rax, 0Fh
0x14003f500  jnb     loc_14003F32E
0x14003f506  call    MpFgIsProtectingRemoteFolders
0x14003f50b  test    al, al
0x14003f50d  jz      loc_14003F32E
0x14003f513  jmp     loc_14003F3A9
0x14003f518  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f51f  lea     rax, WPP_GLOBAL_Control
0x14003f526  cmp     rcx, rax
0x14003f529  jz      loc_14003F48D
0x14003f52f  mov     eax, [rcx+2Ch]
0x14003f532  test    al, 1
0x14003f534  jz      loc_14003F48D
0x14003f53a  lfence
0x14003f53d  mov     r9, gs:188h
0x14003f546  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x14003f54d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f554  mov     edx, 6Ah ; 'j'
0x14003f559  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x14003f55d  mov     rcx, [rcx+18h]
0x14003f561  call    WPP_SF_qD
0x14003f566  jmp     loc_14003F48D
0x14003f56b  xor     al, al
0x14003f56d  mov     [rsp+0C8h+IsDirectory], al
0x14003f571  jmp     loc_14003F410
0x14003f576  mov     r9, r14
0x14003f579  mov     r15, r14
0x14003f57c  jmp     loc_14003F429
0x14003f581  test    r12, r12
0x14003f584  jz      loc_14003F46B
0x14003f58a  jmp     loc_14003F442
0x14003f58f  mov     r13, qword ptr [rsp+0C8h+Data+4]
0x14003f594  mov     ebx, 1C0001h
0x14003f599  mov     r12, [rsp+0C8h+var_70]
0x14003f59e  xor     dil, dil
0x14003f5a1  mov     dword ptr [r13+18h], 0C0000022h
0x14003f5a9  mov     [r13+20h], r14
0x14003f5ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f5b4  lea     rax, WPP_GLOBAL_Control
0x14003f5bb  lea     rsi, aCfa; "CFA"
0x14003f5c2  lea     rdx, aFshardening; "FsHardening"
0x14003f5c9  cmp     rcx, rax
0x14003f5cc  jz      loc_14003F69A
0x14003f5d2  mov     eax, [rcx+2Ch]
0x14003f5d5  test    al, 2
0x14003f5d7  jz      loc_14003F69A
0x14003f5dd  test    dil, dil
0x14003f5e0  jz      short loc_14003F633
0x14003f5e2  mov     rbp, rsi
0x14003f5e5  jmp     short loc_14003F641
0x14003f5e7  lfence
0x14003f5ea  test    r12, r12
0x14003f5ed  jnz     short loc_14003F5F8
0x14003f5ef  mov     r12, [rsp+0C8h+FileNameInformation]
0x14003f5f4  add     r12, 8
0x14003f5f8  mov     r13, qword ptr [rsp+0C8h+Data+4]
0x14003f5fd  mov     r9, r12
0x14003f600  mov     r12, [rsp+0C8h+var_70]
0x14003f605  mov     rdx, rbp
0x14003f608  mov     r8, r12
0x14003f60b  mov     byte ptr [rsp+0C8h+var_A8], r14b
0x14003f610  mov     rcx, r13
0x14003f613  call    MpApplyFolderGuard
0x14003f618  movzx   edi, al
0x14003f61b  test    al, al
0x14003f61d  jz      loc_14003F300
0x14003f623  lfence
0x14003f626  mov     rcx, r13; Data
0x14003f629  call    MpRemoveWriteAccess
0x14003f62e  jmp     loc_14003F300
0x14003f633  test    r15d, r15d
0x14003f636  lea     rbp, aDynamicfsharde; "DynamicFsHardening"
0x14003f63d  cmovz   rbp, rdx
0x14003f641  test    r12, r12
0x14003f644  jz      short loc_14003F650
0x14003f646  mov     r15, [r12+80h]
0x14003f64e  jmp     short loc_14003F653
0x14003f650  mov     r15, r14
0x14003f653  call    cs:__imp_PsGetCurrentProcessId
0x14003f65a  nop     dword ptr [rax+rax+00h]
0x14003f65f  mov     rcx, [r13+10h]
0x14003f663  mov     edx, 6Bh ; 'k'
0x14003f668  mov     [rsp+0C8h+var_98], rbp
0x14003f66d  mov     [rsp+0C8h+var_A0], eax
0x14003f671  mov     [rsp+0C8h+var_A8], r15
0x14003f676  mov     r9, [rcx+8]
0x14003f67a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f681  add     r9, 58h ; 'X'
0x14003f685  mov     rcx, [rcx+18h]
0x14003f689  call    WPP_SF_ZZDS
0x14003f68e  mov     r15d, [rsp+0C8h+var_78]
0x14003f693  lea     rdx, aFshardening; "FsHardening"
0x14003f69a  test    dil, dil
0x14003f69d  jnz     short loc_14003F6AD
0x14003f69f  test    r15d, r15d
0x14003f6a2  lea     rsi, aDynamicfsharde; "DynamicFsHardening"
0x14003f6a9  cmovz   rsi, rdx
0x14003f6ad  test    r12, r12
0x14003f6b0  jz      short loc_14003F6BA
0x14003f6b2  mov     r14, [r12+80h]
0x14003f6ba  call    cs:__imp_PsGetCurrentProcessId
0x14003f6c1  nop     dword ptr [rax+rax+00h]
0x14003f6c6  mov     rcx, [r13+10h]
0x14003f6ca  mov     r8, r14
0x14003f6cd  mov     r9d, eax
0x14003f6d0  mov     [rsp+0C8h+var_A8], rsi
0x14003f6d5  mov     rdx, [rcx+8]
0x14003f6d9  lea     rcx, aMiniFilterDeni_6; "[Mini-filter] Denied access to file [%w"...
0x14003f6e0  add     rdx, 58h ; 'X'
0x14003f6e4  call    MpLogPrintfW
0x14003f6e9  jmp     loc_14003F32E
0x14003f6ee  mov     [r13+18h], ebx
0x14003f6f2  mov     ebx, 1C0001h
0x14003f6f7  mov     [r13+20h], r14
0x14003f6fb  jmp     loc_14003F32E
```
