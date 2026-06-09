# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001f6c`
- end: `0x18000229c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U2@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564446@Z`
- size: `816`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, __int64, int **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c5b4`
- `0x18000c8d8`

## callees

- `0x180001ecc`
- `0x180001f6c`
- `0x18001a210`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
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
  int v28; // r9d
  int *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  int v35; // r8d
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
  v99 = 4;
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
0x180001f6c  push    rbp
0x180001f6e  push    rbx
0x180001f6f  push    rsi
0x180001f70  push    rdi
0x180001f71  push    r14
0x180001f73  lea     rbp, [rsp-0A0h]
0x180001f7b  sub     rsp, 1A0h
0x180001f82  mov     rax, cs:__security_cookie
0x180001f89  xor     rax, rsp
0x180001f8c  mov     [rbp+0C0h+var_30], rax
0x180001f93  mov     rax, [rbp+0C0h+arg_B8]
0x180001f9a  mov     r11, rdx
0x180001f9d  mov     r10, rcx
0x180001fa0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001fa4  xor     edi, edi
0x180001fa6  mov     rbx, r8
0x180001fa9  mov     r9d, 2
0x180001faf  mov     rcx, [rax]
0x180001fb2  test    rcx, rcx
0x180001fb5  jz      short loc_180001FCC
0x180001fb7  mov     rax, rdx
0x180001fba  inc     rax
0x180001fbd  cmp     [rcx+rax*2], di
0x180001fc1  jnz     short loc_180001FBA
0x180001fc3  lea     eax, ds:2[rax*2]
0x180001fca  jmp     short loc_180001FD6
0x180001fcc  lea     rcx, dword_18001F7A4
0x180001fd3  mov     eax, r9d
0x180001fd6  mov     [rbp+0C0h+var_38], eax
0x180001fdc  mov     rax, [rbp+0C0h+arg_B0]
0x180001fe3  mov     [rbp+0C0h+var_50], rax
0x180001fe7  mov     rax, [rbp+0C0h+arg_A8]
0x180001fee  mov     [rbp+0C0h+var_60], rax
0x180001ff2  mov     rax, [rbp+0C0h+arg_A0]
0x180001ff9  mov     [rbp+0C0h+var_70], rax
0x180001ffd  mov     rax, [rbp+0C0h+arg_98]
0x180002004  mov     [rbp+0C0h+var_40], rcx
0x18000200b  mov     [rbp+0C0h+var_34], edi
0x180002011  mov     [rbp+0C0h+var_48], 4
0x180002019  mov     rcx, [rax]
0x18000201c  mov     [rbp+0C0h+var_58], 4
0x180002024  mov     [rbp+0C0h+var_68], 4
0x18000202c  test    rcx, rcx
0x18000202f  jz      short loc_180002046
0x180002031  mov     rax, rdx
0x180002034  inc     rax
0x180002037  cmp     [rcx+rax*2], di
0x18000203b  jnz     short loc_180002034
0x18000203d  lea     eax, ds:2[rax*2]
0x180002044  jmp     short loc_180002050
0x180002046  lea     rcx, dword_18001F7A4
0x18000204d  mov     eax, r9d
0x180002050  mov     [rbp+0C0h+var_78], eax
0x180002053  lea     rsi, qword_18001EF80
0x18000205a  mov     rax, [rbp+0C0h+arg_90]
0x180002061  mov     r8d, 1
0x180002067  mov     [rbp+0C0h+var_80], rcx
0x18000206b  mov     [rbp+0C0h+var_74], edi
0x18000206e  mov     rcx, [rax]
0x180002071  test    rcx, rcx
0x180002074  jz      short loc_180002086
0x180002076  mov     rax, rdx
0x180002079  inc     rax
0x18000207c  cmp     [rcx+rax], dil
0x180002080  jnz     short loc_180002079
0x180002082  inc     eax
0x180002084  jmp     short loc_18000208C
0x180002086  mov     rcx, rsi
0x180002089  mov     eax, r8d
0x18000208c  mov     [rbp+0C0h+var_88], eax
0x18000208f  mov     rax, [rbp+0C0h+arg_88]
0x180002096  mov     [rbp+0C0h+var_A0], rax
0x18000209a  mov     rax, [rbp+0C0h+arg_80]
0x1800020a1  mov     [rbp+0C0h+var_90], rcx
0x1800020a5  mov     [rbp+0C0h+var_84], edi
0x1800020a8  mov     [rbp+0C0h+var_98], 4
0x1800020b0  mov     rcx, [rax]
0x1800020b3  test    rcx, rcx
0x1800020b6  jz      short loc_1800020CD
0x1800020b8  mov     rax, rdx
0x1800020bb  inc     rax
0x1800020be  cmp     [rcx+rax*2], di
0x1800020c2  jnz     short loc_1800020BB
0x1800020c4  lea     eax, ds:2[rax*2]
0x1800020cb  jmp     short loc_1800020D7
0x1800020cd  lea     rcx, dword_18001F7A4
0x1800020d4  mov     eax, r9d
0x1800020d7  mov     [rbp+0C0h+var_A8], eax
0x1800020da  mov     rax, [rbp+0C0h+arg_78]
0x1800020e1  mov     [rbp+0C0h+var_B0], rcx
0x1800020e5  mov     [rbp+0C0h+var_A4], edi
0x1800020e8  mov     rcx, [rax]
0x1800020eb  test    rcx, rcx
0x1800020ee  jz      short loc_180002100
0x1800020f0  mov     rax, rdx
0x1800020f3  inc     rax
0x1800020f6  cmp     [rcx+rax], dil
0x1800020fa  jnz     short loc_1800020F3
0x1800020fc  inc     eax
0x1800020fe  jmp     short loc_180002106
0x180002100  mov     rcx, rsi
0x180002103  mov     eax, r8d
0x180002106  mov     [rbp+0C0h+var_B8], eax
0x180002109  mov     rax, [rbp+0C0h+arg_70]
0x180002110  mov     [rbp+0C0h+var_D0], rax
0x180002114  mov     rax, [rbp+0C0h+arg_68]
0x18000211b  mov     [rbp+0C0h+var_C0], rcx
0x18000211f  mov     [rbp+0C0h+var_B4], edi
0x180002122  mov     [rbp+0C0h+var_C8], 4
0x18000212a  mov     rcx, [rax]
0x18000212d  test    rcx, rcx
0x180002130  jz      short loc_180002142
0x180002132  mov     rax, rdx
0x180002135  inc     rax
0x180002138  cmp     [rcx+rax], dil
0x18000213c  jnz     short loc_180002135
0x18000213e  inc     eax
0x180002140  jmp     short loc_180002148
0x180002142  mov     rcx, rsi
0x180002145  mov     eax, r8d
0x180002148  mov     [rbp+0C0h+var_D8], eax
0x18000214b  mov     rax, [rbp+0C0h+arg_60]
0x180002152  mov     [rbp+0C0h+var_F0], rax
0x180002156  mov     rax, [rbp+0C0h+arg_58]
0x18000215d  mov     [rbp+0C0h+var_E0], rcx
0x180002161  mov     [rbp+0C0h+var_D4], edi
0x180002164  mov     [rbp+0C0h+var_E8], 4
0x18000216c  mov     rcx, [rax]
0x18000216f  test    rcx, rcx
0x180002172  jz      short loc_18000218A
0x180002174  mov     rax, rdx
0x180002177  inc     rax
0x18000217a  cmp     [rcx+rax*2], di
0x18000217e  jnz     short loc_180002177
0x180002180  lea     r9d, ds:2[rax*2]
0x180002188  jmp     short loc_180002191
0x18000218a  lea     rcx, dword_18001F7A4
0x180002191  mov     rax, [rbp+0C0h+arg_50]
0x180002198  mov     [rbp+0C0h+var_110], rax
0x18000219c  mov     rax, [rbp+0C0h+arg_48]
0x1800021a3  mov     [rbp+0C0h+var_100], rcx
0x1800021a7  mov     [rbp+0C0h+var_F8], r9d
0x1800021ab  mov     [rbp+0C0h+var_F4], edi
0x1800021ae  mov     rcx, [rax]
0x1800021b1  mov     [rbp+0C0h+var_108], 4
0x1800021b9  test    rcx, rcx
0x1800021bc  jz      short loc_1800021CE
0x1800021be  mov     rax, rdx
0x1800021c1  inc     rax
0x1800021c4  cmp     [rcx+rax], dil
0x1800021c8  jnz     short loc_1800021C1
0x1800021ca  inc     eax
0x1800021cc  jmp     short loc_1800021D4
0x1800021ce  mov     rcx, rsi
0x1800021d1  mov     eax, r8d
0x1800021d4  mov     [rbp+0C0h+var_118], eax
0x1800021d7  mov     rax, [rbp+0C0h+arg_40]
0x1800021de  mov     [rbp+0C0h+var_130], rax
0x1800021e2  mov     rax, [rbp+0C0h+arg_38]
0x1800021e9  mov     [rbp+0C0h+var_120], rcx
0x1800021ed  mov     [rbp+0C0h+var_114], edi
0x1800021f0  mov     [rbp+0C0h+var_128], 4
0x1800021f8  mov     rcx, [rax]
0x1800021fb  test    rcx, rcx
0x1800021fe  jz      short loc_18000220F
0x180002200  inc     rdx
0x180002203  cmp     [rcx+rdx], dil
0x180002207  jnz     short loc_180002200
0x180002209  lea     r8d, [rdx+1]
0x18000220d  jmp     short loc_180002212
0x18000220f  mov     rcx, rsi
0x180002212  mov     rax, [rbp+0C0h+arg_30]
0x180002219  xor     r9d, r9d
0x18000221c  mov     [rsp+1C0h+var_150], rax
0x180002221  mov     rdx, r11
0x180002224  mov     rax, [rbp+0C0h+arg_28]
0x18000222b  mov     [rsp+1C0h+var_160], rax
0x180002230  mov     rax, [rbp+0C0h+arg_20]
0x180002237  mov     [rsp+1C0h+var_170], rax
0x18000223c  lea     rax, [rsp+1C0h+var_190]
0x180002241  mov     [rbp+0C0h+var_140], rcx
0x180002245  mov     rcx, r10
0x180002248  mov     [rbp+0C0h+var_138], r8d
0x18000224c  mov     r8, rbx
0x18000224f  mov     [rsp+1C0h+var_198], rax
0x180002254  mov     [rsp+1C0h+var_1A0], 16h
0x18000225c  mov     [rbp+0C0h+var_134], edi
0x18000225f  mov     [rsp+1C0h+var_148], 4
0x180002268  mov     [rsp+1C0h+var_158], 8
0x180002271  mov     [rsp+1C0h+var_168], 8
0x18000227a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000227f  mov     rcx, [rbp+0C0h+var_30]
0x180002286  xor     rcx, rsp; StackCookie
0x180002289  call    __security_check_cookie
0x18000228e  add     rsp, 1A0h
0x180002295  pop     r14
0x180002297  pop     rdi
0x180002298  pop     rsi
0x180002299  pop     rbx
0x18000229a  pop     rbp
0x18000229b  retn
```
