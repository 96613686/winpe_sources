# CoreInputSink::Cleanup(void)

- ea: `0x1800274f4`
- end: `0x1800275b8`
- name: `?Cleanup@CoreInputSink@@QEAAXXZ`
- size: `196`
- prototype: `void __fastcall(CoreInputSink *__hidden this)`
- caller_count: `7`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000d228`
- `0x18000db78`
- `0x18000df20`
- `0x18002714c`
- `0x1800274dc`
- `0x18006d978`
- `0x18006e068`

## callees

- `0x1800274f4`
- `0x1800275c0`
- `0x180027d7c`
- `0x180056d3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027544`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027524`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027524`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002758a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002758a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CoreInputSink::Cleanup(CoreInputSink *this)
{
  DWORD CurrentThreadId; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids,
      this,
      CurrentThreadId);
  }
  AcquireSRWLockExclusive(&CoreInputSink::_srwLock);
  if ( *(_QWORD *)this )
  {
    CoreInputSink::UpdateAndRegisterInputSink(this, *((_DWORD *)this + 2), 0, 0, 0, *(struct _InputSinkEntry **)this);
    CoreInputSink::RemoveInputSinkEntry(this, *(struct _InputSinkEntry **)this);
    *(_QWORD *)this = 0;
    *((_DWORD *)this + 2) = 0;
  }
  ReleaseSRWLockExclusive(&CoreInputSink::_srwLock);
}

```

## disassembly

```asm
0x1800274f4  mov     [rsp+arg_8], rbx
0x1800274f9  push    rdi
0x1800274fa  sub     rsp, 30h
0x1800274fe  mov     rbx, rcx
0x180027501  lea     rcx, WPP_GLOBAL_Control
0x180027508  mov     rax, cs:WPP_GLOBAL_Control
0x18002750f  cmp     rax, rcx
0x180027512  jz      short loc_18002751A
0x180027514  test    byte ptr [rax+1Ch], 40h
0x180027518  jnz     short loc_180027584
0x18002751a  lea     rdi, ?_srwLock@CoreInputSink@@0VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock CoreInputSink::_srwLock
0x180027521  mov     rcx, rdi; SRWLock
0x180027524  call    cs:__imp_AcquireSRWLockExclusive
0x18002752a  mov     [rsp+38h+arg_0], rdi
0x18002752f  mov     rax, [rbx]
0x180027532  test    rax, rax
0x180027535  jnz     short loc_18002754B
0x180027537  mov     rcx, rdi
0x18002753a  mov     rbx, [rsp+38h+arg_8]
0x18002753f  add     rsp, 30h
0x180027543  pop     rdi
0x180027544  jmp     cs:__imp_ReleaseSRWLockExclusive
0x18002754b  mov     [rsp+38h+var_10], rax; struct _InputSinkEntry *
0x180027550  mov     [rsp+38h+var_18], 0; unsigned int
0x180027558  xor     r9d, r9d; bool
0x18002755b  xor     r8d, r8d; HWND
0x18002755e  mov     edx, [rbx+8]; unsigned int
0x180027561  mov     rcx, rbx; this
0x180027564  call    ?UpdateAndRegisterInputSink@CoreInputSink@@AEAAJIPEAUHWND__@@_NIPEAU_InputSinkEntry@@@Z; CoreInputSink::UpdateAndRegisterInputSink(uint,HWND__ *,bool,uint,_InputSinkEntry *)
0x180027569  mov     rdx, [rbx]; struct _InputSinkEntry *
0x18002756c  mov     rcx, rbx; this
0x18002756f  call    ?RemoveInputSinkEntry@CoreInputSink@@AEAAIPEAU_InputSinkEntry@@@Z; CoreInputSink::RemoveInputSinkEntry(_InputSinkEntry *)
0x180027574  mov     qword ptr [rbx], 0
0x18002757b  mov     dword ptr [rbx+8], 0
0x180027582  jmp     short loc_180027537
0x180027584  cmp     byte ptr [rax+19h], 4
0x180027588  jb      short loc_18002751A
0x18002758a  call    cs:__imp_GetCurrentThreadId
0x180027590  mov     edx, 0Bh
0x180027595  mov     [rsp+38h+var_18], eax
0x180027599  mov     r9, rbx
0x18002759c  lea     r8, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x1800275a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275aa  mov     rcx, [rcx+10h]
0x1800275ae  call    WPP_SF_qD
0x1800275b3  jmp     loc_18002751A
```
