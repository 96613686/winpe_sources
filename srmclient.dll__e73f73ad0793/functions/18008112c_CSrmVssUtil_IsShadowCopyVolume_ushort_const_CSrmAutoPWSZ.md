# CSrmVssUtil::IsShadowCopyVolume(ushort const *,CSrmAutoPWSZ &)

- ea: `0x18008112c`
- end: `0x180081603`
- name: `?IsShadowCopyVolume@CSrmVssUtil@@SA_NPEBGAEAVCSrmAutoPWSZ@@@Z`
- size: `1239`
- prototype: `bool __fastcall(const unsigned __int16 *, struct CSrmAutoPWSZ *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task`

## callers

- `0x18008093c`

## callees

- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000ad14`
- `0x18000af40`
- `0x180017fd8`
- `0x18005ac64`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x18007424c`
- `0x18008112c`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180081344`
- `msvcrt!_wcsnicmp` at `0x180081344`
- `ole32!CoTaskMemFree` at `0x180081309`
- `ole32!CoTaskMemFree` at `0x1800814cd`
- `ole32!CoTaskMemFree` at `0x180081309`
- `ole32!CoTaskMemFree` at `0x1800814cd`
- `KERNEL32!CreateFileW` at `0x180081239`
- `KERNEL32!CreateFileW` at `0x180081239`
- `KERNEL32!CloseHandle` at `0x1800812f1`
- `KERNEL32!CloseHandle` at `0x1800814b5`
- `KERNEL32!CloseHandle` at `0x1800812f1`
- `KERNEL32!CloseHandle` at `0x1800814b5`
- `KERNEL32!LocalFree` at `0x180081455`
- `KERNEL32!LocalFree` at `0x180081455`
- `KERNEL32!DeviceIoControl` at `0x18008129c`
- `KERNEL32!DeviceIoControl` at `0x1800813da`
- `KERNEL32!DeviceIoControl` at `0x18008129c`
- `KERNEL32!DeviceIoControl` at `0x1800813da`

## string_xrefs

- `0x180081176`: `CSrmVssUtil::IsShadowCopyVolume`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
char __fastcall CSrmVssUtil::IsShadowCopyVolume(const unsigned __int16 *a1, struct CSrmAutoPWSZ *this)
{
  __int64 v4; // rdi
  WCHAR *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rcx
  HANDLE FileW; // r14
  __int64 v9; // rdx
  __int64 v10; // rcx
  _WORD *v12; // r15
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // esi
  int v16; // eax
  int v17; // eax
  char v18; // al
  int LastFailureAsHRESULT; // eax
  char Hr; // al
  int v21; // eax
  char v22; // al
  int v23; // eax
  char v24; // al
  char v25; // al
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  void **v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  void **v31; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpOutBuffer; // [rsp+68h] [rbp-98h]
  _QWORD OutBuffer[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v34[4]; // [rsp+80h] [rbp-80h] BYREF
  int v35; // [rsp+A0h] [rbp-60h]
  _BYTE v36[96]; // [rsp+A8h] [rbp-58h] BYREF
  int v37; // [rsp+108h] [rbp+8h]
  void **v38; // [rsp+110h] [rbp+10h] BYREF
  int v39; // [rsp+118h] [rbp+18h]

  OutBuffer[1] = v34;
  v34[0] = L"base\\fs\\fsrm\\utilities\\vss\\srmvss.cpp";
  v34[1] = L"CSrmVssUtil::IsShadowCopyVolume";
  v34[2] = L"SRMVSSUC";
  v34[3] = 60;
  v35 = 255;
  v37 = 0x1000000;
  memset_0(v36, 0, sizeof(v36));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v38, (const struct CSrmDebugInfo *)v34, 0);
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  lpFileName = 0;
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&lpFileName, a1);
  v5 = (WCHAR *)lpFileName;
  if ( lpFileName[v4 - 1] == 92 )
    lpFileName[v4 - 1] = 0;
  v29 = -1;
  v28 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  FileW = CreateFileW(v5, 0x100080u, 3u, 0, 3u, 0, 0);
  v29 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7, v6);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, LastFailureAsHRESULT);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0x53u, Hr, 0);
  }
  BytesReturned = 0;
  OutBuffer[0] = 0;
  v39 = 0;
  if ( !DeviceIoControl(FileW, 0x560038u, 0, 0, OutBuffer, 8u, &BytesReturned, 0) )
  {
    v21 = GetLastFailureAsHRESULT(v10, v9);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, v21);
    v22 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0x60u, v22, 0);
  }
  v39 = 0;
  if ( (OutBuffer[0] & 0x2000000000000000LL) != 0 )
  {
    if ( _wcsnicmp(v5, L"\\\\?\\GLOBALROOT", 0xEu) )
    {
      lpOutBuffer = 0;
      v31 = &CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable';
      CSrmAutoLocalPtr_Storage<unsigned char *>::AllocateBytes(&v31, 524);
      v12 = lpOutBuffer;
      if ( !DeviceIoControl(FileW, 0x4D0008u, 0, 0, lpOutBuffer, 0x20Cu, &BytesReturned, 0) )
      {
        v23 = GetLastFailureAsHRESULT(v14, v13);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, v23);
        v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0x81u, v24, 0);
      }
      v39 = 0;
      if ( !*v12 )
      {
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, -2147200234);
        v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0x84u, v25, 0);
      }
      v39 = 0;
      v15 = (unsigned __int16)*v12 >> 1;
      CSrmAutoPWSZ::Allocate(this, (unsigned int)(v15 + 14));
      dwCreationDisposition[0] = v15;
      v16 = StringCchPrintfW(
              *(unsigned __int16 **)this,
              (unsigned int)(v15 + 15),
              L"%s%.*s",
              L"\\\\?\\GLOBALROOT",
              *(_QWORD *)dwCreationDisposition,
              v12 + 1);
      v39 = v16;
      if ( v16 < 0 )
      {
        v17 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, v17);
        v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0x8Fu, v18, 0);
      }
      v39 = v16;
      v31 = &CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable';
      LocalFree(v12);
      v31 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
      lpOutBuffer = 0;
    }
    else
    {
      CSrmAutoPWSZ::CopyFrom(this, v5);
    }
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)&v38,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"TRUE");
    v28 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
    CloseHandle(FileW);
    v28 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
    v29 = -1;
    CoTaskMemFree(v5);
    lpFileName = 0;
    v38 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v38);
    return 1;
  }
  else
  {
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)&v38,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"FALSE");
    v28 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
    CloseHandle(FileW);
    v28 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
    v29 = -1;
    CoTaskMemFree(v5);
    lpFileName = 0;
    v38 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v38);
    return 0;
  }
}

```

## disassembly

```asm
0x18008112c  mov     [rsp-8+arg_10], rbx
0x180081131  push    rbp
0x180081132  push    rsi
0x180081133  push    rdi
0x180081134  push    r12
0x180081136  push    r13
0x180081138  push    r14
0x18008113a  push    r15
0x18008113c  lea     rbp, [rsp-0D0h]
0x180081144  sub     rsp, 1D0h
0x18008114b  mov     rax, cs:__security_cookie
0x180081152  xor     rax, rsp
0x180081155  mov     [rbp+100h+var_40], rax
0x18008115c  mov     r12, rdx
0x18008115f  mov     rbx, rcx
0x180081162  lea     rax, [rbp+100h+var_180]
0x180081166  mov     [rsp+200h+var_188], rax
0x18008116b  lea     rax, aBaseFsFsrmUtil_15; "base\\fs\\fsrm\\utilities\\vss\\srmvss."...
0x180081172  mov     [rbp+100h+var_180], rax
0x180081176  lea     rax, aCsrmvssutilIss; "CSrmVssUtil::IsShadowCopyVolume"
0x18008117d  mov     [rbp+100h+var_178], rax
0x180081181  lea     rax, aSrmvssuc; "SRMVSSUC"
0x180081188  mov     [rbp+100h+var_170], rax
0x18008118c  mov     [rbp+100h+var_168], 3Ch ; '<'
0x180081194  xor     r13d, r13d
0x180081197  mov     [rbp+100h+var_160], 0FFh
0x18008119e  mov     [rbp+100h+var_F8], 1000000h
0x1800811a5  xor     edx, edx; Val
0x1800811a7  lea     r8d, [r13+60h]; Size
0x1800811ab  lea     rcx, [rbp+100h+var_158]; void *
0x1800811af  call    memset_0
0x1800811b4  nop
0x1800811b5  xor     r8d, r8d
0x1800811b8  lea     rdx, [rbp+100h+var_180]
0x1800811bc  lea     rcx, [rbp+100h+var_F0]
0x1800811c0  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800811c5  nop
0x1800811c6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800811ca  mov     rdi, rsi
0x1800811cd  inc     rdi
0x1800811d0  cmp     [rbx+rdi*2], r13w
0x1800811d5  jnz     short loc_1800811CD
0x1800811d7  mov     [rsp+200h+lpFileName], r13
0x1800811dc  mov     rdx, rbx; unsigned __int16 *
0x1800811df  lea     rcx, [rsp+200h+lpFileName]; this
0x1800811e4  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x1800811e9  mov     rbx, [rsp+200h+lpFileName]
0x1800811ee  cmp     word ptr [rbx+rdi*2-2], 5Ch ; '\'
0x1800811f4  jnz     short loc_1800811FC
0x1800811f6  mov     [rbx+rdi*2-2], r13w
0x1800811fc  lea     rdi, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x180081203  mov     [rsp+200h+var_1B8], rdi
0x180081208  mov     [rsp+200h+var_1B0], rsi
0x18008120d  lea     r15, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x180081214  mov     [rsp+200h+var_1B8], r15
0x180081219  mov     [rsp+200h+hTemplateFile], r13; hTemplateFile
0x18008121e  mov     [rsp+200h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180081223  mov     r8d, 3; dwShareMode
0x180081229  mov     [rsp+200h+dwCreationDisposition], r8d; dwCreationDisposition
0x18008122e  xor     r9d, r9d; lpSecurityAttributes
0x180081231  mov     edx, 100080h; dwDesiredAccess
0x180081236  mov     rcx, rbx; lpFileName
0x180081239  call    cs:__imp_CreateFileW
0x18008123f  mov     r14, rax
0x180081242  mov     [rsp+200h+var_1B0], rsi
0x180081247  mov     [rsp+200h+var_1B0], rax
0x18008124c  mov     eax, [rbp+100h+var_E8]
0x18008124f  mov     [rbp+100h+var_E8], eax
0x180081252  cmp     r14, rsi
0x180081255  jz      loc_18008154F
0x18008125b  mov     [rbp+100h+var_E8], r13d
0x18008125f  mov     [rsp+200h+BytesReturned], r13d
0x180081264  mov     [rsp+200h+OutBuffer], r13
0x180081269  mov     [rbp+100h+var_E8], r13d
0x18008126d  mov     [rsp+200h+lpOverlapped], r13; lpOverlapped
0x180081272  lea     rax, [rsp+200h+BytesReturned]
0x180081277  mov     [rsp+200h+hTemplateFile], rax; lpBytesReturned
0x18008127c  mov     [rsp+200h+dwFlagsAndAttributes], 8; nOutBufferSize
0x180081284  lea     rax, [rsp+200h+OutBuffer]
0x180081289  mov     qword ptr [rsp+200h+dwCreationDisposition], rax; lpOutBuffer
0x18008128e  xor     r9d, r9d; nInBufferSize
0x180081291  xor     r8d, r8d; lpInBuffer
0x180081294  mov     edx, 560038h; dwIoControlCode
0x180081299  mov     rcx, r14; hDevice
0x18008129c  call    cs:__imp_DeviceIoControl
0x1800812a2  test    eax, eax
0x1800812a4  jz      loc_18008157C
0x1800812aa  mov     [rbp+100h+var_E8], r13d
0x1800812ae  mov     rax, 2000000000000000h
0x1800812b8  test    [rsp+200h+OutBuffer], rax
0x1800812bd  jnz     short loc_180081334
0x1800812bf  lea     rax, aFalse; "FALSE"
0x1800812c6  mov     qword ptr [rsp+200h+dwCreationDisposition], rax
0x1800812cb  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x1800812d2  mov     r8d, 0AAh; unsigned int
0x1800812d8  lea     rdx, aReturn; "RETURN"
0x1800812df  lea     rcx, [rbp+100h+var_F0]; this
0x1800812e3  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1800812e8  nop
0x1800812e9  mov     [rsp+200h+var_1B8], r15
0x1800812ee  mov     rcx, r14; hObject
0x1800812f1  call    cs:__imp_CloseHandle
0x1800812f7  mov     [rsp+200h+var_1B0], rsi
0x1800812fc  mov     [rsp+200h+var_1B8], rdi
0x180081301  mov     [rsp+200h+var_1B0], rsi
0x180081306  mov     rcx, rbx; pv
0x180081309  call    cs:__imp_CoTaskMemFree
0x18008130f  mov     [rsp+200h+lpFileName], r13
0x180081314  mov     [rsp+200h+lpFileName], r13
0x180081319  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180081320  mov     [rbp+100h+var_F0], rax
0x180081324  lea     rcx, [rbp+100h+var_F0]; this
0x180081328  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18008132d  xor     al, al
0x18008132f  jmp     loc_1800814F3
0x180081334  mov     r8d, 0Eh; MaxCount
0x18008133a  lea     rdx, aGlobalroot; "\\\\?\\GLOBALROOT"
0x180081341  mov     rcx, rbx; String1
0x180081344  call    cs:__imp__wcsnicmp
0x18008134a  test    eax, eax
0x18008134c  jnz     short loc_18008135E
0x18008134e  mov     rdx, rbx; unsigned __int16 *
0x180081351  mov     rcx, r12; this
0x180081354  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180081359  jmp     loc_180081483
0x18008135e  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x180081365  mov     [rsp+200h+var_1A0], rax
0x18008136a  mov     [rsp+200h+lpOutBuffer], r13
0x18008136f  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAE@@6B@; const CSrmAutoLocalPtr_Storage<uchar *>::`vftable'
0x180081376  mov     [rsp+200h+var_1A0], rax
0x18008137b  lea     rax, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x180081382  mov     [rsp+200h+var_1A0], rax
0x180081387  mov     [rsp+200h+lpOutBuffer], r13
0x18008138c  lea     rax, ??_7?$CSrmAutoLocalPtr@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@6B@; const CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable'
0x180081393  mov     [rsp+200h+var_1A0], rax
0x180081398  mov     edi, 20Ch
0x18008139d  mov     edx, edi
0x18008139f  lea     rcx, [rsp+200h+var_1A0]
0x1800813a4  call    ?AllocateBytes@?$CSrmAutoLocalPtr_Storage@PEAE@@QEAAX_K@Z; CSrmAutoLocalPtr_Storage<uchar *>::AllocateBytes(unsigned __int64)
0x1800813a9  mov     eax, [rbp+100h+var_E8]
0x1800813ac  mov     [rbp+100h+var_E8], eax
0x1800813af  mov     r15, [rsp+200h+lpOutBuffer]
0x1800813b4  mov     [rsp+200h+lpOverlapped], r13; lpOverlapped
0x1800813b9  lea     rax, [rsp+200h+BytesReturned]
0x1800813be  mov     [rsp+200h+hTemplateFile], rax; lpBytesReturned
0x1800813c3  mov     [rsp+200h+dwFlagsAndAttributes], edi; nOutBufferSize
0x1800813c7  mov     qword ptr [rsp+200h+dwCreationDisposition], r15; lpOutBuffer
0x1800813cc  xor     r9d, r9d; nInBufferSize
0x1800813cf  xor     r8d, r8d; lpInBuffer
0x1800813d2  mov     edx, 4D0008h; dwIoControlCode
0x1800813d7  mov     rcx, r14; hDevice
0x1800813da  call    cs:__imp_DeviceIoControl
0x1800813e0  test    eax, eax
0x1800813e2  jz      loc_1800815A9
0x1800813e8  mov     [rbp+100h+var_E8], r13d
0x1800813ec  mov     [rbp+100h+var_E8], r13d
0x1800813f0  cmp     r13w, [r15]
0x1800813f4  jz      loc_1800815D7
0x1800813fa  mov     [rbp+100h+var_E8], r13d
0x1800813fe  movzx   esi, word ptr [r15]
0x180081402  shr     esi, 1
0x180081404  lea     edi, [rsi+0Eh]
0x180081407  mov     edx, edi; unsigned __int64
0x180081409  mov     rcx, r12; this
0x18008140c  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x180081411  lea     rcx, [r15+2]
0x180081415  lea     edx, [rdi+1]; unsigned __int64
0x180081418  mov     qword ptr [rsp+200h+dwFlagsAndAttributes], rcx
0x18008141d  mov     [rsp+200h+dwCreationDisposition], esi
0x180081421  lea     r9, aGlobalroot; "\\\\?\\GLOBALROOT"
0x180081428  lea     r8, aSS; "%s%.*s"
0x18008142f  mov     rcx, [r12]; unsigned __int16 *
0x180081433  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180081438  mov     [rbp+100h+var_E8], eax
0x18008143b  test    eax, eax
0x18008143d  js      loc_18008151D
0x180081443  mov     [rbp+100h+var_E8], eax
0x180081446  lea     rax, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x18008144d  mov     [rsp+200h+var_1A0], rax
0x180081452  mov     rcx, r15; hMem
0x180081455  call    cs:__imp_LocalFree
0x18008145b  mov     [rsp+200h+lpOutBuffer], r13
0x180081460  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x180081467  mov     [rsp+200h+var_1A0], rax
0x18008146c  mov     [rsp+200h+lpOutBuffer], r13
0x180081471  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180081475  lea     rdi, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18008147c  lea     r15, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x180081483  lea     rax, aTrue_0; "TRUE"
0x18008148a  mov     qword ptr [rsp+200h+dwCreationDisposition], rax
0x18008148f  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180081496  mov     r8d, 0AAh; unsigned int
0x18008149c  lea     rdx, aReturn; "RETURN"
0x1800814a3  lea     rcx, [rbp+100h+var_F0]; this
0x1800814a7  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1800814ac  nop
0x1800814ad  mov     [rsp+200h+var_1B8], r15
0x1800814b2  mov     rcx, r14; hObject
0x1800814b5  call    cs:__imp_CloseHandle
0x1800814bb  mov     [rsp+200h+var_1B0], rsi
0x1800814c0  mov     [rsp+200h+var_1B8], rdi
0x1800814c5  mov     [rsp+200h+var_1B0], rsi
0x1800814ca  mov     rcx, rbx; pv
0x1800814cd  call    cs:__imp_CoTaskMemFree
0x1800814d3  mov     [rsp+200h+lpFileName], r13
0x1800814d8  mov     [rsp+200h+lpFileName], r13
0x1800814dd  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800814e4  mov     [rbp+100h+var_F0], rax
0x1800814e8  lea     rcx, [rbp+100h+var_F0]; this
0x1800814ec  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800814f1  mov     al, 1
0x1800814f3  mov     rcx, [rbp+100h+var_40]
0x1800814fa  xor     rcx, rsp; StackCookie
0x1800814fd  call    __security_check_cookie
0x180081502  mov     rbx, [rsp+200h+arg_10]
0x18008150a  add     rsp, 1D0h
0x180081511  pop     r15
0x180081513  pop     r14
0x180081515  pop     r13
0x180081517  pop     r12
0x180081519  pop     rdi
0x18008151a  pop     rsi
0x18008151b  pop     rbp
0x18008151c  retn
0x18008151d  lea     rcx, [rbp+100h+var_F0]; this
0x180081521  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180081526  mov     edx, eax; int
0x180081528  lea     rcx, [rbp+100h+var_F0]; this
0x18008152c  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180081531  lea     rcx, [rbp+100h+var_F0]; this
0x180081535  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18008153a  mov     r8d, eax; char
0x18008153d  xor     r9d, r9d; unsigned __int16 *
0x180081540  mov     edx, 8Fh; unsigned int
0x180081545  lea     rcx, [rbp+100h+var_F0]; this
0x180081549  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18008154f  call    GetLastFailureAsHRESULT
0x180081554  mov     edx, eax; int
0x180081556  lea     rcx, [rbp+100h+var_F0]; this
0x18008155a  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18008155f  lea     rcx, [rbp+100h+var_F0]; this
0x180081563  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180081568  mov     r8d, eax; char
0x18008156b  xor     r9d, r9d; unsigned __int16 *
0x18008156e  lea     edx, [r9+53h]; unsigned int
0x180081572  lea     rcx, [rbp+100h+var_F0]; this
0x180081576  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18008157c  call    GetLastFailureAsHRESULT
0x180081581  mov     edx, eax; int
0x180081583  lea     rcx, [rbp+100h+var_F0]; this
0x180081587  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18008158c  lea     rcx, [rbp+100h+var_F0]; this
0x180081590  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180081595  mov     r8d, eax; char
0x180081598  xor     r9d, r9d; unsigned __int16 *
0x18008159b  lea     edx, [r9+60h]; unsigned int
0x18008159f  lea     rcx, [rbp+100h+var_F0]; this
0x1800815a3  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800815a9  call    GetLastFailureAsHRESULT
0x1800815ae  mov     edx, eax; int
0x1800815b0  lea     rcx, [rbp+100h+var_F0]; this
0x1800815b4  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800815b9  lea     rcx, [rbp+100h+var_F0]; this
0x1800815bd  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800815c2  mov     r8d, eax; char
0x1800815c5  xor     r9d, r9d; unsigned __int16 *
0x1800815c8  mov     edx, 81h; unsigned int
0x1800815cd  lea     rcx, [rbp+100h+var_F0]; this
0x1800815d1  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800815d7  mov     edx, 80045316h; int
0x1800815dc  lea     rcx, [rbp+100h+var_F0]; this
0x1800815e0  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800815e5  lea     rcx, [rbp+100h+var_F0]; this
0x1800815e9  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800815ee  mov     r8d, eax; char
0x1800815f1  xor     r9d, r9d; unsigned __int16 *
0x1800815f4  mov     edx, 84h; unsigned int
0x1800815f9  lea     rcx, [rbp+100h+var_F0]; this
0x1800815fd  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
