# File::~File(void)

- ea: `0x18008aed8`
- end: `0x18008afd5`
- name: `??1File@@QEAA@XZ`
- size: `253`
- prototype: `void __fastcall(File *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800471c0`

## callees

- `0x180017b60`
- `0x18001c310`
- `0x18003420c`
- `0x180046938`
- `0x180048ffc`
- `0x18008aed8`
- `0x18008afdc`
- `0x18008d7a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008aef9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008aef9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18008af18`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18008af18`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008af0b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008af0b`

## pseudocode

```c
void __fastcall File::~File(File *this)
{
  struct _TP_TIMER *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 82);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 82), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 82));
    *((_QWORD *)this + 82) = 0;
  }
  if ( *((_BYTE *)this + 833) )
  {
    v3 = *((_QWORD *)this + 84);
    *((_QWORD *)this + 84) = 0;
    v5 = v3;
    CloseAndDelete(&v5);
  }
  else
  {
    File::FullFlush(this, 2);
  }
  *((_QWORD *)this + 96) = -1;
  _InterlockedDecrement(&g_ActiveChannels);
  utl::condition_variable_any::~condition_variable_any((File *)((char *)this + 744));
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 712);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 680);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 672);
  FileView::~FileView((File *)((char *)this + 160));
  v4 = *((_QWORD *)this + 18);
  if ( v4 )
    utl::_RefCountVtable<utl::_RefCountStored<PublisherManifestResource,utl::allocator<int>,0>,0>::_FreeRefCount(
      v4,
      128);
}

```

## disassembly

```asm
0x18008aed8  mov     [rsp+arg_0], rcx
0x18008aedd  push    rbx
0x18008aede  sub     rsp, 20h
0x18008aee2  mov     rbx, rcx
0x18008aee5  mov     rcx, [rcx+290h]; pti
0x18008aeec  test    rcx, rcx
0x18008aeef  jz      short loc_18008AF29
0x18008aef1  xor     r9d, r9d; msWindowLength
0x18008aef4  xor     r8d, r8d; msPeriod
0x18008aef7  xor     edx, edx; pftDueTime
0x18008aef9  call    cs:__imp_SetThreadpoolTimer
0x18008aeff  mov     edx, 1; fCancelPendingCallbacks
0x18008af04  mov     rcx, [rbx+290h]; pti
0x18008af0b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18008af11  mov     rcx, [rbx+290h]; pti
0x18008af18  call    cs:__imp_CloseThreadpoolTimer
0x18008af1e  mov     qword ptr [rbx+290h], 0
0x18008af29  cmp     byte ptr [rbx+341h], 0
0x18008af30  jz      short loc_18008AF55
0x18008af32  mov     rax, [rbx+2A0h]
0x18008af39  mov     qword ptr [rbx+2A0h], 0
0x18008af44  mov     [rsp+28h+arg_8], rax
0x18008af49  lea     rcx, [rsp+28h+arg_8]
0x18008af4e  call    CloseAndDelete
0x18008af53  jmp     short loc_18008AF63
0x18008af55  mov     edx, 2
0x18008af5a  mov     rcx, rbx
0x18008af5d  call    ?FullFlush@File@@QEAAKW4FlushType@@@Z; File::FullFlush(FlushType)
0x18008af62  nop
0x18008af63  jmp     short loc_18008AF6A
0x18008af65  mov     rbx, [rsp+28h+arg_0]
0x18008af6a  mov     qword ptr [rbx+300h], 0FFFFFFFFFFFFFFFFh
0x18008af75  lock dec cs:?g_ActiveChannels@@3JA; long g_ActiveChannels
0x18008af7c  lea     rcx, [rbx+2E8h]; this
0x18008af83  call    ??1condition_variable_any@utl@@QEAA@XZ; utl::condition_variable_any::~condition_variable_any(void)
0x18008af88  lea     rcx, [rbx+2C8h]; void *
0x18008af8f  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008af94  lea     rcx, [rbx+2A8h]; void *
0x18008af9b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008afa0  lea     rcx, [rbx+2A0h]
0x18008afa7  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18008afac  lea     rcx, [rbx+0A0h]; this
0x18008afb3  call    ??1FileView@@QEAA@XZ; FileView::~FileView(void)
0x18008afb8  mov     rcx, [rbx+90h]
0x18008afbf  test    rcx, rcx
0x18008afc2  jz      short loc_18008AFCF
0x18008afc4  mov     edx, 80h
0x18008afc9  call    ?_FreeRefCount@?$_RefCountVtable@V?$_RefCountStored@VPublisherManifestResource@@V?$allocator@H@utl@@$0A@@utl@@$0A@@utl@@UEAAXXZ; utl::_RefCountVtable<utl::_RefCountStored<PublisherManifestResource,utl::allocator<int>,0>,0>::_FreeRefCount(void)
0x18008afce  nop
0x18008afcf  add     rsp, 20h
0x18008afd3  pop     rbx
0x18008afd4  retn
```
