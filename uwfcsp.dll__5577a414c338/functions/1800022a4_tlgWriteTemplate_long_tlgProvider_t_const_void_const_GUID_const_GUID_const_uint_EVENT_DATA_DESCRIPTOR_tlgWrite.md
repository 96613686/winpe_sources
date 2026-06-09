# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800022a4`
- end: `0x1800025fa`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U4@U2@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564646@Z`
- size: `854`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, int **, __int64, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cbfc`

## callees

- `0x180001ecc`
- `0x1800022a4`
- `0x18001a210`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        int **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        int **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        int **a20,
        __int64 a21,
        int **a22,
        __int64 a23,
        int **a24)
{
  __int64 v26; // rdx
  int v28; // r9d
  int *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  int *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  int v38; // r8d
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  int *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  int *v51; // rcx
  __int64 v52; // rax
  const unsigned __int16 *v53; // rcx
  __int64 v54; // rax
  int v55; // eax
  const unsigned __int16 *v56; // rcx
  _BYTE v58[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v59; // [rsp+50h] [rbp-B0h]
  __int64 v60; // [rsp+58h] [rbp-A8h]
  __int64 v61; // [rsp+60h] [rbp-A0h]
  __int64 v62; // [rsp+68h] [rbp-98h]
  __int64 v63; // [rsp+70h] [rbp-90h]
  __int64 v64; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v65; // [rsp+80h] [rbp-80h]
  int v66; // [rsp+88h] [rbp-78h]
  int v67; // [rsp+8Ch] [rbp-74h]
  __int64 v68; // [rsp+90h] [rbp-70h]
  __int64 v69; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v70; // [rsp+A0h] [rbp-60h]
  int v71; // [rsp+A8h] [rbp-58h]
  int v72; // [rsp+ACh] [rbp-54h]
  __int64 v73; // [rsp+B0h] [rbp-50h]
  __int64 v74; // [rsp+B8h] [rbp-48h]
  int *v75; // [rsp+C0h] [rbp-40h]
  int v76; // [rsp+C8h] [rbp-38h]
  int v77; // [rsp+CCh] [rbp-34h]
  __int64 v78; // [rsp+D0h] [rbp-30h]
  __int64 v79; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v80; // [rsp+E0h] [rbp-20h]
  int v81; // [rsp+E8h] [rbp-18h]
  int v82; // [rsp+ECh] [rbp-14h]
  __int64 v83; // [rsp+F0h] [rbp-10h]
  __int64 v84; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v85; // [rsp+100h] [rbp+0h]
  int v86; // [rsp+108h] [rbp+8h]
  int v87; // [rsp+10Ch] [rbp+Ch]
  int *v88; // [rsp+110h] [rbp+10h]
  int v89; // [rsp+118h] [rbp+18h]
  int v90; // [rsp+11Ch] [rbp+1Ch]
  __int64 v91; // [rsp+120h] [rbp+20h]
  __int64 v92; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v93; // [rsp+130h] [rbp+30h]
  int v94; // [rsp+138h] [rbp+38h]
  int v95; // [rsp+13Ch] [rbp+3Ch]
  int *v96; // [rsp+140h] [rbp+40h]
  int v97; // [rsp+148h] [rbp+48h]
  int v98; // [rsp+14Ch] [rbp+4Ch]
  __int64 v99; // [rsp+150h] [rbp+50h]
  __int64 v100; // [rsp+158h] [rbp+58h]
  int *v101; // [rsp+160h] [rbp+60h]
  int v102; // [rsp+168h] [rbp+68h]
  int v103; // [rsp+16Ch] [rbp+6Ch]
  __int64 v104; // [rsp+170h] [rbp+70h]
  __int64 v105; // [rsp+178h] [rbp+78h]
  int *v106; // [rsp+180h] [rbp+80h]
  int v107; // [rsp+188h] [rbp+88h]
  int v108; // [rsp+18Ch] [rbp+8Ch]

  v26 = -1;
  v28 = 2;
  v29 = *a24;
  if ( *a24 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_WORD *)v29 + v30) );
    v31 = 2 * v30 + 2;
  }
  else
  {
    v29 = &dword_18001F7A4;
    v31 = 2;
  }
  v107 = v31;
  v104 = a23;
  v106 = v29;
  v108 = 0;
  v105 = 4;
  v32 = *a22;
  if ( *a22 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)v32 + v33) );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &dword_18001F7A4;
    v34 = 2;
  }
  v102 = v34;
  v99 = a21;
  v101 = v32;
  v103 = 0;
  v100 = 4;
  v35 = *a20;
  if ( *a20 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_WORD *)v35 + v36) );
    v37 = 2 * v36 + 2;
  }
  else
  {
    v35 = &dword_18001F7A4;
    v37 = 2;
  }
  v97 = v37;
  v38 = 1;
  v96 = v35;
  v98 = 0;
  v39 = *a19;
  if ( *a19 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &qword_18001EF80;
    v41 = 1;
  }
  v94 = v41;
  v91 = a18;
  v93 = v39;
  v95 = 0;
  v92 = 4;
  v42 = *a17;
  if ( *a17 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)v42 + v43) );
    v44 = 2 * v43 + 2;
  }
  else
  {
    v42 = &dword_18001F7A4;
    v44 = 2;
  }
  v89 = v44;
  v88 = v42;
  v90 = 0;
  v45 = *a16;
  if ( *a16 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *((_BYTE *)v45 + v46) );
    v47 = v46 + 1;
  }
  else
  {
    v45 = &qword_18001EF80;
    v47 = 1;
  }
  v86 = v47;
  v83 = a15;
  v85 = v45;
  v87 = 0;
  v84 = 4;
  v48 = *a14;
  if ( *a14 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_BYTE *)v48 + v49) );
    v50 = v49 + 1;
  }
  else
  {
    v48 = &qword_18001EF80;
    v50 = 1;
  }
  v81 = v50;
  v78 = a13;
  v80 = v48;
  v82 = 0;
  v79 = 4;
  v51 = *a12;
  if ( *a12 )
  {
    v52 = -1;
    do
      ++v52;
    while ( *((_WORD *)v51 + v52) );
    v28 = 2 * v52 + 2;
  }
  else
  {
    v51 = &dword_18001F7A4;
  }
  v73 = a11;
  v75 = v51;
  v76 = v28;
  v77 = 0;
  v53 = *a10;
  v74 = 4;
  if ( v53 )
  {
    v54 = -1;
    do
      ++v54;
    while ( *((_BYTE *)v53 + v54) );
    v55 = v54 + 1;
  }
  else
  {
    v53 = &qword_18001EF80;
    v55 = 1;
  }
  v71 = v55;
  v68 = a9;
  v70 = v53;
  v72 = 0;
  v69 = 4;
  v56 = *a8;
  if ( *a8 )
  {
    do
      ++v26;
    while ( *((_BYTE *)v56 + v26) );
    v38 = v26 + 1;
  }
  else
  {
    v56 = &qword_18001EF80;
  }
  v63 = a7;
  v61 = a6;
  v59 = a5;
  v65 = v56;
  v66 = v38;
  v67 = 0;
  v64 = 4;
  v62 = 8;
  v60 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 22, v58);
}

```

## disassembly

```asm
0x1800022a4  mov     [rsp-8+arg_18], rbx
0x1800022a9  push    rbp
0x1800022aa  push    rsi
0x1800022ab  push    rdi
0x1800022ac  push    r14
0x1800022ae  push    r15
0x1800022b0  lea     rbp, [rsp-0A0h]
0x1800022b8  sub     rsp, 1A0h
0x1800022bf  mov     rax, cs:__security_cookie
0x1800022c6  xor     rax, rsp
0x1800022c9  mov     [rbp+0C0h+var_30], rax
0x1800022d0  mov     rax, [rbp+0C0h+arg_B8]
0x1800022d7  lea     r14, dword_18001F7A4
0x1800022de  mov     r11, rdx
0x1800022e1  mov     r10, rcx
0x1800022e4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800022e8  xor     edi, edi
0x1800022ea  mov     rbx, r8
0x1800022ed  mov     r9d, 2
0x1800022f3  mov     rcx, [rax]
0x1800022f6  test    rcx, rcx
0x1800022f9  jz      short loc_180002310
0x1800022fb  mov     rax, rdx
0x1800022fe  inc     rax
0x180002301  cmp     [rcx+rax*2], di
0x180002305  jnz     short loc_1800022FE
0x180002307  lea     eax, ds:2[rax*2]
0x18000230e  jmp     short loc_180002316
0x180002310  mov     rcx, r14
0x180002313  mov     eax, r9d
0x180002316  mov     [rbp+0C0h+var_38], eax
0x18000231c  mov     rax, [rbp+0C0h+arg_B0]
0x180002323  mov     [rbp+0C0h+var_50], rax
0x180002327  mov     rax, [rbp+0C0h+arg_A8]
0x18000232e  mov     [rbp+0C0h+var_40], rcx
0x180002335  mov     [rbp+0C0h+var_34], edi
0x18000233b  mov     [rbp+0C0h+var_48], 4
0x180002343  mov     rcx, [rax]
0x180002346  test    rcx, rcx
0x180002349  jz      short loc_180002360
0x18000234b  mov     rax, rdx
0x18000234e  inc     rax
0x180002351  cmp     [rcx+rax*2], di
0x180002355  jnz     short loc_18000234E
0x180002357  lea     eax, ds:2[rax*2]
0x18000235e  jmp     short loc_180002366
0x180002360  mov     rcx, r14
0x180002363  mov     eax, r9d
0x180002366  mov     [rbp+0C0h+var_58], eax
0x180002369  mov     rax, [rbp+0C0h+arg_A0]
0x180002370  mov     [rbp+0C0h+var_70], rax
0x180002374  mov     rax, [rbp+0C0h+arg_98]
0x18000237b  mov     [rbp+0C0h+var_60], rcx
0x18000237f  mov     [rbp+0C0h+var_54], edi
0x180002382  mov     [rbp+0C0h+var_68], 4
0x18000238a  mov     rcx, [rax]
0x18000238d  test    rcx, rcx
0x180002390  jz      short loc_1800023A7
0x180002392  mov     rax, rdx
0x180002395  inc     rax
0x180002398  cmp     [rcx+rax*2], di
0x18000239c  jnz     short loc_180002395
0x18000239e  lea     eax, ds:2[rax*2]
0x1800023a5  jmp     short loc_1800023AD
0x1800023a7  mov     rcx, r14
0x1800023aa  mov     eax, r9d
0x1800023ad  mov     [rbp+0C0h+var_78], eax
0x1800023b0  lea     rsi, qword_18001EF80
0x1800023b7  mov     rax, [rbp+0C0h+arg_90]
0x1800023be  mov     r8d, 1
0x1800023c4  mov     [rbp+0C0h+var_80], rcx
0x1800023c8  mov     [rbp+0C0h+var_74], edi
0x1800023cb  mov     rcx, [rax]
0x1800023ce  test    rcx, rcx
0x1800023d1  jz      short loc_1800023E3
0x1800023d3  mov     rax, rdx
0x1800023d6  inc     rax
0x1800023d9  cmp     [rcx+rax], dil
0x1800023dd  jnz     short loc_1800023D6
0x1800023df  inc     eax
0x1800023e1  jmp     short loc_1800023E9
0x1800023e3  mov     rcx, rsi
0x1800023e6  mov     eax, r8d
0x1800023e9  mov     [rbp+0C0h+var_88], eax
0x1800023ec  mov     rax, [rbp+0C0h+arg_88]
0x1800023f3  mov     [rbp+0C0h+var_A0], rax
0x1800023f7  mov     rax, [rbp+0C0h+arg_80]
0x1800023fe  mov     [rbp+0C0h+var_90], rcx
0x180002402  mov     [rbp+0C0h+var_84], edi
0x180002405  mov     [rbp+0C0h+var_98], 4
0x18000240d  mov     rcx, [rax]
0x180002410  test    rcx, rcx
0x180002413  jz      short loc_18000242A
0x180002415  mov     rax, rdx
0x180002418  inc     rax
0x18000241b  cmp     [rcx+rax*2], di
0x18000241f  jnz     short loc_180002418
0x180002421  lea     eax, ds:2[rax*2]
0x180002428  jmp     short loc_180002430
0x18000242a  mov     rcx, r14
0x18000242d  mov     eax, r9d
0x180002430  mov     [rbp+0C0h+var_A8], eax
0x180002433  mov     rax, [rbp+0C0h+arg_78]
0x18000243a  mov     [rbp+0C0h+var_B0], rcx
0x18000243e  mov     [rbp+0C0h+var_A4], edi
0x180002441  mov     rcx, [rax]
0x180002444  test    rcx, rcx
0x180002447  jz      short loc_180002459
0x180002449  mov     rax, rdx
0x18000244c  inc     rax
0x18000244f  cmp     [rcx+rax], dil
0x180002453  jnz     short loc_18000244C
0x180002455  inc     eax
0x180002457  jmp     short loc_18000245F
0x180002459  mov     rcx, rsi
0x18000245c  mov     eax, r8d
0x18000245f  mov     [rbp+0C0h+var_B8], eax
0x180002462  mov     rax, [rbp+0C0h+arg_70]
0x180002469  mov     [rbp+0C0h+var_D0], rax
0x18000246d  mov     rax, [rbp+0C0h+arg_68]
0x180002474  mov     [rbp+0C0h+var_C0], rcx
0x180002478  mov     [rbp+0C0h+var_B4], edi
0x18000247b  mov     [rbp+0C0h+var_C8], 4
0x180002483  mov     rcx, [rax]
0x180002486  test    rcx, rcx
0x180002489  jz      short loc_18000249B
0x18000248b  mov     rax, rdx
0x18000248e  inc     rax
0x180002491  cmp     [rcx+rax], dil
0x180002495  jnz     short loc_18000248E
0x180002497  inc     eax
0x180002499  jmp     short loc_1800024A1
0x18000249b  mov     rcx, rsi
0x18000249e  mov     eax, r8d
0x1800024a1  mov     [rbp+0C0h+var_D8], eax
0x1800024a4  mov     rax, [rbp+0C0h+arg_60]
0x1800024ab  mov     [rbp+0C0h+var_F0], rax
0x1800024af  mov     rax, [rbp+0C0h+arg_58]
0x1800024b6  mov     [rbp+0C0h+var_E0], rcx
0x1800024ba  mov     [rbp+0C0h+var_D4], edi
0x1800024bd  mov     [rbp+0C0h+var_E8], 4
0x1800024c5  mov     rcx, [rax]
0x1800024c8  test    rcx, rcx
0x1800024cb  jz      short loc_1800024E3
0x1800024cd  mov     rax, rdx
0x1800024d0  inc     rax
0x1800024d3  cmp     [rcx+rax*2], di
0x1800024d7  jnz     short loc_1800024D0
0x1800024d9  lea     r9d, ds:2[rax*2]
0x1800024e1  jmp     short loc_1800024E6
0x1800024e3  mov     rcx, r14
0x1800024e6  mov     rax, [rbp+0C0h+arg_50]
0x1800024ed  mov     [rbp+0C0h+var_110], rax
0x1800024f1  mov     rax, [rbp+0C0h+arg_48]
0x1800024f8  mov     [rbp+0C0h+var_100], rcx
0x1800024fc  mov     [rbp+0C0h+var_F8], r9d
0x180002500  mov     [rbp+0C0h+var_F4], edi
0x180002503  mov     rcx, [rax]
0x180002506  mov     [rbp+0C0h+var_108], 4
0x18000250e  test    rcx, rcx
0x180002511  jz      short loc_180002523
0x180002513  mov     rax, rdx
0x180002516  inc     rax
0x180002519  cmp     [rcx+rax], dil
0x18000251d  jnz     short loc_180002516
0x18000251f  inc     eax
0x180002521  jmp     short loc_180002529
0x180002523  mov     rcx, rsi
0x180002526  mov     eax, r8d
0x180002529  mov     [rbp+0C0h+var_118], eax
0x18000252c  mov     rax, [rbp+0C0h+arg_40]
0x180002533  mov     [rbp+0C0h+var_130], rax
0x180002537  mov     rax, [rbp+0C0h+arg_38]
0x18000253e  mov     [rbp+0C0h+var_120], rcx
0x180002542  mov     [rbp+0C0h+var_114], edi
0x180002545  mov     [rbp+0C0h+var_128], 4
0x18000254d  mov     rcx, [rax]
0x180002550  test    rcx, rcx
0x180002553  jz      short loc_180002564
0x180002555  inc     rdx
0x180002558  cmp     [rcx+rdx], dil
0x18000255c  jnz     short loc_180002555
0x18000255e  lea     r8d, [rdx+1]
0x180002562  jmp     short loc_180002567
0x180002564  mov     rcx, rsi
0x180002567  mov     rax, [rbp+0C0h+arg_30]
0x18000256e  xor     r9d, r9d
0x180002571  mov     [rsp+1C0h+var_150], rax
0x180002576  mov     rdx, r11
0x180002579  mov     rax, [rbp+0C0h+arg_28]
0x180002580  mov     [rsp+1C0h+var_160], rax
0x180002585  mov     rax, [rbp+0C0h+arg_20]
0x18000258c  mov     [rsp+1C0h+var_170], rax
0x180002591  lea     rax, [rsp+1C0h+var_190]
0x180002596  mov     [rbp+0C0h+var_140], rcx
0x18000259a  mov     rcx, r10
0x18000259d  mov     [rbp+0C0h+var_138], r8d
0x1800025a1  mov     r8, rbx
0x1800025a4  mov     [rsp+1C0h+var_198], rax
0x1800025a9  mov     [rsp+1C0h+var_1A0], 16h
0x1800025b1  mov     [rbp+0C0h+var_134], edi
0x1800025b4  mov     [rsp+1C0h+var_148], 4
0x1800025bd  mov     [rsp+1C0h+var_158], 8
0x1800025c6  mov     [rsp+1C0h+var_168], 8
0x1800025cf  call    _tlgWriteTransfer_EventWriteTransfer
0x1800025d4  mov     rcx, [rbp+0C0h+var_30]
0x1800025db  xor     rcx, rsp; StackCookie
0x1800025de  call    __security_check_cookie
0x1800025e3  mov     rbx, [rsp+1C0h+arg_18]
0x1800025eb  add     rsp, 1A0h
0x1800025f2  pop     r15
0x1800025f4  pop     r14
0x1800025f6  pop     rdi
0x1800025f7  pop     rsi
0x1800025f8  pop     rbp
0x1800025f9  retn
```
