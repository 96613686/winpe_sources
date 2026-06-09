# SAL2::CSALFileIoMgr::CSALFileIoMgr(IUnknown *,long *)

- ea: `0x180087c14`
- end: `0x180087db6`
- name: `??0CSALFileIoMgr@SAL2@@AEAA@PEAUIUnknown@@PEAJ@Z`
- size: `418`
- prototype: `__int64 __fastcall(SAL2::CSALFileIoMgr *__hidden this, struct IUnknown *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180088c20`

## callees

- `0x1800089b8`
- `0x1800620f8`
- `0x180062558`
- `0x1800627f0`
- `0x180087c14`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x180087ceb`
- `KERNEL32!GetSystemInfo` at `0x180087ceb`
- `KERNEL32!CreateEventW` at `0x180087d4e`
- `KERNEL32!CreateEventW` at `0x180087d4e`
- `KERNEL32!GetLastError` at `0x180087d60`
- `KERNEL32!GetLastError` at `0x180087d60`
- `KERNEL32!InitializeSListHead` at `0x180087cb1`
- `KERNEL32!InitializeSListHead` at `0x180087cb1`

## pseudocode

```c
SAL2::CSALFileIoMgr *__fastcall SAL2::CSALFileIoMgr::CSALFileIoMgr(
        SAL2::CSALFileIoMgr *this,
        struct IUnknown *a2,
        int *a3)
{
  LPVOID *v3; // r15
  int v7; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+90h] [rbp+30h] BYREF
  unsigned __int64 v13; // [rsp+A0h] [rbp+40h] BYREF

  v3 = (LPVOID *)((char *)this + 8);
  SBEBasicTracers::SBEBasicTracers((SAL2::CSALFileIoMgr *)((char *)this + 8));
  *v3 = &SAL2::CSALFileIoMgr::`vftable'{for `SBEBasicTracers'};
  *(_QWORD *)this = &SAL2::CSALFileIoMgr::`vftable'{for `SAL2::ISALIoMgr'};
  *((_DWORD *)this + 68) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 72) = 0;
  *((_DWORD *)this + 73) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = -1;
  *((_QWORD *)this + 39) = 0;
  *((_DWORD *)this + 80) = 0;
  *((_DWORD *)this + 81) = 0;
  *((_DWORD *)this + 82) = 0;
  *((_QWORD *)this + 42) = 0;
  InitializeSListHead((PSLIST_HEADER)this + 22);
  v7 = *a3;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  v13 = 0;
  v12 = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( v7 >= 0 )
  {
    GetSystemInfo(&SystemInfo);
    *((_DWORD *)this + 75) = SystemInfo.dwPageSize;
    if ( a2 )
    {
      ((void (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
        a2,
        &IID_IDVRContextInfo,
        &v12);
      if ( v12 )
        (*(void (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v12 + 24LL))(v12, &v13);
    }
    SBEBasicTracers::EtwInitialize(v3, &stru_1800CAE90, v13);
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 42) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      SBEBasicTracers::EtwTraceError(
        (SAL2::CSALFileIoMgr *)((char *)this + 56),
        "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
        0x191u,
        v7);
    }
  }
  EhEtw::TPtr<IEhTraceSpan>::Release(&v12);
  *a3 = v7;
  return this;
}

```

## disassembly

```asm
0x180087c14  mov     [rsp-28h+arg_8], rbx
0x180087c19  mov     [rsp-28h+arg_18], rsi
0x180087c1e  push    rbp
0x180087c1f  push    rdi
0x180087c20  push    r12
0x180087c22  push    r14
0x180087c24  push    r15
0x180087c26  mov     rbp, rsp
0x180087c29  sub     rsp, 60h
0x180087c2d  lea     r15, [rcx+8]
0x180087c31  mov     rdi, rcx
0x180087c34  mov     rcx, r15; this
0x180087c37  mov     r14, r8
0x180087c3a  mov     rsi, rdx
0x180087c3d  call    ??0SBEBasicTracers@@QEAA@XZ; SBEBasicTracers::SBEBasicTracers(void)
0x180087c42  xor     r12d, r12d
0x180087c45  lea     rax, ??_7CSALFileIoMgr@SAL2@@6BSBEBasicTracers@@@; const SAL2::CSALFileIoMgr::`vftable'{for `SBEBasicTracers'}
0x180087c4c  mov     [r15], rax
0x180087c4f  lea     rcx, ??_7CSALFileIoMgr@SAL2@@6BISALIoMgr@1@@; const SAL2::CSALFileIoMgr::`vftable'{for `SAL2::ISALIoMgr'}
0x180087c56  mov     [rdi], rcx
0x180087c59  lea     rcx, [rdi+160h]; ListHead
0x180087c60  mov     [rdi+110h], r12d
0x180087c67  mov     [rdi+118h], r12
0x180087c6e  mov     [rdi+120h], r12d
0x180087c75  mov     [rdi+124h], r12d
0x180087c7c  mov     [rdi+128h], r12
0x180087c83  mov     qword ptr [rdi+130h], 0FFFFFFFFFFFFFFFFh
0x180087c8e  mov     [rdi+138h], r12
0x180087c95  mov     [rdi+140h], r12d
0x180087c9c  mov     [rdi+144h], r12d
0x180087ca3  mov     [rdi+148h], r12d
0x180087caa  mov     [rdi+150h], r12
0x180087cb1  call    cs:__imp_InitializeSListHead
0x180087cb7  mov     ebx, [r14]
0x180087cba  xorps   xmm0, xmm0
0x180087cbd  mov     [rdi+170h], r12
0x180087cc4  mov     [rdi+178h], r12
0x180087ccb  mov     [rbp+arg_10], r12
0x180087ccf  mov     [rbp+arg_0], r12
0x180087cd3  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180087cd7  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180087cdb  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180087cdf  test    ebx, ebx
0x180087ce1  js      loc_180087D8E
0x180087ce7  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180087ceb  call    cs:__imp_GetSystemInfo
0x180087cf1  mov     eax, [rbp+SystemInfo.dwPageSize]
0x180087cf4  mov     [rdi+12Ch], eax
0x180087cfa  test    rsi, rsi
0x180087cfd  jz      short loc_180087D31
0x180087cff  mov     rax, [rsi]
0x180087d02  lea     r8, [rbp+arg_0]
0x180087d06  lea     rdx, IID_IDVRContextInfo
0x180087d0d  mov     rcx, rsi
0x180087d10  mov     rax, [rax]
0x180087d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087d18  mov     rcx, [rbp+arg_0]
0x180087d1c  test    rcx, rcx
0x180087d1f  jz      short loc_180087D31
0x180087d21  mov     rax, [rcx]
0x180087d24  lea     rdx, [rbp+arg_10]
0x180087d28  mov     rax, [rax+18h]
0x180087d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087d31  mov     r8, [rbp+arg_10]; unsigned __int64
0x180087d35  lea     rdx, stru_1800CAE90; struct _GUID *
0x180087d3c  mov     rcx, r15; this
0x180087d3f  call    ?EtwInitialize@SBEBasicTracers@@QEAAXAEBU_GUID@@_K11@Z; SBEBasicTracers::EtwInitialize(_GUID const &,unsigned __int64,unsigned __int64,unsigned __int64)
0x180087d44  xor     r9d, r9d; lpName
0x180087d47  xor     r8d, r8d; bInitialState
0x180087d4a  xor     edx, edx; bManualReset
0x180087d4c  xor     ecx, ecx; lpEventAttributes
0x180087d4e  call    cs:__imp_CreateEventW
0x180087d54  mov     [rdi+150h], rax
0x180087d5b  test    rax, rax
0x180087d5e  jnz     short loc_180087D8E
0x180087d60  call    cs:__imp_GetLastError
0x180087d66  mov     ebx, eax
0x180087d68  test    eax, eax
0x180087d6a  jle     short loc_180087D75
0x180087d6c  movzx   ebx, ax
0x180087d6f  or      ebx, 80070000h
0x180087d75  lea     rcx, [rdi+38h]; struct CEhEventTracer *
0x180087d79  mov     r9d, ebx; unsigned int
0x180087d7c  mov     r8d, 191h; unsigned int
0x180087d82  lea     rdx, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180087d89  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x180087d8e  lea     rcx, [rbp+arg_0]
0x180087d92  call    ?Release@?$TPtr@UIEhTraceSpan@@@EhEtw@@QEAAXXZ; EhEtw::TPtr<IEhTraceSpan>::Release(void)
0x180087d97  lea     r11, [rsp+60h+var_s0]
0x180087d9c  mov     [r14], ebx
0x180087d9f  mov     rbx, [r11+38h]
0x180087da3  mov     rax, rdi
0x180087da6  mov     rsi, [r11+48h]
0x180087daa  mov     rsp, r11
0x180087dad  pop     r15
0x180087daf  pop     r14
0x180087db1  pop     r12
0x180087db3  pop     rdi
0x180087db4  pop     rbp
0x180087db5  retn
```
