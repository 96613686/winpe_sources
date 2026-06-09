# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)

- ea: `0x1800017c0`
- end: `0x180001849`
- name: `??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, const WCHAR **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b31c`

## callees

- `0x180001158`
- `0x1800017c0`
- `0x18000fc90`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        int a1,
        int a2,
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
0x1800017c0  sub     rsp, 78h
0x1800017c4  mov     rax, cs:__security_cookie
0x1800017cb  xor     rax, rsp
0x1800017ce  mov     [rsp+78h+var_18], rax
0x1800017d3  mov     rax, [rsp+78h+arg_20]
0x1800017db  mov     r10, rcx
0x1800017de  xor     r8d, r8d; int
0x1800017e1  mov     rcx, [rax]
0x1800017e4  test    rcx, rcx
0x1800017e7  jz      short loc_180001800
0x1800017e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800017ed  inc     rax
0x1800017f0  cmp     [rcx+rax*2], r8w
0x1800017f5  jnz     short loc_1800017ED
0x1800017f7  lea     eax, ds:2[rax*2]
0x1800017fe  jmp     short loc_18000180C
0x180001800  lea     rcx, OutputString
0x180001807  mov     eax, 2
0x18000180c  mov     [rsp+78h+var_20], eax
0x180001810  xor     r9d, r9d; int
0x180001813  lea     rax, [rsp+78h+var_48]
0x180001818  mov     [rsp+78h+var_28], rcx
0x18000181d  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x180001822  mov     rcx, r10; int
0x180001825  mov     [rsp+78h+var_58], 3; ULONG
0x18000182d  mov     [rsp+78h+var_1C], r8d
0x180001832  call    _tlgWriteTransfer_EventWriteTransfer
0x180001837  mov     rcx, [rsp+78h+var_18]
0x18000183c  xor     rcx, rsp; StackCookie
0x18000183f  call    __security_check_cookie
0x180001844  add     rsp, 78h
0x180001848  retn
```
