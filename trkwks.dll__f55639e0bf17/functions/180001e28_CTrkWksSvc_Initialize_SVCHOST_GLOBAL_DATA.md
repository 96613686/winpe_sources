# CTrkWksSvc::Initialize(_SVCHOST_GLOBAL_DATA *)

- ea: `0x180001e28`
- end: `0x18000202f`
- name: `?Initialize@CTrkWksSvc@@QEAAXPEAU_SVCHOST_GLOBAL_DATA@@@Z`
- size: `519`
- prototype: `void __fastcall(CTrkWksSvc *__hidden this, struct _SVCHOST_GLOBAL_DATA *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180001d4c`

## callees

- `0x180001940`
- `0x180001c1c`
- `0x180001cb8`
- `0x180001e28`
- `0x180002038`
- `0x1800020a4`
- `0x1800028f0`
- `0x18000a618`
- `0x18000b520`
- `0x18000cef8`
- `0x18000d020`
- `0x18000f704`
- `0x180010fca`
- `0x180011000`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x180001ee8`
- `ntdll!RtlSetThreadErrorMode` at `0x180001ee8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180001f21`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180001fff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180001f21`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180001fff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001f9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001f9c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001f8e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001f8e`

## pseudocode

```c
void __fastcall CTrkWksSvc::Initialize(CTrkWksSvc *this, struct _SVCHOST_GLOBAL_DATA *a2)
{
  CEntropyRecorder *v3; // r14
  int i; // edi
  CTrkConfiguration *v5; // rcx
  const unsigned __int16 *v6; // rdx
  __int64 v7; // rax
  HANDLE Thread; // rax
  unsigned int v9; // r9d

  g_ptrkwks = this;
  *((_DWORD *)this + 92) |= 1u;
  v3 = (CTrkWksSvc *)((char *)this + 48);
  *((_DWORD *)this + 12) = 1;
  *((_QWORD *)this + 12) = 0;
  memset_0((char *)this + 104, 0, 0x100u);
  CEntropyRecorder::Put(v3);
  *((_DWORD *)this + 142) |= 1u;
  *((_DWORD *)this + 143) = 37;
  CTrkConfiguration::Initialize((CTrkWksSvc *)((char *)this + 536));
  for ( i = 0; ; ++i )
  {
    v5 = (CTrkWksSvc *)((char *)this + 536);
    if ( i > 36 )
      break;
    CTrkConfiguration::Read(
      v5,
      (const unsigned __int16 *)*(&CTrkWksConfiguration::_Parameters + 3 * i),
      (unsigned int *)&qword_18001B008[3 * i] + 1,
      *((_DWORD *)&CTrkWksConfiguration::_Parameters + 6 * i + 2));
  }
  CTrkWksConfiguration::UnInitialize(v5);
  RtlSetThreadErrorMode(0x10u, 0);
  *((_QWORD *)this + 47) = 0;
  CSvcCtrlInterface::Initialize((CTrkWksSvc *)((char *)this + 496), v6, this);
  if ( *((_DWORD *)this + 143) <= 0x22u )
  {
    RaiseException(0x80004005, 0, 0, 0);
    __debugbreak();
  }
  v7 = (unsigned int)dword_18001B33C;
  *((_DWORD *)this + 260) = 1;
  *((_DWORD *)this + 272) = 0;
  *((_QWORD *)this + 297) = 0;
  *((_QWORD *)this + 297) = 10000000 * v7;
  CEntropyRecorder::Put(v3);
  CVerifyAuthentication::Initialize();
  _InterlockedIncrement((volatile signed __int32 *)this + 90);
  Thread = CreateThread(0, 0, CTrkWksSvc::s_ExecuteAsyncInit, this, 0, 0);
  if ( !Thread )
  {
    CTrkWksSvc::Release(this);
    TrkRaiseLastError();
  }
  CloseHandle(Thread);
  CSvcCtrlInterface::SetServiceStatus((CTrkWksSvc *)((char *)this + 496), 4u, 5u, v9);
}

```

## disassembly

```asm
0x180001e28  mov     [rsp+arg_8], rbx
0x180001e2d  mov     [rsp+arg_10], rsi
0x180001e32  push    rdi
0x180001e33  push    r13
0x180001e35  push    r14
0x180001e37  sub     rsp, 260h
0x180001e3e  mov     rax, cs:__security_cookie
0x180001e45  xor     rax, rsp
0x180001e48  mov     [rsp+278h+var_28], rax
0x180001e50  mov     rbx, rcx
0x180001e53  mov     cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA, rcx; CTrkWksSvc * g_ptrkwks
0x180001e5a  or      dword ptr [rcx+170h], 1
0x180001e61  lea     r14, [rcx+30h]
0x180001e65  mov     dword ptr [r14], 1
0x180001e6c  mov     qword ptr [r14+30h], 0
0x180001e74  lea     rcx, [r14+38h]; void *
0x180001e78  xor     edx, edx; Val
0x180001e7a  mov     r8d, 100h; Size
0x180001e80  call    memset_0
0x180001e85  mov     rcx, r14; this
0x180001e88  call    ?Put@CEntropyRecorder@@QEAAXXZ; CEntropyRecorder::Put(void)
0x180001e8d  lea     rsi, [rbx+218h]
0x180001e94  or      dword ptr [rsi+20h], 1
0x180001e98  mov     dword ptr [rsi+24h], 25h ; '%'
0x180001e9f  mov     rcx, rsi; this
0x180001ea2  call    ?Initialize@CTrkConfiguration@@QEAAXXZ; CTrkConfiguration::Initialize(void)
0x180001ea7  xor     edi, edi
0x180001ea9  lea     r13, ?_Parameters@CTrkWksConfiguration@@0PAUSTrkConfigRecord@@A; STrkConfigRecord near * CTrkWksConfiguration::_Parameters
0x180001eb0  mov     [rsp+278h+var_248], edi
0x180001eb4  mov     rcx, rsi; this
0x180001eb7  cmp     edi, 24h ; '$'
0x180001eba  jg      short loc_180001EDE
0x180001ebc  movsxd  rax, edi
0x180001ebf  lea     rdx, [rax+rax*2]
0x180001ec3  lea     r8, [r13+0Ch]
0x180001ec7  lea     r8, [r8+rdx*8]; unsigned int *
0x180001ecb  mov     r9d, [r13+rdx*8+8]; unsigned int
0x180001ed0  mov     rdx, [r13+rdx*8+0]; unsigned __int16 *
0x180001ed5  call    ?Read@CTrkConfiguration@@IEBAXPEBGPEAKK@Z; CTrkConfiguration::Read(ushort const *,ulong *,ulong)
0x180001eda  inc     edi
0x180001edc  jmp     short loc_180001EB0
0x180001ede  call    ?UnInitialize@CTrkWksConfiguration@@QEAAXXZ; CTrkWksConfiguration::UnInitialize(void)
0x180001ee3  xor     edx, edx; OldMode
0x180001ee5  lea     ecx, [rdx+10h]; NewMode
0x180001ee8  call    cs:__imp_RtlSetThreadErrorMode
0x180001eee  mov     qword ptr [rbx+178h], 0
0x180001ef9  lea     rdi, [rbx+1F0h]
0x180001f00  mov     r8, rbx; struct IServiceHandler *
0x180001f03  mov     rcx, rdi; this
0x180001f06  call    ?Initialize@CSvcCtrlInterface@@QEAAXPEBGPEAVIServiceHandler@@@Z; CSvcCtrlInterface::Initialize(ushort const *,IServiceHandler *)
0x180001f0b  cmp     dword ptr [rbx+23Ch], 22h ; '"'
0x180001f12  ja      short loc_180001F28
0x180001f14  xor     r9d, r9d; lpArguments
0x180001f17  xor     r8d, r8d; nNumberOfArguments
0x180001f1a  xor     edx, edx; dwExceptionFlags
0x180001f1c  mov     ecx, 80004005h; dwExceptionCode
0x180001f21  call    cs:__imp_RaiseException
0x180001f27  int     3; Trap to Debugger
0x180001f28  mov     eax, cs:dword_18001B33C
0x180001f2e  mov     dword ptr [rbx+410h], 1
0x180001f38  mov     dword ptr [rbx+440h], 0
0x180001f42  mov     qword ptr [rbx+948h], 0
0x180001f4d  imul    rcx, rax, 989680h
0x180001f54  mov     [rbx+948h], rcx
0x180001f5b  mov     rcx, r14; this
0x180001f5e  call    ?Put@CEntropyRecorder@@QEAAXXZ; CEntropyRecorder::Put(void)
0x180001f63  call    ?Initialize@CVerifyAuthentication@@SAXXZ; CVerifyAuthentication::Initialize(void)
0x180001f68  lock inc dword ptr [rbx+168h]
0x180001f6f  mov     [rsp+278h+lpThreadId], 0; lpThreadId
0x180001f78  mov     [rsp+278h+dwCreationFlags], 0; dwCreationFlags
0x180001f80  mov     r9, rbx; lpParameter
0x180001f83  lea     r8, ?s_ExecuteAsyncInit@CTrkWksSvc@@CAKPEAX@Z; lpStartAddress
0x180001f8a  xor     edx, edx; dwStackSize
0x180001f8c  xor     ecx, ecx; lpThreadAttributes
0x180001f8e  call    cs:__imp_CreateThread
0x180001f94  test    rax, rax
0x180001f97  jz      short loc_180001FB5
0x180001f99  mov     rcx, rax; hObject
0x180001f9c  call    cs:__imp_CloseHandle
0x180001fa2  mov     edx, 4; unsigned int
0x180001fa7  lea     r8d, [rdx+1]; unsigned int
0x180001fab  mov     rcx, rdi; this
0x180001fae  call    ?SetServiceStatus@CSvcCtrlInterface@@QEAAXKKK@Z; CSvcCtrlInterface::SetServiceStatus(ulong,ulong,ulong)
0x180001fb3  jmp     short loc_180002006
0x180001fb5  mov     rcx, rbx; this
0x180001fb8  call    ?Release@CTrkWksSvc@@QEAAKXZ; CTrkWksSvc::Release(void)
0x180001fbd  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x180001fc3  mov     ebx, eax
0x180001fc5  mov     r9d, eax
0x180001fc8  lea     r8, a08x; "%08x"
0x180001fcf  mov     edx, 104h; unsigned __int64
0x180001fd4  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180001fd9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001fde  mov     edx, 1; unsigned __int16
0x180001fe3  xor     r9d, r9d
0x180001fe6  lea     r8, [rsp+278h+var_238]
0x180001feb  mov     ecx, 0C00030D6h; unsigned int
0x180001ff0  call    ?TrkReportEvent@@YAJKGZZ; TrkReportEvent(ulong,ushort,...)
0x180001ff5  mov     ecx, ebx; dwExceptionCode
0x180001ff7  xor     r9d, r9d; lpArguments
0x180001ffa  xor     r8d, r8d; nNumberOfArguments
0x180001ffd  xor     edx, edx; dwExceptionFlags
0x180001fff  call    cs:__imp_RaiseException
0x180002005  nop
0x180002006  mov     rcx, [rsp+278h+var_28]
0x18000200e  xor     rcx, rsp; StackCookie
0x180002011  call    __security_check_cookie
0x180002016  lea     r11, [rsp+278h+var_18]
0x18000201e  mov     rbx, [r11+28h]
0x180002022  mov     rsi, [r11+30h]
0x180002026  mov     rsp, r11
0x180002029  pop     r14
0x18000202b  pop     r13
0x18000202d  pop     rdi
0x18000202e  retn
0x180011186  push    rbp
0x180011188  sub     rsp, 30h
0x18001118c  mov     rbp, rdx
0x18001118f  mov     eax, 1
0x180011194  add     rsp, 30h
0x180011198  pop     rbp
0x180011199  retn
```
