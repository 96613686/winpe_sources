# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800014c0`
- end: `0x1800015b1`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001275c`

## callees

- `0x180001260`
- `0x1800014c0`
- `0x180016c50`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const LPARAM **a5,
        const LPARAM **a6,
        __int64 a7)
{
  __int64 v8; // rcx
  int v9; // r8d
  const LPARAM *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  const LPARAM *v13; // rdx
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-68h] BYREF
  const LPARAM *v16; // [rsp+50h] [rbp-48h]
  int v17; // [rsp+58h] [rbp-40h]
  int v18; // [rsp+5Ch] [rbp-3Ch]
  const LPARAM *v19; // [rsp+60h] [rbp-38h]
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
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &lParam;
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
    while ( *((_WORD *)v13 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v13 = &lParam;
  }
  v16 = v13;
  v17 = v9;
  v18 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180022000, a2, 0, 0, 5u, &v15);
}

```

## disassembly

```asm
0x1800014c0  sub     rsp, 98h
0x1800014c7  mov     rax, cs:__security_cookie
0x1800014ce  xor     rax, rsp
0x1800014d1  mov     [rsp+98h+var_18], rax
0x1800014d9  mov     rax, [rsp+98h+arg_30]
0x1800014e1  xor     r9d, r9d
0x1800014e4  mov     [rsp+98h+var_28], rax
0x1800014e9  mov     r10, rdx
0x1800014ec  mov     rax, [rsp+98h+arg_28]
0x1800014f4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800014f8  mov     [rsp+98h+var_20], 4
0x180001501  lea     r8d, [r9+2]
0x180001505  mov     rdx, [rax]
0x180001508  test    rdx, rdx
0x18000150b  jz      short loc_180001523
0x18000150d  mov     rax, rcx
0x180001510  inc     rax
0x180001513  cmp     [rdx+rax*2], r9w
0x180001518  jnz     short loc_180001510
0x18000151a  lea     eax, ds:2[rax*2]
0x180001521  jmp     short loc_18000152D
0x180001523  lea     rdx, lParam
0x18000152a  mov     eax, r8d
0x18000152d  mov     [rsp+98h+var_30], eax
0x180001531  mov     rax, [rsp+98h+arg_20]
0x180001539  mov     [rsp+98h+var_38], rdx
0x18000153e  mov     [rsp+98h+var_2C], r9d
0x180001543  mov     rdx, [rax]
0x180001546  test    rdx, rdx
0x180001549  jz      short loc_18000155F
0x18000154b  inc     rcx
0x18000154e  cmp     [rdx+rcx*2], r9w
0x180001553  jnz     short loc_18000154B
0x180001555  lea     r8d, ds:2[rcx*2]
0x18000155d  jmp     short loc_180001566
0x18000155f  lea     rdx, lParam
0x180001566  lea     rax, [rsp+98h+var_68]
0x18000156b  mov     [rsp+98h+var_48], rdx
0x180001570  mov     [rsp+98h+var_40], r8d
0x180001575  lea     rcx, dword_180022000
0x18000157c  mov     [rsp+98h+var_70], rax
0x180001581  xor     r8d, r8d
0x180001584  mov     rdx, r10
0x180001587  mov     [rsp+98h+var_78], 5
0x18000158f  mov     [rsp+98h+var_3C], r9d
0x180001594  call    _tlgWriteTransfer_EventWriteTransfer
0x180001599  mov     rcx, [rsp+98h+var_18]
0x1800015a1  xor     rcx, rsp; StackCookie
0x1800015a4  call    __security_check_cookie
0x1800015a9  add     rsp, 98h
0x1800015b0  retn
```
