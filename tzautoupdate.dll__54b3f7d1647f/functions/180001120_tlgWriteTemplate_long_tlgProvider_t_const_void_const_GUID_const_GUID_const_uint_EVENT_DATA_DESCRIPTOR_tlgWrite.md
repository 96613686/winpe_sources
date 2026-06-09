# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001120`
- end: `0x1800011dc`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800094c0`

## callees

- `0x180001120`
- `0x18000169c`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
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
    while ( *((_BYTE *)v7 + v8) );
    v9 = v8 + 1;
  }
  else
  {
    v7 = &word_180021DC6;
    v9 = 1;
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
0x180001120  sub     rsp, 98h
0x180001127  mov     rax, cs:__security_cookie
0x18000112e  xor     rax, rsp
0x180001131  mov     [rsp+98h+var_18], rax
0x180001139  mov     rax, [rsp+98h+arg_30]
0x180001141  xor     r8d, r8d
0x180001144  mov     [rsp+98h+var_28], rax
0x180001149  mov     rax, [rsp+98h+arg_28]
0x180001151  mov     [rsp+98h+var_20], 4
0x18000115a  mov     rcx, [rax]
0x18000115d  test    rcx, rcx
0x180001160  jz      short loc_180001173
0x180001162  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001166  inc     rax
0x180001169  cmp     [rcx+rax], r8b
0x18000116d  jnz     short loc_180001166
0x18000116f  inc     eax
0x180001171  jmp     short loc_18000117F
0x180001173  lea     rcx, word_180021DC6
0x18000117a  mov     eax, 1
0x18000117f  mov     [rsp+98h+var_30], eax
0x180001183  xor     r9d, r9d
0x180001186  mov     rax, [rsp+98h+arg_20]
0x18000118e  mov     [rsp+98h+var_48], rax
0x180001193  lea     rax, [rsp+98h+var_68]
0x180001198  mov     [rsp+98h+var_38], rcx
0x18000119d  lea     rcx, dword_180030000
0x1800011a4  mov     [rsp+98h+var_70], rax
0x1800011a9  mov     [rsp+98h+var_78], 5
0x1800011b1  mov     [rsp+98h+var_2C], r8d
0x1800011b6  mov     [rsp+98h+var_40], 8
0x1800011bf  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011c4  mov     rcx, [rsp+98h+var_18]
0x1800011cc  xor     rcx, rsp; StackCookie
0x1800011cf  call    __security_check_cookie
0x1800011d4  add     rsp, 98h
0x1800011db  retn
```
