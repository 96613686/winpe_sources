# CHostTask::DoSwitchIn(void)

- ea: `0x10041ed30`
- end: `0x10041ee65`
- name: `?DoSwitchIn@CHostTask@@QEAAJXZ`
- size: `309`
- prototype: `__int64 __fastcall(CHostTask *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x100401160`

## callees

- `0x10041ed30`
- `0x10041f670`
- `0x10041f698`
- `0x10041f730`
- `0x10041f7b0`

## import_xrefs

- `sqllang!?AssertValid@CHostTask@@IEBAXXZ` at `0x10041ee48`
- `sqllang!?AssertValid@CHostTask@@IEBAXXZ` at `0x10041ee48`
- `sqllang!?StoreRingBufferRecord@CHostTask@@AEBAXW4HostTaskAction@@J@Z` at `0x10041ee3f`
- `sqllang!?StoreRingBufferRecord@CHostTask@@AEBAXW4HostTaskAction@@J@Z` at `0x10041ee3f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041edb2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041edb2`
- `sqldk!SystemThread_TlsOffset` at `0x10041ed84`
- `sqldk!SystemThread_TlsIndex` at `0x10041ed73`
- `sqldk!?CreateThreadHandle@SystemThread@@AEAAXXZ` at `0x10041edd7`
- `sqldk!?CreateThreadHandle@SystemThread@@AEAAXXZ` at `0x10041edd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CHostTask::DoSwitchIn(CHostTask *this)
{
  unsigned int v2; // edi
  __int64 v3; // r14
  SystemThread *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rbp
  int v7; // eax
  int *v8; // rbx
  unsigned int v9; // ebp
  _BYTE v11[24]; // [rsp+38h] [rbp-30h] BYREF
  char v12; // [rsp+70h] [rbp+8h] BYREF
  int *v13; // [rsp+78h] [rbp+10h]

  v2 = 0;
  *((_DWORD *)this + 72) = 1;
  v3 = *((_QWORD *)this + 38);
  if ( v3 )
  {
    v4 = (SystemThread *)(SystemThread_TlsOffset
                        + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
    v5 = *((_QWORD *)v4 + 32);
    if ( !v5 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v5 = *((_QWORD *)v4 + 32);
    }
    if ( (*(_BYTE *)(v5 + 800) & 8) != 0 )
    {
      v6 = *((_QWORD *)v4 + 37);
      if ( !v6 )
      {
        SystemThread::CreateThreadHandle(v4);
        v6 = *((_QWORD *)v4 + 37);
      }
      v7 = ExtIntCodeProtector<1>::Pre(&v12);
      v8 = (int *)&v12;
      if ( v7 < 0 )
        v8 = 0;
      v13 = v8;
      if ( v7 < 0 )
      {
        _mm_lfence();
        v9 = *(_DWORD *)(CallProtectorImpl::MakeProtectorErrorCallResult<long>(v11, (unsigned int)v7) + 8);
        v8 = v13;
      }
      else
      {
        v9 =  ICLRTask::`vcall'{24,{flat}}(v3, v6);
      }
      if ( v8 )
        SOS_Task::SetInExternalCode(*v8);
      v2 = v9;
      CHostTask::StoreRingBufferRecord(this, 20, v9);
    }
  }
  CHostTask::AssertValid(this);
  return v2;
}

```

## disassembly

```asm
0x10041ed30  mov     rax, rsp
0x10041ed33  push    rsi
0x10041ed34  push    rdi
0x10041ed35  push    r14
0x10041ed37  sub     rsp, 50h
0x10041ed3b  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x10041ed43  mov     [rax+18h], rbx
0x10041ed47  mov     [rax+20h], rbp
0x10041ed4b  mov     rsi, rcx
0x10041ed4e  xor     edi, edi
0x10041ed50  mov     dword ptr [rcx+120h], 1
0x10041ed5a  mov     r14, [rcx+130h]
0x10041ed61  test    r14, r14
0x10041ed64  jz      loc_10041EE45
0x10041ed6a  mov     r8, gs:58h
0x10041ed73  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041ed7a  mov     edx, [rax]
0x10041ed7c  lea     rcx, ds:0[rdx*8]
0x10041ed84  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041ed8b  mov     edx, [rax]
0x10041ed8d  mov     rbx, [rcx+r8]
0x10041ed91  add     rbx, rdx
0x10041ed94  mov     rax, gs:58h
0x10041ed9d  mov     rbp, [rcx+rax]
0x10041eda1  add     rbp, rdx
0x10041eda4  mov     rax, [rbp+100h]
0x10041edab  test    rax, rax
0x10041edae  jnz     short loc_10041EDBF
0x10041edb0  xor     ecx, ecx
0x10041edb2  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041edb8  mov     rax, [rbp+100h]
0x10041edbf  test    byte ptr [rax+320h], 8
0x10041edc6  jz      short loc_10041EE45
0x10041edc8  mov     rbp, [rbx+128h]
0x10041edcf  test    rbp, rbp
0x10041edd2  jnz     short loc_10041EDE4
0x10041edd4  mov     rcx, rbx
0x10041edd7  call    cs:__imp_?CreateThreadHandle@SystemThread@@AEAAXXZ; SystemThread::CreateThreadHandle(void)
0x10041eddd  mov     rbp, [rbx+128h]
0x10041ede4  lea     rcx, [rsp+68h+arg_0]
0x10041ede9  call    ?Pre@?$ExtIntCodeProtector@$00@@QEAAJXZ; ExtIntCodeProtector<1>::Pre(void)
0x10041edee  lea     rbx, [rsp+68h+arg_0]
0x10041edf3  test    eax, eax
0x10041edf5  cmovs   rbx, rdi
0x10041edf9  mov     [rsp+68h+arg_8], rbx
0x10041edfe  js      short loc_10041EE0F
0x10041ee00  mov     rdx, rbp
0x10041ee03  mov     rcx, r14
0x10041ee06  call    ??_9ICLRTask@@$BBI@AA; [thunk]: ICLRTask::`vcall'{24,{flat}}
0x10041ee0b  mov     ebp, eax
0x10041ee0d  jmp     short loc_10041EE26
0x10041ee0f  lfence
0x10041ee12  mov     edx, eax
0x10041ee14  lea     rcx, [rsp+68h+var_30]
0x10041ee19  call    ??$MakeProtectorErrorCallResult@J@CallProtectorImpl@@CA?AV?$SOS_CallResult@J@@J@Z; CallProtectorImpl::MakeProtectorErrorCallResult<long>(long)
0x10041ee1e  mov     ebp, [rax+8]
0x10041ee21  mov     rbx, [rsp+68h+arg_8]
0x10041ee26  test    rbx, rbx
0x10041ee29  jz      short loc_10041EE32
0x10041ee2b  mov     ecx, [rbx]; int
0x10041ee2d  call    ?SetInExternalCode@SOS_Task@@SAXH@Z; SOS_Task::SetInExternalCode(int)
0x10041ee32  mov     edi, ebp
0x10041ee34  mov     r8d, ebp
0x10041ee37  mov     edx, 14h
0x10041ee3c  mov     rcx, rsi
0x10041ee3f  call    cs:__imp_?StoreRingBufferRecord@CHostTask@@AEBAXW4HostTaskAction@@J@Z; CHostTask::StoreRingBufferRecord(HostTaskAction,long)
0x10041ee45  mov     rcx, rsi
0x10041ee48  call    cs:__imp_?AssertValid@CHostTask@@IEBAXXZ; CHostTask::AssertValid(void)
0x10041ee4e  mov     eax, edi
0x10041ee50  lea     r11, [rsp+68h+var_18]
0x10041ee55  mov     rbx, [r11+30h]
0x10041ee59  mov     rbp, [r11+38h]
0x10041ee5d  mov     rsp, r11
0x10041ee60  pop     r14
0x10041ee62  pop     rdi
0x10041ee63  pop     rsi
0x10041ee64  retn
```
