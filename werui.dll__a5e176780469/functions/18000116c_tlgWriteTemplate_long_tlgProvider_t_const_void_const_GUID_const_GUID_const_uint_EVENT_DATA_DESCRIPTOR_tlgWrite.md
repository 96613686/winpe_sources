# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000116c`
- end: `0x18000122d`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800090f8`
- `0x1800091b0`

## callees

- `0x18000116c`
- `0x180001260`
- `0x180016c50`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const LPARAM **a5,
        __int64 a6,
        __int64 a7)
{
  const LPARAM *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-68h] BYREF
  const LPARAM *v12; // [rsp+50h] [rbp-48h]
  int v13; // [rsp+58h] [rbp-40h]
  int v14; // [rsp+5Ch] [rbp-3Ch]
  __int64 v15; // [rsp+60h] [rbp-38h]
  __int64 v16; // [rsp+68h] [rbp-30h]
  __int64 v17; // [rsp+70h] [rbp-28h]
  __int64 v18; // [rsp+78h] [rbp-20h]

  v17 = a7;
  v15 = a6;
  v18 = 4;
  v16 = 8;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)v7 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &lParam;
    v9 = 2;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180022000, a2, 0, 0, 5u, &v11);
}

```

## disassembly

```asm
0x18000116c  mov     r11, rsp
0x18000116f  sub     rsp, 98h
0x180001176  mov     rax, cs:__security_cookie
0x18000117d  xor     rax, rsp
0x180001180  mov     [rsp+98h+var_18], rax
0x180001188  mov     rax, [rsp+98h+arg_30]
0x180001190  xor     r8d, r8d
0x180001193  mov     [r11-28h], rax
0x180001197  mov     rax, [rsp+98h+arg_28]
0x18000119f  mov     [r11-38h], rax
0x1800011a3  mov     rax, [rsp+98h+arg_20]
0x1800011ab  mov     qword ptr [r11-20h], 4
0x1800011b3  mov     qword ptr [r11-30h], 8
0x1800011bb  mov     rcx, [rax]
0x1800011be  test    rcx, rcx
0x1800011c1  jz      short loc_1800011DA
0x1800011c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800011c7  inc     rax
0x1800011ca  cmp     [rcx+rax*2], r8w
0x1800011cf  jnz     short loc_1800011C7
0x1800011d1  lea     eax, ds:2[rax*2]
0x1800011d8  jmp     short loc_1800011E6
0x1800011da  lea     rcx, lParam
0x1800011e1  mov     eax, 2
0x1800011e6  mov     [rsp+98h+var_40], eax
0x1800011ea  xor     r9d, r9d
0x1800011ed  lea     rax, [rsp+98h+var_68]
0x1800011f2  mov     [rsp+98h+var_48], rcx
0x1800011f7  mov     [rsp+98h+var_70], rax
0x1800011fc  lea     rcx, dword_180022000
0x180001203  mov     [rsp+98h+var_78], 5
0x18000120b  mov     [rsp+98h+var_3C], r8d
0x180001210  call    _tlgWriteTransfer_EventWriteTransfer
0x180001215  mov     rcx, [rsp+98h+var_18]
0x18000121d  xor     rcx, rsp; StackCookie
0x180001220  call    __security_check_cookie
0x180001225  add     rsp, 98h
0x18000122c  retn
```
