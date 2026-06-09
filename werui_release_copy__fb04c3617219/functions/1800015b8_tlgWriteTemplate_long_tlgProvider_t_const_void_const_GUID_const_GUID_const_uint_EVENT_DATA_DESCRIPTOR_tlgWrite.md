# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &)

- ea: `0x1800015b8`
- end: `0x18000168e`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperArray@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperArray@$00@@4@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012d68`

## callees

- `0x180001260`
- `0x1800015b8`
- `0x180016c50`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const LPARAM **a5,
        __int64 *a6,
        __int64 *a7)
{
  int v8; // edx
  const LPARAM *v9; // rcx
  __int64 v10; // rax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-41h] BYREF
  const LPARAM *v13; // [rsp+50h] [rbp-21h]
  int v14; // [rsp+58h] [rbp-19h]
  int v15; // [rsp+5Ch] [rbp-15h]
  __int64 *v16; // [rsp+60h] [rbp-11h]
  __int64 v17; // [rsp+68h] [rbp-9h]
  __int64 v18; // [rsp+70h] [rbp-1h]
  int v19; // [rsp+78h] [rbp+7h]
  int v20; // [rsp+7Ch] [rbp+Bh]
  __int64 *v21; // [rsp+80h] [rbp+Fh]
  __int64 v22; // [rsp+88h] [rbp+17h]
  __int64 v23; // [rsp+90h] [rbp+1Fh]
  int v24; // [rsp+98h] [rbp+27h]
  int v25; // [rsp+9Ch] [rbp+2Bh]

  v25 = 0;
  v8 = 2;
  v20 = 0;
  v22 = 2;
  v17 = 2;
  v23 = *a7;
  v24 = *((unsigned __int16 *)a7 + 4);
  v21 = a7 + 1;
  v18 = *a6;
  v19 = *((unsigned __int16 *)a6 + 4);
  v16 = a6 + 1;
  v9 = *a5;
  if ( *a5 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v9 + v10) );
    v8 = 2 * v10 + 2;
  }
  else
  {
    v9 = &lParam;
  }
  v13 = v9;
  v14 = v8;
  v15 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180022000, a2, 0, 0, 7u, &v12);
}

```

## disassembly

```asm
0x1800015b8  push    rbp
0x1800015ba  lea     rbp, [rsp-3Fh]
0x1800015bf  sub     rsp, 0B0h
0x1800015c6  mov     rax, cs:__security_cookie
0x1800015cd  xor     rax, rsp
0x1800015d0  mov     [rbp+3Fh+var_10], rax
0x1800015d4  mov     rax, [rbp+3Fh+arg_30]
0x1800015d8  xor     r8d, r8d
0x1800015db  mov     r10, rdx
0x1800015de  mov     [rbp+3Fh+var_14], r8d
0x1800015e2  mov     edx, 2
0x1800015e7  mov     [rbp+3Fh+var_34], r8d
0x1800015eb  mov     [rbp+3Fh+var_28], rdx
0x1800015ef  lea     rcx, [rax+8]
0x1800015f3  mov     [rbp+3Fh+var_48], rdx
0x1800015f7  mov     rax, [rax]
0x1800015fa  mov     [rbp+3Fh+var_20], rax
0x1800015fe  movzx   eax, word ptr [rcx]
0x180001601  mov     [rbp+3Fh+var_18], eax
0x180001604  mov     rax, [rbp+3Fh+arg_28]
0x180001608  mov     [rbp+3Fh+var_30], rcx
0x18000160c  lea     rcx, [rax+8]
0x180001610  mov     rax, [rax]
0x180001613  mov     [rbp+3Fh+var_40], rax
0x180001617  movzx   eax, word ptr [rcx]
0x18000161a  mov     [rbp+3Fh+var_38], eax
0x18000161d  mov     rax, [rbp+3Fh+arg_20]
0x180001621  mov     [rbp+3Fh+var_50], rcx
0x180001625  mov     rcx, [rax]
0x180001628  test    rcx, rcx
0x18000162b  jz      short loc_180001644
0x18000162d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001631  inc     rax
0x180001634  cmp     [rcx+rax*2], r8w
0x180001639  jnz     short loc_180001631
0x18000163b  lea     edx, ds:2[rax*2]
0x180001642  jmp     short loc_18000164B
0x180001644  lea     rcx, lParam
0x18000164b  lea     rax, [rbp+3Fh+var_80]
0x18000164f  mov     [rbp+3Fh+var_60], rcx
0x180001653  mov     [rbp+3Fh+var_58], edx
0x180001656  lea     rcx, dword_180022000
0x18000165d  mov     [rsp+0B0h+var_88], rax
0x180001662  xor     r9d, r9d
0x180001665  mov     rdx, r10
0x180001668  mov     [rsp+0B0h+var_90], 7
0x180001670  mov     [rbp+3Fh+var_54], r8d
0x180001674  call    _tlgWriteTransfer_EventWriteTransfer
0x180001679  mov     rcx, [rbp+3Fh+var_10]
0x18000167d  xor     rcx, rsp; StackCookie
0x180001680  call    __security_check_cookie
0x180001685  add     rsp, 0B0h
0x18000168c  pop     rbp
0x18000168d  retn
```
