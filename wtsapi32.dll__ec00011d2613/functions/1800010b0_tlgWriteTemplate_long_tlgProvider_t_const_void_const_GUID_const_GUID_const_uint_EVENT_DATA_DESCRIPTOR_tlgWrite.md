# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800010b0`
- end: `0x1800011bf`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z`
- size: `271`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fec0`
- `0x180011310`

## callees

- `0x1800010b0`
- `0x18000131c`
- `0x1800155c0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9)
{
  __int64 v10; // rcx
  int v11; // r8d
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-51h] BYREF
  const unsigned __int16 *v21; // [rsp+50h] [rbp-31h]
  int v22; // [rsp+58h] [rbp-29h]
  int v23; // [rsp+5Ch] [rbp-25h]
  __int64 v24; // [rsp+60h] [rbp-21h]
  __int64 v25; // [rsp+68h] [rbp-19h]
  const unsigned __int16 *v26; // [rsp+70h] [rbp-11h]
  int v27; // [rsp+78h] [rbp-9h]
  int v28; // [rsp+7Ch] [rbp-5h]
  __int64 v29; // [rsp+80h] [rbp-1h]
  __int64 v30; // [rsp+88h] [rbp+7h]
  const unsigned __int16 *v31; // [rsp+90h] [rbp+Fh]
  int v32; // [rsp+98h] [rbp+17h]
  int v33; // [rsp+9Ch] [rbp+1Bh]

  v10 = -1;
  v11 = 1;
  v12 = *a9;
  if ( *a9 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_BYTE *)v12 + v13) );
    v14 = v13 + 1;
  }
  else
  {
    v12 = &qword_180018198;
    v14 = 1;
  }
  v32 = v14;
  v29 = a8;
  v31 = v12;
  v33 = 0;
  v30 = 4;
  v15 = *a7;
  if ( *a7 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_BYTE *)v15 + v16) );
    v17 = v16 + 1;
  }
  else
  {
    v15 = &qword_180018198;
    v17 = 1;
  }
  v27 = v17;
  v24 = a6;
  v26 = v15;
  v28 = 0;
  v25 = 4;
  v18 = *a5;
  if ( *a5 )
  {
    do
      ++v10;
    while ( *((_BYTE *)v18 + v10) );
    v11 = v10 + 1;
  }
  else
  {
    v18 = &qword_180018198;
  }
  v21 = v18;
  v22 = v11;
  v23 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001F000, a2, 0, 0, 7u, &v20);
}

```

## disassembly

```asm
0x1800010b0  push    rbp
0x1800010b2  lea     rbp, [rsp-2Fh]
0x1800010b7  sub     rsp, 0B0h
0x1800010be  mov     rax, cs:__security_cookie
0x1800010c5  xor     rax, rsp
0x1800010c8  mov     [rbp+2Fh+var_10], rax
0x1800010cc  mov     rax, [rbp+2Fh+arg_40]
0x1800010d0  lea     r11, qword_180018198
0x1800010d7  mov     r10, rdx
0x1800010da  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800010de  xor     r9d, r9d
0x1800010e1  mov     r8d, 1
0x1800010e7  mov     rdx, [rax]
0x1800010ea  test    rdx, rdx
0x1800010ed  jz      short loc_1800010FF
0x1800010ef  mov     rax, rcx
0x1800010f2  inc     rax
0x1800010f5  cmp     [rdx+rax], r9b
0x1800010f9  jnz     short loc_1800010F2
0x1800010fb  inc     eax
0x1800010fd  jmp     short loc_180001105
0x1800010ff  mov     rdx, r11
0x180001102  mov     eax, r8d
0x180001105  mov     [rbp+2Fh+var_18], eax
0x180001108  mov     rax, [rbp+2Fh+arg_38]
0x18000110c  mov     [rbp+2Fh+var_30], rax
0x180001110  mov     rax, [rbp+2Fh+arg_30]
0x180001114  mov     [rbp+2Fh+var_20], rdx
0x180001118  mov     [rbp+2Fh+var_14], r9d
0x18000111c  mov     [rbp+2Fh+var_28], 4
0x180001124  mov     rdx, [rax]
0x180001127  test    rdx, rdx
0x18000112a  jz      short loc_18000113C
0x18000112c  mov     rax, rcx
0x18000112f  inc     rax
0x180001132  cmp     [rdx+rax], r9b
0x180001136  jnz     short loc_18000112F
0x180001138  inc     eax
0x18000113a  jmp     short loc_180001142
0x18000113c  mov     rdx, r11
0x18000113f  mov     eax, r8d
0x180001142  mov     [rbp+2Fh+var_38], eax
0x180001145  mov     rax, [rbp+2Fh+arg_28]
0x180001149  mov     [rbp+2Fh+var_50], rax
0x18000114d  mov     rax, [rbp+2Fh+arg_20]
0x180001151  mov     [rbp+2Fh+var_40], rdx
0x180001155  mov     [rbp+2Fh+var_34], r9d
0x180001159  mov     [rbp+2Fh+var_48], 4
0x180001161  mov     rdx, [rax]
0x180001164  test    rdx, rdx
0x180001167  jz      short loc_180001178
0x180001169  inc     rcx
0x18000116c  cmp     [rdx+rcx], r9b
0x180001170  jnz     short loc_180001169
0x180001172  lea     r8d, [rcx+1]
0x180001176  jmp     short loc_18000117B
0x180001178  mov     rdx, r11
0x18000117b  lea     rax, [rbp+2Fh+var_80]
0x18000117f  mov     [rbp+2Fh+var_60], rdx
0x180001183  mov     [rbp+2Fh+var_58], r8d
0x180001187  lea     rcx, dword_18001F000
0x18000118e  mov     [rsp+0B0h+var_88], rax
0x180001193  xor     r8d, r8d
0x180001196  mov     rdx, r10
0x180001199  mov     [rsp+0B0h+var_90], 7
0x1800011a1  mov     [rbp+2Fh+var_54], r9d
0x1800011a5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011aa  mov     rcx, [rbp+2Fh+var_10]
0x1800011ae  xor     rcx, rsp; StackCookie
0x1800011b1  call    __security_check_cookie
0x1800011b6  add     rsp, 0B0h
0x1800011bd  pop     rbp
0x1800011be  retn
```
