# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x18000140c`
- end: `0x1800016fc`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(int, int, int, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, char **, __int64, const wchar_t **, __int64, const wchar_t **, char **, __int64, const wchar_t **, char **, __int64, __int64, const wchar_t **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003ed0`
- `0x18000c830`

## callees

- `0x180001350`
- `0x18000140c`
- `0x180010310`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        int a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const wchar_t **a7,
        __int64 a8,
        const wchar_t **a9,
        __int64 a10,
        char **a11,
        __int64 a12,
        const wchar_t **a13,
        __int64 a14,
        const wchar_t **a15,
        char **a16,
        __int64 a17,
        const wchar_t **a18,
        char **a19,
        __int64 a20,
        __int64 a21,
        const wchar_t **a22)
{
  __int64 v24; // rdx
  int v26; // r8d
  const wchar_t *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // r9d
  char *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const wchar_t *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  char *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const wchar_t *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const wchar_t *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  char *v46; // rcx
  __int64 v47; // rax
  const wchar_t *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const wchar_t *v51; // rcx
  struct _EVENT_DATA_DESCRIPTOR v53; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+68h] [rbp-98h]
  const wchar_t *v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+78h] [rbp-88h]
  int v60; // [rsp+7Ch] [rbp-84h]
  __int64 v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  const wchar_t *v63; // [rsp+90h] [rbp-70h]
  int v64; // [rsp+98h] [rbp-68h]
  int v65; // [rsp+9Ch] [rbp-64h]
  __int64 v66; // [rsp+A0h] [rbp-60h]
  __int64 v67; // [rsp+A8h] [rbp-58h]
  char *v68; // [rsp+B0h] [rbp-50h]
  int v69; // [rsp+B8h] [rbp-48h]
  int v70; // [rsp+BCh] [rbp-44h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  const wchar_t *v73; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+D8h] [rbp-28h]
  int v75; // [rsp+DCh] [rbp-24h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  __int64 v77; // [rsp+E8h] [rbp-18h]
  const wchar_t *v78; // [rsp+F0h] [rbp-10h]
  int v79; // [rsp+F8h] [rbp-8h]
  int v80; // [rsp+FCh] [rbp-4h]
  char *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const wchar_t *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  char *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  __int64 v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]
  __int64 v94; // [rsp+150h] [rbp+50h]
  __int64 v95; // [rsp+158h] [rbp+58h]
  const wchar_t *v96; // [rsp+160h] [rbp+60h]
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
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &word_180018022;
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
    while ( *(_WORD *)&v31[2 * v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = byte_180018020;
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
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &word_180018022;
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
    while ( *(_WORD *)&v37[2 * v38] );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = byte_180018020;
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
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &word_180018022;
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
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &word_180018022;
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
    while ( *(_WORD *)&v46[2 * v47] );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = byte_180018020;
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
    while ( *((_BYTE *)v48 + v49) );
    v50 = v49 + 1;
  }
  else
  {
    v48 = &word_180018022;
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
    while ( *((_BYTE *)v51 + v24) );
    v26 = v24 + 1;
  }
  else
  {
    v51 = &word_180018022;
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
0x18000140c  push    rbp
0x18000140e  push    rbx
0x18000140f  push    rsi
0x180001410  push    rdi
0x180001411  push    r15
0x180001413  lea     rbp, [rsp-80h]
0x180001418  sub     rsp, 180h
0x18000141f  mov     rax, cs:__security_cookie
0x180001426  xor     rax, rsp
0x180001429  mov     [rbp+0A0h+var_30], rax
0x18000142d  mov     rax, [rbp+0A0h+arg_A8]
0x180001434  lea     rsi, word_180018022
0x18000143b  mov     r11, rdx
0x18000143e  mov     r10, rcx
0x180001441  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001445  xor     edi, edi
0x180001447  mov     rbx, r8
0x18000144a  mov     r8d, 1
0x180001450  mov     rcx, [rax]
0x180001453  test    rcx, rcx
0x180001456  jz      short loc_180001468
0x180001458  mov     rax, rdx
0x18000145b  inc     rax
0x18000145e  cmp     [rcx+rax], dil
0x180001462  jnz     short loc_18000145B
0x180001464  inc     eax
0x180001466  jmp     short loc_18000146E
0x180001468  mov     rcx, rsi
0x18000146b  mov     eax, r8d
0x18000146e  mov     [rbp+0A0h+var_38], eax
0x180001471  mov     r9d, 2
0x180001477  mov     rax, [rbp+0A0h+arg_A0]
0x18000147e  mov     [rbp+0A0h+var_50], rax
0x180001482  mov     rax, [rbp+0A0h+arg_98]
0x180001489  mov     [rbp+0A0h+var_60], rax
0x18000148d  mov     rax, [rbp+0A0h+arg_90]
0x180001494  mov     [rbp+0A0h+var_40], rcx
0x180001498  mov     [rbp+0A0h+var_34], edi
0x18000149b  mov     [rbp+0A0h+var_48], 4
0x1800014a3  mov     rcx, [rax]
0x1800014a6  mov     [rbp+0A0h+var_58], 4
0x1800014ae  test    rcx, rcx
0x1800014b1  jz      short loc_1800014C8
0x1800014b3  mov     rax, rdx
0x1800014b6  inc     rax
0x1800014b9  cmp     [rcx+rax*2], di
0x1800014bd  jnz     short loc_1800014B6
0x1800014bf  lea     eax, ds:2[rax*2]
0x1800014c6  jmp     short loc_1800014D2
0x1800014c8  lea     rcx, byte_180018020
0x1800014cf  mov     eax, r9d
0x1800014d2  mov     [rbp+0A0h+var_68], eax
0x1800014d5  mov     rax, [rbp+0A0h+arg_88]
0x1800014dc  mov     [rbp+0A0h+var_70], rcx
0x1800014e0  mov     [rbp+0A0h+var_64], edi
0x1800014e3  mov     rcx, [rax]
0x1800014e6  test    rcx, rcx
0x1800014e9  jz      short loc_1800014FB
0x1800014eb  mov     rax, rdx
0x1800014ee  inc     rax
0x1800014f1  cmp     [rcx+rax], dil
0x1800014f5  jnz     short loc_1800014EE
0x1800014f7  inc     eax
0x1800014f9  jmp     short loc_180001501
0x1800014fb  mov     rcx, rsi
0x1800014fe  mov     eax, r8d
0x180001501  mov     [rbp+0A0h+var_78], eax
0x180001504  mov     rax, [rbp+0A0h+arg_80]
0x18000150b  mov     [rbp+0A0h+var_90], rax
0x18000150f  mov     rax, [rbp+0A0h+arg_78]
0x180001516  mov     [rbp+0A0h+var_80], rcx
0x18000151a  mov     [rbp+0A0h+var_74], edi
0x18000151d  mov     [rbp+0A0h+var_88], 4
0x180001525  mov     rcx, [rax]
0x180001528  test    rcx, rcx
0x18000152b  jz      short loc_180001542
0x18000152d  mov     rax, rdx
0x180001530  inc     rax
0x180001533  cmp     [rcx+rax*2], di
0x180001537  jnz     short loc_180001530
0x180001539  lea     eax, ds:2[rax*2]
0x180001540  jmp     short loc_18000154C
0x180001542  lea     rcx, byte_180018020
0x180001549  mov     eax, r9d
0x18000154c  mov     [rbp+0A0h+var_98], eax
0x18000154f  mov     rax, [rbp+0A0h+arg_70]
0x180001556  mov     [rbp+0A0h+var_A0], rcx
0x18000155a  mov     [rbp+0A0h+var_94], edi
0x18000155d  mov     rcx, [rax]
0x180001560  test    rcx, rcx
0x180001563  jz      short loc_180001575
0x180001565  mov     rax, rdx
0x180001568  inc     rax
0x18000156b  cmp     [rcx+rax], dil
0x18000156f  jnz     short loc_180001568
0x180001571  inc     eax
0x180001573  jmp     short loc_18000157B
0x180001575  mov     rcx, rsi
0x180001578  mov     eax, r8d
0x18000157b  mov     [rbp+0A0h+var_A8], eax
0x18000157e  mov     rax, [rbp+0A0h+arg_68]
0x180001585  mov     [rbp+0A0h+var_C0], rax
0x180001589  mov     rax, [rbp+0A0h+arg_60]
0x180001590  mov     [rbp+0A0h+var_B0], rcx
0x180001594  mov     [rbp+0A0h+var_A4], edi
0x180001597  mov     [rbp+0A0h+var_B8], 4
0x18000159f  mov     rcx, [rax]
0x1800015a2  test    rcx, rcx
0x1800015a5  jz      short loc_1800015B7
0x1800015a7  mov     rax, rdx
0x1800015aa  inc     rax
0x1800015ad  cmp     [rcx+rax], dil
0x1800015b1  jnz     short loc_1800015AA
0x1800015b3  inc     eax
0x1800015b5  jmp     short loc_1800015BD
0x1800015b7  mov     rcx, rsi
0x1800015ba  mov     eax, r8d
0x1800015bd  mov     [rbp+0A0h+var_C8], eax
0x1800015c0  mov     rax, [rbp+0A0h+arg_58]
0x1800015c7  mov     [rbp+0A0h+var_E0], rax
0x1800015cb  mov     rax, [rbp+0A0h+arg_50]
0x1800015d2  mov     [rbp+0A0h+var_D0], rcx
0x1800015d6  mov     [rbp+0A0h+var_C4], edi
0x1800015d9  mov     [rbp+0A0h+var_D8], 4
0x1800015e1  mov     rcx, [rax]
0x1800015e4  test    rcx, rcx
0x1800015e7  jz      short loc_1800015FF
0x1800015e9  mov     rax, rdx
0x1800015ec  inc     rax
0x1800015ef  cmp     [rcx+rax*2], di
0x1800015f3  jnz     short loc_1800015EC
0x1800015f5  lea     r9d, ds:2[rax*2]
0x1800015fd  jmp     short loc_180001606
0x1800015ff  lea     rcx, byte_180018020
0x180001606  mov     rax, [rbp+0A0h+arg_48]
0x18000160d  mov     [rbp+0A0h+var_100], rax
0x180001611  mov     rax, [rbp+0A0h+arg_40]
0x180001618  mov     [rbp+0A0h+var_F0], rcx
0x18000161c  mov     [rbp+0A0h+var_E8], r9d
0x180001620  mov     [rbp+0A0h+var_E4], edi
0x180001623  mov     rcx, [rax]
0x180001626  mov     [rbp+0A0h+var_F8], 4
0x18000162e  test    rcx, rcx
0x180001631  jz      short loc_180001643
0x180001633  mov     rax, rdx
0x180001636  inc     rax
0x180001639  cmp     [rcx+rax], dil
0x18000163d  jnz     short loc_180001636
0x18000163f  inc     eax
0x180001641  jmp     short loc_180001649
0x180001643  mov     rcx, rsi
0x180001646  mov     eax, r8d
0x180001649  mov     [rbp+0A0h+var_108], eax
0x18000164c  mov     rax, [rbp+0A0h+arg_38]
0x180001653  mov     [rbp+0A0h+var_120], rax
0x180001657  mov     rax, [rbp+0A0h+arg_30]
0x18000165e  mov     [rbp+0A0h+var_110], rcx
0x180001662  mov     [rbp+0A0h+var_104], edi
0x180001665  mov     [rbp+0A0h+var_118], 4
0x18000166d  mov     rcx, [rax]
0x180001670  test    rcx, rcx
0x180001673  jz      short loc_180001684
0x180001675  inc     rdx
0x180001678  cmp     [rcx+rdx], dil
0x18000167c  jnz     short loc_180001675
0x18000167e  lea     r8d, [rdx+1]
0x180001682  jmp     short loc_180001687
0x180001684  mov     rcx, rsi
0x180001687  mov     rax, [rbp+0A0h+arg_28]
0x18000168e  xor     r9d, r9d; int
0x180001691  mov     [rsp+1A0h+var_140], rax
0x180001696  mov     rdx, r11; int
0x180001699  mov     rax, [rbp+0A0h+arg_20]
0x1800016a0  mov     [rsp+1A0h+var_150], rax
0x1800016a5  lea     rax, [rsp+1A0h+var_170]
0x1800016aa  mov     [rsp+1A0h+var_130], rcx
0x1800016af  mov     rcx, r10; int
0x1800016b2  mov     [rsp+1A0h+var_128], r8d
0x1800016b7  mov     r8, rbx; int
0x1800016ba  mov     [rsp+1A0h+var_178], rax; PEVENT_DATA_DESCRIPTOR
0x1800016bf  mov     [rsp+1A0h+var_180], 14h; ULONG
0x1800016c7  mov     [rsp+1A0h+var_124], edi
0x1800016cb  mov     [rsp+1A0h+var_138], 4
0x1800016d4  mov     [rsp+1A0h+var_148], 8
0x1800016dd  call    _tlgWriteTransfer_EventWriteTransfer
0x1800016e2  mov     rcx, [rbp+0A0h+var_30]
0x1800016e6  xor     rcx, rsp; StackCookie
0x1800016e9  call    __security_check_cookie
0x1800016ee  add     rsp, 180h
0x1800016f5  pop     r15
0x1800016f7  pop     rdi
0x1800016f8  pop     rsi
0x1800016f9  pop     rbx
0x1800016fa  pop     rbp
0x1800016fb  retn
```
