# CFsrmFileStream::CopyFileInternal(ushort const *,ushort const *,bool)

- ea: `0x18005ba58`
- end: `0x18005c13b`
- name: `?CopyFileInternal@CFsrmFileStream@@CA_NPEBG0_N@Z`
- size: `1763`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005e040`

## callees

- `0x180001350`
- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000cde0`
- `0x18005ba58`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x18007ca74`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18005bc28`
- `ntdll!RtlInitUnicodeString` at `0x18005bc28`
- `ntdll!RtlNtStatusToDosError` at `0x18005bf8e`
- `ntdll!RtlNtStatusToDosError` at `0x18005bf8e`
- `ntdll!NtCreateFile` at `0x18005bcaa`
- `ntdll!NtCreateFile` at `0x18005bcaa`
- `KERNEL32!CloseHandle` at `0x18005bc63`
- `KERNEL32!CloseHandle` at `0x18005bd53`
- `KERNEL32!CloseHandle` at `0x18005bdb9`
- `KERNEL32!CloseHandle` at `0x18005be30`
- `KERNEL32!CloseHandle` at `0x18005bed5`
- `KERNEL32!CloseHandle` at `0x18005bc63`
- `KERNEL32!CloseHandle` at `0x18005bd53`
- `KERNEL32!CloseHandle` at `0x18005bdb9`
- `KERNEL32!CloseHandle` at `0x18005be30`
- `KERNEL32!CloseHandle` at `0x18005bed5`
- `KERNEL32!GetLastError` at `0x18005bd35`
- `KERNEL32!GetLastError` at `0x18005bd9b`
- `KERNEL32!GetLastError` at `0x18005bd35`
- `KERNEL32!GetLastError` at `0x18005bd9b`
- `KERNEL32!PrivCopyFileExW` at `0x18005bd91`
- `KERNEL32!PrivCopyFileExW` at `0x18005bd91`
- `KERNEL32!CreateEventW` at `0x18005bb7d`
- `KERNEL32!CreateEventW` at `0x18005bb7d`
- `KERNEL32!WaitForSingleObject` at `0x18005bdca`
- `KERNEL32!WaitForSingleObject` at `0x18005bdca`
- `KERNEL32!DeviceIoControl` at `0x18005bd27`
- `KERNEL32!DeviceIoControl` at `0x18005bd27`

## string_xrefs

- `0x18005ba9a`: `base\fs\fsrm\service\stream\streamlib.cpp`
- `0x18005baa5`: `CFsrmFileStream::CopyFileInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall CFsrmFileStream::CopyFileInternal(const unsigned __int16 *a1, const unsigned __int16 *a2, char a3)
{
  char v5; // di
  HANDLE EventW; // rsi
  __int64 v7; // rdx
  __int64 v8; // rcx
  ACCESS_MASK v9; // ebx
  ULONG ShareAccess; // r14d
  ULONG CreateOptions; // r15d
  const WCHAR *v12; // rdx
  int v13; // eax
  signed int LastError; // ebx
  HANDLE v15; // r9
  char v16; // r14
  int v18; // eax
  char v19; // al
  signed int v20; // eax
  int v21; // eax
  char v22; // al
  int v23; // eax
  char v24; // al
  int LastFailureAsHRESULT; // eax
  char Hr; // al
  int v27; // eax
  char v28; // al
  int v29; // eax
  char v30; // al
  int v31; // eax
  char v32; // al
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  void **v34; // [rsp+70h] [rbp-90h] BYREF
  HANDLE v35; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v36; // [rsp+80h] [rbp-80h]
  _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v39; // [rsp+C8h] [rbp-38h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-30h] BYREF
  _OVERLAPPED Overlapped; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v42[3]; // [rsp+100h] [rbp+0h] BYREF
  int v43; // [rsp+118h] [rbp+18h]
  int v44; // [rsp+11Ch] [rbp+1Ch]
  int v45; // [rsp+120h] [rbp+20h]
  _BYTE v46[96]; // [rsp+128h] [rbp+28h] BYREF
  int v47; // [rsp+188h] [rbp+88h]
  __int64 InBuffer; // [rsp+190h] [rbp+90h] BYREF
  int v49; // [rsp+198h] [rbp+98h]
  PCWSTR SourceString[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v51; // [rsp+1B0h] [rbp+B0h]
  unsigned __int64 v52; // [rsp+1B8h] [rbp+B8h]
  void **v53; // [rsp+1D0h] [rbp+D0h] BYREF
  int v54; // [rsp+1D8h] [rbp+D8h]
  __int128 OutBuffer; // [rsp+280h] [rbp+180h] BYREF
  __int64 v56; // [rsp+290h] [rbp+190h]

  v36 = a2;
  v39 = v42;
  v42[0] = L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp";
  v42[1] = L"CFsrmFileStream::CopyFileInternal";
  v42[2] = L"STREAMLC";
  v43 = 797;
  v44 = 17;
  v45 = 255;
  v47 = 0x1000000;
  v5 = 1;
  memset_0(v46, 0, sizeof(v46));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v53, (const struct CSrmDebugInfo *)v42, 0);
  InBuffer = 0;
  v49 = 0;
  OutBuffer = 0;
  v56 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  hObject = (HANDLE)-1LL;
  EventW = 0;
  v35 = 0;
  v34 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  if ( a3 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    v35 = EventW;
    if ( !EventW )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8, v7);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v53, LastFailureAsHRESULT);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v53);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v53, 0x33Cu, Hr, 0);
    }
    v9 = 1048705;
    ShareAccess = 1;
    CreateOptions = 81920;
    v54 = 0;
    Overlapped.hEvent = EventW;
  }
  else
  {
    v9 = 1114241;
    CreateOptions = 0x4000;
    ShareAccess = 7;
  }
  v52 = 7;
  v51 = 0;
  LOWORD(SourceString[0]) = 0;
  SrmDosPathNameToRelativeNtPathName(a1, SourceString);
  DestinationString = 0;
  v12 = (const WCHAR *)SourceString;
  if ( v52 >= 8 )
    v12 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v12);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  hObject = (HANDLE)-1LL;
  v13 = NtCreateFile(&hObject, v9, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, ShareAccess, 1u, CreateOptions, 0, 0);
  if ( v13 < 0 )
  {
    if ( v13 == -1073741598 || v13 == -1073739511 )
    {
      v54 = -2147200134;
      v27 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v53);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v53, v27);
      v28 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v53);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v53, 0x365u, v28, 0);
    }
    v20 = RtlNtStatusToDosError(v13);
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x80070000;
    v54 = v20;
    v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v53);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v53, v21);
    v22 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v53);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v53, 0x36Bu, v22, 0);
  }
  if ( a3 )
  {
    InBuffer = 0x3000C0001LL;
    v49 = 1;
    if ( DeviceIoControl(hObject, 0x90240u, &InBuffer, 0xCu, &OutBuffer, 0x18u, 0, &Overlapped) )
    {
      v54 = -2147200234;
      v29 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v53);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v53, v29);
      v30 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v53);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v53, 0x386u, v30, 0);
    }
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      v54 = -2147200134;
      v31 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v53);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v53, v31);
      v32 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v53);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v53, 0x38Eu, v32, 0);
    }
    v15 = EventW;
  }
  else
  {
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
    v15 = 0;
    LastError = 0;
  }
  v16 = 1;
  if ( !(unsigned int)PrivCopyFileExW(
                        a1,
                        v36,
                        (unsigned __int64)CFsrmFileStream::CopyProgressRoutine & -(__int64)(a3 != 0),
                        v15,
                        0,
                        369) )
  {
    LastError = GetLastError();
    v16 = 0;
  }
  if ( a3 )
  {
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
    WaitForSingleObject(EventW, 0xFFFFFFFF);
  }
  if ( v16 )
  {
    if ( v52 >= 8 )
      operator delete((void *)SourceString[0]);
    v52 = 7;
    v51 = 0;
    LOWORD(SourceString[0]) = 0;
    CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(&v34);
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
    v53 = &CSrmFunctionTracer::`vftable';
    goto LABEL_40;
  }
  if ( LastError == 32 )
  {
LABEL_47:
    v54 = -2147200134;
    v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v53);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v53, v23);
    v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v53);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v53, 0x3C1u, v24, 0);
  }
  if ( LastError != 80 && LastError != 183 )
  {
    if ( LastError != 1235 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v54 = LastError;
      v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v53);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v53, v18);
      v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v53);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v53, 0x3C5u, v19, 0);
    }
    goto LABEL_47;
  }
  if ( v52 >= 8 )
    operator delete((void *)SourceString[0]);
  v52 = 7;
  v51 = 0;
  LOWORD(SourceString[0]) = 0;
  CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(&v34);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  hObject = (HANDLE)-1LL;
  v53 = &CSrmFunctionTracer::`vftable';
  v5 = 0;
LABEL_40:
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v53);
  return v5;
}

```

## disassembly

```asm
0x18005ba58  mov     [rsp-8+arg_10], rbx
0x18005ba5d  push    rbp
0x18005ba5e  push    rsi
0x18005ba5f  push    rdi
0x18005ba60  push    r12
0x18005ba62  push    r13
0x18005ba64  push    r14
0x18005ba66  push    r15
0x18005ba68  lea     rbp, [rsp-1A0h]
0x18005ba70  sub     rsp, 2A0h
0x18005ba77  mov     rax, cs:__security_cookie
0x18005ba7e  xor     rax, rsp
0x18005ba81  mov     [rbp+1D0h+var_38], rax
0x18005ba88  mov     r12b, r8b
0x18005ba8b  mov     [rbp+1D0h+var_250], rdx
0x18005ba8f  mov     r13, rcx
0x18005ba92  lea     rax, [rbp+1D0h+var_1D0]
0x18005ba96  mov     [rbp+1D0h+var_208], rax
0x18005ba9a  lea     rax, aBaseFsFsrmServ_12; "base\\fs\\fsrm\\service\\stream\\stream"...
0x18005baa1  mov     [rbp+1D0h+var_1D0], rax
0x18005baa5  lea     rax, aCfsrmfilestrea_1; "CFsrmFileStream::CopyFileInternal"
0x18005baac  mov     [rbp+1D0h+var_1C8], rax
0x18005bab0  lea     rax, aStreamlc; "STREAMLC"
0x18005bab7  mov     [rbp+1D0h+var_1C0], rax
0x18005babb  mov     [rbp+1D0h+var_1B8], 31Dh
0x18005bac2  mov     [rbp+1D0h+var_1B4], 11h
0x18005bac9  mov     [rbp+1D0h+var_1B0], 0FFh
0x18005bad0  mov     [rbp+1D0h+var_148], 1000000h
0x18005bada  mov     edi, 1
0x18005badf  xor     edx, edx; Val
0x18005bae1  lea     r8d, [rdi+5Fh]; Size
0x18005bae5  lea     rcx, [rbp+1D0h+var_1A8]; void *
0x18005bae9  call    memset_0
0x18005baee  nop
0x18005baef  xor     r8d, r8d
0x18005baf2  lea     rdx, [rbp+1D0h+var_1D0]
0x18005baf6  lea     rcx, [rbp+1D0h+var_100]
0x18005bafd  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005bb02  nop
0x18005bb03  xor     eax, eax
0x18005bb05  mov     [rbp+1D0h+InBuffer], rax
0x18005bb0c  mov     [rbp+1D0h+var_138], eax
0x18005bb12  xorps   xmm0, xmm0
0x18005bb15  movups  [rbp+1D0h+OutBuffer], xmm0
0x18005bb1c  mov     [rbp+1D0h+var_40], rax
0x18005bb23  xorps   xmm1, xmm1
0x18005bb26  movups  xmmword ptr [rbp+1D0h+Overlapped.Internal], xmm1
0x18005bb2a  movups  xmmword ptr [rbp+1D0h+Overlapped.10h], xmm1
0x18005bb2e  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18005bb35  mov     [rsp+2D0h+var_270], rax
0x18005bb3a  mov     [rsp+2D0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18005bb43  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005bb4a  mov     [rsp+2D0h+var_270], rax
0x18005bb4f  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18005bb56  mov     [rsp+2D0h+var_260], rax
0x18005bb5b  xor     esi, esi
0x18005bb5d  mov     [rsp+2D0h+var_258], rsi
0x18005bb62  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005bb69  mov     [rsp+2D0h+var_260], rax
0x18005bb6e  test    r12b, r12b
0x18005bb71  jz      short loc_18005BBC7
0x18005bb73  xor     r9d, r9d; lpName
0x18005bb76  xor     r8d, r8d; bInitialState
0x18005bb79  mov     edx, edi; bManualReset
0x18005bb7b  xor     ecx, ecx; lpEventAttributes
0x18005bb7d  call    cs:__imp_CreateEventW
0x18005bb83  mov     rsi, rax
0x18005bb86  mov     [rsp+2D0h+var_258], 0
0x18005bb8f  mov     [rsp+2D0h+var_258], rax
0x18005bb94  mov     eax, [rbp+1D0h+var_F8]
0x18005bb9a  mov     [rbp+1D0h+var_F8], eax
0x18005bba0  test    rsi, rsi
0x18005bba3  jz      loc_18005C02C
0x18005bba9  mov     ebx, 100081h
0x18005bbae  mov     r14d, edi
0x18005bbb1  mov     r15d, 14000h
0x18005bbb7  mov     [rbp+1D0h+var_F8], 0
0x18005bbc1  mov     [rbp+1D0h+Overlapped.hEvent], rsi
0x18005bbc5  jmp     short loc_18005BBD8
0x18005bbc7  mov     ebx, 110081h
0x18005bbcc  mov     r15d, 4000h
0x18005bbd2  mov     r14d, 7
0x18005bbd8  mov     [rbp+1D0h+var_118], 7
0x18005bbe3  mov     [rbp+1D0h+var_120], 0
0x18005bbee  xor     eax, eax
0x18005bbf0  mov     word ptr [rbp+1D0h+SourceString], ax
0x18005bbf7  lea     rdx, [rbp+1D0h+SourceString]; void *
0x18005bbfe  mov     rcx, r13; DosName
0x18005bc01  call    ?SrmDosPathNameToRelativeNtPathName@@YAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SrmDosPathNameToRelativeNtPathName(ushort const *,std::wstring &)
0x18005bc06  xorps   xmm0, xmm0
0x18005bc09  movups  xmmword ptr [rbp+1D0h+DestinationString.Length], xmm0
0x18005bc0d  lea     rdx, [rbp+1D0h+SourceString]
0x18005bc14  cmp     [rbp+1D0h+var_118], 8
0x18005bc1c  cmovnb  rdx, [rbp+1D0h+SourceString]; SourceString
0x18005bc24  lea     rcx, [rbp+1D0h+DestinationString]; DestinationString
0x18005bc28  call    cs:__imp_RtlInitUnicodeString
0x18005bc2e  xor     edx, edx
0x18005bc30  mov     qword ptr [rbp+1D0h+ObjectAttributes.Length], 30h ; '0'
0x18005bc38  mov     qword ptr [rbp+1D0h+ObjectAttributes.Attributes], 40h ; '@'
0x18005bc40  mov     [rbp+1D0h+ObjectAttributes.RootDirectory], rdx
0x18005bc44  lea     rax, [rbp+1D0h+DestinationString]
0x18005bc48  mov     [rbp+1D0h+ObjectAttributes.ObjectName], rax
0x18005bc4c  xorps   xmm0, xmm0
0x18005bc4f  movdqu  xmmword ptr [rbp+1D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005bc54  movups  xmmword ptr [rbp+1D0h+IoStatusBlock], xmm0
0x18005bc58  mov     rcx, [rsp+2D0h+hObject]; hObject
0x18005bc5d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005bc61  jz      short loc_18005BC6B
0x18005bc63  call    cs:__imp_CloseHandle
0x18005bc69  xor     edx, edx
0x18005bc6b  mov     [rsp+2D0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18005bc74  mov     [rsp+2D0h+EaLength], edx; EaLength
0x18005bc78  mov     [rsp+2D0h+EaBuffer], rdx; EaBuffer
0x18005bc7d  mov     [rsp+2D0h+CreateOptions], r15d; CreateOptions
0x18005bc82  mov     [rsp+2D0h+CreateDisposition], edi; CreateDisposition
0x18005bc86  mov     [rsp+2D0h+ShareAccess], r14d; ShareAccess
0x18005bc8b  mov     [rsp+2D0h+FileAttributes], 80h; FileAttributes
0x18005bc93  xor     r15d, r15d
0x18005bc96  mov     [rsp+2D0h+AllocationSize], r15; AllocationSize
0x18005bc9b  lea     r9, [rbp+1D0h+IoStatusBlock]; IoStatusBlock
0x18005bc9f  lea     r8, [rbp+1D0h+ObjectAttributes]; ObjectAttributes
0x18005bca3  mov     edx, ebx; DesiredAccess
0x18005bca5  lea     rcx, [rsp+2D0h+hObject]; FileHandle
0x18005bcaa  call    cs:__imp_NtCreateFile
0x18005bcb0  test    eax, eax
0x18005bcb2  jns     short loc_18005BCCF
0x18005bcb4  cmp     eax, 0C00000E2h
0x18005bcb9  jz      loc_18005C063
0x18005bcbf  cmp     eax, 0C0000909h
0x18005bcc4  jnz     loc_18005BF8C
0x18005bcca  jmp     loc_18005C063
0x18005bccf  mov     rcx, [rsp+2D0h+hObject]; hObject
0x18005bcd4  test    r12b, r12b
0x18005bcd7  jz      short loc_18005BD4D
0x18005bcd9  mov     dword ptr [rbp+1D0h+InBuffer], 0C0001h
0x18005bce3  mov     r9d, 0Ch; nInBufferSize
0x18005bce9  mov     dword ptr [rbp+1D0h+InBuffer+4], 3
0x18005bcf3  mov     [rbp+1D0h+var_138], edi
0x18005bcf9  lea     rax, [rbp+1D0h+Overlapped]
0x18005bcfd  mov     qword ptr [rsp+2D0h+CreateDisposition], rax; lpOverlapped
0x18005bd02  mov     qword ptr [rsp+2D0h+ShareAccess], r15; lpBytesReturned
0x18005bd07  mov     [rsp+2D0h+FileAttributes], 18h; nOutBufferSize
0x18005bd0f  lea     rax, [rbp+1D0h+OutBuffer]
0x18005bd16  mov     [rsp+2D0h+AllocationSize], rax; lpOutBuffer
0x18005bd1b  lea     r8, [rbp+1D0h+InBuffer]; lpInBuffer
0x18005bd22  mov     edx, 90240h; dwIoControlCode
0x18005bd27  call    cs:__imp_DeviceIoControl
0x18005bd2d  test    eax, eax
0x18005bd2f  jnz     loc_18005C0AB
0x18005bd35  call    cs:__imp_GetLastError
0x18005bd3b  mov     ebx, eax
0x18005bd3d  cmp     eax, 3E5h
0x18005bd42  jnz     loc_18005C0F3
0x18005bd48  mov     r9, rsi
0x18005bd4b  jmp     short loc_18005BD68
0x18005bd4d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005bd51  jz      short loc_18005BD59
0x18005bd53  call    cs:__imp_CloseHandle
0x18005bd59  mov     [rsp+2D0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18005bd62  mov     r9, r15
0x18005bd65  mov     ebx, r15d
0x18005bd68  mov     r14b, dil
0x18005bd6b  mov     al, r12b
0x18005bd6e  lea     rcx, ?CopyProgressRoutine@CFsrmFileStream@@CAKT_LARGE_INTEGER@@000KKPEAX11@Z; CFsrmFileStream::CopyProgressRoutine(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)
0x18005bd75  neg     al
0x18005bd77  sbb     r8, r8
0x18005bd7a  and     r8, rcx
0x18005bd7d  mov     [rsp+2D0h+FileAttributes], 171h
0x18005bd85  mov     [rsp+2D0h+AllocationSize], r15
0x18005bd8a  mov     rdx, [rbp+1D0h+var_250]
0x18005bd8e  mov     rcx, r13
0x18005bd91  call    cs:__imp_PrivCopyFileExW
0x18005bd97  test    eax, eax
0x18005bd99  jnz     short loc_18005BDA6
0x18005bd9b  call    cs:__imp_GetLastError
0x18005bda1  mov     ebx, eax
0x18005bda3  mov     r14b, r15b
0x18005bda6  test    r12b, r12b
0x18005bda9  jz      short loc_18005BDD2
0x18005bdab  mov     rcx, [rsp+2D0h+hObject]; hObject
0x18005bdb0  or      r12, 0FFFFFFFFFFFFFFFFh
0x18005bdb4  cmp     rcx, r12
0x18005bdb7  jz      short loc_18005BDBF
0x18005bdb9  call    cs:__imp_CloseHandle
0x18005bdbf  mov     [rsp+2D0h+hObject], r12
0x18005bdc4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005bdc7  mov     rcx, rsi; hHandle
0x18005bdca  call    cs:__imp_WaitForSingleObject
0x18005bdd0  jmp     short loc_18005BDD6
0x18005bdd2  or      r12, 0FFFFFFFFFFFFFFFFh
0x18005bdd6  test    r14b, r14b
0x18005bdd9  jz      loc_18005BE5F
0x18005bddf  cmp     [rbp+1D0h+var_118], 8
0x18005bde7  jb      short loc_18005BDF5
0x18005bde9  mov     rcx, [rbp+1D0h+SourceString]; Block
0x18005bdf0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005bdf5  mov     [rbp+1D0h+var_118], 7
0x18005be00  mov     [rbp+1D0h+var_120], r15
0x18005be07  mov     word ptr [rbp+1D0h+SourceString], r15w
0x18005be0f  lea     rcx, [rsp+2D0h+var_260]
0x18005be14  call    ??1?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@UEAA@XZ; CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::~CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>(void)
0x18005be19  nop
0x18005be1a  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005be21  mov     [rsp+2D0h+var_270], rax
0x18005be26  mov     rcx, [rsp+2D0h+hObject]; hObject
0x18005be2b  cmp     rcx, r12
0x18005be2e  jz      short loc_18005BE36
0x18005be30  call    cs:__imp_CloseHandle
0x18005be36  mov     [rsp+2D0h+hObject], r12
0x18005be3b  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18005be42  mov     [rsp+2D0h+var_270], rax
0x18005be47  mov     [rsp+2D0h+hObject], r12
0x18005be4c  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005be53  mov     [rbp+1D0h+var_100], rax
0x18005be5a  jmp     loc_18005BF02
0x18005be5f  mov     eax, ebx
0x18005be61  sub     eax, 20h ; ' '
0x18005be64  jz      loc_18005BFE4
0x18005be6a  sub     eax, 30h ; '0'
0x18005be6d  jz      short loc_18005BE84
0x18005be6f  sub     eax, 67h ; 'g'
0x18005be72  jz      short loc_18005BE84
0x18005be74  cmp     eax, 41Ch
0x18005be79  jz      loc_18005BFE4
0x18005be7f  jmp     loc_18005BF3B
0x18005be84  cmp     [rbp+1D0h+var_118], 8
0x18005be8c  jb      short loc_18005BE9A
0x18005be8e  mov     rcx, [rbp+1D0h+SourceString]; Block
0x18005be95  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005be9a  mov     [rbp+1D0h+var_118], 7
0x18005bea5  mov     [rbp+1D0h+var_120], r15
0x18005beac  mov     word ptr [rbp+1D0h+SourceString], r15w
0x18005beb4  lea     rcx, [rsp+2D0h+var_260]
0x18005beb9  call    ??1?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@UEAA@XZ; CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::~CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>(void)
0x18005bebe  nop
0x18005bebf  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005bec6  mov     [rsp+2D0h+var_270], rax
0x18005becb  mov     rcx, [rsp+2D0h+hObject]; hObject
0x18005bed0  cmp     rcx, r12
0x18005bed3  jz      short loc_18005BEDB
0x18005bed5  call    cs:__imp_CloseHandle
0x18005bedb  mov     [rsp+2D0h+hObject], r12
0x18005bee0  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18005bee7  mov     [rsp+2D0h+var_270], rax
0x18005beec  mov     [rsp+2D0h+hObject], r12
0x18005bef1  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005bef8  mov     [rbp+1D0h+var_100], rax
0x18005beff  mov     dil, r15b
0x18005bf02  lea     rcx, [rbp+1D0h+var_100]; this
0x18005bf09  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18005bf0e  mov     al, dil
0x18005bf11  mov     rcx, [rbp+1D0h+var_38]
0x18005bf18  xor     rcx, rsp; StackCookie
0x18005bf1b  call    __security_check_cookie
0x18005bf20  mov     rbx, [rsp+2D0h+arg_10]
0x18005bf28  add     rsp, 2A0h
0x18005bf2f  pop     r15
0x18005bf31  pop     r14
0x18005bf33  pop     r13
0x18005bf35  pop     r12
0x18005bf37  pop     rdi
0x18005bf38  pop     rsi
0x18005bf39  pop     rbp
0x18005bf3a  retn
0x18005bf3b  test    ebx, ebx
0x18005bf3d  jle     short loc_18005BF48
0x18005bf3f  movzx   ebx, bx
0x18005bf42  or      ebx, 80070000h
0x18005bf48  mov     [rbp+1D0h+var_F8], ebx
0x18005bf4e  lea     rcx, [rbp+1D0h+var_100]; this
0x18005bf55  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005bf5a  mov     edx, eax; int
0x18005bf5c  lea     rcx, [rbp+1D0h+var_100]; this
0x18005bf63  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005bf68  lea     rcx, [rbp+1D0h+var_100]; this
0x18005bf6f  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005bf74  mov     r8d, eax; char
0x18005bf77  xor     r9d, r9d; unsigned __int16 *
0x18005bf7a  mov     edx, 3C5h; unsigned int
0x18005bf7f  lea     rcx, [rbp+1D0h+var_100]; this
0x18005bf86  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005bf8c  mov     ecx, eax; Status
0x18005bf8e  call    cs:__imp_RtlNtStatusToDosError
0x18005bf94  test    eax, eax
0x18005bf96  jle     short loc_18005BFA0
0x18005bf98  movzx   eax, ax
0x18005bf9b  or      eax, 80070000h
0x18005bfa0  mov     [rbp+1D0h+var_F8], eax
0x18005bfa6  lea     rcx, [rbp+1D0h+var_100]; this
0x18005bfad  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005bfb2  mov     edx, eax; int
0x18005bfb4  lea     rcx, [rbp+1D0h+var_100]; this
0x18005bfbb  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005bfc0  lea     rcx, [rbp+1D0h+var_100]; this
0x18005bfc7  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005bfcc  mov     r8d, eax; char
0x18005bfcf  xor     r9d, r9d; unsigned __int16 *
0x18005bfd2  mov     edx, 36Bh; unsigned int
0x18005bfd7  lea     rcx, [rbp+1D0h+var_100]; this
0x18005bfde  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
  ... truncated ...
```
