# UninitXE(void)

- ea: `0x100403e80`
- end: `0x100404168`
- name: `?UninitXE@@YAXXZ`
- size: `744`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1004064d0`

## callees

- `0x100403e80`
- `0x100405270`
- `0x100405390`
- `0x100461940`
- `0x1004624a0`
- `0x100487cd6`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100403fa8`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100403fa8`
- `sqldk!SystemThread_TlsIndex` at `0x100403f68`
- `sqldk!SystemThread_TlsIndex` at `0x100403fc1`
- `sqldk!SystemThread_TlsOffset` at `0x100403f71`
- `sqldk!SystemThread_TlsOffset` at `0x100403fca`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100403f8a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100403fe5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100403f8a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100403fe5`
- `api-ms-win-crt-stdio-l1-1-0!_flushall` at `0x10040402a`
- `api-ms-win-crt-stdio-l1-1-0!_flushall` at `0x10040402a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall UninitXE(__int64 a1)
{
  int v1; // edi
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rdx
  unsigned int i; // ebx
  __int64 v8; // rsi
  int v9; // [rsp+30h] [rbp-78h] BYREF
  __int64 v10; // [rsp+38h] [rbp-70h]
  int v11; // [rsp+40h] [rbp-68h] BYREF
  int v12; // [rsp+44h] [rbp-64h]
  __int64 v13; // [rsp+48h] [rbp-60h]
  int v14; // [rsp+50h] [rbp-58h] BYREF
  __int64 v15; // [rsp+58h] [rbp-50h]
  __int64 v16; // [rsp+60h] [rbp-48h]
  __int64 v17; // [rsp+68h] [rbp-40h]
  __int64 v18; // [rsp+70h] [rbp-38h]
  bool v19; // [rsp+80h] [rbp-28h]

  v1 = 1;
  if ( qword_100516E68 && qword_1005170A8 && qword_100516E40 && (unsigned int)qword_100516E88(a1) )
    XE_FlushSessions(0x3E8u, 0x2710u, 1, &XE_XMLConfig_SessionTag);
  if ( qword_100516E68 && qword_1005170A8 && qword_100516E40 && (unsigned int)qword_100516E88(a1) )
  {
    Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v9, 1);
    v14 = 4194505;
    v15 = 0;
    v17 = 0;
    v16 = 0;
    v18 = 0;
    v19 = 0;
    v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v3 = *(_QWORD *)(v2 + 256);
    if ( !v3 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v3 = *(_QWORD *)(v2 + 256);
    }
    v4 = *(_QWORD *)(v3 + 600);
    if ( v4 )
      v19 = (unsigned int)SOS_Task::PushWait(v4, &v14) == 0;
    v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v6 = *(_QWORD *)(v5 + 256);
    if ( !v6 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v6 = *(_QWORD *)(v5 + 256);
    }
    v13 = v6;
    v12 = (*(_DWORD *)(v6 + 800) >> 11) & 1;
    if ( v12 || (*(_BYTE *)(v6 + 800) & 4) == 0 )
    {
      v11 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 608) + 8LL))(*(_QWORD *)(v6 + 608));
    }
    else
    {
      v11 = 0;
    }
    _flushall();
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v11);
    *(_DWORD *)(v10 + 616) &= ~v9;
  }
  if ( qword_100516E68
    && qword_1005170A8
    && qword_100516E40
    && XE_PackageManager::sm_initLock
    && XE_PackageManager::sm_targetLock )
  {
    for ( i = 0; i < XE_PackageManager::sm_nPackageCreators; ++i )
    {
      v8 = 24LL * i;
      if ( *(_DWORD *)((char *)&XE_PackageManager::sm_packageCreators + v8 + 16) )
      {
        v1 = (*((__int64 (__fastcall **)(_QWORD))&xmmword_100516E48 + 1))((*(_WORD **)((char *)&XE_PackageManager::sm_packageCreators
                                                                                     + v8))[2] & 0x3FF);
        if ( v1 )
          *(_DWORD *)((char *)&XE_PackageManager::sm_packageCreators + v8 + 16) = 0;
      }
      if ( !v1 )
        return;
    }
    memset_0(&XE_PackageManager::sm_packageCreators, 0, 0x6000u);
    XE_PackageManager::sm_nPackageCreators = 0;
    if ( XE_PackageManager::sm_eventLock )
    {
      qword_100517128(XE_PackageManager::sm_eventLock);
      XE_PackageManager::sm_eventLock = 0;
    }
    if ( XE_PackageManager::sm_targetLock )
    {
      qword_100517128(XE_PackageManager::sm_targetLock);
      XE_PackageManager::sm_targetLock = 0;
    }
    if ( XE_PackageManager::sm_initLock )
    {
      qword_100517128(XE_PackageManager::sm_initLock);
      XE_PackageManager::sm_initLock = 0;
    }
    XE_API::Finalize();
  }
}

```

## disassembly

```asm
0x100403e80  mov     rax, rsp
0x100403e83  push    rdi
0x100403e84  push    r14
0x100403e86  push    r15
0x100403e88  sub     rsp, 90h
0x100403e8f  mov     [rsp+0A8h+var_88], 0FFFFFFFFFFFFFFFEh
0x100403e98  mov     [rax+10h], rbx
0x100403e9c  mov     [rax+18h], rbp
0x100403ea0  mov     [rax+20h], rsi
0x100403ea4  mov     edi, 1
0x100403ea9  cmp     cs:qword_100516E68, 0
0x100403eb1  jz      short loc_100403EEA
0x100403eb3  cmp     cs:qword_1005170A8, 0
0x100403ebb  jz      short loc_100403EEA
0x100403ebd  cmp     cs:qword_100516E40, 0
0x100403ec5  jz      short loc_100403EEA
0x100403ec7  call    cs:qword_100516E88
0x100403ecd  test    eax, eax
0x100403ecf  jz      short loc_100403EEA
0x100403ed1  lea     r9, ?XE_XMLConfig_SessionTag@@3U_GUID@@B; struct _GUID *
0x100403ed8  mov     r8d, edi; int
0x100403edb  mov     edx, 2710h; unsigned int
0x100403ee0  mov     ecx, 3E8h; unsigned int
0x100403ee5  call    ?XE_FlushSessions@@YAHIIHPEBU_GUID@@@Z; XE_FlushSessions(uint,uint,int,_GUID const *)
0x100403eea  xor     ebp, ebp
0x100403eec  cmp     cs:qword_100516E68, rbp
0x100403ef3  jz      loc_10040404D
0x100403ef9  cmp     cs:qword_1005170A8, rbp
0x100403f00  jz      loc_10040404D
0x100403f06  cmp     cs:qword_100516E40, rbp
0x100403f0d  jz      loc_10040404D
0x100403f13  call    cs:qword_100516E88
0x100403f19  test    eax, eax
0x100403f1b  jz      loc_10040404D
0x100403f21  mov     edx, edi
0x100403f23  lea     rcx, [rsp+0A8h+var_78]
0x100403f28  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x100403f2d  nop
0x100403f2e  lea     rax, [rsp+0A8h+var_68]
0x100403f33  mov     [rsp+0A8h+arg_0], rax
0x100403f3b  mov     [rsp+0A8h+var_58], 4000C9h
0x100403f43  mov     [rsp+0A8h+var_50], rbp
0x100403f48  mov     [rsp+0A8h+var_40], rbp
0x100403f4d  mov     [rsp+0A8h+var_48], rbp
0x100403f52  mov     [rsp+0A8h+var_38], rbp
0x100403f57  mov     [rsp+0A8h+var_28], bpl
0x100403f5f  mov     rdx, gs:58h
0x100403f68  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100403f6f  mov     ecx, [rax]
0x100403f71  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100403f78  mov     ebx, [rax]
0x100403f7a  add     rbx, [rdx+rcx*8]
0x100403f7e  mov     rcx, [rbx+100h]
0x100403f85  test    rcx, rcx
0x100403f88  jnz     short loc_100403F97
0x100403f8a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100403f90  mov     rcx, [rbx+100h]
0x100403f97  mov     rcx, [rcx+258h]
0x100403f9e  test    rcx, rcx
0x100403fa1  jz      short loc_100403FB8
0x100403fa3  lea     rdx, [rsp+0A8h+var_58]
0x100403fa8  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x100403fae  test    eax, eax
0x100403fb0  setz    [rsp+0A8h+var_28]
0x100403fb8  mov     rdx, gs:58h
0x100403fc1  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100403fc8  mov     ecx, [rax]
0x100403fca  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100403fd1  mov     ebx, [rax]
0x100403fd3  add     rbx, [rdx+rcx*8]
0x100403fd7  mov     rdx, [rbx+100h]
0x100403fde  test    rdx, rdx
0x100403fe1  jnz     short loc_100403FF2
0x100403fe3  xor     ecx, ecx
0x100403fe5  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100403feb  mov     rdx, [rbx+100h]
0x100403ff2  mov     [rsp+0A8h+var_60], rdx
0x100403ff7  mov     eax, [rdx+320h]
0x100403ffd  shr     eax, 0Bh
0x100404000  and     eax, 1
0x100404003  mov     [rsp+0A8h+var_64], eax
0x100404007  jnz     short loc_100404018
0x100404009  test    byte ptr [rdx+320h], 4
0x100404010  jz      short loc_100404018
0x100404012  mov     [rsp+0A8h+var_68], ebp
0x100404016  jmp     short loc_10040402A
0x100404018  mov     [rsp+0A8h+var_68], edi
0x10040401c  mov     rcx, [rdx+260h]
0x100404023  mov     rax, [rcx]
0x100404026  call    qword ptr [rax+8]
0x100404029  nop
0x10040402a  call    cs:__imp__flushall
0x100404030  nop
0x100404031  lea     rcx, [rsp+0A8h+var_68]; this
0x100404036  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10040403b  nop
0x10040403c  mov     rcx, [rsp+0A8h+var_70]
0x100404041  mov     eax, [rsp+0A8h+var_78]
0x100404045  not     eax
0x100404047  and     [rcx+268h], eax
0x10040404d  cmp     cs:qword_100516E68, 0
0x100404055  jz      loc_10040414B
0x10040405b  cmp     cs:qword_1005170A8, 0
0x100404063  jz      loc_10040414B
0x100404069  cmp     cs:qword_100516E40, 0
0x100404071  jz      loc_10040414B
0x100404077  cmp     cs:?sm_initLock@XE_PackageManager@@0PEAXEA, 0; void * XE_PackageManager::sm_initLock
0x10040407f  jz      loc_10040414B
0x100404085  cmp     cs:?sm_targetLock@XE_PackageManager@@0PEAXEA, 0; void * XE_PackageManager::sm_targetLock
0x10040408d  jz      loc_10040414B
0x100404093  mov     ebx, ebp
0x100404095  lea     r14, ?sm_packageCreators@XE_PackageManager@@0PAUPackageMapEntry@1@A; XE_PackageManager::PackageMapEntry near * XE_PackageManager::sm_packageCreators
0x10040409c  mov     r15d, 3FFh
0x1004040a2  cmp     ebx, cs:?sm_nPackageCreators@XE_PackageManager@@0IA; uint XE_PackageManager::sm_nPackageCreators
0x1004040a8  jnb     short loc_1004040E5
0x1004040aa  mov     eax, ebx
0x1004040ac  lea     rcx, [rax+rax*2]
0x1004040b0  lea     rsi, ds:0[rcx*8]
0x1004040b8  cmp     dword ptr [rsi+r14+10h], 0
0x1004040be  jz      short loc_1004040DD
0x1004040c0  mov     rax, [rsi+r14]
0x1004040c4  movzx   ecx, word ptr [rax+4]
0x1004040c8  and     cx, r15w
0x1004040cc  call    qword ptr cs:xmmword_100516E48+8
0x1004040d2  mov     edi, eax
0x1004040d4  test    eax, eax
0x1004040d6  jz      short loc_1004040DD
0x1004040d8  mov     [rsi+r14+10h], ebp
0x1004040dd  inc     ebx
0x1004040df  test    edi, edi
0x1004040e1  jnz     short loc_1004040A2
0x1004040e3  jmp     short loc_10040414B
0x1004040e5  xor     edx, edx; Val
0x1004040e7  mov     r8d, 6000h; Size
0x1004040ed  mov     rcx, r14; void *
0x1004040f0  call    memset_0
0x1004040f5  mov     cs:?sm_nPackageCreators@XE_PackageManager@@0IA, ebp; uint XE_PackageManager::sm_nPackageCreators
0x1004040fb  mov     rcx, cs:?sm_eventLock@XE_PackageManager@@0PEAXEA; void * XE_PackageManager::sm_eventLock
0x100404102  test    rcx, rcx
0x100404105  jz      short loc_100404114
0x100404107  call    cs:qword_100517128
0x10040410d  mov     cs:?sm_eventLock@XE_PackageManager@@0PEAXEA, rbp; void * XE_PackageManager::sm_eventLock
0x100404114  mov     rcx, cs:?sm_targetLock@XE_PackageManager@@0PEAXEA; void * XE_PackageManager::sm_targetLock
0x10040411b  test    rcx, rcx
0x10040411e  jz      short loc_10040412D
0x100404120  call    cs:qword_100517128
0x100404126  mov     cs:?sm_targetLock@XE_PackageManager@@0PEAXEA, rbp; void * XE_PackageManager::sm_targetLock
0x10040412d  mov     rcx, cs:?sm_initLock@XE_PackageManager@@0PEAXEA; void * XE_PackageManager::sm_initLock
0x100404134  test    rcx, rcx
0x100404137  jz      short loc_100404146
0x100404139  call    cs:qword_100517128
0x10040413f  mov     cs:?sm_initLock@XE_PackageManager@@0PEAXEA, rbp; void * XE_PackageManager::sm_initLock
0x100404146  call    ?Finalize@XE_API@@SAXXZ; XE_API::Finalize(void)
0x10040414b  lea     r11, [rsp+0A8h+var_18]
0x100404153  mov     rbx, [r11+28h]
0x100404157  mov     rbp, [r11+30h]
0x10040415b  mov     rsi, [r11+38h]
0x10040415f  mov     rsp, r11
0x100404162  pop     r15
0x100404164  pop     r14
0x100404166  pop     rdi
0x100404167  retn
```
