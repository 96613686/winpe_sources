# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001d1c`
- end: `0x14000200b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017b24`

## callees

- `0x14000162c`
- `0x140001d1c`
- `0x140003200`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const wchar_t **a7,
        __int64 a8,
        const wchar_t **a9,
        __int64 a10,
        void **a11,
        __int64 a12,
        const wchar_t **a13,
        __int64 a14,
        const wchar_t **a15,
        void **a16,
        __int64 a17,
        const wchar_t **a18,
        void **a19,
        __int64 a20,
        __int64 a21,
        const wchar_t **a22)
{
  __int64 v24; // rdx
  int v25; // r8d
  const wchar_t *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r9d
  _WORD *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const wchar_t *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  _WORD *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const wchar_t *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const wchar_t *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  _WORD *v45; // rcx
  __int64 v46; // rax
  const wchar_t *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  const wchar_t *v50; // rcx
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  const wchar_t *v57; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+7Ch] [rbp-84h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  const wchar_t *v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  _WORD *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  const wchar_t *v72; // [rsp+D0h] [rbp-30h]
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  const wchar_t *v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+F8h] [rbp-8h]
  int v79; // [rsp+FCh] [rbp-4h]
  _WORD *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const wchar_t *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  _WORD *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  const wchar_t *v95; // [rsp+160h] [rbp+60h]
  int v96; // [rsp+168h] [rbp+68h]
  int v97; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v25 = 1;
  v26 = *a22;
  if ( *a22 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &word_140024070;
    v28 = 1;
  }
  v96 = v28;
  v29 = 2;
  v93 = a21;
  v91 = a20;
  v95 = v26;
  v97 = 0;
  v94 = 4;
  v30 = *a19;
  v92 = 4;
  if ( v30 )
  {
    v31 = -1;
    do
      ++v31;
    while ( v30[v31] );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &unk_1400241F4;
    v32 = 2;
  }
  v89 = v32;
  v88 = v30;
  v90 = 0;
  v33 = *a18;
  if ( *a18 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &word_140024070;
    v35 = 1;
  }
  v86 = v35;
  v83 = a17;
  v85 = v33;
  v87 = 0;
  v84 = 4;
  v36 = *a16;
  if ( *a16 )
  {
    v37 = -1;
    do
      ++v37;
    while ( v36[v37] );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &unk_1400241F4;
    v38 = 2;
  }
  v81 = v38;
  v80 = v36;
  v82 = 0;
  v39 = *a15;
  if ( *a15 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &word_140024070;
    v41 = 1;
  }
  v78 = v41;
  v75 = a14;
  v77 = v39;
  v79 = 0;
  v76 = 4;
  v42 = *a13;
  if ( *a13 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &word_140024070;
    v44 = 1;
  }
  v73 = v44;
  v70 = a12;
  v72 = v42;
  v74 = 0;
  v71 = 4;
  v45 = *a11;
  if ( *a11 )
  {
    v46 = -1;
    do
      ++v46;
    while ( v45[v46] );
    v29 = 2 * v46 + 2;
  }
  else
  {
    v45 = &unk_1400241F4;
  }
  v65 = a10;
  v67 = v45;
  v68 = v29;
  v69 = 0;
  v47 = *a9;
  v66 = 4;
  if ( v47 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_BYTE *)v47 + v48) );
    v49 = v48 + 1;
  }
  else
  {
    v47 = &word_140024070;
    v49 = 1;
  }
  v63 = v49;
  v60 = a8;
  v62 = v47;
  v64 = 0;
  v61 = 4;
  v50 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v50 + v24) );
    v25 = v24 + 1;
  }
  else
  {
    v50 = &word_140024070;
  }
  v55 = a6;
  v53 = a5;
  v57 = v50;
  v58 = v25;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x14u, &v52);
}

```

## disassembly

```asm
0x140001d1c  mov     [rsp-8+arg_10], rbx
0x140001d21  push    rbp
0x140001d22  push    rdi
0x140001d23  push    r14
0x140001d25  lea     rbp, [rsp-80h]
0x140001d2a  sub     rsp, 180h
0x140001d31  mov     rax, cs:__security_cookie
0x140001d38  xor     rax, rsp
0x140001d3b  mov     [rbp+90h+var_20], rax
0x140001d3f  mov     rax, [rbp+90h+arg_A8]
0x140001d46  lea     rdi, word_140024070
0x140001d4d  mov     r11, rdx
0x140001d50  mov     r10, rcx
0x140001d53  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001d57  xor     ebx, ebx
0x140001d59  mov     r8d, 1
0x140001d5f  mov     rcx, [rax]
0x140001d62  test    rcx, rcx
0x140001d65  jz      short loc_140001D76
0x140001d67  mov     rax, rdx
0x140001d6a  inc     rax
0x140001d6d  cmp     [rcx+rax], bl
0x140001d70  jnz     short loc_140001D6A
0x140001d72  inc     eax
0x140001d74  jmp     short loc_140001D7C
0x140001d76  mov     rcx, rdi
0x140001d79  mov     eax, r8d
0x140001d7c  mov     [rbp+90h+var_28], eax
0x140001d7f  mov     r9d, 2
0x140001d85  mov     rax, [rbp+90h+arg_A0]
0x140001d8c  mov     [rbp+90h+var_40], rax
0x140001d90  mov     rax, [rbp+90h+arg_98]
0x140001d97  mov     [rbp+90h+var_50], rax
0x140001d9b  mov     rax, [rbp+90h+arg_90]
0x140001da2  mov     [rbp+90h+var_30], rcx
0x140001da6  mov     [rbp+90h+var_24], ebx
0x140001da9  mov     [rbp+90h+var_38], 4
0x140001db1  mov     rcx, [rax]
0x140001db4  mov     [rbp+90h+var_48], 4
0x140001dbc  test    rcx, rcx
0x140001dbf  jz      short loc_140001DD6
0x140001dc1  mov     rax, rdx
0x140001dc4  inc     rax
0x140001dc7  cmp     [rcx+rax*2], bx
0x140001dcb  jnz     short loc_140001DC4
0x140001dcd  lea     eax, ds:2[rax*2]
0x140001dd4  jmp     short loc_140001DE0
0x140001dd6  lea     rcx, unk_1400241F4
0x140001ddd  mov     eax, r9d
0x140001de0  mov     [rbp+90h+var_58], eax
0x140001de3  mov     rax, [rbp+90h+arg_88]
0x140001dea  mov     [rbp+90h+var_60], rcx
0x140001dee  mov     [rbp+90h+var_54], ebx
0x140001df1  mov     rcx, [rax]
0x140001df4  test    rcx, rcx
0x140001df7  jz      short loc_140001E08
0x140001df9  mov     rax, rdx
0x140001dfc  inc     rax
0x140001dff  cmp     [rcx+rax], bl
0x140001e02  jnz     short loc_140001DFC
0x140001e04  inc     eax
0x140001e06  jmp     short loc_140001E0E
0x140001e08  mov     rcx, rdi
0x140001e0b  mov     eax, r8d
0x140001e0e  mov     [rbp+90h+var_68], eax
0x140001e11  mov     rax, [rbp+90h+arg_80]
0x140001e18  mov     [rbp+90h+var_80], rax
0x140001e1c  mov     rax, [rbp+90h+arg_78]
0x140001e23  mov     [rbp+90h+var_70], rcx
0x140001e27  mov     [rbp+90h+var_64], ebx
0x140001e2a  mov     [rbp+90h+var_78], 4
0x140001e32  mov     rcx, [rax]
0x140001e35  test    rcx, rcx
0x140001e38  jz      short loc_140001E4F
0x140001e3a  mov     rax, rdx
0x140001e3d  inc     rax
0x140001e40  cmp     [rcx+rax*2], bx
0x140001e44  jnz     short loc_140001E3D
0x140001e46  lea     eax, ds:2[rax*2]
0x140001e4d  jmp     short loc_140001E59
0x140001e4f  lea     rcx, unk_1400241F4
0x140001e56  mov     eax, r9d
0x140001e59  mov     [rbp+90h+var_88], eax
0x140001e5c  mov     rax, [rbp+90h+arg_70]
0x140001e63  mov     [rbp+90h+var_90], rcx
0x140001e67  mov     [rbp+90h+var_84], ebx
0x140001e6a  mov     rcx, [rax]
0x140001e6d  test    rcx, rcx
0x140001e70  jz      short loc_140001E81
0x140001e72  mov     rax, rdx
0x140001e75  inc     rax
0x140001e78  cmp     [rcx+rax], bl
0x140001e7b  jnz     short loc_140001E75
0x140001e7d  inc     eax
0x140001e7f  jmp     short loc_140001E87
0x140001e81  mov     rcx, rdi
0x140001e84  mov     eax, r8d
0x140001e87  mov     [rbp+90h+var_98], eax
0x140001e8a  mov     rax, [rbp+90h+arg_68]
0x140001e91  mov     [rbp+90h+var_B0], rax
0x140001e95  mov     rax, [rbp+90h+arg_60]
0x140001e9c  mov     [rbp+90h+var_A0], rcx
0x140001ea0  mov     [rbp+90h+var_94], ebx
0x140001ea3  mov     [rbp+90h+var_A8], 4
0x140001eab  mov     rcx, [rax]
0x140001eae  test    rcx, rcx
0x140001eb1  jz      short loc_140001EC2
0x140001eb3  mov     rax, rdx
0x140001eb6  inc     rax
0x140001eb9  cmp     [rcx+rax], bl
0x140001ebc  jnz     short loc_140001EB6
0x140001ebe  inc     eax
0x140001ec0  jmp     short loc_140001EC8
0x140001ec2  mov     rcx, rdi
0x140001ec5  mov     eax, r8d
0x140001ec8  mov     [rbp+90h+var_B8], eax
0x140001ecb  mov     rax, [rbp+90h+arg_58]
0x140001ed2  mov     [rbp+90h+var_D0], rax
0x140001ed6  mov     rax, [rbp+90h+arg_50]
0x140001edd  mov     [rbp+90h+var_C0], rcx
0x140001ee1  mov     [rbp+90h+var_B4], ebx
0x140001ee4  mov     [rbp+90h+var_C8], 4
0x140001eec  mov     rcx, [rax]
0x140001eef  test    rcx, rcx
0x140001ef2  jz      short loc_140001F0A
0x140001ef4  mov     rax, rdx
0x140001ef7  inc     rax
0x140001efa  cmp     [rcx+rax*2], bx
0x140001efe  jnz     short loc_140001EF7
0x140001f00  lea     r9d, ds:2[rax*2]
0x140001f08  jmp     short loc_140001F11
0x140001f0a  lea     rcx, unk_1400241F4
0x140001f11  mov     rax, [rbp+90h+arg_48]
0x140001f18  mov     [rbp+90h+var_F0], rax
0x140001f1c  mov     rax, [rbp+90h+arg_40]
0x140001f23  mov     [rbp+90h+var_E0], rcx
0x140001f27  mov     [rbp+90h+var_D8], r9d
0x140001f2b  mov     [rbp+90h+var_D4], ebx
0x140001f2e  mov     rcx, [rax]
0x140001f31  mov     [rbp+90h+var_E8], 4
0x140001f39  test    rcx, rcx
0x140001f3c  jz      short loc_140001F4D
0x140001f3e  mov     rax, rdx
0x140001f41  inc     rax
0x140001f44  cmp     [rcx+rax], bl
0x140001f47  jnz     short loc_140001F41
0x140001f49  inc     eax
0x140001f4b  jmp     short loc_140001F53
0x140001f4d  mov     rcx, rdi
0x140001f50  mov     eax, r8d
0x140001f53  mov     [rbp+90h+var_F8], eax
0x140001f56  mov     rax, [rbp+90h+arg_38]
0x140001f5d  mov     [rbp+90h+var_110], rax
0x140001f61  mov     rax, [rbp+90h+arg_30]
0x140001f68  mov     [rbp+90h+var_100], rcx
0x140001f6c  mov     [rbp+90h+var_F4], ebx
0x140001f6f  mov     [rbp+90h+var_108], 4
0x140001f77  mov     rcx, [rax]
0x140001f7a  test    rcx, rcx
0x140001f7d  jz      short loc_140001F8D
0x140001f7f  inc     rdx
0x140001f82  cmp     [rcx+rdx], bl
0x140001f85  jnz     short loc_140001F7F
0x140001f87  lea     r8d, [rdx+1]
0x140001f8b  jmp     short loc_140001F90
0x140001f8d  mov     rcx, rdi
0x140001f90  mov     rax, [rbp+90h+arg_28]
0x140001f97  xor     r9d, r9d
0x140001f9a  mov     [rsp+190h+var_130], rax
0x140001f9f  mov     rdx, r11
0x140001fa2  mov     rax, [rbp+90h+arg_20]
0x140001fa9  mov     [rsp+190h+var_140], rax
0x140001fae  lea     rax, [rsp+190h+var_160]
0x140001fb3  mov     [rsp+190h+var_120], rcx
0x140001fb8  mov     rcx, r10
0x140001fbb  mov     [rsp+190h+var_118], r8d
0x140001fc0  xor     r8d, r8d
0x140001fc3  mov     [rsp+190h+var_168], rax
0x140001fc8  mov     [rsp+190h+var_170], 14h
0x140001fd0  mov     [rsp+190h+var_114], ebx
0x140001fd4  mov     [rsp+190h+var_128], 4
0x140001fdd  mov     [rsp+190h+var_138], 8
0x140001fe6  call    _tlgWriteTransfer_EventWriteTransfer
0x140001feb  mov     rcx, [rbp+90h+var_20]
0x140001fef  xor     rcx, rsp; StackCookie
0x140001ff2  call    __security_check_cookie
0x140001ff7  mov     rbx, [rsp+190h+arg_10]
0x140001fff  add     rsp, 180h
0x140002006  pop     r14
0x140002008  pop     rdi
0x140002009  pop     rbp
0x14000200a  retn
```
