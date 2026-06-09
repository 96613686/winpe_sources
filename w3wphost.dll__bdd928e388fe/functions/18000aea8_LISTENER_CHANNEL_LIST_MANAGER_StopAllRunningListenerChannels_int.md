# LISTENER_CHANNEL_LIST_MANAGER::StopAllRunningListenerChannels(int)

- ea: `0x18000aea8`
- end: `0x18000aff5`
- name: `?StopAllRunningListenerChannels@LISTENER_CHANNEL_LIST_MANAGER@@QEAAXH@Z`
- size: `333`
- prototype: `void(LISTENER_CHANNEL_LIST_MANAGER *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006cd8`

## callees

- `0x18000a7b0`
- `0x18000aea8`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000af95`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000af95`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aef4`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aef4`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aed0`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aed0`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000af19`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000af7c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000af19`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000af7c`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aebd`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000af22`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aebd`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000af22`
- `iisutil!PuDbgPrint` at `0x18000afcf`
- `iisutil!PuDbgPrint` at `0x18000afcf`

## string_xrefs

- `0x18000afc8`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\listener_channel_list_manager.cxx`

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
0x18000aea8  push    rbx
0x18000aeaa  push    rbp
0x18000aeab  push    rsi
0x18000aeac  push    rdi
0x18000aead  push    r12
0x18000aeaf  push    r14
0x18000aeb1  push    r15
0x18000aeb3  sub     rsp, 30h
0x18000aeb7  mov     r12d, edx
0x18000aeba  mov     rsi, rcx
0x18000aebd  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000aec3  lea     rdi, [rsi+8]
0x18000aec7  mov     rbx, [rdi]
0x18000aeca  jmp     short loc_18000AF11
0x18000aecc  lea     rcx, [rbx+20h]
0x18000aed0  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000aed6  lea     rax, [rbx+30h]
0x18000aeda  cmp     [rax], rax
0x18000aedd  jnz     short loc_18000AEED
0x18000aedf  cmp     dword ptr [rbx+10h], 5
0x18000aee3  jnz     short loc_18000AEED
0x18000aee5  mov     r14d, 1
0x18000aeeb  jmp     short loc_18000AEF0
0x18000aeed  xor     r14d, r14d
0x18000aef0  lea     rcx, [rbx+20h]
0x18000aef4  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000aefa  test    r14d, r14d
0x18000aefd  jnz     short loc_18000AF0E
0x18000aeff  mov     edx, r12d; int
0x18000af02  lea     rcx, [rbx-0F8h]; this
0x18000af09  call    ?StopListenerChannel@LISTENER_CHANNEL@@QEAAJH@Z; LISTENER_CHANNEL::StopListenerChannel(int)
0x18000af0e  mov     rbx, [rbx]
0x18000af11  cmp     rbx, rdi
0x18000af14  jnz     short loc_18000AECC
0x18000af16  mov     rcx, rsi
0x18000af19  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000af1f  mov     rcx, rsi
0x18000af22  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000af28  mov     rbx, [rdi]
0x18000af2b  jmp     short loc_18000AF74
0x18000af2d  lea     rcx, [rbx-0F8h]
0x18000af34  mov     eax, [rcx+108h]
0x18000af3a  dec     eax
0x18000af3c  test    eax, 0FFFFFFFBh
0x18000af41  jz      short loc_18000AF48
0x18000af43  mov     rbx, [rbx]
0x18000af46  jmp     short loc_18000AF74
0x18000af48  mov     rax, [rbx]
0x18000af4b  cmp     [rax+8], rbx
0x18000af4f  jnz     loc_18000AFDA
0x18000af55  mov     rdx, [rbx+8]
0x18000af59  cmp     [rdx], rbx
0x18000af5c  jnz     short loc_18000AFDA
0x18000af5e  mov     [rdx], rax
0x18000af61  mov     rbx, rax
0x18000af64  mov     [rax+8], rdx
0x18000af68  mov     rax, [rcx]
0x18000af6b  mov     rax, [rax+8]
0x18000af6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af74  cmp     rbx, rdi
0x18000af77  jnz     short loc_18000AF2D
0x18000af79  mov     rcx, rsi
0x18000af7c  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000af82  cmp     [rdi], rdi
0x18000af85  jnz     short loc_18000AF90
0x18000af87  cmp     cs:?s_lNotStoppedCount@LISTENER_CHANNEL@@0JA, 0; long LISTENER_CHANNEL::s_lNotStoppedCount
0x18000af8e  jz      short loc_18000AFE1
0x18000af90  mov     ecx, 0C8h; dwMilliseconds
0x18000af95  call    cs:__imp_Sleep
0x18000af9b  test    byte ptr cs:g_dwDebugFlags, 3
0x18000afa2  jz      loc_18000AF1F
0x18000afa8  mov     rcx, cs:g_pDebug
0x18000afaf  lea     rax, aWaitingForAllL; "Waiting for all LISTENER_CHANNELS to st"...
0x18000afb6  lea     r9, aListenerChanne; "LISTENER_CHANNEL_LIST_MANAGER::StopAllR"...
0x18000afbd  mov     [rsp+68h+var_48], rax
0x18000afc2  mov     r8d, 10Fh
0x18000afc8  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000afcf  call    cs:__imp_PuDbgPrint
0x18000afd5  jmp     loc_18000AF1F
0x18000afda  mov     ecx, 3
0x18000afdf  int     29h; Win8: RtlFailFast(ecx)
0x18000afe1  xor     eax, eax
0x18000afe3  xchg    eax, [rsi+18h]
0x18000afe6  add     rsp, 30h
0x18000afea  pop     r15
0x18000afec  pop     r14
0x18000afee  pop     r12
0x18000aff0  pop     rdi
0x18000aff1  pop     rsi
0x18000aff2  pop     rbp
0x18000aff3  pop     rbx
0x18000aff4  retn
```
