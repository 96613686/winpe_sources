# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180003be0`
- end: `0x180003e7b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180027e30`
- `0x180029198`

## callees

- `0x180001010`
- `0x180003be0`
- `0x1800050f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        int **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        int **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        int **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  int *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rcx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v52; // [rsp+70h] [rbp-90h]
  int v53; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+7Ch] [rbp-84h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v57; // [rsp+90h] [rbp-70h]
  int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+9Ch] [rbp-64h]
  __int64 v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  int *v62; // [rsp+B0h] [rbp-50h]
  int v63; // [rsp+B8h] [rbp-48h]
  int v64; // [rsp+BCh] [rbp-44h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int64 v66; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v67; // [rsp+D0h] [rbp-30h]
  int v68; // [rsp+D8h] [rbp-28h]
  int v69; // [rsp+DCh] [rbp-24h]
  __int64 v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+FCh] [rbp-4h]
  int *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  int *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]

  v21 = -1;
  v23 = 2;
  v24 = *a19;
  if ( *a19 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &dword_180031EE4;
    v26 = 2;
  }
  v84 = v26;
  v27 = 1;
  v83 = v24;
  v85 = 0;
  v28 = *a18;
  if ( *a18 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &byte_180031EE0;
    v30 = 1;
  }
  v81 = v30;
  v78 = a17;
  v80 = v28;
  v82 = 0;
  v79 = 4;
  v31 = *a16;
  if ( *a16 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_180031EE4;
    v33 = 2;
  }
  v76 = v33;
  v75 = v31;
  v77 = 0;
  v34 = *a15;
  if ( *a15 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &byte_180031EE0;
    v36 = 1;
  }
  v73 = v36;
  v70 = a14;
  v72 = v34;
  v74 = 0;
  v71 = 4;
  v37 = *a13;
  if ( *a13 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &byte_180031EE0;
    v39 = 1;
  }
  v68 = v39;
  v65 = a12;
  v67 = v37;
  v69 = 0;
  v66 = 4;
  v40 = *a11;
  if ( *a11 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_WORD *)v40 + v41) );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &dword_180031EE4;
  }
  v60 = a10;
  v62 = v40;
  v63 = v23;
  v64 = 0;
  v42 = *a9;
  v61 = 4;
  if ( v42 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &byte_180031EE0;
    v44 = 1;
  }
  v58 = v44;
  v55 = a8;
  v57 = v42;
  v59 = 0;
  v56 = 4;
  v45 = *a7;
  if ( *a7 )
  {
    do
      ++v21;
    while ( *((_BYTE *)v45 + v21) );
    v27 = v21 + 1;
  }
  else
  {
    v45 = &byte_180031EE0;
  }
  v50 = a6;
  v48 = a5;
  v52 = v45;
  v53 = v27;
  v54 = 0;
  v51 = 4;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x11u, &v47);
}

```

## disassembly

```asm
0x180003be0  push    rbp
0x180003be2  push    rbx
0x180003be3  push    rsi
0x180003be4  push    rdi
0x180003be5  push    r14
0x180003be7  lea     rbp, [rsp-50h]
0x180003bec  sub     rsp, 150h
0x180003bf3  mov     rax, cs:__security_cookie
0x180003bfa  xor     rax, rsp
0x180003bfd  mov     [rbp+70h+var_30], rax
0x180003c01  mov     rax, [rbp+70h+arg_90]
0x180003c08  mov     r11, rdx
0x180003c0b  mov     r10, rcx
0x180003c0e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180003c12  xor     edi, edi
0x180003c14  mov     rbx, r8
0x180003c17  mov     r9d, 2
0x180003c1d  mov     rcx, [rax]
0x180003c20  test    rcx, rcx
0x180003c23  jz      short loc_180003C3A
0x180003c25  mov     rax, rdx
0x180003c28  inc     rax
0x180003c2b  cmp     [rcx+rax*2], di
0x180003c2f  jnz     short loc_180003C28
0x180003c31  lea     eax, ds:2[rax*2]
0x180003c38  jmp     short loc_180003C44
0x180003c3a  lea     rcx, dword_180031EE4
0x180003c41  mov     eax, r9d
0x180003c44  mov     [rbp+70h+var_38], eax
0x180003c47  lea     rsi, byte_180031EE0
0x180003c4e  mov     rax, [rbp+70h+arg_88]
0x180003c55  mov     r8d, 1
0x180003c5b  mov     [rbp+70h+var_40], rcx
0x180003c5f  mov     [rbp+70h+var_34], edi
0x180003c62  mov     rcx, [rax]
0x180003c65  test    rcx, rcx
0x180003c68  jz      short loc_180003C7A
0x180003c6a  mov     rax, rdx
0x180003c6d  inc     rax
0x180003c70  cmp     [rcx+rax], dil
0x180003c74  jnz     short loc_180003C6D
0x180003c76  inc     eax
0x180003c78  jmp     short loc_180003C80
0x180003c7a  mov     rcx, rsi
0x180003c7d  mov     eax, r8d
0x180003c80  mov     [rbp+70h+var_48], eax
0x180003c83  mov     rax, [rbp+70h+arg_80]
0x180003c8a  mov     [rbp+70h+var_60], rax
0x180003c8e  mov     rax, [rbp+70h+arg_78]
0x180003c95  mov     [rbp+70h+var_50], rcx
0x180003c99  mov     [rbp+70h+var_44], edi
0x180003c9c  mov     [rbp+70h+var_58], 4
0x180003ca4  mov     rcx, [rax]
0x180003ca7  test    rcx, rcx
0x180003caa  jz      short loc_180003CC1
0x180003cac  mov     rax, rdx
0x180003caf  inc     rax
0x180003cb2  cmp     [rcx+rax*2], di
0x180003cb6  jnz     short loc_180003CAF
0x180003cb8  lea     eax, ds:2[rax*2]
0x180003cbf  jmp     short loc_180003CCB
0x180003cc1  lea     rcx, dword_180031EE4
0x180003cc8  mov     eax, r9d
0x180003ccb  mov     [rbp+70h+var_68], eax
0x180003cce  mov     rax, [rbp+70h+arg_70]
0x180003cd5  mov     [rbp+70h+var_70], rcx
0x180003cd9  mov     [rbp+70h+var_64], edi
0x180003cdc  mov     rcx, [rax]
0x180003cdf  test    rcx, rcx
0x180003ce2  jz      short loc_180003CF4
0x180003ce4  mov     rax, rdx
0x180003ce7  inc     rax
0x180003cea  cmp     [rcx+rax], dil
0x180003cee  jnz     short loc_180003CE7
0x180003cf0  inc     eax
0x180003cf2  jmp     short loc_180003CFA
0x180003cf4  mov     rcx, rsi
0x180003cf7  mov     eax, r8d
0x180003cfa  mov     [rbp+70h+var_78], eax
0x180003cfd  mov     rax, [rbp+70h+arg_68]
0x180003d04  mov     [rbp+70h+var_90], rax
0x180003d08  mov     rax, [rbp+70h+arg_60]
0x180003d0f  mov     [rbp+70h+var_80], rcx
0x180003d13  mov     [rbp+70h+var_74], edi
0x180003d16  mov     [rbp+70h+var_88], 4
0x180003d1e  mov     rcx, [rax]
0x180003d21  test    rcx, rcx
0x180003d24  jz      short loc_180003D36
0x180003d26  mov     rax, rdx
0x180003d29  inc     rax
0x180003d2c  cmp     [rcx+rax], dil
0x180003d30  jnz     short loc_180003D29
0x180003d32  inc     eax
0x180003d34  jmp     short loc_180003D3C
0x180003d36  mov     rcx, rsi
0x180003d39  mov     eax, r8d
0x180003d3c  mov     [rbp+70h+var_98], eax
0x180003d3f  mov     rax, [rbp+70h+arg_58]
0x180003d46  mov     [rbp+70h+var_B0], rax
0x180003d4a  mov     rax, [rbp+70h+arg_50]
0x180003d51  mov     [rbp+70h+var_A0], rcx
0x180003d55  mov     [rbp+70h+var_94], edi
0x180003d58  mov     [rbp+70h+var_A8], 4
0x180003d60  mov     rcx, [rax]
0x180003d63  test    rcx, rcx
0x180003d66  jz      short loc_180003D7E
0x180003d68  mov     rax, rdx
0x180003d6b  inc     rax
0x180003d6e  cmp     [rcx+rax*2], di
0x180003d72  jnz     short loc_180003D6B
0x180003d74  lea     r9d, ds:2[rax*2]
0x180003d7c  jmp     short loc_180003D85
0x180003d7e  lea     rcx, dword_180031EE4
0x180003d85  mov     rax, [rbp+70h+arg_48]
0x180003d8c  mov     [rbp+70h+var_D0], rax
0x180003d90  mov     rax, [rbp+70h+arg_40]
0x180003d97  mov     [rbp+70h+var_C0], rcx
0x180003d9b  mov     [rbp+70h+var_B8], r9d
0x180003d9f  mov     [rbp+70h+var_B4], edi
0x180003da2  mov     rcx, [rax]
0x180003da5  mov     [rbp+70h+var_C8], 4
0x180003dad  test    rcx, rcx
0x180003db0  jz      short loc_180003DC2
0x180003db2  mov     rax, rdx
0x180003db5  inc     rax
0x180003db8  cmp     [rcx+rax], dil
0x180003dbc  jnz     short loc_180003DB5
0x180003dbe  inc     eax
0x180003dc0  jmp     short loc_180003DC8
0x180003dc2  mov     rcx, rsi
0x180003dc5  mov     eax, r8d
0x180003dc8  mov     [rbp+70h+var_D8], eax
0x180003dcb  mov     rax, [rbp+70h+arg_38]
0x180003dd2  mov     [rbp+70h+var_F0], rax
0x180003dd6  mov     rax, [rbp+70h+arg_30]
0x180003ddd  mov     [rbp+70h+var_E0], rcx
0x180003de1  mov     [rbp+70h+var_D4], edi
0x180003de4  mov     [rbp+70h+var_E8], 4
0x180003dec  mov     rcx, [rax]
0x180003def  test    rcx, rcx
0x180003df2  jz      short loc_180003E03
0x180003df4  inc     rdx
0x180003df7  cmp     [rcx+rdx], dil
0x180003dfb  jnz     short loc_180003DF4
0x180003dfd  lea     r8d, [rdx+1]
0x180003e01  jmp     short loc_180003E06
0x180003e03  mov     rcx, rsi
0x180003e06  mov     rax, [rbp+70h+arg_28]
0x180003e0d  xor     r9d, r9d
0x180003e10  mov     [rsp+170h+var_110], rax
0x180003e15  mov     rdx, r11
0x180003e18  mov     rax, [rbp+70h+arg_20]
0x180003e1f  mov     [rsp+170h+var_120], rax
0x180003e24  lea     rax, [rsp+170h+var_140]
0x180003e29  mov     [rsp+170h+var_100], rcx
0x180003e2e  mov     rcx, r10
0x180003e31  mov     [rsp+170h+var_F8], r8d
0x180003e36  mov     r8, rbx
0x180003e39  mov     [rsp+170h+var_148], rax
0x180003e3e  mov     [rsp+170h+var_150], 11h
0x180003e46  mov     [rsp+170h+var_F4], edi
0x180003e4a  mov     [rsp+170h+var_108], 4
0x180003e53  mov     [rsp+170h+var_118], 8
0x180003e5c  call    _tlgWriteTransfer_EventWriteTransfer
0x180003e61  mov     rcx, [rbp+70h+var_30]
0x180003e65  xor     rcx, rsp; StackCookie
0x180003e68  call    __security_check_cookie
0x180003e6d  add     rsp, 150h
0x180003e74  pop     r14
0x180003e76  pop     rdi
0x180003e77  pop     rsi
0x180003e78  pop     rbx
0x180003e79  pop     rbp
0x180003e7a  retn
```
