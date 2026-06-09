# CVsmAzureAttestationHelper::AttestSession::CreateAttestSession(uchar const *,ulong)

- ea: `0x10082d990`
- end: `0x10082db60`
- name: `?CreateAttestSession@AttestSession@CVsmAzureAttestationHelper@@QEAAXPEBEK@Z`
- size: `464`
- prototype: `void __fastcall(CVsmAzureAttestationHelper::AttestSession *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x10082cb80`

## callees

- `0x10045f130`
- `0x10082cad0`
- `0x10082d990`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10082da47`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10082da47`
- `sqldk!SystemThread_TlsIndex` at `0x10082da07`
- `sqldk!SystemThread_TlsIndex` at `0x10082da60`
- `sqldk!SystemThread_TlsOffset` at `0x10082da10`
- `sqldk!SystemThread_TlsOffset` at `0x10082da69`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082da29`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082da84`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082da29`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082da84`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082db1a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082db1a`
- `AzureAttestManager!AttestationCreateSession` at `0x10082daeb`
- `AzureAttestManager!AttestationCreateSession` at `0x10082daeb`

## string_xrefs

- `0x10082dafc`: `AttestationCreateSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CVsmAzureAttestationHelper::AttestSession::CreateAttestSession(
        CVsmAzureAttestationHelper::AttestSession *this,
        const unsigned __int8 *a2,
        unsigned int a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // [rsp+28h] [rbp-90h]
  int v13; // [rsp+40h] [rbp-78h] BYREF
  __int64 v14; // [rsp+48h] [rbp-70h]
  int v15; // [rsp+50h] [rbp-68h] BYREF
  int v16; // [rsp+54h] [rbp-64h]
  __int64 v17; // [rsp+58h] [rbp-60h]
  int v18; // [rsp+60h] [rbp-58h] BYREF
  __int64 v19; // [rsp+68h] [rbp-50h]
  __int64 v20; // [rsp+70h] [rbp-48h]
  __int64 v21; // [rsp+78h] [rbp-40h]
  __int64 v22; // [rsp+80h] [rbp-38h]
  bool v23; // [rsp+90h] [rbp-28h]
  __int64 v24; // [rsp+C0h] [rbp+8h] BYREF
  int *v25; // [rsp+D8h] [rbp+20h]

  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v13, 1);
  v25 = &v15;
  v18 = 536872437;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v22 = 0;
  v23 = 0;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = *(_QWORD *)(v7 + 600);
  if ( v8 )
    v23 = (unsigned int)SOS_Task::PushWait(v8, &v18) == 0;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v17 = v10;
  v16 = (*(_DWORD *)(v10 + 800) >> 11) & 1;
  if ( v16 || (*(_BYTE *)(v10 + 800) & 4) == 0 )
  {
    v15 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 608) + 8LL))(*(_QWORD *)(v10 + 608));
  }
  else
  {
    v15 = 0;
  }
  v11 = AttestationCreateSession(a2, a3, 0, 0, 0, &v24, -2);
  if ( v11 < 0 )
  {
    _mm_lfence();
    LODWORD(v12) = v11;
    ex_raise(331, 96, 16, 58, L"AttestationCreateSession", v12);
  }
  *((_QWORD *)this + 1) = v24;
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v15);
  *(_DWORD *)(v14 + 616) &= ~v13;
}

```

## disassembly

```asm
0x10082d990  mov     rax, rsp
0x10082d993  push    rsi
0x10082d994  push    rdi
0x10082d995  push    r14
0x10082d997  sub     rsp, 0A0h
0x10082d99e  mov     [rsp+0B8h+var_88], 0FFFFFFFFFFFFFFFEh
0x10082d9a7  mov     [rax+10h], rbx
0x10082d9ab  mov     [rax+18h], rbp
0x10082d9af  mov     esi, r8d
0x10082d9b2  mov     rbp, rdx
0x10082d9b5  mov     rdi, rcx
0x10082d9b8  mov     edx, 1
0x10082d9bd  lea     rcx, [rax-78h]
0x10082d9c1  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10082d9c6  nop
0x10082d9c7  lea     rax, [rsp+0B8h+var_68]
0x10082d9cc  mov     [rsp+0B8h+arg_18], rax
0x10082d9d4  mov     [rsp+0B8h+var_58], 200005F5h
0x10082d9dc  xor     r14d, r14d
0x10082d9df  mov     [rsp+0B8h+var_50], r14
0x10082d9e4  mov     [rsp+0B8h+var_40], r14
0x10082d9e9  mov     [rsp+0B8h+var_48], r14
0x10082d9ee  mov     [rsp+0B8h+var_38], r14
0x10082d9f6  mov     [rsp+0B8h+var_28], r14b
0x10082d9fe  mov     rdx, gs:58h
0x10082da07  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10082da0e  mov     ecx, [rax]
0x10082da10  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10082da17  mov     ebx, [rax]
0x10082da19  add     rbx, [rdx+rcx*8]
0x10082da1d  mov     rcx, [rbx+100h]
0x10082da24  test    rcx, rcx
0x10082da27  jnz     short loc_10082DA36
0x10082da29  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10082da2f  mov     rcx, [rbx+100h]
0x10082da36  mov     rcx, [rcx+258h]
0x10082da3d  test    rcx, rcx
0x10082da40  jz      short loc_10082DA57
0x10082da42  lea     rdx, [rsp+0B8h+var_58]
0x10082da47  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10082da4d  test    eax, eax
0x10082da4f  setz    [rsp+0B8h+var_28]
0x10082da57  mov     rdx, gs:58h
0x10082da60  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10082da67  mov     ecx, [rax]
0x10082da69  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10082da70  mov     ebx, [rax]
0x10082da72  add     rbx, [rdx+rcx*8]
0x10082da76  mov     rdx, [rbx+100h]
0x10082da7d  test    rdx, rdx
0x10082da80  jnz     short loc_10082DA91
0x10082da82  xor     ecx, ecx
0x10082da84  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10082da8a  mov     rdx, [rbx+100h]
0x10082da91  mov     [rsp+0B8h+var_60], rdx
0x10082da96  mov     eax, [rdx+320h]
0x10082da9c  shr     eax, 0Bh
0x10082da9f  and     eax, 1
0x10082daa2  mov     [rsp+0B8h+var_64], eax
0x10082daa6  jnz     short loc_10082DAB8
0x10082daa8  test    byte ptr [rdx+320h], 4
0x10082daaf  jz      short loc_10082DAB8
0x10082dab1  mov     [rsp+0B8h+var_68], r14d
0x10082dab6  jmp     short loc_10082DACE
0x10082dab8  mov     [rsp+0B8h+var_68], 1
0x10082dac0  mov     rcx, [rdx+260h]
0x10082dac7  mov     rax, [rcx]
0x10082daca  call    qword ptr [rax+8]
0x10082dacd  nop
0x10082dace  lea     rax, [rsp+0B8h+arg_0]
0x10082dad6  mov     [rsp+0B8h+var_90], rax
0x10082dadb  mov     dword ptr [rsp+0B8h+var_98], r14d
0x10082dae0  xor     r9d, r9d
0x10082dae3  xor     r8d, r8d
0x10082dae6  mov     edx, esi
0x10082dae8  mov     rcx, rbp
0x10082daeb  call    cs:__imp_AttestationCreateSession
0x10082daf1  test    eax, eax
0x10082daf3  jns     short loc_10082DB20
0x10082daf5  lfence
0x10082daf8  mov     dword ptr [rsp+0B8h+var_90], eax
0x10082dafc  lea     rax, aAttestationcre_0; "AttestationCreateSession"
0x10082db03  mov     [rsp+0B8h+var_98], rax
0x10082db08  mov     edx, 60h ; '`'
0x10082db0d  lea     r9d, [rdx-26h]
0x10082db11  lea     r8d, [rdx-50h]
0x10082db15  mov     ecx, 14Bh
0x10082db1a  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082db20  mov     rax, [rsp+0B8h+arg_0]
0x10082db28  mov     [rdi+8], rax
0x10082db2c  lea     rcx, [rsp+0B8h+var_68]; this
0x10082db31  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10082db36  nop
0x10082db37  mov     rcx, [rsp+0B8h+var_70]
0x10082db3c  mov     eax, [rsp+0B8h+var_78]
0x10082db40  not     eax
0x10082db42  and     [rcx+268h], eax
0x10082db48  lea     r11, [rsp+0B8h+var_18]
0x10082db50  mov     rbx, [r11+28h]
0x10082db54  mov     rbp, [r11+30h]
0x10082db58  mov     rsp, r11
0x10082db5b  pop     r14
0x10082db5d  pop     rdi
0x10082db5e  pop     rsi
0x10082db5f  retn
```
