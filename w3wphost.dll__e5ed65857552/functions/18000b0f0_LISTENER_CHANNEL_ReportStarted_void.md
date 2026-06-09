# LISTENER_CHANNEL::ReportStarted(void)

- ea: `0x18000b0f0`
- end: `0x18000b18f`
- name: `?ReportStarted@LISTENER_CHANNEL@@UEAAJXZ`
- size: `159`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800086a0`
- `0x18000b0f0`
- `0x18000b630`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b177`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b177`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b106`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b106`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b140`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b140`

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
0x18000b0f0  push    rbx
0x18000b0f2  push    rbp
0x18000b0f3  push    rsi
0x18000b0f4  push    rdi
0x18000b0f5  sub     rsp, 28h
0x18000b0f9  lea     rbp, [rcx+118h]
0x18000b100  mov     rsi, rcx
0x18000b103  mov     rcx, rbp
0x18000b106  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000b10d  nop     dword ptr [rax+rax+00h]
0x18000b112  cmp     dword ptr [rsi+124h], 0
0x18000b119  jnz     short loc_18000B172
0x18000b11b  cmp     dword ptr [rsi+108h], 5
0x18000b122  jz      short loc_18000B172
0x18000b124  mov     rax, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000b12b  lea     rcx, [rsi+10h]
0x18000b12f  mov     ebx, [rsi+48h]
0x18000b132  mov     dword ptr [rsi+108h], 3
0x18000b13c  mov     rdi, [rax+58h]
0x18000b140  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b147  nop     dword ptr [rax+rax+00h]
0x18000b14c  mov     r8d, ebx; unsigned int
0x18000b14f  mov     rcx, rdi; this
0x18000b152  mov     rdx, rax; Src
0x18000b155  call    ?ReportListenerChannelStarted@WP_IPM@@QEAAXPEBGK@Z; WP_IPM::ReportListenerChannelStarted(ushort const *,ulong)
0x18000b15a  mov     rcx, rsi; this
0x18000b15d  mov     dword ptr [rsi+120h], 1
0x18000b167  call    ?UnblockNextWaitingListenerChannelAction@LISTENER_CHANNEL@@AEAAJXZ; LISTENER_CHANNEL::UnblockNextWaitingListenerChannelAction(void)
0x18000b16c  mov     ebx, eax
0x18000b16e  test    eax, eax
0x18000b170  js      short loc_18000B174
0x18000b172  xor     ebx, ebx
0x18000b174  mov     rcx, rbp
0x18000b177  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b17e  nop     dword ptr [rax+rax+00h]
0x18000b183  mov     eax, ebx
0x18000b185  add     rsp, 28h
0x18000b189  pop     rdi
0x18000b18a  pop     rsi
0x18000b18b  pop     rbp
0x18000b18c  pop     rbx
0x18000b18d  retn
```
