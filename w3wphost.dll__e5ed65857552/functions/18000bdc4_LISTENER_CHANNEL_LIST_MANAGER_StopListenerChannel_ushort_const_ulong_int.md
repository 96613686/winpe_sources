# LISTENER_CHANNEL_LIST_MANAGER::StopListenerChannel(ushort const *,ulong,int)

- ea: `0x18000bdc4`
- end: `0x18000be76`
- name: `?StopListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBGKH@Z`
- size: `178`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL_LIST_MANAGER *__hidden this, const unsigned __int16 *Src, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800075dc`

## callees

- `0x180008818`
- `0x18000b4ec`
- `0x18000b838`
- `0x18000bdc4`
- `0x18000e010`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000be33`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000be33`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bdeb`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000bdeb`

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
0x18000bdc4  mov     [rsp+arg_8], rbx
0x18000bdc9  mov     [rsp+arg_10], rbp
0x18000bdce  push    rsi
0x18000bdcf  push    rdi
0x18000bdd0  push    r14
0x18000bdd2  sub     rsp, 20h
0x18000bdd6  mov     ebx, r9d
0x18000bdd9  mov     [rsp+38h+arg_0], 0
0x18000bde2  mov     ebp, r8d
0x18000bde5  mov     r14, rdx
0x18000bde8  mov     rdi, rcx
0x18000bdeb  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000bdf2  nop     dword ptr [rax+rax+00h]
0x18000bdf7  lea     r9, [rsp+38h+arg_0]; struct LISTENER_CHANNEL **
0x18000bdfc  mov     r8d, ebp; unsigned int
0x18000bdff  mov     rdx, r14; unsigned __int16 *
0x18000be02  mov     rcx, rdi; this
0x18000be05  call    ?RemoveListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBGKPEAPEAVLISTENER_CHANNEL@@@Z; LISTENER_CHANNEL_LIST_MANAGER::RemoveListenerChannel(ushort const *,ulong,LISTENER_CHANNEL * *)
0x18000be0a  mov     esi, eax
0x18000be0c  test    eax, eax
0x18000be0e  js      short loc_18000BE30
0x18000be10  mov     edx, ebx; int
0x18000be12  mov     rbx, [rsp+38h+arg_0]
0x18000be17  mov     rcx, rbx; this
0x18000be1a  call    ?StopListenerChannel@LISTENER_CHANNEL@@QEAAJH@Z; LISTENER_CHANNEL::StopListenerChannel(int)
0x18000be1f  mov     esi, eax
0x18000be21  mov     rcx, rbx
0x18000be24  mov     rax, [rbx]
0x18000be27  mov     rax, [rax+8]
0x18000be2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be30  mov     rcx, rdi
0x18000be33  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000be3a  nop     dword ptr [rax+rax+00h]
0x18000be3f  test    esi, esi
0x18000be41  jns     short loc_18000BE5C
0x18000be43  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000be4a  mov     r9d, esi; int
0x18000be4d  mov     r8d, ebp; unsigned int
0x18000be50  mov     rdx, r14; Src
0x18000be53  mov     rcx, [rcx+58h]; this
0x18000be57  call    ?ReportListenerChannelStopped@WP_IPM@@QEAAXPEBGKJ@Z; WP_IPM::ReportListenerChannelStopped(ushort const *,ulong,long)
0x18000be5c  lock dec dword ptr [rdi+18h]
0x18000be60  mov     eax, esi
0x18000be62  mov     rbx, [rsp+38h+arg_8]
0x18000be67  mov     rbp, [rsp+38h+arg_10]
0x18000be6c  add     rsp, 20h
0x18000be70  pop     r14
0x18000be72  pop     rdi
0x18000be73  pop     rsi
0x18000be74  retn
```
