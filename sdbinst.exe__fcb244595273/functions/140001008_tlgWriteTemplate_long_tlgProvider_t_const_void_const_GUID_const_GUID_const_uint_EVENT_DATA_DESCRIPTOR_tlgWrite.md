# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)

- ea: `0x140001008`
- end: `0x14000120b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@D@@U2@U2@U2@U2@U2@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@D@@44444AEBU?$_tlgWrapSz@G@@4@Z`
- size: `515`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c540`

## callees

- `0x140001008`
- `0x1400013bc`
- `0x14002e420`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        _QWORD *a8,
        _QWORD *a9,
        _QWORD *a10,
        _QWORD *a11,
        _QWORD *a12,
        _QWORD *a13,
        _QWORD *a14)
{
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax

  v14 = -1;
  if ( *a14 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *(_BYTE *)(*a14 + v15) );
  }
  if ( *a13 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)(*a13 + 2 * v16) );
  }
  if ( *a12 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *(_BYTE *)(*a12 + v17) );
  }
  if ( *a11 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *(_BYTE *)(*a11 + v18) );
  }
  if ( *a10 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *(_BYTE *)(*a10 + v19) );
  }
  if ( *a9 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *(_BYTE *)(*a9 + v20) );
  }
  if ( *a8 )
  {
    v21 = -1;
    do
      ++v21;
    while ( *(_BYTE *)(*a8 + v21) );
  }
  if ( *a7 )
  {
    do
      ++v14;
    while ( *(_BYTE *)(*a7 + v14) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_140042000, a2, 0);
}

```

## disassembly

```asm
0x140001008  push    rbp
0x14000100a  lea     rbp, [rsp-7]
0x14000100f  sub     rsp, 100h
0x140001016  mov     rax, cs:__security_cookie
0x14000101d  xor     rax, rsp
0x140001020  mov     [rbp+7+var_10], rax
0x140001024  mov     rax, [rbp+7+arg_68]
0x140001028  lea     r11, dword_1400326D4
0x14000102f  mov     r10, rdx
0x140001032  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001036  xor     r9d, r9d
0x140001039  mov     r8d, 1
0x14000103f  mov     rdx, [rax]
0x140001042  test    rdx, rdx
0x140001045  jz      short loc_140001057
0x140001047  mov     rax, rcx
0x14000104a  inc     rax
0x14000104d  cmp     [rdx+rax], r9b
0x140001051  jnz     short loc_14000104A
0x140001053  inc     eax
0x140001055  jmp     short loc_14000105D
0x140001057  mov     rdx, r11
0x14000105a  mov     eax, r8d
0x14000105d  mov     [rbp+7+var_18], eax
0x140001060  mov     rax, [rbp+7+arg_60]
0x140001064  mov     [rbp+7+var_20], rdx
0x140001068  mov     [rbp+7+var_14], r9d
0x14000106c  mov     rdx, [rax]
0x14000106f  test    rdx, rdx
0x140001072  jz      short loc_14000108A
0x140001074  mov     rax, rcx
0x140001077  inc     rax
0x14000107a  cmp     [rdx+rax*2], r9w
0x14000107f  jnz     short loc_140001077
0x140001081  lea     eax, ds:2[rax*2]
0x140001088  jmp     short loc_140001096
0x14000108a  lea     rdx, Format
0x140001091  mov     eax, 2
0x140001096  mov     [rbp+7+var_28], eax
0x140001099  mov     rax, [rbp+7+arg_58]
0x14000109d  mov     [rbp+7+var_30], rdx
0x1400010a1  mov     [rbp+7+var_24], r9d
0x1400010a5  mov     rdx, [rax]
0x1400010a8  test    rdx, rdx
0x1400010ab  jz      short loc_1400010BD
0x1400010ad  mov     rax, rcx
0x1400010b0  inc     rax
0x1400010b3  cmp     [rdx+rax], r9b
0x1400010b7  jnz     short loc_1400010B0
0x1400010b9  inc     eax
0x1400010bb  jmp     short loc_1400010C3
0x1400010bd  mov     rdx, r11
0x1400010c0  mov     eax, r8d
0x1400010c3  mov     [rbp+7+var_38], eax
0x1400010c6  mov     rax, [rbp+7+arg_50]
0x1400010ca  mov     [rbp+7+var_40], rdx
0x1400010ce  mov     [rbp+7+var_34], r9d
0x1400010d2  mov     rdx, [rax]
0x1400010d5  test    rdx, rdx
0x1400010d8  jz      short loc_1400010EA
0x1400010da  mov     rax, rcx
0x1400010dd  inc     rax
0x1400010e0  cmp     [rdx+rax], r9b
0x1400010e4  jnz     short loc_1400010DD
0x1400010e6  inc     eax
0x1400010e8  jmp     short loc_1400010F0
0x1400010ea  mov     rdx, r11
0x1400010ed  mov     eax, r8d
0x1400010f0  mov     [rbp+7+var_48], eax
0x1400010f3  mov     rax, [rbp+7+arg_48]
0x1400010f7  mov     [rbp+7+var_50], rdx
0x1400010fb  mov     [rbp+7+var_44], r9d
0x1400010ff  mov     rdx, [rax]
0x140001102  test    rdx, rdx
0x140001105  jz      short loc_140001117
0x140001107  mov     rax, rcx
0x14000110a  inc     rax
0x14000110d  cmp     [rdx+rax], r9b
0x140001111  jnz     short loc_14000110A
0x140001113  inc     eax
0x140001115  jmp     short loc_14000111D
0x140001117  mov     rdx, r11
0x14000111a  mov     eax, r8d
0x14000111d  mov     [rbp+7+var_58], eax
0x140001120  mov     rax, [rbp+7+arg_40]
0x140001124  mov     [rbp+7+var_60], rdx
0x140001128  mov     [rbp+7+var_54], r9d
0x14000112c  mov     rdx, [rax]
0x14000112f  test    rdx, rdx
0x140001132  jz      short loc_140001144
0x140001134  mov     rax, rcx
0x140001137  inc     rax
0x14000113a  cmp     [rdx+rax], r9b
0x14000113e  jnz     short loc_140001137
0x140001140  inc     eax
0x140001142  jmp     short loc_14000114A
0x140001144  mov     rdx, r11
0x140001147  mov     eax, r8d
0x14000114a  mov     [rbp+7+var_68], eax
0x14000114d  mov     rax, [rbp+7+arg_38]
0x140001151  mov     [rbp+7+var_70], rdx
0x140001155  mov     [rbp+7+var_64], r9d
0x140001159  mov     rdx, [rax]
0x14000115c  test    rdx, rdx
0x14000115f  jz      short loc_140001171
0x140001161  mov     rax, rcx
0x140001164  inc     rax
0x140001167  cmp     [rdx+rax], r9b
0x14000116b  jnz     short loc_140001164
0x14000116d  inc     eax
0x14000116f  jmp     short loc_140001177
0x140001171  mov     rdx, r11
0x140001174  mov     eax, r8d
0x140001177  mov     [rbp+7+var_78], eax
0x14000117a  mov     rax, [rbp+7+arg_30]
0x14000117e  mov     [rbp+7+var_80], rdx
0x140001182  mov     [rbp+7+var_74], r9d
0x140001186  mov     rdx, [rax]
0x140001189  test    rdx, rdx
0x14000118c  jz      short loc_14000119D
0x14000118e  inc     rcx
0x140001191  cmp     [rdx+rcx], r9b
0x140001195  jnz     short loc_14000118E
0x140001197  lea     r8d, [rcx+1]
0x14000119b  jmp     short loc_1400011A0
0x14000119d  mov     rdx, r11
0x1400011a0  mov     rax, [rbp+7+arg_28]
0x1400011a4  lea     rcx, dword_140042000
0x1400011ab  mov     [rsp+100h+var_A0], rax
0x1400011b0  mov     rax, [rbp+7+arg_20]
0x1400011b4  mov     [rsp+100h+var_B0], rax
0x1400011b9  lea     rax, [rsp+100h+var_D0]
0x1400011be  mov     [rsp+100h+var_90], rdx
0x1400011c3  mov     rdx, r10
0x1400011c6  mov     [rsp+100h+var_88], r8d
0x1400011cb  xor     r8d, r8d
0x1400011ce  mov     [rsp+100h+var_D8], rax
0x1400011d3  mov     [rsp+100h+var_E0], 0Ch
0x1400011db  mov     [rbp+7+var_84], r9d
0x1400011df  mov     [rsp+100h+var_98], 8
0x1400011e8  mov     [rsp+100h+var_A8], 8
0x1400011f1  call    _tlgWriteTransfer_EventWriteTransfer
0x1400011f6  mov     rcx, [rbp+7+var_10]
0x1400011fa  xor     rcx, rsp; StackCookie
0x1400011fd  call    __security_check_cookie
0x140001202  add     rsp, 100h
0x140001209  pop     rbp
0x14000120a  retn
```
