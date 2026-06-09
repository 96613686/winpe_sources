# ThumbnailCacheLogging::Instance(void)

- ea: `0x18001f1c0`
- end: `0x18001f274`
- name: `?Instance@ThumbnailCacheLogging@@KAPEAV1@XZ`
- size: `180`
- prototype: `struct ThumbnailCacheLogging *(void)`
- caller_count: `73`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e280`
- `0x18000e584`
- `0x18000ef80`
- `0x18000f15c`
- `0x18000f27c`
- `0x18000f5b0`
- `0x18000f7d8`
- `0x18000ff2c`
- `0x1800103ec`
- `0x180011b70`
- `0x180015bd4`
- `0x18001a5c0`
- `0x18001b5ec`
- `0x18001c950`
- `0x18001ca80`
- `0x18001eee0`
- `0x180020154`
- `0x180020350`
- `0x180020470`
- `0x180024f64`
- `0x18002871c`
- `0x180028e1c`
- `0x18002b708`
- `0x18002d5d8`
- `0x18002e2d4`
- `0x18002fcb0`
- `0x1800301a0`
- `0x1800303e0`
- `0x180030620`
- `0x1800308dc`
- `0x180030984`
- `0x180030c10`
- `0x180030e50`
- `0x180031090`
- `0x1800312d0`
- `0x180031510`
- `0x180031750`
- `0x180031990`
- `0x180031bd0`
- `0x180031fa0`
- `0x1800321d4`
- `0x180032210`
- `0x180032450`
- `0x180032690`
- `0x1800328c4`
- `0x1800329f0`
- `0x180033010`
- `0x180033250`
- `0x180033df0`
- `0x180039eb4`

## callees

- `0x18001f1c0`
- `0x18001f27c`
- `0x180035c48`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001f1e4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001f1e4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001f267`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001f267`

## pseudocode

```c
struct ThumbnailCacheLogging *ThumbnailCacheLogging::Instance(void)
{
  void (*v1)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL fPending; // [rsp+30h] [rbp+8h] BYREF
  LPVOID Context; // [rsp+38h] [rbp+10h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`ThumbnailCacheLogging::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_1800628C8 = 0;
    Context = &qword_1800628C0;
    byte_1800628D0 = 0;
    dword_1800628D4 = 0;
    qword_1800628C0 = &ThumbnailCacheLogging::`vftable';
    qword_1800628D8 = (struct _tlgProvider_t *)&`ThumbnailCacheLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_b1b092cfbf8511623b79512cf00f3540_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800628C0, qword_1800628D8, v1);
    InitOnceComplete(&`ThumbnailCacheLogging::Instance'::`2'::wrapper, 0, &qword_1800628C0);
  }
  return (struct ThumbnailCacheLogging *)Context;
}

```

## disassembly

```asm
0x18001f1c0  push    rdi
0x18001f1c2  sub     rsp, 20h
0x18001f1c6  xor     edi, edi
0x18001f1c8  lea     r9, [rsp+28h+Context]; lpContext
0x18001f1cd  lea     r8, [rsp+28h+fPending]; fPending
0x18001f1d2  mov     [rsp+28h+Context], rdi
0x18001f1d7  xor     edx, edx; dwFlags
0x18001f1d9  mov     [rsp+28h+fPending], edi
0x18001f1dd  lea     rcx, ?wrapper@?1??Instance@ThumbnailCacheLogging@@KAPEAV2@XZ@4V?$static_lazy@VThumbnailCacheLogging@@@details@wil@@A; lpInitOnce
0x18001f1e4  call    cs:__imp_InitOnceBeginInitialize
0x18001f1ea  test    eax, eax
0x18001f1ec  jz      short loc_18001F1F4
0x18001f1ee  cmp     [rsp+28h+fPending], edi
0x18001f1f2  jnz     short loc_18001F1FF
0x18001f1f4  mov     rax, [rsp+28h+Context]
0x18001f1f9  add     rsp, 20h
0x18001f1fd  pop     rdi
0x18001f1fe  retn
0x18001f1ff  mov     [rsp+28h+arg_10], rbx
0x18001f204  lea     rax, ??_7ThumbnailCacheLogging@@6B@; const ThumbnailCacheLogging::`vftable'
0x18001f20b  lea     rbx, qword_1800628C0
0x18001f212  mov     cs:qword_1800628C8, rdi
0x18001f219  mov     [rsp+28h+Context], rbx
0x18001f21e  mov     cs:byte_1800628D0, dil
0x18001f225  mov     cs:dword_1800628D4, edi
0x18001f22b  mov     cs:qword_1800628C0, rax
0x18001f232  lea     rax, ?__hInner@?1???0StaticHandle@ThumbnailCacheLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ThumbnailCacheLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001f239  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b1b092cfbf8511623b79512cf00f3540_@@CA@XZ; void (__cdecl *)()
0x18001f240  mov     cs:qword_1800628D8, rax
0x18001f247  call    atexit
0x18001f24c  mov     rdx, cs:qword_1800628D8; struct _tlgProvider_t *
0x18001f253  mov     rcx, rbx; this
0x18001f256  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18001f25b  mov     r8, rbx; lpContext
0x18001f25e  lea     rcx, ?wrapper@?1??Instance@ThumbnailCacheLogging@@KAPEAV2@XZ@4V?$static_lazy@VThumbnailCacheLogging@@@details@wil@@A; lpInitOnce
0x18001f265  xor     edx, edx; dwFlags
0x18001f267  call    cs:__imp_InitOnceComplete
0x18001f26d  mov     rbx, [rsp+28h+arg_10]
0x18001f272  jmp     short loc_18001F1F4
```
