# LISTENER_CHANNEL::ReportStopped(long)

- ea: `0x18000b1a0`
- end: `0x18000b2f5`
- name: `?ReportStopped@LISTENER_CHANNEL@@UEAAJJ@Z`
- size: `341`
- prototype: `int(LISTENER_CHANNEL *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180008818`
- `0x18000b1a0`
- `0x18000b838`
- `0x18000e010`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b1da`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b24b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b1da`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b24b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b1bf`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b22b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b1bf`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b22b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b219`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b275`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b219`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b275`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL::ReportStopped(LISTENER_CHANNEL *this, int a2)
{
  CReaderWriterLock3 *v2; // r15
  int v5; // edi
  unsigned int v7; // edi
  CReaderWriterLock3 *v8; // rsi
  const unsigned __int16 *Str; // rbx
  W3WP_HOST *v10; // rax
  WP_IPM *v11; // rdi
  const unsigned __int16 *v12; // rax
  _QWORD **v13; // rbx
  _QWORD *v14; // rax
  _QWORD *v15; // rcx

  v2 = (LISTENER_CHANNEL *)((char *)this + 280);
  CReaderWriterLock3::WriteLock((LISTENER_CHANNEL *)((char *)this + 280));
  if ( *((_DWORD *)this + 73) )
  {
    v5 = 0;
  }
  else
  {
    v7 = *((_DWORD *)this + 18);
    v8 = (W3WP_HOST *)((char *)g_pW3WPHost + 368);
    Str = STRU::QueryStr((LISTENER_CHANNEL *)((char *)this + 16));
    CReaderWriterLock3::WriteLock(v8);
    LISTENER_CHANNEL_LIST_MANAGER::RemoveListenerChannel(v8, Str, v7, 0);
    CReaderWriterLock3::WriteUnlock(v8);
    v10 = g_pW3WPHost;
    LODWORD(Str) = *((_DWORD *)this + 18);
    *((_DWORD *)this + 66) = 5;
    v11 = (WP_IPM *)*((_QWORD *)v10 + 11);
    v12 = STRU::QueryStr((LISTENER_CHANNEL *)((char *)this + 16));
    WP_IPM::ReportListenerChannelStopped(v11, v12, (unsigned int)Str, a2);
    v5 = 1;
    v13 = (_QWORD **)((char *)this + 296);
    *((_DWORD *)this + 73) = 1;
    while ( 1 )
    {
      v14 = *v13;
      if ( *v13 == v13 )
        break;
      if ( (_QWORD **)v14[1] != v13 || (v15 = (_QWORD *)*v14, *(_QWORD **)(*v14 + 8LL) != v14) )
        __fastfail(3u);
      *v13 = v15;
      v15[1] = v13;
      *v14 = 0;
      v14[1] = 0;
      if ( v14 != (_QWORD *)16 )
        (*(void (__fastcall **)(_QWORD *, __int64))*(v14 - 2))(v14 - 2, 1);
    }
  }
  CReaderWriterLock3::WriteUnlock(v2);
  if ( v5 )
    _InterlockedDecrement(&LISTENER_CHANNEL::s_lNotStoppedCount);
  return 0;
}

```

## disassembly

```asm
0x18000b1a0  push    rbx
0x18000b1a2  push    rbp
0x18000b1a3  push    rsi
0x18000b1a4  push    rdi
0x18000b1a5  push    r12
0x18000b1a7  push    r14
0x18000b1a9  push    r15
0x18000b1ab  sub     rsp, 20h
0x18000b1af  lea     r15, [rcx+118h]
0x18000b1b6  mov     r14, rcx
0x18000b1b9  mov     rcx, r15
0x18000b1bc  mov     r12d, edx
0x18000b1bf  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000b1c6  nop     dword ptr [rax+rax+00h]
0x18000b1cb  cmp     dword ptr [r14+124h], 0
0x18000b1d3  jz      short loc_18000B203
0x18000b1d5  xor     edi, edi
0x18000b1d7  mov     rcx, r15
0x18000b1da  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b1e1  nop     dword ptr [rax+rax+00h]
0x18000b1e6  test    edi, edi
0x18000b1e8  jz      short loc_18000B1F1
0x18000b1ea  lock dec cs:?s_lNotStoppedCount@LISTENER_CHANNEL@@0JA; long LISTENER_CHANNEL::s_lNotStoppedCount
0x18000b1f1  xor     eax, eax
0x18000b1f3  add     rsp, 20h
0x18000b1f7  pop     r15
0x18000b1f9  pop     r14
0x18000b1fb  pop     r12
0x18000b1fd  pop     rdi
0x18000b1fe  pop     rsi
0x18000b1ff  pop     rbp
0x18000b200  pop     rbx
0x18000b201  retn
0x18000b203  mov     rsi, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000b20a  lea     rcx, [r14+10h]
0x18000b20e  mov     edi, [r14+48h]
0x18000b212  add     rsi, 170h
0x18000b219  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b220  nop     dword ptr [rax+rax+00h]
0x18000b225  mov     rcx, rsi
0x18000b228  mov     rbx, rax
0x18000b22b  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000b232  nop     dword ptr [rax+rax+00h]
0x18000b237  xor     r9d, r9d; struct LISTENER_CHANNEL **
0x18000b23a  mov     r8d, edi; unsigned int
0x18000b23d  mov     rdx, rbx; unsigned __int16 *
0x18000b240  mov     rcx, rsi; this
0x18000b243  call    ?RemoveListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBGKPEAPEAVLISTENER_CHANNEL@@@Z; LISTENER_CHANNEL_LIST_MANAGER::RemoveListenerChannel(ushort const *,ulong,LISTENER_CHANNEL * *)
0x18000b248  mov     rcx, rsi
0x18000b24b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b252  nop     dword ptr [rax+rax+00h]
0x18000b257  mov     rax, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000b25e  lea     rcx, [r14+10h]
0x18000b262  mov     ebx, [r14+48h]
0x18000b266  mov     dword ptr [r14+108h], 5
0x18000b271  mov     rdi, [rax+58h]
0x18000b275  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b27c  nop     dword ptr [rax+rax+00h]
0x18000b281  mov     r9d, r12d; int
0x18000b284  mov     r8d, ebx; unsigned int
0x18000b287  mov     rdx, rax; Src
0x18000b28a  mov     rcx, rdi; this
0x18000b28d  call    ?ReportListenerChannelStopped@WP_IPM@@QEAAXPEBGKJ@Z; WP_IPM::ReportListenerChannelStopped(ushort const *,ulong,long)
0x18000b292  mov     edi, 1
0x18000b297  lea     rbx, [r14+128h]
0x18000b29e  mov     [r14+124h], edi
0x18000b2a5  mov     rax, [rbx]
0x18000b2a8  cmp     rax, rbx
0x18000b2ab  jz      loc_18000B1D7
0x18000b2b1  cmp     [rax+8], rbx
0x18000b2b5  jnz     short loc_18000B2EE
0x18000b2b7  mov     rcx, [rax]
0x18000b2ba  cmp     [rcx+8], rax
0x18000b2be  jnz     short loc_18000B2EE
0x18000b2c0  mov     [rbx], rcx
0x18000b2c3  mov     [rcx+8], rbx
0x18000b2c7  lea     rcx, [rax-10h]
0x18000b2cb  mov     qword ptr [rax], 0
0x18000b2d2  mov     qword ptr [rax+8], 0
0x18000b2da  test    rcx, rcx
0x18000b2dd  jz      short loc_18000B2A5
0x18000b2df  mov     rax, [rcx]
0x18000b2e2  mov     edx, edi
0x18000b2e4  mov     rax, [rax]
0x18000b2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2ec  jmp     short loc_18000B2A5
0x18000b2ee  mov     ecx, 3
0x18000b2f3  int     29h; Win8: RtlFailFast(ecx)
```
