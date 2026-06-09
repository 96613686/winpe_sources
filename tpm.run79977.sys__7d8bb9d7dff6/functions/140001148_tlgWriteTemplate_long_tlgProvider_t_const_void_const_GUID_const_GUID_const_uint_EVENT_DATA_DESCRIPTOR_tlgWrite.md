# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001148`
- end: `0x14000120b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `195`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400116fc`
- `0x140016628`
- `0x1400171d0`

## callees

- `0x1400010a4`
- `0x140001148`
- `0x140039740`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 **a7)
{
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-68h] BYREF
  __int64 v12; // [rsp+50h] [rbp-48h]
  __int64 v13; // [rsp+58h] [rbp-40h]
  __int64 v14; // [rsp+60h] [rbp-38h]
  __int64 v15; // [rsp+68h] [rbp-30h]
  __int64 *v16; // [rsp+70h] [rbp-28h]
  int v17; // [rsp+78h] [rbp-20h]
  int v18; // [rsp+7Ch] [rbp-1Ch]

  v7 = *a7;
  if ( *a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)v7 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &qword_14003C270;
    v9 = 2;
  }
  v17 = v9;
  v14 = a6;
  v12 = a5;
  v16 = v7;
  v18 = 0;
  v15 = 4;
  v13 = 8;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_1400470A0, a2, 0, 0, 5u, &v11);
}

```

## disassembly

```asm
0x140001148  sub     rsp, 98h
0x14000114f  mov     rax, cs:__security_cookie
0x140001156  xor     rax, rsp
0x140001159  mov     [rsp+98h+var_18], rax
0x140001161  mov     rax, [rsp+98h+arg_30]
0x140001169  xor     r8d, r8d
0x14000116c  mov     rcx, [rax]
0x14000116f  test    rcx, rcx
0x140001172  jz      short loc_14000118B
0x140001174  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001178  inc     rax
0x14000117b  cmp     [rcx+rax*2], r8w
0x140001180  jnz     short loc_140001178
0x140001182  lea     eax, ds:2[rax*2]
0x140001189  jmp     short loc_140001197
0x14000118b  lea     rcx, qword_14003C270
0x140001192  mov     eax, 2
0x140001197  mov     [rsp+98h+var_20], eax
0x14000119b  xor     r9d, r9d
0x14000119e  mov     rax, [rsp+98h+arg_28]
0x1400011a6  mov     [rsp+98h+var_38], rax
0x1400011ab  mov     rax, [rsp+98h+arg_20]
0x1400011b3  mov     [rsp+98h+var_48], rax
0x1400011b8  lea     rax, [rsp+98h+var_68]
0x1400011bd  mov     [rsp+98h+var_28], rcx
0x1400011c2  lea     rcx, dword_1400470A0
0x1400011c9  mov     [rsp+98h+var_70], rax
0x1400011ce  mov     [rsp+98h+var_78], 5
0x1400011d6  mov     [rsp+98h+var_1C], r8d
0x1400011db  mov     [rsp+98h+var_30], 4
0x1400011e4  mov     [rsp+98h+var_40], 8
0x1400011ed  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400011f2  mov     rcx, [rsp+98h+var_18]
0x1400011fa  xor     rcx, rsp; StackCookie
0x1400011fd  call    __security_check_cookie
0x140001202  add     rsp, 98h
0x140001209  retn
```
