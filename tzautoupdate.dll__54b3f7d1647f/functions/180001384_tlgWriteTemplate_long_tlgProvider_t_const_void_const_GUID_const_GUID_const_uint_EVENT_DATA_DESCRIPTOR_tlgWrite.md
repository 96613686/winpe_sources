# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001384`
- end: `0x180001446`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bc30`

## callees

- `0x180001384`
- `0x18000169c`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        __int64 a7)
{
  const unsigned __int16 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _BYTE v11[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v12; // [rsp+50h] [rbp-48h]
  __int64 v13; // [rsp+58h] [rbp-40h]
  const unsigned __int16 *v14; // [rsp+60h] [rbp-38h]
  int v15; // [rsp+68h] [rbp-30h]
  int v16; // [rsp+6Ch] [rbp-2Ch]
  __int64 v17; // [rsp+70h] [rbp-28h]
  __int64 v18; // [rsp+78h] [rbp-20h]

  v17 = a7;
  v18 = 4;
  v7 = *a6;
  if ( *a6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &qword_180021DC8;
    v9 = 2;
  }
  v15 = v9;
  v12 = a5;
  v14 = v7;
  v16 = 0;
  v13 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 5, v11);
}

```

## disassembly

```asm
0x180001384  sub     rsp, 98h
0x18000138b  mov     rax, cs:__security_cookie
0x180001392  xor     rax, rsp
0x180001395  mov     [rsp+98h+var_18], rax
0x18000139d  mov     rax, [rsp+98h+arg_30]
0x1800013a5  xor     r8d, r8d
0x1800013a8  mov     [rsp+98h+var_28], rax
0x1800013ad  mov     rax, [rsp+98h+arg_28]
0x1800013b5  mov     [rsp+98h+var_20], 4
0x1800013be  mov     rcx, [rax]
0x1800013c1  test    rcx, rcx
0x1800013c4  jz      short loc_1800013DD
0x1800013c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800013ca  inc     rax
0x1800013cd  cmp     [rcx+rax*2], r8w
0x1800013d2  jnz     short loc_1800013CA
0x1800013d4  lea     eax, ds:2[rax*2]
0x1800013db  jmp     short loc_1800013E9
0x1800013dd  lea     rcx, qword_180021DC8
0x1800013e4  mov     eax, 2
0x1800013e9  mov     [rsp+98h+var_30], eax
0x1800013ed  xor     r9d, r9d
0x1800013f0  mov     rax, [rsp+98h+arg_20]
0x1800013f8  mov     [rsp+98h+var_48], rax
0x1800013fd  lea     rax, [rsp+98h+var_68]
0x180001402  mov     [rsp+98h+var_38], rcx
0x180001407  lea     rcx, dword_180030000
0x18000140e  mov     [rsp+98h+var_70], rax
0x180001413  mov     [rsp+98h+var_78], 5
0x18000141b  mov     [rsp+98h+var_2C], r8d
0x180001420  mov     [rsp+98h+var_40], 8
0x180001429  call    _tlgWriteTransfer_EventWriteTransfer
0x18000142e  mov     rcx, [rsp+98h+var_18]
0x180001436  xor     rcx, rsp; StackCookie
0x180001439  call    __security_check_cookie
0x18000143e  add     rsp, 98h
0x180001445  retn
```
