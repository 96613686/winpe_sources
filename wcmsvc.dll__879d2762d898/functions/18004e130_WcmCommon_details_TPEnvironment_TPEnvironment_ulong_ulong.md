# WcmCommon::details::TPEnvironment::TPEnvironment(ulong,ulong)

- ea: `0x18004e130`
- end: `0x18004e217`
- name: `??0TPEnvironment@details@WcmCommon@@QEAA@KK@Z`
- size: `231`
- prototype: `_QWORD(WcmCommon::details::TPEnvironment *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004e058`
- `0x1800999e4`

## callees

- `0x18004e130`
- `0x180072c04`
- `0x18007b57c`
- `0x180085bc4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18004e1a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18004e1a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18004e1fe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18004e1fe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18004e1dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18004e1dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WcmCommon::details::TPEnvironment *__fastcall WcmCommon::details::TPEnvironment::TPEnvironment(
        WcmCommon::details::TPEnvironment *this,
        __int64 a2,
        DWORD a3)
{
  PTP_POOL *v5; // rdi
  PTP_POOL Threadpool; // rax
  const char *v7; // r9
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  memset_0(this, 0, 0x48u);
  v5 = (PTP_POOL *)((char *)this + 72);
  *((_QWORD *)this + 9) = 0;
  *(_DWORD *)this = 3;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_DWORD *)this + 15) = 1;
  *((_DWORD *)this + 16) = 72;
  Threadpool = CreateThreadpool(0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(
    (char *)this + 72,
    Threadpool);
  if ( !*((_QWORD *)this + 9) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecore\\internal\\net\\inc\\wcm\\wcm_work_queue.h",
      v7);
  if ( !SetThreadpoolThreadMinimum(*v5, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\internal\\net\\inc\\wcm\\wcm_work_queue.h",
      v8);
  SetThreadpoolThreadMaximum(*v5, a3);
  *((_QWORD *)this + 1) = *v5;
  return this;
}

```

## disassembly

```asm
0x18004e130  mov     [rsp+arg_0], rcx
0x18004e135  push    rbx
0x18004e136  push    rbp
0x18004e137  push    rsi
0x18004e138  push    rdi
0x18004e139  sub     rsp, 28h
0x18004e13d  mov     ebp, r8d
0x18004e140  mov     rbx, rcx
0x18004e143  mov     esi, 48h ; 'H'
0x18004e148  mov     r8d, esi; Size
0x18004e14b  xor     edx, edx; Val
0x18004e14d  call    memset_0
0x18004e152  lea     rdi, [rbx+48h]
0x18004e156  mov     qword ptr [rdi], 0
0x18004e15d  mov     dword ptr [rbx], 3
0x18004e163  mov     qword ptr [rbx+8], 0
0x18004e16b  mov     qword ptr [rbx+10h], 0
0x18004e173  mov     qword ptr [rbx+18h], 0
0x18004e17b  mov     qword ptr [rbx+20h], 0
0x18004e183  mov     qword ptr [rbx+28h], 0
0x18004e18b  mov     qword ptr [rbx+30h], 0
0x18004e193  mov     dword ptr [rbx+38h], 0
0x18004e19a  mov     dword ptr [rbx+3Ch], 1
0x18004e1a1  mov     [rbx+40h], esi
0x18004e1a4  xor     ecx, ecx; reserved
0x18004e1a6  call    cs:__imp_CreateThreadpool
0x18004e1ac  mov     rdx, rax
0x18004e1af  mov     rcx, rdi
0x18004e1b2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_POOL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(_TP_POOL *)
0x18004e1b7  mov     rcx, [rsp+48h]; this
0x18004e1bc  cmp     qword ptr [rdi], 0
0x18004e1c0  jnz     short loc_18004E1D2
0x18004e1c2  lea     r8, aOnecoreInterna_9; "onecore\\internal\\net\\inc\\wcm\\wcm_w"...
0x18004e1c9  lea     edx, [rsi+22h]; void *
0x18004e1cc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004e1d2  mov     rsi, [rsp+48h]
0x18004e1d7  xor     edx, edx; cthrdMic
0x18004e1d9  mov     rcx, [rdi]; ptpp
0x18004e1dc  call    cs:__imp_SetThreadpoolThreadMinimum
0x18004e1e2  test    eax, eax
0x18004e1e4  jnz     short loc_18004E1F9
0x18004e1e6  lea     r8, aOnecoreInterna_9; "onecore\\internal\\net\\inc\\wcm\\wcm_w"...
0x18004e1ed  lea     edx, [rax+6Dh]; void *
0x18004e1f0  mov     rcx, rsi; this
0x18004e1f3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004e1f9  mov     edx, ebp; cthrdMost
0x18004e1fb  mov     rcx, [rdi]; ptpp
0x18004e1fe  call    cs:__imp_SetThreadpoolThreadMaximum
0x18004e204  mov     rax, [rdi]
0x18004e207  mov     [rbx+8], rax
0x18004e20b  mov     rax, rbx
0x18004e20e  add     rsp, 28h
0x18004e212  pop     rdi
0x18004e213  pop     rsi
0x18004e214  pop     rbp
0x18004e215  pop     rbx
0x18004e216  retn
```
