# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001008`
- end: `0x180001313`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `779`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180026140`
- `0x180026380`
- `0x1800265c0`
- `0x180026800`

## callees

- `0x180001008`
- `0x1800018c8`
- `0x18002a590`

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
        const CHAR **a8,
        __int64 a9,
        const CHAR **a10,
        __int64 a11,
        int **a12,
        __int64 a13,
        const CHAR **a14,
        __int64 a15,
        const CHAR **a16,
        int **a17,
        __int64 a18,
        const CHAR **a19,
        int **a20,
        __int64 a21,
        __int64 a22,
        const CHAR **a23)
{
  __int64 v25; // rdx
  int v27; // r8d
  const CHAR *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int v31; // r9d
  int *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const CHAR *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  int *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  const CHAR *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  const CHAR *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  int *v47; // rcx
  __int64 v48; // rax
  const CHAR *v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  const CHAR *v52; // rcx
  struct _EVENT_DATA_DESCRIPTOR v54; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B0h]
  __int64 v56; // [rsp+58h] [rbp-A8h]
  __int64 v57; // [rsp+60h] [rbp-A0h]
  __int64 v58; // [rsp+68h] [rbp-98h]
  __int64 v59; // [rsp+70h] [rbp-90h]
  __int64 v60; // [rsp+78h] [rbp-88h]
  const CHAR *v61; // [rsp+80h] [rbp-80h]
  int v62; // [rsp+88h] [rbp-78h]
  int v63; // [rsp+8Ch] [rbp-74h]
  __int64 v64; // [rsp+90h] [rbp-70h]
  __int64 v65; // [rsp+98h] [rbp-68h]
  const CHAR *v66; // [rsp+A0h] [rbp-60h]
  int v67; // [rsp+A8h] [rbp-58h]
  int v68; // [rsp+ACh] [rbp-54h]
  __int64 v69; // [rsp+B0h] [rbp-50h]
  __int64 v70; // [rsp+B8h] [rbp-48h]
  int *v71; // [rsp+C0h] [rbp-40h]
  int v72; // [rsp+C8h] [rbp-38h]
  int v73; // [rsp+CCh] [rbp-34h]
  __int64 v74; // [rsp+D0h] [rbp-30h]
  __int64 v75; // [rsp+D8h] [rbp-28h]
  const CHAR *v76; // [rsp+E0h] [rbp-20h]
  int v77; // [rsp+E8h] [rbp-18h]
  int v78; // [rsp+ECh] [rbp-14h]
  __int64 v79; // [rsp+F0h] [rbp-10h]
  __int64 v80; // [rsp+F8h] [rbp-8h]
  const CHAR *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  int *v84; // [rsp+110h] [rbp+10h]
  int v85; // [rsp+118h] [rbp+18h]
  int v86; // [rsp+11Ch] [rbp+1Ch]
  __int64 v87; // [rsp+120h] [rbp+20h]
  __int64 v88; // [rsp+128h] [rbp+28h]
  const CHAR *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  int *v92; // [rsp+140h] [rbp+40h]
  int v93; // [rsp+148h] [rbp+48h]
  int v94; // [rsp+14Ch] [rbp+4Ch]
  __int64 v95; // [rsp+150h] [rbp+50h]
  __int64 v96; // [rsp+158h] [rbp+58h]
  __int64 v97; // [rsp+160h] [rbp+60h]
  __int64 v98; // [rsp+168h] [rbp+68h]
  const CHAR *v99; // [rsp+170h] [rbp+70h]
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
    while ( v28[v29] );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &Class;
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
    v32 = &dword_18002C8C4;
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
    while ( v35[v36] );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &Class;
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
    v38 = &dword_18002C8C4;
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
    while ( v41[v42] );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &Class;
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
    while ( v44[v45] );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &Class;
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
    v47 = &dword_18002C8C4;
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
    while ( v49[v50] );
    v51 = v50 + 1;
  }
  else
  {
    v49 = &Class;
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
    while ( v52[v25] );
    v27 = v25 + 1;
  }
  else
  {
    v52 = &Class;
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
0x180001008  push    rbp
0x18000100a  push    rbx
0x18000100b  push    rsi
0x18000100c  push    rdi
0x18000100d  push    r14
0x18000100f  lea     rbp, [rsp-90h]
0x180001017  sub     rsp, 190h
0x18000101e  mov     rax, cs:__security_cookie
0x180001025  xor     rax, rsp
0x180001028  mov     [rbp+0B0h+var_30], rax
0x18000102f  mov     rax, [rbp+0B0h+arg_B0]
0x180001036  lea     rsi, Class
0x18000103d  mov     r11, rdx
0x180001040  mov     r10, rcx
0x180001043  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001047  xor     edi, edi
0x180001049  mov     rbx, r8
0x18000104c  mov     r8d, 1
0x180001052  mov     rcx, [rax]
0x180001055  test    rcx, rcx
0x180001058  jz      short loc_18000106A
0x18000105a  mov     rax, rdx
0x18000105d  inc     rax
0x180001060  cmp     [rcx+rax], dil
0x180001064  jnz     short loc_18000105D
0x180001066  inc     eax
0x180001068  jmp     short loc_180001070
0x18000106a  mov     rcx, rsi
0x18000106d  mov     eax, r8d
0x180001070  mov     [rbp+0B0h+var_38], eax
0x180001073  mov     r9d, 2
0x180001079  mov     rax, [rbp+0B0h+arg_A8]
0x180001080  mov     [rbp+0B0h+var_50], rax
0x180001084  mov     rax, [rbp+0B0h+arg_A0]
0x18000108b  mov     [rbp+0B0h+var_60], rax
0x18000108f  mov     rax, [rbp+0B0h+arg_98]
0x180001096  mov     [rbp+0B0h+var_40], rcx
0x18000109a  mov     [rbp+0B0h+var_34], edi
0x18000109d  mov     [rbp+0B0h+var_48], 4
0x1800010a5  mov     rcx, [rax]
0x1800010a8  mov     [rbp+0B0h+var_58], 4
0x1800010b0  test    rcx, rcx
0x1800010b3  jz      short loc_1800010CA
0x1800010b5  mov     rax, rdx
0x1800010b8  inc     rax
0x1800010bb  cmp     [rcx+rax*2], di
0x1800010bf  jnz     short loc_1800010B8
0x1800010c1  lea     eax, ds:2[rax*2]
0x1800010c8  jmp     short loc_1800010D4
0x1800010ca  lea     rcx, dword_18002C8C4
0x1800010d1  mov     eax, r9d
0x1800010d4  mov     [rbp+0B0h+var_68], eax
0x1800010d7  mov     rax, [rbp+0B0h+arg_90]
0x1800010de  mov     [rbp+0B0h+var_70], rcx
0x1800010e2  mov     [rbp+0B0h+var_64], edi
0x1800010e5  mov     rcx, [rax]
0x1800010e8  test    rcx, rcx
0x1800010eb  jz      short loc_1800010FD
0x1800010ed  mov     rax, rdx
0x1800010f0  inc     rax
0x1800010f3  cmp     [rcx+rax], dil
0x1800010f7  jnz     short loc_1800010F0
0x1800010f9  inc     eax
0x1800010fb  jmp     short loc_180001103
0x1800010fd  mov     rcx, rsi
0x180001100  mov     eax, r8d
0x180001103  mov     [rbp+0B0h+var_78], eax
0x180001106  mov     rax, [rbp+0B0h+arg_88]
0x18000110d  mov     [rbp+0B0h+var_90], rax
0x180001111  mov     rax, [rbp+0B0h+arg_80]
0x180001118  mov     [rbp+0B0h+var_80], rcx
0x18000111c  mov     [rbp+0B0h+var_74], edi
0x18000111f  mov     [rbp+0B0h+var_88], 4
0x180001127  mov     rcx, [rax]
0x18000112a  test    rcx, rcx
0x18000112d  jz      short loc_180001144
0x18000112f  mov     rax, rdx
0x180001132  inc     rax
0x180001135  cmp     [rcx+rax*2], di
0x180001139  jnz     short loc_180001132
0x18000113b  lea     eax, ds:2[rax*2]
0x180001142  jmp     short loc_18000114E
0x180001144  lea     rcx, dword_18002C8C4
0x18000114b  mov     eax, r9d
0x18000114e  mov     [rbp+0B0h+var_98], eax
0x180001151  mov     rax, [rbp+0B0h+arg_78]
0x180001158  mov     [rbp+0B0h+var_A0], rcx
0x18000115c  mov     [rbp+0B0h+var_94], edi
0x18000115f  mov     rcx, [rax]
0x180001162  test    rcx, rcx
0x180001165  jz      short loc_180001177
0x180001167  mov     rax, rdx
0x18000116a  inc     rax
0x18000116d  cmp     [rcx+rax], dil
0x180001171  jnz     short loc_18000116A
0x180001173  inc     eax
0x180001175  jmp     short loc_18000117D
0x180001177  mov     rcx, rsi
0x18000117a  mov     eax, r8d
0x18000117d  mov     [rbp+0B0h+var_A8], eax
0x180001180  mov     rax, [rbp+0B0h+arg_70]
0x180001187  mov     [rbp+0B0h+var_C0], rax
0x18000118b  mov     rax, [rbp+0B0h+arg_68]
0x180001192  mov     [rbp+0B0h+var_B0], rcx
0x180001196  mov     [rbp+0B0h+var_A4], edi
0x180001199  mov     [rbp+0B0h+var_B8], 4
0x1800011a1  mov     rcx, [rax]
0x1800011a4  test    rcx, rcx
0x1800011a7  jz      short loc_1800011B9
0x1800011a9  mov     rax, rdx
0x1800011ac  inc     rax
0x1800011af  cmp     [rcx+rax], dil
0x1800011b3  jnz     short loc_1800011AC
0x1800011b5  inc     eax
0x1800011b7  jmp     short loc_1800011BF
0x1800011b9  mov     rcx, rsi
0x1800011bc  mov     eax, r8d
0x1800011bf  mov     [rbp+0B0h+var_C8], eax
0x1800011c2  mov     rax, [rbp+0B0h+arg_60]
0x1800011c9  mov     [rbp+0B0h+var_E0], rax
0x1800011cd  mov     rax, [rbp+0B0h+arg_58]
0x1800011d4  mov     [rbp+0B0h+var_D0], rcx
0x1800011d8  mov     [rbp+0B0h+var_C4], edi
0x1800011db  mov     [rbp+0B0h+var_D8], 4
0x1800011e3  mov     rcx, [rax]
0x1800011e6  test    rcx, rcx
0x1800011e9  jz      short loc_180001201
0x1800011eb  mov     rax, rdx
0x1800011ee  inc     rax
0x1800011f1  cmp     [rcx+rax*2], di
0x1800011f5  jnz     short loc_1800011EE
0x1800011f7  lea     r9d, ds:2[rax*2]
0x1800011ff  jmp     short loc_180001208
0x180001201  lea     rcx, dword_18002C8C4
0x180001208  mov     rax, [rbp+0B0h+arg_50]
0x18000120f  mov     [rbp+0B0h+var_100], rax
0x180001213  mov     rax, [rbp+0B0h+arg_48]
0x18000121a  mov     [rbp+0B0h+var_F0], rcx
0x18000121e  mov     [rbp+0B0h+var_E8], r9d
0x180001222  mov     [rbp+0B0h+var_E4], edi
0x180001225  mov     rcx, [rax]
0x180001228  mov     [rbp+0B0h+var_F8], 4
0x180001230  test    rcx, rcx
0x180001233  jz      short loc_180001245
0x180001235  mov     rax, rdx
0x180001238  inc     rax
0x18000123b  cmp     [rcx+rax], dil
0x18000123f  jnz     short loc_180001238
0x180001241  inc     eax
0x180001243  jmp     short loc_18000124B
0x180001245  mov     rcx, rsi
0x180001248  mov     eax, r8d
0x18000124b  mov     [rbp+0B0h+var_108], eax
0x18000124e  mov     rax, [rbp+0B0h+arg_40]
0x180001255  mov     [rbp+0B0h+var_120], rax
0x180001259  mov     rax, [rbp+0B0h+arg_38]
0x180001260  mov     [rbp+0B0h+var_110], rcx
0x180001264  mov     [rbp+0B0h+var_104], edi
0x180001267  mov     [rbp+0B0h+var_118], 4
0x18000126f  mov     rcx, [rax]
0x180001272  test    rcx, rcx
0x180001275  jz      short loc_180001286
0x180001277  inc     rdx
0x18000127a  cmp     [rcx+rdx], dil
0x18000127e  jnz     short loc_180001277
0x180001280  lea     r8d, [rdx+1]
0x180001284  jmp     short loc_180001289
0x180001286  mov     rcx, rsi
0x180001289  mov     rax, [rbp+0B0h+arg_30]
0x180001290  xor     r9d, r9d
0x180001293  mov     [rsp+1B0h+var_140], rax
0x180001298  mov     rdx, r11
0x18000129b  mov     rax, [rbp+0B0h+arg_28]
0x1800012a2  mov     [rsp+1B0h+var_150], rax
0x1800012a7  mov     rax, [rbp+0B0h+arg_20]
0x1800012ae  mov     [rsp+1B0h+var_160], rax
0x1800012b3  lea     rax, [rsp+1B0h+var_180]
0x1800012b8  mov     [rbp+0B0h+var_130], rcx
0x1800012bc  mov     rcx, r10
0x1800012bf  mov     [rbp+0B0h+var_128], r8d
0x1800012c3  mov     r8, rbx
0x1800012c6  mov     [rsp+1B0h+var_188], rax
0x1800012cb  mov     [rsp+1B0h+var_190], 15h
0x1800012d3  mov     [rbp+0B0h+var_124], edi
0x1800012d6  mov     [rsp+1B0h+var_138], 4
0x1800012df  mov     [rsp+1B0h+var_148], 8
0x1800012e8  mov     [rsp+1B0h+var_158], 8
0x1800012f1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012f6  mov     rcx, [rbp+0B0h+var_30]
0x1800012fd  xor     rcx, rsp; StackCookie
0x180001300  call    __security_check_cookie
0x180001305  add     rsp, 190h
0x18000130c  pop     r14
0x18000130e  pop     rdi
0x18000130f  pop     rsi
0x180001310  pop     rbx
0x180001311  pop     rbp
0x180001312  retn
```
