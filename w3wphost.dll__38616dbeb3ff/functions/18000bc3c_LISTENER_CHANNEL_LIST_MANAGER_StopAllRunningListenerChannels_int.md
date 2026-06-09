# LISTENER_CHANNEL_LIST_MANAGER::StopAllRunningListenerChannels(int)

- ea: `0x18000bc3c`
- end: `0x18000bdbe`
- name: `?StopAllRunningListenerChannels@LISTENER_CHANNEL_LIST_MANAGER@@QEAAXH@Z`
- size: `386`
- prototype: `void __fastcall(LISTENER_CHANNEL_LIST_MANAGER *this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007398`

## callees

- `0x18000b4ec`
- `0x18000bc3c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bd51`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bd51`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bc94`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bc94`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bc6a`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bc6a`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bcbf`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bd32`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bcbf`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bd32`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bc51`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bcce`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bc51`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bcce`
- `iisutil!PuDbgPrint` at `0x18000bd91`
- `iisutil!PuDbgPrint` at `0x18000bd91`

## string_xrefs

- `0x18000bd8a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\listener_channel_list_manager.cxx`

## pseudocode

```c
void __fastcall LISTENER_CHANNEL_LIST_MANAGER::StopAllRunningListenerChannels(
        LISTENER_CHANNEL_LIST_MANAGER *this,
        int a2)
{
  _QWORD **v4; // rdi
  _QWORD *i; // rbx
  BOOL v6; // r14d
  _QWORD *v7; // rbx
  _QWORD *v8; // rcx
  _QWORD *v9; // rax
  _QWORD *v10; // rdx

  CReaderWriterLock3::WriteLock(this);
  v4 = (_QWORD **)((char *)this + 8);
  for ( i = (_QWORD *)*((_QWORD *)this + 1); i != v4; i = (_QWORD *)*i )
  {
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(i + 4));
    v6 = (_QWORD *)i[6] == i + 6 && *((_DWORD *)i + 4) == 5;
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(i + 4));
    if ( !v6 )
      LISTENER_CHANNEL::StopListenerChannel((LISTENER_CHANNEL *)(i - 31), a2);
  }
  CReaderWriterLock3::WriteUnlock(this);
  while ( 1 )
  {
    CReaderWriterLock3::WriteLock(this);
    v7 = *v4;
    while ( v7 != v4 )
    {
      v8 = v7 - 31;
      if ( ((*((_DWORD *)v7 + 4) - 1) & 0xFFFFFFFB) != 0 )
      {
        v7 = (_QWORD *)*v7;
      }
      else
      {
        v9 = (_QWORD *)*v7;
        if ( *(_QWORD **)(*v7 + 8LL) != v7 || (v10 = (_QWORD *)v7[1], (_QWORD *)*v10 != v7) )
          __fastfail(3u);
        *v10 = v9;
        v7 = v9;
        v9[1] = v10;
        (*(void (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
      }
    }
    CReaderWriterLock3::WriteUnlock(this);
    if ( *v4 == v4 && !LISTENER_CHANNEL::s_lNotStoppedCount )
      break;
    Sleep(0xC8u);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\listener_channel_list_manager.cxx",
        271,
        "LISTENER_CHANNEL_LIST_MANAGER::StopAllRunningListenerChannels",
        "Waiting for all LISTENER_CHANNELS to stop\r\n");
  }
  _InterlockedExchange((volatile __int32 *)this + 6, 0);
}

```

## disassembly

```asm
0x18000bc3c  push    rbx
0x18000bc3e  push    rbp
0x18000bc3f  push    rsi
0x18000bc40  push    rdi
0x18000bc41  push    r12
0x18000bc43  push    r14
0x18000bc45  push    r15
0x18000bc47  sub     rsp, 30h
0x18000bc4b  mov     r12d, edx
0x18000bc4e  mov     rsi, rcx
0x18000bc51  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000bc58  nop     dword ptr [rax+rax+00h]
0x18000bc5d  lea     rdi, [rsi+8]
0x18000bc61  mov     rbx, [rdi]
0x18000bc64  jmp     short loc_18000BCB7
0x18000bc66  lea     rcx, [rbx+20h]
0x18000bc6a  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000bc71  nop     dword ptr [rax+rax+00h]
0x18000bc76  lea     rax, [rbx+30h]
0x18000bc7a  cmp     [rax], rax
0x18000bc7d  jnz     short loc_18000BC8D
0x18000bc7f  cmp     dword ptr [rbx+10h], 5
0x18000bc83  jnz     short loc_18000BC8D
0x18000bc85  mov     r14d, 1
0x18000bc8b  jmp     short loc_18000BC90
0x18000bc8d  xor     r14d, r14d
0x18000bc90  lea     rcx, [rbx+20h]
0x18000bc94  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000bc9b  nop     dword ptr [rax+rax+00h]
0x18000bca0  test    r14d, r14d
0x18000bca3  jnz     short loc_18000BCB4
0x18000bca5  mov     edx, r12d; int
0x18000bca8  lea     rcx, [rbx-0F8h]; this
0x18000bcaf  call    ?StopListenerChannel@LISTENER_CHANNEL@@QEAAJH@Z; LISTENER_CHANNEL::StopListenerChannel(int)
0x18000bcb4  mov     rbx, [rbx]
0x18000bcb7  cmp     rbx, rdi
0x18000bcba  jnz     short loc_18000BC66
0x18000bcbc  mov     rcx, rsi
0x18000bcbf  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000bcc6  nop     dword ptr [rax+rax+00h]
0x18000bccb  mov     rcx, rsi
0x18000bcce  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000bcd5  nop     dword ptr [rax+rax+00h]
0x18000bcda  mov     rbx, [rdi]
0x18000bcdd  jmp     short loc_18000BD2A
0x18000bcdf  lea     rcx, [rbx-0F8h]
0x18000bce6  mov     eax, [rcx+108h]
0x18000bcec  dec     eax
0x18000bcee  test    eax, 0FFFFFFFBh
0x18000bcf3  jz      short loc_18000BCFA
0x18000bcf5  mov     rbx, [rbx]
0x18000bcf8  jmp     short loc_18000BD2A
0x18000bcfa  mov     rax, [rbx]
0x18000bcfd  cmp     [rax+8], rbx
0x18000bd01  jnz     loc_18000BDA2
0x18000bd07  mov     rdx, [rbx+8]
0x18000bd0b  cmp     [rdx], rbx
0x18000bd0e  jnz     loc_18000BDA2
0x18000bd14  mov     [rdx], rax
0x18000bd17  mov     rbx, rax
0x18000bd1a  mov     [rax+8], rdx
0x18000bd1e  mov     rax, [rcx]
0x18000bd21  mov     rax, [rax+8]
0x18000bd25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd2a  cmp     rbx, rdi
0x18000bd2d  jnz     short loc_18000BCDF
0x18000bd2f  mov     rcx, rsi
0x18000bd32  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000bd39  nop     dword ptr [rax+rax+00h]
0x18000bd3e  cmp     [rdi], rdi
0x18000bd41  jnz     short loc_18000BD4C
0x18000bd43  cmp     cs:?s_lNotStoppedCount@LISTENER_CHANNEL@@0JA, 0; long LISTENER_CHANNEL::s_lNotStoppedCount
0x18000bd4a  jz      short loc_18000BDA9
0x18000bd4c  mov     ecx, 0C8h; dwMilliseconds
0x18000bd51  call    cs:__imp_Sleep
0x18000bd58  nop     dword ptr [rax+rax+00h]
0x18000bd5d  test    byte ptr cs:g_dwDebugFlags, 3
0x18000bd64  jz      loc_18000BCCB
0x18000bd6a  mov     rcx, cs:g_pDebug
0x18000bd71  lea     rax, aWaitingForAllL; "Waiting for all LISTENER_CHANNELS to st"...
0x18000bd78  lea     r9, aListenerChanne; "LISTENER_CHANNEL_LIST_MANAGER::StopAllR"...
0x18000bd7f  mov     [rsp+68h+var_48], rax
0x18000bd84  mov     r8d, 10Fh
0x18000bd8a  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000bd91  call    cs:__imp_PuDbgPrint
0x18000bd98  nop     dword ptr [rax+rax+00h]
0x18000bd9d  jmp     loc_18000BCCB
0x18000bda2  mov     ecx, 3
0x18000bda7  int     29h; Win8: RtlFailFast(ecx)
0x18000bda9  xor     eax, eax
0x18000bdab  xchg    eax, [rsi+18h]
0x18000bdae  add     rsp, 30h
0x18000bdb2  pop     r15
0x18000bdb4  pop     r14
0x18000bdb6  pop     r12
0x18000bdb8  pop     rdi
0x18000bdb9  pop     rsi
0x18000bdba  pop     rbp
0x18000bdbb  pop     rbx
0x18000bdbc  retn
```
