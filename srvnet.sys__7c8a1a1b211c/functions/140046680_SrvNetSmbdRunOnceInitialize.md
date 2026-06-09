# SrvNetSmbdRunOnceInitialize

- ea: `0x140046680`
- end: `0x140046a35`
- name: `SrvNetSmbdRunOnceInitialize`
- size: `949`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x14001389c`
- `0x1400163d8`
- `0x140019b78`
- `0x14001a6f4`
- `0x14002a3e0`
- `0x140045df0`
- `0x140045ed0`
- `0x140046680`

## import_xrefs

- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400468fb`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400468fb`
- `ntoskrnl!ZwLoadDriver` at `0x140046765`
- `ntoskrnl!ZwLoadDriver` at `0x140046765`
- `ntoskrnl!ZwOpenFile` at `0x1400468a6`
- `ntoskrnl!ZwOpenFile` at `0x1400468a6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140046850`
- `ntoskrnl!RtlInitUnicodeString` at `0x140046850`
- `ntoskrnl!ZwClose` at `0x140046914`
- `ntoskrnl!ZwClose` at `0x140046914`

## pseudocode

```c
_BOOL8 __fastcall SrvNetSmbdRunOnceInitialize(PRTL_RUN_ONCE a1, PVOID a2, PVOID *a3)
{
  int SMBDirectServicePath; // eax
  int v4; // r8d
  NTSTATUS v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // r15
  __int64 *v10; // rax
  _OWORD *v11; // rcx
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int64 v19; // rax
  struct _UNICODE_STRING DriverServiceName; // [rsp+50h] [rbp-B0h] BYREF
  __int64 InputBuffer; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t SourceString[128]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v27[256]; // [rsp+1C0h] [rbp+C0h] BYREF

  *(_QWORD *)&DriverServiceName.Length = 0x1000000;
  DriverServiceName.Buffer = (PWSTR)v27;
  SMBDirectServicePath = SrvNetGetSMBDirectServicePath(&DriverServiceName);
  v5 = SMBDirectServicePath;
  if ( SMBDirectServicePath >= 0 )
  {
    v9 = 2;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids,
        &DriverServiceName);
    }
    v5 = ZwLoadDriver(&DriverServiceName);
    if ( (int)(v5 + 0x80000000) >= 0 && v5 != -1073741554 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_37;
      }
      v7 = 22;
      goto LABEL_17;
    }
    SrvNetGetSMBDirectDeviceName(SourceString);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids, SourceString);
    }
    InputBuffer = 0;
    memset(&ObjectAttributes, 0, 44);
    IoStatusBlock = 0;
    DestinationString = 0;
    if ( _InterlockedCompareExchange(&SmbdInitingOrDeiniting, 1, 0) )
    {
      v5 = -1073741436;
LABEL_31:
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_37;
      }
      v7 = 24;
LABEL_17:
      v8 = (unsigned int)v5;
      goto LABEL_6;
    }
    if ( SmbdHandle )
    {
      v5 = 0;
      goto LABEL_30;
    }
    InputBuffer = 0xA00000001LL;
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v5 = ZwOpenFile(&SmbdHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x60u);
    if ( v5 >= 0 )
    {
      v5 = ZwDeviceIoControlFile(
             SmbdHandle,
             0,
             0,
             0,
             &IoStatusBlock,
             0x508008u,
             &InputBuffer,
             8u,
             &SmbdFastDispatch,
             8u);
      if ( v5 >= 0 )
        goto LABEL_30;
      ZwClose(SmbdHandle);
      SmbdFastDispatch = 0;
    }
    SmbdHandle = 0;
LABEL_30:
    _InterlockedExchange(&SmbdInitingOrDeiniting, 0);
    if ( v5 >= 0 )
    {
      v10 = SrvNetLastLoadedSmbDirectServicePath;
      v11 = v27;
      do
      {
        v12 = v11[1];
        *(_OWORD *)v10 = *v11;
        v13 = v11[2];
        *((_OWORD *)v10 + 1) = v12;
        v14 = v11[3];
        *((_OWORD *)v10 + 2) = v13;
        v15 = v11[4];
        *((_OWORD *)v10 + 3) = v14;
        v16 = v11[5];
        *((_OWORD *)v10 + 4) = v15;
        v17 = v11[6];
        *((_OWORD *)v10 + 5) = v16;
        v18 = v11[7];
        v11 += 8;
        *((_OWORD *)v10 + 6) = v17;
        *((_OWORD *)v10 + 7) = v18;
        v10 += 16;
        --v9;
      }
      while ( v9 );
      goto LABEL_37;
    }
    goto LABEL_31;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v7 = 20;
    v8 = (unsigned int)SMBDirectServicePath;
LABEL_6:
    WPP_SF_d(v6->AttachedDevice, v7, WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids, v8);
  }
LABEL_37:
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
  {
    v19 = -1;
    do
      ++v19;
    while ( SourceString[v19] );
    McTemplateK0tdhzr2hzr4_EtwWriteTransfer(
      DriverServiceName.Length >> 1,
      (unsigned int)SourceString,
      v4,
      v5 >= 0,
      v5,
      DriverServiceName.Length >> 1,
      (__int64)DriverServiceName.Buffer,
      v19,
      (__int64)SourceString);
  }
  return v5 >= 0;
}

```

## disassembly

```asm
0x140046680  push    rbp
0x140046682  push    rbx
0x140046683  push    rsi
0x140046684  push    rdi
0x140046685  push    r12
0x140046687  push    r13
0x140046689  push    r15
0x14004668b  lea     rbp, [rsp-1D0h]
0x140046693  sub     rsp, 2D0h
0x14004669a  mov     rax, cs:__security_cookie
0x1400466a1  xor     rax, rsp
0x1400466a4  mov     [rbp+200h+var_40], rax
0x1400466ab  lea     rax, [rbp+200h+var_140]
0x1400466b2  mov     qword ptr [rsp+300h+DriverServiceName.Length], 1000000h
0x1400466bb  lea     rcx, [rsp+300h+DriverServiceName]; Destination
0x1400466c0  mov     [rsp+300h+DriverServiceName.Buffer], rax
0x1400466c5  xor     r12d, r12d
0x1400466c8  call    SrvNetGetSMBDirectServicePath
0x1400466cd  lea     r13d, [r12+1]
0x1400466d2  mov     ebx, eax
0x1400466d4  test    eax, eax
0x1400466d6  jns     short loc_140046721
0x1400466d8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400466df  lea     rsi, WPP_GLOBAL_Control
0x1400466e6  cmp     rcx, rsi
0x1400466e9  jz      loc_1400469BA
0x1400466ef  bt      dword ptr [rcx+2Ch], 13h
0x1400466f4  jnb     loc_1400469BA
0x1400466fa  cmp     [rcx+29h], r13b
0x1400466fe  jb      loc_1400469BA
0x140046704  lea     edx, [r12+14h]
0x140046709  mov     r9d, eax
0x14004670c  mov     rcx, [rcx+18h]
0x140046710  lea     r8, WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids
0x140046717  call    WPP_SF_d
0x14004671c  jmp     loc_1400469BA
0x140046721  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140046728  lea     rsi, WPP_GLOBAL_Control
0x14004672f  mov     r15d, 2
0x140046735  cmp     rcx, rsi
0x140046738  jz      short loc_140046760
0x14004673a  bt      dword ptr [rcx+2Ch], 13h
0x14004673f  jnb     short loc_140046760
0x140046741  cmp     [rcx+29h], r15b
0x140046745  jb      short loc_140046760
0x140046747  mov     rcx, [rcx+18h]
0x14004674b  lea     edx, [r15+13h]
0x14004674f  lea     r9, [rsp+300h+DriverServiceName]
0x140046754  lea     r8, WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids
0x14004675b  call    WPP_SF_Z
0x140046760  lea     rcx, [rsp+300h+DriverServiceName]; DriverServiceName
0x140046765  call    cs:__imp_ZwLoadDriver
0x14004676c  nop     dword ptr [rax+rax+00h]
0x140046771  mov     ecx, 80000000h
0x140046776  mov     ebx, eax
0x140046778  add     eax, ecx
0x14004677a  test    ecx, eax
0x14004677c  jnz     short loc_1400467B8
0x14004677e  cmp     ebx, 0C000010Eh
0x140046784  jz      short loc_1400467B8
0x140046786  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004678d  cmp     rcx, rsi
0x140046790  jz      loc_1400469BA
0x140046796  bt      dword ptr [rcx+2Ch], 13h
0x14004679b  jnb     loc_1400469BA
0x1400467a1  cmp     [rcx+29h], r13b
0x1400467a5  jb      loc_1400469BA
0x1400467ab  mov     edx, 16h
0x1400467b0  mov     r9d, ebx
0x1400467b3  jmp     loc_14004670C
0x1400467b8  lea     rcx, [rbp+200h+SourceString]; pszDest
0x1400467bc  call    SrvNetGetSMBDirectDeviceName
0x1400467c1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400467c8  cmp     rcx, rsi
0x1400467cb  jz      short loc_1400467F3
0x1400467cd  bt      dword ptr [rcx+2Ch], 13h
0x1400467d2  jnb     short loc_1400467F3
0x1400467d4  cmp     [rcx+29h], r15b
0x1400467d8  jb      short loc_1400467F3
0x1400467da  mov     rcx, [rcx+18h]
0x1400467de  lea     r9, [rbp+200h+SourceString]
0x1400467e2  mov     edx, 17h
0x1400467e7  lea     r8, WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids
0x1400467ee  call    WPP_SF_S
0x1400467f3  xorps   xmm0, xmm0
0x1400467f6  mov     [rsp+300h+var_2A0], r12
0x1400467fb  xorps   xmm1, xmm1
0x1400467fe  xor     eax, eax
0x140046800  movups  xmmword ptr [rsp+300h+ObjectAttributes.ObjectName], xmm0
0x140046805  movups  xmmword ptr [rbp+200h+ObjectAttributes+1Ch], xmm0
0x140046809  movups  xmmword ptr [rsp+300h+ObjectAttributes.Length], xmm0
0x14004680e  movups  xmmword ptr [rbp+200h+IoStatusBlock], xmm0
0x140046812  movups  xmmword ptr [rbp+200h+DestinationString.Length], xmm1
0x140046816  lock cmpxchg cs:SmbdInitingOrDeiniting, r13d
0x14004681f  jz      short loc_14004682B
0x140046821  mov     ebx, 0C0000184h
0x140046826  jmp     loc_14004693B
0x14004682b  cmp     cs:SmbdHandle, r12
0x140046832  jz      short loc_14004683C
0x140046834  mov     ebx, r12d
0x140046837  jmp     loc_14004692E
0x14004683c  mov     rax, cs:qword_1400307B8
0x140046843  lea     rdx, [rbp+200h+SourceString]; SourceString
0x140046847  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x14004684b  mov     [rsp+300h+var_2A0], rax
0x140046850  call    cs:__imp_RtlInitUnicodeString
0x140046857  nop     dword ptr [rax+rax+00h]
0x14004685c  lea     rax, [rbp+200h+DestinationString]
0x140046860  mov     [rsp+300h+OpenOptions], 60h ; '`'; OpenOptions
0x140046868  xorps   xmm0, xmm0
0x14004686b  mov     [rsp+300h+ObjectAttributes.ObjectName], rax
0x140046870  lea     r9, [rbp+200h+IoStatusBlock]; IoStatusBlock
0x140046874  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x14004687c  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x140046881  mov     [rsp+300h+ObjectAttributes.RootDirectory], r12
0x140046886  mov     edx, 0C0100000h; DesiredAccess
0x14004688b  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x140046892  lea     rcx, SmbdHandle; FileHandle
0x140046899  mov     [rsp+300h+ShareAccess], 3; ShareAccess
0x1400468a1  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400468a6  call    cs:__imp_ZwOpenFile
0x1400468ad  nop     dword ptr [rax+rax+00h]
0x1400468b2  mov     ebx, eax
0x1400468b4  test    eax, eax
0x1400468b6  js      short loc_140046927
0x1400468b8  mov     ecx, 8
0x1400468bd  lea     rax, SmbdFastDispatch
0x1400468c4  mov     [rsp+300h+OutputBufferLength], ecx; OutputBufferLength
0x1400468c8  xor     r9d, r9d; ApcContext
0x1400468cb  mov     [rsp+300h+OutputBuffer], rax; OutputBuffer
0x1400468d0  xor     r8d, r8d; ApcRoutine
0x1400468d3  mov     [rsp+300h+InputBufferLength], ecx; InputBufferLength
0x1400468d7  lea     rax, [rsp+300h+var_2A0]
0x1400468dc  mov     rcx, cs:SmbdHandle; FileHandle
0x1400468e3  xor     edx, edx; Event
0x1400468e5  mov     [rsp+300h+InputBuffer], rax; InputBuffer
0x1400468ea  lea     rax, [rbp+200h+IoStatusBlock]
0x1400468ee  mov     [rsp+300h+OpenOptions], 508008h; IoControlCode
0x1400468f6  mov     qword ptr [rsp+300h+ShareAccess], rax; IoStatusBlock
0x1400468fb  call    cs:__imp_ZwDeviceIoControlFile
0x140046902  nop     dword ptr [rax+rax+00h]
0x140046907  mov     ebx, eax
0x140046909  test    eax, eax
0x14004690b  jns     short loc_14004692E
0x14004690d  mov     rcx, cs:SmbdHandle; Handle
0x140046914  call    cs:__imp_ZwClose
0x14004691b  nop     dword ptr [rax+rax+00h]
0x140046920  mov     cs:SmbdFastDispatch, r12
0x140046927  mov     cs:SmbdHandle, r12
0x14004692e  mov     eax, r12d
0x140046931  xchg    eax, cs:SmbdInitingOrDeiniting
0x140046937  test    ebx, ebx
0x140046939  jns     short loc_14004695E
0x14004693b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140046942  cmp     rcx, rsi
0x140046945  jz      short loc_1400469BA
0x140046947  bt      dword ptr [rcx+2Ch], 13h
0x14004694c  jnb     short loc_1400469BA
0x14004694e  cmp     [rcx+29h], r13b
0x140046952  jb      short loc_1400469BA
0x140046954  mov     edx, 18h
0x140046959  jmp     loc_1400467B0
0x14004695e  lea     rax, SrvNetLastLoadedSmbDirectServicePath
0x140046965  mov     edx, 80h
0x14004696a  lea     rcx, [rbp+200h+var_140]
0x140046971  movups  xmm0, xmmword ptr [rcx]
0x140046974  movups  xmm1, xmmword ptr [rcx+10h]
0x140046978  movups  xmmword ptr [rax], xmm0
0x14004697b  movups  xmm0, xmmword ptr [rcx+20h]
0x14004697f  movups  xmmword ptr [rax+10h], xmm1
0x140046983  movups  xmm1, xmmword ptr [rcx+30h]
0x140046987  movups  xmmword ptr [rax+20h], xmm0
0x14004698b  movups  xmm0, xmmword ptr [rcx+40h]
0x14004698f  movups  xmmword ptr [rax+30h], xmm1
0x140046993  movups  xmm1, xmmword ptr [rcx+50h]
0x140046997  movups  xmmword ptr [rax+40h], xmm0
0x14004699b  movups  xmm0, xmmword ptr [rcx+60h]
0x14004699f  movups  xmmword ptr [rax+50h], xmm1
0x1400469a3  movups  xmm1, xmmword ptr [rcx+70h]
0x1400469a7  add     rcx, rdx
0x1400469aa  movups  xmmword ptr [rax+60h], xmm0
0x1400469ae  movups  xmmword ptr [rax+70h], xmm1
0x1400469b2  add     rax, rdx
0x1400469b5  sub     r15, r13
0x1400469b8  jnz     short loc_140046971
0x1400469ba  mov     edi, ebx
0x1400469bc  shr     edi, 1Fh
0x1400469bf  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 10h
0x1400469c6  jz      short loc_140046A0E
0x1400469c8  mov     r9d, edi
0x1400469cb  lea     rcx, [rbp+200h+SourceString]
0x1400469cf  xor     r9d, r13d
0x1400469d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400469d6  inc     rax
0x1400469d9  cmp     [rcx+rax*2], r12w
0x1400469de  jnz     short loc_1400469D6
0x1400469e0  movzx   ecx, [rsp+300h+DriverServiceName.Length]
0x1400469e5  lea     rdx, [rbp+200h+SourceString]
0x1400469e9  mov     [rsp+300h+OutputBuffer], rdx
0x1400469ee  mov     word ptr [rsp+300h+InputBufferLength], ax
0x1400469f3  mov     rax, [rsp+300h+DriverServiceName.Buffer]
0x1400469f8  mov     [rsp+300h+InputBuffer], rax
0x1400469fd  shr     cx, 1
0x140046a00  mov     word ptr [rsp+300h+OpenOptions], cx
0x140046a05  mov     [rsp+300h+ShareAccess], ebx
0x140046a09  call    McTemplateK0tdhzr2hzr4_EtwWriteTransfer
0x140046a0e  xor     edi, r13d
0x140046a11  mov     eax, edi
0x140046a13  mov     rcx, [rbp+200h+var_40]
0x140046a1a  xor     rcx, rsp; StackCookie
0x140046a1d  call    __security_check_cookie
0x140046a22  add     rsp, 2D0h
0x140046a29  pop     r15
0x140046a2b  pop     r13
0x140046a2d  pop     r12
0x140046a2f  pop     rdi
0x140046a30  pop     rsi
0x140046a31  pop     rbx
0x140046a32  pop     rbp
0x140046a33  retn
```
