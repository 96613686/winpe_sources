# StackFrames<24>::Dump(void)

- ea: `0x10040cda0`
- end: `0x10040d02d`
- name: `?Dump@?$StackFrames@$0BI@@@QEAAXXZ`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x10040c5b0`

## callees

- `0x100401010`
- `0x1004010b0`
- `0x100401580`
- `0x100402ec0`
- `0x1004043a0`
- `0x10040cda0`

## import_xrefs

- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040cdeb`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040cf17`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040d00c`
- `sqldk!?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA` at `0x10040cddc`
- `sqldk!?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA` at `0x10040cf08`
- `sqldk!?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA` at `0x10040cffd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040ce2b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040cf64`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040cfac`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040ce2b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040cf64`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040cfac`
- `sqldk!SystemThread_TlsOffset` at `0x10040ce10`
- `sqldk!SystemThread_TlsOffset` at `0x10040cf4b`
- `sqldk!SystemThread_TlsOffset` at `0x10040cf93`
- `sqldk!SystemThread_TlsIndex` at `0x10040ce07`
- `sqldk!SystemThread_TlsIndex` at `0x10040cf42`
- `sqldk!SystemThread_TlsIndex` at `0x10040cf8a`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10040cf7a`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10040cf7a`
- `sqldk!?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z` at `0x10040ce3f`
- `sqldk!?SilentBackoutHandler@@YAHHHHHPEAD@Z` at `0x10040ce5a`
- `sqldk!?SOS_OS_SymbolizeRoutine@@3P6AHPEBQEAXIPEADI@ZEA` at `0x10040cee3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StackFrames<24>::Dump(__int64 a1)
{
  void (*v2)(const wchar_t *, ...); // rdx
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned __int64 StackAvailableBytes; // rax
  unsigned int v7; // r9d
  BOOL v8; // ecx
  unsigned int i; // r9d
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  void (*v14)(const wchar_t *, ...); // r8
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 result; // rax
  void (*v20)(const wchar_t *, ...); // r8
  unsigned int v21; // ebx
  _DWORD v22[4]; // [rsp+30h] [rbp+0h] BYREF
  __int64 v23; // [rsp+40h] [rbp+10h]
  __int64 v24; // [rsp+48h] [rbp+18h]
  _BYTE v25[16]; // [rsp+50h] [rbp+20h] BYREF
  _BYTE v26[24]; // [rsp+60h] [rbp+30h] BYREF
  _BYTE v27[40]; // [rsp+78h] [rbp+48h] BYREF

  v24 = -2;
  v2 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
  if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
    v2 = SOS_OS_LogUnlocalizedRoutine;
  v2(L"----------------- Backtrace ---------------\n");
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v4 = *(_QWORD *)(v3 + 256);
  if ( !v4 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v4 = *(_QWORD *)(v3 + 256);
  }
  v5 = *(_QWORD *)(v4 + 3208);
  *(_QWORD *)(v4 + 3208) = ex_trans_cexcept_nodump;
  v23 = v5;
  try
  {
    v21 = 0;
    ExcHandler::ExcHandler((ExcHandler *)v27, 0, 0, 0, SilentBackoutHandler, 0);
    v8 = 0;
    v22[0] = 0;
    for ( i = 4096; ; i = v7 >> 1 )
    {
      v22[1] = i;
      if ( v8 )
        break;
      if ( i < 0x400 )
        goto LABEL_23;
      StackAvailableBytes = SOS_Task::GetStackAvailableBytes();
      v8 = StackAvailableBytes >= (unsigned __int64)(v7 + 0x4000) + 0x10000;
      v22[0] = v8;
    }
    v10 = i + 15LL;
    if ( v10 <= i )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
    v12 = alloca(v11);
    v13 = alloca(v11);
    v22[0] = SOS_OS_SymbolizeRoutine((void *const *)(a1 + 24), *(_DWORD *)(a1 + 216), (char *)v22, i);
    if ( !v22[0] )
    {
LABEL_23:
      while ( 1 )
      {
        v22[2] = v21;
        if ( v21 >= *(_DWORD *)(a1 + 216) )
          break;
        v20 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
        if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
          v20 = SOS_OS_LogUnlocalizedRoutine;
        v20(L"0x%p\n", *(_QWORD *)(a1 + 8LL * v21++ + 24));
      }
      goto LABEL_15;
    }
    v14 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
    if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
      v14 = SOS_OS_LogUnlocalizedRoutine;
    v14(L"%hs\n", v22);
LABEL_15:
    ExcHandler::~ExcHandler((ExcHandler *)v27);
  }
  catch ( SQLError v26 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v25, (const struct SQLError *)v26);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v25);
    }
    catch ( ShortStackException )
    {
    }
  }
  v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v16 = *(_QWORD *)(v15 + 256);
  if ( !v16 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v16 = *(_QWORD *)(v15 + 256);
  }
  if ( *(_DWORD *)(v16 + 556) )
    ExceptionPostCatchActions((struct Worker *)v16);
  v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v18 = *(_QWORD *)(v17 + 256);
  if ( !v18 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v18 = *(_QWORD *)(v17 + 256);
  }
  result = v23;
  *(_QWORD *)(v18 + 3208) = v23;
  return result;
}

```

## disassembly

```asm
0x10040cda0  push    rbp
0x10040cda2  sub     rsp, 0B0h
0x10040cda9  lea     rbp, [rsp+30h]
0x10040cdae  mov     [rbp+80h+var_68], 0FFFFFFFFFFFFFFFEh
0x10040cdb6  mov     [rbp+80h+arg_0], rbx
0x10040cdbd  mov     [rbp+80h+arg_8], rsi
0x10040cdc4  mov     [rbp+80h+arg_10], rdi
0x10040cdcb  mov     rax, cs:__security_cookie
0x10040cdd2  xor     rax, rbp
0x10040cdd5  mov     [rbp+80h+var_10], rax
0x10040cdd9  mov     rdi, rcx
0x10040cddc  mov     rax, cs:__imp_?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x10040cde3  mov     rdx, [rax]
0x10040cde6  test    rdx, rdx
0x10040cde9  jnz     short loc_10040CDF5
0x10040cdeb  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10040cdf2  mov     rdx, [rax]
0x10040cdf5  lea     rcx, aBacktrace; "----------------- Backtrace -----------"...
0x10040cdfc  call    rdx
0x10040cdfe  mov     rdx, gs:58h
0x10040ce07  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040ce0e  mov     ecx, [rax]
0x10040ce10  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040ce17  mov     ebx, [rax]
0x10040ce19  add     rbx, [rdx+rcx*8]
0x10040ce1d  mov     rdx, [rbx+100h]
0x10040ce24  test    rdx, rdx
0x10040ce27  jnz     short loc_10040CE38
0x10040ce29  xor     ecx, ecx
0x10040ce2b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040ce31  mov     rdx, [rbx+100h]
0x10040ce38  mov     rcx, [rdx+0C88h]
0x10040ce3f  mov     rax, cs:__imp_?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; ex_trans_cexcept_nodump(uint,_EXCEPTION_POINTERS *)
0x10040ce46  mov     [rdx+0C88h], rax
0x10040ce4d  mov     [rbp+80h+var_70], rcx
0x10040ce51  xor     edx, edx; unsigned __int16
0x10040ce53  xor     ebx, ebx
0x10040ce55  mov     [rsp+0B0h+var_88], rbx; struct Worker *
0x10040ce5a  mov     rax, cs:__imp_?SilentBackoutHandler@@YAHHHHHPEAD@Z; SilentBackoutHandler(int,int,int,int,char *)
0x10040ce61  mov     [rsp+0B0h+var_90], rax; int (*)(int, int, int, int, char *)
0x10040ce66  xor     r9d, r9d; unsigned __int8
0x10040ce69  xor     r8d, r8d; unsigned __int8
0x10040ce6c  lea     rcx, [rbp+80h+var_38]; this
0x10040ce70  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10040ce75  nop
0x10040ce76  mov     ecx, ebx
0x10040ce78  mov     [rbp+80h+var_80], ebx
0x10040ce7b  mov     r9d, 1000h
0x10040ce81  mov     [rbp+80h+var_7C], r9d
0x10040ce85  test    ecx, ecx
0x10040ce87  jnz     short loc_10040CEB9
0x10040ce89  cmp     r9d, 400h
0x10040ce90  jb      loc_10040CFEE
0x10040ce96  call    ?GetStackAvailableBytes@SOS_Task@@SA_KXZ; SOS_Task::GetStackAvailableBytes(void)
0x10040ce9b  lea     edx, [r9+4000h]
0x10040cea2  add     rdx, 10000h
0x10040cea9  mov     ecx, ebx
0x10040ceab  cmp     rax, rdx
0x10040ceae  setnb   cl
0x10040ceb1  mov     [rbp+80h+var_80], ecx
0x10040ceb4  shr     r9d, 1
0x10040ceb7  jmp     short loc_10040CE81
0x10040ceb9  mov     eax, r9d
0x10040cebc  lea     rcx, [rax+0Fh]
0x10040cec0  cmp     rcx, rax
0x10040cec3  ja      short loc_10040CECF
0x10040cec5  mov     rcx, 0FFFFFFFFFFFFFF0h
0x10040cecf  and     rcx, 0FFFFFFFFFFFFFFF0h
0x10040ced3  mov     rax, rcx
0x10040ced6  call    _alloca_probe
0x10040cedb  sub     rsp, rcx
0x10040cede  lea     rsi, [rsp+0B0h+var_80]
0x10040cee3  mov     rax, cs:__imp_?SOS_OS_SymbolizeRoutine@@3P6AHPEBQEAXIPEADI@ZEA; int (*SOS_OS_SymbolizeRoutine)(void * const *,uint,char *,uint)
0x10040ceea  mov     r10, [rax]
0x10040ceed  lea     rcx, [rdi+18h]
0x10040cef1  mov     r8, rsi
0x10040cef4  mov     edx, [rdi+0D8h]
0x10040cefa  call    r10
0x10040cefd  mov     [rbp+80h+var_80], eax
0x10040cf00  test    eax, eax
0x10040cf02  jz      loc_10040CFEE
0x10040cf08  mov     rax, cs:__imp_?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x10040cf0f  mov     r8, [rax]
0x10040cf12  test    r8, r8
0x10040cf15  jnz     short loc_10040CF21
0x10040cf17  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10040cf1e  mov     r8, [rax]
0x10040cf21  mov     rdx, rsi
0x10040cf24  lea     rcx, aHs; "%hs\n"
0x10040cf2b  call    r8
0x10040cf2e  nop
0x10040cf2f  lea     rcx, [rbp+80h+var_38]; this
0x10040cf33  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10040cf38  nop
0x10040cf39  mov     rdx, gs:58h
0x10040cf42  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040cf49  mov     ecx, [rax]
0x10040cf4b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040cf52  mov     ebx, [rax]
0x10040cf54  add     rbx, [rdx+rcx*8]
0x10040cf58  mov     rcx, [rbx+100h]
0x10040cf5f  test    rcx, rcx
0x10040cf62  jnz     short loc_10040CF71
0x10040cf64  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040cf6a  mov     rcx, [rbx+100h]
0x10040cf71  cmp     dword ptr [rcx+22Ch], 0
0x10040cf78  jz      short loc_10040CF81
0x10040cf7a  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x10040cf80  nop
0x10040cf81  mov     rdx, gs:58h
0x10040cf8a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040cf91  mov     ecx, [rax]
0x10040cf93  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040cf9a  mov     ebx, [rax]
0x10040cf9c  add     rbx, [rdx+rcx*8]
0x10040cfa0  mov     rcx, [rbx+100h]
0x10040cfa7  test    rcx, rcx
0x10040cfaa  jnz     short loc_10040CFB9
0x10040cfac  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040cfb2  mov     rcx, [rbx+100h]
0x10040cfb9  mov     rax, [rbp+80h+var_70]
0x10040cfbd  mov     [rcx+0C88h], rax
0x10040cfc4  mov     rcx, [rbp+80h+var_10]
0x10040cfc8  xor     rcx, rbp; StackCookie
0x10040cfcb  call    __security_check_cookie
0x10040cfd0  mov     rbx, [rbp+80h+arg_0]
0x10040cfd7  mov     rsi, [rbp+80h+arg_8]
0x10040cfde  mov     rdi, [rbp+80h+arg_10]
0x10040cfe5  lea     rsp, [rbp+80h]
0x10040cfec  pop     rbp
0x10040cfed  retn
0x10040cfee  mov     [rbp+80h+var_78], ebx
0x10040cff1  cmp     ebx, [rdi+0D8h]
0x10040cff7  jnb     loc_10040CF2F
0x10040cffd  mov     rax, cs:__imp_?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x10040d004  mov     r8, [rax]
0x10040d007  test    r8, r8
0x10040d00a  jnz     short loc_10040D016
0x10040d00c  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10040d013  mov     r8, [rax]
0x10040d016  mov     edx, ebx
0x10040d018  mov     rdx, [rdi+rdx*8+18h]
0x10040d01d  lea     rcx, a0xP; "0x%p\n"
0x10040d024  call    r8
0x10040d027  inc     ebx
0x10040d029  jmp     short loc_10040CFEE
```
