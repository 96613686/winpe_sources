# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800013dc`
- end: `0x1800016c7`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@U1@U1@U2@U2@U2@U2@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@33444433333333334@Z`
- size: `747`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, __int64, const unsigned __int16 **, const unsigned __int16 **, const unsigned __int16 **, const unsigned __int16 **, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e5c4`

## callees

- `0x180001010`
- `0x1800013dc`
- `0x180001ec0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        __int64 a9,
        __int64 a10,
        const unsigned __int16 **a11,
        const unsigned __int16 **a12,
        const unsigned __int16 **a13,
        const unsigned __int16 **a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        __int64 a23,
        __int64 a24,
        const unsigned __int16 **a25)
{
  __int64 v25; // rcx
  int v27; // edx
  const unsigned __int16 *v28; // r8
  __int64 v29; // rax
  int v30; // eax
  const unsigned __int16 *v31; // r8
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // r8
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // r8
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // r8
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // r8
  _BYTE v45[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B0h]
  __int64 v47; // [rsp+58h] [rbp-A8h]
  __int64 v48; // [rsp+60h] [rbp-A0h]
  __int64 v49; // [rsp+68h] [rbp-98h]
  __int64 v50; // [rsp+70h] [rbp-90h]
  __int64 v51; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v52; // [rsp+80h] [rbp-80h]
  int v53; // [rsp+88h] [rbp-78h]
  int v54; // [rsp+8Ch] [rbp-74h]
  __int64 v55; // [rsp+90h] [rbp-70h]
  __int64 v56; // [rsp+98h] [rbp-68h]
  __int64 v57; // [rsp+A0h] [rbp-60h]
  __int64 v58; // [rsp+A8h] [rbp-58h]
  const unsigned __int16 *v59; // [rsp+B0h] [rbp-50h]
  int v60; // [rsp+B8h] [rbp-48h]
  int v61; // [rsp+BCh] [rbp-44h]
  const unsigned __int16 *v62; // [rsp+C0h] [rbp-40h]
  int v63; // [rsp+C8h] [rbp-38h]
  int v64; // [rsp+CCh] [rbp-34h]
  const unsigned __int16 *v65; // [rsp+D0h] [rbp-30h]
  int v66; // [rsp+D8h] [rbp-28h]
  int v67; // [rsp+DCh] [rbp-24h]
  const unsigned __int16 *v68; // [rsp+E0h] [rbp-20h]
  int v69; // [rsp+E8h] [rbp-18h]
  int v70; // [rsp+ECh] [rbp-14h]
  __int64 v71; // [rsp+F0h] [rbp-10h]
  __int64 v72; // [rsp+F8h] [rbp-8h]
  __int64 v73; // [rsp+100h] [rbp+0h]
  __int64 v74; // [rsp+108h] [rbp+8h]
  __int64 v75; // [rsp+110h] [rbp+10h]
  __int64 v76; // [rsp+118h] [rbp+18h]
  __int64 v77; // [rsp+120h] [rbp+20h]
  __int64 v78; // [rsp+128h] [rbp+28h]
  __int64 v79; // [rsp+130h] [rbp+30h]
  __int64 v80; // [rsp+138h] [rbp+38h]
  __int64 v81; // [rsp+140h] [rbp+40h]
  __int64 v82; // [rsp+148h] [rbp+48h]
  __int64 v83; // [rsp+150h] [rbp+50h]
  __int64 v84; // [rsp+158h] [rbp+58h]
  __int64 v85; // [rsp+160h] [rbp+60h]
  __int64 v86; // [rsp+168h] [rbp+68h]
  __int64 v87; // [rsp+170h] [rbp+70h]
  __int64 v88; // [rsp+178h] [rbp+78h]
  __int64 v89; // [rsp+180h] [rbp+80h]
  __int64 v90; // [rsp+188h] [rbp+88h]
  const unsigned __int16 *v91; // [rsp+190h] [rbp+90h]
  int v92; // [rsp+198h] [rbp+98h]
  int v93; // [rsp+19Ch] [rbp+9Ch]

  v25 = -1;
  v27 = 2;
  v28 = *a25;
  if ( *a25 )
  {
    v29 = -1;
    do
      ++v29;
    while ( v28[v29] );
    v30 = 2 * v29 + 2;
  }
  else
  {
    v28 = &qword_18003BA28;
    v30 = 2;
  }
  v92 = v30;
  v89 = a24;
  v87 = a23;
  v85 = a22;
  v83 = a21;
  v81 = a20;
  v79 = a19;
  v77 = a18;
  v75 = a17;
  v73 = a16;
  v71 = a15;
  v91 = v28;
  v93 = 0;
  v90 = 4;
  v31 = *a14;
  v88 = 4;
  v86 = 4;
  v84 = 4;
  v82 = 4;
  v80 = 4;
  v78 = 4;
  v76 = 4;
  v74 = 4;
  v72 = 4;
  if ( v31 )
  {
    v32 = -1;
    do
      ++v32;
    while ( v31[v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &qword_18003BA28;
    v33 = 2;
  }
  v69 = v33;
  v68 = v31;
  v70 = 0;
  v34 = *a13;
  if ( *a13 )
  {
    v35 = -1;
    do
      ++v35;
    while ( v34[v35] );
    v36 = 2 * v35 + 2;
  }
  else
  {
    v34 = &qword_18003BA28;
    v36 = 2;
  }
  v66 = v36;
  v65 = v34;
  v67 = 0;
  v37 = *a12;
  if ( *a12 )
  {
    v38 = -1;
    do
      ++v38;
    while ( v37[v38] );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &qword_18003BA28;
    v39 = 2;
  }
  v63 = v39;
  v62 = v37;
  v64 = 0;
  v40 = *a11;
  if ( *a11 )
  {
    v41 = -1;
    do
      ++v41;
    while ( v40[v41] );
    v42 = 2 * v41 + 2;
  }
  else
  {
    v40 = &qword_18003BA28;
    v42 = 2;
  }
  v60 = v42;
  v57 = a10;
  v55 = a9;
  v59 = v40;
  v61 = 0;
  v58 = 4;
  v43 = *a8;
  v56 = 4;
  if ( v43 )
  {
    do
      ++v25;
    while ( v43[v25] );
    v27 = 2 * v25 + 2;
  }
  else
  {
    v43 = &qword_18003BA28;
  }
  v50 = a7;
  v48 = a6;
  v46 = a5;
  v52 = v43;
  v53 = v27;
  v54 = 0;
  v51 = 4;
  v49 = 4;
  v47 = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180048098, a2, 0, 0, 23, v45);
}

```

## disassembly

```asm
0x1800013dc  mov     [rsp-8+arg_0], rbx
0x1800013e1  push    rbp
0x1800013e2  lea     rbp, [rsp-0B0h]
0x1800013ea  sub     rsp, 1B0h
0x1800013f1  mov     rax, cs:__security_cookie
0x1800013f8  xor     rax, rsp
0x1800013fb  mov     [rbp+0B0h+var_10], rax
0x180001402  mov     rax, [rbp+0B0h+arg_C0]
0x180001409  lea     r11, qword_18003BA28
0x180001410  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001414  xor     r9d, r9d
0x180001417  mov     r10, rdx
0x18000141a  mov     edx, 2
0x18000141f  mov     r8, [rax]
0x180001422  test    r8, r8
0x180001425  jz      short loc_18000143D
0x180001427  mov     rax, rcx
0x18000142a  inc     rax
0x18000142d  cmp     [r8+rax*2], r9w
0x180001432  jnz     short loc_18000142A
0x180001434  lea     eax, ds:2[rax*2]
0x18000143b  jmp     short loc_180001442
0x18000143d  mov     r8, r11
0x180001440  mov     eax, edx
0x180001442  mov     [rbp+0B0h+var_18], eax
0x180001448  mov     rax, [rbp+0B0h+arg_B8]
0x18000144f  mov     [rbp+0B0h+var_30], rax
0x180001456  mov     rax, [rbp+0B0h+arg_B0]
0x18000145d  mov     [rbp+0B0h+var_40], rax
0x180001461  mov     rax, [rbp+0B0h+arg_A8]
0x180001468  mov     [rbp+0B0h+var_50], rax
0x18000146c  mov     rax, [rbp+0B0h+arg_A0]
0x180001473  mov     [rbp+0B0h+var_60], rax
0x180001477  mov     rax, [rbp+0B0h+arg_98]
0x18000147e  mov     [rbp+0B0h+var_70], rax
0x180001482  mov     rax, [rbp+0B0h+arg_90]
0x180001489  mov     [rbp+0B0h+var_80], rax
0x18000148d  mov     rax, [rbp+0B0h+arg_88]
0x180001494  mov     [rbp+0B0h+var_90], rax
0x180001498  mov     rax, [rbp+0B0h+arg_80]
0x18000149f  mov     [rbp+0B0h+var_A0], rax
0x1800014a3  mov     rax, [rbp+0B0h+arg_78]
0x1800014aa  mov     [rbp+0B0h+var_B0], rax
0x1800014ae  mov     rax, [rbp+0B0h+arg_70]
0x1800014b5  mov     [rbp+0B0h+var_C0], rax
0x1800014b9  mov     rax, [rbp+0B0h+arg_68]
0x1800014c0  mov     [rbp+0B0h+var_20], r8
0x1800014c7  mov     [rbp+0B0h+var_14], r9d
0x1800014ce  mov     [rbp+0B0h+var_28], 4
0x1800014d9  mov     r8, [rax]
0x1800014dc  mov     [rbp+0B0h+var_38], 4
0x1800014e4  mov     [rbp+0B0h+var_48], 4
0x1800014ec  mov     [rbp+0B0h+var_58], 4
0x1800014f4  mov     [rbp+0B0h+var_68], 4
0x1800014fc  mov     [rbp+0B0h+var_78], 4
0x180001504  mov     [rbp+0B0h+var_88], 4
0x18000150c  mov     [rbp+0B0h+var_98], 4
0x180001514  mov     [rbp+0B0h+var_A8], 4
0x18000151c  mov     [rbp+0B0h+var_B8], 4
0x180001524  test    r8, r8
0x180001527  jz      short loc_18000153F
0x180001529  mov     rax, rcx
0x18000152c  inc     rax
0x18000152f  cmp     [r8+rax*2], r9w
0x180001534  jnz     short loc_18000152C
0x180001536  lea     eax, ds:2[rax*2]
0x18000153d  jmp     short loc_180001544
0x18000153f  mov     r8, r11
0x180001542  mov     eax, edx
0x180001544  mov     [rbp+0B0h+var_C8], eax
0x180001547  mov     rax, [rbp+0B0h+arg_60]
0x18000154e  mov     [rbp+0B0h+var_D0], r8
0x180001552  mov     [rbp+0B0h+var_C4], r9d
0x180001556  mov     r8, [rax]
0x180001559  test    r8, r8
0x18000155c  jz      short loc_180001574
0x18000155e  mov     rax, rcx
0x180001561  inc     rax
0x180001564  cmp     [r8+rax*2], r9w
0x180001569  jnz     short loc_180001561
0x18000156b  lea     eax, ds:2[rax*2]
0x180001572  jmp     short loc_180001579
0x180001574  mov     r8, r11
0x180001577  mov     eax, edx
0x180001579  mov     [rbp+0B0h+var_D8], eax
0x18000157c  mov     rax, [rbp+0B0h+arg_58]
0x180001583  mov     [rbp+0B0h+var_E0], r8
0x180001587  mov     [rbp+0B0h+var_D4], r9d
0x18000158b  mov     r8, [rax]
0x18000158e  test    r8, r8
0x180001591  jz      short loc_1800015A9
0x180001593  mov     rax, rcx
0x180001596  inc     rax
0x180001599  cmp     [r8+rax*2], r9w
0x18000159e  jnz     short loc_180001596
0x1800015a0  lea     eax, ds:2[rax*2]
0x1800015a7  jmp     short loc_1800015AE
0x1800015a9  mov     r8, r11
0x1800015ac  mov     eax, edx
0x1800015ae  mov     [rbp+0B0h+var_E8], eax
0x1800015b1  mov     rax, [rbp+0B0h+arg_50]
0x1800015b8  mov     [rbp+0B0h+var_F0], r8
0x1800015bc  mov     [rbp+0B0h+var_E4], r9d
0x1800015c0  mov     r8, [rax]
0x1800015c3  test    r8, r8
0x1800015c6  jz      short loc_1800015DE
0x1800015c8  mov     rax, rcx
0x1800015cb  inc     rax
0x1800015ce  cmp     [r8+rax*2], r9w
0x1800015d3  jnz     short loc_1800015CB
0x1800015d5  lea     eax, ds:2[rax*2]
0x1800015dc  jmp     short loc_1800015E3
0x1800015de  mov     r8, r11
0x1800015e1  mov     eax, edx
0x1800015e3  mov     [rbp+0B0h+var_F8], eax
0x1800015e6  mov     rax, [rbp+0B0h+arg_48]
0x1800015ed  mov     [rbp+0B0h+var_110], rax
0x1800015f1  mov     rax, [rbp+0B0h+arg_40]
0x1800015f8  mov     [rbp+0B0h+var_120], rax
0x1800015fc  mov     rax, [rbp+0B0h+arg_38]
0x180001603  mov     [rbp+0B0h+var_100], r8
0x180001607  mov     [rbp+0B0h+var_F4], r9d
0x18000160b  mov     [rbp+0B0h+var_108], 4
0x180001613  mov     r8, [rax]
0x180001616  mov     [rbp+0B0h+var_118], 4
0x18000161e  test    r8, r8
0x180001621  jz      short loc_180001636
0x180001623  inc     rcx
0x180001626  cmp     [r8+rcx*2], r9w
0x18000162b  jnz     short loc_180001623
0x18000162d  lea     edx, ds:2[rcx*2]
0x180001634  jmp     short loc_180001639
0x180001636  mov     r8, r11
0x180001639  mov     rax, [rbp+0B0h+arg_30]
0x180001640  lea     rcx, dword_180048098
0x180001647  mov     [rsp+1B0h+var_140], rax
0x18000164c  mov     rax, [rbp+0B0h+arg_28]
0x180001653  mov     [rsp+1B0h+var_150], rax
0x180001658  mov     rax, [rbp+0B0h+arg_20]
0x18000165f  mov     [rsp+1B0h+var_160], rax
0x180001664  lea     rax, [rsp+1B0h+var_180]
0x180001669  mov     [rbp+0B0h+var_130], r8
0x18000166d  xor     r8d, r8d
0x180001670  mov     [rbp+0B0h+var_128], edx
0x180001673  mov     rdx, r10
0x180001676  mov     [rsp+1B0h+var_188], rax
0x18000167b  mov     [rsp+1B0h+var_190], 17h
0x180001683  mov     [rbp+0B0h+var_124], r9d
0x180001687  mov     [rsp+1B0h+var_138], 4
0x180001690  mov     [rsp+1B0h+var_148], 4
0x180001699  mov     [rsp+1B0h+var_158], 4
0x1800016a2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800016a7  mov     rcx, [rbp+0B0h+var_10]
0x1800016ae  xor     rcx, rsp; StackCookie
0x1800016b1  call    __security_check_cookie
0x1800016b6  mov     rbx, [rsp+1B0h+arg_0]
0x1800016be  add     rsp, 1B0h
0x1800016c5  pop     rbp
0x1800016c6  retn
```
