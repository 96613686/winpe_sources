# PMH_LISTENER_CHANNEL_CALLBACK::GetId(ulong *)

- ea: `0x1800033f0`
- end: `0x18000344e`
- name: `?GetId@PMH_LISTENER_CHANNEL_CALLBACK@@UEAAJPEAK@Z`
- size: `94`
- prototype: `__int64 __fastcall(PMH_LISTENER_CHANNEL_CALLBACK *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800033f0`
- `0x180005010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000340c`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000340c`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003436`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003436`

## pseudocode

```c
__int64 __fastcall PMH_LISTENER_CHANNEL_CALLBACK::GetId(PMH_LISTENER_CHANNEL_CALLBACK *this, unsigned int *a2)
{
  CReaderWriterLock3 *v2; // rdi
  __int64 v5; // rcx
  unsigned int v6; // ebx

  v2 = (PMH_LISTENER_CHANNEL_CALLBACK *)((char *)this + 8);
  CReaderWriterLock3::ReadLock((PMH_LISTENER_CHANNEL_CALLBACK *)((char *)this + 8));
  v5 = *((_QWORD *)this + 3);
  if ( v5 )
    v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 40LL))(v5, a2);
  else
    v6 = -2147467259;
  CReaderWriterLock3::ReadUnlock(v2);
  return v6;
}

```

## disassembly

```asm
0x1800033f0  mov     [rsp+arg_0], rbx
0x1800033f5  mov     [rsp+arg_8], rsi
0x1800033fa  push    rdi
0x1800033fb  sub     rsp, 20h
0x1800033ff  lea     rdi, [rcx+8]
0x180003403  mov     rbx, rcx
0x180003406  mov     rcx, rdi
0x180003409  mov     rsi, rdx
0x18000340c  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180003412  mov     rcx, [rbx+18h]
0x180003416  test    rcx, rcx
0x180003419  jz      short loc_18000342E
0x18000341b  mov     rax, [rcx]
0x18000341e  mov     rdx, rsi
0x180003421  mov     rax, [rax+28h]
0x180003425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000342a  mov     ebx, eax
0x18000342c  jmp     short loc_180003433
0x18000342e  mov     ebx, 80004005h
0x180003433  mov     rcx, rdi
0x180003436  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000343c  mov     rsi, [rsp+28h+arg_8]
0x180003441  mov     eax, ebx
0x180003443  mov     rbx, [rsp+28h+arg_0]
0x180003448  add     rsp, 20h
0x18000344c  pop     rdi
0x18000344d  retn
```
