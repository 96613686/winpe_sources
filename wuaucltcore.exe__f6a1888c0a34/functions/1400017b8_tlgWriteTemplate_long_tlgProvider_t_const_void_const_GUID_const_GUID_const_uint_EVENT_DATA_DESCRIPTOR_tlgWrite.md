# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)

- ea: `0x1400017b8`
- end: `0x140001841`
- name: `??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z`
- size: `137`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d5f4`

## callees

- `0x1400015b4`
- `0x1400017b8`
- `0x14001aa60`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const WCHAR **a5)
{
  const WCHAR *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-48h] BYREF
  const WCHAR *v11; // [rsp+50h] [rbp-28h]
  int v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+5Ch] [rbp-1Ch]

  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &OutputString;
    v8 = 2;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 3u, &v10);
}

```

## disassembly

```asm
0x1400017b8  sub     rsp, 78h
0x1400017bc  mov     rax, cs:__security_cookie
0x1400017c3  xor     rax, rsp
0x1400017c6  mov     [rsp+78h+var_18], rax
0x1400017cb  mov     rax, [rsp+78h+arg_20]
0x1400017d3  mov     r10, rcx
0x1400017d6  xor     r8d, r8d; int
0x1400017d9  mov     rcx, [rax]
0x1400017dc  test    rcx, rcx
0x1400017df  jz      short loc_1400017F8
0x1400017e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400017e5  inc     rax
0x1400017e8  cmp     [rcx+rax*2], r8w
0x1400017ed  jnz     short loc_1400017E5
0x1400017ef  lea     eax, ds:2[rax*2]
0x1400017f6  jmp     short loc_140001804
0x1400017f8  lea     rcx, OutputString
0x1400017ff  mov     eax, 2
0x140001804  mov     [rsp+78h+var_20], eax
0x140001808  xor     r9d, r9d; int
0x14000180b  lea     rax, [rsp+78h+var_48]
0x140001810  mov     [rsp+78h+var_28], rcx
0x140001815  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x14000181a  mov     rcx, r10; int
0x14000181d  mov     [rsp+78h+var_58], 3; ULONG
0x140001825  mov     [rsp+78h+var_1C], r8d
0x14000182a  call    _tlgWriteTransfer_EventWriteTransfer
0x14000182f  mov     rcx, [rsp+78h+var_18]
0x140001834  xor     rcx, rsp; StackCookie
0x140001837  call    __security_check_cookie
0x14000183c  add     rsp, 78h
0x140001840  retn
```
