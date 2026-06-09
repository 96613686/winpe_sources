# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400016cc`
- end: `0x14000199e`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U1@U?$_tlgWrapSz@D@@U2@U3@U3@U3@U2@U3@U3@U3@U3@U1@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@3AEBU?$_tlgWrapSz@D@@455545555353@Z`
- size: `722`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, const wchar_t **, const wchar_t **, __int64, const wchar_t **, const wchar_t **, const wchar_t **, const wchar_t **, __int64, const wchar_t **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017360`

## callees

- `0x14000162c`
- `0x1400016cc`
- `0x140003200`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        const wchar_t **a10,
        __int64 a11,
        const wchar_t **a12,
        const wchar_t **a13,
        const wchar_t **a14,
        __int64 a15,
        const wchar_t **a16,
        const wchar_t **a17,
        const wchar_t **a18,
        const wchar_t **a19,
        __int64 a20,
        const wchar_t **a21,
        __int64 a22)
{
  __int64 v23; // rcx
  int v25; // edx
  const wchar_t *v26; // r8
  __int64 v27; // rax
  int v28; // eax
  const wchar_t *v29; // r8
  __int64 v30; // rax
  int v31; // eax
  const wchar_t *v32; // r8
  __int64 v33; // rax
  int v34; // eax
  const wchar_t *v35; // r8
  __int64 v36; // rax
  int v37; // eax
  const wchar_t *v38; // r8
  __int64 v39; // rax
  int v40; // eax
  const wchar_t *v41; // r8
  __int64 v42; // rax
  int v43; // eax
  const wchar_t *v44; // r8
  __int64 v45; // rax
  int v46; // eax
  const wchar_t *v47; // r8
  __int64 v48; // rax
  int v49; // eax
  const wchar_t *v50; // r8
  _BYTE v52[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  __int64 v57; // [rsp+70h] [rbp-90h]
  __int64 v58; // [rsp+78h] [rbp-88h]
  __int64 v59; // [rsp+80h] [rbp-80h]
  __int64 v60; // [rsp+88h] [rbp-78h]
  __int64 v61; // [rsp+90h] [rbp-70h]
  __int64 v62; // [rsp+98h] [rbp-68h]
  const wchar_t *v63; // [rsp+A0h] [rbp-60h]
  int v64; // [rsp+A8h] [rbp-58h]
  int v65; // [rsp+ACh] [rbp-54h]
  __int64 v66; // [rsp+B0h] [rbp-50h]
  __int64 v67; // [rsp+B8h] [rbp-48h]
  const wchar_t *v68; // [rsp+C0h] [rbp-40h]
  int v69; // [rsp+C8h] [rbp-38h]
  int v70; // [rsp+CCh] [rbp-34h]
  const wchar_t *v71; // [rsp+D0h] [rbp-30h]
  int v72; // [rsp+D8h] [rbp-28h]
  int v73; // [rsp+DCh] [rbp-24h]
  const wchar_t *v74; // [rsp+E0h] [rbp-20h]
  int v75; // [rsp+E8h] [rbp-18h]
  int v76; // [rsp+ECh] [rbp-14h]
  __int64 v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  const wchar_t *v79; // [rsp+100h] [rbp+0h]
  int v80; // [rsp+108h] [rbp+8h]
  int v81; // [rsp+10Ch] [rbp+Ch]
  const wchar_t *v82; // [rsp+110h] [rbp+10h]
  int v83; // [rsp+118h] [rbp+18h]
  int v84; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  const wchar_t *v93; // [rsp+150h] [rbp+50h]
  int v94; // [rsp+158h] [rbp+58h]
  int v95; // [rsp+15Ch] [rbp+5Ch]
  __int64 v96; // [rsp+160h] [rbp+60h]
  __int64 v97; // [rsp+168h] [rbp+68h]

  v96 = a22;
  v23 = -1;
  v97 = 4;
  v25 = 1;
  v26 = *a21;
  if ( *a21 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &qword_140024070;
    v28 = 1;
  }
  v94 = v28;
  v91 = a20;
  v93 = v26;
  v95 = 0;
  v92 = 4;
  v29 = *a19;
  if ( *a19 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &qword_140024070;
    v31 = 1;
  }
  v89 = v31;
  v88 = v29;
  v90 = 0;
  v32 = *a18;
  if ( *a18 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_BYTE *)v32 + v33) );
    v34 = v33 + 1;
  }
  else
  {
    v32 = &qword_140024070;
    v34 = 1;
  }
  v86 = v34;
  v85 = v32;
  v87 = 0;
  v35 = *a17;
  if ( *a17 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &qword_140024070;
    v37 = 1;
  }
  v83 = v37;
  v82 = v35;
  v84 = 0;
  v38 = *a16;
  if ( *a16 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &qword_140024070;
    v40 = 1;
  }
  v80 = v40;
  v77 = a15;
  v79 = v38;
  v81 = 0;
  v78 = 2;
  v41 = *a14;
  if ( *a14 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &qword_140024070;
    v43 = 1;
  }
  v75 = v43;
  v74 = v41;
  v76 = 0;
  v44 = *a13;
  if ( *a13 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &qword_140024070;
    v46 = 1;
  }
  v72 = v46;
  v71 = v44;
  v73 = 0;
  v47 = *a12;
  if ( *a12 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_BYTE *)v47 + v48) );
    v49 = v48 + 1;
  }
  else
  {
    v47 = &qword_140024070;
    v49 = 1;
  }
  v69 = v49;
  v66 = a11;
  v68 = v47;
  v70 = 0;
  v67 = 2;
  v50 = *a10;
  if ( *a10 )
  {
    do
      ++v23;
    while ( *((_BYTE *)v50 + v23) );
    v25 = v23 + 1;
  }
  else
  {
    v50 = &qword_140024070;
  }
  v61 = a9;
  v59 = a8;
  v57 = a7;
  v55 = a6;
  v53 = a5;
  v63 = v50;
  v64 = v25;
  v65 = 0;
  v62 = 4;
  v60 = 2;
  v58 = 4;
  v56 = 4;
  v54 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 20, v52);
}

```

## disassembly

```asm
0x1400016cc  mov     [rsp-8+arg_10], rbx
0x1400016d1  mov     [rsp-8+arg_18], rsi
0x1400016d6  push    rbp
0x1400016d7  lea     rbp, [rsp-80h]
0x1400016dc  sub     rsp, 180h
0x1400016e3  mov     rax, cs:__security_cookie
0x1400016ea  xor     rax, rsp
0x1400016ed  mov     [rbp+80h+var_10], rax
0x1400016f1  mov     rax, [rbp+80h+arg_A8]
0x1400016f8  lea     rbx, qword_140024070
0x1400016ff  xor     r9d, r9d
0x140001702  mov     [rbp+80h+var_20], rax
0x140001706  mov     rax, [rbp+80h+arg_A0]
0x14000170d  mov     r10, rcx
0x140001710  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001714  mov     [rbp+80h+var_18], 4
0x14000171c  mov     r11, rdx
0x14000171f  lea     edx, [r9+1]
0x140001723  mov     r8, [rax]
0x140001726  test    r8, r8
0x140001729  jz      short loc_14000173B
0x14000172b  mov     rax, rcx
0x14000172e  inc     rax
0x140001731  cmp     [r8+rax], r9b
0x140001735  jnz     short loc_14000172E
0x140001737  inc     eax
0x140001739  jmp     short loc_140001740
0x14000173b  mov     r8, rbx
0x14000173e  mov     eax, edx
0x140001740  mov     [rbp+80h+var_28], eax
0x140001743  mov     rax, [rbp+80h+arg_98]
0x14000174a  mov     [rbp+80h+var_40], rax
0x14000174e  mov     rax, [rbp+80h+arg_90]
0x140001755  mov     [rbp+80h+var_30], r8
0x140001759  mov     [rbp+80h+var_24], r9d
0x14000175d  mov     [rbp+80h+var_38], 4
0x140001765  mov     r8, [rax]
0x140001768  test    r8, r8
0x14000176b  jz      short loc_14000177D
0x14000176d  mov     rax, rcx
0x140001770  inc     rax
0x140001773  cmp     [r8+rax], r9b
0x140001777  jnz     short loc_140001770
0x140001779  inc     eax
0x14000177b  jmp     short loc_140001782
0x14000177d  mov     r8, rbx
0x140001780  mov     eax, edx
0x140001782  mov     [rbp+80h+var_48], eax
0x140001785  mov     rax, [rbp+80h+arg_88]
0x14000178c  mov     [rbp+80h+var_50], r8
0x140001790  mov     [rbp+80h+var_44], r9d
0x140001794  mov     r8, [rax]
0x140001797  test    r8, r8
0x14000179a  jz      short loc_1400017AC
0x14000179c  mov     rax, rcx
0x14000179f  inc     rax
0x1400017a2  cmp     [r8+rax], r9b
0x1400017a6  jnz     short loc_14000179F
0x1400017a8  inc     eax
0x1400017aa  jmp     short loc_1400017B1
0x1400017ac  mov     r8, rbx
0x1400017af  mov     eax, edx
0x1400017b1  mov     [rbp+80h+var_58], eax
0x1400017b4  mov     rax, [rbp+80h+arg_80]
0x1400017bb  mov     [rbp+80h+var_60], r8
0x1400017bf  mov     [rbp+80h+var_54], r9d
0x1400017c3  mov     r8, [rax]
0x1400017c6  test    r8, r8
0x1400017c9  jz      short loc_1400017DB
0x1400017cb  mov     rax, rcx
0x1400017ce  inc     rax
0x1400017d1  cmp     [r8+rax], r9b
0x1400017d5  jnz     short loc_1400017CE
0x1400017d7  inc     eax
0x1400017d9  jmp     short loc_1400017E0
0x1400017db  mov     r8, rbx
0x1400017de  mov     eax, edx
0x1400017e0  mov     [rbp+80h+var_68], eax
0x1400017e3  mov     rax, [rbp+80h+arg_78]
0x1400017ea  mov     [rbp+80h+var_70], r8
0x1400017ee  mov     [rbp+80h+var_64], r9d
0x1400017f2  mov     r8, [rax]
0x1400017f5  test    r8, r8
0x1400017f8  jz      short loc_14000180A
0x1400017fa  mov     rax, rcx
0x1400017fd  inc     rax
0x140001800  cmp     [r8+rax], r9b
0x140001804  jnz     short loc_1400017FD
0x140001806  inc     eax
0x140001808  jmp     short loc_14000180F
0x14000180a  mov     r8, rbx
0x14000180d  mov     eax, edx
0x14000180f  mov     [rbp+80h+var_78], eax
0x140001812  mov     rax, [rbp+80h+arg_70]
0x140001819  mov     [rbp+80h+var_90], rax
0x14000181d  mov     rax, [rbp+80h+arg_68]
0x140001824  mov     [rbp+80h+var_80], r8
0x140001828  mov     [rbp+80h+var_74], r9d
0x14000182c  mov     [rbp+80h+var_88], 2
0x140001834  mov     r8, [rax]
0x140001837  test    r8, r8
0x14000183a  jz      short loc_14000184C
0x14000183c  mov     rax, rcx
0x14000183f  inc     rax
0x140001842  cmp     [r8+rax], r9b
0x140001846  jnz     short loc_14000183F
0x140001848  inc     eax
0x14000184a  jmp     short loc_140001851
0x14000184c  mov     r8, rbx
0x14000184f  mov     eax, edx
0x140001851  mov     [rbp+80h+var_98], eax
0x140001854  mov     rax, [rbp+80h+arg_60]
0x14000185b  mov     [rbp+80h+var_A0], r8
0x14000185f  mov     [rbp+80h+var_94], r9d
0x140001863  mov     r8, [rax]
0x140001866  test    r8, r8
0x140001869  jz      short loc_14000187B
0x14000186b  mov     rax, rcx
0x14000186e  inc     rax
0x140001871  cmp     [r8+rax], r9b
0x140001875  jnz     short loc_14000186E
0x140001877  inc     eax
0x140001879  jmp     short loc_140001880
0x14000187b  mov     r8, rbx
0x14000187e  mov     eax, edx
0x140001880  mov     [rbp+80h+var_A8], eax
0x140001883  mov     rax, [rbp+80h+arg_58]
0x14000188a  mov     [rbp+80h+var_B0], r8
0x14000188e  mov     [rbp+80h+var_A4], r9d
0x140001892  mov     r8, [rax]
0x140001895  test    r8, r8
0x140001898  jz      short loc_1400018AA
0x14000189a  mov     rax, rcx
0x14000189d  inc     rax
0x1400018a0  cmp     [r8+rax], r9b
0x1400018a4  jnz     short loc_14000189D
0x1400018a6  inc     eax
0x1400018a8  jmp     short loc_1400018AF
0x1400018aa  mov     r8, rbx
0x1400018ad  mov     eax, edx
0x1400018af  mov     [rbp+80h+var_B8], eax
0x1400018b2  mov     rax, [rbp+80h+arg_50]
0x1400018b9  mov     [rbp+80h+var_D0], rax
0x1400018bd  mov     rax, [rbp+80h+arg_48]
0x1400018c4  mov     [rbp+80h+var_C0], r8
0x1400018c8  mov     [rbp+80h+var_B4], r9d
0x1400018cc  mov     [rbp+80h+var_C8], 2
0x1400018d4  mov     r8, [rax]
0x1400018d7  test    r8, r8
0x1400018da  jz      short loc_1400018EA
0x1400018dc  inc     rcx
0x1400018df  cmp     [r8+rcx], r9b
0x1400018e3  jnz     short loc_1400018DC
0x1400018e5  lea     edx, [rcx+1]
0x1400018e8  jmp     short loc_1400018ED
0x1400018ea  mov     r8, rbx
0x1400018ed  mov     rax, [rbp+80h+arg_40]
0x1400018f4  mov     rcx, r10
0x1400018f7  mov     [rbp+80h+var_F0], rax
0x1400018fb  mov     rax, [rbp+80h+arg_38]
0x140001902  mov     [rbp+80h+var_100], rax
0x140001906  mov     rax, [rbp+80h+arg_30]
0x14000190d  mov     [rsp+180h+var_110], rax
0x140001912  mov     rax, [rbp+80h+arg_28]
0x140001919  mov     [rsp+180h+var_120], rax
0x14000191e  mov     rax, [rbp+80h+arg_20]
0x140001925  mov     [rsp+180h+var_130], rax
0x14000192a  lea     rax, [rsp+180h+var_150]
0x14000192f  mov     [rbp+80h+var_E0], r8
0x140001933  xor     r8d, r8d
0x140001936  mov     [rbp+80h+var_D8], edx
0x140001939  mov     rdx, r11
0x14000193c  mov     [rsp+180h+var_158], rax
0x140001941  mov     [rsp+180h+var_160], 14h
0x140001949  mov     [rbp+80h+var_D4], r9d
0x14000194d  mov     [rbp+80h+var_E8], 4
0x140001955  mov     [rbp+80h+var_F8], 2
0x14000195d  mov     [rsp+180h+var_108], 4
0x140001966  mov     [rsp+180h+var_118], 4
0x14000196f  mov     [rsp+180h+var_128], 4
0x140001978  call    _tlgWriteTransfer_EventWriteTransfer
0x14000197d  mov     rcx, [rbp+80h+var_10]
0x140001981  xor     rcx, rsp; StackCookie
0x140001984  call    __security_check_cookie
0x140001989  lea     r11, [rsp+180h+var_s0]
0x140001991  mov     rbx, [r11+20h]
0x140001995  mov     rsi, [r11+28h]
0x140001999  mov     rsp, r11
0x14000199c  pop     rbp
0x14000199d  retn
```
