# PMH_LISTENER_CHANNEL_CALLBACK::ReportStarted(void)

- ea: `0x180003580`
- end: `0x1800035cb`
- name: `?ReportStarted@PMH_LISTENER_CHANNEL_CALLBACK@@UEAAJXZ`
- size: `75`
- prototype: `__int64 __fastcall(PMH_LISTENER_CHANNEL_CALLBACK *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003580`
- `0x180005010`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003594`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003594`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800035b8`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800035b8`

## pseudocode

```c
__int64 __fastcall PMH_LISTENER_CHANNEL_CALLBACK::ReportStarted(PMH_LISTENER_CHANNEL_CALLBACK *this)
{
  CReaderWriterLock3 *v1; // rdi
  __int64 v3; // rcx
  unsigned int v4; // ebx

  v1 = (PMH_LISTENER_CHANNEL_CALLBACK *)((char *)this + 8);
  CReaderWriterLock3::WriteLock((PMH_LISTENER_CHANNEL_CALLBACK *)((char *)this + 8));
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  else
    v4 = 0;
  CReaderWriterLock3::WriteUnlock(v1);
  return v4;
}

```

## disassembly

```asm
0x180003580  mov     [rsp+arg_0], rbx
0x180003585  push    rdi
0x180003586  sub     rsp, 20h
0x18000358a  lea     rdi, [rcx+8]
0x18000358e  mov     rbx, rcx
0x180003591  mov     rcx, rdi
0x180003594  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000359a  mov     rcx, [rbx+18h]
0x18000359e  test    rcx, rcx
0x1800035a1  jz      short loc_1800035B3
0x1800035a3  mov     rax, [rcx]
0x1800035a6  mov     rax, [rax+10h]
0x1800035aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035af  mov     ebx, eax
0x1800035b1  jmp     short loc_1800035B5
0x1800035b3  xor     ebx, ebx
0x1800035b5  mov     rcx, rdi
0x1800035b8  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800035be  mov     eax, ebx
0x1800035c0  mov     rbx, [rsp+28h+arg_0]
0x1800035c5  add     rsp, 20h
0x1800035c9  pop     rdi
0x1800035ca  retn
```
