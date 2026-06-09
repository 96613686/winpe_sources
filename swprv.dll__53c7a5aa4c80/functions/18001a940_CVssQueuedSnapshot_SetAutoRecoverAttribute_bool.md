# CVssQueuedSnapshot::SetAutoRecoverAttribute(bool)

- ea: `0x18001a940`
- end: `0x18001abb0`
- name: `?SetAutoRecoverAttribute@CVssQueuedSnapshot@@AEAAX_N@Z`
- size: `624`
- prototype: `void __fastcall(CVssQueuedSnapshot *__hidden this, bool)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18001a01c`
- `0x18001a0d0`

## callees

- `0x18000212c`
- `0x18000313c`
- `0x1800036e8`
- `0x180003de8`
- `0x1800048f8`
- `0x180004a38`
- `0x180004b10`
- `0x18000dc10`
- `0x180018334`
- `0x180019458`
- `0x180019d64`
- `0x18001a940`
- `0x180033a8c`
- `0x180033c78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab12`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001aaf5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001aaf5`

## string_xrefs

- `0x18001ab67`: `CreateFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssQueuedSnapshot::SetAutoRecoverAttribute(CVssQueuedSnapshot *this)
{
  bool v2; // dl
  struct _VSS_SNAPSHOT_PROP *SnapshotProperties; // rax
  HANDLE FileW; // rax
  signed int LastError; // eax
  void **v6; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h]
  _QWORD v8[2]; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v9; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v10; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v11; // [rsp+70h] [rbp-90h]
  int v12; // [rsp+78h] [rbp-88h]
  int v13; // [rsp+7Ch] [rbp-84h]
  int v14; // [rsp+80h] [rbp-80h]
  _BYTE v15[120]; // [rsp+88h] [rbp-78h] BYREF
  int v16; // [rsp+100h] [rbp+0h]
  LPVOID v17; // [rsp+110h] [rbp+10h] BYREF
  signed int v18; // [rsp+118h] [rbp+18h]
  __int64 v19; // [rsp+1D0h] [rbp+D0h] BYREF

  v9 = L"base\\stor\\vss\\modules\\softprv\\src\\qsnap.cxx";
  v10 = L"CVssQueuedSnapshot::SetAutoRecoverAttribute";
  v11 = L"SPRQSNPC";
  v12 = 398;
  v13 = 2;
  v14 = 255;
  v16 = 0x1000000;
  memset_0(v15, 0, sizeof(v15));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v17, (__int64)&v9, 0);
  CVssQueuedSnapshot::OpenSnapshotChannel(this, v2);
  v19 = 0;
  CVssIOCTLChannel::Call((_QWORD *)this + 18, (__int64)&v17, 0x560038u, 1, 2, 0);
  CVssIOCTLChannel::Unpack<__int64>((CVssQueuedSnapshot *)((char *)this + 144), (struct CVssFunctionTracer *)&v17, &v19);
  CVssIOCTLChannel::Call((_QWORD *)this + 18, (__int64)&v17, 0x90020u, 1, 2, 0);
  lpFileName = 0;
  CVssIOCTLChannel::PackArray<_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION>(
    (CVssQueuedSnapshot *)((char *)this + 144),
    (struct CVssFunctionTracer *)&v17);
  CVssIOCTLChannel::Call((_QWORD *)this + 18, (__int64)&v17, 0x560034u, 1, 2, 0);
  CVssIOCTLChannel::Close((CVssQueuedSnapshot *)((char *)this + 144));
  lpFileName = 0;
  v6 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  SnapshotProperties = CVssQueuedSnapshot::GetSnapshotProperties(this);
  CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::CopyFrom(
    (__int64)&v6,
    SnapshotProperties->m_pwszSnapshotDeviceObject);
  FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
  v8[0] = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v8[1] = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v18 = LastError;
    v9 = L"base\\stor\\vss\\modules\\softprv\\src\\qsnap.cxx";
    v10 = L"CVssQueuedSnapshot::SetAutoRecoverAttribute";
    v11 = L"SPRQSNPC";
    v12 = 437;
    v13 = 2;
    v14 = 255;
    v16 = 0x1000000;
    memset_0(v15, 0, sizeof(v15));
    CVssFunctionTracer::CheckForError(&v17, &v9, L"CreateFile");
  }
  CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(v8);
  CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>(&v6);
  CVssFunctionTracer::~CVssFunctionTracer(&v17);
}

```

## disassembly

```asm
0x18001a940  push    rbp
0x18001a942  push    rbx
0x18001a943  push    rsi
0x18001a944  push    rdi
0x18001a945  push    r12
0x18001a947  push    r13
0x18001a949  push    r14
0x18001a94b  push    r15
0x18001a94d  lea     rbp, [rsp-88h]
0x18001a955  sub     rsp, 188h
0x18001a95c  mov     bl, dl
0x18001a95e  mov     rsi, rcx
0x18001a961  lea     r12, aBaseStorVssMod_18; "base\\stor\\vss\\modules\\softprv\\src"...
0x18001a968  mov     [rsp+1C0h+var_160], r12
0x18001a96d  lea     r13, aCvssqueuedsnap_37; "CVssQueuedSnapshot::SetAutoRecoverAttri"...
0x18001a974  mov     [rsp+1C0h+var_158], r13
0x18001a979  lea     rax, aSprqsnpc; "SPRQSNPC"
0x18001a980  mov     [rsp+1C0h+var_150], rax
0x18001a985  mov     [rsp+1C0h+var_148], 18Eh
0x18001a98d  mov     r15d, 2
0x18001a993  mov     [rsp+1C0h+var_144], r15d
0x18001a998  mov     [rbp+0C0h+var_140], 0FFh
0x18001a99f  xor     r14d, r14d
0x18001a9a2  mov     [rbp+0C0h+var_C0], 1000000h
0x18001a9a9  xor     edx, edx; Val
0x18001a9ab  lea     r8d, [r15+76h]; Size
0x18001a9af  lea     rcx, [rbp+0C0h+var_138]; void *
0x18001a9b3  call    memset_0
0x18001a9b8  xor     r8d, r8d
0x18001a9bb  lea     rdx, [rsp+1C0h+var_160]
0x18001a9c0  lea     rcx, [rbp+0C0h+var_B0]
0x18001a9c4  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18001a9c9  nop
0x18001a9ca  mov     rcx, rsi; this
0x18001a9cd  call    ?OpenSnapshotChannel@CVssQueuedSnapshot@@QEAAX_N@Z; CVssQueuedSnapshot::OpenSnapshotChannel(bool)
0x18001a9d2  mov     [rbp+0C0h+arg_0], r14
0x18001a9d9  lea     rdi, [rsi+90h]
0x18001a9e0  mov     [rsp+1C0h+hTemplateFile], r14
0x18001a9e5  mov     byte ptr [rsp+1C0h+dwFlagsAndAttributes], r14b
0x18001a9ea  mov     [rsp+1C0h+dwCreationDisposition], r15d
0x18001a9ef  mov     r9b, 1
0x18001a9f2  mov     r8d, 560038h
0x18001a9f8  lea     rdx, [rbp+0C0h+var_B0]
0x18001a9fc  mov     rcx, rdi
0x18001a9ff  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x18001aa04  lea     r8, [rbp+0C0h+arg_0]
0x18001aa0b  lea     rdx, [rbp+0C0h+var_B0]
0x18001aa0f  mov     rcx, rdi
0x18001aa12  call    ??$Unpack@_J@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEA_JK_N@Z; CVssIOCTLChannel::Unpack<__int64>(CVssFunctionTracer &,__int64 *,ulong,bool)
0x18001aa17  mov     [rsp+1C0h+hTemplateFile], r14
0x18001aa1c  mov     byte ptr [rsp+1C0h+dwFlagsAndAttributes], r14b
0x18001aa21  mov     [rsp+1C0h+dwCreationDisposition], r15d
0x18001aa26  mov     r9b, 1
0x18001aa29  mov     r8d, 90020h
0x18001aa2f  lea     rdx, [rbp+0C0h+var_B0]
0x18001aa33  mov     rcx, rdi
0x18001aa36  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x18001aa3b  mov     [rsp+1C0h+lpFileName], r14
0x18001aa40  mov     rax, [rbp+0C0h+arg_0]
0x18001aa47  test    bl, bl
0x18001aa49  jz      short loc_18001AA5A
0x18001aa4b  mov     rcx, 0EFFFFFFFFFFFFFFFh
0x18001aa55  and     rax, rcx
0x18001aa58  jmp     short loc_18001AA67
0x18001aa5a  mov     rcx, 1000000000000000h
0x18001aa64  or      rax, rcx
0x18001aa67  mov     [rsp+1C0h+var_180], rax
0x18001aa6c  lea     r8, [rsp+1C0h+var_180]
0x18001aa71  lea     rdx, [rbp+0C0h+var_B0]; struct CVssFunctionTracer *
0x18001aa75  mov     rcx, rdi; this
0x18001aa78  call    ??$PackArray@U_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION@@@CVssIOCTLChannel@@QEAAPEAXAEAVCVssFunctionTracer@@PEAU_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION@@K@Z; CVssIOCTLChannel::PackArray<_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION>(CVssFunctionTracer &,_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION *,ulong)
0x18001aa7d  mov     [rsp+1C0h+hTemplateFile], r14
0x18001aa82  mov     byte ptr [rsp+1C0h+dwFlagsAndAttributes], r14b
0x18001aa87  mov     [rsp+1C0h+dwCreationDisposition], r15d
0x18001aa8c  mov     r9b, 1
0x18001aa8f  mov     r8d, 560034h
0x18001aa95  lea     rdx, [rbp+0C0h+var_B0]
0x18001aa99  mov     rcx, rdi
0x18001aa9c  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x18001aaa1  mov     rcx, rdi; this
0x18001aaa4  call    ?Close@CVssIOCTLChannel@@QEAAXXZ; CVssIOCTLChannel::Close(void)
0x18001aaa9  mov     [rsp+1C0h+lpFileName], r14
0x18001aaae  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x18001aab5  mov     [rsp+1C0h+var_180], rax
0x18001aaba  mov     rcx, rsi; this
0x18001aabd  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x18001aac2  mov     rdx, [rax+28h]
0x18001aac6  lea     rcx, [rsp+1C0h+var_180]
0x18001aacb  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::CopyFrom(ushort const *)
0x18001aad0  mov     [rsp+1C0h+hTemplateFile], r14; hTemplateFile
0x18001aad5  mov     [rsp+1C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18001aadd  mov     r8d, 3; dwShareMode
0x18001aae3  mov     [rsp+1C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001aae8  xor     r9d, r9d; lpSecurityAttributes
0x18001aaeb  mov     edx, 80000000h; dwDesiredAccess
0x18001aaf0  mov     rcx, [rsp+1C0h+lpFileName]; lpFileName
0x18001aaf5  call    cs:__imp_CreateFileW
0x18001aafb  lea     rcx, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18001ab02  mov     [rsp+1C0h+var_170], rcx
0x18001ab07  mov     [rsp+1C0h+var_168], rax
0x18001ab0c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ab10  jnz     short loc_18001AB7D
0x18001ab12  call    cs:__imp_GetLastError
0x18001ab18  test    eax, eax
0x18001ab1a  jle     short loc_18001AB24
0x18001ab1c  movzx   eax, ax
0x18001ab1f  or      eax, 80070000h
0x18001ab24  mov     [rbp+0C0h+var_A8], eax
0x18001ab27  mov     [rsp+1C0h+var_160], r12
0x18001ab2c  mov     [rsp+1C0h+var_158], r13
0x18001ab31  lea     rax, aSprqsnpc; "SPRQSNPC"
0x18001ab38  mov     [rsp+1C0h+var_150], rax
0x18001ab3d  mov     [rsp+1C0h+var_148], 1B5h
0x18001ab45  mov     [rsp+1C0h+var_144], r15d
0x18001ab4a  mov     [rbp+0C0h+var_140], 0FFh
0x18001ab51  mov     [rbp+0C0h+var_C0], 1000000h
0x18001ab58  xor     edx, edx; Val
0x18001ab5a  lea     r8d, [rdx+78h]; Size
0x18001ab5e  lea     rcx, [rbp+0C0h+var_138]; void *
0x18001ab62  call    memset_0
0x18001ab67  lea     r8, aCreatefile; "CreateFile"
0x18001ab6e  lea     rdx, [rsp+1C0h+var_160]
0x18001ab73  lea     rcx, [rbp+0C0h+var_B0]
0x18001ab77  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x18001ab7c  nop
0x18001ab7d  lea     rcx, [rsp+1C0h+var_170]
0x18001ab82  call    ??1?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@UEAA@XZ; CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>(void)
0x18001ab87  nop
0x18001ab88  lea     rcx, [rsp+1C0h+var_180]
0x18001ab8d  call    ??1?$CVssAuto@PEAU_SID@@V?$CVssAllocatingPtr_Storage@PEAU_SID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6APEAX_K@Z$1?LocalAllocate@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>(void)
0x18001ab92  nop
0x18001ab93  lea     rcx, [rbp+0C0h+var_B0]; this
0x18001ab97  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18001ab9c  add     rsp, 188h
0x18001aba3  pop     r15
0x18001aba5  pop     r14
0x18001aba7  pop     r13
0x18001aba9  pop     r12
0x18001abab  pop     rdi
0x18001abac  pop     rsi
0x18001abad  pop     rbx
0x18001abae  pop     rbp
0x18001abaf  retn
```
