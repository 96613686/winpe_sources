# LISTENER_CHANNEL::ReportStarted(void)

- ea: `0x18000a410`
- end: `0x18000a49c`
- name: `?ReportStarted@LISTENER_CHANNEL@@UEAAJXZ`
- size: `140`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007e48`
- `0x18000a410`
- `0x18000a8e0`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a48b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a48b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a426`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a426`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a45a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a45a`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL::ReportStarted(LISTENER_CHANNEL *this)
{
  CReaderWriterLock3 *v1; // rbp
  W3WP_HOST *v3; // rax
  unsigned int v4; // ebx
  WP_IPM *v5; // rdi
  const unsigned __int16 *Str; // rax
  int WaitingListenerChannelAction; // ebx

  v1 = (LISTENER_CHANNEL *)((char *)this + 280);
  CReaderWriterLock3::WriteLock((LISTENER_CHANNEL *)((char *)this + 280));
  if ( *((_DWORD *)this + 73) )
    goto LABEL_4;
  if ( *((_DWORD *)this + 66) == 5 )
    goto LABEL_4;
  v3 = g_pW3WPHost;
  v4 = *((_DWORD *)this + 18);
  *((_DWORD *)this + 66) = 3;
  v5 = (WP_IPM *)*((_QWORD *)v3 + 11);
  Str = STRU::QueryStr((LISTENER_CHANNEL *)((char *)this + 16));
  WP_IPM::ReportListenerChannelStarted(v5, Str, v4);
  *((_DWORD *)this + 72) = 1;
  WaitingListenerChannelAction = LISTENER_CHANNEL::UnblockNextWaitingListenerChannelAction(this);
  if ( WaitingListenerChannelAction >= 0 )
LABEL_4:
    WaitingListenerChannelAction = 0;
  CReaderWriterLock3::WriteUnlock(v1);
  return (unsigned int)WaitingListenerChannelAction;
}

```

## disassembly

```asm
0x18000a410  push    rbx
0x18000a412  push    rbp
0x18000a413  push    rsi
0x18000a414  push    rdi
0x18000a415  sub     rsp, 28h
0x18000a419  lea     rbp, [rcx+118h]
0x18000a420  mov     rsi, rcx
0x18000a423  mov     rcx, rbp
0x18000a426  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000a42c  cmp     dword ptr [rsi+124h], 0
0x18000a433  jnz     short loc_18000A486
0x18000a435  cmp     dword ptr [rsi+108h], 5
0x18000a43c  jz      short loc_18000A486
0x18000a43e  mov     rax, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000a445  lea     rcx, [rsi+10h]
0x18000a449  mov     ebx, [rsi+48h]
0x18000a44c  mov     dword ptr [rsi+108h], 3
0x18000a456  mov     rdi, [rax+58h]
0x18000a45a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a460  mov     r8d, ebx; unsigned int
0x18000a463  mov     rcx, rdi; this
0x18000a466  mov     rdx, rax; Src
0x18000a469  call    ?ReportListenerChannelStarted@WP_IPM@@QEAAXPEBGK@Z; WP_IPM::ReportListenerChannelStarted(ushort const *,ulong)
0x18000a46e  mov     rcx, rsi; this
0x18000a471  mov     dword ptr [rsi+120h], 1
0x18000a47b  call    ?UnblockNextWaitingListenerChannelAction@LISTENER_CHANNEL@@AEAAJXZ; LISTENER_CHANNEL::UnblockNextWaitingListenerChannelAction(void)
0x18000a480  mov     ebx, eax
0x18000a482  test    eax, eax
0x18000a484  js      short loc_18000A488
0x18000a486  xor     ebx, ebx
0x18000a488  mov     rcx, rbp
0x18000a48b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000a491  mov     eax, ebx
0x18000a493  add     rsp, 28h
0x18000a497  pop     rdi
0x18000a498  pop     rsi
0x18000a499  pop     rbp
0x18000a49a  pop     rbx
0x18000a49b  retn
```
