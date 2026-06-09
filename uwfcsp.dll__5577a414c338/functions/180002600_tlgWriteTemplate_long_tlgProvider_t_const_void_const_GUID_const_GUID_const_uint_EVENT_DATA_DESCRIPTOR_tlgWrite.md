# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180002600`
- end: `0x18000292c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U?$_tlgWrapperByVal@$01@@U2@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564AEBU?$_tlgWrapperByVal@$01@@46@Z`
- size: `812`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, __int64, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c1ec`

## callees

- `0x180001ecc`
- `0x180002600`
- `0x18001a210`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
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
        __int64 a22,
        __int64 a23,
        int **a24)
{
  __int64 v26; // rdx
  int v28; // r8d
  int *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  int v35; // r9d
  const unsigned __int16 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  int *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  int *v48; // rcx
  __int64 v49; // rax
  const unsigned __int16 *v50; // rcx
  __int64 v51; // rax
  int v52; // eax
  const unsigned __int16 *v53; // rcx
  _BYTE v55[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v56; // [rsp+50h] [rbp-B0h]
  __int64 v57; // [rsp+58h] [rbp-A8h]
  __int64 v58; // [rsp+60h] [rbp-A0h]
  __int64 v59; // [rsp+68h] [rbp-98h]
  __int64 v60; // [rsp+70h] [rbp-90h]
  __int64 v61; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v62; // [rsp+80h] [rbp-80h]
  int v63; // [rsp+88h] [rbp-78h]
  int v64; // [rsp+8Ch] [rbp-74h]
  __int64 v65; // [rsp+90h] [rbp-70h]
  __int64 v66; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v67; // [rsp+A0h] [rbp-60h]
  int v68; // [rsp+A8h] [rbp-58h]
  int v69; // [rsp+ACh] [rbp-54h]
  __int64 v70; // [rsp+B0h] [rbp-50h]
  __int64 v71; // [rsp+B8h] [rbp-48h]
  int *v72; // [rsp+C0h] [rbp-40h]
  int v73; // [rsp+C8h] [rbp-38h]
  int v74; // [rsp+CCh] [rbp-34h]
  __int64 v75; // [rsp+D0h] [rbp-30h]
  __int64 v76; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v77; // [rsp+E0h] [rbp-20h]
  int v78; // [rsp+E8h] [rbp-18h]
  int v79; // [rsp+ECh] [rbp-14h]
  __int64 v80; // [rsp+F0h] [rbp-10h]
  __int64 v81; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v82; // [rsp+100h] [rbp+0h]
  int v83; // [rsp+108h] [rbp+8h]
  int v84; // [rsp+10Ch] [rbp+Ch]
  int *v85; // [rsp+110h] [rbp+10h]
  int v86; // [rsp+118h] [rbp+18h]
  int v87; // [rsp+11Ch] [rbp+1Ch]
  __int64 v88; // [rsp+120h] [rbp+20h]
  __int64 v89; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v90; // [rsp+130h] [rbp+30h]
  int v91; // [rsp+138h] [rbp+38h]
  int v92; // [rsp+13Ch] [rbp+3Ch]
  int *v93; // [rsp+140h] [rbp+40h]
  int v94; // [rsp+148h] [rbp+48h]
  int v95; // [rsp+14Ch] [rbp+4Ch]
  __int64 v96; // [rsp+150h] [rbp+50h]
  __int64 v97; // [rsp+158h] [rbp+58h]
  __int64 v98; // [rsp+160h] [rbp+60h]
  __int64 v99; // [rsp+168h] [rbp+68h]
  __int64 v100; // [rsp+170h] [rbp+70h]
  __int64 v101; // [rsp+178h] [rbp+78h]
  int *v102; // [rsp+180h] [rbp+80h]
  int v103; // [rsp+188h] [rbp+88h]
  int v104; // [rsp+18Ch] [rbp+8Ch]

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
  v103 = v31;
  v100 = a23;
  v98 = a22;
  v96 = a21;
  v102 = v29;
  v104 = 0;
  v101 = 4;
  v32 = *a20;
  v99 = 2;
  v97 = 4;
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
    v32 = &dword_18001F7A4;
    v34 = 2;
  }
  v94 = v34;
  v35 = 1;
  v93 = v32;
  v95 = 0;
  v36 = *a19;
  if ( *a19 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &qword_18001EF80;
    v38 = 1;
  }
  v91 = v38;
  v88 = a18;
  v90 = v36;
  v92 = 0;
  v89 = 4;
  v39 = *a17;
  if ( *a17 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_WORD *)v39 + v40) );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v39 = &dword_18001F7A4;
    v41 = 2;
  }
  v86 = v41;
  v85 = v39;
  v87 = 0;
  v42 = *a16;
  if ( *a16 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &qword_18001EF80;
    v44 = 1;
  }
  v83 = v44;
  v80 = a15;
  v82 = v42;
  v84 = 0;
  v81 = 4;
  v45 = *a14;
  if ( *a14 )
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
  v78 = v47;
  v75 = a13;
  v77 = v45;
  v79 = 0;
  v76 = 4;
  v48 = *a12;
  if ( *a12 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_WORD *)v48 + v49) );
    v28 = 2 * v49 + 2;
  }
  else
  {
    v48 = &dword_18001F7A4;
  }
  v70 = a11;
  v72 = v48;
  v73 = v28;
  v74 = 0;
  v50 = *a10;
  v71 = 4;
  if ( v50 )
  {
    v51 = -1;
    do
      ++v51;
    while ( *((_BYTE *)v50 + v51) );
    v52 = v51 + 1;
  }
  else
  {
    v50 = &qword_18001EF80;
    v52 = 1;
  }
  v68 = v52;
  v65 = a9;
  v67 = v50;
  v69 = 0;
  v66 = 4;
  v53 = *a8;
  if ( *a8 )
  {
    do
      ++v26;
    while ( *((_BYTE *)v53 + v26) );
    v35 = v26 + 1;
  }
  else
  {
    v53 = &qword_18001EF80;
  }
  v60 = a7;
  v58 = a6;
  v56 = a5;
  v62 = v53;
  v63 = v35;
  v64 = 0;
  v61 = 4;
  v59 = 8;
  v57 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 22, v55);
}

```

## disassembly

```asm
0x180002600  push    rbp
0x180002602  push    rbx
0x180002603  push    rsi
0x180002604  push    rdi
0x180002605  push    r15
0x180002607  lea     rbp, [rsp-0A0h]
0x18000260f  sub     rsp, 1A0h
0x180002616  mov     rax, cs:__security_cookie
0x18000261d  xor     rax, rsp
0x180002620  mov     [rbp+0C0h+var_30], rax
0x180002627  mov     rax, [rbp+0C0h+arg_B8]
0x18000262e  mov     r11, rdx
0x180002631  mov     r10, rcx
0x180002634  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180002638  xor     edi, edi
0x18000263a  mov     rbx, r8
0x18000263d  mov     r8d, 2
0x180002643  mov     rcx, [rax]
0x180002646  test    rcx, rcx
0x180002649  jz      short loc_180002660
0x18000264b  mov     rax, rdx
0x18000264e  inc     rax
0x180002651  cmp     [rcx+rax*2], di
0x180002655  jnz     short loc_18000264E
0x180002657  lea     eax, ds:2[rax*2]
0x18000265e  jmp     short loc_18000266A
0x180002660  lea     rcx, dword_18001F7A4
0x180002667  mov     eax, r8d
0x18000266a  mov     [rbp+0C0h+var_38], eax
0x180002670  mov     rax, [rbp+0C0h+arg_B0]
0x180002677  mov     [rbp+0C0h+var_50], rax
0x18000267b  mov     rax, [rbp+0C0h+arg_A8]
0x180002682  mov     [rbp+0C0h+var_60], rax
0x180002686  mov     rax, [rbp+0C0h+arg_A0]
0x18000268d  mov     [rbp+0C0h+var_70], rax
0x180002691  mov     rax, [rbp+0C0h+arg_98]
0x180002698  mov     [rbp+0C0h+var_40], rcx
0x18000269f  mov     [rbp+0C0h+var_34], edi
0x1800026a5  mov     [rbp+0C0h+var_48], 4
0x1800026ad  mov     rcx, [rax]
0x1800026b0  mov     [rbp+0C0h+var_58], r8
0x1800026b4  mov     [rbp+0C0h+var_68], 4
0x1800026bc  test    rcx, rcx
0x1800026bf  jz      short loc_1800026D6
0x1800026c1  mov     rax, rdx
0x1800026c4  inc     rax
0x1800026c7  cmp     [rcx+rax*2], di
0x1800026cb  jnz     short loc_1800026C4
0x1800026cd  lea     eax, ds:2[rax*2]
0x1800026d4  jmp     short loc_1800026E0
0x1800026d6  lea     rcx, dword_18001F7A4
0x1800026dd  mov     eax, r8d
0x1800026e0  mov     [rbp+0C0h+var_78], eax
0x1800026e3  lea     rsi, qword_18001EF80
0x1800026ea  mov     rax, [rbp+0C0h+arg_90]
0x1800026f1  mov     r9d, 1
0x1800026f7  mov     [rbp+0C0h+var_80], rcx
0x1800026fb  mov     [rbp+0C0h+var_74], edi
0x1800026fe  mov     rcx, [rax]
0x180002701  test    rcx, rcx
0x180002704  jz      short loc_180002716
0x180002706  mov     rax, rdx
0x180002709  inc     rax
0x18000270c  cmp     [rcx+rax], dil
0x180002710  jnz     short loc_180002709
0x180002712  inc     eax
0x180002714  jmp     short loc_18000271C
0x180002716  mov     rcx, rsi
0x180002719  mov     eax, r9d
0x18000271c  mov     [rbp+0C0h+var_88], eax
0x18000271f  mov     rax, [rbp+0C0h+arg_88]
0x180002726  mov     [rbp+0C0h+var_A0], rax
0x18000272a  mov     rax, [rbp+0C0h+arg_80]
0x180002731  mov     [rbp+0C0h+var_90], rcx
0x180002735  mov     [rbp+0C0h+var_84], edi
0x180002738  mov     [rbp+0C0h+var_98], 4
0x180002740  mov     rcx, [rax]
0x180002743  test    rcx, rcx
0x180002746  jz      short loc_18000275D
0x180002748  mov     rax, rdx
0x18000274b  inc     rax
0x18000274e  cmp     [rcx+rax*2], di
0x180002752  jnz     short loc_18000274B
0x180002754  lea     eax, ds:2[rax*2]
0x18000275b  jmp     short loc_180002767
0x18000275d  lea     rcx, dword_18001F7A4
0x180002764  mov     eax, r8d
0x180002767  mov     [rbp+0C0h+var_A8], eax
0x18000276a  mov     rax, [rbp+0C0h+arg_78]
0x180002771  mov     [rbp+0C0h+var_B0], rcx
0x180002775  mov     [rbp+0C0h+var_A4], edi
0x180002778  mov     rcx, [rax]
0x18000277b  test    rcx, rcx
0x18000277e  jz      short loc_180002790
0x180002780  mov     rax, rdx
0x180002783  inc     rax
0x180002786  cmp     [rcx+rax], dil
0x18000278a  jnz     short loc_180002783
0x18000278c  inc     eax
0x18000278e  jmp     short loc_180002796
0x180002790  mov     rcx, rsi
0x180002793  mov     eax, r9d
0x180002796  mov     [rbp+0C0h+var_B8], eax
0x180002799  mov     rax, [rbp+0C0h+arg_70]
0x1800027a0  mov     [rbp+0C0h+var_D0], rax
0x1800027a4  mov     rax, [rbp+0C0h+arg_68]
0x1800027ab  mov     [rbp+0C0h+var_C0], rcx
0x1800027af  mov     [rbp+0C0h+var_B4], edi
0x1800027b2  mov     [rbp+0C0h+var_C8], 4
0x1800027ba  mov     rcx, [rax]
0x1800027bd  test    rcx, rcx
0x1800027c0  jz      short loc_1800027D2
0x1800027c2  mov     rax, rdx
0x1800027c5  inc     rax
0x1800027c8  cmp     [rcx+rax], dil
0x1800027cc  jnz     short loc_1800027C5
0x1800027ce  inc     eax
0x1800027d0  jmp     short loc_1800027D8
0x1800027d2  mov     rcx, rsi
0x1800027d5  mov     eax, r9d
0x1800027d8  mov     [rbp+0C0h+var_D8], eax
0x1800027db  mov     rax, [rbp+0C0h+arg_60]
0x1800027e2  mov     [rbp+0C0h+var_F0], rax
0x1800027e6  mov     rax, [rbp+0C0h+arg_58]
0x1800027ed  mov     [rbp+0C0h+var_E0], rcx
0x1800027f1  mov     [rbp+0C0h+var_D4], edi
0x1800027f4  mov     [rbp+0C0h+var_E8], 4
0x1800027fc  mov     rcx, [rax]
0x1800027ff  test    rcx, rcx
0x180002802  jz      short loc_18000281A
0x180002804  mov     rax, rdx
0x180002807  inc     rax
0x18000280a  cmp     [rcx+rax*2], di
0x18000280e  jnz     short loc_180002807
0x180002810  lea     r8d, ds:2[rax*2]
0x180002818  jmp     short loc_180002821
0x18000281a  lea     rcx, dword_18001F7A4
0x180002821  mov     rax, [rbp+0C0h+arg_50]
0x180002828  mov     [rbp+0C0h+var_110], rax
0x18000282c  mov     rax, [rbp+0C0h+arg_48]
0x180002833  mov     [rbp+0C0h+var_100], rcx
0x180002837  mov     [rbp+0C0h+var_F8], r8d
0x18000283b  mov     [rbp+0C0h+var_F4], edi
0x18000283e  mov     rcx, [rax]
0x180002841  mov     [rbp+0C0h+var_108], 4
0x180002849  test    rcx, rcx
0x18000284c  jz      short loc_18000285E
0x18000284e  mov     rax, rdx
0x180002851  inc     rax
0x180002854  cmp     [rcx+rax], dil
0x180002858  jnz     short loc_180002851
0x18000285a  inc     eax
0x18000285c  jmp     short loc_180002864
0x18000285e  mov     rcx, rsi
0x180002861  mov     eax, r9d
0x180002864  mov     [rbp+0C0h+var_118], eax
0x180002867  mov     rax, [rbp+0C0h+arg_40]
0x18000286e  mov     [rbp+0C0h+var_130], rax
0x180002872  mov     rax, [rbp+0C0h+arg_38]
0x180002879  mov     [rbp+0C0h+var_120], rcx
0x18000287d  mov     [rbp+0C0h+var_114], edi
0x180002880  mov     [rbp+0C0h+var_128], 4
0x180002888  mov     rcx, [rax]
0x18000288b  test    rcx, rcx
0x18000288e  jz      short loc_18000289F
0x180002890  inc     rdx
0x180002893  cmp     [rcx+rdx], dil
0x180002897  jnz     short loc_180002890
0x180002899  lea     r9d, [rdx+1]
0x18000289d  jmp     short loc_1800028A2
0x18000289f  mov     rcx, rsi
0x1800028a2  mov     rax, [rbp+0C0h+arg_30]
0x1800028a9  mov     r8, rbx
0x1800028ac  mov     [rsp+1C0h+var_150], rax
0x1800028b1  mov     rdx, r11
0x1800028b4  mov     rax, [rbp+0C0h+arg_28]
0x1800028bb  mov     [rsp+1C0h+var_160], rax
0x1800028c0  mov     rax, [rbp+0C0h+arg_20]
0x1800028c7  mov     [rsp+1C0h+var_170], rax
0x1800028cc  lea     rax, [rsp+1C0h+var_190]
0x1800028d1  mov     [rbp+0C0h+var_140], rcx
0x1800028d5  mov     rcx, r10
0x1800028d8  mov     [rbp+0C0h+var_138], r9d
0x1800028dc  xor     r9d, r9d
0x1800028df  mov     [rsp+1C0h+var_198], rax
0x1800028e4  mov     [rsp+1C0h+var_1A0], 16h
0x1800028ec  mov     [rbp+0C0h+var_134], edi
0x1800028ef  mov     [rsp+1C0h+var_148], 4
0x1800028f8  mov     [rsp+1C0h+var_158], 8
0x180002901  mov     [rsp+1C0h+var_168], 8
0x18000290a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000290f  mov     rcx, [rbp+0C0h+var_30]
0x180002916  xor     rcx, rsp; StackCookie
0x180002919  call    __security_check_cookie
0x18000291e  add     rsp, 1A0h
0x180002925  pop     r15
0x180002927  pop     rdi
0x180002928  pop     rsi
0x180002929  pop     rbx
0x18000292a  pop     rbp
0x18000292b  retn
```
