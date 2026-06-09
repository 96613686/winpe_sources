# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800011a4`
- end: `0x18000144f`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, char **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, char **, __int64, const unsigned __int16 **, char **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d3a0`

## callees

- `0x1800011a4`
- `0x180002018`
- `0x1800027f0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        char **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        char **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        char **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  char *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  char *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  char *v40; // rdx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rdx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  char *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  char *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  char *v85; // [rsp+140h] [rbp+40h]
  int v86; // [rsp+148h] [rbp+48h]
  int v87; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v23 = 2;
  v24 = *a20;
  if ( *a20 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)&v24[2 * v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = byte_180017D50;
    v26 = 2;
  }
  v86 = v26;
  v27 = 1;
  v85 = v24;
  v87 = 0;
  v28 = *a19;
  if ( *a19 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &word_180017D52;
    v30 = 1;
  }
  v83 = v30;
  v80 = a18;
  v82 = v28;
  v84 = 0;
  v81 = 4;
  v31 = *a17;
  if ( *a17 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *(_WORD *)&v31[2 * v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = byte_180017D50;
    v33 = 2;
  }
  v78 = v33;
  v77 = v31;
  v79 = 0;
  v34 = *a16;
  if ( *a16 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &word_180017D52;
    v36 = 1;
  }
  v75 = v36;
  v72 = a15;
  v74 = v34;
  v76 = 0;
  v73 = 4;
  v37 = *a14;
  if ( *a14 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &word_180017D52;
    v39 = 1;
  }
  v70 = v39;
  v67 = a13;
  v69 = v37;
  v71 = 0;
  v68 = 4;
  v40 = *a12;
  if ( *a12 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *(_WORD *)&v40[2 * v41] );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = byte_180017D50;
  }
  v62 = a11;
  v64 = v40;
  v65 = v23;
  v66 = 0;
  v42 = *a10;
  v63 = 4;
  if ( v42 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &word_180017D52;
    v44 = 1;
  }
  v60 = v44;
  v57 = a9;
  v59 = v42;
  v61 = 0;
  v58 = 4;
  v45 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v45 + v22) );
    v27 = v22 + 1;
  }
  else
  {
    v45 = &word_180017D52;
  }
  v52 = a7;
  v50 = a6;
  v48 = a5;
  v54 = v45;
  v55 = v27;
  v56 = 0;
  v53 = 4;
  v51 = 8;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 18, v47);
}

```

## disassembly

```asm
0x1800011a4  mov     [rsp-8+arg_10], rbx
0x1800011a9  push    rbp
0x1800011aa  push    rsi
0x1800011ab  push    rdi
0x1800011ac  lea     rbp, [rsp-60h]
0x1800011b1  sub     rsp, 160h
0x1800011b8  mov     rax, cs:__security_cookie
0x1800011bf  xor     rax, rsp
0x1800011c2  mov     [rbp+70h+var_20], rax
0x1800011c6  mov     rax, [rbp+70h+arg_98]
0x1800011cd  mov     r11, rdx
0x1800011d0  mov     r10, rcx
0x1800011d3  xor     ebx, ebx
0x1800011d5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800011d9  mov     r9d, 2
0x1800011df  mov     rdx, [rax]
0x1800011e2  test    rdx, rdx
0x1800011e5  jz      short loc_1800011FC
0x1800011e7  mov     rax, rcx
0x1800011ea  inc     rax
0x1800011ed  cmp     [rdx+rax*2], bx
0x1800011f1  jnz     short loc_1800011EA
0x1800011f3  lea     eax, ds:2[rax*2]
0x1800011fa  jmp     short loc_180001206
0x1800011fc  lea     rdx, byte_180017D50
0x180001203  mov     eax, r9d
0x180001206  mov     [rbp+70h+var_28], eax
0x180001209  lea     rdi, word_180017D52
0x180001210  mov     rax, [rbp+70h+arg_90]
0x180001217  mov     r8d, 1
0x18000121d  mov     [rbp+70h+var_30], rdx
0x180001221  mov     [rbp+70h+var_24], ebx
0x180001224  mov     rdx, [rax]
0x180001227  test    rdx, rdx
0x18000122a  jz      short loc_18000123B
0x18000122c  mov     rax, rcx
0x18000122f  inc     rax
0x180001232  cmp     [rdx+rax], bl
0x180001235  jnz     short loc_18000122F
0x180001237  inc     eax
0x180001239  jmp     short loc_180001241
0x18000123b  mov     rdx, rdi
0x18000123e  mov     eax, r8d
0x180001241  mov     [rbp+70h+var_38], eax
0x180001244  mov     rax, [rbp+70h+arg_88]
0x18000124b  mov     [rbp+70h+var_50], rax
0x18000124f  mov     rax, [rbp+70h+arg_80]
0x180001256  mov     [rbp+70h+var_40], rdx
0x18000125a  mov     [rbp+70h+var_34], ebx
0x18000125d  mov     [rbp+70h+var_48], 4
0x180001265  mov     rdx, [rax]
0x180001268  test    rdx, rdx
0x18000126b  jz      short loc_180001282
0x18000126d  mov     rax, rcx
0x180001270  inc     rax
0x180001273  cmp     [rdx+rax*2], bx
0x180001277  jnz     short loc_180001270
0x180001279  lea     eax, ds:2[rax*2]
0x180001280  jmp     short loc_18000128C
0x180001282  lea     rdx, byte_180017D50
0x180001289  mov     eax, r9d
0x18000128c  mov     [rbp+70h+var_58], eax
0x18000128f  mov     rax, [rbp+70h+arg_78]
0x180001296  mov     [rbp+70h+var_60], rdx
0x18000129a  mov     [rbp+70h+var_54], ebx
0x18000129d  mov     rdx, [rax]
0x1800012a0  test    rdx, rdx
0x1800012a3  jz      short loc_1800012B4
0x1800012a5  mov     rax, rcx
0x1800012a8  inc     rax
0x1800012ab  cmp     [rdx+rax], bl
0x1800012ae  jnz     short loc_1800012A8
0x1800012b0  inc     eax
0x1800012b2  jmp     short loc_1800012BA
0x1800012b4  mov     rdx, rdi
0x1800012b7  mov     eax, r8d
0x1800012ba  mov     [rbp+70h+var_68], eax
0x1800012bd  mov     rax, [rbp+70h+arg_70]
0x1800012c4  mov     [rbp+70h+var_80], rax
0x1800012c8  mov     rax, [rbp+70h+arg_68]
0x1800012cf  mov     [rbp+70h+var_70], rdx
0x1800012d3  mov     [rbp+70h+var_64], ebx
0x1800012d6  mov     [rbp+70h+var_78], 4
0x1800012de  mov     rdx, [rax]
0x1800012e1  test    rdx, rdx
0x1800012e4  jz      short loc_1800012F5
0x1800012e6  mov     rax, rcx
0x1800012e9  inc     rax
0x1800012ec  cmp     [rdx+rax], bl
0x1800012ef  jnz     short loc_1800012E9
0x1800012f1  inc     eax
0x1800012f3  jmp     short loc_1800012FB
0x1800012f5  mov     rdx, rdi
0x1800012f8  mov     eax, r8d
0x1800012fb  mov     [rbp+70h+var_88], eax
0x1800012fe  mov     rax, [rbp+70h+arg_60]
0x180001305  mov     [rbp+70h+var_A0], rax
0x180001309  mov     rax, [rbp+70h+arg_58]
0x180001310  mov     [rbp+70h+var_90], rdx
0x180001314  mov     [rbp+70h+var_84], ebx
0x180001317  mov     [rbp+70h+var_98], 4
0x18000131f  mov     rdx, [rax]
0x180001322  test    rdx, rdx
0x180001325  jz      short loc_18000133D
0x180001327  mov     rax, rcx
0x18000132a  inc     rax
0x18000132d  cmp     [rdx+rax*2], bx
0x180001331  jnz     short loc_18000132A
0x180001333  lea     r9d, ds:2[rax*2]
0x18000133b  jmp     short loc_180001344
0x18000133d  lea     rdx, byte_180017D50
0x180001344  mov     rax, [rbp+70h+arg_50]
0x18000134b  mov     [rbp+70h+var_C0], rax
0x18000134f  mov     rax, [rbp+70h+arg_48]
0x180001356  mov     [rbp+70h+var_B0], rdx
0x18000135a  mov     [rbp+70h+var_A8], r9d
0x18000135e  mov     [rbp+70h+var_A4], ebx
0x180001361  mov     rdx, [rax]
0x180001364  mov     [rbp+70h+var_B8], 4
0x18000136c  test    rdx, rdx
0x18000136f  jz      short loc_180001380
0x180001371  mov     rax, rcx
0x180001374  inc     rax
0x180001377  cmp     [rdx+rax], bl
0x18000137a  jnz     short loc_180001374
0x18000137c  inc     eax
0x18000137e  jmp     short loc_180001386
0x180001380  mov     rdx, rdi
0x180001383  mov     eax, r8d
0x180001386  mov     [rbp+70h+var_C8], eax
0x180001389  mov     rax, [rbp+70h+arg_40]
0x180001390  mov     [rbp+70h+var_E0], rax
0x180001394  mov     rax, [rbp+70h+arg_38]
0x18000139b  mov     [rbp+70h+var_D0], rdx
0x18000139f  mov     [rbp+70h+var_C4], ebx
0x1800013a2  mov     [rbp+70h+var_D8], 4
0x1800013aa  mov     rdx, [rax]
0x1800013ad  test    rdx, rdx
0x1800013b0  jz      short loc_1800013C0
0x1800013b2  inc     rcx
0x1800013b5  cmp     [rdx+rcx], bl
0x1800013b8  jnz     short loc_1800013B2
0x1800013ba  lea     r8d, [rcx+1]
0x1800013be  jmp     short loc_1800013C3
0x1800013c0  mov     rdx, rdi
0x1800013c3  mov     rax, [rbp+70h+arg_30]
0x1800013ca  xor     r9d, r9d
0x1800013cd  mov     [rsp+170h+var_100], rax
0x1800013d2  mov     rcx, r10
0x1800013d5  mov     rax, [rbp+70h+arg_28]
0x1800013dc  mov     [rsp+170h+var_110], rax
0x1800013e1  mov     rax, [rbp+70h+arg_20]
0x1800013e8  mov     [rsp+170h+var_120], rax
0x1800013ed  lea     rax, [rsp+170h+var_140]
0x1800013f2  mov     [rbp+70h+var_F0], rdx
0x1800013f6  mov     rdx, r11
0x1800013f9  mov     [rbp+70h+var_E8], r8d
0x1800013fd  xor     r8d, r8d
0x180001400  mov     [rsp+170h+var_148], rax
0x180001405  mov     [rsp+170h+var_150], 12h
0x18000140d  mov     [rbp+70h+var_E4], ebx
0x180001410  mov     [rsp+170h+var_F8], 4
0x180001419  mov     [rsp+170h+var_108], 8
0x180001422  mov     [rsp+170h+var_118], 8
0x18000142b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001430  mov     rcx, [rbp+70h+var_20]
0x180001434  xor     rcx, rsp; StackCookie
0x180001437  call    __security_check_cookie
0x18000143c  mov     rbx, [rsp+170h+arg_10]
0x180001444  add     rsp, 160h
0x18000144b  pop     rdi
0x18000144c  pop     rsi
0x18000144d  pop     rbp
0x18000144e  retn
```
