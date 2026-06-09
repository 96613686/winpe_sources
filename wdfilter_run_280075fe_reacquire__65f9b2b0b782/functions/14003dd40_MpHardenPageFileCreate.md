# MpHardenPageFileCreate

- ea: `0x14003dd40`
- end: `0x14003e0c2`
- name: `MpHardenPageFileCreate`
- size: `898`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003c990`

## callees

- `0x140002450`
- `0x1400051bc`
- `0x1400068fc`
- `0x1400118d0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003dd40`
- `0x14003ee80`
- `0x140040388`
- `0x140046e30`
- `0x1400471ac`
- `0x14008ab44`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14003dfd0`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003e02d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003dfd0`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003e02d`
- `FLTMGR!FltGetFileNameInformation` at `0x14003de6f`
- `FLTMGR!FltGetFileNameInformation` at `0x14003de6f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003e081`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003e081`

## string_xrefs

- `0x14003e03d`: `[Mini-filter] Denied access to file [%wZ] from process [%wZ][Pid:%u]. DynamicFsHardeningEnabled[%d].`

## pseudocode

```c
__int64 __fastcall MpHardenPageFileCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  int v2; // ebp
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  struct _KPROCESS *RequestorProcess; // rax
  int ProcessContextByObject; // ebx
  int v8; // r15d
  char IsAMPath; // al
  char CurrentProcessId; // al
  unsigned int v11; // eax
  __int64 v12; // [rsp+20h] [rbp-68h]
  __int64 v13; // [rsp+40h] [rbp-48h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+48h] [rbp-40h] BYREF

  v2 = a2;
  v13 = 0;
  FileNameInformation = 0;
  if ( !CallbackData )
    return 3221225485LL;
  if ( !a2 )
    return 3221225485LL;
  Iopb = CallbackData->Iopb;
  if ( Iopb->MajorFunction || (Iopb->OperationFlags & 2) == 0 )
    return 3221225485LL;
  if ( !dword_140026A20 )
    return 0;
  RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(CallbackData);
  if ( !RequestorProcess || RequestorProcess == *(struct _KPROCESS **)(MpData + 232) )
    return 0;
  ProcessContextByObject = MpGetProcessContextByObject(RequestorProcess);
  if ( ProcessContextByObject >= 0 )
  {
    _mm_lfence();
    v8 = *(_DWORD *)(MpData + 868) & 0x4000;
    if ( (unsigned __int8)MpCheckForAmHardening((_DWORD)CallbackData, v2, 0, v13, 0) )
    {
      ProcessContextByObject = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
      if ( ProcessContextByObject >= 0 )
      {
        if ( v8 )
          IsAMPath = 1;
        else
          IsAMPath = MpIsAMPath(v13, FileNameInformation);
        if ( IsAMPath )
        {
          CallbackData->IoStatus.Status = -1073741790;
          ProcessContextByObject = 1835009;
          CallbackData->IoStatus.Information = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
            WPP_SF_ZZDd(
              WPP_GLOBAL_Control->AttachedDevice,
              99,
              (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
              &CallbackData->Iopb->TargetFileObject->FileName,
              0,
              CurrentProcessId,
              v8 != 0);
          }
          v11 = (unsigned int)PsGetCurrentProcessId();
          LODWORD(v12) = v8 != 0;
          MpLogPrintfW(
            L"[Mini-filter] Denied access to file [%wZ] from process [%wZ][Pid:%u]. DynamicFsHardeningEnabled[%d].",
            &CallbackData->Iopb->TargetFileObject->FileName,
            0,
            v11,
            v12);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            98,
            WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
            KeGetCurrentThread(),
            ProcessContextByObject);
        }
        if ( ProcessContextByObject == -1073741536 || ProcessContextByObject == -1073741749 )
        {
          CallbackData->IoStatus.Status = ProcessContextByObject;
          ProcessContextByObject = 1835009;
          CallbackData->IoStatus.Information = 0;
        }
      }
    }
    if ( FileNameInformation )
      FltReleaseFileNameInformation(FileNameInformation);
  }
  else
  {
    _mm_lfence();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        97,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        CallbackData->Thread,
        ProcessContextByObject);
  }
  return (unsigned int)ProcessContextByObject;
}

```

## disassembly

```asm
0x14003dd40  mov     r11, rsp
0x14003dd43  mov     [r11+18h], rbx
0x14003dd47  mov     [r11+20h], rbp
0x14003dd4b  push    rsi
0x14003dd4c  push    rdi
0x14003dd4d  push    r12
0x14003dd4f  push    r14
0x14003dd51  push    r15
0x14003dd53  sub     rsp, 60h
0x14003dd57  mov     rax, cs:__security_cookie
0x14003dd5e  xor     rax, rsp
0x14003dd61  mov     [rsp+88h+var_38], rax
0x14003dd66  xor     r12d, r12d
0x14003dd69  mov     rbp, rdx
0x14003dd6c  mov     [r11-48h], r12
0x14003dd70  mov     rdi, rcx
0x14003dd73  mov     [r11-40h], r12
0x14003dd77  test    rcx, rcx
0x14003dd7a  jz      loc_14003E096
0x14003dd80  test    rdx, rdx
0x14003dd83  jz      loc_14003E096
0x14003dd89  mov     rax, [rcx+10h]
0x14003dd8d  cmp     [rax+4], r12b
0x14003dd91  jnz     loc_14003E096
0x14003dd97  test    byte ptr [rax+6], 2
0x14003dd9b  jz      loc_14003E096
0x14003dda1  cmp     cs:dword_140026A20, r12d
0x14003dda8  jz      loc_14003E092
0x14003ddae  call    MpGetRequestorProcess
0x14003ddb3  test    rax, rax
0x14003ddb6  jz      loc_14003E092
0x14003ddbc  mov     rcx, cs:MpData
0x14003ddc3  cmp     rax, [rcx+0E8h]
0x14003ddca  jz      loc_14003E092
0x14003ddd0  lea     rdx, [rsp+88h+var_48]
0x14003ddd5  mov     rcx, rax; Process
0x14003ddd8  call    MpGetProcessContextByObject
0x14003dddd  mov     ebx, eax
0x14003dddf  test    eax, eax
0x14003dde1  jns     short loc_14003DE27
0x14003dde3  lfence
0x14003dde6  mov     r10, cs:WPP_GLOBAL_Control
0x14003dded  lea     rax, WPP_GLOBAL_Control
0x14003ddf4  cmp     r10, rax
0x14003ddf7  jz      short loc_14003DE20
0x14003ddf9  mov     edx, [r10+2Ch]
0x14003ddfd  mov     cl, 1
0x14003ddff  test    cl, dl
0x14003de01  jz      short loc_14003DE20
0x14003de03  mov     r9, [rdi+8]
0x14003de07  lea     edx, [r12+61h]
0x14003de0c  mov     rcx, [r10+18h]
0x14003de10  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x14003de17  mov     dword ptr [rsp+88h+var_68], ebx
0x14003de1b  call    WPP_SF_qD
0x14003de20  mov     eax, ebx
0x14003de22  jmp     loc_14003E09B
0x14003de27  lfence
0x14003de2a  mov     rax, cs:MpData
0x14003de31  xor     r8d, r8d
0x14003de34  mov     rsi, [rsp+88h+var_48]
0x14003de39  mov     rdx, rbp
0x14003de3c  mov     r9, rsi
0x14003de3f  mov     byte ptr [rsp+88h+var_68], r12b
0x14003de44  mov     rcx, rdi
0x14003de47  mov     r15d, [rax+364h]
0x14003de4e  and     r15d, 4000h
0x14003de55  call    MpCheckForAmHardening
0x14003de5a  test    al, al
0x14003de5c  jz      loc_14003E066
0x14003de62  lea     r8, [rsp+88h+FileNameInformation]; FileNameInformation
0x14003de67  mov     edx, 101h; NameOptions
0x14003de6c  mov     rcx, rdi; CallbackData
0x14003de6f  call    cs:__imp_FltGetFileNameInformation
0x14003de76  nop     dword ptr [rax+rax+00h]
0x14003de7b  mov     ebx, eax
0x14003de7d  test    eax, eax
0x14003de7f  jns     short loc_14003DEEF
0x14003de81  mov     rcx, cs:WPP_GLOBAL_Control
0x14003de88  lea     rax, WPP_GLOBAL_Control
0x14003de8f  cmp     rcx, rax
0x14003de92  jz      short loc_14003DEC9
0x14003de94  mov     eax, [rcx+2Ch]
0x14003de97  mov     cl, 1
0x14003de99  test    cl, al
0x14003de9b  jz      short loc_14003DEC9
0x14003de9d  lfence
0x14003dea0  mov     r9, gs:188h
0x14003dea9  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x14003deb0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003deb7  mov     edx, 62h ; 'b'
0x14003debc  mov     dword ptr [rsp+88h+var_68], ebx
0x14003dec0  mov     rcx, [rcx+18h]
0x14003dec4  call    WPP_SF_qD
0x14003dec9  mov     eax, ebx
0x14003decb  cmp     ebx, 0C0000120h
0x14003ded1  jz      short loc_14003DEDE
0x14003ded3  cmp     eax, 0C000004Bh
0x14003ded8  jnz     loc_14003E066
0x14003dede  mov     [rdi+18h], eax
0x14003dee1  mov     ebx, 1C0001h
0x14003dee6  mov     [rdi+20h], r12
0x14003deea  jmp     loc_14003E066
0x14003deef  test    r15d, r15d
0x14003def2  jz      loc_14003DF7D
0x14003def8  cmp     cs:MpFsHardeningData, r12
0x14003deff  mov     r9, [rbp+18h]
0x14003df03  mov     r14, [rsp+88h+FileNameInformation]
0x14003df08  jz      short loc_14003DF73
0x14003df0a  test    rsi, rsi
0x14003df0d  jz      short loc_14003DF73
0x14003df0f  test    r14, r14
0x14003df12  jz      short loc_14003DF73
0x14003df14  lea     rax, [rsp+88h+var_48]
0x14003df19  mov     dword ptr [rsp+88h+var_48], r12d
0x14003df1e  mov     [rsp+88h+var_58], rax; __int64
0x14003df23  xor     r8d, r8d
0x14003df26  xor     edx, edx; String2
0x14003df28  mov     [rsp+88h+var_68], r12; __int64
0x14003df2d  mov     rcx, r14; FileNameInformation
0x14003df30  call    FsHardeningMatch
0x14003df35  mov     dl, al
0x14003df37  mov     cl, 1
0x14003df39  test    al, al
0x14003df3b  jz      short loc_14003DF76
0x14003df3d  mov     eax, dword ptr [rsp+88h+var_48]
0x14003df41  and     al, cl
0x14003df43  neg     al
0x14003df45  sbb     bpl, bpl
0x14003df48  and     bpl, dl
0x14003df4b  test    byte ptr [rsp+88h+var_48], 2
0x14003df50  jz      short loc_14003DF6E
0x14003df52  mov     r8, [rsi+80h]
0x14003df59  mov     r9, r14
0x14003df5c  mov     byte ptr [rsp+88h+var_60], r12b
0x14003df61  mov     dl, bpl
0x14003df64  mov     [rsp+88h+var_68], r12
0x14003df69  call    MpTraceFsHardeningNotification
0x14003df6e  mov     cl, bpl
0x14003df71  jmp     short loc_14003DF76
0x14003df73  mov     cl, r12b
0x14003df76  test    cl, cl
0x14003df78  setz    al
0x14003df7b  jmp     short loc_14003DF8D
0x14003df7d  mov     rdx, [rsp+88h+FileNameInformation]
0x14003df82  xor     r8d, r8d
0x14003df85  mov     rcx, rsi
0x14003df88  call    MpIsAMPath
0x14003df8d  test    al, al
0x14003df8f  jz      loc_14003E066
0x14003df95  mov     dword ptr [rdi+18h], 0C0000022h
0x14003df9c  mov     ebx, 1C0001h
0x14003dfa1  mov     [rdi+20h], r12
0x14003dfa5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dfac  lea     rax, WPP_GLOBAL_Control
0x14003dfb3  cmp     rcx, rax
0x14003dfb6  jz      short loc_14003E01C
0x14003dfb8  mov     eax, [rcx+2Ch]
0x14003dfbb  test    al, 2
0x14003dfbd  jz      short loc_14003E01C
0x14003dfbf  test    rsi, rsi
0x14003dfc2  jz      short loc_14003DFCD
0x14003dfc4  mov     rbp, [rsi+80h]
0x14003dfcb  jmp     short loc_14003DFD0
0x14003dfcd  mov     rbp, r12
0x14003dfd0  call    cs:__imp_PsGetCurrentProcessId
0x14003dfd7  nop     dword ptr [rax+rax+00h]
0x14003dfdc  mov     rcx, [rdi+10h]
0x14003dfe0  mov     r8d, r12d
0x14003dfe3  test    r15d, r15d
0x14003dfe6  mov     edx, 63h ; 'c'
0x14003dfeb  setnz   r8b
0x14003dfef  mov     r9, [rcx+8]
0x14003dff3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dffa  add     r9, 58h ; 'X'
0x14003dffe  mov     dword ptr [rsp+88h+var_58], r8d
0x14003e003  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x14003e00a  mov     [rsp+88h+var_60], eax
0x14003e00e  mov     [rsp+88h+var_68], rbp
0x14003e013  mov     rcx, [rcx+18h]
0x14003e017  call    WPP_SF_ZZDd
0x14003e01c  test    rsi, rsi
0x14003e01f  jz      short loc_14003E02A
0x14003e021  mov     rbp, [rsi+80h]
0x14003e028  jmp     short loc_14003E02D
0x14003e02a  mov     rbp, r12
0x14003e02d  call    cs:__imp_PsGetCurrentProcessId
0x14003e034  nop     dword ptr [rax+rax+00h]
0x14003e039  mov     rdx, [rdi+10h]
0x14003e03d  lea     rcx, aMiniFilterDeni_1; "[Mini-filter] Denied access to file [%w"...
0x14003e044  mov     r9d, r12d
0x14003e047  test    r15d, r15d
0x14003e04a  mov     r8, rbp
0x14003e04d  setnz   r9b
0x14003e051  mov     rdx, [rdx+8]
0x14003e055  mov     dword ptr [rsp+88h+var_68], r9d
0x14003e05a  add     rdx, 58h ; 'X'
0x14003e05e  mov     r9d, eax
0x14003e061  call    MpLogPrintfW
0x14003e066  test    rsi, rsi
0x14003e069  jz      short loc_14003E073
0x14003e06b  mov     rcx, rsi
0x14003e06e  call    MpReleaseProcessContext
0x14003e073  mov     rcx, [rsp+88h+FileNameInformation]; FileNameInformation
0x14003e078  test    rcx, rcx
0x14003e07b  jz      loc_14003DE20
0x14003e081  call    cs:__imp_FltReleaseFileNameInformation
0x14003e088  nop     dword ptr [rax+rax+00h]
0x14003e08d  jmp     loc_14003DE20
0x14003e092  xor     eax, eax
0x14003e094  jmp     short loc_14003E09B
0x14003e096  mov     eax, 0C000000Dh
0x14003e09b  mov     rcx, [rsp+88h+var_38]
0x14003e0a0  xor     rcx, rsp; StackCookie
0x14003e0a3  call    __security_check_cookie
0x14003e0a8  lea     r11, [rsp+88h+var_28]
0x14003e0ad  mov     rbx, [r11+40h]
0x14003e0b1  mov     rbp, [r11+48h]
0x14003e0b5  mov     rsp, r11
0x14003e0b8  pop     r15
0x14003e0ba  pop     r14
0x14003e0bc  pop     r12
0x14003e0be  pop     rdi
0x14003e0bf  pop     rsi
0x14003e0c0  retn
```
