# CFsrmFileStream::OpenStreamForRead(bool)

- ea: `0x18005e5a8`
- end: `0x18005ea53`
- name: `?OpenStreamForRead@CFsrmFileStream@@AEAAX_N@Z`
- size: `1195`
- prototype: `void __fastcall(CFsrmFileStream *__hidden this, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005e24c`

## callees

- `0x180001350`
- `0x180006a1c`
- `0x1800095f4`
- `0x18005daa8`
- `0x18005e5a8`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073f54`
- `0x18007ca74`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18005e693`
- `ntdll!RtlInitUnicodeString` at `0x18005e693`
- `ntdll!RtlNtStatusToDosError` at `0x18005e97f`
- `ntdll!RtlNtStatusToDosError` at `0x18005e97f`
- `ntdll!NtCreateFile` at `0x18005e729`
- `ntdll!NtCreateFile` at `0x18005e729`
- `KERNEL32!CloseHandle` at `0x18005e7d1`
- `KERNEL32!CloseHandle` at `0x18005e811`
- `KERNEL32!CloseHandle` at `0x18005e831`
- `KERNEL32!CloseHandle` at `0x18005e8d8`
- `KERNEL32!CloseHandle` at `0x18005e9f7`
- `KERNEL32!CloseHandle` at `0x18005e7d1`
- `KERNEL32!CloseHandle` at `0x18005e811`
- `KERNEL32!CloseHandle` at `0x18005e831`
- `KERNEL32!CloseHandle` at `0x18005e8d8`
- `KERNEL32!CloseHandle` at `0x18005e9f7`
- `KERNEL32!GetLastError` at `0x18005e7ab`
- `KERNEL32!GetLastError` at `0x18005e7ab`
- `KERNEL32!CloseThreadpoolWait` at `0x18005e8bf`
- `KERNEL32!CloseThreadpoolWait` at `0x18005e9de`
- `KERNEL32!CloseThreadpoolWait` at `0x18005e8bf`
- `KERNEL32!CloseThreadpoolWait` at `0x18005e9de`
- `KERNEL32!DeviceIoControl` at `0x18005e79d`
- `KERNEL32!DeviceIoControl` at `0x18005e79d`

## string_xrefs

- `0x18005e5e8`: `base\fs\fsrm\service\stream\streamlib.cpp`
- `0x18005e5f3`: `CFsrmFileStream::OpenStreamForRead`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CFsrmFileStream::OpenStreamForRead(struct _OVERLAPPED *this, unsigned __int8 a2)
{
  int v2; // esi
  const WCHAR *p_InternalHigh; // rcx
  const WCHAR *v5; // rdx
  int v6; // eax
  ULONG_PTR *v7; // rdi
  DWORD LastError; // esi
  void *v9; // rsi
  PVOID v10; // rcx
  void *v11; // rbx
  void *v12; // rcx
  struct _TP_WAIT *v13; // rcx
  PVOID v14; // rcx
  int v15; // eax
  char v16; // al
  int Hr; // eax
  char v18; // al
  struct _TP_WAIT *hEvent; // rcx
  PVOID Pointer; // rcx
  int v21; // eax
  char v22; // al
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-E0h]
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v27; // [rsp+B0h] [rbp-50h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v29[3]; // [rsp+C8h] [rbp-38h] BYREF
  int v30; // [rsp+E0h] [rbp-20h]
  int v31; // [rsp+E4h] [rbp-1Ch]
  int v32; // [rsp+E8h] [rbp-18h]
  _BYTE v33[96]; // [rsp+F0h] [rbp-10h] BYREF
  int v34; // [rsp+150h] [rbp+50h]
  PCWSTR SourceString[2]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v36; // [rsp+168h] [rbp+68h]
  unsigned __int64 v37; // [rsp+170h] [rbp+70h]
  void **v38; // [rsp+180h] [rbp+80h] BYREF
  int v39; // [rsp+188h] [rbp+88h]

  v2 = a2;
  v27 = v29;
  v29[0] = L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp";
  v29[1] = L"CFsrmFileStream::OpenStreamForRead";
  v29[2] = L"STREAMLC";
  v30 = 158;
  v31 = 26;
  v32 = 255;
  v34 = 0x1000000;
  memset_0(v33, 0, sizeof(v33));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v38, (const struct CSrmDebugInfo *)v29, 0);
  v37 = 7;
  v36 = 0;
  LOWORD(SourceString[0]) = 0;
  p_InternalHigh = (const WCHAR *)&this->InternalHigh;
  if ( this[1].Internal >= 8 )
    p_InternalHigh = *(const WCHAR **)p_InternalHigh;
  SrmDosPathNameToRelativeNtPathName(p_InternalHigh, SourceString);
  DestinationString = 0;
  v5 = (const WCHAR *)SourceString;
  if ( v37 >= 8 )
    v5 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v5);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  FileHandle = (void *)-1LL;
  v6 = NtCreateFile(
         &FileHandle,
         0x100081u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0x80u,
         1u,
         1u,
         (v2 << 16) + 16388,
         0,
         0);
  if ( v6 < 0 )
  {
    if ( v6 == -1073741757 || v6 == -1073741598 || (v39 = -2147200189, v6 == -1073739511) )
      v39 = -2147200134;
    LODWORD(this[2].hEvent) = RtlNtStatusToDosError(v6);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, Hr);
    v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0xDDu, v18, 0);
  }
  v7 = &this[3].InternalHigh;
  if ( (_BYTE)v2 )
  {
    CFsrmFileStream::CSrmOplockHandle::Initialize(&this[3].InternalHigh);
    LOWORD(this[6].Internal) = 1;
    WORD1(this[6].Internal) = 12;
    HIDWORD(this[6].Internal) = 3;
    LODWORD(this[6].InternalHigh) = 1;
    if ( DeviceIoControl(FileHandle, 0x90240u, &this[6], 0xCu, (char *)&this[6].InternalHigh + 4, 0x18u, 0, this + 5) )
    {
      hEvent = (struct _TP_WAIT *)this[4].hEvent;
      if ( hEvent )
      {
        CloseThreadpoolWait(hEvent);
        this[4].hEvent = 0;
      }
      Pointer = this[4].Pointer;
      if ( Pointer )
        CloseHandle(Pointer);
      this[4].Pointer = 0;
      this[5].hEvent = 0;
      v39 = -2147200234;
      v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, v21);
      v22 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0xF8u, v22, 0);
    }
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      v13 = (struct _TP_WAIT *)this[4].hEvent;
      if ( v13 )
      {
        CloseThreadpoolWait(v13);
        this[4].hEvent = 0;
      }
      v14 = this[4].Pointer;
      if ( v14 )
        CloseHandle(v14);
      this[4].Pointer = 0;
      this[5].hEvent = 0;
      LODWORD(AllocationSize) = LastError;
      CSrmFunctionTracer::Trace(
        (CSrmFunctionTracer *)&v38,
        0x8Cu,
        0x101u,
        L"Failed to acquire oplock with error %ld, assuming file in use",
        AllocationSize);
      v39 = -2147200134;
      v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, v15);
      v16 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0x102u, v16, 0);
    }
    v9 = FileHandle;
    FileHandle = (void *)-1LL;
    v10 = this[3].Pointer;
    if ( v10 != (PVOID)-1LL )
      CloseHandle(v10);
    this[3].Pointer = v9;
    CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v38, 0x8Cu, 0x10Bu, L"Oplock %p acquired", &this[3].InternalHigh);
  }
  else
  {
    v11 = FileHandle;
    FileHandle = (void *)-1LL;
    v12 = (void *)v7[1];
    if ( v12 != (void *)-1LL )
      CloseHandle(v12);
    v7[1] = (ULONG_PTR)v11;
  }
  if ( FileHandle != (void *)-1LL )
    CloseHandle(FileHandle);
  FileHandle = (void *)-1LL;
  if ( v37 >= 8 )
    operator delete((void *)SourceString[0]);
  v37 = 7;
  v36 = 0;
  LOWORD(SourceString[0]) = 0;
  v38 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v38);
}

```

## disassembly

```asm
0x18005e5a8  mov     [rsp-8+arg_8], rbx
0x18005e5ad  mov     [rsp-8+arg_10], rsi
0x18005e5b2  push    rbp
0x18005e5b3  push    rdi
0x18005e5b4  push    r12
0x18005e5b6  push    r14
0x18005e5b8  push    r15
0x18005e5ba  lea     rbp, [rsp-140h]
0x18005e5c2  sub     rsp, 240h
0x18005e5c9  mov     rax, cs:__security_cookie
0x18005e5d0  xor     rax, rsp
0x18005e5d3  mov     [rbp+160h+var_30], rax
0x18005e5da  movzx   esi, dl
0x18005e5dd  mov     rbx, rcx
0x18005e5e0  lea     rax, [rbp+160h+var_198]
0x18005e5e4  mov     [rbp+160h+var_1B0], rax
0x18005e5e8  lea     rax, aBaseFsFsrmServ_12; "base\\fs\\fsrm\\service\\stream\\stream"...
0x18005e5ef  mov     [rbp+160h+var_198], rax
0x18005e5f3  lea     rax, aCfsrmfilestrea_6; "CFsrmFileStream::OpenStreamForRead"
0x18005e5fa  mov     [rbp+160h+var_190], rax
0x18005e5fe  lea     rax, aStreamlc; "STREAMLC"
0x18005e605  mov     [rbp+160h+var_188], rax
0x18005e609  mov     [rbp+160h+var_180], 9Eh
0x18005e610  mov     [rbp+160h+var_17C], 1Ah
0x18005e617  mov     [rbp+160h+var_178], 0FFh
0x18005e61e  xor     r14d, r14d
0x18005e621  mov     [rbp+160h+var_110], 1000000h
0x18005e628  xor     edx, edx; Val
0x18005e62a  lea     r12d, [r14+1]
0x18005e62e  lea     r8d, [r14+60h]; Size
0x18005e632  lea     rcx, [rbp+160h+var_170]; void *
0x18005e636  call    memset_0
0x18005e63b  nop
0x18005e63c  xor     r8d, r8d
0x18005e63f  lea     rdx, [rbp+160h+var_198]
0x18005e643  lea     rcx, [rbp+160h+var_E0]
0x18005e64a  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005e64f  nop
0x18005e650  mov     [rbp+160h+var_F0], 7
0x18005e658  mov     [rbp+160h+var_F8], r14
0x18005e65c  mov     word ptr [rbp+160h+SourceString], r14w
0x18005e661  lea     rcx, [rbx+8]
0x18005e665  cmp     qword ptr [rcx+18h], 8
0x18005e66a  jb      short loc_18005E66F
0x18005e66c  mov     rcx, [rcx]; DosName
0x18005e66f  lea     rdx, [rbp+160h+SourceString]; void *
0x18005e673  call    ?SrmDosPathNameToRelativeNtPathName@@YAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SrmDosPathNameToRelativeNtPathName(ushort const *,std::wstring &)
0x18005e678  xorps   xmm0, xmm0
0x18005e67b  movups  xmmword ptr [rsp+260h+DestinationString.Length], xmm0
0x18005e680  lea     rdx, [rbp+160h+SourceString]
0x18005e684  cmp     [rbp+160h+var_F0], 8
0x18005e689  cmovnb  rdx, [rbp+160h+SourceString]; SourceString
0x18005e68e  lea     rcx, [rsp+260h+DestinationString]; DestinationString
0x18005e693  call    cs:__imp_RtlInitUnicodeString
0x18005e699  mov     qword ptr [rbp+160h+ObjectAttributes.Length], 30h ; '0'
0x18005e6a1  mov     qword ptr [rbp+160h+ObjectAttributes.Attributes], 40h ; '@'
0x18005e6a9  mov     [rbp+160h+ObjectAttributes.RootDirectory], r14
0x18005e6ad  lea     rax, [rsp+260h+DestinationString]
0x18005e6b2  mov     [rbp+160h+ObjectAttributes.ObjectName], rax
0x18005e6b6  xorps   xmm0, xmm0
0x18005e6b9  movdqu  xmmword ptr [rbp+160h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005e6be  movups  xmmword ptr [rbp+160h+IoStatusBlock], xmm0
0x18005e6c2  mov     eax, esi
0x18005e6c4  shl     eax, 10h
0x18005e6c7  add     eax, 4004h
0x18005e6cc  lea     rcx, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18005e6d3  mov     [rsp+260h+var_200], rcx
0x18005e6d8  or      r15, 0FFFFFFFFFFFFFFFFh
0x18005e6dc  mov     [rsp+260h+FileHandle], r15
0x18005e6e1  lea     rcx, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005e6e8  mov     [rsp+260h+var_200], rcx
0x18005e6ed  mov     [rsp+260h+FileHandle], r15
0x18005e6f2  mov     [rsp+260h+EaLength], r14d; EaLength
0x18005e6f7  mov     [rsp+260h+EaBuffer], r14; EaBuffer
0x18005e6fc  mov     [rsp+260h+CreateOptions], eax; CreateOptions
0x18005e700  mov     [rsp+260h+CreateDisposition], r12d; CreateDisposition
0x18005e705  mov     [rsp+260h+ShareAccess], r12d; ShareAccess
0x18005e70a  mov     [rsp+260h+FileAttributes], 80h; FileAttributes
0x18005e712  mov     [rsp+260h+AllocationSize], r14; AllocationSize
0x18005e717  lea     r9, [rbp+160h+IoStatusBlock]; IoStatusBlock
0x18005e71b  lea     r8, [rbp+160h+ObjectAttributes]; ObjectAttributes
0x18005e71f  mov     edx, 100081h; DesiredAccess
0x18005e724  lea     rcx, [rsp+260h+FileHandle]; FileHandle
0x18005e729  call    cs:__imp_NtCreateFile
0x18005e72f  test    eax, eax
0x18005e731  js      loc_18005E954
0x18005e737  lea     rdi, [rbx+68h]
0x18005e73b  test    sil, sil
0x18005e73e  jz      loc_18005E7FE
0x18005e744  mov     rcx, rdi; pv
0x18005e747  call    ?Initialize@CSrmOplockHandle@CFsrmFileStream@@QEAAXXZ; CFsrmFileStream::CSrmOplockHandle::Initialize(void)
0x18005e74c  lea     r8, [rbx+0C0h]; lpInBuffer
0x18005e753  mov     [r8], r12w
0x18005e757  lea     r9d, [r15+0Dh]; nInBufferSize
0x18005e75b  mov     [rbx+0C2h], r9w
0x18005e763  mov     dword ptr [rbx+0C4h], 3
0x18005e76d  mov     [rbx+0C8h], r12d
0x18005e774  lea     rax, [rdi+38h]
0x18005e778  lea     rcx, [rdi+64h]
0x18005e77c  mov     qword ptr [rsp+260h+CreateDisposition], rax; lpOverlapped
0x18005e781  mov     qword ptr [rsp+260h+ShareAccess], r14; lpBytesReturned
0x18005e786  mov     [rsp+260h+FileAttributes], 18h; nOutBufferSize
0x18005e78e  mov     [rsp+260h+AllocationSize], rcx; lpOutBuffer
0x18005e793  mov     edx, 90240h; dwIoControlCode
0x18005e798  mov     rcx, [rsp+260h+FileHandle]; hDevice
0x18005e79d  call    cs:__imp_DeviceIoControl
0x18005e7a3  test    eax, eax
0x18005e7a5  jnz     loc_18005E9D2
0x18005e7ab  call    cs:__imp_GetLastError
0x18005e7b1  mov     esi, eax
0x18005e7b3  cmp     eax, 3E5h
0x18005e7b8  jnz     loc_18005E8B3
0x18005e7be  mov     rsi, [rsp+260h+FileHandle]
0x18005e7c3  mov     [rsp+260h+FileHandle], r15
0x18005e7c8  mov     rcx, [rbx+70h]; hObject
0x18005e7cc  cmp     rcx, r15
0x18005e7cf  jz      short loc_18005E7D7
0x18005e7d1  call    cs:__imp_CloseHandle
0x18005e7d7  mov     [rbx+70h], rsi
0x18005e7db  mov     [rsp+260h+AllocationSize], rdi
0x18005e7e0  lea     r9, aOplockPAcquire; "Oplock %p acquired"
0x18005e7e7  mov     edx, 8Ch; unsigned int
0x18005e7ec  lea     r8d, [rdx+7Fh]; unsigned int
0x18005e7f0  lea     rcx, [rbp+160h+var_E0]; this
0x18005e7f7  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18005e7fc  jmp     short loc_18005E81B
0x18005e7fe  mov     rbx, [rsp+260h+FileHandle]
0x18005e803  mov     [rsp+260h+FileHandle], r15
0x18005e808  mov     rcx, [rdi+8]; hObject
0x18005e80c  cmp     rcx, r15
0x18005e80f  jz      short loc_18005E817
0x18005e811  call    cs:__imp_CloseHandle
0x18005e817  mov     [rdi+8], rbx
0x18005e81b  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005e822  mov     [rsp+260h+var_200], rax
0x18005e827  mov     rcx, [rsp+260h+FileHandle]; hObject
0x18005e82c  cmp     rcx, r15
0x18005e82f  jz      short loc_18005E837
0x18005e831  call    cs:__imp_CloseHandle
0x18005e837  mov     [rsp+260h+FileHandle], r15
0x18005e83c  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18005e843  mov     [rsp+260h+var_200], rax
0x18005e848  mov     [rsp+260h+FileHandle], r15
0x18005e84d  cmp     [rbp+160h+var_F0], 8
0x18005e852  jb      short loc_18005E85D
0x18005e854  mov     rcx, [rbp+160h+SourceString]; Block
0x18005e858  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005e85d  mov     [rbp+160h+var_F0], 7
0x18005e865  mov     [rbp+160h+var_F8], r14
0x18005e869  mov     word ptr [rbp+160h+SourceString], r14w
0x18005e86e  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005e875  mov     [rbp+160h+var_E0], rax
0x18005e87c  lea     rcx, [rbp+160h+var_E0]; this
0x18005e883  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18005e888  mov     rcx, [rbp+160h+var_30]
0x18005e88f  xor     rcx, rsp; StackCookie
0x18005e892  call    __security_check_cookie
0x18005e897  lea     r11, [rsp+260h+var_20]
0x18005e89f  mov     rbx, [r11+38h]
0x18005e8a3  mov     rsi, [r11+40h]
0x18005e8a7  mov     rsp, r11
0x18005e8aa  pop     r15
0x18005e8ac  pop     r14
0x18005e8ae  pop     r12
0x18005e8b0  pop     rdi
0x18005e8b1  pop     rbp
0x18005e8b2  retn
0x18005e8b3  mov     rcx, [rbx+98h]; pwa
0x18005e8ba  test    rcx, rcx
0x18005e8bd  jz      short loc_18005E8CC
0x18005e8bf  call    cs:__imp_CloseThreadpoolWait
0x18005e8c5  mov     [rbx+98h], r14
0x18005e8cc  mov     rcx, [rbx+90h]; hObject
0x18005e8d3  test    rcx, rcx
0x18005e8d6  jz      short loc_18005E8DE
0x18005e8d8  call    cs:__imp_CloseHandle
0x18005e8de  mov     [rbx+90h], r14
0x18005e8e5  mov     [rbx+0B8h], r14
0x18005e8ec  mov     dword ptr [rsp+260h+AllocationSize], esi
0x18005e8f0  lea     r9, aFailedToAcquir; "Failed to acquire oplock with error %ld"...
0x18005e8f7  mov     edx, 8Ch; unsigned int
0x18005e8fc  lea     r8d, [rdx+75h]; unsigned int
0x18005e900  lea     rcx, [rbp+160h+var_E0]; this
0x18005e907  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18005e90c  mov     [rbp+160h+var_D8], 8004537Ah
0x18005e916  lea     rcx, [rbp+160h+var_E0]; this
0x18005e91d  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005e922  mov     edx, eax; int
0x18005e924  lea     rcx, [rbp+160h+var_E0]; this
0x18005e92b  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005e930  lea     rcx, [rbp+160h+var_E0]; this
0x18005e937  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005e93c  mov     r8d, eax; char
0x18005e93f  xor     r9d, r9d; unsigned __int16 *
0x18005e942  mov     edx, 102h; unsigned int
0x18005e947  lea     rcx, [rbp+160h+var_E0]; this
0x18005e94e  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005e954  cmp     eax, 0C0000043h
0x18005e959  jz      short loc_18005E973
0x18005e95b  cmp     eax, 0C00000E2h
0x18005e960  jz      short loc_18005E973
0x18005e962  cmp     eax, 0C0000909h
0x18005e967  mov     [rbp+160h+var_D8], 80045343h
0x18005e971  jnz     short loc_18005E97D
0x18005e973  mov     [rbp+160h+var_D8], 8004537Ah
0x18005e97d  mov     ecx, eax; Status
0x18005e97f  call    cs:__imp_RtlNtStatusToDosError
0x18005e985  mov     [rbx+58h], eax
0x18005e988  mov     eax, [rbp+160h+var_D8]
0x18005e98e  mov     [rbp+160h+var_D8], eax
0x18005e994  lea     rcx, [rbp+160h+var_E0]; this
0x18005e99b  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005e9a0  mov     edx, eax; int
0x18005e9a2  lea     rcx, [rbp+160h+var_E0]; this
0x18005e9a9  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005e9ae  lea     rcx, [rbp+160h+var_E0]; this
0x18005e9b5  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005e9ba  mov     r8d, eax; char
0x18005e9bd  xor     r9d, r9d; unsigned __int16 *
0x18005e9c0  mov     edx, 0DDh; unsigned int
0x18005e9c5  lea     rcx, [rbp+160h+var_E0]; this
0x18005e9cc  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005e9d2  mov     rcx, [rbx+98h]; pwa
0x18005e9d9  test    rcx, rcx
0x18005e9dc  jz      short loc_18005E9EB
0x18005e9de  call    cs:__imp_CloseThreadpoolWait
0x18005e9e4  mov     [rbx+98h], r14
0x18005e9eb  mov     rcx, [rbx+90h]; hObject
0x18005e9f2  test    rcx, rcx
0x18005e9f5  jz      short loc_18005E9FD
0x18005e9f7  call    cs:__imp_CloseHandle
0x18005e9fd  mov     [rbx+90h], r14
0x18005ea04  mov     [rbx+0B8h], r14
0x18005ea0b  mov     [rbp+160h+var_D8], 80045316h
0x18005ea15  lea     rcx, [rbp+160h+var_E0]; this
0x18005ea1c  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005ea21  mov     edx, eax; int
0x18005ea23  lea     rcx, [rbp+160h+var_E0]; this
0x18005ea2a  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005ea2f  lea     rcx, [rbp+160h+var_E0]; this
0x18005ea36  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005ea3b  mov     r8d, eax; char
0x18005ea3e  xor     r9d, r9d; unsigned __int16 *
0x18005ea41  mov     edx, 0F8h; unsigned int
0x18005ea46  lea     rcx, [rbp+160h+var_E0]; this
0x18005ea4d  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
