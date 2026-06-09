# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001b54`
- end: `0x180001e44`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180009890`
- `0x18000aeb8`

## callees

- `0x180001b54`
- `0x180001ecc`
- `0x18001a210`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        int **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        int **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        int **a19,
        __int64 a20,
        __int64 a21,
        const unsigned __int16 **a22)
{
  __int64 v24; // rdx
  int v26; // r8d
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // r9d
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  int *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  int *v46; // rcx
  __int64 v47; // rax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const unsigned __int16 *v51; // rcx
  _BYTE v53[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+78h] [rbp-88h]
  int v60; // [rsp+7Ch] [rbp-84h]
  __int64 v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v63; // [rsp+90h] [rbp-70h]
  int v64; // [rsp+98h] [rbp-68h]
  int v65; // [rsp+9Ch] [rbp-64h]
  __int64 v66; // [rsp+A0h] [rbp-60h]
  __int64 v67; // [rsp+A8h] [rbp-58h]
  int *v68; // [rsp+B0h] [rbp-50h]
  int v69; // [rsp+B8h] [rbp-48h]
  int v70; // [rsp+BCh] [rbp-44h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v73; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+D8h] [rbp-28h]
  int v75; // [rsp+DCh] [rbp-24h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  __int64 v77; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v78; // [rsp+F0h] [rbp-10h]
  int v79; // [rsp+F8h] [rbp-8h]
  int v80; // [rsp+FCh] [rbp-4h]
  int *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  int *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  __int64 v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]
  __int64 v94; // [rsp+150h] [rbp+50h]
  __int64 v95; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v96; // [rsp+160h] [rbp+60h]
  int v97; // [rsp+168h] [rbp+68h]
  int v98; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v26 = 1;
  v27 = *a22;
  if ( *a22 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &qword_18001EF80;
    v29 = 1;
  }
  v97 = v29;
  v30 = 2;
  v94 = a21;
  v92 = a20;
  v96 = v27;
  v98 = 0;
  v95 = 4;
  v31 = *a19;
  v93 = 4;
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
  v90 = v33;
  v89 = v31;
  v91 = 0;
  v34 = *a18;
  if ( *a18 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &qword_18001EF80;
    v36 = 1;
  }
  v87 = v36;
  v84 = a17;
  v86 = v34;
  v88 = 0;
  v85 = 4;
  v37 = *a16;
  if ( *a16 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_WORD *)v37 + v38) );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &dword_18001F7A4;
    v39 = 2;
  }
  v82 = v39;
  v81 = v37;
  v83 = 0;
  v40 = *a15;
  if ( *a15 )
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
  v79 = v42;
  v76 = a14;
  v78 = v40;
  v80 = 0;
  v77 = 4;
  v43 = *a13;
  if ( *a13 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &qword_18001EF80;
    v45 = 1;
  }
  v74 = v45;
  v71 = a12;
  v73 = v43;
  v75 = 0;
  v72 = 4;
  v46 = *a11;
  if ( *a11 )
  {
    v47 = -1;
    do
      ++v47;
    while ( *((_WORD *)v46 + v47) );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = &dword_18001F7A4;
  }
  v66 = a10;
  v68 = v46;
  v69 = v30;
  v70 = 0;
  v48 = *a9;
  v67 = 4;
  if ( v48 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_BYTE *)v48 + v49) );
    v50 = v49 + 1;
  }
  else
  {
    v48 = &qword_18001EF80;
    v50 = 1;
  }
  v64 = v50;
  v61 = a8;
  v63 = v48;
  v65 = 0;
  v62 = 4;
  v51 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v51 + v24) );
    v26 = v24 + 1;
  }
  else
  {
    v51 = &qword_18001EF80;
  }
  v56 = a6;
  v54 = a5;
  v58 = v51;
  v59 = v26;
  v60 = 0;
  v57 = 4;
  v55 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 20, v53);
}

```

## disassembly

```asm
0x180001b54  push    rbp
0x180001b56  push    rbx
0x180001b57  push    rsi
0x180001b58  push    rdi
0x180001b59  push    r15
0x180001b5b  lea     rbp, [rsp-80h]
0x180001b60  sub     rsp, 180h
0x180001b67  mov     rax, cs:__security_cookie
0x180001b6e  xor     rax, rsp
0x180001b71  mov     [rbp+0A0h+var_30], rax
0x180001b75  mov     rax, [rbp+0A0h+arg_A8]
0x180001b7c  lea     rsi, qword_18001EF80
0x180001b83  mov     r11, rdx
0x180001b86  mov     r10, rcx
0x180001b89  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001b8d  xor     edi, edi
0x180001b8f  mov     rbx, r8
0x180001b92  mov     r8d, 1
0x180001b98  mov     rcx, [rax]
0x180001b9b  test    rcx, rcx
0x180001b9e  jz      short loc_180001BB0
0x180001ba0  mov     rax, rdx
0x180001ba3  inc     rax
0x180001ba6  cmp     [rcx+rax], dil
0x180001baa  jnz     short loc_180001BA3
0x180001bac  inc     eax
0x180001bae  jmp     short loc_180001BB6
0x180001bb0  mov     rcx, rsi
0x180001bb3  mov     eax, r8d
0x180001bb6  mov     [rbp+0A0h+var_38], eax
0x180001bb9  mov     r9d, 2
0x180001bbf  mov     rax, [rbp+0A0h+arg_A0]
0x180001bc6  mov     [rbp+0A0h+var_50], rax
0x180001bca  mov     rax, [rbp+0A0h+arg_98]
0x180001bd1  mov     [rbp+0A0h+var_60], rax
0x180001bd5  mov     rax, [rbp+0A0h+arg_90]
0x180001bdc  mov     [rbp+0A0h+var_40], rcx
0x180001be0  mov     [rbp+0A0h+var_34], edi
0x180001be3  mov     [rbp+0A0h+var_48], 4
0x180001beb  mov     rcx, [rax]
0x180001bee  mov     [rbp+0A0h+var_58], 4
0x180001bf6  test    rcx, rcx
0x180001bf9  jz      short loc_180001C10
0x180001bfb  mov     rax, rdx
0x180001bfe  inc     rax
0x180001c01  cmp     [rcx+rax*2], di
0x180001c05  jnz     short loc_180001BFE
0x180001c07  lea     eax, ds:2[rax*2]
0x180001c0e  jmp     short loc_180001C1A
0x180001c10  lea     rcx, dword_18001F7A4
0x180001c17  mov     eax, r9d
0x180001c1a  mov     [rbp+0A0h+var_68], eax
0x180001c1d  mov     rax, [rbp+0A0h+arg_88]
0x180001c24  mov     [rbp+0A0h+var_70], rcx
0x180001c28  mov     [rbp+0A0h+var_64], edi
0x180001c2b  mov     rcx, [rax]
0x180001c2e  test    rcx, rcx
0x180001c31  jz      short loc_180001C43
0x180001c33  mov     rax, rdx
0x180001c36  inc     rax
0x180001c39  cmp     [rcx+rax], dil
0x180001c3d  jnz     short loc_180001C36
0x180001c3f  inc     eax
0x180001c41  jmp     short loc_180001C49
0x180001c43  mov     rcx, rsi
0x180001c46  mov     eax, r8d
0x180001c49  mov     [rbp+0A0h+var_78], eax
0x180001c4c  mov     rax, [rbp+0A0h+arg_80]
0x180001c53  mov     [rbp+0A0h+var_90], rax
0x180001c57  mov     rax, [rbp+0A0h+arg_78]
0x180001c5e  mov     [rbp+0A0h+var_80], rcx
0x180001c62  mov     [rbp+0A0h+var_74], edi
0x180001c65  mov     [rbp+0A0h+var_88], 4
0x180001c6d  mov     rcx, [rax]
0x180001c70  test    rcx, rcx
0x180001c73  jz      short loc_180001C8A
0x180001c75  mov     rax, rdx
0x180001c78  inc     rax
0x180001c7b  cmp     [rcx+rax*2], di
0x180001c7f  jnz     short loc_180001C78
0x180001c81  lea     eax, ds:2[rax*2]
0x180001c88  jmp     short loc_180001C94
0x180001c8a  lea     rcx, dword_18001F7A4
0x180001c91  mov     eax, r9d
0x180001c94  mov     [rbp+0A0h+var_98], eax
0x180001c97  mov     rax, [rbp+0A0h+arg_70]
0x180001c9e  mov     [rbp+0A0h+var_A0], rcx
0x180001ca2  mov     [rbp+0A0h+var_94], edi
0x180001ca5  mov     rcx, [rax]
0x180001ca8  test    rcx, rcx
0x180001cab  jz      short loc_180001CBD
0x180001cad  mov     rax, rdx
0x180001cb0  inc     rax
0x180001cb3  cmp     [rcx+rax], dil
0x180001cb7  jnz     short loc_180001CB0
0x180001cb9  inc     eax
0x180001cbb  jmp     short loc_180001CC3
0x180001cbd  mov     rcx, rsi
0x180001cc0  mov     eax, r8d
0x180001cc3  mov     [rbp+0A0h+var_A8], eax
0x180001cc6  mov     rax, [rbp+0A0h+arg_68]
0x180001ccd  mov     [rbp+0A0h+var_C0], rax
0x180001cd1  mov     rax, [rbp+0A0h+arg_60]
0x180001cd8  mov     [rbp+0A0h+var_B0], rcx
0x180001cdc  mov     [rbp+0A0h+var_A4], edi
0x180001cdf  mov     [rbp+0A0h+var_B8], 4
0x180001ce7  mov     rcx, [rax]
0x180001cea  test    rcx, rcx
0x180001ced  jz      short loc_180001CFF
0x180001cef  mov     rax, rdx
0x180001cf2  inc     rax
0x180001cf5  cmp     [rcx+rax], dil
0x180001cf9  jnz     short loc_180001CF2
0x180001cfb  inc     eax
0x180001cfd  jmp     short loc_180001D05
0x180001cff  mov     rcx, rsi
0x180001d02  mov     eax, r8d
0x180001d05  mov     [rbp+0A0h+var_C8], eax
0x180001d08  mov     rax, [rbp+0A0h+arg_58]
0x180001d0f  mov     [rbp+0A0h+var_E0], rax
0x180001d13  mov     rax, [rbp+0A0h+arg_50]
0x180001d1a  mov     [rbp+0A0h+var_D0], rcx
0x180001d1e  mov     [rbp+0A0h+var_C4], edi
0x180001d21  mov     [rbp+0A0h+var_D8], 4
0x180001d29  mov     rcx, [rax]
0x180001d2c  test    rcx, rcx
0x180001d2f  jz      short loc_180001D47
0x180001d31  mov     rax, rdx
0x180001d34  inc     rax
0x180001d37  cmp     [rcx+rax*2], di
0x180001d3b  jnz     short loc_180001D34
0x180001d3d  lea     r9d, ds:2[rax*2]
0x180001d45  jmp     short loc_180001D4E
0x180001d47  lea     rcx, dword_18001F7A4
0x180001d4e  mov     rax, [rbp+0A0h+arg_48]
0x180001d55  mov     [rbp+0A0h+var_100], rax
0x180001d59  mov     rax, [rbp+0A0h+arg_40]
0x180001d60  mov     [rbp+0A0h+var_F0], rcx
0x180001d64  mov     [rbp+0A0h+var_E8], r9d
0x180001d68  mov     [rbp+0A0h+var_E4], edi
0x180001d6b  mov     rcx, [rax]
0x180001d6e  mov     [rbp+0A0h+var_F8], 4
0x180001d76  test    rcx, rcx
0x180001d79  jz      short loc_180001D8B
0x180001d7b  mov     rax, rdx
0x180001d7e  inc     rax
0x180001d81  cmp     [rcx+rax], dil
0x180001d85  jnz     short loc_180001D7E
0x180001d87  inc     eax
0x180001d89  jmp     short loc_180001D91
0x180001d8b  mov     rcx, rsi
0x180001d8e  mov     eax, r8d
0x180001d91  mov     [rbp+0A0h+var_108], eax
0x180001d94  mov     rax, [rbp+0A0h+arg_38]
0x180001d9b  mov     [rbp+0A0h+var_120], rax
0x180001d9f  mov     rax, [rbp+0A0h+arg_30]
0x180001da6  mov     [rbp+0A0h+var_110], rcx
0x180001daa  mov     [rbp+0A0h+var_104], edi
0x180001dad  mov     [rbp+0A0h+var_118], 4
0x180001db5  mov     rcx, [rax]
0x180001db8  test    rcx, rcx
0x180001dbb  jz      short loc_180001DCC
0x180001dbd  inc     rdx
0x180001dc0  cmp     [rcx+rdx], dil
0x180001dc4  jnz     short loc_180001DBD
0x180001dc6  lea     r8d, [rdx+1]
0x180001dca  jmp     short loc_180001DCF
0x180001dcc  mov     rcx, rsi
0x180001dcf  mov     rax, [rbp+0A0h+arg_28]
0x180001dd6  xor     r9d, r9d
0x180001dd9  mov     [rsp+1A0h+var_140], rax
0x180001dde  mov     rdx, r11
0x180001de1  mov     rax, [rbp+0A0h+arg_20]
0x180001de8  mov     [rsp+1A0h+var_150], rax
0x180001ded  lea     rax, [rsp+1A0h+var_170]
0x180001df2  mov     [rsp+1A0h+var_130], rcx
0x180001df7  mov     rcx, r10
0x180001dfa  mov     [rsp+1A0h+var_128], r8d
0x180001dff  mov     r8, rbx
0x180001e02  mov     [rsp+1A0h+var_178], rax
0x180001e07  mov     [rsp+1A0h+var_180], 14h
0x180001e0f  mov     [rsp+1A0h+var_124], edi
0x180001e13  mov     [rsp+1A0h+var_138], 4
0x180001e1c  mov     [rsp+1A0h+var_148], 8
0x180001e25  call    _tlgWriteTransfer_EventWriteTransfer
0x180001e2a  mov     rcx, [rbp+0A0h+var_30]
0x180001e2e  xor     rcx, rsp; StackCookie
0x180001e31  call    __security_check_cookie
0x180001e36  add     rsp, 180h
0x180001e3d  pop     r15
0x180001e3f  pop     rdi
0x180001e40  pop     rsi
0x180001e41  pop     rbx
0x180001e42  pop     rbp
0x180001e43  retn
```
