# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x18000131c`
- end: `0x18000160c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800252c0`
- `0x1800258b0`

## callees

- `0x18000131c`
- `0x1800018c8`
- `0x18002a590`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const CHAR **a7,
        __int64 a8,
        const CHAR **a9,
        __int64 a10,
        int **a11,
        __int64 a12,
        const CHAR **a13,
        __int64 a14,
        const CHAR **a15,
        int **a16,
        __int64 a17,
        const CHAR **a18,
        int **a19,
        __int64 a20,
        __int64 a21,
        const CHAR **a22)
{
  __int64 v24; // rdx
  int v26; // r8d
  const CHAR *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // r9d
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const CHAR *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  int *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const CHAR *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const CHAR *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  int *v46; // rcx
  __int64 v47; // rax
  const CHAR *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const CHAR *v51; // rcx
  struct _EVENT_DATA_DESCRIPTOR v53; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+68h] [rbp-98h]
  const CHAR *v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+78h] [rbp-88h]
  int v60; // [rsp+7Ch] [rbp-84h]
  __int64 v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  const CHAR *v63; // [rsp+90h] [rbp-70h]
  int v64; // [rsp+98h] [rbp-68h]
  int v65; // [rsp+9Ch] [rbp-64h]
  __int64 v66; // [rsp+A0h] [rbp-60h]
  __int64 v67; // [rsp+A8h] [rbp-58h]
  int *v68; // [rsp+B0h] [rbp-50h]
  int v69; // [rsp+B8h] [rbp-48h]
  int v70; // [rsp+BCh] [rbp-44h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  const CHAR *v73; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+D8h] [rbp-28h]
  int v75; // [rsp+DCh] [rbp-24h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  __int64 v77; // [rsp+E8h] [rbp-18h]
  const CHAR *v78; // [rsp+F0h] [rbp-10h]
  int v79; // [rsp+F8h] [rbp-8h]
  int v80; // [rsp+FCh] [rbp-4h]
  int *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const CHAR *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  int *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  __int64 v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]
  __int64 v94; // [rsp+150h] [rbp+50h]
  __int64 v95; // [rsp+158h] [rbp+58h]
  const CHAR *v96; // [rsp+160h] [rbp+60h]
  int v97; // [rsp+168h] [rbp+68h]
  int v98; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v26 = 1;
  v27 = *a22;
  if ( *a22 )
  {
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &Class;
    v29 = 1;
  }
  v97 = v29;
  v30 = 2;
  v94 = a21;
  v92 = a20;
  v96 = v27;
  v98 = 0;
  v95 = 4;
  v31 = *a19;
  v93 = 4;
  if ( v31 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_18002C8C4;
    v33 = 2;
  }
  v90 = v33;
  v89 = v31;
  v91 = 0;
  v34 = *a18;
  if ( *a18 )
  {
    v35 = -1;
    do
      ++v35;
    while ( v34[v35] );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &Class;
    v36 = 1;
  }
  v87 = v36;
  v84 = a17;
  v86 = v34;
  v88 = 0;
  v85 = 4;
  v37 = *a16;
  if ( *a16 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_WORD *)v37 + v38) );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &dword_18002C8C4;
    v39 = 2;
  }
  v82 = v39;
  v81 = v37;
  v83 = 0;
  v40 = *a15;
  if ( *a15 )
  {
    v41 = -1;
    do
      ++v41;
    while ( v40[v41] );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &Class;
    v42 = 1;
  }
  v79 = v42;
  v76 = a14;
  v78 = v40;
  v80 = 0;
  v77 = 4;
  v43 = *a13;
  if ( *a13 )
  {
    v44 = -1;
    do
      ++v44;
    while ( v43[v44] );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &Class;
    v45 = 1;
  }
  v74 = v45;
  v71 = a12;
  v73 = v43;
  v75 = 0;
  v72 = 4;
  v46 = *a11;
  if ( *a11 )
  {
    v47 = -1;
    do
      ++v47;
    while ( *((_WORD *)v46 + v47) );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = &dword_18002C8C4;
  }
  v66 = a10;
  v68 = v46;
  v69 = v30;
  v70 = 0;
  v48 = *a9;
  v67 = 4;
  if ( v48 )
  {
    v49 = -1;
    do
      ++v49;
    while ( v48[v49] );
    v50 = v49 + 1;
  }
  else
  {
    v48 = &Class;
    v50 = 1;
  }
  v64 = v50;
  v61 = a8;
  v63 = v48;
  v65 = 0;
  v62 = 4;
  v51 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( v51[v24] );
    v26 = v24 + 1;
  }
  else
  {
    v51 = &Class;
  }
  v56 = a6;
  v54 = a5;
  v58 = v51;
  v59 = v26;
  v60 = 0;
  v57 = 4;
  v55 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x14u, &v53);
}

```

## disassembly

```asm
0x18000131c  push    rbp
0x18000131e  push    rbx
0x18000131f  push    rsi
0x180001320  push    rdi
0x180001321  push    r15
0x180001323  lea     rbp, [rsp-80h]
0x180001328  sub     rsp, 180h
0x18000132f  mov     rax, cs:__security_cookie
0x180001336  xor     rax, rsp
0x180001339  mov     [rbp+0A0h+var_30], rax
0x18000133d  mov     rax, [rbp+0A0h+arg_A8]
0x180001344  lea     rsi, Class
0x18000134b  mov     r11, rdx
0x18000134e  mov     r10, rcx
0x180001351  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001355  xor     edi, edi
0x180001357  mov     rbx, r8
0x18000135a  mov     r8d, 1
0x180001360  mov     rcx, [rax]
0x180001363  test    rcx, rcx
0x180001366  jz      short loc_180001378
0x180001368  mov     rax, rdx
0x18000136b  inc     rax
0x18000136e  cmp     [rcx+rax], dil
0x180001372  jnz     short loc_18000136B
0x180001374  inc     eax
0x180001376  jmp     short loc_18000137E
0x180001378  mov     rcx, rsi
0x18000137b  mov     eax, r8d
0x18000137e  mov     [rbp+0A0h+var_38], eax
0x180001381  mov     r9d, 2
0x180001387  mov     rax, [rbp+0A0h+arg_A0]
0x18000138e  mov     [rbp+0A0h+var_50], rax
0x180001392  mov     rax, [rbp+0A0h+arg_98]
0x180001399  mov     [rbp+0A0h+var_60], rax
0x18000139d  mov     rax, [rbp+0A0h+arg_90]
0x1800013a4  mov     [rbp+0A0h+var_40], rcx
0x1800013a8  mov     [rbp+0A0h+var_34], edi
0x1800013ab  mov     [rbp+0A0h+var_48], 4
0x1800013b3  mov     rcx, [rax]
0x1800013b6  mov     [rbp+0A0h+var_58], 4
0x1800013be  test    rcx, rcx
0x1800013c1  jz      short loc_1800013D8
0x1800013c3  mov     rax, rdx
0x1800013c6  inc     rax
0x1800013c9  cmp     [rcx+rax*2], di
0x1800013cd  jnz     short loc_1800013C6
0x1800013cf  lea     eax, ds:2[rax*2]
0x1800013d6  jmp     short loc_1800013E2
0x1800013d8  lea     rcx, dword_18002C8C4
0x1800013df  mov     eax, r9d
0x1800013e2  mov     [rbp+0A0h+var_68], eax
0x1800013e5  mov     rax, [rbp+0A0h+arg_88]
0x1800013ec  mov     [rbp+0A0h+var_70], rcx
0x1800013f0  mov     [rbp+0A0h+var_64], edi
0x1800013f3  mov     rcx, [rax]
0x1800013f6  test    rcx, rcx
0x1800013f9  jz      short loc_18000140B
0x1800013fb  mov     rax, rdx
0x1800013fe  inc     rax
0x180001401  cmp     [rcx+rax], dil
0x180001405  jnz     short loc_1800013FE
0x180001407  inc     eax
0x180001409  jmp     short loc_180001411
0x18000140b  mov     rcx, rsi
0x18000140e  mov     eax, r8d
0x180001411  mov     [rbp+0A0h+var_78], eax
0x180001414  mov     rax, [rbp+0A0h+arg_80]
0x18000141b  mov     [rbp+0A0h+var_90], rax
0x18000141f  mov     rax, [rbp+0A0h+arg_78]
0x180001426  mov     [rbp+0A0h+var_80], rcx
0x18000142a  mov     [rbp+0A0h+var_74], edi
0x18000142d  mov     [rbp+0A0h+var_88], 4
0x180001435  mov     rcx, [rax]
0x180001438  test    rcx, rcx
0x18000143b  jz      short loc_180001452
0x18000143d  mov     rax, rdx
0x180001440  inc     rax
0x180001443  cmp     [rcx+rax*2], di
0x180001447  jnz     short loc_180001440
0x180001449  lea     eax, ds:2[rax*2]
0x180001450  jmp     short loc_18000145C
0x180001452  lea     rcx, dword_18002C8C4
0x180001459  mov     eax, r9d
0x18000145c  mov     [rbp+0A0h+var_98], eax
0x18000145f  mov     rax, [rbp+0A0h+arg_70]
0x180001466  mov     [rbp+0A0h+var_A0], rcx
0x18000146a  mov     [rbp+0A0h+var_94], edi
0x18000146d  mov     rcx, [rax]
0x180001470  test    rcx, rcx
0x180001473  jz      short loc_180001485
0x180001475  mov     rax, rdx
0x180001478  inc     rax
0x18000147b  cmp     [rcx+rax], dil
0x18000147f  jnz     short loc_180001478
0x180001481  inc     eax
0x180001483  jmp     short loc_18000148B
0x180001485  mov     rcx, rsi
0x180001488  mov     eax, r8d
0x18000148b  mov     [rbp+0A0h+var_A8], eax
0x18000148e  mov     rax, [rbp+0A0h+arg_68]
0x180001495  mov     [rbp+0A0h+var_C0], rax
0x180001499  mov     rax, [rbp+0A0h+arg_60]
0x1800014a0  mov     [rbp+0A0h+var_B0], rcx
0x1800014a4  mov     [rbp+0A0h+var_A4], edi
0x1800014a7  mov     [rbp+0A0h+var_B8], 4
0x1800014af  mov     rcx, [rax]
0x1800014b2  test    rcx, rcx
0x1800014b5  jz      short loc_1800014C7
0x1800014b7  mov     rax, rdx
0x1800014ba  inc     rax
0x1800014bd  cmp     [rcx+rax], dil
0x1800014c1  jnz     short loc_1800014BA
0x1800014c3  inc     eax
0x1800014c5  jmp     short loc_1800014CD
0x1800014c7  mov     rcx, rsi
0x1800014ca  mov     eax, r8d
0x1800014cd  mov     [rbp+0A0h+var_C8], eax
0x1800014d0  mov     rax, [rbp+0A0h+arg_58]
0x1800014d7  mov     [rbp+0A0h+var_E0], rax
0x1800014db  mov     rax, [rbp+0A0h+arg_50]
0x1800014e2  mov     [rbp+0A0h+var_D0], rcx
0x1800014e6  mov     [rbp+0A0h+var_C4], edi
0x1800014e9  mov     [rbp+0A0h+var_D8], 4
0x1800014f1  mov     rcx, [rax]
0x1800014f4  test    rcx, rcx
0x1800014f7  jz      short loc_18000150F
0x1800014f9  mov     rax, rdx
0x1800014fc  inc     rax
0x1800014ff  cmp     [rcx+rax*2], di
0x180001503  jnz     short loc_1800014FC
0x180001505  lea     r9d, ds:2[rax*2]
0x18000150d  jmp     short loc_180001516
0x18000150f  lea     rcx, dword_18002C8C4
0x180001516  mov     rax, [rbp+0A0h+arg_48]
0x18000151d  mov     [rbp+0A0h+var_100], rax
0x180001521  mov     rax, [rbp+0A0h+arg_40]
0x180001528  mov     [rbp+0A0h+var_F0], rcx
0x18000152c  mov     [rbp+0A0h+var_E8], r9d
0x180001530  mov     [rbp+0A0h+var_E4], edi
0x180001533  mov     rcx, [rax]
0x180001536  mov     [rbp+0A0h+var_F8], 4
0x18000153e  test    rcx, rcx
0x180001541  jz      short loc_180001553
0x180001543  mov     rax, rdx
0x180001546  inc     rax
0x180001549  cmp     [rcx+rax], dil
0x18000154d  jnz     short loc_180001546
0x18000154f  inc     eax
0x180001551  jmp     short loc_180001559
0x180001553  mov     rcx, rsi
0x180001556  mov     eax, r8d
0x180001559  mov     [rbp+0A0h+var_108], eax
0x18000155c  mov     rax, [rbp+0A0h+arg_38]
0x180001563  mov     [rbp+0A0h+var_120], rax
0x180001567  mov     rax, [rbp+0A0h+arg_30]
0x18000156e  mov     [rbp+0A0h+var_110], rcx
0x180001572  mov     [rbp+0A0h+var_104], edi
0x180001575  mov     [rbp+0A0h+var_118], 4
0x18000157d  mov     rcx, [rax]
0x180001580  test    rcx, rcx
0x180001583  jz      short loc_180001594
0x180001585  inc     rdx
0x180001588  cmp     [rcx+rdx], dil
0x18000158c  jnz     short loc_180001585
0x18000158e  lea     r8d, [rdx+1]
0x180001592  jmp     short loc_180001597
0x180001594  mov     rcx, rsi
0x180001597  mov     rax, [rbp+0A0h+arg_28]
0x18000159e  xor     r9d, r9d
0x1800015a1  mov     [rsp+1A0h+var_140], rax
0x1800015a6  mov     rdx, r11
0x1800015a9  mov     rax, [rbp+0A0h+arg_20]
0x1800015b0  mov     [rsp+1A0h+var_150], rax
0x1800015b5  lea     rax, [rsp+1A0h+var_170]
0x1800015ba  mov     [rsp+1A0h+var_130], rcx
0x1800015bf  mov     rcx, r10
0x1800015c2  mov     [rsp+1A0h+var_128], r8d
0x1800015c7  mov     r8, rbx
0x1800015ca  mov     [rsp+1A0h+var_178], rax
0x1800015cf  mov     [rsp+1A0h+var_180], 14h
0x1800015d7  mov     [rsp+1A0h+var_124], edi
0x1800015db  mov     [rsp+1A0h+var_138], 4
0x1800015e4  mov     [rsp+1A0h+var_148], 8
0x1800015ed  call    _tlgWriteTransfer_EventWriteTransfer
0x1800015f2  mov     rcx, [rbp+0A0h+var_30]
0x1800015f6  xor     rcx, rsp; StackCookie
0x1800015f9  call    __security_check_cookie
0x1800015fe  add     rsp, 180h
0x180001605  pop     r15
0x180001607  pop     rdi
0x180001608  pop     rsi
0x180001609  pop     rbx
0x18000160a  pop     rbp
0x18000160b  retn
```
