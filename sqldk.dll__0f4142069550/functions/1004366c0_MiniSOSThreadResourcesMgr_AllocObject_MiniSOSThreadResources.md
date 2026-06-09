# MiniSOSThreadResourcesMgr::AllocObject(MiniSOSThreadResources * *)

- ea: `0x1004366c0`
- end: `0x10043684b`
- name: `?AllocObject@MiniSOSThreadResourcesMgr@@AEAA?AW4SOS_RESULT@@PEAPEAVMiniSOSThreadResources@@@Z`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x10042bcc0`
- `0x100435fb0`

## callees

- `0x100403070`
- `0x100404bf2`
- `0x1004104a0`
- `0x1004208d0`
- `0x100434490`
- `0x1004366c0`
- `0x10048d250`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1004367df`
- `KERNEL32!CreateEventW` at `0x1004367df`
- `KERNEL32!HeapAlloc` at `0x10043671a`
- `KERNEL32!HeapAlloc` at `0x10043671a`
- `KERNEL32!GetProcessHeap` at `0x1004366f9`
- `KERNEL32!GetProcessHeap` at `0x10048d411`
- `KERNEL32!GetProcessHeap` at `0x1004366f9`
- `KERNEL32!GetProcessHeap` at `0x10048d411`
- `KERNEL32!HeapFree` at `0x10048d41f`
- `KERNEL32!HeapFree` at `0x10048d41f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MiniSOSThreadResourcesMgr::AllocObject(__int64 a1, MiniSOSThreadResources **a2)
{
  HANDLE ProcessHeap; // rax
  __int64 v4; // rbp
  size_t v5; // r14
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  _QWORD *v8; // rbx
  HANDLE EventW; // rax
  MiniSOSThreadResources *v11; // rbx
  HANDLE v12; // rax
  _BYTE v13[80]; // [rsp+60h] [rbp-78h] BYREF

  ProcessHeap = GetProcessHeap();
  v4 = qword_100714440;
  v5 = 8 * qword_100714440;
  v6 = HeapAlloc(ProcessHeap, 0, 8 * qword_100714440 + 6080);
  v7 = v6;
  if ( !v6 )
    return 3221225472LL;
  *v6 = 0;
  v6[1] = 0;
  v8 = v6 + 2;
  Worker::Worker(v6 + 2, 2);
  *v8 = &SpecialWorker::`vftable';
  SOS_Task::Param::Init(
    (SOS_Task::Param *)v13,
    0,
    (struct SOS_ResourceGroup *)qword_100716558,
    0xFFFFFFFFFFFFFFFFuLL,
    (void *(*)(void *))MiniSOSThreadResources::FakeTaskFunc,
    0,
    0);
  SOSHost_Task::SOSHost_Task((SOSHost_Task *)(v7 + 633), (struct SOS_Task::Param *)v13, 0, 0);
  v7[632] = &ISOSHost_TaskImpl::`vftable';
  v7[756] = 0;
  v7[757] = 0;
  *((_DWORD *)v7 + 1516) = 0;
  *((_DWORD *)v7 + 186) = 1;
  *a2 = (MiniSOSThreadResources *)v7;
  EventW = CreateEventW(0, 0, 0, 0);
  v7[756] = EventW;
  if ( EventW )
  {
    *((_DWORD *)v7 + 204) |= 0x400u;
    v7[9] = v4;
    v7[10] = v7 + 760;
    memset_0(v7 + 760, 0, v5);
    return 0;
  }
  else
  {
    v11 = *a2;
    MiniSOSThreadResources::~MiniSOSThreadResources(*a2);
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
    *a2 = 0;
    return 0x80000000LL;
  }
}

```

## disassembly

```asm
0x1004366c0  mov     rax, rsp
0x1004366c3  push    rdi
0x1004366c4  push    r14
0x1004366c6  push    r15
0x1004366c8  sub     rsp, 0C0h
0x1004366cf  mov     [rsp+0D8h+var_98], 0FFFFFFFFFFFFFFFEh
0x1004366d8  mov     [rax+8], rbx
0x1004366dc  mov     [rax+18h], rbp
0x1004366e0  mov     [rax+20h], rsi
0x1004366e4  mov     rax, cs:__security_cookie
0x1004366eb  xor     rax, rsp
0x1004366ee  mov     [rsp+0D8h+var_28], rax
0x1004366f6  mov     rsi, rdx
0x1004366f9  call    cs:__imp_GetProcessHeap
0x1004366ff  mov     rbp, cs:qword_100714440
0x100436706  lea     r14, ds:0[rbp*8]
0x10043670e  lea     r8, [r14+17C0h]; dwBytes
0x100436715  xor     edx, edx; dwFlags
0x100436717  mov     rcx, rax; hHeap
0x10043671a  call    cs:__imp_HeapAlloc
0x100436720  mov     rdi, rax
0x100436723  test    rax, rax
0x100436726  jz      loc_10048D433
0x10043672c  mov     [rsp+0D8h+var_90], rax
0x100436731  xor     r15d, r15d
0x100436734  mov     [rax], r15
0x100436737  mov     [rax+8], r15
0x10043673b  lea     rbx, [rax+10h]
0x10043673f  mov     [rsp+0D8h+var_88], rbx
0x100436744  lea     edx, [r15+2]
0x100436748  mov     rcx, rbx
0x10043674b  call    ??0Worker@@IEAA@W4WORKER_TYPE@@@Z; Worker::Worker(WORKER_TYPE)
0x100436750  nop
0x100436751  lea     rax, ??_7SpecialWorker@@6B@; const SpecialWorker::`vftable'
0x100436758  mov     [rbx], rax
0x10043675b  mov     [rsp+0D8h+var_A8], r15; struct SOS_Task *
0x100436760  mov     [rsp+0D8h+var_B0], r15; void *
0x100436765  lea     rax, ?FakeTaskFunc@MiniSOSThreadResources@@CAPEAXPEAX@Z; MiniSOSThreadResources::FakeTaskFunc(void *)
0x10043676c  mov     [rsp+0D8h+var_B8], rax; void *(*)(void *)
0x100436771  lea     r9, [r15-1]; unsigned __int64
0x100436775  lea     r8, qword_100716558; struct SOS_ResourceGroup *
0x10043677c  xor     edx, edx; unsigned int
0x10043677e  lea     rcx, [rsp+0D8h+var_78]; this
0x100436783  call    ?Init@Param@SOS_Task@@QEAAXKPEAVSOS_ResourceGroup@@_KP6APEAXPEAX@Z2PEAV2@@Z; SOS_Task::Param::Init(ulong,SOS_ResourceGroup *,unsigned __int64,void * (*)(void *),void *,SOS_Task *)
0x100436788  lea     rbx, [rdi+13C0h]
0x10043678f  mov     [rsp+0D8h+var_80], rbx
0x100436794  lea     rcx, [rbx+8]; this
0x100436798  xor     r9d, r9d; struct SOSHost *
0x10043679b  xor     r8d, r8d; struct SOS_Scheduler *
0x10043679e  lea     rdx, [rsp+0D8h+var_78]; struct SOS_Task::Param *
0x1004367a3  call    ??0SOSHost_Task@@IEAA@PEAVParam@SOS_Task@@PEAVSOS_Scheduler@@PEAVSOSHost@@@Z; SOSHost_Task::SOSHost_Task(SOS_Task::Param *,SOS_Scheduler *,SOSHost *)
0x1004367a8  nop
0x1004367a9  lea     rax, ??_7ISOSHost_TaskImpl@@6B@; const ISOSHost_TaskImpl::`vftable'
0x1004367b0  mov     [rbx], rax
0x1004367b3  mov     [rdi+17A0h], r15
0x1004367ba  mov     [rdi+17A8h], r15
0x1004367c1  mov     [rdi+17B0h], r15d
0x1004367c8  mov     dword ptr [rdi+2E8h], 1
0x1004367d2  mov     [rsi], rdi
0x1004367d5  xor     r9d, r9d; lpName
0x1004367d8  xor     r8d, r8d; bInitialState
0x1004367db  xor     edx, edx; bManualReset
0x1004367dd  xor     ecx, ecx; lpEventAttributes
0x1004367df  call    cs:__imp_CreateEventW
0x1004367e5  mov     [rdi+17A0h], rax
0x1004367ec  test    rax, rax
0x1004367ef  jz      loc_10048D406
0x1004367f5  or      dword ptr [rdi+330h], 400h
0x1004367ff  mov     [rdi+48h], rbp
0x100436803  lea     rcx, [rdi+17C0h]; void *
0x10043680a  mov     [rdi+50h], rcx
0x10043680e  mov     r8, r14; Size
0x100436811  xor     edx, edx; Val
0x100436813  call    memset_0
0x100436818  mov     eax, r15d
0x10043681b  jmp     short loc_10043681E
0x10043681e  mov     rcx, [rsp+0D8h+var_28]
0x100436826  xor     rcx, rsp; StackCookie
0x100436829  call    __security_check_cookie
0x10043682e  lea     r11, [rsp+0D8h+var_18]
0x100436836  mov     rbx, [r11+20h]
0x10043683a  mov     rbp, [r11+30h]
0x10043683e  mov     rsi, [r11+38h]
0x100436842  mov     rsp, r11
0x100436845  pop     r15
0x100436847  pop     r14
0x100436849  pop     rdi
0x10043684a  retn
0x10048d406  mov     rbx, [rsi]
0x10048d409  mov     rcx, rbx; this
0x10048d40c  call    ??1MiniSOSThreadResources@@AEAA@XZ; MiniSOSThreadResources::~MiniSOSThreadResources(void)
0x10048d411  call    cs:__imp_GetProcessHeap
0x10048d417  mov     r8, rbx; lpMem
0x10048d41a  xor     edx, edx; dwFlags
0x10048d41c  mov     rcx, rax; hHeap
0x10048d41f  call    cs:__imp_HeapFree
0x10048d425  mov     [rsi], r15
0x10048d428  mov     eax, 80000000h
0x10048d42d  jmp     loc_10043681E
0x10048d433  mov     eax, 0C0000000h
0x10048d438  jmp     loc_10043681E
```
