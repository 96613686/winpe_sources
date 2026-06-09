# LISTENER_CHANNEL_LIST_MANAGER::StopListenerChannel(ushort const *,ulong,int)

- ea: `0x18000affc`
- end: `0x18000b0a1`
- name: `?StopListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBGKH@Z`
- size: `165`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL_LIST_MANAGER *__hidden this, const unsigned __int16 *Src, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006f04`

## callees

- `0x180007f8c`
- `0x18000a7b0`
- `0x18000ab2c`
- `0x18000affc`
- `0x18000d010`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b065`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b065`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b023`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b023`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL_LIST_MANAGER::StopListenerChannel(
        LISTENER_CHANNEL_LIST_MANAGER *this,
        const unsigned __int16 *Src,
        unsigned int a3,
        int a4)
{
  int v8; // esi
  int v9; // edx
  LISTENER_CHANNEL *v10; // rbx
  LISTENER_CHANNEL *v12; // [rsp+40h] [rbp+8h] BYREF

  v12 = 0;
  CReaderWriterLock3::WriteLock(this);
  v8 = LISTENER_CHANNEL_LIST_MANAGER::RemoveListenerChannel(this, Src, a3, &v12);
  if ( v8 >= 0 )
  {
    v9 = a4;
    v10 = v12;
    v8 = LISTENER_CHANNEL::StopListenerChannel(v12, v9);
    (*(void (__fastcall **)(LISTENER_CHANNEL *))(*(_QWORD *)v10 + 8LL))(v10);
  }
  CReaderWriterLock3::WriteUnlock(this);
  if ( v8 < 0 )
    WP_IPM::ReportListenerChannelStopped(*((WP_IPM **)g_pW3WPHost + 11), Src, a3, v8);
  _InterlockedDecrement((volatile signed __int32 *)this + 6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000affc  mov     [rsp+arg_8], rbx
0x18000b001  mov     [rsp+arg_10], rbp
0x18000b006  push    rsi
0x18000b007  push    rdi
0x18000b008  push    r14
0x18000b00a  sub     rsp, 20h
0x18000b00e  mov     ebx, r9d
0x18000b011  mov     [rsp+38h+arg_0], 0
0x18000b01a  mov     ebp, r8d
0x18000b01d  mov     r14, rdx
0x18000b020  mov     rdi, rcx
0x18000b023  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000b029  lea     r9, [rsp+38h+arg_0]; struct LISTENER_CHANNEL **
0x18000b02e  mov     r8d, ebp; unsigned int
0x18000b031  mov     rdx, r14; unsigned __int16 *
0x18000b034  mov     rcx, rdi; this
0x18000b037  call    ?RemoveListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBGKPEAPEAVLISTENER_CHANNEL@@@Z; LISTENER_CHANNEL_LIST_MANAGER::RemoveListenerChannel(ushort const *,ulong,LISTENER_CHANNEL * *)
0x18000b03c  mov     esi, eax
0x18000b03e  test    eax, eax
0x18000b040  js      short loc_18000B062
0x18000b042  mov     edx, ebx; int
0x18000b044  mov     rbx, [rsp+38h+arg_0]
0x18000b049  mov     rcx, rbx; this
0x18000b04c  call    ?StopListenerChannel@LISTENER_CHANNEL@@QEAAJH@Z; LISTENER_CHANNEL::StopListenerChannel(int)
0x18000b051  mov     esi, eax
0x18000b053  mov     rcx, rbx
0x18000b056  mov     rax, [rbx]
0x18000b059  mov     rax, [rax+8]
0x18000b05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b062  mov     rcx, rdi
0x18000b065  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b06b  test    esi, esi
0x18000b06d  jns     short loc_18000B088
0x18000b06f  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000b076  mov     r9d, esi; int
0x18000b079  mov     r8d, ebp; unsigned int
0x18000b07c  mov     rdx, r14; Src
0x18000b07f  mov     rcx, [rcx+58h]; this
0x18000b083  call    ?ReportListenerChannelStopped@WP_IPM@@QEAAXPEBGKJ@Z; WP_IPM::ReportListenerChannelStopped(ushort const *,ulong,long)
0x18000b088  lock dec dword ptr [rdi+18h]
0x18000b08c  mov     eax, esi
0x18000b08e  mov     rbx, [rsp+38h+arg_8]
0x18000b093  mov     rbp, [rsp+38h+arg_10]
0x18000b098  add     rsp, 20h
0x18000b09c  pop     r14
0x18000b09e  pop     rdi
0x18000b09f  pop     rsi
0x18000b0a0  retn
```
