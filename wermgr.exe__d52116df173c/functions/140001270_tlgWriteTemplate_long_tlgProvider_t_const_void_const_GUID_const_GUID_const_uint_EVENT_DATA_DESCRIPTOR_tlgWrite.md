# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001270`
- end: `0x140001315`
- name: `??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140008ce4`
- `0x14000a804`
- `0x14000b0d8`
- `0x14000b70c`
- `0x14000be08`

## callees

- `0x140001270`
- `0x14000162c`
- `0x140003200`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        __int64 a6)
{
  int *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _BYTE v10[32]; // [rsp+30h] [rbp-58h] BYREF
  int *v11; // [rsp+50h] [rbp-38h]
  int v12; // [rsp+58h] [rbp-30h]
  int v13; // [rsp+5Ch] [rbp-2Ch]
  __int64 v14; // [rsp+60h] [rbp-28h]
  __int64 v15; // [rsp+68h] [rbp-20h]

  v14 = a6;
  v15 = 4;
  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)v6 + v7) );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &dword_1400241F4;
    v8 = 2;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x140001270  sub     rsp, 88h
0x140001277  mov     rax, cs:__security_cookie
0x14000127e  xor     rax, rsp
0x140001281  mov     [rsp+88h+var_18], rax
0x140001286  mov     rax, [rsp+88h+arg_28]
0x14000128e  xor     r8d, r8d
0x140001291  mov     [rsp+88h+var_28], rax
0x140001296  mov     r9d, 4
0x14000129c  mov     rax, [rsp+88h+arg_20]
0x1400012a4  mov     [rsp+88h+var_20], r9
0x1400012a9  mov     rcx, [rax]
0x1400012ac  test    rcx, rcx
0x1400012af  jz      short loc_1400012C8
0x1400012b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400012b5  inc     rax
0x1400012b8  cmp     [rcx+rax*2], r8w
0x1400012bd  jnz     short loc_1400012B5
0x1400012bf  lea     eax, ds:2[rax*2]
0x1400012c6  jmp     short loc_1400012D4
0x1400012c8  lea     rcx, dword_1400241F4
0x1400012cf  mov     eax, 2
0x1400012d4  mov     [rsp+88h+var_30], eax
0x1400012d8  lea     rax, [rsp+88h+var_58]
0x1400012dd  mov     [rsp+88h+var_60], rax
0x1400012e2  mov     [rsp+88h+var_68], r9d
0x1400012e7  xor     r9d, r9d
0x1400012ea  mov     [rsp+88h+var_38], rcx
0x1400012ef  lea     rcx, dword_14002C000
0x1400012f6  mov     [rsp+88h+var_2C], r8d
0x1400012fb  call    _tlgWriteTransfer_EventWriteTransfer
0x140001300  mov     rcx, [rsp+88h+var_18]
0x140001305  xor     rcx, rsp; StackCookie
0x140001308  call    __security_check_cookie
0x14000130d  add     rsp, 88h
0x140001314  retn
```
