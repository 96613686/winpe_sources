# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x18000144c`
- end: `0x180001508`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a108`
- `0x18000a27c`
- `0x18000a3f0`
- `0x18000a564`
- `0x18000a6d8`
- `0x18000a84c`
- `0x18000a8dc`
- `0x18000a96c`
- `0x18000a9fc`
- `0x18000aa8c`
- `0x180012738`
- `0x1800127fc`
- `0x1800128c0`
- `0x180012984`
- `0x180012af8`
- `0x180012b88`
- `0x180012c18`
- `0x180012ca8`

## callees

- `0x18000144c`
- `0x18000169c`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7)
{
  const unsigned __int16 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _BYTE v11[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v12; // [rsp+50h] [rbp-48h]
  __int64 v13; // [rsp+58h] [rbp-40h]
  __int64 v14; // [rsp+60h] [rbp-38h]
  __int64 v15; // [rsp+68h] [rbp-30h]
  const unsigned __int16 *v16; // [rsp+70h] [rbp-28h]
  int v17; // [rsp+78h] [rbp-20h]
  int v18; // [rsp+7Ch] [rbp-1Ch]

  v7 = *a7;
  if ( *a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_BYTE *)v7 + v8) );
    v9 = v8 + 1;
  }
  else
  {
    v7 = &word_180021DC6;
    v9 = 1;
  }
  v17 = v9;
  v14 = a6;
  v12 = a5;
  v16 = v7;
  v18 = 0;
  v15 = 4;
  v13 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 5, v11);
}

```

## disassembly

```asm
0x18000144c  sub     rsp, 98h
0x180001453  mov     rax, cs:__security_cookie
0x18000145a  xor     rax, rsp
0x18000145d  mov     [rsp+98h+var_18], rax
0x180001465  mov     rax, [rsp+98h+arg_30]
0x18000146d  xor     r8d, r8d
0x180001470  mov     rcx, [rax]
0x180001473  test    rcx, rcx
0x180001476  jz      short loc_180001489
0x180001478  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000147c  inc     rax
0x18000147f  cmp     [rcx+rax], r8b
0x180001483  jnz     short loc_18000147C
0x180001485  inc     eax
0x180001487  jmp     short loc_180001495
0x180001489  lea     rcx, word_180021DC6
0x180001490  mov     eax, 1
0x180001495  mov     [rsp+98h+var_20], eax
0x180001499  xor     r9d, r9d
0x18000149c  mov     rax, [rsp+98h+arg_28]
0x1800014a4  mov     [rsp+98h+var_38], rax
0x1800014a9  mov     rax, [rsp+98h+arg_20]
0x1800014b1  mov     [rsp+98h+var_48], rax
0x1800014b6  lea     rax, [rsp+98h+var_68]
0x1800014bb  mov     [rsp+98h+var_28], rcx
0x1800014c0  lea     rcx, dword_180030000
0x1800014c7  mov     [rsp+98h+var_70], rax
0x1800014cc  mov     [rsp+98h+var_78], 5
0x1800014d4  mov     [rsp+98h+var_1C], r8d
0x1800014d9  mov     [rsp+98h+var_30], 4
0x1800014e2  mov     [rsp+98h+var_40], 8
0x1800014eb  call    _tlgWriteTransfer_EventWriteTransfer
0x1800014f0  mov     rcx, [rsp+98h+var_18]
0x1800014f8  xor     rcx, rsp; StackCookie
0x1800014fb  call    __security_check_cookie
0x180001500  add     rsp, 98h
0x180001507  retn
```
