# CHostTask::DoSwitchOut(void)

- ea: `0x10041ee70`
- end: `0x10041ef62`
- name: `?DoSwitchOut@CHostTask@@QEAAJXZ`
- size: `242`
- prototype: `__int64 __fastcall(CHostTask *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x100401160`

## callees

- `0x10041ee70`
- `0x10041f670`
- `0x10041f68c`
- `0x10041f730`
- `0x10041f7b0`

## import_xrefs

- `sqllang!?AssertValid@CHostTask@@IEBAXXZ` at `0x10041ee8c`
- `sqllang!?AssertValid@CHostTask@@IEBAXXZ` at `0x10041ee8c`
- `sqllang!?StoreRingBufferRecord@CHostTask@@AEBAXW4HostTaskAction@@J@Z` at `0x10041eeee`
- `sqllang!?StoreRingBufferRecord@CHostTask@@AEBAXW4HostTaskAction@@J@Z` at `0x10041eeee`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041eece`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041eece`
- `sqldk!SystemThread_TlsOffset` at `0x10041eeb3`
- `sqldk!SystemThread_TlsIndex` at `0x10041eeaa`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CHostTask::DoSwitchOut(CHostTask *this)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rsi
  int v5; // eax
  int *v6; // rbx
  unsigned int v7; // esi
  __int64 result; // rax
  _BYTE v9[48]; // [rsp+38h] [rbp-30h] BYREF
  char v10; // [rsp+70h] [rbp+8h] BYREF
  int *v11; // [rsp+78h] [rbp+10h]

  CHostTask::AssertValid(this);
  if ( !*((_QWORD *)this + 38) )
    goto LABEL_13;
  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  if ( (*(_BYTE *)(v3 + 800) & 8) != 0 )
  {
    CHostTask::StoreRingBufferRecord(this, 21, 0);
    v4 = *((_QWORD *)this + 38);
    v5 = ExtIntCodeProtector<1>::Pre(&v10);
    v6 = (int *)&v10;
    if ( v5 < 0 )
      v6 = 0;
    v11 = v6;
    if ( v5 < 0 )
    {
      _mm_lfence();
      v7 = *(_DWORD *)(CallProtectorImpl::MakeProtectorErrorCallResult<long>(v9, (unsigned int)v5) + 8);
      v6 = v11;
    }
    else
    {
      v7 =  ICLRTask::`vcall'{32,{flat}}(v4);
    }
    if ( v6 )
      SOS_Task::SetInExternalCode(*v6);
    result = v7;
  }
  else
  {
LABEL_13:
    result = 0;
  }
  *((_DWORD *)this + 72) = 0;
  return result;
}

```

## disassembly

```asm
0x10041ee70  push    rbp
0x10041ee72  push    rsi
0x10041ee73  push    rdi
0x10041ee74  sub     rsp, 50h
0x10041ee78  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x10041ee81  mov     [rsp+68h+arg_10], rbx
0x10041ee89  mov     rdi, rcx
0x10041ee8c  call    cs:__imp_?AssertValid@CHostTask@@IEBAXXZ; CHostTask::AssertValid(void)
0x10041ee92  xor     ebp, ebp
0x10041ee94  cmp     [rdi+130h], rbp
0x10041ee9b  jz      loc_10041EF4A
0x10041eea1  mov     r8, gs:58h
0x10041eeaa  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041eeb1  mov     edx, [rax]
0x10041eeb3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041eeba  mov     ebx, [rax]
0x10041eebc  add     rbx, [r8+rdx*8]
0x10041eec0  mov     rax, [rbx+100h]
0x10041eec7  test    rax, rax
0x10041eeca  jnz     short loc_10041EEDB
0x10041eecc  xor     ecx, ecx
0x10041eece  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041eed4  mov     rax, [rbx+100h]
0x10041eedb  test    byte ptr [rax+320h], 8
0x10041eee2  jz      short loc_10041EF4A
0x10041eee4  xor     r8d, r8d
0x10041eee7  lea     edx, [r8+15h]
0x10041eeeb  mov     rcx, rdi
0x10041eeee  call    cs:__imp_?StoreRingBufferRecord@CHostTask@@AEBAXW4HostTaskAction@@J@Z; CHostTask::StoreRingBufferRecord(HostTaskAction,long)
0x10041eef4  mov     rsi, [rdi+130h]
0x10041eefb  lea     rcx, [rsp+68h+arg_0]
0x10041ef00  call    ?Pre@?$ExtIntCodeProtector@$00@@QEAAJXZ; ExtIntCodeProtector<1>::Pre(void)
0x10041ef05  lea     rbx, [rsp+68h+arg_0]
0x10041ef0a  test    eax, eax
0x10041ef0c  cmovs   rbx, rbp
0x10041ef10  mov     [rsp+68h+arg_8], rbx
0x10041ef15  js      short loc_10041EF23
0x10041ef17  mov     rcx, rsi
0x10041ef1a  call    ??_9ICLRTask@@$BCA@AA; [thunk]: ICLRTask::`vcall'{32,{flat}}
0x10041ef1f  mov     esi, eax
0x10041ef21  jmp     short loc_10041EF3A
0x10041ef23  lfence
0x10041ef26  mov     edx, eax
0x10041ef28  lea     rcx, [rsp+68h+var_30]
0x10041ef2d  call    ??$MakeProtectorErrorCallResult@J@CallProtectorImpl@@CA?AV?$SOS_CallResult@J@@J@Z; CallProtectorImpl::MakeProtectorErrorCallResult<long>(long)
0x10041ef32  mov     esi, [rax+8]
0x10041ef35  mov     rbx, [rsp+68h+arg_8]
0x10041ef3a  test    rbx, rbx
0x10041ef3d  jz      short loc_10041EF46
0x10041ef3f  mov     ecx, [rbx]; int
0x10041ef41  call    ?SetInExternalCode@SOS_Task@@SAXH@Z; SOS_Task::SetInExternalCode(int)
0x10041ef46  mov     eax, esi
0x10041ef48  jmp     short loc_10041EF4C
0x10041ef4a  mov     eax, ebp
0x10041ef4c  mov     [rdi+120h], ebp
0x10041ef52  mov     rbx, [rsp+68h+arg_10]
0x10041ef5a  add     rsp, 50h
0x10041ef5e  pop     rdi
0x10041ef5f  pop     rsi
0x10041ef60  pop     rbp
0x10041ef61  retn
```
