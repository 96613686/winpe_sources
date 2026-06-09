# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x180001a7c`
- end: `0x180001d17`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `667`
- prototype: `__int64 __fastcall(int, int, int, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, char **, __int64, const wchar_t **, __int64, const wchar_t **, char **, __int64, const wchar_t **, char **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c830`

## callees

- `0x180001350`
- `0x180001a7c`
- `0x180010310`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        int a1,
        int a2,
        int a3,
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
    v24 = byte_180018020;
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
    v28 = &word_180018022;
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
    v31 = byte_180018020;
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
    v34 = &word_180018022;
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
    v37 = &word_180018022;
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
    v40 = byte_180018020;
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
    v42 = &word_180018022;
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
    v45 = &word_180018022;
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
0x180001a7c  push    rbp
0x180001a7e  push    rbx
0x180001a7f  push    rsi
0x180001a80  push    rdi
0x180001a81  push    r14
0x180001a83  lea     rbp, [rsp-50h]
0x180001a88  sub     rsp, 150h
0x180001a8f  mov     rax, cs:__security_cookie
0x180001a96  xor     rax, rsp
0x180001a99  mov     [rbp+70h+var_30], rax
0x180001a9d  mov     rax, [rbp+70h+arg_90]
0x180001aa4  mov     r11, rdx
0x180001aa7  mov     r10, rcx
0x180001aaa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001aae  xor     edi, edi
0x180001ab0  mov     rbx, r8
0x180001ab3  mov     r9d, 2
0x180001ab9  mov     rcx, [rax]
0x180001abc  test    rcx, rcx
0x180001abf  jz      short loc_180001AD6
0x180001ac1  mov     rax, rdx
0x180001ac4  inc     rax
0x180001ac7  cmp     [rcx+rax*2], di
0x180001acb  jnz     short loc_180001AC4
0x180001acd  lea     eax, ds:2[rax*2]
0x180001ad4  jmp     short loc_180001AE0
0x180001ad6  lea     rcx, byte_180018020
0x180001add  mov     eax, r9d
0x180001ae0  mov     [rbp+70h+var_38], eax
0x180001ae3  lea     rsi, word_180018022
0x180001aea  mov     rax, [rbp+70h+arg_88]
0x180001af1  mov     r8d, 1
0x180001af7  mov     [rbp+70h+var_40], rcx
0x180001afb  mov     [rbp+70h+var_34], edi
0x180001afe  mov     rcx, [rax]
0x180001b01  test    rcx, rcx
0x180001b04  jz      short loc_180001B16
0x180001b06  mov     rax, rdx
0x180001b09  inc     rax
0x180001b0c  cmp     [rcx+rax], dil
0x180001b10  jnz     short loc_180001B09
0x180001b12  inc     eax
0x180001b14  jmp     short loc_180001B1C
0x180001b16  mov     rcx, rsi
0x180001b19  mov     eax, r8d
0x180001b1c  mov     [rbp+70h+var_48], eax
0x180001b1f  mov     rax, [rbp+70h+arg_80]
0x180001b26  mov     [rbp+70h+var_60], rax
0x180001b2a  mov     rax, [rbp+70h+arg_78]
0x180001b31  mov     [rbp+70h+var_50], rcx
0x180001b35  mov     [rbp+70h+var_44], edi
0x180001b38  mov     [rbp+70h+var_58], 4
0x180001b40  mov     rcx, [rax]
0x180001b43  test    rcx, rcx
0x180001b46  jz      short loc_180001B5D
0x180001b48  mov     rax, rdx
0x180001b4b  inc     rax
0x180001b4e  cmp     [rcx+rax*2], di
0x180001b52  jnz     short loc_180001B4B
0x180001b54  lea     eax, ds:2[rax*2]
0x180001b5b  jmp     short loc_180001B67
0x180001b5d  lea     rcx, byte_180018020
0x180001b64  mov     eax, r9d
0x180001b67  mov     [rbp+70h+var_68], eax
0x180001b6a  mov     rax, [rbp+70h+arg_70]
0x180001b71  mov     [rbp+70h+var_70], rcx
0x180001b75  mov     [rbp+70h+var_64], edi
0x180001b78  mov     rcx, [rax]
0x180001b7b  test    rcx, rcx
0x180001b7e  jz      short loc_180001B90
0x180001b80  mov     rax, rdx
0x180001b83  inc     rax
0x180001b86  cmp     [rcx+rax], dil
0x180001b8a  jnz     short loc_180001B83
0x180001b8c  inc     eax
0x180001b8e  jmp     short loc_180001B96
0x180001b90  mov     rcx, rsi
0x180001b93  mov     eax, r8d
0x180001b96  mov     [rbp+70h+var_78], eax
0x180001b99  mov     rax, [rbp+70h+arg_68]
0x180001ba0  mov     [rbp+70h+var_90], rax
0x180001ba4  mov     rax, [rbp+70h+arg_60]
0x180001bab  mov     [rbp+70h+var_80], rcx
0x180001baf  mov     [rbp+70h+var_74], edi
0x180001bb2  mov     [rbp+70h+var_88], 4
0x180001bba  mov     rcx, [rax]
0x180001bbd  test    rcx, rcx
0x180001bc0  jz      short loc_180001BD2
0x180001bc2  mov     rax, rdx
0x180001bc5  inc     rax
0x180001bc8  cmp     [rcx+rax], dil
0x180001bcc  jnz     short loc_180001BC5
0x180001bce  inc     eax
0x180001bd0  jmp     short loc_180001BD8
0x180001bd2  mov     rcx, rsi
0x180001bd5  mov     eax, r8d
0x180001bd8  mov     [rbp+70h+var_98], eax
0x180001bdb  mov     rax, [rbp+70h+arg_58]
0x180001be2  mov     [rbp+70h+var_B0], rax
0x180001be6  mov     rax, [rbp+70h+arg_50]
0x180001bed  mov     [rbp+70h+var_A0], rcx
0x180001bf1  mov     [rbp+70h+var_94], edi
0x180001bf4  mov     [rbp+70h+var_A8], 4
0x180001bfc  mov     rcx, [rax]
0x180001bff  test    rcx, rcx
0x180001c02  jz      short loc_180001C1A
0x180001c04  mov     rax, rdx
0x180001c07  inc     rax
0x180001c0a  cmp     [rcx+rax*2], di
0x180001c0e  jnz     short loc_180001C07
0x180001c10  lea     r9d, ds:2[rax*2]
0x180001c18  jmp     short loc_180001C21
0x180001c1a  lea     rcx, byte_180018020
0x180001c21  mov     rax, [rbp+70h+arg_48]
0x180001c28  mov     [rbp+70h+var_D0], rax
0x180001c2c  mov     rax, [rbp+70h+arg_40]
0x180001c33  mov     [rbp+70h+var_C0], rcx
0x180001c37  mov     [rbp+70h+var_B8], r9d
0x180001c3b  mov     [rbp+70h+var_B4], edi
0x180001c3e  mov     rcx, [rax]
0x180001c41  mov     [rbp+70h+var_C8], 4
0x180001c49  test    rcx, rcx
0x180001c4c  jz      short loc_180001C5E
0x180001c4e  mov     rax, rdx
0x180001c51  inc     rax
0x180001c54  cmp     [rcx+rax], dil
0x180001c58  jnz     short loc_180001C51
0x180001c5a  inc     eax
0x180001c5c  jmp     short loc_180001C64
0x180001c5e  mov     rcx, rsi
0x180001c61  mov     eax, r8d
0x180001c64  mov     [rbp+70h+var_D8], eax
0x180001c67  mov     rax, [rbp+70h+arg_38]
0x180001c6e  mov     [rbp+70h+var_F0], rax
0x180001c72  mov     rax, [rbp+70h+arg_30]
0x180001c79  mov     [rbp+70h+var_E0], rcx
0x180001c7d  mov     [rbp+70h+var_D4], edi
0x180001c80  mov     [rbp+70h+var_E8], 4
0x180001c88  mov     rcx, [rax]
0x180001c8b  test    rcx, rcx
0x180001c8e  jz      short loc_180001C9F
0x180001c90  inc     rdx
0x180001c93  cmp     [rcx+rdx], dil
0x180001c97  jnz     short loc_180001C90
0x180001c99  lea     r8d, [rdx+1]
0x180001c9d  jmp     short loc_180001CA2
0x180001c9f  mov     rcx, rsi
0x180001ca2  mov     rax, [rbp+70h+arg_28]
0x180001ca9  xor     r9d, r9d; int
0x180001cac  mov     [rsp+170h+var_110], rax
0x180001cb1  mov     rdx, r11; int
0x180001cb4  mov     rax, [rbp+70h+arg_20]
0x180001cbb  mov     [rsp+170h+var_120], rax
0x180001cc0  lea     rax, [rsp+170h+var_140]
0x180001cc5  mov     [rsp+170h+var_100], rcx
0x180001cca  mov     rcx, r10; int
0x180001ccd  mov     [rsp+170h+var_F8], r8d
0x180001cd2  mov     r8, rbx; int
0x180001cd5  mov     [rsp+170h+var_148], rax; PEVENT_DATA_DESCRIPTOR
0x180001cda  mov     [rsp+170h+var_150], 11h; ULONG
0x180001ce2  mov     [rsp+170h+var_F4], edi
0x180001ce6  mov     [rsp+170h+var_108], 4
0x180001cef  mov     [rsp+170h+var_118], 8
0x180001cf8  call    _tlgWriteTransfer_EventWriteTransfer
0x180001cfd  mov     rcx, [rbp+70h+var_30]
0x180001d01  xor     rcx, rsp; StackCookie
0x180001d04  call    __security_check_cookie
0x180001d09  add     rsp, 150h
0x180001d10  pop     r14
0x180001d12  pop     rdi
0x180001d13  pop     rsi
0x180001d14  pop     rbx
0x180001d15  pop     rbp
0x180001d16  retn
```
