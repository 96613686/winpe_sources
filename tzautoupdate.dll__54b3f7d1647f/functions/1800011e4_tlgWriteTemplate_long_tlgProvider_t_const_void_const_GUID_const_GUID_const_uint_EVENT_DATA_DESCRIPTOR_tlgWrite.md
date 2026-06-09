# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800011e4`
- end: `0x18000128a`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bc30`
- `0x18000bf20`
- `0x18000dc80`
- `0x18000fa60`
- `0x1800101c0`
- `0x1800116bc`
- `0x18001307c`
- `0x180013e60`
- `0x1800140a0`
- `0x1800144ec`
- `0x180014704`
- `0x180014ec0`
- `0x180015bd0`

## callees

- `0x1800011e4`
- `0x18000169c`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6)
{
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _BYTE v10[32]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h]
  __int64 v12; // [rsp+58h] [rbp-30h]
  const unsigned __int16 *v13; // [rsp+60h] [rbp-28h]
  int v14; // [rsp+68h] [rbp-20h]
  int v15; // [rsp+6Ch] [rbp-1Ch]

  v6 = *a6;
  if ( *a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &qword_180021DC8;
    v8 = 2;
  }
  v14 = v8;
  v11 = a5;
  v13 = v6;
  v15 = 0;
  v12 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x1800011e4  sub     rsp, 88h
0x1800011eb  mov     rax, cs:__security_cookie
0x1800011f2  xor     rax, rsp
0x1800011f5  mov     [rsp+88h+var_18], rax
0x1800011fa  mov     rax, [rsp+88h+arg_28]
0x180001202  xor     r8d, r8d
0x180001205  mov     rcx, [rax]
0x180001208  test    rcx, rcx
0x18000120b  jz      short loc_180001224
0x18000120d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001211  inc     rax
0x180001214  cmp     [rcx+rax*2], r8w
0x180001219  jnz     short loc_180001211
0x18000121b  lea     eax, ds:2[rax*2]
0x180001222  jmp     short loc_180001230
0x180001224  lea     rcx, qword_180021DC8
0x18000122b  mov     eax, 2
0x180001230  mov     [rsp+88h+var_20], eax
0x180001234  xor     r9d, r9d
0x180001237  mov     rax, [rsp+88h+arg_20]
0x18000123f  mov     [rsp+88h+var_38], rax
0x180001244  lea     rax, [rsp+88h+var_58]
0x180001249  mov     [rsp+88h+var_28], rcx
0x18000124e  lea     rcx, dword_180030000
0x180001255  mov     [rsp+88h+var_60], rax
0x18000125a  mov     [rsp+88h+var_68], 4
0x180001262  mov     [rsp+88h+var_1C], r8d
0x180001267  mov     [rsp+88h+var_30], 8
0x180001270  call    _tlgWriteTransfer_EventWriteTransfer
0x180001275  mov     rcx, [rsp+88h+var_18]
0x18000127a  xor     rcx, rsp; StackCookie
0x18000127d  call    __security_check_cookie
0x180001282  add     rsp, 88h
0x180001289  retn
```
