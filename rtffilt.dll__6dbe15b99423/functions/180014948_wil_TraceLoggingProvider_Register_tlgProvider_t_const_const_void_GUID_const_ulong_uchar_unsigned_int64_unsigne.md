# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180014948`
- end: `0x180014a06`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e034`
- `0x1800143b4`

## callees

- `0x180001e40`
- `0x180014948`
- `0x18001b010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800149b5`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800149b5`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800149cd`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800149cd`

## pseudocode

```c
void __fastcall wil::TraceLoggingProvider::Register(
        wil::TraceLoggingProvider *this,
        const struct _tlgProvider_t *const a2,
        void (*a3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))
{
  _QWORD *v3; // rsi
  bool v5; // zf
  __int64 v7; // rax
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  *((_QWORD *)this + 1) = a2;
  v3 = (_QWORD *)((char *)a2 + 32);
  *((_BYTE *)this + 16) = 1;
  v5 = *((_QWORD *)a2 + 4) == 0;
  ProviderId = *(GUID *)(*((_QWORD *)a2 + 1) - 16LL);
  if ( !v5 )
    __fastfail(5u);
  *((_QWORD *)a2 + 5) = 0;
  *((_QWORD *)a2 + 6) = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, a2, (PREGHANDLE)a2 + 4) )
    EventSetInformation(
      *v3,
      2,
      *((_QWORD *)a2 + 1),
      **((unsigned __int16 **)a2 + 1),
      *(_QWORD *)&ProviderId.Data1,
      *(_QWORD *)ProviderId.Data4);
  v7 = *(_QWORD *)this;
  *((_DWORD *)this + 5) = 1;
  (*(void (__fastcall **)(wil::TraceLoggingProvider *))(v7 + 8))(this);
}

```

## disassembly

```asm
0x180014948  mov     [rsp+arg_10], rbx
0x18001494d  mov     [rsp+arg_18], rsi
0x180014952  push    rdi
0x180014953  sub     rsp, 40h
0x180014957  mov     rax, cs:__security_cookie
0x18001495e  xor     rax, rsp
0x180014961  mov     [rsp+48h+var_18], rax
0x180014966  mov     [rcx+8], rdx
0x18001496a  lea     rsi, [rdx+20h]
0x18001496e  mov     byte ptr [rcx+10h], 1
0x180014972  mov     rdi, rdx
0x180014975  cmp     qword ptr [rsi], 0
0x180014979  mov     rbx, rcx
0x18001497c  mov     rax, [rdx+8]
0x180014980  movups  xmm0, xmmword ptr [rax-10h]
0x180014984  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x18001498a  jz      short loc_180014993
0x18001498c  mov     ecx, 5
0x180014991  int     29h; Win8: RtlFailFast(ecx)
0x180014993  mov     qword ptr [rdx+28h], 0
0x18001499b  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x1800149a0  mov     qword ptr [rdx+30h], 0
0x1800149a8  mov     r9, rsi; RegHandle
0x1800149ab  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800149b2  mov     r8, rdi; CallbackContext
0x1800149b5  call    cs:__imp_EventRegister
0x1800149bb  test    eax, eax
0x1800149bd  jnz     short loc_1800149D3
0x1800149bf  mov     r8, [rdi+8]
0x1800149c3  lea     edx, [rax+2]
0x1800149c6  mov     rcx, [rsi]
0x1800149c9  movzx   r9d, word ptr [r8]
0x1800149cd  call    cs:__imp_EventSetInformation
0x1800149d3  mov     rax, [rbx]
0x1800149d6  mov     rcx, rbx
0x1800149d9  mov     dword ptr [rbx+14h], 1
0x1800149e0  mov     rax, [rax+8]
0x1800149e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149e9  mov     rcx, [rsp+48h+var_18]
0x1800149ee  xor     rcx, rsp; StackCookie
0x1800149f1  call    __security_check_cookie
0x1800149f6  mov     rbx, [rsp+48h+arg_10]
0x1800149fb  mov     rsi, [rsp+48h+arg_18]
0x180014a00  add     rsp, 40h
0x180014a04  pop     rdi
0x180014a05  retn
```
