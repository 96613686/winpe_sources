# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001704`
- end: `0x180001a76`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564566645@Z`
- size: `882`
- prototype: `__int64 __fastcall(int, int, int, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, char **, __int64, const wchar_t **, __int64, const wchar_t **, char **, __int64, const wchar_t **, char **, char **, char **, __int64, const wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c3d0`

## callees

- `0x180001350`
- `0x180001704`
- `0x180010310`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        int a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const wchar_t **a8,
        __int64 a9,
        const wchar_t **a10,
        __int64 a11,
        char **a12,
        __int64 a13,
        const wchar_t **a14,
        __int64 a15,
        const wchar_t **a16,
        char **a17,
        __int64 a18,
        const wchar_t **a19,
        char **a20,
        char **a21,
        char **a22,
        __int64 a23,
        const wchar_t **a24)
{
  __int64 v26; // rdx
  int v28; // r9d
  const wchar_t *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int v32; // r8d
  char *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  char *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  char *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const wchar_t *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  char *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  const wchar_t *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const wchar_t *v51; // rcx
  __int64 v52; // rax
  int v53; // eax
  char *v54; // rcx
  __int64 v55; // rax
  const wchar_t *v56; // rcx
  __int64 v57; // rax
  int v58; // eax
  const wchar_t *v59; // rcx
  struct _EVENT_DATA_DESCRIPTOR v61; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v62; // [rsp+50h] [rbp-B0h]
  __int64 v63; // [rsp+58h] [rbp-A8h]
  __int64 v64; // [rsp+60h] [rbp-A0h]
  __int64 v65; // [rsp+68h] [rbp-98h]
  __int64 v66; // [rsp+70h] [rbp-90h]
  __int64 v67; // [rsp+78h] [rbp-88h]
  const wchar_t *v68; // [rsp+80h] [rbp-80h]
  int v69; // [rsp+88h] [rbp-78h]
  int v70; // [rsp+8Ch] [rbp-74h]
  __int64 v71; // [rsp+90h] [rbp-70h]
  __int64 v72; // [rsp+98h] [rbp-68h]
  const wchar_t *v73; // [rsp+A0h] [rbp-60h]
  int v74; // [rsp+A8h] [rbp-58h]
  int v75; // [rsp+ACh] [rbp-54h]
  __int64 v76; // [rsp+B0h] [rbp-50h]
  __int64 v77; // [rsp+B8h] [rbp-48h]
  char *v78; // [rsp+C0h] [rbp-40h]
  int v79; // [rsp+C8h] [rbp-38h]
  int v80; // [rsp+CCh] [rbp-34h]
  __int64 v81; // [rsp+D0h] [rbp-30h]
  __int64 v82; // [rsp+D8h] [rbp-28h]
  const wchar_t *v83; // [rsp+E0h] [rbp-20h]
  int v84; // [rsp+E8h] [rbp-18h]
  int v85; // [rsp+ECh] [rbp-14h]
  __int64 v86; // [rsp+F0h] [rbp-10h]
  __int64 v87; // [rsp+F8h] [rbp-8h]
  const wchar_t *v88; // [rsp+100h] [rbp+0h]
  int v89; // [rsp+108h] [rbp+8h]
  int v90; // [rsp+10Ch] [rbp+Ch]
  char *v91; // [rsp+110h] [rbp+10h]
  int v92; // [rsp+118h] [rbp+18h]
  int v93; // [rsp+11Ch] [rbp+1Ch]
  __int64 v94; // [rsp+120h] [rbp+20h]
  __int64 v95; // [rsp+128h] [rbp+28h]
  const wchar_t *v96; // [rsp+130h] [rbp+30h]
  int v97; // [rsp+138h] [rbp+38h]
  int v98; // [rsp+13Ch] [rbp+3Ch]
  char *v99; // [rsp+140h] [rbp+40h]
  int v100; // [rsp+148h] [rbp+48h]
  int v101; // [rsp+14Ch] [rbp+4Ch]
  char *v102; // [rsp+150h] [rbp+50h]
  int v103; // [rsp+158h] [rbp+58h]
  int v104; // [rsp+15Ch] [rbp+5Ch]
  char *v105; // [rsp+160h] [rbp+60h]
  int v106; // [rsp+168h] [rbp+68h]
  int v107; // [rsp+16Ch] [rbp+6Ch]
  __int64 v108; // [rsp+170h] [rbp+70h]
  __int64 v109; // [rsp+178h] [rbp+78h]
  const wchar_t *v110; // [rsp+180h] [rbp+80h]
  int v111; // [rsp+188h] [rbp+88h]
  int v112; // [rsp+18Ch] [rbp+8Ch]

  v26 = -1;
  v28 = 1;
  v29 = *a24;
  if ( *a24 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &word_180018022;
    v31 = 1;
  }
  v111 = v31;
  v32 = 2;
  v108 = a23;
  v110 = v29;
  v112 = 0;
  v109 = 4;
  v33 = *a22;
  if ( *a22 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *(_WORD *)&v33[2 * v34] );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v33 = byte_180018020;
    v35 = 2;
  }
  v106 = v35;
  v105 = v33;
  v107 = 0;
  v36 = *a21;
  if ( *a21 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *(_WORD *)&v36[2 * v37] );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = byte_180018020;
    v38 = 2;
  }
  v103 = v38;
  v102 = v36;
  v104 = 0;
  v39 = *a20;
  if ( *a20 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *(_WORD *)&v39[2 * v40] );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v39 = byte_180018020;
    v41 = 2;
  }
  v100 = v41;
  v99 = v39;
  v101 = 0;
  v42 = *a19;
  if ( *a19 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &word_180018022;
    v44 = 1;
  }
  v97 = v44;
  v94 = a18;
  v96 = v42;
  v98 = 0;
  v95 = 4;
  v45 = *a17;
  if ( *a17 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *(_WORD *)&v45[2 * v46] );
    v47 = 2 * v46 + 2;
  }
  else
  {
    v45 = byte_180018020;
    v47 = 2;
  }
  v92 = v47;
  v91 = v45;
  v93 = 0;
  v48 = *a16;
  if ( *a16 )
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
  v89 = v50;
  v86 = a15;
  v88 = v48;
  v90 = 0;
  v87 = 4;
  v51 = *a14;
  if ( *a14 )
  {
    v52 = -1;
    do
      ++v52;
    while ( *((_BYTE *)v51 + v52) );
    v53 = v52 + 1;
  }
  else
  {
    v51 = &word_180018022;
    v53 = 1;
  }
  v84 = v53;
  v81 = a13;
  v83 = v51;
  v85 = 0;
  v82 = 4;
  v54 = *a12;
  if ( *a12 )
  {
    v55 = -1;
    do
      ++v55;
    while ( *(_WORD *)&v54[2 * v55] );
    v32 = 2 * v55 + 2;
  }
  else
  {
    v54 = byte_180018020;
  }
  v76 = a11;
  v78 = v54;
  v79 = v32;
  v80 = 0;
  v56 = *a10;
  v77 = 4;
  if ( v56 )
  {
    v57 = -1;
    do
      ++v57;
    while ( *((_BYTE *)v56 + v57) );
    v58 = v57 + 1;
  }
  else
  {
    v56 = &word_180018022;
    v58 = 1;
  }
  v74 = v58;
  v71 = a9;
  v73 = v56;
  v75 = 0;
  v72 = 4;
  v59 = *a8;
  if ( *a8 )
  {
    do
      ++v26;
    while ( *((_BYTE *)v59 + v26) );
    v28 = v26 + 1;
  }
  else
  {
    v59 = &word_180018022;
  }
  v66 = a7;
  v64 = a6;
  v62 = a5;
  v68 = v59;
  v69 = v28;
  v70 = 0;
  v67 = 4;
  v65 = 8;
  v63 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x16u, &v61);
}

```

## disassembly

```asm
0x180001704  mov     [rsp-8+arg_18], rbx
0x180001709  push    rbp
0x18000170a  push    rsi
0x18000170b  push    rdi
0x18000170c  push    r14
0x18000170e  push    r15
0x180001710  lea     rbp, [rsp-0A0h]
0x180001718  sub     rsp, 1A0h
0x18000171f  mov     rax, cs:__security_cookie
0x180001726  xor     rax, rsp
0x180001729  mov     [rbp+0C0h+var_30], rax
0x180001730  mov     rax, [rbp+0C0h+arg_B8]
0x180001737  lea     r14, word_180018022
0x18000173e  mov     r11, rdx
0x180001741  mov     r10, rcx
0x180001744  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001748  xor     edi, edi
0x18000174a  mov     rbx, r8
0x18000174d  mov     r9d, 1
0x180001753  mov     rcx, [rax]
0x180001756  test    rcx, rcx
0x180001759  jz      short loc_18000176B
0x18000175b  mov     rax, rdx
0x18000175e  inc     rax
0x180001761  cmp     [rcx+rax], dil
0x180001765  jnz     short loc_18000175E
0x180001767  inc     eax
0x180001769  jmp     short loc_180001771
0x18000176b  mov     rcx, r14
0x18000176e  mov     eax, r9d
0x180001771  mov     [rbp+0C0h+var_38], eax
0x180001777  lea     rsi, byte_180018020
0x18000177e  mov     rax, [rbp+0C0h+arg_B0]
0x180001785  mov     r8d, 2
0x18000178b  mov     [rbp+0C0h+var_50], rax
0x18000178f  mov     rax, [rbp+0C0h+arg_A8]
0x180001796  mov     [rbp+0C0h+var_40], rcx
0x18000179d  mov     [rbp+0C0h+var_34], edi
0x1800017a3  mov     [rbp+0C0h+var_48], 4
0x1800017ab  mov     rcx, [rax]
0x1800017ae  test    rcx, rcx
0x1800017b1  jz      short loc_1800017C8
0x1800017b3  mov     rax, rdx
0x1800017b6  inc     rax
0x1800017b9  cmp     [rcx+rax*2], di
0x1800017bd  jnz     short loc_1800017B6
0x1800017bf  lea     eax, ds:2[rax*2]
0x1800017c6  jmp     short loc_1800017CE
0x1800017c8  mov     rcx, rsi
0x1800017cb  mov     eax, r8d
0x1800017ce  mov     [rbp+0C0h+var_58], eax
0x1800017d1  mov     rax, [rbp+0C0h+arg_A0]
0x1800017d8  mov     [rbp+0C0h+var_60], rcx
0x1800017dc  mov     [rbp+0C0h+var_54], edi
0x1800017df  mov     rcx, [rax]
0x1800017e2  test    rcx, rcx
0x1800017e5  jz      short loc_1800017FC
0x1800017e7  mov     rax, rdx
0x1800017ea  inc     rax
0x1800017ed  cmp     [rcx+rax*2], di
0x1800017f1  jnz     short loc_1800017EA
0x1800017f3  lea     eax, ds:2[rax*2]
0x1800017fa  jmp     short loc_180001802
0x1800017fc  mov     rcx, rsi
0x1800017ff  mov     eax, r8d
0x180001802  mov     [rbp+0C0h+var_68], eax
0x180001805  mov     rax, [rbp+0C0h+arg_98]
0x18000180c  mov     [rbp+0C0h+var_70], rcx
0x180001810  mov     [rbp+0C0h+var_64], edi
0x180001813  mov     rcx, [rax]
0x180001816  test    rcx, rcx
0x180001819  jz      short loc_180001830
0x18000181b  mov     rax, rdx
0x18000181e  inc     rax
0x180001821  cmp     [rcx+rax*2], di
0x180001825  jnz     short loc_18000181E
0x180001827  lea     eax, ds:2[rax*2]
0x18000182e  jmp     short loc_180001836
0x180001830  mov     rcx, rsi
0x180001833  mov     eax, r8d
0x180001836  mov     [rbp+0C0h+var_78], eax
0x180001839  mov     rax, [rbp+0C0h+arg_90]
0x180001840  mov     [rbp+0C0h+var_80], rcx
0x180001844  mov     [rbp+0C0h+var_74], edi
0x180001847  mov     rcx, [rax]
0x18000184a  test    rcx, rcx
0x18000184d  jz      short loc_18000185F
0x18000184f  mov     rax, rdx
0x180001852  inc     rax
0x180001855  cmp     [rcx+rax], dil
0x180001859  jnz     short loc_180001852
0x18000185b  inc     eax
0x18000185d  jmp     short loc_180001865
0x18000185f  mov     rcx, r14
0x180001862  mov     eax, r9d
0x180001865  mov     [rbp+0C0h+var_88], eax
0x180001868  mov     rax, [rbp+0C0h+arg_88]
0x18000186f  mov     [rbp+0C0h+var_A0], rax
0x180001873  mov     rax, [rbp+0C0h+arg_80]
0x18000187a  mov     [rbp+0C0h+var_90], rcx
0x18000187e  mov     [rbp+0C0h+var_84], edi
0x180001881  mov     [rbp+0C0h+var_98], 4
0x180001889  mov     rcx, [rax]
0x18000188c  test    rcx, rcx
0x18000188f  jz      short loc_1800018A6
0x180001891  mov     rax, rdx
0x180001894  inc     rax
0x180001897  cmp     [rcx+rax*2], di
0x18000189b  jnz     short loc_180001894
0x18000189d  lea     eax, ds:2[rax*2]
0x1800018a4  jmp     short loc_1800018AC
0x1800018a6  mov     rcx, rsi
0x1800018a9  mov     eax, r8d
0x1800018ac  mov     [rbp+0C0h+var_A8], eax
0x1800018af  mov     rax, [rbp+0C0h+arg_78]
0x1800018b6  mov     [rbp+0C0h+var_B0], rcx
0x1800018ba  mov     [rbp+0C0h+var_A4], edi
0x1800018bd  mov     rcx, [rax]
0x1800018c0  test    rcx, rcx
0x1800018c3  jz      short loc_1800018D5
0x1800018c5  mov     rax, rdx
0x1800018c8  inc     rax
0x1800018cb  cmp     [rcx+rax], dil
0x1800018cf  jnz     short loc_1800018C8
0x1800018d1  inc     eax
0x1800018d3  jmp     short loc_1800018DB
0x1800018d5  mov     rcx, r14
0x1800018d8  mov     eax, r9d
0x1800018db  mov     [rbp+0C0h+var_B8], eax
0x1800018de  mov     rax, [rbp+0C0h+arg_70]
0x1800018e5  mov     [rbp+0C0h+var_D0], rax
0x1800018e9  mov     rax, [rbp+0C0h+arg_68]
0x1800018f0  mov     [rbp+0C0h+var_C0], rcx
0x1800018f4  mov     [rbp+0C0h+var_B4], edi
0x1800018f7  mov     [rbp+0C0h+var_C8], 4
0x1800018ff  mov     rcx, [rax]
0x180001902  test    rcx, rcx
0x180001905  jz      short loc_180001917
0x180001907  mov     rax, rdx
0x18000190a  inc     rax
0x18000190d  cmp     [rcx+rax], dil
0x180001911  jnz     short loc_18000190A
0x180001913  inc     eax
0x180001915  jmp     short loc_18000191D
0x180001917  mov     rcx, r14
0x18000191a  mov     eax, r9d
0x18000191d  mov     [rbp+0C0h+var_D8], eax
0x180001920  mov     rax, [rbp+0C0h+arg_60]
0x180001927  mov     [rbp+0C0h+var_F0], rax
0x18000192b  mov     rax, [rbp+0C0h+arg_58]
0x180001932  mov     [rbp+0C0h+var_E0], rcx
0x180001936  mov     [rbp+0C0h+var_D4], edi
0x180001939  mov     [rbp+0C0h+var_E8], 4
0x180001941  mov     rcx, [rax]
0x180001944  test    rcx, rcx
0x180001947  jz      short loc_18000195F
0x180001949  mov     rax, rdx
0x18000194c  inc     rax
0x18000194f  cmp     [rcx+rax*2], di
0x180001953  jnz     short loc_18000194C
0x180001955  lea     r8d, ds:2[rax*2]
0x18000195d  jmp     short loc_180001962
0x18000195f  mov     rcx, rsi
0x180001962  mov     rax, [rbp+0C0h+arg_50]
0x180001969  mov     [rbp+0C0h+var_110], rax
0x18000196d  mov     rax, [rbp+0C0h+arg_48]
0x180001974  mov     [rbp+0C0h+var_100], rcx
0x180001978  mov     [rbp+0C0h+var_F8], r8d
0x18000197c  mov     [rbp+0C0h+var_F4], edi
0x18000197f  mov     rcx, [rax]
0x180001982  mov     [rbp+0C0h+var_108], 4
0x18000198a  test    rcx, rcx
0x18000198d  jz      short loc_18000199F
0x18000198f  mov     rax, rdx
0x180001992  inc     rax
0x180001995  cmp     [rcx+rax], dil
0x180001999  jnz     short loc_180001992
0x18000199b  inc     eax
0x18000199d  jmp     short loc_1800019A5
0x18000199f  mov     rcx, r14
0x1800019a2  mov     eax, r9d
0x1800019a5  mov     [rbp+0C0h+var_118], eax
0x1800019a8  mov     rax, [rbp+0C0h+arg_40]
0x1800019af  mov     [rbp+0C0h+var_130], rax
0x1800019b3  mov     rax, [rbp+0C0h+arg_38]
0x1800019ba  mov     [rbp+0C0h+var_120], rcx
0x1800019be  mov     [rbp+0C0h+var_114], edi
0x1800019c1  mov     [rbp+0C0h+var_128], 4
0x1800019c9  mov     rcx, [rax]
0x1800019cc  test    rcx, rcx
0x1800019cf  jz      short loc_1800019E0
0x1800019d1  inc     rdx
0x1800019d4  cmp     [rcx+rdx], dil
0x1800019d8  jnz     short loc_1800019D1
0x1800019da  lea     r9d, [rdx+1]
0x1800019de  jmp     short loc_1800019E3
0x1800019e0  mov     rcx, r14
0x1800019e3  mov     rax, [rbp+0C0h+arg_30]
0x1800019ea  mov     r8, rbx; int
0x1800019ed  mov     [rsp+1C0h+var_150], rax
0x1800019f2  mov     rdx, r11; int
0x1800019f5  mov     rax, [rbp+0C0h+arg_28]
0x1800019fc  mov     [rsp+1C0h+var_160], rax
0x180001a01  mov     rax, [rbp+0C0h+arg_20]
0x180001a08  mov     [rsp+1C0h+var_170], rax
0x180001a0d  lea     rax, [rsp+1C0h+var_190]
0x180001a12  mov     [rbp+0C0h+var_140], rcx
0x180001a16  mov     rcx, r10; int
0x180001a19  mov     [rbp+0C0h+var_138], r9d
0x180001a1d  xor     r9d, r9d; int
0x180001a20  mov     [rsp+1C0h+var_198], rax; PEVENT_DATA_DESCRIPTOR
0x180001a25  mov     [rsp+1C0h+var_1A0], 16h; ULONG
0x180001a2d  mov     [rbp+0C0h+var_134], edi
0x180001a30  mov     [rsp+1C0h+var_148], 4
0x180001a39  mov     [rsp+1C0h+var_158], 8
0x180001a42  mov     [rsp+1C0h+var_168], 8
0x180001a4b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001a50  mov     rcx, [rbp+0C0h+var_30]
0x180001a57  xor     rcx, rsp; StackCookie
0x180001a5a  call    __security_check_cookie
0x180001a5f  mov     rbx, [rsp+1C0h+arg_18]
0x180001a67  add     rsp, 1A0h
0x180001a6e  pop     r15
0x180001a70  pop     r14
0x180001a72  pop     rdi
0x180001a73  pop     rsi
0x180001a74  pop     rbp
0x180001a75  retn
```
