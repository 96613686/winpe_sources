# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x1800019a0`
- end: `0x180001c3b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a970`

## callees

- `0x18000163c`
- `0x1800019a0`
- `0x18000e990`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const wchar_t **a7,
        __int64 a8,
        const wchar_t **a9,
        __int64 a10,
        char **a11,
        __int64 a12,
        const wchar_t **a13,
        __int64 a14,
        const wchar_t **a15,
        char **a16,
        __int64 a17,
        const wchar_t **a18,
        char **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  char *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const wchar_t *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  char *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const wchar_t *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const wchar_t *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  char *v40; // rcx
  __int64 v41; // rax
  const wchar_t *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const wchar_t *v45; // rcx
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  const wchar_t *v52; // [rsp+70h] [rbp-90h]
  int v53; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+7Ch] [rbp-84h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  const wchar_t *v57; // [rsp+90h] [rbp-70h]
  int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+9Ch] [rbp-64h]
  __int64 v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  char *v62; // [rsp+B0h] [rbp-50h]
  int v63; // [rsp+B8h] [rbp-48h]
  int v64; // [rsp+BCh] [rbp-44h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int64 v66; // [rsp+C8h] [rbp-38h]
  const wchar_t *v67; // [rsp+D0h] [rbp-30h]
  int v68; // [rsp+D8h] [rbp-28h]
  int v69; // [rsp+DCh] [rbp-24h]
  __int64 v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  const wchar_t *v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+FCh] [rbp-4h]
  char *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const wchar_t *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  char *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]

  v21 = -1;
  v23 = 2;
  v24 = *a19;
  if ( *a19 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)&v24[2 * v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = byte_1800138F4;
    v26 = 2;
  }
  v84 = v26;
  v27 = 1;
  v83 = v24;
  v85 = 0;
  v28 = *a18;
  if ( *a18 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &word_1800138F6;
    v30 = 1;
  }
  v81 = v30;
  v78 = a17;
  v80 = v28;
  v82 = 0;
  v79 = 4;
  v31 = *a16;
  if ( *a16 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *(_WORD *)&v31[2 * v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = byte_1800138F4;
    v33 = 2;
  }
  v76 = v33;
  v75 = v31;
  v77 = 0;
  v34 = *a15;
  if ( *a15 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &word_1800138F6;
    v36 = 1;
  }
  v73 = v36;
  v70 = a14;
  v72 = v34;
  v74 = 0;
  v71 = 4;
  v37 = *a13;
  if ( *a13 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &word_1800138F6;
    v39 = 1;
  }
  v68 = v39;
  v65 = a12;
  v67 = v37;
  v69 = 0;
  v66 = 4;
  v40 = *a11;
  if ( *a11 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *(_WORD *)&v40[2 * v41] );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = byte_1800138F4;
  }
  v60 = a10;
  v62 = v40;
  v63 = v23;
  v64 = 0;
  v42 = *a9;
  v61 = 4;
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
    v42 = &word_1800138F6;
    v44 = 1;
  }
  v58 = v44;
  v55 = a8;
  v57 = v42;
  v59 = 0;
  v56 = 4;
  v45 = *a7;
  if ( *a7 )
  {
    do
      ++v21;
    while ( *((_BYTE *)v45 + v21) );
    v27 = v21 + 1;
  }
  else
  {
    v45 = &word_1800138F6;
  }
  v50 = a6;
  v48 = a5;
  v52 = v45;
  v53 = v27;
  v54 = 0;
  v51 = 4;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x11u, &v47);
}

```

## disassembly

```asm
0x1800019a0  push    rbp
0x1800019a2  push    rbx
0x1800019a3  push    rsi
0x1800019a4  push    rdi
0x1800019a5  push    r14
0x1800019a7  lea     rbp, [rsp-50h]
0x1800019ac  sub     rsp, 150h
0x1800019b3  mov     rax, cs:__security_cookie
0x1800019ba  xor     rax, rsp
0x1800019bd  mov     [rbp+70h+var_30], rax
0x1800019c1  mov     rax, [rbp+70h+arg_90]
0x1800019c8  mov     r11, rdx
0x1800019cb  mov     r10, rcx
0x1800019ce  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800019d2  xor     edi, edi
0x1800019d4  mov     rbx, r8
0x1800019d7  mov     r9d, 2
0x1800019dd  mov     rcx, [rax]
0x1800019e0  test    rcx, rcx
0x1800019e3  jz      short loc_1800019FA
0x1800019e5  mov     rax, rdx
0x1800019e8  inc     rax
0x1800019eb  cmp     [rcx+rax*2], di
0x1800019ef  jnz     short loc_1800019E8
0x1800019f1  lea     eax, ds:2[rax*2]
0x1800019f8  jmp     short loc_180001A04
0x1800019fa  lea     rcx, byte_1800138F4
0x180001a01  mov     eax, r9d
0x180001a04  mov     [rbp+70h+var_38], eax
0x180001a07  lea     rsi, word_1800138F6
0x180001a0e  mov     rax, [rbp+70h+arg_88]
0x180001a15  mov     r8d, 1
0x180001a1b  mov     [rbp+70h+var_40], rcx
0x180001a1f  mov     [rbp+70h+var_34], edi
0x180001a22  mov     rcx, [rax]
0x180001a25  test    rcx, rcx
0x180001a28  jz      short loc_180001A3A
0x180001a2a  mov     rax, rdx
0x180001a2d  inc     rax
0x180001a30  cmp     [rcx+rax], dil
0x180001a34  jnz     short loc_180001A2D
0x180001a36  inc     eax
0x180001a38  jmp     short loc_180001A40
0x180001a3a  mov     rcx, rsi
0x180001a3d  mov     eax, r8d
0x180001a40  mov     [rbp+70h+var_48], eax
0x180001a43  mov     rax, [rbp+70h+arg_80]
0x180001a4a  mov     [rbp+70h+var_60], rax
0x180001a4e  mov     rax, [rbp+70h+arg_78]
0x180001a55  mov     [rbp+70h+var_50], rcx
0x180001a59  mov     [rbp+70h+var_44], edi
0x180001a5c  mov     [rbp+70h+var_58], 4
0x180001a64  mov     rcx, [rax]
0x180001a67  test    rcx, rcx
0x180001a6a  jz      short loc_180001A81
0x180001a6c  mov     rax, rdx
0x180001a6f  inc     rax
0x180001a72  cmp     [rcx+rax*2], di
0x180001a76  jnz     short loc_180001A6F
0x180001a78  lea     eax, ds:2[rax*2]
0x180001a7f  jmp     short loc_180001A8B
0x180001a81  lea     rcx, byte_1800138F4
0x180001a88  mov     eax, r9d
0x180001a8b  mov     [rbp+70h+var_68], eax
0x180001a8e  mov     rax, [rbp+70h+arg_70]
0x180001a95  mov     [rbp+70h+var_70], rcx
0x180001a99  mov     [rbp+70h+var_64], edi
0x180001a9c  mov     rcx, [rax]
0x180001a9f  test    rcx, rcx
0x180001aa2  jz      short loc_180001AB4
0x180001aa4  mov     rax, rdx
0x180001aa7  inc     rax
0x180001aaa  cmp     [rcx+rax], dil
0x180001aae  jnz     short loc_180001AA7
0x180001ab0  inc     eax
0x180001ab2  jmp     short loc_180001ABA
0x180001ab4  mov     rcx, rsi
0x180001ab7  mov     eax, r8d
0x180001aba  mov     [rbp+70h+var_78], eax
0x180001abd  mov     rax, [rbp+70h+arg_68]
0x180001ac4  mov     [rbp+70h+var_90], rax
0x180001ac8  mov     rax, [rbp+70h+arg_60]
0x180001acf  mov     [rbp+70h+var_80], rcx
0x180001ad3  mov     [rbp+70h+var_74], edi
0x180001ad6  mov     [rbp+70h+var_88], 4
0x180001ade  mov     rcx, [rax]
0x180001ae1  test    rcx, rcx
0x180001ae4  jz      short loc_180001AF6
0x180001ae6  mov     rax, rdx
0x180001ae9  inc     rax
0x180001aec  cmp     [rcx+rax], dil
0x180001af0  jnz     short loc_180001AE9
0x180001af2  inc     eax
0x180001af4  jmp     short loc_180001AFC
0x180001af6  mov     rcx, rsi
0x180001af9  mov     eax, r8d
0x180001afc  mov     [rbp+70h+var_98], eax
0x180001aff  mov     rax, [rbp+70h+arg_58]
0x180001b06  mov     [rbp+70h+var_B0], rax
0x180001b0a  mov     rax, [rbp+70h+arg_50]
0x180001b11  mov     [rbp+70h+var_A0], rcx
0x180001b15  mov     [rbp+70h+var_94], edi
0x180001b18  mov     [rbp+70h+var_A8], 4
0x180001b20  mov     rcx, [rax]
0x180001b23  test    rcx, rcx
0x180001b26  jz      short loc_180001B3E
0x180001b28  mov     rax, rdx
0x180001b2b  inc     rax
0x180001b2e  cmp     [rcx+rax*2], di
0x180001b32  jnz     short loc_180001B2B
0x180001b34  lea     r9d, ds:2[rax*2]
0x180001b3c  jmp     short loc_180001B45
0x180001b3e  lea     rcx, byte_1800138F4
0x180001b45  mov     rax, [rbp+70h+arg_48]
0x180001b4c  mov     [rbp+70h+var_D0], rax
0x180001b50  mov     rax, [rbp+70h+arg_40]
0x180001b57  mov     [rbp+70h+var_C0], rcx
0x180001b5b  mov     [rbp+70h+var_B8], r9d
0x180001b5f  mov     [rbp+70h+var_B4], edi
0x180001b62  mov     rcx, [rax]
0x180001b65  mov     [rbp+70h+var_C8], 4
0x180001b6d  test    rcx, rcx
0x180001b70  jz      short loc_180001B82
0x180001b72  mov     rax, rdx
0x180001b75  inc     rax
0x180001b78  cmp     [rcx+rax], dil
0x180001b7c  jnz     short loc_180001B75
0x180001b7e  inc     eax
0x180001b80  jmp     short loc_180001B88
0x180001b82  mov     rcx, rsi
0x180001b85  mov     eax, r8d
0x180001b88  mov     [rbp+70h+var_D8], eax
0x180001b8b  mov     rax, [rbp+70h+arg_38]
0x180001b92  mov     [rbp+70h+var_F0], rax
0x180001b96  mov     rax, [rbp+70h+arg_30]
0x180001b9d  mov     [rbp+70h+var_E0], rcx
0x180001ba1  mov     [rbp+70h+var_D4], edi
0x180001ba4  mov     [rbp+70h+var_E8], 4
0x180001bac  mov     rcx, [rax]
0x180001baf  test    rcx, rcx
0x180001bb2  jz      short loc_180001BC3
0x180001bb4  inc     rdx
0x180001bb7  cmp     [rcx+rdx], dil
0x180001bbb  jnz     short loc_180001BB4
0x180001bbd  lea     r8d, [rdx+1]
0x180001bc1  jmp     short loc_180001BC6
0x180001bc3  mov     rcx, rsi
0x180001bc6  mov     rax, [rbp+70h+arg_28]
0x180001bcd  xor     r9d, r9d
0x180001bd0  mov     [rsp+170h+var_110], rax
0x180001bd5  mov     rdx, r11
0x180001bd8  mov     rax, [rbp+70h+arg_20]
0x180001bdf  mov     [rsp+170h+var_120], rax
0x180001be4  lea     rax, [rsp+170h+var_140]
0x180001be9  mov     [rsp+170h+var_100], rcx
0x180001bee  mov     rcx, r10
0x180001bf1  mov     [rsp+170h+var_F8], r8d
0x180001bf6  mov     r8, rbx
0x180001bf9  mov     [rsp+170h+var_148], rax
0x180001bfe  mov     [rsp+170h+var_150], 11h
0x180001c06  mov     [rsp+170h+var_F4], edi
0x180001c0a  mov     [rsp+170h+var_108], 4
0x180001c13  mov     [rsp+170h+var_118], 8
0x180001c1c  call    _tlgWriteTransfer_EventWriteTransfer
0x180001c21  mov     rcx, [rbp+70h+var_30]
0x180001c25  xor     rcx, rsp; StackCookie
0x180001c28  call    __security_check_cookie
0x180001c2d  add     rsp, 150h
0x180001c34  pop     r14
0x180001c36  pop     rdi
0x180001c37  pop     rsi
0x180001c38  pop     rbx
0x180001c39  pop     rbp
0x180001c3a  retn
```
