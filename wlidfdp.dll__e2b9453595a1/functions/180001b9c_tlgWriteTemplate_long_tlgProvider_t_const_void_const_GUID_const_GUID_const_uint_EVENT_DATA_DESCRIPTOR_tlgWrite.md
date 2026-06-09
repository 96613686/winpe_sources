# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001b9c`
- end: `0x180001e8c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, char **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, char **, __int64, const unsigned __int16 **, char **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cae0`
- `0x18000d510`

## callees

- `0x180001b9c`
- `0x180002018`
- `0x1800027f0`

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
        char **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        char **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        char **a19,
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
  char *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  char *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  char *v46; // rcx
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
  char *v68; // [rsp+B0h] [rbp-50h]
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
  char *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  char *v89; // [rsp+130h] [rbp+30h]
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
    v27 = &word_180017D52;
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
    while ( *(_WORD *)&v31[2 * v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = byte_180017D50;
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
    v34 = &word_180017D52;
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
    while ( *(_WORD *)&v37[2 * v38] );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = byte_180017D50;
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
    v40 = &word_180017D52;
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
    v43 = &word_180017D52;
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
    while ( *(_WORD *)&v46[2 * v47] );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = byte_180017D50;
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
    v48 = &word_180017D52;
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
    v51 = &word_180017D52;
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
0x180001b9c  push    rbp
0x180001b9e  push    rbx
0x180001b9f  push    rsi
0x180001ba0  push    rdi
0x180001ba1  push    r15
0x180001ba3  lea     rbp, [rsp-80h]
0x180001ba8  sub     rsp, 180h
0x180001baf  mov     rax, cs:__security_cookie
0x180001bb6  xor     rax, rsp
0x180001bb9  mov     [rbp+0A0h+var_30], rax
0x180001bbd  mov     rax, [rbp+0A0h+arg_A8]
0x180001bc4  lea     rsi, word_180017D52
0x180001bcb  mov     r11, rdx
0x180001bce  mov     r10, rcx
0x180001bd1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001bd5  xor     edi, edi
0x180001bd7  mov     rbx, r8
0x180001bda  mov     r8d, 1
0x180001be0  mov     rcx, [rax]
0x180001be3  test    rcx, rcx
0x180001be6  jz      short loc_180001BF8
0x180001be8  mov     rax, rdx
0x180001beb  inc     rax
0x180001bee  cmp     [rcx+rax], dil
0x180001bf2  jnz     short loc_180001BEB
0x180001bf4  inc     eax
0x180001bf6  jmp     short loc_180001BFE
0x180001bf8  mov     rcx, rsi
0x180001bfb  mov     eax, r8d
0x180001bfe  mov     [rbp+0A0h+var_38], eax
0x180001c01  mov     r9d, 2
0x180001c07  mov     rax, [rbp+0A0h+arg_A0]
0x180001c0e  mov     [rbp+0A0h+var_50], rax
0x180001c12  mov     rax, [rbp+0A0h+arg_98]
0x180001c19  mov     [rbp+0A0h+var_60], rax
0x180001c1d  mov     rax, [rbp+0A0h+arg_90]
0x180001c24  mov     [rbp+0A0h+var_40], rcx
0x180001c28  mov     [rbp+0A0h+var_34], edi
0x180001c2b  mov     [rbp+0A0h+var_48], 4
0x180001c33  mov     rcx, [rax]
0x180001c36  mov     [rbp+0A0h+var_58], 4
0x180001c3e  test    rcx, rcx
0x180001c41  jz      short loc_180001C58
0x180001c43  mov     rax, rdx
0x180001c46  inc     rax
0x180001c49  cmp     [rcx+rax*2], di
0x180001c4d  jnz     short loc_180001C46
0x180001c4f  lea     eax, ds:2[rax*2]
0x180001c56  jmp     short loc_180001C62
0x180001c58  lea     rcx, byte_180017D50
0x180001c5f  mov     eax, r9d
0x180001c62  mov     [rbp+0A0h+var_68], eax
0x180001c65  mov     rax, [rbp+0A0h+arg_88]
0x180001c6c  mov     [rbp+0A0h+var_70], rcx
0x180001c70  mov     [rbp+0A0h+var_64], edi
0x180001c73  mov     rcx, [rax]
0x180001c76  test    rcx, rcx
0x180001c79  jz      short loc_180001C8B
0x180001c7b  mov     rax, rdx
0x180001c7e  inc     rax
0x180001c81  cmp     [rcx+rax], dil
0x180001c85  jnz     short loc_180001C7E
0x180001c87  inc     eax
0x180001c89  jmp     short loc_180001C91
0x180001c8b  mov     rcx, rsi
0x180001c8e  mov     eax, r8d
0x180001c91  mov     [rbp+0A0h+var_78], eax
0x180001c94  mov     rax, [rbp+0A0h+arg_80]
0x180001c9b  mov     [rbp+0A0h+var_90], rax
0x180001c9f  mov     rax, [rbp+0A0h+arg_78]
0x180001ca6  mov     [rbp+0A0h+var_80], rcx
0x180001caa  mov     [rbp+0A0h+var_74], edi
0x180001cad  mov     [rbp+0A0h+var_88], 4
0x180001cb5  mov     rcx, [rax]
0x180001cb8  test    rcx, rcx
0x180001cbb  jz      short loc_180001CD2
0x180001cbd  mov     rax, rdx
0x180001cc0  inc     rax
0x180001cc3  cmp     [rcx+rax*2], di
0x180001cc7  jnz     short loc_180001CC0
0x180001cc9  lea     eax, ds:2[rax*2]
0x180001cd0  jmp     short loc_180001CDC
0x180001cd2  lea     rcx, byte_180017D50
0x180001cd9  mov     eax, r9d
0x180001cdc  mov     [rbp+0A0h+var_98], eax
0x180001cdf  mov     rax, [rbp+0A0h+arg_70]
0x180001ce6  mov     [rbp+0A0h+var_A0], rcx
0x180001cea  mov     [rbp+0A0h+var_94], edi
0x180001ced  mov     rcx, [rax]
0x180001cf0  test    rcx, rcx
0x180001cf3  jz      short loc_180001D05
0x180001cf5  mov     rax, rdx
0x180001cf8  inc     rax
0x180001cfb  cmp     [rcx+rax], dil
0x180001cff  jnz     short loc_180001CF8
0x180001d01  inc     eax
0x180001d03  jmp     short loc_180001D0B
0x180001d05  mov     rcx, rsi
0x180001d08  mov     eax, r8d
0x180001d0b  mov     [rbp+0A0h+var_A8], eax
0x180001d0e  mov     rax, [rbp+0A0h+arg_68]
0x180001d15  mov     [rbp+0A0h+var_C0], rax
0x180001d19  mov     rax, [rbp+0A0h+arg_60]
0x180001d20  mov     [rbp+0A0h+var_B0], rcx
0x180001d24  mov     [rbp+0A0h+var_A4], edi
0x180001d27  mov     [rbp+0A0h+var_B8], 4
0x180001d2f  mov     rcx, [rax]
0x180001d32  test    rcx, rcx
0x180001d35  jz      short loc_180001D47
0x180001d37  mov     rax, rdx
0x180001d3a  inc     rax
0x180001d3d  cmp     [rcx+rax], dil
0x180001d41  jnz     short loc_180001D3A
0x180001d43  inc     eax
0x180001d45  jmp     short loc_180001D4D
0x180001d47  mov     rcx, rsi
0x180001d4a  mov     eax, r8d
0x180001d4d  mov     [rbp+0A0h+var_C8], eax
0x180001d50  mov     rax, [rbp+0A0h+arg_58]
0x180001d57  mov     [rbp+0A0h+var_E0], rax
0x180001d5b  mov     rax, [rbp+0A0h+arg_50]
0x180001d62  mov     [rbp+0A0h+var_D0], rcx
0x180001d66  mov     [rbp+0A0h+var_C4], edi
0x180001d69  mov     [rbp+0A0h+var_D8], 4
0x180001d71  mov     rcx, [rax]
0x180001d74  test    rcx, rcx
0x180001d77  jz      short loc_180001D8F
0x180001d79  mov     rax, rdx
0x180001d7c  inc     rax
0x180001d7f  cmp     [rcx+rax*2], di
0x180001d83  jnz     short loc_180001D7C
0x180001d85  lea     r9d, ds:2[rax*2]
0x180001d8d  jmp     short loc_180001D96
0x180001d8f  lea     rcx, byte_180017D50
0x180001d96  mov     rax, [rbp+0A0h+arg_48]
0x180001d9d  mov     [rbp+0A0h+var_100], rax
0x180001da1  mov     rax, [rbp+0A0h+arg_40]
0x180001da8  mov     [rbp+0A0h+var_F0], rcx
0x180001dac  mov     [rbp+0A0h+var_E8], r9d
0x180001db0  mov     [rbp+0A0h+var_E4], edi
0x180001db3  mov     rcx, [rax]
0x180001db6  mov     [rbp+0A0h+var_F8], 4
0x180001dbe  test    rcx, rcx
0x180001dc1  jz      short loc_180001DD3
0x180001dc3  mov     rax, rdx
0x180001dc6  inc     rax
0x180001dc9  cmp     [rcx+rax], dil
0x180001dcd  jnz     short loc_180001DC6
0x180001dcf  inc     eax
0x180001dd1  jmp     short loc_180001DD9
0x180001dd3  mov     rcx, rsi
0x180001dd6  mov     eax, r8d
0x180001dd9  mov     [rbp+0A0h+var_108], eax
0x180001ddc  mov     rax, [rbp+0A0h+arg_38]
0x180001de3  mov     [rbp+0A0h+var_120], rax
0x180001de7  mov     rax, [rbp+0A0h+arg_30]
0x180001dee  mov     [rbp+0A0h+var_110], rcx
0x180001df2  mov     [rbp+0A0h+var_104], edi
0x180001df5  mov     [rbp+0A0h+var_118], 4
0x180001dfd  mov     rcx, [rax]
0x180001e00  test    rcx, rcx
0x180001e03  jz      short loc_180001E14
0x180001e05  inc     rdx
0x180001e08  cmp     [rcx+rdx], dil
0x180001e0c  jnz     short loc_180001E05
0x180001e0e  lea     r8d, [rdx+1]
0x180001e12  jmp     short loc_180001E17
0x180001e14  mov     rcx, rsi
0x180001e17  mov     rax, [rbp+0A0h+arg_28]
0x180001e1e  xor     r9d, r9d
0x180001e21  mov     [rsp+1A0h+var_140], rax
0x180001e26  mov     rdx, r11
0x180001e29  mov     rax, [rbp+0A0h+arg_20]
0x180001e30  mov     [rsp+1A0h+var_150], rax
0x180001e35  lea     rax, [rsp+1A0h+var_170]
0x180001e3a  mov     [rsp+1A0h+var_130], rcx
0x180001e3f  mov     rcx, r10
0x180001e42  mov     [rsp+1A0h+var_128], r8d
0x180001e47  mov     r8, rbx
0x180001e4a  mov     [rsp+1A0h+var_178], rax
0x180001e4f  mov     [rsp+1A0h+var_180], 14h
0x180001e57  mov     [rsp+1A0h+var_124], edi
0x180001e5b  mov     [rsp+1A0h+var_138], 4
0x180001e64  mov     [rsp+1A0h+var_148], 8
0x180001e6d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001e72  mov     rcx, [rbp+0A0h+var_30]
0x180001e76  xor     rcx, rsp; StackCookie
0x180001e79  call    __security_check_cookie
0x180001e7e  add     rsp, 180h
0x180001e85  pop     r15
0x180001e87  pop     rdi
0x180001e88  pop     rsi
0x180001e89  pop     rbx
0x180001e8a  pop     rbp
0x180001e8b  retn
```
