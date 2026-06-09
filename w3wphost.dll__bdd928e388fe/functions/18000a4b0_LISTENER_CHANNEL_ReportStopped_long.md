# LISTENER_CHANNEL::ReportStopped(long)

- ea: `0x18000a4b0`
- end: `0x18000a5e0`
- name: `?ReportStopped@LISTENER_CHANNEL@@UEAAJJ@Z`
- size: `304`
- prototype: `int(LISTENER_CHANNEL *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180007f8c`
- `0x18000a4b0`
- `0x18000ab2c`
- `0x18000d010`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a4e4`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a542`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a4e4`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a542`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a4cf`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a528`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a4cf`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a528`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a51c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a566`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a51c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a566`

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
0x18000a4b0  push    rbx
0x18000a4b2  push    rbp
0x18000a4b3  push    rsi
0x18000a4b4  push    rdi
0x18000a4b5  push    r12
0x18000a4b7  push    r14
0x18000a4b9  push    r15
0x18000a4bb  sub     rsp, 20h
0x18000a4bf  lea     r15, [rcx+118h]
0x18000a4c6  mov     r14, rcx
0x18000a4c9  mov     rcx, r15
0x18000a4cc  mov     r12d, edx
0x18000a4cf  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000a4d5  cmp     dword ptr [r14+124h], 0
0x18000a4dd  jz      short loc_18000A506
0x18000a4df  xor     edi, edi
0x18000a4e1  mov     rcx, r15
0x18000a4e4  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000a4ea  test    edi, edi
0x18000a4ec  jz      short loc_18000A4F5
0x18000a4ee  lock dec cs:?s_lNotStoppedCount@LISTENER_CHANNEL@@0JA; long LISTENER_CHANNEL::s_lNotStoppedCount
0x18000a4f5  xor     eax, eax
0x18000a4f7  add     rsp, 20h
0x18000a4fb  pop     r15
0x18000a4fd  pop     r14
0x18000a4ff  pop     r12
0x18000a501  pop     rdi
0x18000a502  pop     rsi
0x18000a503  pop     rbp
0x18000a504  pop     rbx
0x18000a505  retn
0x18000a506  mov     rsi, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000a50d  lea     rcx, [r14+10h]
0x18000a511  mov     edi, [r14+48h]
0x18000a515  add     rsi, 170h
0x18000a51c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a522  mov     rcx, rsi
0x18000a525  mov     rbx, rax
0x18000a528  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000a52e  xor     r9d, r9d; struct LISTENER_CHANNEL **
0x18000a531  mov     r8d, edi; unsigned int
0x18000a534  mov     rdx, rbx; unsigned __int16 *
0x18000a537  mov     rcx, rsi; this
0x18000a53a  call    ?RemoveListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBGKPEAPEAVLISTENER_CHANNEL@@@Z; LISTENER_CHANNEL_LIST_MANAGER::RemoveListenerChannel(ushort const *,ulong,LISTENER_CHANNEL * *)
0x18000a53f  mov     rcx, rsi
0x18000a542  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000a548  mov     rax, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000a54f  lea     rcx, [r14+10h]
0x18000a553  mov     ebx, [r14+48h]
0x18000a557  mov     dword ptr [r14+108h], 5
0x18000a562  mov     rdi, [rax+58h]
0x18000a566  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a56c  mov     r9d, r12d; int
0x18000a56f  mov     r8d, ebx; unsigned int
0x18000a572  mov     rdx, rax; Src
0x18000a575  mov     rcx, rdi; this
0x18000a578  call    ?ReportListenerChannelStopped@WP_IPM@@QEAAXPEBGKJ@Z; WP_IPM::ReportListenerChannelStopped(ushort const *,ulong,long)
0x18000a57d  mov     edi, 1
0x18000a582  lea     rbx, [r14+128h]
0x18000a589  mov     [r14+124h], edi
0x18000a590  mov     rax, [rbx]
0x18000a593  cmp     rax, rbx
0x18000a596  jz      loc_18000A4E1
0x18000a59c  cmp     [rax+8], rbx
0x18000a5a0  jnz     short loc_18000A5D9
0x18000a5a2  mov     rcx, [rax]
0x18000a5a5  cmp     [rcx+8], rax
0x18000a5a9  jnz     short loc_18000A5D9
0x18000a5ab  mov     [rbx], rcx
0x18000a5ae  mov     [rcx+8], rbx
0x18000a5b2  lea     rcx, [rax-10h]
0x18000a5b6  mov     qword ptr [rax], 0
0x18000a5bd  mov     qword ptr [rax+8], 0
0x18000a5c5  test    rcx, rcx
0x18000a5c8  jz      short loc_18000A590
0x18000a5ca  mov     rax, [rcx]
0x18000a5cd  mov     edx, edi
0x18000a5cf  mov     rax, [rax]
0x18000a5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5d7  jmp     short loc_18000A590
0x18000a5d9  mov     ecx, 3
0x18000a5de  int     29h; Win8: RtlFailFast(ecx)
```
