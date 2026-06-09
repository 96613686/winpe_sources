# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001120`
- end: `0x18000123d`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005a30`

## callees

- `0x180001120`
- `0x180001244`
- `0x18000aea0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        char **a5,
        __int64 a6,
        char **a7,
        __int64 a8,
        char **a9,
        __int64 a10)
{
  __int64 v11; // rcx
  int v12; // r8d
  char *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  char *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  char *v19; // rdx
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+30h] [rbp-69h] BYREF
  char *v22; // [rsp+50h] [rbp-49h]
  int v23; // [rsp+58h] [rbp-41h]
  int v24; // [rsp+5Ch] [rbp-3Dh]
  __int64 v25; // [rsp+60h] [rbp-39h]
  __int64 v26; // [rsp+68h] [rbp-31h]
  char *v27; // [rsp+70h] [rbp-29h]
  int v28; // [rsp+78h] [rbp-21h]
  int v29; // [rsp+7Ch] [rbp-1Dh]
  __int64 v30; // [rsp+80h] [rbp-19h]
  __int64 v31; // [rsp+88h] [rbp-11h]
  char *v32; // [rsp+90h] [rbp-9h]
  int v33; // [rsp+98h] [rbp-1h]
  int v34; // [rsp+9Ch] [rbp+3h]
  __int64 v35; // [rsp+A0h] [rbp+7h]
  __int64 v36; // [rsp+A8h] [rbp+Fh]

  v35 = a10;
  v11 = -1;
  v36 = 4;
  v12 = 1;
  v13 = *a9;
  if ( *a9 )
  {
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    v15 = v14 + 1;
  }
  else
  {
    v13 = byte_18001023D;
    v15 = 1;
  }
  v33 = v15;
  v30 = a8;
  v32 = v13;
  v34 = 0;
  v31 = 4;
  v16 = *a7;
  if ( *a7 )
  {
    v17 = -1;
    do
      ++v17;
    while ( v16[v17] );
    v18 = v17 + 1;
  }
  else
  {
    v16 = byte_18001023D;
    v18 = 1;
  }
  v28 = v18;
  v25 = a6;
  v27 = v16;
  v29 = 0;
  v26 = 4;
  v19 = *a5;
  if ( *a5 )
  {
    do
      ++v11;
    while ( v19[v11] );
    v12 = v11 + 1;
  }
  else
  {
    v19 = byte_18001023D;
  }
  v22 = v19;
  v23 = v12;
  v24 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180013020, a2, 0, 0, 8u, &v21);
}

```

## disassembly

```asm
0x180001120  push    rbp
0x180001122  lea     rbp, [rsp-27h]
0x180001127  sub     rsp, 0C0h
0x18000112e  mov     rax, cs:__security_cookie
0x180001135  xor     rax, rsp
0x180001138  mov     [rbp+27h+var_10], rax
0x18000113c  mov     rax, [rbp+27h+arg_48]
0x180001140  lea     r11, byte_18001023D
0x180001147  xor     r9d, r9d
0x18000114a  mov     [rbp+27h+var_20], rax
0x18000114e  mov     rax, [rbp+27h+arg_40]
0x180001152  mov     r10, rdx
0x180001155  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001159  mov     [rbp+27h+var_18], 4
0x180001161  lea     r8d, [r9+1]
0x180001165  mov     rdx, [rax]
0x180001168  test    rdx, rdx
0x18000116b  jz      short loc_18000117D
0x18000116d  mov     rax, rcx
0x180001170  inc     rax
0x180001173  cmp     [rdx+rax], r9b
0x180001177  jnz     short loc_180001170
0x180001179  inc     eax
0x18000117b  jmp     short loc_180001183
0x18000117d  mov     rdx, r11
0x180001180  mov     eax, r8d
0x180001183  mov     [rbp+27h+var_28], eax
0x180001186  mov     rax, [rbp+27h+arg_38]
0x18000118a  mov     [rbp+27h+var_40], rax
0x18000118e  mov     rax, [rbp+27h+arg_30]
0x180001192  mov     [rbp+27h+var_30], rdx
0x180001196  mov     [rbp+27h+var_24], r9d
0x18000119a  mov     [rbp+27h+var_38], 4
0x1800011a2  mov     rdx, [rax]
0x1800011a5  test    rdx, rdx
0x1800011a8  jz      short loc_1800011BA
0x1800011aa  mov     rax, rcx
0x1800011ad  inc     rax
0x1800011b0  cmp     [rdx+rax], r9b
0x1800011b4  jnz     short loc_1800011AD
0x1800011b6  inc     eax
0x1800011b8  jmp     short loc_1800011C0
0x1800011ba  mov     rdx, r11
0x1800011bd  mov     eax, r8d
0x1800011c0  mov     [rbp+27h+var_48], eax
0x1800011c3  mov     rax, [rbp+27h+arg_28]
0x1800011c7  mov     [rbp+27h+var_60], rax
0x1800011cb  mov     rax, [rbp+27h+arg_20]
0x1800011cf  mov     [rbp+27h+var_50], rdx
0x1800011d3  mov     [rbp+27h+var_44], r9d
0x1800011d7  mov     [rbp+27h+var_58], 4
0x1800011df  mov     rdx, [rax]
0x1800011e2  test    rdx, rdx
0x1800011e5  jz      short loc_1800011F6
0x1800011e7  inc     rcx
0x1800011ea  cmp     [rdx+rcx], r9b
0x1800011ee  jnz     short loc_1800011E7
0x1800011f0  lea     r8d, [rcx+1]
0x1800011f4  jmp     short loc_1800011F9
0x1800011f6  mov     rdx, r11
0x1800011f9  lea     rax, [rbp+27h+var_90]
0x1800011fd  mov     [rbp+27h+var_70], rdx
0x180001201  mov     [rbp+27h+var_68], r8d
0x180001205  lea     rcx, dword_180013020
0x18000120c  mov     [rsp+0C0h+var_98], rax
0x180001211  xor     r8d, r8d
0x180001214  mov     rdx, r10
0x180001217  mov     [rsp+0C0h+var_A0], 8
0x18000121f  mov     [rbp+27h+var_64], r9d
0x180001223  call    _tlgWriteTransfer_EventWriteTransfer
0x180001228  mov     rcx, [rbp+27h+var_10]
0x18000122c  xor     rcx, rsp; StackCookie
0x18000122f  call    __security_check_cookie
0x180001234  add     rsp, 0C0h
0x18000123b  pop     rbp
0x18000123c  retn
```
