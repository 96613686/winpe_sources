# PMH_LISTENER_CHANNEL_CALLBACK::ReportStopped(long)

- ea: `0x1800035e0`
- end: `0x18000364f`
- name: `?ReportStopped@PMH_LISTENER_CHANNEL_CALLBACK@@UEAAJJ@Z`
- size: `111`
- prototype: `__int64 __fastcall(PMH_LISTENER_CHANNEL_CALLBACK *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800035e0`
- `0x180005010`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800035f8`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800035f8`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003637`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003637`

## pseudocode

```c
__int64 __fastcall PMH_LISTENER_CHANNEL_CALLBACK::ReportStopped(PMH_LISTENER_CHANNEL_CALLBACK *this, unsigned int a2)
{
  __int64 v4; // rcx
  unsigned int v5; // esi

  CReaderWriterLock3::WriteLock((PMH_LISTENER_CHANNEL_CALLBACK *)((char *)this + 8));
  v4 = *((_QWORD *)this + 3);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 24LL))(v4, a2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
    *((_QWORD *)this + 3) = 0;
  }
  else
  {
    v5 = 0;
  }
  CReaderWriterLock3::WriteUnlock((PMH_LISTENER_CHANNEL_CALLBACK *)((char *)this + 8));
  return v5;
}

```

## disassembly

```asm
0x1800035e0  mov     [rsp+arg_0], rbx
0x1800035e5  mov     [rsp+arg_8], rsi
0x1800035ea  push    rdi
0x1800035eb  sub     rsp, 20h
0x1800035ef  mov     rbx, rcx
0x1800035f2  mov     esi, edx
0x1800035f4  add     rcx, 8
0x1800035f8  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800035fe  mov     rcx, [rbx+18h]
0x180003602  test    rcx, rcx
0x180003605  jz      short loc_180003631
0x180003607  mov     rax, [rcx]
0x18000360a  mov     edx, esi
0x18000360c  mov     rax, [rax+18h]
0x180003610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003615  mov     rcx, [rbx+18h]
0x180003619  mov     esi, eax
0x18000361b  mov     rdx, [rcx]
0x18000361e  mov     rax, [rdx+8]
0x180003622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003627  mov     qword ptr [rbx+18h], 0
0x18000362f  jmp     short loc_180003633
0x180003631  xor     esi, esi
0x180003633  lea     rcx, [rbx+8]
0x180003637  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000363d  mov     rbx, [rsp+28h+arg_0]
0x180003642  mov     eax, esi
0x180003644  mov     rsi, [rsp+28h+arg_8]
0x180003649  add     rsp, 20h
0x18000364d  pop     rdi
0x18000364e  retn
```
