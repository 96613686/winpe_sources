# CFsrmFileStream::CSrmOplockHandle::Initialize(void)

- ea: `0x18005daa8`
- end: `0x18005dc74`
- name: `?Initialize@CSrmOplockHandle@CFsrmFileStream@@QEAAXXZ`
- size: `460`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18005e5a8`

## callees

- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000cde0`
- `0x18005daa8`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18005dbcb`
- `KERNEL32!CloseHandle` at `0x18005dbcb`
- `KERNEL32!CreateThreadpoolWait` at `0x18005db9e`
- `KERNEL32!CreateThreadpoolWait` at `0x18005db9e`
- `KERNEL32!CreateEventW` at `0x18005db4c`
- `KERNEL32!CreateEventW` at `0x18005db4c`

## string_xrefs

- `0x18005dada`: `base\fs\fsrm\service\inc\streamlib.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CFsrmFileStream::CSrmOplockHandle::Initialize(PVOID pv)
{
  __int64 v2; // rdx
  HANDLE EventW; // rsi
  __int64 v4; // rdx
  PTP_WAIT ThreadpoolWait; // rdi
  void *v6; // rcx
  int v7; // eax
  char v8; // al
  int LastFailureAsHRESULT; // eax
  char Hr; // al
  void **v11; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE v12; // [rsp+28h] [rbp-D8h]
  _QWORD *v13; // [rsp+30h] [rbp-D0h]
  _QWORD v14[3]; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+50h] [rbp-B0h]
  int v16; // [rsp+54h] [rbp-ACh]
  int v17; // [rsp+58h] [rbp-A8h]
  _BYTE v18[96]; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+C0h] [rbp-40h]
  void **v20; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v21; // [rsp+D8h] [rbp-28h]

  v13 = v14;
  v14[0] = L"base\\fs\\fsrm\\service\\inc\\streamlib.h";
  v14[1] = L"CFsrmFileStream::CSrmOplockHandle::Initialize";
  v14[2] = L"STREAMLH";
  v15 = 175;
  v16 = 17;
  v17 = 255;
  v19 = 0x1000000;
  memset_0(v18, 0, sizeof(v18));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v20, (const struct CSrmDebugInfo *)v14, 0);
  EventW = CreateEventW(0, 1, 0, 0);
  v11 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v12 = EventW;
  if ( !EventW )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v21, v2);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v20, LastFailureAsHRESULT);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v20);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v20, 0xB5u, Hr, 0, v11, 0, v13);
  }
  v21 = 0;
  ThreadpoolWait = CreateThreadpoolWait(CFsrmFileStream::OplockWaitCallback, pv, 0);
  if ( !ThreadpoolWait )
  {
    v7 = GetLastFailureAsHRESULT(v21, v4);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v20, v7);
    v8 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v20);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v20, 0xB8u, v8, 0, v11, v12, v13);
  }
  v21 = 0;
  v12 = 0;
  v6 = (void *)*((_QWORD *)pv + 5);
  if ( v6 )
    CloseHandle(v6);
  *((_QWORD *)pv + 5) = EventW;
  *((_QWORD *)pv + 6) = ThreadpoolWait;
  *((_QWORD *)pv + 10) = EventW;
  CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(&v11);
  v20 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v20);
}

```

## disassembly

```asm
0x18005daa8  push    rbp
0x18005daaa  push    rbx
0x18005daab  push    rsi
0x18005daac  push    rdi
0x18005daad  lea     rbp, [rsp-98h]
0x18005dab5  sub     rsp, 198h
0x18005dabc  mov     rax, cs:__security_cookie
0x18005dac3  xor     rax, rsp
0x18005dac6  mov     [rbp+0B0h+var_30], rax
0x18005dacd  mov     rbx, rcx
0x18005dad0  lea     rax, [rsp+1B0h+var_178]
0x18005dad5  mov     [rsp+1B0h+var_180], rax
0x18005dada  lea     rax, aBaseFsFsrmServ_32; "base\\fs\\fsrm\\service\\inc\\streamlib"...
0x18005dae1  mov     [rsp+1B0h+var_178], rax
0x18005dae6  lea     rax, aCfsrmfilestrea_10; "CFsrmFileStream::CSrmOplockHandle::Init"...
0x18005daed  mov     [rsp+1B0h+var_170], rax
0x18005daf2  lea     rax, aStreamlh; "STREAMLH"
0x18005daf9  mov     [rsp+1B0h+var_168], rax
0x18005dafe  mov     [rsp+1B0h+var_160], 0AFh
0x18005db06  mov     [rsp+1B0h+var_15C], 11h
0x18005db0e  mov     [rsp+1B0h+var_158], 0FFh
0x18005db16  mov     [rbp+0B0h+var_F0], 1000000h
0x18005db1d  xor     edx, edx; Val
0x18005db1f  lea     r8d, [rdx+60h]; Size
0x18005db23  lea     rcx, [rsp+1B0h+var_150]; void *
0x18005db28  call    memset_0
0x18005db2d  nop
0x18005db2e  xor     r8d, r8d
0x18005db31  lea     rdx, [rsp+1B0h+var_178]
0x18005db36  lea     rcx, [rbp+0B0h+var_E0]
0x18005db3a  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005db3f  nop
0x18005db40  xor     r9d, r9d; lpName
0x18005db43  xor     r8d, r8d; bInitialState
0x18005db46  lea     edx, [r9+1]; bManualReset
0x18005db4a  xor     ecx, ecx; lpEventAttributes
0x18005db4c  call    cs:__imp_CreateEventW
0x18005db52  mov     rsi, rax
0x18005db55  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18005db5c  mov     [rsp+1B0h+var_190], rax
0x18005db61  mov     [rsp+1B0h+var_188], 0
0x18005db6a  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18005db71  mov     [rsp+1B0h+var_190], rax
0x18005db76  mov     [rsp+1B0h+var_188], rsi
0x18005db7b  mov     ecx, [rbp+0B0h+var_D8]
0x18005db7e  mov     [rbp+0B0h+var_D8], ecx
0x18005db81  test    rsi, rsi
0x18005db84  jz      loc_18005DC46
0x18005db8a  mov     [rbp+0B0h+var_D8], 0
0x18005db91  xor     r8d, r8d; pcbe
0x18005db94  mov     rdx, rbx; pv
0x18005db97  lea     rcx, ?OplockWaitCallback@CFsrmFileStream@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18005db9e  call    cs:__imp_CreateThreadpoolWait
0x18005dba4  mov     rdi, rax
0x18005dba7  mov     ecx, [rbp+0B0h+var_D8]
0x18005dbaa  mov     [rbp+0B0h+var_D8], ecx
0x18005dbad  test    rax, rax
0x18005dbb0  jz      short loc_18005DC17
0x18005dbb2  mov     [rbp+0B0h+var_D8], 0
0x18005dbb9  mov     [rsp+1B0h+var_188], 0
0x18005dbc2  mov     rcx, [rbx+28h]; hObject
0x18005dbc6  test    rcx, rcx
0x18005dbc9  jz      short loc_18005DBD1
0x18005dbcb  call    cs:__imp_CloseHandle
0x18005dbd1  mov     [rbx+28h], rsi
0x18005dbd5  mov     [rbx+30h], rdi
0x18005dbd9  mov     [rbx+50h], rsi
0x18005dbdd  lea     rcx, [rsp+1B0h+var_190]
0x18005dbe2  call    ??1?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@UEAA@XZ; CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::~CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>(void)
0x18005dbe7  nop
0x18005dbe8  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005dbef  mov     [rbp+0B0h+var_E0], rax
0x18005dbf3  lea     rcx, [rbp+0B0h+var_E0]; this
0x18005dbf7  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18005dbfc  mov     rcx, [rbp+0B0h+var_30]
0x18005dc03  xor     rcx, rsp; StackCookie
0x18005dc06  call    __security_check_cookie
0x18005dc0b  add     rsp, 198h
0x18005dc12  pop     rdi
0x18005dc13  pop     rsi
0x18005dc14  pop     rbx
0x18005dc15  pop     rbp
0x18005dc16  retn
0x18005dc17  call    GetLastFailureAsHRESULT
0x18005dc1c  nop
0x18005dc1d  mov     edx, eax; int
0x18005dc1f  lea     rcx, [rbp+0B0h+var_E0]; this
0x18005dc23  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005dc28  lea     rcx, [rbp+0B0h+var_E0]; this
0x18005dc2c  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005dc31  mov     r8d, eax; char
0x18005dc34  xor     r9d, r9d; unsigned __int16 *
0x18005dc37  mov     edx, 0B8h; unsigned int
0x18005dc3c  lea     rcx, [rbp+0B0h+var_E0]; this
0x18005dc40  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005dc46  call    GetLastFailureAsHRESULT
0x18005dc4b  mov     edx, eax; int
0x18005dc4d  lea     rcx, [rbp+0B0h+var_E0]; this
0x18005dc51  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005dc56  lea     rcx, [rbp+0B0h+var_E0]; this
0x18005dc5a  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005dc5f  mov     r8d, eax; char
0x18005dc62  xor     r9d, r9d; unsigned __int16 *
0x18005dc65  mov     edx, 0B5h; unsigned int
0x18005dc6a  lea     rcx, [rbp+0B0h+var_E0]; this
0x18005dc6e  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
