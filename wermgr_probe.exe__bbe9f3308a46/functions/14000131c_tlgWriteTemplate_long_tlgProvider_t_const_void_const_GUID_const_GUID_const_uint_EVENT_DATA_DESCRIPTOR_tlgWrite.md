# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x14000131c`
- end: `0x1400013ea`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@55@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e49c`

## callees

- `0x14000131c`
- `0x14000162c`
- `0x140003200`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        void **a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  _WORD *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-51h] BYREF
  __int64 v14; // [rsp+50h] [rbp-31h]
  __int64 v15; // [rsp+58h] [rbp-29h]
  _WORD *v16; // [rsp+60h] [rbp-21h]
  int v17; // [rsp+68h] [rbp-19h]
  int v18; // [rsp+6Ch] [rbp-15h]
  __int64 v19; // [rsp+70h] [rbp-11h]
  __int64 v20; // [rsp+78h] [rbp-9h]
  __int64 v21; // [rsp+80h] [rbp-1h]
  __int64 v22; // [rsp+88h] [rbp+7h]
  __int64 v23; // [rsp+90h] [rbp+Fh]
  __int64 v24; // [rsp+98h] [rbp+17h]

  v23 = a9;
  v21 = a8;
  v19 = a7;
  v24 = 4;
  v22 = 4;
  v20 = 4;
  v9 = *a6;
  if ( *a6 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = &unk_1400241F4;
    v11 = 2;
  }
  v17 = v11;
  v14 = a5;
  v16 = v9;
  v18 = 0;
  v15 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14002C000, a2, 0, 0, 7u, &v13);
}

```

## disassembly

```asm
0x14000131c  push    rbp
0x14000131e  lea     rbp, [rsp-2Fh]
0x140001323  sub     rsp, 0B0h
0x14000132a  mov     rax, cs:__security_cookie
0x140001331  xor     rax, rsp
0x140001334  mov     [rbp+2Fh+var_10], rax
0x140001338  mov     rax, [rbp+2Fh+arg_40]
0x14000133c  xor     r8d, r8d
0x14000133f  mov     [rbp+2Fh+var_20], rax
0x140001343  mov     rax, [rbp+2Fh+arg_38]
0x140001347  mov     [rbp+2Fh+var_30], rax
0x14000134b  mov     rax, [rbp+2Fh+arg_30]
0x14000134f  mov     [rbp+2Fh+var_40], rax
0x140001353  mov     rax, [rbp+2Fh+arg_28]
0x140001357  mov     [rbp+2Fh+var_18], 4
0x14000135f  mov     [rbp+2Fh+var_28], 4
0x140001367  mov     [rbp+2Fh+var_38], 4
0x14000136f  mov     rcx, [rax]
0x140001372  test    rcx, rcx
0x140001375  jz      short loc_14000138E
0x140001377  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000137b  inc     rax
0x14000137e  cmp     [rcx+rax*2], r8w
0x140001383  jnz     short loc_14000137B
0x140001385  lea     eax, ds:2[rax*2]
0x14000138c  jmp     short loc_14000139A
0x14000138e  lea     rcx, unk_1400241F4
0x140001395  mov     eax, 2
0x14000139a  mov     [rbp+2Fh+var_48], eax
0x14000139d  xor     r9d, r9d
0x1400013a0  mov     rax, [rbp+2Fh+arg_20]
0x1400013a4  mov     [rbp+2Fh+var_60], rax
0x1400013a8  lea     rax, [rbp+2Fh+var_80]
0x1400013ac  mov     [rbp+2Fh+var_50], rcx
0x1400013b0  lea     rcx, dword_14002C000
0x1400013b7  mov     [rsp+0B0h+var_88], rax
0x1400013bc  mov     [rsp+0B0h+var_90], 7
0x1400013c4  mov     [rbp+2Fh+var_44], r8d
0x1400013c8  mov     [rbp+2Fh+var_58], 8
0x1400013d0  call    _tlgWriteTransfer_EventWriteTransfer
0x1400013d5  mov     rcx, [rbp+2Fh+var_10]
0x1400013d9  xor     rcx, rsp; StackCookie
0x1400013dc  call    __security_check_cookie
0x1400013e1  add     rsp, 0B0h
0x1400013e8  pop     rbp
0x1400013e9  retn
```
