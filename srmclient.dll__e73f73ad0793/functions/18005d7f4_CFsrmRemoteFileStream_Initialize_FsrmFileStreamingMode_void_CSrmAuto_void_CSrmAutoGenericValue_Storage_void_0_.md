# CFsrmRemoteFileStream::Initialize(_FsrmFileStreamingMode,void *,CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>> &)

- ea: `0x18005d7f4`
- end: `0x18005daa1`
- name: `?Initialize@CFsrmRemoteFileStream@@AEAAXW4_FsrmFileStreamingMode@@PEAXAEAV?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@@Z`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x18005c750`

## callees

- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000cde0`
- `0x18005d7f4`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073f54`
- `0x180075510`
- `0x180075eb8`
- `0x18007691c`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18005d9d7`
- `KERNEL32!CloseHandle` at `0x18005d9f3`
- `KERNEL32!CloseHandle` at `0x18005d9d7`
- `KERNEL32!CloseHandle` at `0x18005d9f3`
- `KERNEL32!CreateEventW` at `0x18005d8ea`
- `KERNEL32!CreateEventW` at `0x18005d8ea`

## string_xrefs

- `0x18005d833`: `base\fs\fsrm\service\stream\streamlib.cpp`
- `0x18005d9a4`: `Stream created with handle: %p`
- `0x18005d97c`: `- Access: %d`
- `0x18005d92f`: `System\CurrentControlSet\Services\SrmSvc\Settings`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CFsrmRemoteFileStream::Initialize(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdx
  HANDLE EventW; // rdi
  __int64 v10; // rsi
  void *v11; // rcx
  void *v12; // rcx
  int LastFailureAsHRESULT; // eax
  char v14; // al
  char Hr; // al
  unsigned int v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  void **v17; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v18; // [rsp+40h] [rbp-C0h]
  LPVOID v19[3]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v20[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+78h] [rbp-88h]
  int v22; // [rsp+7Ch] [rbp-84h]
  int v23; // [rsp+80h] [rbp-80h]
  _BYTE v24[96]; // [rsp+88h] [rbp-78h] BYREF
  int v25; // [rsp+E8h] [rbp-18h]
  void **v26; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v27; // [rsp+F8h] [rbp-8h]

  *(_QWORD *)v16 = v20;
  v20[0] = L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp";
  v20[1] = L"CFsrmRemoteFileStream::Initialize";
  v20[2] = L"STREAMLC";
  v21 = 1537;
  v22 = 26;
  v23 = 255;
  v25 = 0x1000000;
  memset_0(v24, 0, sizeof(v24));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v26, (const struct CSrmDebugInfo *)v20, 0);
  v19[2] = 0;
  v19[1] = 0;
  v19[0] = (LPVOID)131353;
  v16[0] = 1;
  if ( ((a3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v26, -2147024809);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v26);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v26, 0x607u, Hr, 0);
  }
  v27 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v17 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v18 = EventW;
  if ( !EventW )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v27, v8);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v26, LastFailureAsHRESULT);
    v14 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v26);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v26, 0x60Bu, v14, 0);
  }
  v27 = 0;
  if ( CSrmRegistryKey::Open(
         (CSrmRegistryKey *)v19,
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\SrmSvc\\Settings")
    && CSrmRegistryKey::GetValue((HKEY *)v19, L"UseStreamBackgroundIO", v16) )
  {
    *(_BYTE *)(a1 + 128) = v16[0] != 0;
  }
  *(_DWORD *)(a1 + 112) = a2;
  CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v26, 0x78u, 0x618u, L"- Access: %d", a2);
  *(_QWORD *)(a1 + 72) = a3;
  CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v26, 0x78u, 0x61Bu, L"Stream created with handle: %p", a3);
  v10 = *(_QWORD *)(a4 + 8);
  if ( v10 )
  {
    *(_QWORD *)(a4 + 8) = 0;
    v11 = *(void **)(a1 + 88);
    if ( v11 )
      CloseHandle(v11);
    *(_QWORD *)(a1 + 88) = v10;
  }
  v18 = 0;
  v12 = *(void **)(a1 + 104);
  if ( v12 )
    CloseHandle(v12);
  *(_QWORD *)(a1 + 104) = EventW;
  CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(&v17);
  CSrmRegistryKey::~CSrmRegistryKey(v19);
  v26 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v26);
}

```

## disassembly

```asm
0x18005d7f4  push    rbp
0x18005d7f6  push    rbx
0x18005d7f7  push    rsi
0x18005d7f8  push    rdi
0x18005d7f9  push    r14
0x18005d7fb  push    r15
0x18005d7fd  lea     rbp, [rsp-0B8h]
0x18005d805  sub     rsp, 1B8h
0x18005d80c  mov     rax, cs:__security_cookie
0x18005d813  xor     rax, rsp
0x18005d816  mov     [rbp+0E0h+var_40], rax
0x18005d81d  mov     r14, r9
0x18005d820  mov     rsi, r8
0x18005d823  mov     r15d, edx
0x18005d826  mov     rbx, rcx
0x18005d829  lea     rax, [rsp+1E0h+var_180]
0x18005d82e  mov     qword ptr [rsp+1E0h+var_1B0], rax
0x18005d833  lea     rax, aBaseFsFsrmServ_12; "base\\fs\\fsrm\\service\\stream\\stream"...
0x18005d83a  mov     [rsp+1E0h+var_180], rax
0x18005d83f  lea     rax, aCfsrmremotefil_7; "CFsrmRemoteFileStream::Initialize"
0x18005d846  mov     [rsp+1E0h+var_178], rax
0x18005d84b  lea     rax, aStreamlc; "STREAMLC"
0x18005d852  mov     [rsp+1E0h+var_170], rax
0x18005d857  mov     [rsp+1E0h+var_168], 601h
0x18005d85f  mov     [rsp+1E0h+var_164], 1Ah
0x18005d867  mov     [rbp+0E0h+var_160], 0FFh
0x18005d86e  mov     [rbp+0E0h+var_F8], 1000000h
0x18005d875  mov     edi, 1
0x18005d87a  xor     edx, edx; Val
0x18005d87c  lea     r8d, [rdi+5Fh]; Size
0x18005d880  lea     rcx, [rbp+0E0h+var_158]; void *
0x18005d884  call    memset_0
0x18005d889  nop
0x18005d88a  xor     r8d, r8d
0x18005d88d  lea     rdx, [rsp+1E0h+var_180]
0x18005d892  lea     rcx, [rbp+0E0h+var_F0]
0x18005d896  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005d89b  nop
0x18005d89c  mov     [rsp+1E0h+var_188], 0
0x18005d8a5  mov     [rsp+1E0h+var_190], 0
0x18005d8ae  mov     [rsp+1E0h+var_198], 20019h
0x18005d8b7  mov     dword ptr [rsp+1E0h+var_198], 20119h
0x18005d8bf  mov     [rsp+1E0h+var_1B0], edi
0x18005d8c3  mov     eax, [rbp+0E0h+var_E8]
0x18005d8c6  mov     [rbp+0E0h+var_E8], eax
0x18005d8c9  lea     rax, [rsi+1]
0x18005d8cd  test    rax, 0FFFFFFFFFFFFFFFEh
0x18005d8d3  jz      loc_18005DA75
0x18005d8d9  mov     [rbp+0E0h+var_E8], 0
0x18005d8e0  xor     r9d, r9d; lpName
0x18005d8e3  xor     r8d, r8d; bInitialState
0x18005d8e6  mov     edx, edi; bManualReset
0x18005d8e8  xor     ecx, ecx; lpEventAttributes
0x18005d8ea  call    cs:__imp_CreateEventW
0x18005d8f0  mov     rdi, rax
0x18005d8f3  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18005d8fa  mov     [rsp+1E0h+var_1A8], rax
0x18005d8ff  mov     [rsp+1E0h+var_1A0], 0
0x18005d908  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005d90f  mov     [rsp+1E0h+var_1A8], rax
0x18005d914  mov     [rsp+1E0h+var_1A0], rdi
0x18005d919  mov     ecx, [rbp+0E0h+var_E8]
0x18005d91c  mov     [rbp+0E0h+var_E8], ecx
0x18005d91f  test    rdi, rdi
0x18005d922  jz      loc_18005DA46
0x18005d928  mov     [rbp+0E0h+var_E8], 0
0x18005d92f  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Sr"...
0x18005d936  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18005d93d  lea     rcx, [rsp+1E0h+var_198]; this
0x18005d942  call    ?Open@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Open(HKEY__ *,ushort const *,...)
0x18005d947  test    al, al
0x18005d949  jz      short loc_18005D973
0x18005d94b  lea     r8, [rsp+1E0h+var_1B0]; unsigned int *
0x18005d950  lea     rdx, aUsestreambackg; "UseStreamBackgroundIO"
0x18005d957  lea     rcx, [rsp+1E0h+var_198]; this
0x18005d95c  call    ?GetValue@CSrmRegistryKey@@QEAA_NPEBGPEAK_N@Z; CSrmRegistryKey::GetValue(ushort const *,ulong *,bool)
0x18005d961  test    al, al
0x18005d963  jz      short loc_18005D973
0x18005d965  cmp     [rsp+1E0h+var_1B0], 0
0x18005d96a  setnz   al
0x18005d96d  mov     [rbx+80h], al
0x18005d973  mov     [rbx+70h], r15d
0x18005d977  mov     dword ptr [rsp+1E0h+var_1C0], r15d
0x18005d97c  lea     r9, aAccessD; "- Access: %d"
0x18005d983  mov     r8d, 618h; unsigned int
0x18005d989  mov     r15d, 78h ; 'x'
0x18005d98f  mov     edx, r15d; unsigned int
0x18005d992  lea     rcx, [rbp+0E0h+var_F0]; this
0x18005d996  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18005d99b  mov     [rbx+48h], rsi
0x18005d99f  mov     [rsp+1E0h+var_1C0], rsi
0x18005d9a4  lea     r9, aStreamCreatedW; "Stream created with handle: %p"
0x18005d9ab  mov     r8d, 61Bh; unsigned int
0x18005d9b1  mov     edx, r15d; unsigned int
0x18005d9b4  lea     rcx, [rbp+0E0h+var_F0]; this
0x18005d9b8  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18005d9bd  mov     rsi, [r14+8]
0x18005d9c1  test    rsi, rsi
0x18005d9c4  jz      short loc_18005D9E1
0x18005d9c6  mov     qword ptr [r14+8], 0
0x18005d9ce  mov     rcx, [rbx+58h]; hObject
0x18005d9d2  test    rcx, rcx
0x18005d9d5  jz      short loc_18005D9DD
0x18005d9d7  call    cs:__imp_CloseHandle
0x18005d9dd  mov     [rbx+58h], rsi
0x18005d9e1  mov     [rsp+1E0h+var_1A0], 0
0x18005d9ea  mov     rcx, [rbx+68h]; hObject
0x18005d9ee  test    rcx, rcx
0x18005d9f1  jz      short loc_18005D9F9
0x18005d9f3  call    cs:__imp_CloseHandle
0x18005d9f9  mov     [rbx+68h], rdi
0x18005d9fd  lea     rcx, [rsp+1E0h+var_1A8]
0x18005da02  call    ??1?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@UEAA@XZ; CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::~CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>(void)
0x18005da07  nop
0x18005da08  lea     rcx, [rsp+1E0h+var_198]; this
0x18005da0d  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x18005da12  nop
0x18005da13  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005da1a  mov     [rbp+0E0h+var_F0], rax
0x18005da1e  lea     rcx, [rbp+0E0h+var_F0]; this
0x18005da22  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18005da27  mov     rcx, [rbp+0E0h+var_40]
0x18005da2e  xor     rcx, rsp; StackCookie
0x18005da31  call    __security_check_cookie
0x18005da36  add     rsp, 1B8h
0x18005da3d  pop     r15
0x18005da3f  pop     r14
0x18005da41  pop     rdi
0x18005da42  pop     rsi
0x18005da43  pop     rbx
0x18005da44  pop     rbp
0x18005da45  retn
0x18005da46  call    GetLastFailureAsHRESULT
0x18005da4b  nop
0x18005da4c  mov     edx, eax; int
0x18005da4e  lea     rcx, [rbp+0E0h+var_F0]; this
0x18005da52  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005da57  lea     rcx, [rbp+0E0h+var_F0]; this
0x18005da5b  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005da60  mov     r8d, eax; char
0x18005da63  xor     r9d, r9d; unsigned __int16 *
0x18005da66  mov     edx, 60Bh; unsigned int
0x18005da6b  lea     rcx, [rbp+0E0h+var_F0]; this
0x18005da6f  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005da75  mov     edx, 80070057h; int
0x18005da7a  lea     rcx, [rbp+0E0h+var_F0]; this
0x18005da7e  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005da83  lea     rcx, [rbp+0E0h+var_F0]; this
0x18005da87  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005da8c  mov     r8d, eax; char
0x18005da8f  xor     r9d, r9d; unsigned __int16 *
0x18005da92  mov     edx, 607h; unsigned int
0x18005da97  lea     rcx, [rbp+0E0h+var_F0]; this
0x18005da9b  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
