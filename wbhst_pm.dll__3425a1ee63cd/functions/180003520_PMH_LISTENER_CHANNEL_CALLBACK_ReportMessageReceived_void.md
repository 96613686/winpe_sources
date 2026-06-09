# PMH_LISTENER_CHANNEL_CALLBACK::ReportMessageReceived(void)

- ea: `0x180003520`
- end: `0x18000356e`
- name: `?ReportMessageReceived@PMH_LISTENER_CHANNEL_CALLBACK@@UEAAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(PMH_LISTENER_CHANNEL_CALLBACK *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003520`
- `0x180005010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003534`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003534`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000355b`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000355b`

## pseudocode

```c
__int64 __fastcall PMH_LISTENER_CHANNEL_CALLBACK::ReportMessageReceived(PMH_LISTENER_CHANNEL_CALLBACK *this)
{
  CReaderWriterLock3 *v1; // rdi
  __int64 v3; // rcx
  unsigned int v4; // ebx

  v1 = (PMH_LISTENER_CHANNEL_CALLBACK *)((char *)this + 8);
  CReaderWriterLock3::ReadLock((PMH_LISTENER_CHANNEL_CALLBACK *)((char *)this + 8));
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3);
  else
    v4 = -2147467259;
  CReaderWriterLock3::ReadUnlock(v1);
  return v4;
}

```

## disassembly

```asm
0x180003520  mov     [rsp+arg_0], rbx
0x180003525  push    rdi
0x180003526  sub     rsp, 20h
0x18000352a  lea     rdi, [rcx+8]
0x18000352e  mov     rbx, rcx
0x180003531  mov     rcx, rdi
0x180003534  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000353a  mov     rcx, [rbx+18h]
0x18000353e  test    rcx, rcx
0x180003541  jz      short loc_180003553
0x180003543  mov     rax, [rcx]
0x180003546  mov     rax, [rax+20h]
0x18000354a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000354f  mov     ebx, eax
0x180003551  jmp     short loc_180003558
0x180003553  mov     ebx, 80004005h
0x180003558  mov     rcx, rdi
0x18000355b  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180003561  mov     eax, ebx
0x180003563  mov     rbx, [rsp+28h+arg_0]
0x180003568  add     rsp, 20h
0x18000356c  pop     rdi
0x18000356d  retn
```
