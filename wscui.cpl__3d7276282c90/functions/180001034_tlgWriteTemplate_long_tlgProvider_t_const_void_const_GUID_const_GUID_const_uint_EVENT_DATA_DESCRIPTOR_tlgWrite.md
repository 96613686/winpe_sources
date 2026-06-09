# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001034`
- end: `0x180001125`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007938`

## callees

- `0x180001034`
- `0x180001160`
- `0x18000a640`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        _BYTE **a5,
        _BYTE **a6,
        __int64 a7)
{
  __int64 v8; // rcx
  int v9; // r8d
  _BYTE *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  _BYTE *v13; // rdx
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-68h] BYREF
  _BYTE *v16; // [rsp+50h] [rbp-48h]
  int v17; // [rsp+58h] [rbp-40h]
  int v18; // [rsp+5Ch] [rbp-3Ch]
  _BYTE *v19; // [rsp+60h] [rbp-38h]
  int v20; // [rsp+68h] [rbp-30h]
  int v21; // [rsp+6Ch] [rbp-2Ch]
  __int64 v22; // [rsp+70h] [rbp-28h]
  __int64 v23; // [rsp+78h] [rbp-20h]

  v22 = a7;
  v8 = -1;
  v23 = 4;
  v9 = 2;
  v10 = *a6;
  if ( *a6 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&v10[2 * v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = byte_18000F684;
    v12 = 2;
  }
  v20 = v12;
  v19 = v10;
  v21 = 0;
  v13 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *(_WORD *)&v13[2 * v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v13 = byte_18000F684;
  }
  v16 = v13;
  v17 = v9;
  v18 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180014060, a2, 0, 0, 5u, &v15);
}

```

## disassembly

```asm
0x180001034  sub     rsp, 98h
0x18000103b  mov     rax, cs:__security_cookie
0x180001042  xor     rax, rsp
0x180001045  mov     [rsp+98h+var_18], rax
0x18000104d  mov     rax, [rsp+98h+arg_30]
0x180001055  xor     r9d, r9d
0x180001058  mov     [rsp+98h+var_28], rax
0x18000105d  mov     r10, rdx
0x180001060  mov     rax, [rsp+98h+arg_28]
0x180001068  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000106c  mov     [rsp+98h+var_20], 4
0x180001075  lea     r8d, [r9+2]
0x180001079  mov     rdx, [rax]
0x18000107c  test    rdx, rdx
0x18000107f  jz      short loc_180001097
0x180001081  mov     rax, rcx
0x180001084  inc     rax
0x180001087  cmp     [rdx+rax*2], r9w
0x18000108c  jnz     short loc_180001084
0x18000108e  lea     eax, ds:2[rax*2]
0x180001095  jmp     short loc_1800010A1
0x180001097  lea     rdx, byte_18000F684
0x18000109e  mov     eax, r8d
0x1800010a1  mov     [rsp+98h+var_30], eax
0x1800010a5  mov     rax, [rsp+98h+arg_20]
0x1800010ad  mov     [rsp+98h+var_38], rdx
0x1800010b2  mov     [rsp+98h+var_2C], r9d
0x1800010b7  mov     rdx, [rax]
0x1800010ba  test    rdx, rdx
0x1800010bd  jz      short loc_1800010D3
0x1800010bf  inc     rcx
0x1800010c2  cmp     [rdx+rcx*2], r9w
0x1800010c7  jnz     short loc_1800010BF
0x1800010c9  lea     r8d, ds:2[rcx*2]
0x1800010d1  jmp     short loc_1800010DA
0x1800010d3  lea     rdx, byte_18000F684
0x1800010da  lea     rax, [rsp+98h+var_68]
0x1800010df  mov     [rsp+98h+var_48], rdx
0x1800010e4  mov     [rsp+98h+var_40], r8d
0x1800010e9  lea     rcx, dword_180014060
0x1800010f0  mov     [rsp+98h+var_70], rax
0x1800010f5  xor     r8d, r8d
0x1800010f8  mov     rdx, r10
0x1800010fb  mov     [rsp+98h+var_78], 5
0x180001103  mov     [rsp+98h+var_3C], r9d
0x180001108  call    _tlgWriteTransfer_EventWriteTransfer
0x18000110d  mov     rcx, [rsp+98h+var_18]
0x180001115  xor     rcx, rsp; StackCookie
0x180001118  call    __security_check_cookie
0x18000111d  add     rsp, 98h
0x180001124  retn
```
