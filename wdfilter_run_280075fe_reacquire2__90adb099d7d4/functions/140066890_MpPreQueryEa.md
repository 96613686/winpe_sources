# MpPreQueryEa

- ea: `0x140066890`
- end: `0x140066db3`
- name: `MpPreQueryEa`
- size: `1315`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140002450`
- `0x1400049dc`
- `0x1400118d0`
- `0x140011900`
- `0x140011bc0`
- `0x140066890`
- `0x140066dc0`

## import_xrefs

- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14006697d`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14006697d`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140066969`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140066969`
- `ntoskrnl!PsInitialSystemProcess` at `0x140066941`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x140066d31`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x140066d31`
- `FLTMGR!FltGetFileNameInformation` at `0x140066a58`
- `FLTMGR!FltGetFileNameInformation` at `0x140066a58`
- `FLTMGR!FltGetFileSystemType` at `0x14006690d`
- `FLTMGR!FltGetFileSystemType` at `0x14006690d`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140066d4d`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140066d4d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140066d93`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008cd22`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140066d93`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008cd22`

## pseudocode

```c
__int64 __fastcall MpPreQueryEa(PFLT_CALLBACK_DATA Data, __int64 a2, _QWORD *a3)
{
  unsigned int v5; // r12d
  struct _KPROCESS *RequestorProcess; // rax
  PACCESS_TOKEN v7; // rax
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  unsigned __int8 *EaList; // rcx
  unsigned int LowPart; // r8d
  int v11; // edx
  unsigned __int8 *v12; // rax
  ULONG_PTR v13; // r8
  int v14; // ecx
  int v15; // edx
  int v17; // ebx
  PFLT_IO_PARAMETER_BLOCK v18; // r14
  size_t Length; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v20; // rdx
  struct _FILE_FULL_EA_INFORMATION *EaBuffer; // r14
  size_t v22; // r9
  CHAR *EaName; // rcx
  char *v24; // r15
  unsigned __int64 v25; // rsi
  unsigned __int64 v26; // rax
  int v27; // edx
  unsigned int v28; // r8d
  __int64 v29; // rbx
  unsigned __int64 v30; // rdx
  __int64 v31; // r8
  unsigned __int64 v32; // r12
  __int64 v33; // rax
  size_t v34; // r8
  ULONG v35; // r15d
  bool v36; // al
  char *v37; // rcx
  unsigned __int64 v38; // r15
  int v39; // eax
  unsigned int v40; // ecx
  __int64 v41; // rbx
  unsigned __int64 v42; // rax
  ULONG EaLength; // [rsp+30h] [rbp-78h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-58h] BYREF
  char v45; // [rsp+58h] [rbp-50h]
  unsigned __int8 EffectiveOnly; // [rsp+59h] [rbp-4Fh] BYREF
  unsigned __int8 CopyOnOpen[2]; // [rsp+5Ah] [rbp-4Eh] BYREF
  enum _FLT_FILESYSTEM_TYPE FileSystemType; // [rsp+5Ch] [rbp-4Ch] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+60h] [rbp-48h] BYREF
  ULONG ErrorOffset; // [rsp+64h] [rbp-44h] BYREF

  FileSystemType = FLT_FSTYPE_UNKNOWN;
  CopyOnOpen[0] = 0;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityAnonymous;
  v5 = 0;
  FileNameInformation = 0;
  if ( !*(_QWORD *)(a2 + 32) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids);
    return 1;
  }
  *a3 = 0;
  v45 = 0;
  MpQueryEaFromNetworkFileStubIfNeeded(Data);
  if ( FltGetFileSystemType(*(PVOID *)(a2 + 24), &FileSystemType) < 0 )
    return 1;
  if ( FileSystemType == FLT_FSTYPE_MUP )
    return 1;
  RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(Data);
  if ( !RequestorProcess )
    return 1;
  if ( PsInitialSystemProcess != RequestorProcess )
    return 1;
  v7 = PsReferenceImpersonationToken(KeGetCurrentThread(), CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  if ( !v7 )
    return 1;
  PsDereferenceImpersonationToken(v7);
  Iopb = Data->Iopb;
  if ( Iopb->Parameters.Create.AllocationSize.QuadPart )
    return 1;
  EaList = (unsigned __int8 *)Iopb->Parameters.QueryEa.EaList;
  if ( !EaList )
    return 1;
  LowPart = Iopb->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart < 8 )
    return 1;
  if ( *(_DWORD *)EaList )
    return 1;
  v11 = EaList[4];
  if ( v11 + 6 > LowPart || *(_BYTE *)(MpData + 3904) != (_BYTE)v11 )
    return 1;
  v12 = EaList + 5;
  v13 = MpData + 3648 - (_QWORD)(EaList + 5);
  do
  {
    v14 = v12[v13];
    v15 = *v12 - v14;
    if ( v15 )
      break;
    ++v12;
  }
  while ( v14 );
  if ( v15 )
    return 1;
  v17 = FltGetFileNameInformation(Data, 0x101u, &FileNameInformation);
  if ( v17 < 0 )
    goto LABEL_68;
  _mm_lfence();
  v18 = Data->Iopb;
  Length = v18->Parameters.Read.Length;
  EaLength = Length;
  v20 = FileNameInformation;
  if ( FileNameInformation->Name.Length + (unsigned int)*(unsigned __int8 *)(MpData + 3904) + 23 <= (unsigned int)Length )
  {
    EaBuffer = (struct _FILE_FULL_EA_INFORMATION *)v18->Parameters.Create.EaBuffer;
    memset(EaBuffer, 0, Length);
    EaBuffer->NextEntryOffset = 0;
    EaBuffer->Flags = 0;
    EaBuffer->EaNameLength = *(_BYTE *)(MpData + 3904);
    EaBuffer->EaValueLength = FileNameInformation->Name.Length + 14;
    v22 = *(unsigned __int8 *)(MpData + 3904);
    if ( EaBuffer )
    {
      if ( (_DWORD)Length )
      {
        EaName = EaBuffer->EaName;
        if ( EaBuffer->EaName >= (CHAR *)EaBuffer )
        {
          v24 = (char *)EaBuffer + Length;
          if ( (struct _FILE_FULL_EA_INFORMATION *)((char *)EaBuffer + Length) >= EaBuffer )
          {
            v25 = -1;
            if ( v24 < EaName )
            {
              v27 = -1073741675;
              v26 = -1;
              v28 = -1;
            }
            else
            {
              v26 = v24 - EaName;
              v27 = 0;
              v28 = (_DWORD)v24 - (_DWORD)EaName;
            }
            if ( v27 >= 0 && v26 <= 0xFFFFFFFF && (unsigned int)v22 <= v28 && (unsigned int)v22 <= (unsigned int)Length )
            {
              v29 = *(unsigned __int8 *)(MpData + 3904);
              memmove(EaName, (const void *)(MpData + 3648), v22);
              v30 = v29 + 9;
              if ( (unsigned __int64)(v29 + 9) < 8 )
              {
                v17 = -1073741675;
                v30 = -1;
                v31 = -1;
              }
              else
              {
                v17 = 0;
                v31 = v30;
              }
              if ( v17 < 0 )
                goto LABEL_67;
              *(ULONG *)((char *)&EaBuffer->NextEntryOffset + v31) = EaBuffer->EaValueLength;
              *(_DWORD *)&EaBuffer->EaName[v31] = FileNameInformation->Volume.Length;
              *(_DWORD *)(&EaBuffer->Flags + v31) = FileNameInformation->Name.Length;
              v32 = v30 + 12;
              if ( v30 + 12 < v30 )
              {
                v32 = -1;
                v17 = -1073741675;
                v33 = -1;
              }
              else
              {
                v17 = 0;
                v33 = v30 + 12;
              }
              if ( v17 < 0 )
              {
LABEL_67:
                v5 = 0;
                goto LABEL_68;
              }
              v20 = FileNameInformation;
              v34 = FileNameInformation->Name.Length;
              if ( v33 )
              {
                v37 = (char *)EaBuffer + v33;
                if ( (struct _FILE_FULL_EA_INFORMATION *)((char *)EaBuffer + v33) < EaBuffer )
                  goto LABEL_64;
                if ( v24 < v37 )
                {
                  v39 = -1073741675;
                  v38 = -1;
                  v40 = -1;
                }
                else
                {
                  v38 = v24 - v37;
                  v39 = 0;
                  v40 = v38;
                }
                if ( v39 < 0 )
                  goto LABEL_64;
                if ( v38 > 0xFFFFFFFF )
                  goto LABEL_64;
                if ( (unsigned int)v34 > v40 )
                  goto LABEL_64;
                v35 = EaLength;
                if ( (unsigned int)v34 > EaLength )
                  goto LABEL_64;
                v36 = 1;
              }
              else
              {
                v35 = EaLength;
                v36 = (unsigned int)v34 <= EaLength;
              }
              if ( v36 )
              {
                v41 = FileNameInformation->Name.Length;
                memmove((char *)EaBuffer + v32, FileNameInformation->Name.Buffer, v34);
                v42 = v32 + v41 + 2;
                if ( v42 < v32 )
                {
                  LODWORD(v42) = -1;
                  v17 = -1073741675;
                }
                else
                {
                  v17 = 0;
                  v25 = v42;
                }
                if ( v17 >= 0 )
                {
                  v5 = -1;
                  if ( v25 > 0xFFFFFFFF )
                  {
                    v17 = -1073741675;
                  }
                  else
                  {
                    v5 = v42;
                    _mm_lfence();
                    ErrorOffset = 0;
                    v17 = IoCheckEaBufferValidity(EaBuffer, v35, &ErrorOffset);
                    if ( v17 >= 0 )
                    {
                      _mm_lfence();
                      FltSetCallbackDataDirty(Data);
                      v17 = 0;
                    }
                  }
                  goto LABEL_68;
                }
                goto LABEL_67;
              }
LABEL_64:
              v17 = -1073741789;
              v5 = 0;
              goto LABEL_69;
            }
            v5 = 0;
          }
        }
      }
    }
    v17 = -1073741789;
LABEL_68:
    v20 = FileNameInformation;
    goto LABEL_69;
  }
  v17 = -1073741789;
LABEL_69:
  if ( v20 )
    FltReleaseFileNameInformation(v20);
  Data->IoStatus.Status = v17;
  Data->IoStatus.Information = v5;
  return 4;
}

```

## disassembly

```asm
0x140066890  mov     r11, rsp
0x140066893  push    rbx
0x140066894  push    rsi
0x140066895  push    rdi
0x140066896  push    r12
0x140066898  push    r13
0x14006689a  push    r14
0x14006689c  push    r15
0x14006689e  sub     rsp, 70h
0x1400668a2  mov     rax, cs:__security_cookie
0x1400668a9  xor     rax, rsp
0x1400668ac  mov     [rsp+0A8h+var_40], rax
0x1400668b1  mov     rbx, rdx
0x1400668b4  mov     rdi, rcx
0x1400668b7  mov     [rsp+0A8h+var_60], rcx
0x1400668bc  xor     r13d, r13d
0x1400668bf  mov     [r11-4Ch], r13d
0x1400668c3  mov     [r11-4Eh], r13b
0x1400668c7  mov     [r11-4Fh], r13b
0x1400668cb  mov     [r11-48h], r13d
0x1400668cf  mov     r12d, r13d
0x1400668d2  mov     [rsp+0A8h+var_84], r13d
0x1400668d7  mov     [r11-74h], r13d
0x1400668db  mov     [r11-58h], r13
0x1400668df  cmp     [rdx+20h], r12
0x1400668e3  jz      loc_140066A1A
0x1400668e9  mov     [r8], r13
0x1400668ec  mov     [r11-50h], r12b
0x1400668f0  lea     r8, [r11-50h]
0x1400668f4  call    MpQueryEaFromNetworkFileStubIfNeeded
0x1400668f9  cmp     [rsp+0A8h+var_50], r12b
0x1400668fe  jnz     loc_140066DA9
0x140066904  lea     rdx, [rsp+0A8h+FileSystemType]; FileSystemType
0x140066909  mov     rcx, [rbx+18h]; FltObject
0x14006690d  call    cs:__imp_FltGetFileSystemType
0x140066914  nop     dword ptr [rax+rax+00h]
0x140066919  mov     [rsp+0A8h+var_88], eax
0x14006691d  test    eax, eax
0x14006691f  js      loc_1400669F7
0x140066925  cmp     [rsp+0A8h+FileSystemType], 0Dh
0x14006692a  jz      loc_1400669F7
0x140066930  mov     rcx, rdi
0x140066933  call    MpGetRequestorProcess
0x140066938  test    rax, rax
0x14006693b  jz      loc_1400669F7
0x140066941  mov     rcx, cs:__imp_PsInitialSystemProcess
0x140066948  cmp     [rcx], rax
0x14006694b  jnz     loc_1400669F7
0x140066951  mov     rcx, gs:188h; Thread
0x14006695a  lea     r9, [rsp+0A8h+ImpersonationLevel]; ImpersonationLevel
0x14006695f  lea     r8, [rsp+0A8h+EffectiveOnly]; EffectiveOnly
0x140066964  lea     rdx, [rsp+0A8h+CopyOnOpen]; CopyOnOpen
0x140066969  call    cs:__imp_PsReferenceImpersonationToken
0x140066970  nop     dword ptr [rax+rax+00h]
0x140066975  test    rax, rax
0x140066978  jz      short loc_1400669F7
0x14006697a  mov     rcx, rax; ImpersonationToken
0x14006697d  call    cs:__imp_PsDereferenceImpersonationToken
0x140066984  nop     dword ptr [rax+rax+00h]
0x140066989  mov     rax, [rdi+10h]
0x14006698d  cmp     [rax+40h], r12
0x140066991  jnz     short loc_1400669F7
0x140066993  mov     rcx, [rax+20h]
0x140066997  test    rcx, rcx
0x14006699a  jz      short loc_1400669F7
0x14006699c  mov     r8d, [rax+28h]
0x1400669a0  cmp     r8d, 8
0x1400669a4  jb      short loc_1400669F7
0x1400669a6  cmp     [rcx], r13d
0x1400669a9  jnz     short loc_1400669F7
0x1400669ab  movzx   edx, byte ptr [rcx+4]
0x1400669af  lea     eax, [rdx+6]
0x1400669b2  cmp     eax, r8d
0x1400669b5  ja      short loc_1400669F7
0x1400669b7  mov     r8, cs:MpData
0x1400669be  cmp     [r8+0F40h], dl
0x1400669c5  jnz     short loc_1400669F7
0x1400669c7  add     r8, 0E40h
0x1400669ce  lea     rax, [rcx+5]
0x1400669d2  sub     r8, rax
0x1400669d5  nop     word ptr [rax+rax+00000000h]
0x1400669e0  movzx   edx, byte ptr [rax]
0x1400669e3  movzx   ecx, byte ptr [rax+r8]
0x1400669e8  sub     edx, ecx
0x1400669ea  jnz     short loc_1400669F3
0x1400669ec  inc     rax
0x1400669ef  test    ecx, ecx
0x1400669f1  jnz     short loc_1400669E0
0x1400669f3  test    edx, edx
0x1400669f5  jz      short loc_140066A4B
0x1400669f7  mov     eax, 1
0x1400669fc  mov     rcx, [rsp+0A8h+var_40]
0x140066a01  xor     rcx, rsp; StackCookie
0x140066a04  call    __security_check_cookie
0x140066a09  add     rsp, 70h
0x140066a0d  pop     r15
0x140066a0f  pop     r14
0x140066a11  pop     r13
0x140066a13  pop     r12
0x140066a15  pop     rdi
0x140066a16  pop     rsi
0x140066a17  pop     rbx
0x140066a18  retn
0x140066a1a  lea     rax, WPP_GLOBAL_Control
0x140066a21  mov     rcx, cs:WPP_GLOBAL_Control
0x140066a28  cmp     rcx, rax
0x140066a2b  jz      short loc_1400669F7
0x140066a2d  mov     eax, [rcx+2Ch]
0x140066a30  test    al, 1
0x140066a32  jz      short loc_1400669F7
0x140066a34  mov     edx, 2Bh ; '+'
0x140066a39  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x140066a40  mov     rcx, [rcx+18h]
0x140066a44  call    WPP_SF_
0x140066a49  jmp     short loc_1400669F7
0x140066a4b  lea     r8, [rsp+0A8h+FileNameInformation]; FileNameInformation
0x140066a50  mov     edx, 101h; NameOptions
0x140066a55  mov     rcx, rdi; CallbackData
0x140066a58  call    cs:__imp_FltGetFileNameInformation
0x140066a5f  nop     dword ptr [rax+rax+00h]
0x140066a64  mov     ebx, eax
0x140066a66  mov     [rsp+0A8h+var_88], eax
0x140066a6a  test    eax, eax
0x140066a6c  js      loc_140066D86
0x140066a72  lfence
0x140066a75  mov     r14, [rdi+10h]
0x140066a79  mov     ebx, [r14+18h]
0x140066a7d  mov     [rsp+0A8h+EaLength], ebx
0x140066a81  mov     rax, cs:MpData
0x140066a88  movzx   ecx, byte ptr [rax+0F40h]
0x140066a8f  mov     rdx, [rsp+0A8h+FileNameInformation]
0x140066a94  movzx   eax, word ptr [rdx+8]
0x140066a98  add     ecx, 17h
0x140066a9b  add     ecx, eax
0x140066a9d  cmp     ecx, ebx
0x140066a9f  jbe     short loc_140066AAF
0x140066aa1  mov     ebx, 0C0000023h
0x140066aa6  mov     [rsp+0A8h+var_88], ebx
0x140066aaa  jmp     loc_140066D8B
0x140066aaf  mov     r14, [r14+38h]
0x140066ab3  mov     [rsp+0A8h+var_80], r13
0x140066ab8  mov     r8, rbx; Size
0x140066abb  xor     edx, edx; Val
0x140066abd  mov     rcx, r14; void *
0x140066ac0  call    memset
0x140066ac5  mov     [rsp+0A8h+var_88], r13d
0x140066aca  mov     [r14], r13d
0x140066acd  mov     byte ptr [r14+4], 0
0x140066ad2  mov     rax, cs:MpData
0x140066ad9  movzx   ecx, byte ptr [rax+0F40h]
0x140066ae0  mov     [r14+5], cl
0x140066ae4  mov     rax, [rsp+0A8h+FileNameInformation]
0x140066ae9  movzx   ecx, word ptr [rax+8]
0x140066aed  add     cx, 0Eh
0x140066af1  mov     [r14+6], cx
0x140066af6  mov     [rsp+0A8h+var_80], 8
0x140066aff  mov     r10, cs:MpData
0x140066b06  movzx   r9d, byte ptr [r10+0F40h]
0x140066b0e  mov     [rsp+0A8h+var_70], r13
0x140066b13  test    r14, r14
0x140066b16  jz      loc_140066D76
0x140066b1c  test    ebx, ebx
0x140066b1e  jz      loc_140066D76
0x140066b24  lea     rcx, [r14+8]; void *
0x140066b28  cmp     rcx, r14
0x140066b2b  jb      loc_140066D76
0x140066b31  lea     r15, [rbx+r14]
0x140066b35  cmp     r15, r14
0x140066b38  jb      loc_140066D76
0x140066b3e  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x140066b45  mov     r12d, 0C0000095h
0x140066b4b  cmp     r15, rcx
0x140066b4e  jb      short loc_140066B69
0x140066b50  mov     rax, r15
0x140066b53  sub     rax, rcx
0x140066b56  mov     [rsp+0A8h+var_70], rax
0x140066b5b  mov     edx, r13d
0x140066b5e  mov     r8d, eax
0x140066b61  mov     r13d, 0FFFFFFFFh
0x140066b67  jmp     short loc_140066B7D
0x140066b69  mov     [rsp+0A8h+var_70], rsi
0x140066b6e  mov     edx, r12d
0x140066b71  mov     rax, rsi
0x140066b74  mov     r13d, 0FFFFFFFFh
0x140066b7a  mov     r8d, r13d
0x140066b7d  test    edx, edx
0x140066b7f  js      loc_140066D71
0x140066b85  cmp     rax, r13
0x140066b88  ja      loc_140066D71
0x140066b8e  cmp     r9d, r8d
0x140066b91  ja      loc_140066D71
0x140066b97  cmp     r9d, ebx
0x140066b9a  ja      loc_140066D71
0x140066ba0  mov     rbx, r9
0x140066ba3  lea     rdx, [r10+0E40h]; Src
0x140066baa  mov     r8, r9; Size
0x140066bad  call    memmove
0x140066bb2  lea     rdx, [rbx+9]
0x140066bb6  cmp     rdx, 8
0x140066bba  jb      short loc_140066BC8
0x140066bbc  mov     [rsp+0A8h+var_80], rdx
0x140066bc1  xor     ebx, ebx
0x140066bc3  mov     r8, rdx
0x140066bc6  jmp     short loc_140066BD6
0x140066bc8  mov     [rsp+0A8h+var_80], rsi
0x140066bcd  mov     ebx, r12d
0x140066bd0  mov     rdx, rsi
0x140066bd3  mov     r8, rsi
0x140066bd6  mov     [rsp+0A8h+var_88], ebx
0x140066bda  test    ebx, ebx
0x140066bdc  js      loc_140066D81
0x140066be2  movzx   eax, word ptr [r14+6]
0x140066be7  mov     [r14+r8], eax
0x140066beb  mov     rax, [rsp+0A8h+FileNameInformation]
0x140066bf0  movzx   ecx, word ptr [rax+18h]
0x140066bf4  mov     [r14+r8+8], ecx
0x140066bf9  mov     rax, [rsp+0A8h+FileNameInformation]
0x140066bfe  movzx   ecx, word ptr [rax+8]
0x140066c02  mov     [r14+r8+4], ecx
0x140066c07  lea     r12, [rdx+0Ch]
0x140066c0b  cmp     r12, rdx
0x140066c0e  jb      short loc_140066C1C
0x140066c10  mov     [rsp+0A8h+var_80], r12
0x140066c15  xor     ebx, ebx
0x140066c17  mov     rax, r12
0x140066c1a  jmp     short loc_140066C2C
0x140066c1c  mov     r12, rsi
0x140066c1f  mov     [rsp+0A8h+var_80], rsi
0x140066c24  mov     ebx, 0C0000095h
0x140066c29  mov     rax, rsi
0x140066c2c  mov     [rsp+0A8h+var_88], ebx
0x140066c30  test    ebx, ebx
0x140066c32  js      loc_140066D81
0x140066c38  mov     rdx, [rsp+0A8h+FileNameInformation]
0x140066c3d  movzx   r8d, word ptr [rdx+8]; Size
0x140066c42  mov     [rsp+0A8h+var_68], 0
0x140066c4b  test    rax, rax
0x140066c4e  jnz     short loc_140066C5D
0x140066c50  mov     r15d, [rsp+0A8h+EaLength]
0x140066c55  cmp     r8d, r15d
0x140066c58  setbe   al
0x140066c5b  jmp     short loc_140066CB8
0x140066c5d  lea     rcx, [rax+r14]
0x140066c61  cmp     rcx, r14
0x140066c64  jb      loc_140066D61
0x140066c6a  cmp     r15, rcx
0x140066c6d  jb      short loc_140066C7E
0x140066c6f  sub     r15, rcx
0x140066c72  mov     [rsp+0A8h+var_68], r15
0x140066c77  xor     eax, eax
0x140066c79  mov     ecx, r15d
0x140066c7c  jmp     short loc_140066C8E
0x140066c7e  mov     [rsp+0A8h+var_68], rsi
0x140066c83  mov     eax, 0C0000095h
0x140066c88  mov     r15, rsi
0x140066c8b  mov     ecx, r13d
0x140066c8e  test    eax, eax
0x140066c90  js      loc_140066D61
0x140066c96  cmp     r15, r13
0x140066c99  ja      loc_140066D61
0x140066c9f  cmp     r8d, ecx
0x140066ca2  ja      loc_140066D61
0x140066ca8  mov     r15d, [rsp+0A8h+EaLength]
0x140066cad  cmp     r8d, r15d
0x140066cb0  ja      loc_140066D61
0x140066cb6  mov     al, 1
0x140066cb8  test    al, al
0x140066cba  jz      loc_140066D61
0x140066cc0  mov     rbx, r8
0x140066cc3  lea     rcx, [r14+r12]; void *
0x140066cc7  mov     rdx, [rdx+10h]; Src
0x140066ccb  call    memmove
0x140066cd0  lea     rax, [rbx+2]
0x140066cd4  add     rax, r12
0x140066cd7  mov     ecx, 0C0000095h
0x140066cdc  cmp     rax, r12
0x140066cdf  jb      short loc_140066CE8
0x140066ce1  xor     ebx, ebx
0x140066ce3  mov     rsi, rax
0x140066ce6  jmp     short loc_140066CED
0x140066ce8  mov     rax, rsi
0x140066ceb  mov     ebx, ecx
0x140066ced  mov     [rsp+0A8h+var_80], rax
0x140066cf2  mov     [rsp+0A8h+var_88], ebx
0x140066cf6  test    ebx, ebx
0x140066cf8  js      loc_140066D81
0x140066cfe  mov     r12d, r13d
0x140066d01  cmp     rsi, r13
0x140066d04  cmovbe  r12d, eax
0x140066d08  mov     [rsp+0A8h+var_74], r12d
0x140066d0d  xor     ebx, ebx
0x140066d0f  cmp     rsi, r13
0x140066d12  cmova   ebx, ecx
0x140066d15  mov     [rsp+0A8h+var_88], ebx
0x140066d19  ja      short loc_140066D86
0x140066d1b  lfence
0x140066d1e  mov     [rsp+0A8h+ErrorOffset], 0
0x140066d26  lea     r8, [rsp+0A8h+ErrorOffset]; ErrorOffset
0x140066d2b  mov     edx, r15d; EaLength
0x140066d2e  mov     rcx, r14; EaBuffer
  ... truncated ...
```
