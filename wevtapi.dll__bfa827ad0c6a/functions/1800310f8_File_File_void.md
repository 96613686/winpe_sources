# File::~File(void)

- ea: `0x1800310f8`
- end: `0x1800311e4`
- name: `??1File@@QEAA@XZ`
- size: `236`
- prototype: `void __fastcall(File *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180026688`

## callees

- `0x18000a724`
- `0x18001585c`
- `0x1800225a8`
- `0x1800310d4`
- `0x1800310f8`
- `0x1800311fc`
- `0x180031ec0`
- `0x180034fd8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180031138`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180031138`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180031119`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180031119`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003112b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003112b`

## pseudocode

```c
void __fastcall File::~File(File *this)
{
  struct _TP_TIMER *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

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
    v4 = v3;
    CloseAndDelete(&v4);
  }
  else
  {
    File::FullFlush(this);
  }
  *((_QWORD *)this + 96) = -1;
  _InterlockedDecrement(&g_ActiveChannels);
  utl::condition_variable_any::~condition_variable_any((File *)((char *)this + 744));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit((char *)this + 712);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit((char *)this + 680);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 672);
  FileView::~FileView((File *)((char *)this + 160));
  utl::unique_ptr<FileHeader,utl::default_delete<FileHeader>>::~unique_ptr<FileHeader,utl::default_delete<FileHeader>>((char *)this + 144);
}

```

## disassembly

```asm
0x1800310f8  mov     [rsp+arg_0], rcx
0x1800310fd  push    rbx
0x1800310fe  sub     rsp, 20h
0x180031102  mov     rbx, rcx
0x180031105  mov     rcx, [rcx+290h]; pti
0x18003110c  test    rcx, rcx
0x18003110f  jz      short loc_180031149
0x180031111  xor     r9d, r9d; msWindowLength
0x180031114  xor     r8d, r8d; msPeriod
0x180031117  xor     edx, edx; pftDueTime
0x180031119  call    cs:__imp_SetThreadpoolTimer
0x18003111f  mov     edx, 1; fCancelPendingCallbacks
0x180031124  mov     rcx, [rbx+290h]; pti
0x18003112b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180031131  mov     rcx, [rbx+290h]; pti
0x180031138  call    cs:__imp_CloseThreadpoolTimer
0x18003113e  mov     qword ptr [rbx+290h], 0
0x180031149  cmp     byte ptr [rbx+341h], 0
0x180031150  jz      short loc_180031175
0x180031152  mov     rax, [rbx+2A0h]
0x180031159  mov     qword ptr [rbx+2A0h], 0
0x180031164  mov     [rsp+28h+arg_8], rax
0x180031169  lea     rcx, [rsp+28h+arg_8]
0x18003116e  call    CloseAndDelete
0x180031173  jmp     short loc_18003117E
0x180031175  mov     rcx, rbx
0x180031178  call    ?FullFlush@File@@QEAAKW4FlushType@@@Z; File::FullFlush(FlushType)
0x18003117d  nop
0x18003117e  jmp     short loc_180031185
0x180031180  mov     rbx, [rsp+28h+arg_0]
0x180031185  mov     qword ptr [rbx+300h], 0FFFFFFFFFFFFFFFFh
0x180031190  lock dec cs:?g_ActiveChannels@@3JA; long g_ActiveChannels
0x180031197  lea     rcx, [rbx+2E8h]; this
0x18003119e  call    ??1condition_variable_any@utl@@QEAA@XZ; utl::condition_variable_any::~condition_variable_any(void)
0x1800311a3  lea     rcx, [rbx+2C8h]
0x1800311aa  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x1800311af  lea     rcx, [rbx+2A8h]
0x1800311b6  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x1800311bb  lea     rcx, [rbx+2A0h]
0x1800311c2  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800311c7  lea     rcx, [rbx+0A0h]; this
0x1800311ce  call    ??1FileView@@QEAA@XZ; FileView::~FileView(void)
0x1800311d3  lea     rcx, [rbx+90h]
0x1800311da  add     rsp, 20h
0x1800311de  pop     rbx
0x1800311df  jmp     ??1?$unique_ptr@UFileHeader@@U?$default_delete@UFileHeader@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<FileHeader,utl::default_delete<FileHeader>>::~unique_ptr<FileHeader,utl::default_delete<FileHeader>>(void)
```
