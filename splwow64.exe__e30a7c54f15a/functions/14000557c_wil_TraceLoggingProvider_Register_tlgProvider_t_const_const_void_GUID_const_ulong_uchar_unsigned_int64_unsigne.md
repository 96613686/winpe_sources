# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x14000557c`
- end: `0x14000563a`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140004d0c`
- `0x1400149d0`

## callees

- `0x140001ee0`
- `0x14000557c`
- `0x140016010`

## import_xrefs

- `ADVAPI32!EventSetInformation` at `0x140005601`
- `ADVAPI32!EventSetInformation` at `0x140005601`
- `ADVAPI32!EventRegister` at `0x1400055e9`
- `ADVAPI32!EventRegister` at `0x1400055e9`

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
0x14000557c  mov     [rsp+arg_10], rbx
0x140005581  mov     [rsp+arg_18], rsi
0x140005586  push    rdi
0x140005587  sub     rsp, 40h
0x14000558b  mov     rax, cs:__security_cookie
0x140005592  xor     rax, rsp
0x140005595  mov     [rsp+48h+var_18], rax
0x14000559a  mov     [rcx+8], rdx
0x14000559e  lea     rsi, [rdx+20h]
0x1400055a2  mov     byte ptr [rcx+10h], 1
0x1400055a6  mov     rdi, rdx
0x1400055a9  cmp     qword ptr [rsi], 0
0x1400055ad  mov     rbx, rcx
0x1400055b0  mov     rax, [rdx+8]
0x1400055b4  movups  xmm0, xmmword ptr [rax-10h]
0x1400055b8  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x1400055be  jz      short loc_1400055C7
0x1400055c0  mov     ecx, 5
0x1400055c5  int     29h; Win8: RtlFailFast(ecx)
0x1400055c7  mov     qword ptr [rdx+28h], 0
0x1400055cf  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x1400055d4  mov     qword ptr [rdx+30h], 0
0x1400055dc  mov     r9, rsi; RegHandle
0x1400055df  lea     rdx, _tlgEnableCallback; EnableCallback
0x1400055e6  mov     r8, rdi; CallbackContext
0x1400055e9  call    cs:__imp_EventRegister
0x1400055ef  test    eax, eax
0x1400055f1  jnz     short loc_140005607
0x1400055f3  mov     r8, [rdi+8]
0x1400055f7  lea     edx, [rax+2]
0x1400055fa  mov     rcx, [rsi]
0x1400055fd  movzx   r9d, word ptr [r8]
0x140005601  call    cs:__imp_EventSetInformation
0x140005607  mov     rax, [rbx]
0x14000560a  mov     rcx, rbx
0x14000560d  mov     dword ptr [rbx+14h], 1
0x140005614  mov     rax, [rax+8]
0x140005618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000561d  mov     rcx, [rsp+48h+var_18]
0x140005622  xor     rcx, rsp; StackCookie
0x140005625  call    __security_check_cookie
0x14000562a  mov     rbx, [rsp+48h+arg_10]
0x14000562f  mov     rsi, [rsp+48h+arg_18]
0x140005634  add     rsp, 40h
0x140005638  pop     rdi
0x140005639  retn
```
