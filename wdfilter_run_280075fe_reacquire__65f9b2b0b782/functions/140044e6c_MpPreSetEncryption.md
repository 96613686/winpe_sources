# MpPreSetEncryption

- ea: `0x140044e6c`
- end: `0x1400451b3`
- name: `MpPreSetEncryption`
- size: `839`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140044520`

## callees

- `0x140002450`
- `0x1400051bc`
- `0x1400068fc`
- `0x1400118d0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003ee80`
- `0x140040388`
- `0x140044e6c`
- `0x140046e30`
- `0x1400471ac`
- `0x14008ab44`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14004511b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140045178`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14004511b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140045178`
- `FLTMGR!FltGetFileNameInformation` at `0x140044f3a`
- `FLTMGR!FltGetFileNameInformation` at `0x140044f3a`
- `FLTMGR!FltGetFileSystemType` at `0x140044ee0`
- `FLTMGR!FltGetFileSystemType` at `0x140044ee0`
- `FLTMGR!FltIsDirectory` at `0x140045017`
- `FLTMGR!FltIsDirectory` at `0x140045017`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140044fcb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140044fcb`

## string_xrefs

- `0x14004519a`: `[Mini-filter] Denied access to file [%wZ] from process [%wZ][Pid:%u]. DynamicFsHardeningEnabled[%d].`

## pseudocode

```c
__int64 __fastcall MpPreSetEncryption(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  unsigned int v4; // ebx
  struct _KPROCESS *RequestorProcess; // rax
  int v6; // esi
  int v7; // r12d
  struct _FLT_INSTANCE *v9; // rdx
  struct _FILE_OBJECT *v10; // rcx
  char IsAMPath; // al
  char CurrentProcessId; // al
  HANDLE v13; // rax
  __int64 v14; // [rsp+20h] [rbp-50h]
  __int64 v15; // [rsp+40h] [rbp-30h]
  int v16; // [rsp+48h] [rbp-28h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int8 IsDirectory[4]; // [rsp+58h] [rbp-18h] BYREF
  enum _FLT_FILESYSTEM_TYPE FileSystemType; // [rsp+5Ch] [rbp-14h] BYREF

  v15 = 0;
  FileSystemType = FLT_FSTYPE_UNKNOWN;
  v4 = 1;
  FileNameInformation = 0;
  RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(CallbackData);
  if ( !RequestorProcess || (int)MpGetProcessContextByObject(RequestorProcess) < 0 )
    return v4;
  _mm_lfence();
  v6 = FltGetFileSystemType(*(PVOID *)(a2 + 24), &FileSystemType);
  v7 = *(_DWORD *)(MpData + 868) & 0x4000;
  v16 = v7;
  if ( (unsigned __int8)MpCheckForAmHardening((_DWORD)CallbackData, a2, 0, v15, FileSystemType == FLT_FSTYPE_MUP) )
  {
    _mm_lfence();
    v6 = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
    if ( v6 >= 0 )
    {
      if ( v7 )
      {
        v9 = *(struct _FLT_INSTANCE **)(a2 + 24);
        v10 = *(struct _FILE_OBJECT **)(a2 + 32);
        IsDirectory[0] = 0;
        v6 = FltIsDirectory(v10, v9, IsDirectory);
        if ( v6 < 0 )
          IsDirectory[0] = 0;
        v7 = v16;
        IsAMPath = 1;
      }
      else
      {
        IsAMPath = MpIsAMPath(v15, FileNameInformation);
      }
      if ( IsAMPath )
      {
        _mm_lfence();
        CallbackData->IoStatus.Status = -1073741790;
        v4 = 4;
        CallbackData->IoStatus.Information = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        {
          _mm_lfence();
          CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
          WPP_SF_ZZDd(
            WPP_GLOBAL_Control->AttachedDevice,
            27,
            (unsigned int)WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
            &CallbackData->Iopb->TargetFileObject->FileName,
            0,
            CurrentProcessId,
            v7 != 0);
        }
        v13 = PsGetCurrentProcessId();
        LODWORD(v14) = v7 != 0;
        MpLogPrintfW(
          L"[Mini-filter] Denied access to file [%wZ] from process [%wZ][Pid:%u]. DynamicFsHardeningEnabled[%d].",
          &CallbackData->Iopb->TargetFileObject->FileName,
          0,
          v13,
          v14);
        goto LABEL_11;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
        KeGetCurrentThread(),
        v6);
    }
  }
  if ( v6 == -1073741536 || v6 == -1073741749 )
  {
    CallbackData->IoStatus.Status = v6;
    v4 = 4;
    CallbackData->IoStatus.Information = 0;
  }
LABEL_11:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return v4;
}

```

## disassembly

```asm
0x140044e6c  mov     [rsp-38h+arg_10], rbx
0x140044e71  push    rbp
0x140044e72  push    rsi
0x140044e73  push    rdi
0x140044e74  push    r12
0x140044e76  push    r13
0x140044e78  push    r14
0x140044e7a  push    r15
0x140044e7c  mov     rbp, rsp
0x140044e7f  sub     rsp, 70h
0x140044e83  mov     rax, cs:__security_cookie
0x140044e8a  xor     rax, rsp
0x140044e8d  mov     [rbp+var_10], rax
0x140044e91  mov     r15, rdx
0x140044e94  mov     [rbp+var_30], 0
0x140044e9c  mov     r14, rcx
0x140044e9f  mov     [rbp+FileSystemType], 0
0x140044ea6  mov     ebx, 1
0x140044eab  mov     [rbp+FileNameInformation], 0
0x140044eb3  call    MpGetRequestorProcess
0x140044eb8  test    rax, rax
0x140044ebb  jz      loc_140044FD7
0x140044ec1  lea     rdx, [rbp+var_30]
0x140044ec5  mov     rcx, rax; Process
0x140044ec8  call    MpGetProcessContextByObject
0x140044ecd  test    eax, eax
0x140044ecf  js      loc_140044FD7
0x140044ed5  lfence
0x140044ed8  mov     rcx, [r15+18h]; FltObject
0x140044edc  lea     rdx, [rbp+FileSystemType]; FileSystemType
0x140044ee0  call    cs:__imp_FltGetFileSystemType
0x140044ee7  nop     dword ptr [rax+rax+00h]
0x140044eec  mov     rdi, [rbp+var_30]
0x140044ef0  mov     rdx, r15
0x140044ef3  mov     esi, eax
0x140044ef5  mov     r9, rdi
0x140044ef8  mov     rax, cs:MpData
0x140044eff  mov     rcx, r14
0x140044f02  mov     r12d, [rax+364h]
0x140044f09  and     r12d, 4000h
0x140044f10  cmp     [rbp+FileSystemType], 0Dh
0x140044f14  mov     [rbp+var_28], r12d
0x140044f18  setz    al
0x140044f1b  xor     r8d, r8d
0x140044f1e  mov     byte ptr [rsp+70h+var_50], al
0x140044f22  call    MpCheckForAmHardening
0x140044f27  test    al, al
0x140044f29  jz      short loc_140044F94
0x140044f2b  lfence
0x140044f2e  lea     r8, [rbp+FileNameInformation]; FileNameInformation
0x140044f32  mov     edx, 101h; NameOptions
0x140044f37  mov     rcx, r14; CallbackData
0x140044f3a  call    cs:__imp_FltGetFileNameInformation
0x140044f41  nop     dword ptr [rax+rax+00h]
0x140044f46  mov     esi, eax
0x140044f48  test    eax, eax
0x140044f4a  jns     loc_140044FFE
0x140044f50  mov     rcx, cs:WPP_GLOBAL_Control
0x140044f57  lea     rax, WPP_GLOBAL_Control
0x140044f5e  cmp     rcx, rax
0x140044f61  jz      short loc_140044F94
0x140044f63  mov     eax, [rcx+2Ch]
0x140044f66  test    bl, al
0x140044f68  jz      short loc_140044F94
0x140044f6a  lfence
0x140044f6d  mov     r9, gs:188h
0x140044f76  lea     edx, [rbx+19h]
0x140044f79  mov     rcx, cs:WPP_GLOBAL_Control
0x140044f80  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x140044f87  mov     dword ptr [rsp+70h+var_50], esi
0x140044f8b  mov     rcx, [rcx+18h]
0x140044f8f  call    WPP_SF_qD
0x140044f94  cmp     esi, 0C0000120h
0x140044f9a  jz      short loc_140044FA4
0x140044f9c  cmp     esi, 0C000004Bh
0x140044fa2  jnz     short loc_140044FB5
0x140044fa4  mov     [r14+18h], esi
0x140044fa8  mov     ebx, 4
0x140044fad  mov     qword ptr [r14+20h], 0
0x140044fb5  test    rdi, rdi
0x140044fb8  jz      short loc_140044FC2
0x140044fba  mov     rcx, rdi
0x140044fbd  call    MpReleaseProcessContext
0x140044fc2  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x140044fc6  test    rcx, rcx
0x140044fc9  jz      short loc_140044FD7
0x140044fcb  call    cs:__imp_FltReleaseFileNameInformation
0x140044fd2  nop     dword ptr [rax+rax+00h]
0x140044fd7  mov     eax, ebx
0x140044fd9  mov     rcx, [rbp+var_10]
0x140044fdd  xor     rcx, rsp; StackCookie
0x140044fe0  call    __security_check_cookie
0x140044fe5  mov     rbx, [rsp+70h+arg_10]
0x140044fed  add     rsp, 70h
0x140044ff1  pop     r15
0x140044ff3  pop     r14
0x140044ff5  pop     r13
0x140044ff7  pop     r12
0x140044ff9  pop     rdi
0x140044ffa  pop     rsi
0x140044ffb  pop     rbp
0x140044ffc  retn
0x140044ffe  test    r12d, r12d
0x140045001  jz      loc_1400450BF
0x140045007  mov     rdx, [r15+18h]; Instance
0x14004500b  lea     r8, [rbp+IsDirectory]; IsDirectory
0x14004500f  mov     rcx, [r15+20h]; FileObject
0x140045013  mov     [rbp+IsDirectory], 0
0x140045017  call    cs:__imp_FltIsDirectory
0x14004501e  nop     dword ptr [rax+rax+00h]
0x140045023  mov     esi, eax
0x140045025  test    eax, eax
0x140045027  jns     short loc_140045032
0x140045029  xor     r12b, r12b
0x14004502c  mov     [rbp+IsDirectory], r12b
0x140045030  jmp     short loc_140045036
0x140045032  mov     r12b, [rbp+IsDirectory]
0x140045036  mov     r9, [r15+18h]
0x14004503a  xor     r15d, r15d
0x14004503d  cmp     cs:MpFsHardeningData, r15
0x140045044  mov     r13, [rbp+FileNameInformation]
0x140045048  jz      short loc_1400450B3
0x14004504a  test    rdi, rdi
0x14004504d  jz      short loc_1400450B3
0x14004504f  test    r13, r13
0x140045052  jz      short loc_1400450B3
0x140045054  lea     rax, [rbp+var_30]
0x140045058  mov     dword ptr [rbp+var_30], r15d
0x14004505c  mov     [rsp+70h+var_40], rax; __int64
0x140045061  xor     r8d, r8d
0x140045064  xor     edx, edx; String2
0x140045066  mov     [rsp+70h+var_50], r15; __int64
0x14004506b  mov     rcx, r13; FileNameInformation
0x14004506e  call    FsHardeningMatch
0x140045073  mov     cl, al
0x140045075  test    al, al
0x140045077  jnz     short loc_14004507E
0x140045079  mov     r15b, bl
0x14004507c  jmp     short loc_1400450B3
0x14004507e  mov     eax, dword ptr [rbp+var_30]
0x140045081  and     al, bl
0x140045083  neg     al
0x140045085  sbb     r15b, r15b
0x140045088  and     r15b, cl
0x14004508b  test    byte ptr [rbp+var_30], 2
0x14004508f  jz      short loc_1400450B3
0x140045091  mov     r8, [rdi+80h]
0x140045098  mov     r9, r13
0x14004509b  mov     byte ptr [rsp+70h+var_48], r12b
0x1400450a0  mov     dl, r15b
0x1400450a3  mov     cl, bl
0x1400450a5  mov     [rsp+70h+var_50], 0
0x1400450ae  call    MpTraceFsHardeningNotification
0x1400450b3  mov     r12d, [rbp+var_28]
0x1400450b7  test    r15b, r15b
0x1400450ba  setz    al
0x1400450bd  jmp     short loc_1400450CE
0x1400450bf  mov     rdx, [rbp+FileNameInformation]
0x1400450c3  xor     r8d, r8d
0x1400450c6  mov     rcx, rdi
0x1400450c9  call    MpIsAMPath
0x1400450ce  test    al, al
0x1400450d0  jz      loc_140044F94
0x1400450d6  lfence
0x1400450d9  mov     dword ptr [r14+18h], 0C0000022h
0x1400450e1  mov     ebx, 4
0x1400450e6  mov     qword ptr [r14+20h], 0
0x1400450ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400450f5  lea     rax, WPP_GLOBAL_Control
0x1400450fc  cmp     rcx, rax
0x1400450ff  jz      short loc_140045168
0x140045101  mov     eax, [rcx+2Ch]
0x140045104  test    al, 2
0x140045106  jz      short loc_140045168
0x140045108  lfence
0x14004510b  test    rdi, rdi
0x14004510e  jz      short loc_140045119
0x140045110  mov     rsi, [rdi+80h]
0x140045117  jmp     short loc_14004511B
0x140045119  xor     esi, esi
0x14004511b  call    cs:__imp_PsGetCurrentProcessId
0x140045122  nop     dword ptr [rax+rax+00h]
0x140045127  xor     ecx, ecx
0x140045129  mov     edx, 1Bh
0x14004512e  mov     r8, rax
0x140045131  test    r12d, r12d
0x140045134  mov     rax, [r14+10h]
0x140045138  setnz   cl
0x14004513b  mov     dword ptr [rsp+70h+var_40], ecx
0x14004513f  mov     rcx, cs:WPP_GLOBAL_Control
0x140045146  mov     r9, [rax+8]
0x14004514a  mov     [rsp+70h+var_48], r8d
0x14004514f  add     r9, 58h ; 'X'
0x140045153  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x14004515a  mov     [rsp+70h+var_50], rsi
0x14004515f  mov     rcx, [rcx+18h]
0x140045163  call    WPP_SF_ZZDd
0x140045168  test    rdi, rdi
0x14004516b  jz      short loc_140045176
0x14004516d  mov     rsi, [rdi+80h]
0x140045174  jmp     short loc_140045178
0x140045176  xor     esi, esi
0x140045178  call    cs:__imp_PsGetCurrentProcessId
0x14004517f  nop     dword ptr [rax+rax+00h]
0x140045184  xor     ecx, ecx
0x140045186  mov     r8, rsi
0x140045189  mov     r9, rax
0x14004518c  test    r12d, r12d
0x14004518f  mov     rax, [r14+10h]
0x140045193  setnz   cl
0x140045196  mov     dword ptr [rsp+70h+var_50], ecx
0x14004519a  lea     rcx, aMiniFilterDeni_1; "[Mini-filter] Denied access to file [%w"...
0x1400451a1  mov     rdx, [rax+8]
0x1400451a5  add     rdx, 58h ; 'X'
0x1400451a9  call    MpLogPrintfW
0x1400451ae  jmp     loc_140044FB5
```
