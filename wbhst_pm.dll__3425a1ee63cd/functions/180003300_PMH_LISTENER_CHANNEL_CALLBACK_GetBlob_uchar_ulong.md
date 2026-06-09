# PMH_LISTENER_CHANNEL_CALLBACK::GetBlob(uchar *,ulong *)

- ea: `0x180003300`
- end: `0x180003357`
- name: `?GetBlob@PMH_LISTENER_CHANNEL_CALLBACK@@UEAAJPEAEPEAK@Z`
- size: `87`
- prototype: `__int64 __fastcall(PMH_LISTENER_CHANNEL_CALLBACK *__hidden this, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003300`
- `0x180005010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003319`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003319`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003346`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003346`

## pseudocode

```c
__int64 __fastcall PMH_LISTENER_CHANNEL_CALLBACK::GetBlob(
        PMH_LISTENER_CHANNEL_CALLBACK *this,
        unsigned __int8 *a2,
        unsigned int *a3)
{
  CReaderWriterLock3 *v3; // rdi
  __int64 v7; // rcx
  unsigned int v8; // ebx

  v3 = (PMH_LISTENER_CHANNEL_CALLBACK *)((char *)this + 8);
  CReaderWriterLock3::ReadLock((PMH_LISTENER_CHANNEL_CALLBACK *)((char *)this + 8));
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
    v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, unsigned int *))(*(_QWORD *)v7 + 48LL))(v7, a2, a3);
  else
    v8 = -2147467259;
  CReaderWriterLock3::ReadUnlock(v3);
  return v8;
}

```

## disassembly

```asm
0x180003300  push    rbx
0x180003302  push    rbp
0x180003303  push    rsi
0x180003304  push    rdi
0x180003305  sub     rsp, 28h
0x180003309  lea     rdi, [rcx+8]
0x18000330d  mov     rbx, rcx
0x180003310  mov     rcx, rdi
0x180003313  mov     rsi, r8
0x180003316  mov     rbp, rdx
0x180003319  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000331f  mov     rcx, [rbx+18h]
0x180003323  test    rcx, rcx
0x180003326  jz      short loc_18000333E
0x180003328  mov     rax, [rcx]
0x18000332b  mov     r8, rsi
0x18000332e  mov     rdx, rbp
0x180003331  mov     rax, [rax+30h]
0x180003335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000333a  mov     ebx, eax
0x18000333c  jmp     short loc_180003343
0x18000333e  mov     ebx, 80004005h
0x180003343  mov     rcx, rdi
0x180003346  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000334c  mov     eax, ebx
0x18000334e  add     rsp, 28h
0x180003352  pop     rdi
0x180003353  pop     rsi
0x180003354  pop     rbp
0x180003355  pop     rbx
0x180003356  retn
```
