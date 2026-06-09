# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800036d0`
- end: `0x1800039db`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029b80`

## callees

- `0x180001010`
- `0x1800036d0`
- `0x1800050f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
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
        __int64 a22,
        const unsigned __int16 **a23)
{
  __int64 v25; // rdx
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int v31; // r9d
  int *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  int *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  int *v47; // rcx
  __int64 v48; // rax
  const unsigned __int16 *v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  const unsigned __int16 *v52; // rcx
  struct _EVENT_DATA_DESCRIPTOR v54; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B0h]
  __int64 v56; // [rsp+58h] [rbp-A8h]
  __int64 v57; // [rsp+60h] [rbp-A0h]
  __int64 v58; // [rsp+68h] [rbp-98h]
  __int64 v59; // [rsp+70h] [rbp-90h]
  __int64 v60; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v61; // [rsp+80h] [rbp-80h]
  int v62; // [rsp+88h] [rbp-78h]
  int v63; // [rsp+8Ch] [rbp-74h]
  __int64 v64; // [rsp+90h] [rbp-70h]
  __int64 v65; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v66; // [rsp+A0h] [rbp-60h]
  int v67; // [rsp+A8h] [rbp-58h]
  int v68; // [rsp+ACh] [rbp-54h]
  __int64 v69; // [rsp+B0h] [rbp-50h]
  __int64 v70; // [rsp+B8h] [rbp-48h]
  int *v71; // [rsp+C0h] [rbp-40h]
  int v72; // [rsp+C8h] [rbp-38h]
  int v73; // [rsp+CCh] [rbp-34h]
  __int64 v74; // [rsp+D0h] [rbp-30h]
  __int64 v75; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v76; // [rsp+E0h] [rbp-20h]
  int v77; // [rsp+E8h] [rbp-18h]
  int v78; // [rsp+ECh] [rbp-14h]
  __int64 v79; // [rsp+F0h] [rbp-10h]
  __int64 v80; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  int *v84; // [rsp+110h] [rbp+10h]
  int v85; // [rsp+118h] [rbp+18h]
  int v86; // [rsp+11Ch] [rbp+1Ch]
  __int64 v87; // [rsp+120h] [rbp+20h]
  __int64 v88; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  int *v92; // [rsp+140h] [rbp+40h]
  int v93; // [rsp+148h] [rbp+48h]
  int v94; // [rsp+14Ch] [rbp+4Ch]
  __int64 v95; // [rsp+150h] [rbp+50h]
  __int64 v96; // [rsp+158h] [rbp+58h]
  __int64 v97; // [rsp+160h] [rbp+60h]
  __int64 v98; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v99; // [rsp+170h] [rbp+70h]
  int v100; // [rsp+178h] [rbp+78h]
  int v101; // [rsp+17Ch] [rbp+7Ch]

  v25 = -1;
  v27 = 1;
  v28 = *a23;
  if ( *a23 )
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
  v100 = v30;
  v31 = 2;
  v97 = a22;
  v95 = a21;
  v99 = v28;
  v101 = 0;
  v98 = 4;
  v32 = *a20;
  v96 = 4;
  if ( v32 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)v32 + v33) );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &dword_180031EE4;
    v34 = 2;
  }
  v93 = v34;
  v92 = v32;
  v94 = 0;
  v35 = *a19;
  if ( *a19 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &byte_180031EE0;
    v37 = 1;
  }
  v90 = v37;
  v87 = a18;
  v89 = v35;
  v91 = 0;
  v88 = 4;
  v38 = *a17;
  if ( *a17 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_WORD *)v38 + v39) );
    v40 = 2 * v39 + 2;
  }
  else
  {
    v38 = &dword_180031EE4;
    v40 = 2;
  }
  v85 = v40;
  v84 = v38;
  v86 = 0;
  v41 = *a16;
  if ( *a16 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &byte_180031EE0;
    v43 = 1;
  }
  v82 = v43;
  v79 = a15;
  v81 = v41;
  v83 = 0;
  v80 = 4;
  v44 = *a14;
  if ( *a14 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &byte_180031EE0;
    v46 = 1;
  }
  v77 = v46;
  v74 = a13;
  v76 = v44;
  v78 = 0;
  v75 = 4;
  v47 = *a12;
  if ( *a12 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_WORD *)v47 + v48) );
    v31 = 2 * v48 + 2;
  }
  else
  {
    v47 = &dword_180031EE4;
  }
  v69 = a11;
  v71 = v47;
  v72 = v31;
  v73 = 0;
  v49 = *a10;
  v70 = 4;
  if ( v49 )
  {
    v50 = -1;
    do
      ++v50;
    while ( *((_BYTE *)v49 + v50) );
    v51 = v50 + 1;
  }
  else
  {
    v49 = &byte_180031EE0;
    v51 = 1;
  }
  v67 = v51;
  v64 = a9;
  v66 = v49;
  v68 = 0;
  v65 = 4;
  v52 = *a8;
  if ( *a8 )
  {
    do
      ++v25;
    while ( *((_BYTE *)v52 + v25) );
    v27 = v25 + 1;
  }
  else
  {
    v52 = &byte_180031EE0;
  }
  v59 = a7;
  v57 = a6;
  v55 = a5;
  v61 = v52;
  v62 = v27;
  v63 = 0;
  v60 = 4;
  v58 = 8;
  v56 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x15u, &v54);
}

```

## disassembly

```asm
0x1800036d0  push    rbp
0x1800036d2  push    rbx
0x1800036d3  push    rsi
0x1800036d4  push    rdi
0x1800036d5  push    r14
0x1800036d7  lea     rbp, [rsp-90h]
0x1800036df  sub     rsp, 190h
0x1800036e6  mov     rax, cs:__security_cookie
0x1800036ed  xor     rax, rsp
0x1800036f0  mov     [rbp+0B0h+var_30], rax
0x1800036f7  mov     rax, [rbp+0B0h+arg_B0]
0x1800036fe  lea     rsi, byte_180031EE0
0x180003705  mov     r11, rdx
0x180003708  mov     r10, rcx
0x18000370b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000370f  xor     edi, edi
0x180003711  mov     rbx, r8
0x180003714  mov     r8d, 1
0x18000371a  mov     rcx, [rax]
0x18000371d  test    rcx, rcx
0x180003720  jz      short loc_180003732
0x180003722  mov     rax, rdx
0x180003725  inc     rax
0x180003728  cmp     [rcx+rax], dil
0x18000372c  jnz     short loc_180003725
0x18000372e  inc     eax
0x180003730  jmp     short loc_180003738
0x180003732  mov     rcx, rsi
0x180003735  mov     eax, r8d
0x180003738  mov     [rbp+0B0h+var_38], eax
0x18000373b  mov     r9d, 2
0x180003741  mov     rax, [rbp+0B0h+arg_A8]
0x180003748  mov     [rbp+0B0h+var_50], rax
0x18000374c  mov     rax, [rbp+0B0h+arg_A0]
0x180003753  mov     [rbp+0B0h+var_60], rax
0x180003757  mov     rax, [rbp+0B0h+arg_98]
0x18000375e  mov     [rbp+0B0h+var_40], rcx
0x180003762  mov     [rbp+0B0h+var_34], edi
0x180003765  mov     [rbp+0B0h+var_48], 4
0x18000376d  mov     rcx, [rax]
0x180003770  mov     [rbp+0B0h+var_58], 4
0x180003778  test    rcx, rcx
0x18000377b  jz      short loc_180003792
0x18000377d  mov     rax, rdx
0x180003780  inc     rax
0x180003783  cmp     [rcx+rax*2], di
0x180003787  jnz     short loc_180003780
0x180003789  lea     eax, ds:2[rax*2]
0x180003790  jmp     short loc_18000379C
0x180003792  lea     rcx, dword_180031EE4
0x180003799  mov     eax, r9d
0x18000379c  mov     [rbp+0B0h+var_68], eax
0x18000379f  mov     rax, [rbp+0B0h+arg_90]
0x1800037a6  mov     [rbp+0B0h+var_70], rcx
0x1800037aa  mov     [rbp+0B0h+var_64], edi
0x1800037ad  mov     rcx, [rax]
0x1800037b0  test    rcx, rcx
0x1800037b3  jz      short loc_1800037C5
0x1800037b5  mov     rax, rdx
0x1800037b8  inc     rax
0x1800037bb  cmp     [rcx+rax], dil
0x1800037bf  jnz     short loc_1800037B8
0x1800037c1  inc     eax
0x1800037c3  jmp     short loc_1800037CB
0x1800037c5  mov     rcx, rsi
0x1800037c8  mov     eax, r8d
0x1800037cb  mov     [rbp+0B0h+var_78], eax
0x1800037ce  mov     rax, [rbp+0B0h+arg_88]
0x1800037d5  mov     [rbp+0B0h+var_90], rax
0x1800037d9  mov     rax, [rbp+0B0h+arg_80]
0x1800037e0  mov     [rbp+0B0h+var_80], rcx
0x1800037e4  mov     [rbp+0B0h+var_74], edi
0x1800037e7  mov     [rbp+0B0h+var_88], 4
0x1800037ef  mov     rcx, [rax]
0x1800037f2  test    rcx, rcx
0x1800037f5  jz      short loc_18000380C
0x1800037f7  mov     rax, rdx
0x1800037fa  inc     rax
0x1800037fd  cmp     [rcx+rax*2], di
0x180003801  jnz     short loc_1800037FA
0x180003803  lea     eax, ds:2[rax*2]
0x18000380a  jmp     short loc_180003816
0x18000380c  lea     rcx, dword_180031EE4
0x180003813  mov     eax, r9d
0x180003816  mov     [rbp+0B0h+var_98], eax
0x180003819  mov     rax, [rbp+0B0h+arg_78]
0x180003820  mov     [rbp+0B0h+var_A0], rcx
0x180003824  mov     [rbp+0B0h+var_94], edi
0x180003827  mov     rcx, [rax]
0x18000382a  test    rcx, rcx
0x18000382d  jz      short loc_18000383F
0x18000382f  mov     rax, rdx
0x180003832  inc     rax
0x180003835  cmp     [rcx+rax], dil
0x180003839  jnz     short loc_180003832
0x18000383b  inc     eax
0x18000383d  jmp     short loc_180003845
0x18000383f  mov     rcx, rsi
0x180003842  mov     eax, r8d
0x180003845  mov     [rbp+0B0h+var_A8], eax
0x180003848  mov     rax, [rbp+0B0h+arg_70]
0x18000384f  mov     [rbp+0B0h+var_C0], rax
0x180003853  mov     rax, [rbp+0B0h+arg_68]
0x18000385a  mov     [rbp+0B0h+var_B0], rcx
0x18000385e  mov     [rbp+0B0h+var_A4], edi
0x180003861  mov     [rbp+0B0h+var_B8], 4
0x180003869  mov     rcx, [rax]
0x18000386c  test    rcx, rcx
0x18000386f  jz      short loc_180003881
0x180003871  mov     rax, rdx
0x180003874  inc     rax
0x180003877  cmp     [rcx+rax], dil
0x18000387b  jnz     short loc_180003874
0x18000387d  inc     eax
0x18000387f  jmp     short loc_180003887
0x180003881  mov     rcx, rsi
0x180003884  mov     eax, r8d
0x180003887  mov     [rbp+0B0h+var_C8], eax
0x18000388a  mov     rax, [rbp+0B0h+arg_60]
0x180003891  mov     [rbp+0B0h+var_E0], rax
0x180003895  mov     rax, [rbp+0B0h+arg_58]
0x18000389c  mov     [rbp+0B0h+var_D0], rcx
0x1800038a0  mov     [rbp+0B0h+var_C4], edi
0x1800038a3  mov     [rbp+0B0h+var_D8], 4
0x1800038ab  mov     rcx, [rax]
0x1800038ae  test    rcx, rcx
0x1800038b1  jz      short loc_1800038C9
0x1800038b3  mov     rax, rdx
0x1800038b6  inc     rax
0x1800038b9  cmp     [rcx+rax*2], di
0x1800038bd  jnz     short loc_1800038B6
0x1800038bf  lea     r9d, ds:2[rax*2]
0x1800038c7  jmp     short loc_1800038D0
0x1800038c9  lea     rcx, dword_180031EE4
0x1800038d0  mov     rax, [rbp+0B0h+arg_50]
0x1800038d7  mov     [rbp+0B0h+var_100], rax
0x1800038db  mov     rax, [rbp+0B0h+arg_48]
0x1800038e2  mov     [rbp+0B0h+var_F0], rcx
0x1800038e6  mov     [rbp+0B0h+var_E8], r9d
0x1800038ea  mov     [rbp+0B0h+var_E4], edi
0x1800038ed  mov     rcx, [rax]
0x1800038f0  mov     [rbp+0B0h+var_F8], 4
0x1800038f8  test    rcx, rcx
0x1800038fb  jz      short loc_18000390D
0x1800038fd  mov     rax, rdx
0x180003900  inc     rax
0x180003903  cmp     [rcx+rax], dil
0x180003907  jnz     short loc_180003900
0x180003909  inc     eax
0x18000390b  jmp     short loc_180003913
0x18000390d  mov     rcx, rsi
0x180003910  mov     eax, r8d
0x180003913  mov     [rbp+0B0h+var_108], eax
0x180003916  mov     rax, [rbp+0B0h+arg_40]
0x18000391d  mov     [rbp+0B0h+var_120], rax
0x180003921  mov     rax, [rbp+0B0h+arg_38]
0x180003928  mov     [rbp+0B0h+var_110], rcx
0x18000392c  mov     [rbp+0B0h+var_104], edi
0x18000392f  mov     [rbp+0B0h+var_118], 4
0x180003937  mov     rcx, [rax]
0x18000393a  test    rcx, rcx
0x18000393d  jz      short loc_18000394E
0x18000393f  inc     rdx
0x180003942  cmp     [rcx+rdx], dil
0x180003946  jnz     short loc_18000393F
0x180003948  lea     r8d, [rdx+1]
0x18000394c  jmp     short loc_180003951
0x18000394e  mov     rcx, rsi
0x180003951  mov     rax, [rbp+0B0h+arg_30]
0x180003958  xor     r9d, r9d
0x18000395b  mov     [rsp+1B0h+var_140], rax
0x180003960  mov     rdx, r11
0x180003963  mov     rax, [rbp+0B0h+arg_28]
0x18000396a  mov     [rsp+1B0h+var_150], rax
0x18000396f  mov     rax, [rbp+0B0h+arg_20]
0x180003976  mov     [rsp+1B0h+var_160], rax
0x18000397b  lea     rax, [rsp+1B0h+var_180]
0x180003980  mov     [rbp+0B0h+var_130], rcx
0x180003984  mov     rcx, r10
0x180003987  mov     [rbp+0B0h+var_128], r8d
0x18000398b  mov     r8, rbx
0x18000398e  mov     [rsp+1B0h+var_188], rax
0x180003993  mov     [rsp+1B0h+var_190], 15h
0x18000399b  mov     [rbp+0B0h+var_124], edi
0x18000399e  mov     [rsp+1B0h+var_138], 4
0x1800039a7  mov     [rsp+1B0h+var_148], 8
0x1800039b0  mov     [rsp+1B0h+var_158], 8
0x1800039b9  call    _tlgWriteTransfer_EventWriteTransfer
0x1800039be  mov     rcx, [rbp+0B0h+var_30]
0x1800039c5  xor     rcx, rsp; StackCookie
0x1800039c8  call    __security_check_cookie
0x1800039cd  add     rsp, 190h
0x1800039d4  pop     r14
0x1800039d6  pop     rdi
0x1800039d7  pop     rsi
0x1800039d8  pop     rbx
0x1800039d9  pop     rbp
0x1800039da  retn
```
