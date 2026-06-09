# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001008`
- end: `0x1800010d8`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013f9c`

## callees

- `0x180001008`
- `0x180001830`
- `0x180005680`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 **a6)
{
  __int64 v8; // rdx
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  const unsigned __int16 *v12; // rcx
  int v13; // edx
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *v16; // [rsp+50h] [rbp-38h]
  int v17; // [rsp+58h] [rbp-30h]
  int v18; // [rsp+5Ch] [rbp-2Ch]
  __int64 *v19; // [rsp+60h] [rbp-28h]
  int v20; // [rsp+68h] [rbp-20h]
  int v21; // [rsp+6Ch] [rbp-1Ch]

  v8 = -1;
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
    v9 = &qword_18001C1B8;
    v11 = 2;
  }
  v20 = v11;
  v19 = v9;
  v21 = 0;
  v12 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *((_BYTE *)v12 + v8) );
    v13 = v8 + 1;
  }
  else
  {
    v12 = &dword_18001929C;
    v13 = 1;
  }
  v16 = v12;
  v17 = v13;
  v18 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 4u, &v15);
}

```

## disassembly

```asm
0x180001008  sub     rsp, 88h
0x18000100f  mov     rax, cs:__security_cookie
0x180001016  xor     rax, rsp
0x180001019  mov     [rsp+88h+var_18], rax
0x18000101e  mov     rax, [rsp+88h+arg_28]
0x180001026  mov     r11, rdx
0x180001029  mov     r10, rcx
0x18000102c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001030  xor     r8d, r8d
0x180001033  mov     rcx, [rax]
0x180001036  test    rcx, rcx
0x180001039  jz      short loc_180001051
0x18000103b  mov     rax, rdx
0x18000103e  inc     rax
0x180001041  cmp     [rcx+rax*2], r8w
0x180001046  jnz     short loc_18000103E
0x180001048  lea     eax, ds:2[rax*2]
0x18000104f  jmp     short loc_18000105D
0x180001051  lea     rcx, qword_18001C1B8
0x180001058  mov     eax, 2
0x18000105d  mov     [rsp+88h+var_20], eax
0x180001061  mov     rax, [rsp+88h+arg_20]
0x180001069  mov     [rsp+88h+var_28], rcx
0x18000106e  mov     [rsp+88h+var_1C], r8d
0x180001073  mov     rcx, [rax]
0x180001076  test    rcx, rcx
0x180001079  jz      short loc_180001088
0x18000107b  inc     rdx
0x18000107e  cmp     [rcx+rdx], r8b
0x180001082  jnz     short loc_18000107B
0x180001084  inc     edx
0x180001086  jmp     short loc_180001094
0x180001088  lea     rcx, dword_18001929C
0x18000108f  mov     edx, 1
0x180001094  lea     rax, [rsp+88h+var_58]
0x180001099  mov     [rsp+88h+var_38], rcx
0x18000109e  mov     [rsp+88h+var_30], edx
0x1800010a2  xor     r9d, r9d
0x1800010a5  mov     [rsp+88h+var_60], rax
0x1800010aa  mov     rdx, r11
0x1800010ad  mov     rcx, r10
0x1800010b0  mov     [rsp+88h+var_68], 4
0x1800010b8  mov     [rsp+88h+var_2C], r8d
0x1800010bd  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010c2  mov     rcx, [rsp+88h+var_18]
0x1800010c7  xor     rcx, rsp; StackCookie
0x1800010ca  call    __security_check_cookie
0x1800010cf  add     rsp, 88h
0x1800010d6  retn
```
