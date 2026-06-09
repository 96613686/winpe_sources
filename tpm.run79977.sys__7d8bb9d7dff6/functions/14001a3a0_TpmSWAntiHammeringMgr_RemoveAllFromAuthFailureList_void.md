# TpmSWAntiHammeringMgr::RemoveAllFromAuthFailureList(void)

- ea: `0x14001a3a0`
- end: `0x14001a415`
- name: `?RemoveAllFromAuthFailureList@TpmSWAntiHammeringMgr@@QEAAJXZ`
- size: `117`
- prototype: `__int64 __fastcall(TpmSWAntiHammeringMgr *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400116fc`
- `0x1400171d0`

## callees

- `0x140005698`
- `0x14001a3a0`
- `0x1400222b8`
- `0x140028eb8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001a3c7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a3c7`
- `ntoskrnl!KeReleaseMutex` at `0x14001a3fc`
- `ntoskrnl!KeReleaseMutex` at `0x14001a3fc`

## pseudocode

```c
__int64 __fastcall TpmSWAntiHammeringMgr::RemoveAllFromAuthFailureList(PVOID *this)
{
  TpmSWAntiHammeringMgr *i; // rdi
  TpmSWAntiHammeringMgr *v3; // rcx

  TpmSWAntiHammeringMgr::LoadUserAuthFailures((TpmSWAntiHammeringMgr *)this);
  KeWaitForSingleObject(this[4], Executive, 0, 0, 0);
  for ( i = (TpmSWAntiHammeringMgr *)this[2]; i != (TpmSWAntiHammeringMgr *)(this + 2); i = *(TpmSWAntiHammeringMgr **)i )
  {
    TpmUserAuthFailureData::ClearHistory((TpmSWAntiHammeringMgr *)((char *)i - 24));
    TpmSWAntiHammeringMgr::WriteUserAuthFailureData(v3, (TpmSWAntiHammeringMgr *)((char *)i - 24));
  }
  KeReleaseMutex((PRKMUTEX)this[4], 0);
  return 0;
}

```

## disassembly

```asm
0x14001a3a0  push    rbx
0x14001a3a2  push    rsi
0x14001a3a3  push    rdi
0x14001a3a4  push    r14
0x14001a3a6  sub     rsp, 38h
0x14001a3aa  mov     rsi, rcx
0x14001a3ad  call    ?LoadUserAuthFailures@TpmSWAntiHammeringMgr@@QEAAJXZ; TpmSWAntiHammeringMgr::LoadUserAuthFailures(void)
0x14001a3b2  mov     rcx, [rsi+20h]; Object
0x14001a3b6  xor     r9d, r9d; Alertable
0x14001a3b9  xor     r8d, r8d; WaitMode
0x14001a3bc  mov     [rsp+58h+Timeout], 0; Timeout
0x14001a3c5  xor     edx, edx; WaitReason
0x14001a3c7  call    cs:__imp_KeWaitForSingleObject
0x14001a3ce  nop     dword ptr [rax+rax+00h]
0x14001a3d3  lea     r14, [rsi+10h]
0x14001a3d7  mov     rdi, [r14]
0x14001a3da  jmp     short loc_14001A3F1
0x14001a3dc  lea     rcx, [rdi-18h]; this
0x14001a3e0  call    ?ClearHistory@TpmUserAuthFailureData@@QEAAXXZ; TpmUserAuthFailureData::ClearHistory(void)
0x14001a3e5  lea     rdx, [rdi-18h]; struct TpmUserAuthFailureData *
0x14001a3e9  call    ?WriteUserAuthFailureData@TpmSWAntiHammeringMgr@@AEAAJPEAVTpmUserAuthFailureData@@@Z; TpmSWAntiHammeringMgr::WriteUserAuthFailureData(TpmUserAuthFailureData *)
0x14001a3ee  mov     rdi, [rdi]
0x14001a3f1  cmp     rdi, r14
0x14001a3f4  jnz     short loc_14001A3DC
0x14001a3f6  mov     rcx, [rsi+20h]; Mutex
0x14001a3fa  xor     edx, edx; Wait
0x14001a3fc  call    cs:__imp_KeReleaseMutex
0x14001a403  nop     dword ptr [rax+rax+00h]
0x14001a408  xor     eax, eax
0x14001a40a  add     rsp, 38h
0x14001a40e  pop     r14
0x14001a410  pop     rdi
0x14001a411  pop     rsi
0x14001a412  pop     rbx
0x14001a413  retn
```
