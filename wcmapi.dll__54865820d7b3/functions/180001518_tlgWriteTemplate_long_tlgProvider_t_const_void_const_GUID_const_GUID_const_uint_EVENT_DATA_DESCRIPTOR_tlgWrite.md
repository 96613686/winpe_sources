# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001518`
- end: `0x180001629`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@33@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012b10`

## callees

- `0x180001518`
- `0x180005a74`
- `0x180008a90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6,
        __int64 **a7,
        __int64 **a8)
{
  __int64 v9; // rcx
  int v10; // r8d
  __int64 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  __int64 *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  __int64 *v17; // rdx
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+30h] [rbp-39h] BYREF
  __int64 *v20; // [rsp+50h] [rbp-19h]
  int v21; // [rsp+58h] [rbp-11h]
  int v22; // [rsp+5Ch] [rbp-Dh]
  __int64 v23; // [rsp+60h] [rbp-9h]
  __int64 v24; // [rsp+68h] [rbp-1h]
  __int64 *v25; // [rsp+70h] [rbp+7h]
  int v26; // [rsp+78h] [rbp+Fh]
  int v27; // [rsp+7Ch] [rbp+13h]
  __int64 *v28; // [rsp+80h] [rbp+17h]
  int v29; // [rsp+88h] [rbp+1Fh]
  int v30; // [rsp+8Ch] [rbp+23h]

  v9 = -1;
  v10 = 2;
  v11 = *a8;
  if ( *a8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v11 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &qword_180022030;
    v13 = 2;
  }
  v29 = v13;
  v28 = v11;
  v30 = 0;
  v14 = *a7;
  if ( *a7 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v14 + v15) );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v14 = &qword_180022030;
    v16 = 2;
  }
  v26 = v16;
  v23 = a6;
  v25 = v14;
  v27 = 0;
  v24 = 4;
  v17 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_WORD *)v17 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v17 = &qword_180022030;
  }
  v20 = v17;
  v21 = v10;
  v22 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18002A000, a2, 0, 0, 6u, &v19);
}

```

## disassembly

```asm
0x180001518  push    rbp
0x18000151a  lea     rbp, [rsp-37h]
0x18000151f  sub     rsp, 0A0h
0x180001526  mov     rax, cs:__security_cookie
0x18000152d  xor     rax, rsp
0x180001530  mov     [rbp+37h+var_10], rax
0x180001534  mov     rax, [rbp+37h+arg_38]
0x180001538  lea     r11, qword_180022030
0x18000153f  mov     r10, rdx
0x180001542  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001546  xor     r9d, r9d; int
0x180001549  mov     r8d, 2
0x18000154f  mov     rdx, [rax]
0x180001552  test    rdx, rdx
0x180001555  jz      short loc_18000156D
0x180001557  mov     rax, rcx
0x18000155a  inc     rax
0x18000155d  cmp     [rdx+rax*2], r9w
0x180001562  jnz     short loc_18000155A
0x180001564  lea     eax, ds:2[rax*2]
0x18000156b  jmp     short loc_180001573
0x18000156d  mov     rdx, r11
0x180001570  mov     eax, r8d
0x180001573  mov     [rbp+37h+var_18], eax
0x180001576  mov     rax, [rbp+37h+arg_30]
0x18000157a  mov     [rbp+37h+var_20], rdx
0x18000157e  mov     [rbp+37h+var_14], r9d
0x180001582  mov     rdx, [rax]
0x180001585  test    rdx, rdx
0x180001588  jz      short loc_1800015A0
0x18000158a  mov     rax, rcx
0x18000158d  inc     rax
0x180001590  cmp     [rdx+rax*2], r9w
0x180001595  jnz     short loc_18000158D
0x180001597  lea     eax, ds:2[rax*2]
0x18000159e  jmp     short loc_1800015A6
0x1800015a0  mov     rdx, r11
0x1800015a3  mov     eax, r8d
0x1800015a6  mov     [rbp+37h+var_28], eax
0x1800015a9  mov     rax, [rbp+37h+arg_28]
0x1800015ad  mov     [rbp+37h+var_40], rax
0x1800015b1  mov     rax, [rbp+37h+arg_20]
0x1800015b5  mov     [rbp+37h+var_30], rdx
0x1800015b9  mov     [rbp+37h+var_24], r9d
0x1800015bd  mov     [rbp+37h+var_38], 4
0x1800015c5  mov     rdx, [rax]
0x1800015c8  test    rdx, rdx
0x1800015cb  jz      short loc_1800015E1
0x1800015cd  inc     rcx
0x1800015d0  cmp     [rdx+rcx*2], r9w
0x1800015d5  jnz     short loc_1800015CD
0x1800015d7  lea     r8d, ds:2[rcx*2]
0x1800015df  jmp     short loc_1800015E4
0x1800015e1  mov     rdx, r11
0x1800015e4  lea     rax, [rbp+37h+var_70]
0x1800015e8  mov     [rbp+37h+var_50], rdx
0x1800015ec  mov     [rbp+37h+var_48], r8d
0x1800015f0  lea     rcx, dword_18002A000; int
0x1800015f7  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x1800015fc  xor     r8d, r8d; int
0x1800015ff  mov     rdx, r10; int
0x180001602  mov     [rsp+0A0h+var_80], 6; ULONG
0x18000160a  mov     [rbp+37h+var_44], r9d
0x18000160e  call    _tlgWriteTransfer_EventWriteTransfer
0x180001613  mov     rcx, [rbp+37h+var_10]
0x180001617  xor     rcx, rsp; StackCookie
0x18000161a  call    __security_check_cookie
0x18000161f  add     rsp, 0A0h
0x180001626  pop     rbp
0x180001627  retn
```
