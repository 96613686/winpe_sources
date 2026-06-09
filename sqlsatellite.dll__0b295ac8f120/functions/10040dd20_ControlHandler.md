# ControlHandler

- ea: `0x10040dd20`
- end: `0x10040de8a`
- name: `ControlHandler`
- size: `362`
- prototype: `BOOL __stdcall(DWORD CtrlType)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x10040dd20`
- `0x10045d370`
- `0x1004624a0`
- `0x100486af0`
- `0x1004880d0`

## import_xrefs

- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x10040de4d`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x10040de4d`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040de5c`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040de5c`
- `sqldk!??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z` at `0x10040ddbb`
- `sqldk!??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z` at `0x10040ddbb`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040ddc2`
- `sqldk!?sm_WorkerLsBitmap@SOS_PublicGlobals@@2VSmallBitmap@@A` at `0x10040dd5d`
- `api-ms-win-crt-stdio-l1-1-0!_flushall` at `0x10040de42`
- `api-ms-win-crt-stdio-l1-1-0!_flushall` at `0x10040de42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ControlHandler(DWORD CtrlType)
{
  __int64 v2; // r8
  unsigned int v3; // edi
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rcx
  void *v6; // rsp
  void *v7; // rsp
  void **v8; // r9
  __int64 v9; // rcx
  DWORD v10; // ebx
  DWORD v11; // ebx
  __int64 v13; // [rsp+40h] [rbp+0h] BYREF
  _BYTE v14[6048]; // [rsp+50h] [rbp+10h] BYREF

  v13 = -2;
  v2 = SOS_PublicGlobals::sm_WorkerLsBitmap[1];
  v3 = 0;
  if ( v2 )
  {
    v4 = 8 * v2 + 15;
    if ( v4 <= 8 * v2 )
      v4 = 0xFFFFFFFFFFFFFF0LL;
    v5 = v4 & 0xFFFFFFFFFFFFFFF0uLL;
    v6 = alloca(v5);
    v7 = alloca(v5);
    v8 = (void **)&v13;
  }
  else
  {
    v8 = 0;
  }
  AutoMakeMicroSOSThread::AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v14, 0, v2, v8, 1, 0, 0);
  SOS_OS_LogUnlocalizedRoutine(L"Running ControlHandler, calling with control signal type: %d\n", CtrlType);
  if ( !CtrlType || (v10 = CtrlType - 1) == 0 || (v11 = v10 - 1) == 0 || v11 - 3 <= 1 )
  {
    if ( qword_100516E68
      && qword_1005170A8
      && qword_100516E40
      && (unsigned int)qword_100516E88(v9)
      && !(unsigned int)XE_FlushSessions(0x3E8u, 0x2710u, 1, &XE_XMLConfig_SessionTag) )
    {
      scierrlog(0x647Du);
    }
    _flushall();
    SOS_OS::KillProcess(0x3ECu);
    v3 = 1;
  }
  AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v14);
  return v3;
}

```

## disassembly

```asm
0x10040dd20  push    rbp
0x10040dd22  mov     eax, 1800h
0x10040dd27  call    _alloca_probe
0x10040dd2c  sub     rsp, rax
0x10040dd2f  lea     rbp, [rsp+40h]
0x10040dd34  mov     [rbp+17C0h+var_17C0], 0FFFFFFFFFFFFFFFEh
0x10040dd3c  mov     [rbp+17C0h+arg_8], rbx
0x10040dd43  mov     [rbp+17C0h+arg_10], rdi
0x10040dd4a  mov     rax, cs:__security_cookie
0x10040dd51  xor     rax, rbp
0x10040dd54  mov     [rbp+17C0h+var_10], rax
0x10040dd5b  mov     ebx, ecx
0x10040dd5d  mov     rax, cs:__imp_?sm_WorkerLsBitmap@SOS_PublicGlobals@@2VSmallBitmap@@A; SmallBitmap SOS_PublicGlobals::sm_WorkerLsBitmap
0x10040dd64  mov     r8, [rax+8]
0x10040dd68  xor     edi, edi
0x10040dd6a  test    r8, r8
0x10040dd6d  jz      short loc_10040DDA0
0x10040dd6f  lea     rax, ds:0[r8*8]
0x10040dd77  lea     rcx, [rax+0Fh]
0x10040dd7b  cmp     rcx, rax
0x10040dd7e  ja      short loc_10040DD8A
0x10040dd80  mov     rcx, 0FFFFFFFFFFFFFF0h
0x10040dd8a  and     rcx, 0FFFFFFFFFFFFFFF0h
0x10040dd8e  mov     rax, rcx
0x10040dd91  call    _alloca_probe
0x10040dd96  sub     rsp, rcx
0x10040dd99  lea     r9, [rsp+1800h+var_17C0]
0x10040dd9e  jmp     short loc_10040DDA3
0x10040dda0  mov     r9, rdi
0x10040dda3  mov     [rsp+1800h+var_17D0], rdi
0x10040dda8  mov     [rsp+1800h+var_17D8], rdi
0x10040ddad  mov     [rsp+1800h+var_17E0], 1
0x10040ddb5  xor     edx, edx
0x10040ddb7  lea     rcx, [rbp+17C0h+var_17B0]
0x10040ddbb  call    cs:__imp_??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z; AutoMakeMicroSOSThread::AutoMakeMicroSOSThread(void * const,__int64,void * *,int,SOS_Scheduler *,IMemObj *)
0x10040ddc1  nop
0x10040ddc2  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10040ddc9  mov     r8, [rax]
0x10040ddcc  mov     edx, ebx
0x10040ddce  lea     rcx, aRunningControl; "Running ControlHandler, calling with co"...
0x10040ddd5  call    r8
0x10040ddd8  test    ebx, ebx
0x10040ddda  jz      short loc_10040DDF0
0x10040dddc  sub     ebx, 1
0x10040dddf  jz      short loc_10040DDF0
0x10040dde1  sub     ebx, 1
0x10040dde4  jz      short loc_10040DDF0
0x10040dde6  sub     ebx, 3
0x10040dde9  jz      short loc_10040DDF0
0x10040ddeb  cmp     ebx, 1
0x10040ddee  jnz     short loc_10040DE58
0x10040ddf0  cmp     cs:qword_100516E68, 0
0x10040ddf8  jz      short loc_10040DE42
0x10040ddfa  cmp     cs:qword_1005170A8, 0
0x10040de02  jz      short loc_10040DE42
0x10040de04  cmp     cs:qword_100516E40, 0
0x10040de0c  jz      short loc_10040DE42
0x10040de0e  call    cs:qword_100516E88
0x10040de14  test    eax, eax
0x10040de16  jz      short loc_10040DE42
0x10040de18  lea     r9, ?XE_XMLConfig_SessionTag@@3U_GUID@@B; struct _GUID *
0x10040de1f  mov     edx, 2710h; unsigned int
0x10040de24  mov     ecx, 3E8h; unsigned int
0x10040de29  mov     r8d, 1; int
0x10040de2f  call    ?XE_FlushSessions@@YAHIIHPEBU_GUID@@@Z; XE_FlushSessions(uint,uint,int,_GUID const *)
0x10040de34  test    eax, eax
0x10040de36  jnz     short loc_10040DE42
0x10040de38  mov     ecx, 647Dh; unsigned int
0x10040de3d  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040de42  call    cs:__imp__flushall
0x10040de48  mov     ecx, 3ECh
0x10040de4d  call    cs:__imp_?KillProcess@SOS_OS@@SAXK@Z; SOS_OS::KillProcess(ulong)
0x10040de53  mov     edi, 1
0x10040de58  lea     rcx, [rbp+17C0h+var_17B0]
0x10040de5c  call    cs:__imp_??1AutoMakeMicroSOSThread@@QEAA@XZ; AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread(void)
0x10040de62  mov     eax, edi
0x10040de64  mov     rcx, [rbp+17C0h+var_10]
0x10040de6b  xor     rcx, rbp; StackCookie
0x10040de6e  call    __security_check_cookie
0x10040de73  mov     rbx, [rbp+17C0h+arg_8]
0x10040de7a  mov     rdi, [rbp+17C0h+arg_10]
0x10040de81  lea     rsp, [rbp+17C0h]
0x10040de88  pop     rbp
0x10040de89  retn
```
