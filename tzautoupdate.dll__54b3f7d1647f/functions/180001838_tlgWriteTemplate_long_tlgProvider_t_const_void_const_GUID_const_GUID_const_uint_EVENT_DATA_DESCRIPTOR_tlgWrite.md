# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001838`
- end: `0x1800018f6`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@5@Z`
- size: `190`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dc80`

## callees

- `0x18000169c`
- `0x180001838`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        __int64 a7,
        __int64 a8)
{
  const unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  _BYTE v12[32]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v13; // [rsp+50h] [rbp-19h]
  __int64 v14; // [rsp+58h] [rbp-11h]
  const unsigned __int16 *v15; // [rsp+60h] [rbp-9h]
  int v16; // [rsp+68h] [rbp-1h]
  int v17; // [rsp+6Ch] [rbp+3h]
  __int64 v18; // [rsp+70h] [rbp+7h]
  __int64 v19; // [rsp+78h] [rbp+Fh]
  __int64 v20; // [rsp+80h] [rbp+17h]
  __int64 v21; // [rsp+88h] [rbp+1Fh]

  v20 = a8;
  v18 = a7;
  v21 = 4;
  v19 = 4;
  v8 = *a6;
  if ( *a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &qword_180021DC8;
    v10 = 2;
  }
  v16 = v10;
  v13 = a5;
  v15 = v8;
  v17 = 0;
  v14 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 6, v12);
}

```

## disassembly

```asm
0x180001838  push    rbp
0x18000183a  lea     rbp, [rsp-37h]
0x18000183f  sub     rsp, 0A0h
0x180001846  mov     rax, cs:__security_cookie
0x18000184d  xor     rax, rsp
0x180001850  mov     [rbp+37h+var_10], rax
0x180001854  mov     rax, [rbp+37h+arg_38]
0x180001858  xor     r8d, r8d
0x18000185b  mov     [rbp+37h+var_20], rax
0x18000185f  mov     rax, [rbp+37h+arg_30]
0x180001863  mov     [rbp+37h+var_30], rax
0x180001867  mov     rax, [rbp+37h+arg_28]
0x18000186b  mov     [rbp+37h+var_18], 4
0x180001873  mov     [rbp+37h+var_28], 4
0x18000187b  mov     rcx, [rax]
0x18000187e  test    rcx, rcx
0x180001881  jz      short loc_18000189A
0x180001883  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001887  inc     rax
0x18000188a  cmp     [rcx+rax*2], r8w
0x18000188f  jnz     short loc_180001887
0x180001891  lea     eax, ds:2[rax*2]
0x180001898  jmp     short loc_1800018A6
0x18000189a  lea     rcx, qword_180021DC8
0x1800018a1  mov     eax, 2
0x1800018a6  mov     [rbp+37h+var_38], eax
0x1800018a9  xor     r9d, r9d
0x1800018ac  mov     rax, [rbp+37h+arg_20]
0x1800018b0  mov     [rbp+37h+var_50], rax
0x1800018b4  lea     rax, [rbp+37h+var_70]
0x1800018b8  mov     [rbp+37h+var_40], rcx
0x1800018bc  lea     rcx, dword_180030000
0x1800018c3  mov     [rsp+0A0h+var_78], rax
0x1800018c8  mov     [rsp+0A0h+var_80], 6
0x1800018d0  mov     [rbp+37h+var_34], r8d
0x1800018d4  mov     [rbp+37h+var_48], 8
0x1800018dc  call    _tlgWriteTransfer_EventWriteTransfer
0x1800018e1  mov     rcx, [rbp+37h+var_10]
0x1800018e5  xor     rcx, rsp; StackCookie
0x1800018e8  call    __security_check_cookie
0x1800018ed  add     rsp, 0A0h
0x1800018f4  pop     rbp
0x1800018f5  retn
```
