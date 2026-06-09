# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001098`
- end: `0x18000116f`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z`
- size: `215`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800045cc`
- `0x180004d28`

## callees

- `0x180001098`
- `0x18000131c`
- `0x1800121b0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 **a6)
{
  __int64 v7; // rcx
  int v8; // r8d
  __int64 *v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  __int64 *v12; // rdx
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-58h] BYREF
  __int64 *v15; // [rsp+50h] [rbp-38h]
  int v16; // [rsp+58h] [rbp-30h]
  int v17; // [rsp+5Ch] [rbp-2Ch]
  __int64 *v18; // [rsp+60h] [rbp-28h]
  int v19; // [rsp+68h] [rbp-20h]
  int v20; // [rsp+6Ch] [rbp-1Ch]

  v7 = -1;
  v8 = 2;
  v9 = *a6;
  if ( *a6 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v9 + v10) );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = &qword_180016858;
    v11 = 2;
  }
  v19 = v11;
  v18 = v9;
  v20 = 0;
  v12 = *a5;
  if ( *a5 )
  {
    do
      ++v7;
    while ( *((_WORD *)v12 + v7) );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v12 = &qword_180016858;
  }
  v15 = v12;
  v16 = v8;
  v17 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001C008, a2, 0, 0, 4u, &v14);
}

```

## disassembly

```asm
0x180001098  sub     rsp, 88h
0x18000109f  mov     rax, cs:__security_cookie
0x1800010a6  xor     rax, rsp
0x1800010a9  mov     [rsp+88h+var_18], rax
0x1800010ae  mov     rax, [rsp+88h+arg_28]
0x1800010b6  mov     r10, rdx
0x1800010b9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800010bd  xor     r9d, r9d
0x1800010c0  mov     r8d, 2
0x1800010c6  mov     rdx, [rax]
0x1800010c9  test    rdx, rdx
0x1800010cc  jz      short loc_1800010E4
0x1800010ce  mov     rax, rcx
0x1800010d1  inc     rax
0x1800010d4  cmp     [rdx+rax*2], r9w
0x1800010d9  jnz     short loc_1800010D1
0x1800010db  lea     eax, ds:2[rax*2]
0x1800010e2  jmp     short loc_1800010EE
0x1800010e4  lea     rdx, qword_180016858
0x1800010eb  mov     eax, r8d
0x1800010ee  mov     [rsp+88h+var_20], eax
0x1800010f2  mov     rax, [rsp+88h+arg_20]
0x1800010fa  mov     [rsp+88h+var_28], rdx
0x1800010ff  mov     [rsp+88h+var_1C], r9d
0x180001104  mov     rdx, [rax]
0x180001107  test    rdx, rdx
0x18000110a  jz      short loc_180001120
0x18000110c  inc     rcx
0x18000110f  cmp     [rdx+rcx*2], r9w
0x180001114  jnz     short loc_18000110C
0x180001116  lea     r8d, ds:2[rcx*2]
0x18000111e  jmp     short loc_180001127
0x180001120  lea     rdx, qword_180016858
0x180001127  lea     rax, [rsp+88h+var_58]
0x18000112c  mov     [rsp+88h+var_38], rdx
0x180001131  mov     [rsp+88h+var_30], r8d
0x180001136  lea     rcx, dword_18001C008
0x18000113d  mov     [rsp+88h+var_60], rax
0x180001142  xor     r8d, r8d
0x180001145  mov     rdx, r10
0x180001148  mov     [rsp+88h+var_68], 4
0x180001150  mov     [rsp+88h+var_2C], r9d
0x180001155  call    _tlgWriteTransfer_EventWriteTransfer
0x18000115a  mov     rcx, [rsp+88h+var_18]
0x18000115f  xor     rcx, rsp; StackCookie
0x180001162  call    __security_check_cookie
0x180001167  add     rsp, 88h
0x18000116e  retn
```
