# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001594`
- end: `0x1800018a8`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456446@Z`
- size: `788`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007788`

## callees

- `0x180001594`
- `0x180001ecc`
- `0x18001a210`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
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
        int **a23)
{
  __int64 v25; // rdx
  int v27; // r9d
  int *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  int v34; // r8d
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
  _BYTE v54[32]; // [rsp+30h] [rbp-D0h] BYREF
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
  int *v99; // [rsp+170h] [rbp+70h]
  int v100; // [rsp+178h] [rbp+78h]
  int v101; // [rsp+17Ch] [rbp+7Ch]

  v25 = -1;
  v27 = 2;
  v28 = *a23;
  if ( *a23 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_WORD *)v28 + v29) );
    v30 = 2 * v29 + 2;
  }
  else
  {
    v28 = &dword_18001F7A4;
    v30 = 2;
  }
  v100 = v30;
  v97 = a22;
  v95 = a21;
  v99 = v28;
  v101 = 0;
  v98 = 4;
  v31 = *a20;
  v96 = 4;
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
    v31 = &dword_18001F7A4;
    v33 = 2;
  }
  v93 = v33;
  v34 = 1;
  v92 = v31;
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
    v35 = &qword_18001EF80;
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
    v38 = &dword_18001F7A4;
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
    v41 = &qword_18001EF80;
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
    v44 = &qword_18001EF80;
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
    v27 = 2 * v48 + 2;
  }
  else
  {
    v47 = &dword_18001F7A4;
  }
  v69 = a11;
  v71 = v47;
  v72 = v27;
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
    v49 = &qword_18001EF80;
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
    v34 = v25 + 1;
  }
  else
  {
    v52 = &qword_18001EF80;
  }
  v59 = a7;
  v57 = a6;
  v55 = a5;
  v61 = v52;
  v62 = v34;
  v63 = 0;
  v60 = 4;
  v58 = 8;
  v56 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 21, v54);
}

```

## disassembly

```asm
0x180001594  push    rbp
0x180001596  push    rbx
0x180001597  push    rsi
0x180001598  push    rdi
0x180001599  push    r14
0x18000159b  lea     rbp, [rsp-90h]
0x1800015a3  sub     rsp, 190h
0x1800015aa  mov     rax, cs:__security_cookie
0x1800015b1  xor     rax, rsp
0x1800015b4  mov     [rbp+0B0h+var_30], rax
0x1800015bb  mov     rax, [rbp+0B0h+arg_B0]
0x1800015c2  mov     r11, rdx
0x1800015c5  mov     r10, rcx
0x1800015c8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800015cc  xor     edi, edi
0x1800015ce  mov     rbx, r8
0x1800015d1  mov     r9d, 2
0x1800015d7  mov     rcx, [rax]
0x1800015da  test    rcx, rcx
0x1800015dd  jz      short loc_1800015F4
0x1800015df  mov     rax, rdx
0x1800015e2  inc     rax
0x1800015e5  cmp     [rcx+rax*2], di
0x1800015e9  jnz     short loc_1800015E2
0x1800015eb  lea     eax, ds:2[rax*2]
0x1800015f2  jmp     short loc_1800015FE
0x1800015f4  lea     rcx, dword_18001F7A4
0x1800015fb  mov     eax, r9d
0x1800015fe  mov     [rbp+0B0h+var_38], eax
0x180001601  mov     rax, [rbp+0B0h+arg_A8]
0x180001608  mov     [rbp+0B0h+var_50], rax
0x18000160c  mov     rax, [rbp+0B0h+arg_A0]
0x180001613  mov     [rbp+0B0h+var_60], rax
0x180001617  mov     rax, [rbp+0B0h+arg_98]
0x18000161e  mov     [rbp+0B0h+var_40], rcx
0x180001622  mov     [rbp+0B0h+var_34], edi
0x180001625  mov     [rbp+0B0h+var_48], 4
0x18000162d  mov     rcx, [rax]
0x180001630  mov     [rbp+0B0h+var_58], 4
0x180001638  test    rcx, rcx
0x18000163b  jz      short loc_180001652
0x18000163d  mov     rax, rdx
0x180001640  inc     rax
0x180001643  cmp     [rcx+rax*2], di
0x180001647  jnz     short loc_180001640
0x180001649  lea     eax, ds:2[rax*2]
0x180001650  jmp     short loc_18000165C
0x180001652  lea     rcx, dword_18001F7A4
0x180001659  mov     eax, r9d
0x18000165c  mov     [rbp+0B0h+var_68], eax
0x18000165f  lea     rsi, qword_18001EF80
0x180001666  mov     rax, [rbp+0B0h+arg_90]
0x18000166d  mov     r8d, 1
0x180001673  mov     [rbp+0B0h+var_70], rcx
0x180001677  mov     [rbp+0B0h+var_64], edi
0x18000167a  mov     rcx, [rax]
0x18000167d  test    rcx, rcx
0x180001680  jz      short loc_180001692
0x180001682  mov     rax, rdx
0x180001685  inc     rax
0x180001688  cmp     [rcx+rax], dil
0x18000168c  jnz     short loc_180001685
0x18000168e  inc     eax
0x180001690  jmp     short loc_180001698
0x180001692  mov     rcx, rsi
0x180001695  mov     eax, r8d
0x180001698  mov     [rbp+0B0h+var_78], eax
0x18000169b  mov     rax, [rbp+0B0h+arg_88]
0x1800016a2  mov     [rbp+0B0h+var_90], rax
0x1800016a6  mov     rax, [rbp+0B0h+arg_80]
0x1800016ad  mov     [rbp+0B0h+var_80], rcx
0x1800016b1  mov     [rbp+0B0h+var_74], edi
0x1800016b4  mov     [rbp+0B0h+var_88], 4
0x1800016bc  mov     rcx, [rax]
0x1800016bf  test    rcx, rcx
0x1800016c2  jz      short loc_1800016D9
0x1800016c4  mov     rax, rdx
0x1800016c7  inc     rax
0x1800016ca  cmp     [rcx+rax*2], di
0x1800016ce  jnz     short loc_1800016C7
0x1800016d0  lea     eax, ds:2[rax*2]
0x1800016d7  jmp     short loc_1800016E3
0x1800016d9  lea     rcx, dword_18001F7A4
0x1800016e0  mov     eax, r9d
0x1800016e3  mov     [rbp+0B0h+var_98], eax
0x1800016e6  mov     rax, [rbp+0B0h+arg_78]
0x1800016ed  mov     [rbp+0B0h+var_A0], rcx
0x1800016f1  mov     [rbp+0B0h+var_94], edi
0x1800016f4  mov     rcx, [rax]
0x1800016f7  test    rcx, rcx
0x1800016fa  jz      short loc_18000170C
0x1800016fc  mov     rax, rdx
0x1800016ff  inc     rax
0x180001702  cmp     [rcx+rax], dil
0x180001706  jnz     short loc_1800016FF
0x180001708  inc     eax
0x18000170a  jmp     short loc_180001712
0x18000170c  mov     rcx, rsi
0x18000170f  mov     eax, r8d
0x180001712  mov     [rbp+0B0h+var_A8], eax
0x180001715  mov     rax, [rbp+0B0h+arg_70]
0x18000171c  mov     [rbp+0B0h+var_C0], rax
0x180001720  mov     rax, [rbp+0B0h+arg_68]
0x180001727  mov     [rbp+0B0h+var_B0], rcx
0x18000172b  mov     [rbp+0B0h+var_A4], edi
0x18000172e  mov     [rbp+0B0h+var_B8], 4
0x180001736  mov     rcx, [rax]
0x180001739  test    rcx, rcx
0x18000173c  jz      short loc_18000174E
0x18000173e  mov     rax, rdx
0x180001741  inc     rax
0x180001744  cmp     [rcx+rax], dil
0x180001748  jnz     short loc_180001741
0x18000174a  inc     eax
0x18000174c  jmp     short loc_180001754
0x18000174e  mov     rcx, rsi
0x180001751  mov     eax, r8d
0x180001754  mov     [rbp+0B0h+var_C8], eax
0x180001757  mov     rax, [rbp+0B0h+arg_60]
0x18000175e  mov     [rbp+0B0h+var_E0], rax
0x180001762  mov     rax, [rbp+0B0h+arg_58]
0x180001769  mov     [rbp+0B0h+var_D0], rcx
0x18000176d  mov     [rbp+0B0h+var_C4], edi
0x180001770  mov     [rbp+0B0h+var_D8], 4
0x180001778  mov     rcx, [rax]
0x18000177b  test    rcx, rcx
0x18000177e  jz      short loc_180001796
0x180001780  mov     rax, rdx
0x180001783  inc     rax
0x180001786  cmp     [rcx+rax*2], di
0x18000178a  jnz     short loc_180001783
0x18000178c  lea     r9d, ds:2[rax*2]
0x180001794  jmp     short loc_18000179D
0x180001796  lea     rcx, dword_18001F7A4
0x18000179d  mov     rax, [rbp+0B0h+arg_50]
0x1800017a4  mov     [rbp+0B0h+var_100], rax
0x1800017a8  mov     rax, [rbp+0B0h+arg_48]
0x1800017af  mov     [rbp+0B0h+var_F0], rcx
0x1800017b3  mov     [rbp+0B0h+var_E8], r9d
0x1800017b7  mov     [rbp+0B0h+var_E4], edi
0x1800017ba  mov     rcx, [rax]
0x1800017bd  mov     [rbp+0B0h+var_F8], 4
0x1800017c5  test    rcx, rcx
0x1800017c8  jz      short loc_1800017DA
0x1800017ca  mov     rax, rdx
0x1800017cd  inc     rax
0x1800017d0  cmp     [rcx+rax], dil
0x1800017d4  jnz     short loc_1800017CD
0x1800017d6  inc     eax
0x1800017d8  jmp     short loc_1800017E0
0x1800017da  mov     rcx, rsi
0x1800017dd  mov     eax, r8d
0x1800017e0  mov     [rbp+0B0h+var_108], eax
0x1800017e3  mov     rax, [rbp+0B0h+arg_40]
0x1800017ea  mov     [rbp+0B0h+var_120], rax
0x1800017ee  mov     rax, [rbp+0B0h+arg_38]
0x1800017f5  mov     [rbp+0B0h+var_110], rcx
0x1800017f9  mov     [rbp+0B0h+var_104], edi
0x1800017fc  mov     [rbp+0B0h+var_118], 4
0x180001804  mov     rcx, [rax]
0x180001807  test    rcx, rcx
0x18000180a  jz      short loc_18000181B
0x18000180c  inc     rdx
0x18000180f  cmp     [rcx+rdx], dil
0x180001813  jnz     short loc_18000180C
0x180001815  lea     r8d, [rdx+1]
0x180001819  jmp     short loc_18000181E
0x18000181b  mov     rcx, rsi
0x18000181e  mov     rax, [rbp+0B0h+arg_30]
0x180001825  xor     r9d, r9d
0x180001828  mov     [rsp+1B0h+var_140], rax
0x18000182d  mov     rdx, r11
0x180001830  mov     rax, [rbp+0B0h+arg_28]
0x180001837  mov     [rsp+1B0h+var_150], rax
0x18000183c  mov     rax, [rbp+0B0h+arg_20]
0x180001843  mov     [rsp+1B0h+var_160], rax
0x180001848  lea     rax, [rsp+1B0h+var_180]
0x18000184d  mov     [rbp+0B0h+var_130], rcx
0x180001851  mov     rcx, r10
0x180001854  mov     [rbp+0B0h+var_128], r8d
0x180001858  mov     r8, rbx
0x18000185b  mov     [rsp+1B0h+var_188], rax
0x180001860  mov     [rsp+1B0h+var_190], 15h
0x180001868  mov     [rbp+0B0h+var_124], edi
0x18000186b  mov     [rsp+1B0h+var_138], 4
0x180001874  mov     [rsp+1B0h+var_148], 8
0x18000187d  mov     [rsp+1B0h+var_158], 8
0x180001886  call    _tlgWriteTransfer_EventWriteTransfer
0x18000188b  mov     rcx, [rbp+0B0h+var_30]
0x180001892  xor     rcx, rsp; StackCookie
0x180001895  call    __security_check_cookie
0x18000189a  add     rsp, 190h
0x1800018a1  pop     r14
0x1800018a3  pop     rdi
0x1800018a4  pop     rsi
0x1800018a5  pop     rbx
0x1800018a6  pop     rbp
0x1800018a7  retn
```
