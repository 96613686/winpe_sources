# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001ba4`
- end: `0x180001c92`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@34@Z`
- size: `238`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014ec0`

## callees

- `0x18000169c`
- `0x180001ba4`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        __int64 a7,
        const unsigned __int16 **a8)
{
  __int64 v9; // rcx
  int v10; // r8d
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  _BYTE v16[32]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v17; // [rsp+50h] [rbp-19h]
  __int64 v18; // [rsp+58h] [rbp-11h]
  const unsigned __int16 *v19; // [rsp+60h] [rbp-9h]
  int v20; // [rsp+68h] [rbp-1h]
  int v21; // [rsp+6Ch] [rbp+3h]
  __int64 v22; // [rsp+70h] [rbp+7h]
  __int64 v23; // [rsp+78h] [rbp+Fh]
  const unsigned __int16 *v24; // [rsp+80h] [rbp+17h]
  int v25; // [rsp+88h] [rbp+1Fh]
  int v26; // [rsp+8Ch] [rbp+23h]

  v9 = -1;
  v10 = 2;
  v11 = *a8;
  if ( *a8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &qword_180021DC8;
    v13 = 2;
  }
  v25 = v13;
  v22 = a7;
  v24 = v11;
  v26 = 0;
  v23 = 8;
  v14 = *a6;
  if ( *a6 )
  {
    do
      ++v9;
    while ( v14[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v14 = &qword_180021DC8;
  }
  v17 = a5;
  v19 = v14;
  v20 = v10;
  v21 = 0;
  v18 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 6, v16);
}

```

## disassembly

```asm
0x180001ba4  push    rbp
0x180001ba6  lea     rbp, [rsp-37h]
0x180001bab  sub     rsp, 0A0h
0x180001bb2  mov     rax, cs:__security_cookie
0x180001bb9  xor     rax, rsp
0x180001bbc  mov     [rbp+37h+var_10], rax
0x180001bc0  mov     rax, [rbp+37h+arg_38]
0x180001bc4  mov     r10, rdx
0x180001bc7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001bcb  xor     r9d, r9d
0x180001bce  mov     r8d, 2
0x180001bd4  mov     rdx, [rax]
0x180001bd7  test    rdx, rdx
0x180001bda  jz      short loc_180001BF2
0x180001bdc  mov     rax, rcx
0x180001bdf  inc     rax
0x180001be2  cmp     [rdx+rax*2], r9w
0x180001be7  jnz     short loc_180001BDF
0x180001be9  lea     eax, ds:2[rax*2]
0x180001bf0  jmp     short loc_180001BFC
0x180001bf2  lea     rdx, qword_180021DC8
0x180001bf9  mov     eax, r8d
0x180001bfc  mov     [rbp+37h+var_18], eax
0x180001bff  mov     rax, [rbp+37h+arg_30]
0x180001c03  mov     [rbp+37h+var_30], rax
0x180001c07  mov     rax, [rbp+37h+arg_28]
0x180001c0b  mov     [rbp+37h+var_20], rdx
0x180001c0f  mov     [rbp+37h+var_14], r9d
0x180001c13  mov     [rbp+37h+var_28], 8
0x180001c1b  mov     rdx, [rax]
0x180001c1e  test    rdx, rdx
0x180001c21  jz      short loc_180001C37
0x180001c23  inc     rcx
0x180001c26  cmp     [rdx+rcx*2], r9w
0x180001c2b  jnz     short loc_180001C23
0x180001c2d  lea     r8d, ds:2[rcx*2]
0x180001c35  jmp     short loc_180001C3E
0x180001c37  lea     rdx, qword_180021DC8
0x180001c3e  mov     rax, [rbp+37h+arg_20]
0x180001c42  lea     rcx, dword_180030000
0x180001c49  mov     [rbp+37h+var_50], rax
0x180001c4d  lea     rax, [rbp+37h+var_70]
0x180001c51  mov     [rbp+37h+var_40], rdx
0x180001c55  mov     rdx, r10
0x180001c58  mov     [rbp+37h+var_38], r8d
0x180001c5c  xor     r8d, r8d
0x180001c5f  mov     [rsp+0A0h+var_78], rax
0x180001c64  mov     [rsp+0A0h+var_80], 6
0x180001c6c  mov     [rbp+37h+var_34], r9d
0x180001c70  mov     [rbp+37h+var_48], 8
0x180001c78  call    _tlgWriteTransfer_EventWriteTransfer
0x180001c7d  mov     rcx, [rbp+37h+var_10]
0x180001c81  xor     rcx, rsp; StackCookie
0x180001c84  call    __security_check_cookie
0x180001c89  add     rsp, 0A0h
0x180001c90  pop     rbp
0x180001c91  retn
```
