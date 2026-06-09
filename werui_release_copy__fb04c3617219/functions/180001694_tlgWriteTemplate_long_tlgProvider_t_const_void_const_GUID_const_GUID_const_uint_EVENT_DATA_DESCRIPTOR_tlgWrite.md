# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001694`
- end: `0x180001739`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `165`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800115c4`
- `0x180011af0`
- `0x18001275c`

## callees

- `0x180001260`
- `0x180001694`
- `0x180016c50`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const LPARAM **a5,
        __int64 a6)
{
  const LPARAM *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-58h] BYREF
  const LPARAM *v11; // [rsp+50h] [rbp-38h]
  int v12; // [rsp+58h] [rbp-30h]
  int v13; // [rsp+5Ch] [rbp-2Ch]
  __int64 v14; // [rsp+60h] [rbp-28h]
  __int64 v15; // [rsp+68h] [rbp-20h]

  v14 = a6;
  v15 = 4;
  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)v6 + v7) );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &lParam;
    v8 = 2;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180022000, a2, 0, 0, 4u, &v10);
}

```

## disassembly

```asm
0x180001694  sub     rsp, 88h
0x18000169b  mov     rax, cs:__security_cookie
0x1800016a2  xor     rax, rsp
0x1800016a5  mov     [rsp+88h+var_18], rax
0x1800016aa  mov     rax, [rsp+88h+arg_28]
0x1800016b2  xor     r8d, r8d
0x1800016b5  mov     [rsp+88h+var_28], rax
0x1800016ba  mov     r9d, 4
0x1800016c0  mov     rax, [rsp+88h+arg_20]
0x1800016c8  mov     [rsp+88h+var_20], r9
0x1800016cd  mov     rcx, [rax]
0x1800016d0  test    rcx, rcx
0x1800016d3  jz      short loc_1800016EC
0x1800016d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800016d9  inc     rax
0x1800016dc  cmp     [rcx+rax*2], r8w
0x1800016e1  jnz     short loc_1800016D9
0x1800016e3  lea     eax, ds:2[rax*2]
0x1800016ea  jmp     short loc_1800016F8
0x1800016ec  lea     rcx, lParam
0x1800016f3  mov     eax, 2
0x1800016f8  mov     [rsp+88h+var_30], eax
0x1800016fc  lea     rax, [rsp+88h+var_58]
0x180001701  mov     [rsp+88h+var_60], rax
0x180001706  mov     [rsp+88h+var_68], r9d
0x18000170b  xor     r9d, r9d
0x18000170e  mov     [rsp+88h+var_38], rcx
0x180001713  lea     rcx, dword_180022000
0x18000171a  mov     [rsp+88h+var_2C], r8d
0x18000171f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001724  mov     rcx, [rsp+88h+var_18]
0x180001729  xor     rcx, rsp; StackCookie
0x18000172c  call    __security_check_cookie
0x180001731  add     rsp, 88h
0x180001738  retn
```
