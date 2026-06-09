# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800014c8`
- end: `0x1800017b7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const WCHAR **, __int64, const wchar_t **, __int64, const wchar_t **, const WCHAR **, __int64, const wchar_t **, const WCHAR **, __int64, __int64, const wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800060cc`

## callees

- `0x180001158`
- `0x1800014c8`
- `0x18000fc90`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const wchar_t **a7,
        __int64 a8,
        const wchar_t **a9,
        __int64 a10,
        const WCHAR **a11,
        __int64 a12,
        const wchar_t **a13,
        __int64 a14,
        const wchar_t **a15,
        const WCHAR **a16,
        __int64 a17,
        const wchar_t **a18,
        const WCHAR **a19,
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
  const WCHAR *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const wchar_t *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  const WCHAR *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const wchar_t *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const wchar_t *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const WCHAR *v45; // rcx
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
  const WCHAR *v67; // [rsp+B0h] [rbp-50h]
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
  const WCHAR *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const wchar_t *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  const WCHAR *v88; // [rsp+130h] [rbp+30h]
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
    v26 = &word_1800189A6;
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
    v30 = &OutputString;
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
    v33 = &word_1800189A6;
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
    v36 = &OutputString;
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
    v39 = &word_1800189A6;
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
    v42 = &word_1800189A6;
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
    v45 = &OutputString;
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
    v47 = &word_1800189A6;
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
    v50 = &word_1800189A6;
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
0x1800014c8  mov     [rsp-8+arg_10], rbx
0x1800014cd  push    rbp
0x1800014ce  push    rdi
0x1800014cf  push    r14
0x1800014d1  lea     rbp, [rsp-80h]
0x1800014d6  sub     rsp, 180h
0x1800014dd  mov     rax, cs:__security_cookie
0x1800014e4  xor     rax, rsp
0x1800014e7  mov     [rbp+90h+var_20], rax
0x1800014eb  mov     rax, [rbp+90h+arg_A8]
0x1800014f2  lea     rdi, word_1800189A6
0x1800014f9  mov     r11, rdx
0x1800014fc  mov     r10, rcx
0x1800014ff  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001503  xor     ebx, ebx
0x180001505  mov     r8d, 1
0x18000150b  mov     rcx, [rax]
0x18000150e  test    rcx, rcx
0x180001511  jz      short loc_180001522
0x180001513  mov     rax, rdx
0x180001516  inc     rax
0x180001519  cmp     [rcx+rax], bl
0x18000151c  jnz     short loc_180001516
0x18000151e  inc     eax
0x180001520  jmp     short loc_180001528
0x180001522  mov     rcx, rdi
0x180001525  mov     eax, r8d
0x180001528  mov     [rbp+90h+var_28], eax
0x18000152b  mov     r9d, 2
0x180001531  mov     rax, [rbp+90h+arg_A0]
0x180001538  mov     [rbp+90h+var_40], rax
0x18000153c  mov     rax, [rbp+90h+arg_98]
0x180001543  mov     [rbp+90h+var_50], rax
0x180001547  mov     rax, [rbp+90h+arg_90]
0x18000154e  mov     [rbp+90h+var_30], rcx
0x180001552  mov     [rbp+90h+var_24], ebx
0x180001555  mov     [rbp+90h+var_38], 4
0x18000155d  mov     rcx, [rax]
0x180001560  mov     [rbp+90h+var_48], 4
0x180001568  test    rcx, rcx
0x18000156b  jz      short loc_180001582
0x18000156d  mov     rax, rdx
0x180001570  inc     rax
0x180001573  cmp     [rcx+rax*2], bx
0x180001577  jnz     short loc_180001570
0x180001579  lea     eax, ds:2[rax*2]
0x180001580  jmp     short loc_18000158C
0x180001582  lea     rcx, OutputString
0x180001589  mov     eax, r9d
0x18000158c  mov     [rbp+90h+var_58], eax
0x18000158f  mov     rax, [rbp+90h+arg_88]
0x180001596  mov     [rbp+90h+var_60], rcx
0x18000159a  mov     [rbp+90h+var_54], ebx
0x18000159d  mov     rcx, [rax]
0x1800015a0  test    rcx, rcx
0x1800015a3  jz      short loc_1800015B4
0x1800015a5  mov     rax, rdx
0x1800015a8  inc     rax
0x1800015ab  cmp     [rcx+rax], bl
0x1800015ae  jnz     short loc_1800015A8
0x1800015b0  inc     eax
0x1800015b2  jmp     short loc_1800015BA
0x1800015b4  mov     rcx, rdi
0x1800015b7  mov     eax, r8d
0x1800015ba  mov     [rbp+90h+var_68], eax
0x1800015bd  mov     rax, [rbp+90h+arg_80]
0x1800015c4  mov     [rbp+90h+var_80], rax
0x1800015c8  mov     rax, [rbp+90h+arg_78]
0x1800015cf  mov     [rbp+90h+var_70], rcx
0x1800015d3  mov     [rbp+90h+var_64], ebx
0x1800015d6  mov     [rbp+90h+var_78], 4
0x1800015de  mov     rcx, [rax]
0x1800015e1  test    rcx, rcx
0x1800015e4  jz      short loc_1800015FB
0x1800015e6  mov     rax, rdx
0x1800015e9  inc     rax
0x1800015ec  cmp     [rcx+rax*2], bx
0x1800015f0  jnz     short loc_1800015E9
0x1800015f2  lea     eax, ds:2[rax*2]
0x1800015f9  jmp     short loc_180001605
0x1800015fb  lea     rcx, OutputString
0x180001602  mov     eax, r9d
0x180001605  mov     [rbp+90h+var_88], eax
0x180001608  mov     rax, [rbp+90h+arg_70]
0x18000160f  mov     [rbp+90h+var_90], rcx
0x180001613  mov     [rbp+90h+var_84], ebx
0x180001616  mov     rcx, [rax]
0x180001619  test    rcx, rcx
0x18000161c  jz      short loc_18000162D
0x18000161e  mov     rax, rdx
0x180001621  inc     rax
0x180001624  cmp     [rcx+rax], bl
0x180001627  jnz     short loc_180001621
0x180001629  inc     eax
0x18000162b  jmp     short loc_180001633
0x18000162d  mov     rcx, rdi
0x180001630  mov     eax, r8d
0x180001633  mov     [rbp+90h+var_98], eax
0x180001636  mov     rax, [rbp+90h+arg_68]
0x18000163d  mov     [rbp+90h+var_B0], rax
0x180001641  mov     rax, [rbp+90h+arg_60]
0x180001648  mov     [rbp+90h+var_A0], rcx
0x18000164c  mov     [rbp+90h+var_94], ebx
0x18000164f  mov     [rbp+90h+var_A8], 4
0x180001657  mov     rcx, [rax]
0x18000165a  test    rcx, rcx
0x18000165d  jz      short loc_18000166E
0x18000165f  mov     rax, rdx
0x180001662  inc     rax
0x180001665  cmp     [rcx+rax], bl
0x180001668  jnz     short loc_180001662
0x18000166a  inc     eax
0x18000166c  jmp     short loc_180001674
0x18000166e  mov     rcx, rdi
0x180001671  mov     eax, r8d
0x180001674  mov     [rbp+90h+var_B8], eax
0x180001677  mov     rax, [rbp+90h+arg_58]
0x18000167e  mov     [rbp+90h+var_D0], rax
0x180001682  mov     rax, [rbp+90h+arg_50]
0x180001689  mov     [rbp+90h+var_C0], rcx
0x18000168d  mov     [rbp+90h+var_B4], ebx
0x180001690  mov     [rbp+90h+var_C8], 4
0x180001698  mov     rcx, [rax]
0x18000169b  test    rcx, rcx
0x18000169e  jz      short loc_1800016B6
0x1800016a0  mov     rax, rdx
0x1800016a3  inc     rax
0x1800016a6  cmp     [rcx+rax*2], bx
0x1800016aa  jnz     short loc_1800016A3
0x1800016ac  lea     r9d, ds:2[rax*2]
0x1800016b4  jmp     short loc_1800016BD
0x1800016b6  lea     rcx, OutputString
0x1800016bd  mov     rax, [rbp+90h+arg_48]
0x1800016c4  mov     [rbp+90h+var_F0], rax
0x1800016c8  mov     rax, [rbp+90h+arg_40]
0x1800016cf  mov     [rbp+90h+var_E0], rcx
0x1800016d3  mov     [rbp+90h+var_D8], r9d
0x1800016d7  mov     [rbp+90h+var_D4], ebx
0x1800016da  mov     rcx, [rax]
0x1800016dd  mov     [rbp+90h+var_E8], 4
0x1800016e5  test    rcx, rcx
0x1800016e8  jz      short loc_1800016F9
0x1800016ea  mov     rax, rdx
0x1800016ed  inc     rax
0x1800016f0  cmp     [rcx+rax], bl
0x1800016f3  jnz     short loc_1800016ED
0x1800016f5  inc     eax
0x1800016f7  jmp     short loc_1800016FF
0x1800016f9  mov     rcx, rdi
0x1800016fc  mov     eax, r8d
0x1800016ff  mov     [rbp+90h+var_F8], eax
0x180001702  mov     rax, [rbp+90h+arg_38]
0x180001709  mov     [rbp+90h+var_110], rax
0x18000170d  mov     rax, [rbp+90h+arg_30]
0x180001714  mov     [rbp+90h+var_100], rcx
0x180001718  mov     [rbp+90h+var_F4], ebx
0x18000171b  mov     [rbp+90h+var_108], 4
0x180001723  mov     rcx, [rax]
0x180001726  test    rcx, rcx
0x180001729  jz      short loc_180001739
0x18000172b  inc     rdx
0x18000172e  cmp     [rcx+rdx], bl
0x180001731  jnz     short loc_18000172B
0x180001733  lea     r8d, [rdx+1]
0x180001737  jmp     short loc_18000173C
0x180001739  mov     rcx, rdi
0x18000173c  mov     rax, [rbp+90h+arg_28]
0x180001743  xor     r9d, r9d; int
0x180001746  mov     [rsp+190h+var_130], rax
0x18000174b  mov     rdx, r11; int
0x18000174e  mov     rax, [rbp+90h+arg_20]
0x180001755  mov     [rsp+190h+var_140], rax
0x18000175a  lea     rax, [rsp+190h+var_160]
0x18000175f  mov     [rsp+190h+var_120], rcx
0x180001764  mov     rcx, r10; int
0x180001767  mov     [rsp+190h+var_118], r8d
0x18000176c  xor     r8d, r8d; int
0x18000176f  mov     [rsp+190h+var_168], rax; PEVENT_DATA_DESCRIPTOR
0x180001774  mov     [rsp+190h+var_170], 14h; ULONG
0x18000177c  mov     [rsp+190h+var_114], ebx
0x180001780  mov     [rsp+190h+var_128], 4
0x180001789  mov     [rsp+190h+var_138], 8
0x180001792  call    _tlgWriteTransfer_EventWriteTransfer
0x180001797  mov     rcx, [rbp+90h+var_20]
0x18000179b  xor     rcx, rsp; StackCookie
0x18000179e  call    __security_check_cookie
0x1800017a3  mov     rbx, [rsp+190h+arg_10]
0x1800017ab  add     rsp, 180h
0x1800017b2  pop     r14
0x1800017b4  pop     rdi
0x1800017b5  pop     rbp
0x1800017b6  retn
```
