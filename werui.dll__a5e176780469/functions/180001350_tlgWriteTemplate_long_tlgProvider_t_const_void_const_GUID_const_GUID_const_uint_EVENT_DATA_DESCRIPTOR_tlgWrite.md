# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x180001350`
- end: `0x1800013da`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `138`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180011af0`
- `0x18001275c`
- `0x180012d68`

## callees

- `0x180001260`
- `0x180001350`
- `0x180016c50`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const LPARAM **a5)
{
  const LPARAM *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  const LPARAM *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)v5 + v6) );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v5 = &lParam;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180022000, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x180001350  sub     rsp, 78h
0x180001354  mov     rax, cs:__security_cookie
0x18000135b  xor     rax, rsp
0x18000135e  mov     [rsp+78h+var_18], rax
0x180001363  mov     rax, [rsp+78h+arg_20]
0x18000136b  xor     r8d, r8d
0x18000136e  mov     rcx, [rax]
0x180001371  test    rcx, rcx
0x180001374  jz      short loc_18000138D
0x180001376  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000137a  inc     rax
0x18000137d  cmp     [rcx+rax*2], r8w
0x180001382  jnz     short loc_18000137A
0x180001384  lea     eax, ds:2[rax*2]
0x18000138b  jmp     short loc_180001399
0x18000138d  lea     rcx, lParam
0x180001394  mov     eax, 2
0x180001399  mov     [rsp+78h+var_20], eax
0x18000139d  xor     r9d, r9d
0x1800013a0  lea     rax, [rsp+78h+var_48]
0x1800013a5  mov     [rsp+78h+var_28], rcx
0x1800013aa  mov     [rsp+78h+var_50], rax
0x1800013af  lea     rcx, dword_180022000
0x1800013b6  mov     [rsp+78h+var_58], 3
0x1800013be  mov     [rsp+78h+var_1C], r8d
0x1800013c3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800013c8  mov     rcx, [rsp+78h+var_18]
0x1800013cd  xor     rcx, rsp; StackCookie
0x1800013d0  call    __security_check_cookie
0x1800013d5  add     rsp, 78h
0x1800013d9  retn
```
