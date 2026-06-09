# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001008`
- end: `0x1800010a8`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002044`
- `0x180002380`

## callees

- `0x180001008`
- `0x180001240`
- `0x180002950`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int16 **a5,
        __int64 a6)
{
  __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-58h] BYREF
  __int16 *v11; // [rsp+50h] [rbp-38h]
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
    while ( *((_BYTE *)v6 + v7) );
    v8 = v7 + 1;
  }
  else
  {
    v6 = word_18000443A;
    v8 = 1;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180006048, a2, 0, 0, 4u, &v10);
}

```

## disassembly

```asm
0x180001008  sub     rsp, 88h
0x18000100f  mov     rax, cs:__security_cookie
0x180001016  xor     rax, rsp
0x180001019  mov     [rsp+88h+var_18], rax
0x18000101e  mov     rax, [rsp+88h+arg_28]
0x180001026  xor     r8d, r8d
0x180001029  mov     [rsp+88h+var_28], rax
0x18000102e  mov     r9d, 4
0x180001034  mov     rax, [rsp+88h+arg_20]
0x18000103c  mov     [rsp+88h+var_20], r9
0x180001041  mov     rcx, [rax]
0x180001044  test    rcx, rcx
0x180001047  jz      short loc_18000105A
0x180001049  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000104d  inc     rax
0x180001050  cmp     [rcx+rax], r8b
0x180001054  jnz     short loc_18000104D
0x180001056  inc     eax
0x180001058  jmp     short loc_180001066
0x18000105a  lea     rcx, word_18000443A
0x180001061  mov     eax, 1
0x180001066  mov     [rsp+88h+var_30], eax
0x18000106a  lea     rax, [rsp+88h+var_58]
0x18000106f  mov     [rsp+88h+var_60], rax
0x180001074  mov     [rsp+88h+var_68], r9d
0x180001079  xor     r9d, r9d
0x18000107c  mov     [rsp+88h+var_38], rcx
0x180001081  lea     rcx, dword_180006048
0x180001088  mov     [rsp+88h+var_2C], r8d
0x18000108d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001092  mov     rcx, [rsp+88h+var_18]
0x180001097  xor     rcx, rsp; StackCookie
0x18000109a  call    __security_check_cookie
0x18000109f  add     rsp, 88h
0x1800010a6  retn
```
