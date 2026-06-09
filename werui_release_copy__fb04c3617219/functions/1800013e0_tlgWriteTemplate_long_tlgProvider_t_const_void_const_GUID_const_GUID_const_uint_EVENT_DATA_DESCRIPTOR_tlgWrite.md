# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800013e0`
- end: `0x1800014b7`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011af0`

## callees

- `0x180001260`
- `0x1800013e0`
- `0x180016c50`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const LPARAM **a5,
        const LPARAM **a6)
{
  __int64 v7; // rcx
  int v8; // r8d
  const LPARAM *v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  const LPARAM *v12; // rdx
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-58h] BYREF
  const LPARAM *v15; // [rsp+50h] [rbp-38h]
  int v16; // [rsp+58h] [rbp-30h]
  int v17; // [rsp+5Ch] [rbp-2Ch]
  const LPARAM *v18; // [rsp+60h] [rbp-28h]
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
    v9 = &lParam;
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
    v12 = &lParam;
  }
  v15 = v12;
  v16 = v8;
  v17 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180022000, a2, 0, 0, 4u, &v14);
}

```

## disassembly

```asm
0x1800013e0  sub     rsp, 88h
0x1800013e7  mov     rax, cs:__security_cookie
0x1800013ee  xor     rax, rsp
0x1800013f1  mov     [rsp+88h+var_18], rax
0x1800013f6  mov     rax, [rsp+88h+arg_28]
0x1800013fe  mov     r10, rdx
0x180001401  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001405  xor     r9d, r9d
0x180001408  mov     r8d, 2
0x18000140e  mov     rdx, [rax]
0x180001411  test    rdx, rdx
0x180001414  jz      short loc_18000142C
0x180001416  mov     rax, rcx
0x180001419  inc     rax
0x18000141c  cmp     [rdx+rax*2], r9w
0x180001421  jnz     short loc_180001419
0x180001423  lea     eax, ds:2[rax*2]
0x18000142a  jmp     short loc_180001436
0x18000142c  lea     rdx, lParam
0x180001433  mov     eax, r8d
0x180001436  mov     [rsp+88h+var_20], eax
0x18000143a  mov     rax, [rsp+88h+arg_20]
0x180001442  mov     [rsp+88h+var_28], rdx
0x180001447  mov     [rsp+88h+var_1C], r9d
0x18000144c  mov     rdx, [rax]
0x18000144f  test    rdx, rdx
0x180001452  jz      short loc_180001468
0x180001454  inc     rcx
0x180001457  cmp     [rdx+rcx*2], r9w
0x18000145c  jnz     short loc_180001454
0x18000145e  lea     r8d, ds:2[rcx*2]
0x180001466  jmp     short loc_18000146F
0x180001468  lea     rdx, lParam
0x18000146f  lea     rax, [rsp+88h+var_58]
0x180001474  mov     [rsp+88h+var_38], rdx
0x180001479  mov     [rsp+88h+var_30], r8d
0x18000147e  lea     rcx, dword_180022000
0x180001485  mov     [rsp+88h+var_60], rax
0x18000148a  xor     r8d, r8d
0x18000148d  mov     rdx, r10
0x180001490  mov     [rsp+88h+var_68], 4
0x180001498  mov     [rsp+88h+var_2C], r9d
0x18000149d  call    _tlgWriteTransfer_EventWriteTransfer
0x1800014a2  mov     rcx, [rsp+88h+var_18]
0x1800014a7  xor     rcx, rsp; StackCookie
0x1800014aa  call    __security_check_cookie
0x1800014af  add     rsp, 88h
0x1800014b6  retn
```
