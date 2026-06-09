# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001f6c`
- end: `0x18000225c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fbd0`

## callees

- `0x180001f6c`
- `0x180005a74`
- `0x180008a90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        __int64 **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        __int64 **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        __int64 **a19,
        __int64 a20,
        __int64 a21,
        const unsigned __int16 **a22)
{
  __int64 v24; // rdx
  int v25; // r8d
  const unsigned __int16 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r9d
  __int64 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  __int64 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  __int64 *v45; // rcx
  __int64 v46; // rax
  const unsigned __int16 *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // rcx
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v57; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+7Ch] [rbp-84h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  __int64 *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v72; // [rsp+D0h] [rbp-30h]
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+F8h] [rbp-8h]
  int v79; // [rsp+FCh] [rbp-4h]
  __int64 *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v95; // [rsp+160h] [rbp+60h]
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
    v26 = &dword_18002202C;
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
    while ( *((_WORD *)v30 + v31) );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &qword_180022030;
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
    v33 = &dword_18002202C;
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
    while ( *((_WORD *)v36 + v37) );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &qword_180022030;
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
    v39 = &dword_18002202C;
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
    v42 = &dword_18002202C;
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
    while ( *((_WORD *)v45 + v46) );
    v29 = 2 * v46 + 2;
  }
  else
  {
    v45 = &qword_180022030;
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
    v47 = &dword_18002202C;
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
    v50 = &dword_18002202C;
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
0x180001f6c  mov     [rsp-8+arg_10], rbx
0x180001f71  push    rbp
0x180001f72  push    rdi
0x180001f73  push    r14
0x180001f75  lea     rbp, [rsp-80h]
0x180001f7a  sub     rsp, 180h
0x180001f81  mov     rax, cs:__security_cookie
0x180001f88  xor     rax, rsp
0x180001f8b  mov     [rbp+90h+var_20], rax
0x180001f8f  mov     rax, [rbp+90h+arg_A8]
0x180001f96  lea     rdi, dword_18002202C
0x180001f9d  mov     r11, rdx
0x180001fa0  mov     r10, rcx
0x180001fa3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001fa7  xor     ebx, ebx
0x180001fa9  mov     r8d, 1
0x180001faf  mov     rcx, [rax]
0x180001fb2  test    rcx, rcx
0x180001fb5  jz      short loc_180001FC6
0x180001fb7  mov     rax, rdx
0x180001fba  inc     rax
0x180001fbd  cmp     [rcx+rax], bl
0x180001fc0  jnz     short loc_180001FBA
0x180001fc2  inc     eax
0x180001fc4  jmp     short loc_180001FCC
0x180001fc6  mov     rcx, rdi
0x180001fc9  mov     eax, r8d
0x180001fcc  mov     [rbp+90h+var_28], eax
0x180001fcf  mov     r9d, 2
0x180001fd5  mov     rax, [rbp+90h+arg_A0]
0x180001fdc  mov     [rbp+90h+var_40], rax
0x180001fe0  mov     rax, [rbp+90h+arg_98]
0x180001fe7  mov     [rbp+90h+var_50], rax
0x180001feb  mov     rax, [rbp+90h+arg_90]
0x180001ff2  mov     [rbp+90h+var_30], rcx
0x180001ff6  mov     [rbp+90h+var_24], ebx
0x180001ff9  mov     [rbp+90h+var_38], 4
0x180002001  mov     rcx, [rax]
0x180002004  mov     [rbp+90h+var_48], 4
0x18000200c  test    rcx, rcx
0x18000200f  jz      short loc_180002026
0x180002011  mov     rax, rdx
0x180002014  inc     rax
0x180002017  cmp     [rcx+rax*2], bx
0x18000201b  jnz     short loc_180002014
0x18000201d  lea     eax, ds:2[rax*2]
0x180002024  jmp     short loc_180002030
0x180002026  lea     rcx, qword_180022030
0x18000202d  mov     eax, r9d
0x180002030  mov     [rbp+90h+var_58], eax
0x180002033  mov     rax, [rbp+90h+arg_88]
0x18000203a  mov     [rbp+90h+var_60], rcx
0x18000203e  mov     [rbp+90h+var_54], ebx
0x180002041  mov     rcx, [rax]
0x180002044  test    rcx, rcx
0x180002047  jz      short loc_180002058
0x180002049  mov     rax, rdx
0x18000204c  inc     rax
0x18000204f  cmp     [rcx+rax], bl
0x180002052  jnz     short loc_18000204C
0x180002054  inc     eax
0x180002056  jmp     short loc_18000205E
0x180002058  mov     rcx, rdi
0x18000205b  mov     eax, r8d
0x18000205e  mov     [rbp+90h+var_68], eax
0x180002061  mov     rax, [rbp+90h+arg_80]
0x180002068  mov     [rbp+90h+var_80], rax
0x18000206c  mov     rax, [rbp+90h+arg_78]
0x180002073  mov     [rbp+90h+var_70], rcx
0x180002077  mov     [rbp+90h+var_64], ebx
0x18000207a  mov     [rbp+90h+var_78], 4
0x180002082  mov     rcx, [rax]
0x180002085  test    rcx, rcx
0x180002088  jz      short loc_18000209F
0x18000208a  mov     rax, rdx
0x18000208d  inc     rax
0x180002090  cmp     [rcx+rax*2], bx
0x180002094  jnz     short loc_18000208D
0x180002096  lea     eax, ds:2[rax*2]
0x18000209d  jmp     short loc_1800020A9
0x18000209f  lea     rcx, qword_180022030
0x1800020a6  mov     eax, r9d
0x1800020a9  mov     [rbp+90h+var_88], eax
0x1800020ac  mov     rax, [rbp+90h+arg_70]
0x1800020b3  mov     [rbp+90h+var_90], rcx
0x1800020b7  mov     [rbp+90h+var_84], ebx
0x1800020ba  mov     rcx, [rax]
0x1800020bd  test    rcx, rcx
0x1800020c0  jz      short loc_1800020D1
0x1800020c2  mov     rax, rdx
0x1800020c5  inc     rax
0x1800020c8  cmp     [rcx+rax], bl
0x1800020cb  jnz     short loc_1800020C5
0x1800020cd  inc     eax
0x1800020cf  jmp     short loc_1800020D7
0x1800020d1  mov     rcx, rdi
0x1800020d4  mov     eax, r8d
0x1800020d7  mov     [rbp+90h+var_98], eax
0x1800020da  mov     rax, [rbp+90h+arg_68]
0x1800020e1  mov     [rbp+90h+var_B0], rax
0x1800020e5  mov     rax, [rbp+90h+arg_60]
0x1800020ec  mov     [rbp+90h+var_A0], rcx
0x1800020f0  mov     [rbp+90h+var_94], ebx
0x1800020f3  mov     [rbp+90h+var_A8], 4
0x1800020fb  mov     rcx, [rax]
0x1800020fe  test    rcx, rcx
0x180002101  jz      short loc_180002112
0x180002103  mov     rax, rdx
0x180002106  inc     rax
0x180002109  cmp     [rcx+rax], bl
0x18000210c  jnz     short loc_180002106
0x18000210e  inc     eax
0x180002110  jmp     short loc_180002118
0x180002112  mov     rcx, rdi
0x180002115  mov     eax, r8d
0x180002118  mov     [rbp+90h+var_B8], eax
0x18000211b  mov     rax, [rbp+90h+arg_58]
0x180002122  mov     [rbp+90h+var_D0], rax
0x180002126  mov     rax, [rbp+90h+arg_50]
0x18000212d  mov     [rbp+90h+var_C0], rcx
0x180002131  mov     [rbp+90h+var_B4], ebx
0x180002134  mov     [rbp+90h+var_C8], 4
0x18000213c  mov     rcx, [rax]
0x18000213f  test    rcx, rcx
0x180002142  jz      short loc_18000215A
0x180002144  mov     rax, rdx
0x180002147  inc     rax
0x18000214a  cmp     [rcx+rax*2], bx
0x18000214e  jnz     short loc_180002147
0x180002150  lea     r9d, ds:2[rax*2]
0x180002158  jmp     short loc_180002161
0x18000215a  lea     rcx, qword_180022030
0x180002161  mov     rax, [rbp+90h+arg_48]
0x180002168  mov     [rbp+90h+var_F0], rax
0x18000216c  mov     rax, [rbp+90h+arg_40]
0x180002173  mov     [rbp+90h+var_E0], rcx
0x180002177  mov     [rbp+90h+var_D8], r9d
0x18000217b  mov     [rbp+90h+var_D4], ebx
0x18000217e  mov     rcx, [rax]
0x180002181  mov     [rbp+90h+var_E8], 4
0x180002189  test    rcx, rcx
0x18000218c  jz      short loc_18000219D
0x18000218e  mov     rax, rdx
0x180002191  inc     rax
0x180002194  cmp     [rcx+rax], bl
0x180002197  jnz     short loc_180002191
0x180002199  inc     eax
0x18000219b  jmp     short loc_1800021A3
0x18000219d  mov     rcx, rdi
0x1800021a0  mov     eax, r8d
0x1800021a3  mov     [rbp+90h+var_F8], eax
0x1800021a6  mov     rax, [rbp+90h+arg_38]
0x1800021ad  mov     [rbp+90h+var_110], rax
0x1800021b1  mov     rax, [rbp+90h+arg_30]
0x1800021b8  mov     [rbp+90h+var_100], rcx
0x1800021bc  mov     [rbp+90h+var_F4], ebx
0x1800021bf  mov     [rbp+90h+var_108], 4
0x1800021c7  mov     rcx, [rax]
0x1800021ca  test    rcx, rcx
0x1800021cd  jz      short loc_1800021DD
0x1800021cf  inc     rdx
0x1800021d2  cmp     [rcx+rdx], bl
0x1800021d5  jnz     short loc_1800021CF
0x1800021d7  lea     r8d, [rdx+1]
0x1800021db  jmp     short loc_1800021E0
0x1800021dd  mov     rcx, rdi
0x1800021e0  mov     rax, [rbp+90h+arg_28]
0x1800021e7  xor     r9d, r9d; int
0x1800021ea  mov     [rsp+190h+var_130], rax
0x1800021ef  mov     rdx, r11; int
0x1800021f2  mov     rax, [rbp+90h+arg_20]
0x1800021f9  mov     [rsp+190h+var_140], rax
0x1800021fe  lea     rax, [rsp+190h+var_160]
0x180002203  mov     [rsp+190h+var_120], rcx
0x180002208  mov     rcx, r10; int
0x18000220b  mov     [rsp+190h+var_118], r8d
0x180002210  xor     r8d, r8d; int
0x180002213  mov     [rsp+190h+var_168], rax; PEVENT_DATA_DESCRIPTOR
0x180002218  mov     [rsp+190h+var_170], 14h; ULONG
0x180002220  mov     [rsp+190h+var_114], ebx
0x180002224  mov     [rsp+190h+var_128], 4
0x18000222d  mov     [rsp+190h+var_138], 8
0x180002236  call    _tlgWriteTransfer_EventWriteTransfer
0x18000223b  mov     rcx, [rbp+90h+var_20]
0x18000223f  xor     rcx, rsp; StackCookie
0x180002242  call    __security_check_cookie
0x180002247  mov     rbx, [rsp+190h+arg_10]
0x18000224f  add     rsp, 180h
0x180002256  pop     r14
0x180002258  pop     rdi
0x180002259  pop     rbp
0x18000225a  retn
```
