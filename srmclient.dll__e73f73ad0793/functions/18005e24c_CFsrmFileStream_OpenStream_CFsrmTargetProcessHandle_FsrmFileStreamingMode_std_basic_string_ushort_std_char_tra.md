# CFsrmFileStream::OpenStream(CFsrmTargetProcessHandle *,_FsrmFileStreamingMode,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,bool,void * *,void * *)

- ea: `0x18005e24c`
- end: `0x18005e5a0`
- name: `?OpenStream@CFsrmFileStream@@QEAAXPEAVCFsrmTargetProcessHandle@@W4_FsrmFileStreamingMode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N3PEAPEAX4@Z`
- size: `852`
- prototype: `__int64 __usercall@<rax>(CFsrmFileStream *this@<rcx>, char, int, void **, void **)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008ef58`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000af10`
- `0x18000ed14`
- `0x18005ada0`
- `0x18005af00`
- `0x18005b128`
- `0x18005d194`
- `0x18005d6fc`
- `0x18005e24c`
- `0x18005e5a8`
- `0x18005ea5c`
- `0x18006febc`
- `0x1800700b8`
- `0x180072a80`
- `0x180073a80`
- `0x180073f54`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18005e38d`
- `KERNEL32!GetCurrentProcess` at `0x18005e3d0`
- `KERNEL32!GetCurrentProcess` at `0x18005e38d`
- `KERNEL32!GetCurrentProcess` at `0x18005e3d0`
- `KERNEL32!SetThreadpoolWait` at `0x18005e41f`
- `KERNEL32!SetThreadpoolWait` at `0x18005e41f`

## string_xrefs

- `0x18005e2a8`: `CFsrmFileStream::OpenStream`
- `0x18005e29c`: `base\fs\fsrm\service\stream\streamlib.cpp`
- `0x18005e4f5`: `Unknown access mode %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CFsrmFileStream::OpenStream(
        CFsrmFileStream *this,
        __int64 a2,
        int a3,
        __int64 a4,
        unsigned __int8 a5,
        int a6,
        void **a7,
        void **a8)
{
  CFsrmFileStream *v10; // rdi
  __int64 v11; // rax
  HANDLE v12; // rax
  __int64 v13; // rax
  HANDLE CurrentProcess; // rax
  char v15; // al
  char Hr; // al
  int v17; // eax
  char v18; // al
  int v20; // [rsp+48h] [rbp-1B0h] BYREF
  _QWORD *v21; // [rsp+50h] [rbp-1A8h]
  _com_error *v22; // [rsp+58h] [rbp-1A0h] BYREF
  const exception *v23; // [rsp+60h] [rbp-198h] BYREF
  _QWORD v24[3]; // [rsp+68h] [rbp-190h] BYREF
  int v25; // [rsp+80h] [rbp-178h]
  int v26; // [rsp+84h] [rbp-174h]
  int v27; // [rsp+88h] [rbp-170h]
  _BYTE v28[96]; // [rsp+90h] [rbp-168h] BYREF
  int v29; // [rsp+F0h] [rbp-108h]
  void **v30; // [rsp+100h] [rbp-F8h] BYREF
  int v31; // [rsp+108h] [rbp-F0h]
  unsigned int v32; // [rsp+12Ch] [rbp-CCh]

  v10 = this;
  v21 = v24;
  v24[0] = L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp";
  v24[1] = L"CFsrmFileStream::OpenStream";
  v24[2] = L"STREAMLC";
  v25 = 80;
  v26 = 17;
  v27 = 255;
  v29 = 0x1000000;
  memset_0(v28, 0, sizeof(v28));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v30, (const struct CSrmDebugInfo *)v24, 0);
  *a7 = (void *)-1LL;
  *a8 = 0;
  if ( !a2 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v30, -2147024809);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v30);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v30, 0x57u, Hr, 0);
  }
  v31 = 0;
  if ( *((_BYTE *)v10 + 96) )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v30, -2147200234);
    v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v30);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v30, 0x58u, v15, 0);
  }
  v31 = 0;
  *((_QWORD *)v10 + 33) = a2;
  *(_DWORD *)v10 = a3;
  std::wstring::assign((char *)v10 + 8);
  try
  {
    if ( a3 == 1 )
    {
      v13 = *((_QWORD *)v10 + 33);
      if ( *(_DWORD *)(v13 + 20) )
        CurrentProcess = GetCurrentProcess();
      else
        CurrentProcess = *(HANDLE *)(v13 + 8);
      CFsrmDuplicatedAutoHandle::AttachToTargetProcess((CFsrmFileStream *)((char *)v10 + 120), CurrentProcess);
      CFsrmFileStream::OpenStreamForRead((struct _OVERLAPPED *)v10, a5);
      CFsrmFileStream::GetReadStreamForTarget(v10, a7, a8);
      if ( a5 )
        SetThreadpoolWait(*((PTP_WAIT *)v10 + 19), *((HANDLE *)v10 + 18), 0);
    }
    else
    {
      if ( a3 != 2 )
      {
        CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v30, 0x8Cu, 0x82u, L"Unknown access mode %d", a3);
        v31 = -2147024809;
        v17 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v30);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v30, v17);
        v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v30);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v30, 0x83u, v18, 0);
      }
      v11 = *((_QWORD *)v10 + 33);
      if ( *(_DWORD *)(v11 + 20) )
        v12 = GetCurrentProcess();
      else
        v12 = *(HANDLE *)(v11 + 8);
      CFsrmDuplicatedAutoHandle::AttachToTargetProcess((CFsrmFileStream *)((char *)v10 + 248), v12);
      CFsrmFileStream::OpenStreamForWrite(v10);
      CFsrmFileStream::GetWriteStreamForTarget(v10, a7);
    }
    *((_BYTE *)v10 + 96) = 1;
  }
  catch ( long v20 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v30,
      v20,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmFileStream::OpenStream",
      0x88u,
      v32);
    v10 = this;
  }
  catch ( _com_error *v22 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v30,
      v22,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmFileStream::OpenStream",
      0x88u,
      v32);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v30,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmFileStream::OpenStream",
      0x88u,
      v32);
    v10 = this;
  }
  catch ( const exception *v23 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v30,
      v23,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmFileStream::OpenStream",
      0x88u,
      v32);
  }
  if ( v31 < 0 )
  {
    CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close((char *)v10 + 104);
    CFsrmDuplicatedAutoHandle::CloseTargetHandle((CFsrmFileStream *)((char *)v10 + 120));
    CFsrmFileStream::CSrmOplockHandle::Cleanup((CFsrmFileStream *)((char *)v10 + 104));
    CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close((char *)v10 + 232);
    CFsrmDuplicatedAutoHandle::CloseTargetHandle((CFsrmFileStream *)((char *)v10 + 248));
    CSrmFunctionTracer::ReThrow((CSrmFunctionTracer *)&v30);
  }
  v30 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v30);
}

```

## disassembly

```asm
0x18005e24c  push    rbx
0x18005e24e  push    rsi
0x18005e24f  push    rdi
0x18005e250  push    r12
0x18005e252  push    r13
0x18005e254  push    r14
0x18005e256  push    r15
0x18005e258  sub     rsp, 1C0h
0x18005e25f  mov     rax, cs:__security_cookie
0x18005e266  xor     rax, rsp
0x18005e269  mov     [rsp+1F8h+var_48], rax
0x18005e271  mov     r12, r9
0x18005e274  mov     esi, r8d
0x18005e277  mov     r15, rdx
0x18005e27a  mov     rdi, rcx
0x18005e27d  mov     [rsp+1F8h+var_1B8], rcx
0x18005e282  mov     r14, [rsp+1F8h+arg_30]
0x18005e28a  mov     r13, [rsp+1F8h+arg_38]
0x18005e292  lea     rax, [rsp+1F8h+var_190]
0x18005e297  mov     [rsp+1F8h+var_1A8], rax
0x18005e29c  lea     rax, aBaseFsFsrmServ_12; "base\\fs\\fsrm\\service\\stream\\stream"...
0x18005e2a3  mov     [rsp+1F8h+var_190], rax
0x18005e2a8  lea     rax, aCfsrmfilestrea_7; "CFsrmFileStream::OpenStream"
0x18005e2af  mov     [rsp+1F8h+var_188], rax
0x18005e2b4  lea     rax, aStreamlc; "STREAMLC"
0x18005e2bb  mov     [rsp+1F8h+var_180], rax
0x18005e2c0  mov     [rsp+1F8h+var_178], 50h ; 'P'
0x18005e2cb  mov     [rsp+1F8h+var_174], 11h
0x18005e2d6  mov     [rsp+1F8h+var_170], 0FFh
0x18005e2e1  xor     ebx, ebx
0x18005e2e3  mov     [rsp+1F8h+var_108], 1000000h
0x18005e2ee  xor     edx, edx; Val
0x18005e2f0  lea     r8d, [rbx+60h]; Size
0x18005e2f4  lea     rcx, [rsp+1F8h+var_168]; void *
0x18005e2fc  call    memset_0
0x18005e301  nop
0x18005e302  xor     r8d, r8d
0x18005e305  lea     rdx, [rsp+1F8h+var_190]
0x18005e30a  lea     rcx, [rsp+1F8h+var_F8]
0x18005e312  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005e317  nop
0x18005e318  or      r9, 0FFFFFFFFFFFFFFFFh
0x18005e31c  mov     [r14], r9
0x18005e31f  mov     [r13+0], rbx
0x18005e323  mov     eax, [rsp+1F8h+var_F0]
0x18005e32a  mov     [rsp+1F8h+var_F0], eax
0x18005e331  test    r15, r15
0x18005e334  jz      loc_18005E4BB
0x18005e33a  mov     [rsp+1F8h+var_F0], ebx
0x18005e341  mov     [rsp+1F8h+var_F0], ebx
0x18005e348  cmp     [rdi+60h], bl
0x18005e34b  jnz     loc_18005E484
0x18005e351  mov     [rsp+1F8h+var_F0], ebx
0x18005e358  mov     [rdi+108h], r15
0x18005e35f  mov     [rdi], esi
0x18005e361  lea     rcx, [rdi+8]; void *
0x18005e365  xor     r8d, r8d
0x18005e368  mov     rdx, r12
0x18005e36b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18005e370  nop
0x18005e371  mov     ecx, esi
0x18005e373  sub     ecx, 1
0x18005e376  jz      short loc_18005E3C4
0x18005e378  cmp     ecx, 1
0x18005e37b  jnz     loc_18005E4F1
0x18005e381  mov     rax, [rdi+108h]
0x18005e388  cmp     [rax+14h], ebx
0x18005e38b  jz      short loc_18005E395
0x18005e38d  call    cs:__imp_GetCurrentProcess
0x18005e393  jmp     short loc_18005E399
0x18005e395  mov     rax, [rax+8]
0x18005e399  mov     rdx, rax; void *
0x18005e39c  lea     rcx, [rdi+0F8h]; this
0x18005e3a3  call    ?AttachToTargetProcess@CFsrmDuplicatedAutoHandle@@QEAAXPEAX@Z; CFsrmDuplicatedAutoHandle::AttachToTargetProcess(void *)
0x18005e3a8  mov     dl, [rsp+1F8h+arg_20]; bool
0x18005e3af  mov     rcx, rdi; this
0x18005e3b2  call    ?OpenStreamForWrite@CFsrmFileStream@@AEAAX_N0@Z; CFsrmFileStream::OpenStreamForWrite(bool,bool)
0x18005e3b7  mov     rdx, r14; void **
0x18005e3ba  mov     rcx, rdi; this
0x18005e3bd  call    ?GetWriteStreamForTarget@CFsrmFileStream@@AEAAXPEAPEAX@Z; CFsrmFileStream::GetWriteStreamForTarget(void * *)
0x18005e3c2  jmp     short loc_18005E425
0x18005e3c4  mov     rax, [rdi+108h]
0x18005e3cb  cmp     [rax+14h], ebx
0x18005e3ce  jz      short loc_18005E3D8
0x18005e3d0  call    cs:__imp_GetCurrentProcess
0x18005e3d6  jmp     short loc_18005E3DC
0x18005e3d8  mov     rax, [rax+8]
0x18005e3dc  mov     rdx, rax; void *
0x18005e3df  lea     rcx, [rdi+78h]; this
0x18005e3e3  call    ?AttachToTargetProcess@CFsrmDuplicatedAutoHandle@@QEAAXPEAX@Z; CFsrmDuplicatedAutoHandle::AttachToTargetProcess(void *)
0x18005e3e8  mov     dl, [rsp+1F8h+arg_20]; bool
0x18005e3ef  mov     rcx, rdi; this
0x18005e3f2  call    ?OpenStreamForRead@CFsrmFileStream@@AEAAX_N@Z; CFsrmFileStream::OpenStreamForRead(bool)
0x18005e3f7  mov     r8, r13; void **
0x18005e3fa  mov     rdx, r14; void **
0x18005e3fd  mov     rcx, rdi; this
0x18005e400  call    ?GetReadStreamForTarget@CFsrmFileStream@@AEAAXPEAPEAX0@Z; CFsrmFileStream::GetReadStreamForTarget(void * *,void * *)
0x18005e405  cmp     [rsp+1F8h+arg_20], bl
0x18005e40c  jz      short loc_18005E425
0x18005e40e  xor     r8d, r8d; pftTimeout
0x18005e411  mov     rdx, [rdi+90h]; h
0x18005e418  mov     rcx, [rdi+98h]; pwa
0x18005e41f  call    cs:__imp_SetThreadpoolWait
0x18005e425  mov     byte ptr [rdi+60h], 1
0x18005e429  jmp     short loc_18005E432
0x18005e42b  mov     rdi, [rsp+1F8h+var_1B8]
0x18005e430  xor     ebx, ebx
0x18005e432  cmp     [rsp+1F8h+var_F0], ebx
0x18005e439  jl      loc_18005E55F
0x18005e43f  jmp     short loc_18005E445
0x18005e441  jmp     short loc_18005E42B
0x18005e443  jmp     short loc_18005E42B
0x18005e445  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005e44c  mov     [rsp+1F8h+var_F8], rax
0x18005e454  lea     rcx, [rsp+1F8h+var_F8]; this
0x18005e45c  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18005e461  mov     rcx, [rsp+1F8h+var_48]
0x18005e469  xor     rcx, rsp; StackCookie
0x18005e46c  call    __security_check_cookie
0x18005e471  add     rsp, 1C0h
0x18005e478  pop     r15
0x18005e47a  pop     r14
0x18005e47c  pop     r13
0x18005e47e  pop     r12
0x18005e480  pop     rdi
0x18005e481  pop     rsi
0x18005e482  pop     rbx
0x18005e483  retn
0x18005e484  mov     edx, 80045316h; int
0x18005e489  lea     rcx, [rsp+1F8h+var_F8]; this
0x18005e491  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005e496  lea     rcx, [rsp+1F8h+var_F8]; this
0x18005e49e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005e4a3  mov     r8d, eax; char
0x18005e4a6  xor     r9d, r9d; unsigned __int16 *
0x18005e4a9  lea     edx, [r9+58h]; unsigned int
0x18005e4ad  lea     rcx, [rsp+1F8h+var_F8]; this
0x18005e4b5  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005e4bb  mov     edx, 80070057h; int
0x18005e4c0  lea     rcx, [rsp+1F8h+var_F8]; this
0x18005e4c8  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005e4cd  lea     rcx, [rsp+1F8h+var_F8]; this
0x18005e4d5  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005e4da  mov     r8d, eax; char
0x18005e4dd  xor     r9d, r9d; unsigned __int16 *
0x18005e4e0  lea     edx, [rbx+57h]; unsigned int
0x18005e4e3  lea     rcx, [rsp+1F8h+var_F8]; this
0x18005e4eb  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005e4f1  mov     [rsp+1F8h+var_1D8], esi
0x18005e4f5  lea     r9, aUnknownAccessM; "Unknown access mode %d"
0x18005e4fc  mov     edx, 8Ch; unsigned int
0x18005e501  lea     r8d, [rdx-0Ah]; unsigned int
0x18005e505  lea     rcx, [rsp+1F8h+var_F8]; this
0x18005e50d  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18005e512  mov     [rsp+1F8h+var_F0], 80070057h
0x18005e51d  lea     rcx, [rsp+1F8h+var_F8]; this
0x18005e525  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005e52a  mov     edx, eax; int
0x18005e52c  lea     rcx, [rsp+1F8h+var_F8]; this
0x18005e534  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005e539  lea     rcx, [rsp+1F8h+var_F8]; this
0x18005e541  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005e546  mov     r8d, eax; char
0x18005e549  xor     r9d, r9d; unsigned __int16 *
0x18005e54c  mov     edx, 83h; unsigned int
0x18005e551  lea     rcx, [rsp+1F8h+var_F8]; this
0x18005e559  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005e55f  lea     rcx, [rdi+68h]
0x18005e563  call    ?Close@?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@QEAAXXZ; CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::Close(void)
0x18005e568  lea     rcx, [rdi+78h]; this
0x18005e56c  call    ?CloseTargetHandle@CFsrmDuplicatedAutoHandle@@QEAAXXZ; CFsrmDuplicatedAutoHandle::CloseTargetHandle(void)
0x18005e571  lea     rcx, [rdi+68h]; this
0x18005e575  call    ?Cleanup@CSrmOplockHandle@CFsrmFileStream@@QEAAXXZ; CFsrmFileStream::CSrmOplockHandle::Cleanup(void)
0x18005e57a  lea     rcx, [rdi+0E8h]
0x18005e581  call    ?Close@?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@QEAAXXZ; CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::Close(void)
0x18005e586  lea     rcx, [rdi+0F8h]; this
0x18005e58d  call    ?CloseTargetHandle@CFsrmDuplicatedAutoHandle@@QEAAXXZ; CFsrmDuplicatedAutoHandle::CloseTargetHandle(void)
0x18005e592  lea     rcx, [rsp+1F8h+var_F8]; this
0x18005e59a  call    ?ReThrow@CSrmFunctionTracer@@QEAAXXZ; CSrmFunctionTracer::ReThrow(void)
```
