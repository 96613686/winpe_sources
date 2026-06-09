# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800012bc`
- end: `0x18000158d`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644@Z`
- size: `721`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000745c`

## callees

- `0x1800012bc`
- `0x180001ecc`
- `0x18001a210`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
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
        __int64 a22)
{
  __int64 v24; // rdx
  int v25; // r9d
  int *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // r8d
  const unsigned __int16 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  int *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  int *v43; // rcx
  __int64 v44; // rax
  const unsigned __int16 *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  const unsigned __int16 *v48; // rcx
  _BYTE v50[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v51; // [rsp+50h] [rbp-B0h]
  __int64 v52; // [rsp+58h] [rbp-A8h]
  __int64 v53; // [rsp+60h] [rbp-A0h]
  __int64 v54; // [rsp+68h] [rbp-98h]
  __int64 v55; // [rsp+70h] [rbp-90h]
  __int64 v56; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v57; // [rsp+80h] [rbp-80h]
  int v58; // [rsp+88h] [rbp-78h]
  int v59; // [rsp+8Ch] [rbp-74h]
  __int64 v60; // [rsp+90h] [rbp-70h]
  __int64 v61; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v62; // [rsp+A0h] [rbp-60h]
  int v63; // [rsp+A8h] [rbp-58h]
  int v64; // [rsp+ACh] [rbp-54h]
  __int64 v65; // [rsp+B0h] [rbp-50h]
  __int64 v66; // [rsp+B8h] [rbp-48h]
  int *v67; // [rsp+C0h] [rbp-40h]
  int v68; // [rsp+C8h] [rbp-38h]
  int v69; // [rsp+CCh] [rbp-34h]
  __int64 v70; // [rsp+D0h] [rbp-30h]
  __int64 v71; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v72; // [rsp+E0h] [rbp-20h]
  int v73; // [rsp+E8h] [rbp-18h]
  int v74; // [rsp+ECh] [rbp-14h]
  __int64 v75; // [rsp+F0h] [rbp-10h]
  __int64 v76; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v77; // [rsp+100h] [rbp+0h]
  int v78; // [rsp+108h] [rbp+8h]
  int v79; // [rsp+10Ch] [rbp+Ch]
  int *v80; // [rsp+110h] [rbp+10h]
  int v81; // [rsp+118h] [rbp+18h]
  int v82; // [rsp+11Ch] [rbp+1Ch]
  __int64 v83; // [rsp+120h] [rbp+20h]
  __int64 v84; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v85; // [rsp+130h] [rbp+30h]
  int v86; // [rsp+138h] [rbp+38h]
  int v87; // [rsp+13Ch] [rbp+3Ch]
  int *v88; // [rsp+140h] [rbp+40h]
  int v89; // [rsp+148h] [rbp+48h]
  int v90; // [rsp+14Ch] [rbp+4Ch]
  __int64 v91; // [rsp+150h] [rbp+50h]
  __int64 v92; // [rsp+158h] [rbp+58h]
  __int64 v93; // [rsp+160h] [rbp+60h]
  __int64 v94; // [rsp+168h] [rbp+68h]

  v93 = a22;
  v91 = a21;
  v24 = -1;
  v25 = 2;
  v94 = 4;
  v92 = 4;
  v27 = *a20;
  if ( *a20 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)v27 + v28) );
    v29 = 2 * v28 + 2;
  }
  else
  {
    v27 = &dword_18001F7A4;
    v29 = 2;
  }
  v89 = v29;
  v30 = 1;
  v88 = v27;
  v90 = 0;
  v31 = *a19;
  if ( *a19 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_BYTE *)v31 + v32) );
    v33 = v32 + 1;
  }
  else
  {
    v31 = &qword_18001EF80;
    v33 = 1;
  }
  v86 = v33;
  v83 = a18;
  v85 = v31;
  v87 = 0;
  v84 = 4;
  v34 = *a17;
  if ( *a17 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_WORD *)v34 + v35) );
    v36 = 2 * v35 + 2;
  }
  else
  {
    v34 = &dword_18001F7A4;
    v36 = 2;
  }
  v81 = v36;
  v80 = v34;
  v82 = 0;
  v37 = *a16;
  if ( *a16 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &qword_18001EF80;
    v39 = 1;
  }
  v78 = v39;
  v75 = a15;
  v77 = v37;
  v79 = 0;
  v76 = 4;
  v40 = *a14;
  if ( *a14 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &qword_18001EF80;
    v42 = 1;
  }
  v73 = v42;
  v70 = a13;
  v72 = v40;
  v74 = 0;
  v71 = 4;
  v43 = *a12;
  if ( *a12 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_WORD *)v43 + v44) );
    v25 = 2 * v44 + 2;
  }
  else
  {
    v43 = &dword_18001F7A4;
  }
  v65 = a11;
  v67 = v43;
  v68 = v25;
  v69 = 0;
  v45 = *a10;
  v66 = 4;
  if ( v45 )
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
  v63 = v47;
  v60 = a9;
  v62 = v45;
  v64 = 0;
  v61 = 4;
  v48 = *a8;
  if ( *a8 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v48 + v24) );
    v30 = v24 + 1;
  }
  else
  {
    v48 = &qword_18001EF80;
  }
  v55 = a7;
  v53 = a6;
  v51 = a5;
  v57 = v48;
  v58 = v30;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  v52 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 20, v50);
}

```

## disassembly

```asm
0x1800012bc  push    rbp
0x1800012be  push    rbx
0x1800012bf  push    rsi
0x1800012c0  push    rdi
0x1800012c1  push    r14
0x1800012c3  lea     rbp, [rsp-80h]
0x1800012c8  sub     rsp, 180h
0x1800012cf  mov     rax, cs:__security_cookie
0x1800012d6  xor     rax, rsp
0x1800012d9  mov     [rbp+0A0h+var_30], rax
0x1800012dd  mov     rax, [rbp+0A0h+arg_A8]
0x1800012e4  xor     edi, edi
0x1800012e6  mov     [rbp+0A0h+var_40], rax
0x1800012ea  mov     r11, rdx
0x1800012ed  mov     rax, [rbp+0A0h+arg_A0]
0x1800012f4  mov     r10, rcx
0x1800012f7  mov     [rbp+0A0h+var_50], rax
0x1800012fb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800012ff  mov     rax, [rbp+0A0h+arg_98]
0x180001306  lea     r9d, [rdi+2]
0x18000130a  mov     rbx, r8
0x18000130d  mov     [rbp+0A0h+var_38], 4
0x180001315  mov     [rbp+0A0h+var_48], 4
0x18000131d  mov     rcx, [rax]
0x180001320  test    rcx, rcx
0x180001323  jz      short loc_18000133A
0x180001325  mov     rax, rdx
0x180001328  inc     rax
0x18000132b  cmp     [rcx+rax*2], di
0x18000132f  jnz     short loc_180001328
0x180001331  lea     eax, ds:2[rax*2]
0x180001338  jmp     short loc_180001344
0x18000133a  lea     rcx, dword_18001F7A4
0x180001341  mov     eax, r9d
0x180001344  mov     [rbp+0A0h+var_58], eax
0x180001347  lea     rsi, qword_18001EF80
0x18000134e  mov     rax, [rbp+0A0h+arg_90]
0x180001355  mov     r8d, 1
0x18000135b  mov     [rbp+0A0h+var_60], rcx
0x18000135f  mov     [rbp+0A0h+var_54], edi
0x180001362  mov     rcx, [rax]
0x180001365  test    rcx, rcx
0x180001368  jz      short loc_18000137A
0x18000136a  mov     rax, rdx
0x18000136d  inc     rax
0x180001370  cmp     [rcx+rax], dil
0x180001374  jnz     short loc_18000136D
0x180001376  inc     eax
0x180001378  jmp     short loc_180001380
0x18000137a  mov     rcx, rsi
0x18000137d  mov     eax, r8d
0x180001380  mov     [rbp+0A0h+var_68], eax
0x180001383  mov     rax, [rbp+0A0h+arg_88]
0x18000138a  mov     [rbp+0A0h+var_80], rax
0x18000138e  mov     rax, [rbp+0A0h+arg_80]
0x180001395  mov     [rbp+0A0h+var_70], rcx
0x180001399  mov     [rbp+0A0h+var_64], edi
0x18000139c  mov     [rbp+0A0h+var_78], 4
0x1800013a4  mov     rcx, [rax]
0x1800013a7  test    rcx, rcx
0x1800013aa  jz      short loc_1800013C1
0x1800013ac  mov     rax, rdx
0x1800013af  inc     rax
0x1800013b2  cmp     [rcx+rax*2], di
0x1800013b6  jnz     short loc_1800013AF
0x1800013b8  lea     eax, ds:2[rax*2]
0x1800013bf  jmp     short loc_1800013CB
0x1800013c1  lea     rcx, dword_18001F7A4
0x1800013c8  mov     eax, r9d
0x1800013cb  mov     [rbp+0A0h+var_88], eax
0x1800013ce  mov     rax, [rbp+0A0h+arg_78]
0x1800013d5  mov     [rbp+0A0h+var_90], rcx
0x1800013d9  mov     [rbp+0A0h+var_84], edi
0x1800013dc  mov     rcx, [rax]
0x1800013df  test    rcx, rcx
0x1800013e2  jz      short loc_1800013F4
0x1800013e4  mov     rax, rdx
0x1800013e7  inc     rax
0x1800013ea  cmp     [rcx+rax], dil
0x1800013ee  jnz     short loc_1800013E7
0x1800013f0  inc     eax
0x1800013f2  jmp     short loc_1800013FA
0x1800013f4  mov     rcx, rsi
0x1800013f7  mov     eax, r8d
0x1800013fa  mov     [rbp+0A0h+var_98], eax
0x1800013fd  mov     rax, [rbp+0A0h+arg_70]
0x180001404  mov     [rbp+0A0h+var_B0], rax
0x180001408  mov     rax, [rbp+0A0h+arg_68]
0x18000140f  mov     [rbp+0A0h+var_A0], rcx
0x180001413  mov     [rbp+0A0h+var_94], edi
0x180001416  mov     [rbp+0A0h+var_A8], 4
0x18000141e  mov     rcx, [rax]
0x180001421  test    rcx, rcx
0x180001424  jz      short loc_180001436
0x180001426  mov     rax, rdx
0x180001429  inc     rax
0x18000142c  cmp     [rcx+rax], dil
0x180001430  jnz     short loc_180001429
0x180001432  inc     eax
0x180001434  jmp     short loc_18000143C
0x180001436  mov     rcx, rsi
0x180001439  mov     eax, r8d
0x18000143c  mov     [rbp+0A0h+var_B8], eax
0x18000143f  mov     rax, [rbp+0A0h+arg_60]
0x180001446  mov     [rbp+0A0h+var_D0], rax
0x18000144a  mov     rax, [rbp+0A0h+arg_58]
0x180001451  mov     [rbp+0A0h+var_C0], rcx
0x180001455  mov     [rbp+0A0h+var_B4], edi
0x180001458  mov     [rbp+0A0h+var_C8], 4
0x180001460  mov     rcx, [rax]
0x180001463  test    rcx, rcx
0x180001466  jz      short loc_18000147E
0x180001468  mov     rax, rdx
0x18000146b  inc     rax
0x18000146e  cmp     [rcx+rax*2], di
0x180001472  jnz     short loc_18000146B
0x180001474  lea     r9d, ds:2[rax*2]
0x18000147c  jmp     short loc_180001485
0x18000147e  lea     rcx, dword_18001F7A4
0x180001485  mov     rax, [rbp+0A0h+arg_50]
0x18000148c  mov     [rbp+0A0h+var_F0], rax
0x180001490  mov     rax, [rbp+0A0h+arg_48]
0x180001497  mov     [rbp+0A0h+var_E0], rcx
0x18000149b  mov     [rbp+0A0h+var_D8], r9d
0x18000149f  mov     [rbp+0A0h+var_D4], edi
0x1800014a2  mov     rcx, [rax]
0x1800014a5  mov     [rbp+0A0h+var_E8], 4
0x1800014ad  test    rcx, rcx
0x1800014b0  jz      short loc_1800014C2
0x1800014b2  mov     rax, rdx
0x1800014b5  inc     rax
0x1800014b8  cmp     [rcx+rax], dil
0x1800014bc  jnz     short loc_1800014B5
0x1800014be  inc     eax
0x1800014c0  jmp     short loc_1800014C8
0x1800014c2  mov     rcx, rsi
0x1800014c5  mov     eax, r8d
0x1800014c8  mov     [rbp+0A0h+var_F8], eax
0x1800014cb  mov     rax, [rbp+0A0h+arg_40]
0x1800014d2  mov     [rbp+0A0h+var_110], rax
0x1800014d6  mov     rax, [rbp+0A0h+arg_38]
0x1800014dd  mov     [rbp+0A0h+var_100], rcx
0x1800014e1  mov     [rbp+0A0h+var_F4], edi
0x1800014e4  mov     [rbp+0A0h+var_108], 4
0x1800014ec  mov     rcx, [rax]
0x1800014ef  test    rcx, rcx
0x1800014f2  jz      short loc_180001503
0x1800014f4  inc     rdx
0x1800014f7  cmp     [rcx+rdx], dil
0x1800014fb  jnz     short loc_1800014F4
0x1800014fd  lea     r8d, [rdx+1]
0x180001501  jmp     short loc_180001506
0x180001503  mov     rcx, rsi
0x180001506  mov     rax, [rbp+0A0h+arg_30]
0x18000150d  xor     r9d, r9d
0x180001510  mov     [rsp+1A0h+var_130], rax
0x180001515  mov     rdx, r11
0x180001518  mov     rax, [rbp+0A0h+arg_28]
0x18000151f  mov     [rsp+1A0h+var_140], rax
0x180001524  mov     rax, [rbp+0A0h+arg_20]
0x18000152b  mov     [rsp+1A0h+var_150], rax
0x180001530  lea     rax, [rsp+1A0h+var_170]
0x180001535  mov     [rbp+0A0h+var_120], rcx
0x180001539  mov     rcx, r10
0x18000153c  mov     [rbp+0A0h+var_118], r8d
0x180001540  mov     r8, rbx
0x180001543  mov     [rsp+1A0h+var_178], rax
0x180001548  mov     [rsp+1A0h+var_180], 14h
0x180001550  mov     [rbp+0A0h+var_114], edi
0x180001553  mov     [rsp+1A0h+var_128], 4
0x18000155c  mov     [rsp+1A0h+var_138], 8
0x180001565  mov     [rsp+1A0h+var_148], 8
0x18000156e  call    _tlgWriteTransfer_EventWriteTransfer
0x180001573  mov     rcx, [rbp+0A0h+var_30]
0x180001577  xor     rcx, rsp; StackCookie
0x18000157a  call    __security_check_cookie
0x18000157f  add     rsp, 180h
0x180001586  pop     r14
0x180001588  pop     rdi
0x180001589  pop     rsi
0x18000158a  pop     rbx
0x18000158b  pop     rbp
0x18000158c  retn
```
