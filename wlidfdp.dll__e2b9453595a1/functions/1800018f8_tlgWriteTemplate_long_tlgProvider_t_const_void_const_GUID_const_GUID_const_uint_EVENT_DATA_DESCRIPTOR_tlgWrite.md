# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800018f8`
- end: `0x180001b93`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, char **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, char **, __int64, const unsigned __int16 **, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cae0`
- `0x18000d154`

## callees

- `0x1800018f8`
- `0x180002018`
- `0x1800027f0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        char **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  char *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  char *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  char *v40; // rcx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v52; // [rsp+70h] [rbp-90h]
  int v53; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+7Ch] [rbp-84h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v57; // [rsp+90h] [rbp-70h]
  int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+9Ch] [rbp-64h]
  __int64 v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  char *v62; // [rsp+B0h] [rbp-50h]
  int v63; // [rsp+B8h] [rbp-48h]
  int v64; // [rsp+BCh] [rbp-44h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int64 v66; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v67; // [rsp+D0h] [rbp-30h]
  int v68; // [rsp+D8h] [rbp-28h]
  int v69; // [rsp+DCh] [rbp-24h]
  __int64 v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+FCh] [rbp-4h]
  char *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
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
    v24 = byte_180017D50;
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
    v28 = &word_180017D52;
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
    v31 = byte_180017D50;
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
    v34 = &word_180017D52;
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
    v37 = &word_180017D52;
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
    v40 = byte_180017D50;
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
    v42 = &word_180017D52;
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
    v45 = &word_180017D52;
  }
  v50 = a6;
  v48 = a5;
  v52 = v45;
  v53 = v27;
  v54 = 0;
  v51 = 4;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 17, v47);
}

```

## disassembly

```asm
0x1800018f8  push    rbp
0x1800018fa  push    rbx
0x1800018fb  push    rsi
0x1800018fc  push    rdi
0x1800018fd  push    r14
0x1800018ff  lea     rbp, [rsp-50h]
0x180001904  sub     rsp, 150h
0x18000190b  mov     rax, cs:__security_cookie
0x180001912  xor     rax, rsp
0x180001915  mov     [rbp+70h+var_30], rax
0x180001919  mov     rax, [rbp+70h+arg_90]
0x180001920  mov     r11, rdx
0x180001923  mov     r10, rcx
0x180001926  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000192a  xor     edi, edi
0x18000192c  mov     rbx, r8
0x18000192f  mov     r9d, 2
0x180001935  mov     rcx, [rax]
0x180001938  test    rcx, rcx
0x18000193b  jz      short loc_180001952
0x18000193d  mov     rax, rdx
0x180001940  inc     rax
0x180001943  cmp     [rcx+rax*2], di
0x180001947  jnz     short loc_180001940
0x180001949  lea     eax, ds:2[rax*2]
0x180001950  jmp     short loc_18000195C
0x180001952  lea     rcx, byte_180017D50
0x180001959  mov     eax, r9d
0x18000195c  mov     [rbp+70h+var_38], eax
0x18000195f  lea     rsi, word_180017D52
0x180001966  mov     rax, [rbp+70h+arg_88]
0x18000196d  mov     r8d, 1
0x180001973  mov     [rbp+70h+var_40], rcx
0x180001977  mov     [rbp+70h+var_34], edi
0x18000197a  mov     rcx, [rax]
0x18000197d  test    rcx, rcx
0x180001980  jz      short loc_180001992
0x180001982  mov     rax, rdx
0x180001985  inc     rax
0x180001988  cmp     [rcx+rax], dil
0x18000198c  jnz     short loc_180001985
0x18000198e  inc     eax
0x180001990  jmp     short loc_180001998
0x180001992  mov     rcx, rsi
0x180001995  mov     eax, r8d
0x180001998  mov     [rbp+70h+var_48], eax
0x18000199b  mov     rax, [rbp+70h+arg_80]
0x1800019a2  mov     [rbp+70h+var_60], rax
0x1800019a6  mov     rax, [rbp+70h+arg_78]
0x1800019ad  mov     [rbp+70h+var_50], rcx
0x1800019b1  mov     [rbp+70h+var_44], edi
0x1800019b4  mov     [rbp+70h+var_58], 4
0x1800019bc  mov     rcx, [rax]
0x1800019bf  test    rcx, rcx
0x1800019c2  jz      short loc_1800019D9
0x1800019c4  mov     rax, rdx
0x1800019c7  inc     rax
0x1800019ca  cmp     [rcx+rax*2], di
0x1800019ce  jnz     short loc_1800019C7
0x1800019d0  lea     eax, ds:2[rax*2]
0x1800019d7  jmp     short loc_1800019E3
0x1800019d9  lea     rcx, byte_180017D50
0x1800019e0  mov     eax, r9d
0x1800019e3  mov     [rbp+70h+var_68], eax
0x1800019e6  mov     rax, [rbp+70h+arg_70]
0x1800019ed  mov     [rbp+70h+var_70], rcx
0x1800019f1  mov     [rbp+70h+var_64], edi
0x1800019f4  mov     rcx, [rax]
0x1800019f7  test    rcx, rcx
0x1800019fa  jz      short loc_180001A0C
0x1800019fc  mov     rax, rdx
0x1800019ff  inc     rax
0x180001a02  cmp     [rcx+rax], dil
0x180001a06  jnz     short loc_1800019FF
0x180001a08  inc     eax
0x180001a0a  jmp     short loc_180001A12
0x180001a0c  mov     rcx, rsi
0x180001a0f  mov     eax, r8d
0x180001a12  mov     [rbp+70h+var_78], eax
0x180001a15  mov     rax, [rbp+70h+arg_68]
0x180001a1c  mov     [rbp+70h+var_90], rax
0x180001a20  mov     rax, [rbp+70h+arg_60]
0x180001a27  mov     [rbp+70h+var_80], rcx
0x180001a2b  mov     [rbp+70h+var_74], edi
0x180001a2e  mov     [rbp+70h+var_88], 4
0x180001a36  mov     rcx, [rax]
0x180001a39  test    rcx, rcx
0x180001a3c  jz      short loc_180001A4E
0x180001a3e  mov     rax, rdx
0x180001a41  inc     rax
0x180001a44  cmp     [rcx+rax], dil
0x180001a48  jnz     short loc_180001A41
0x180001a4a  inc     eax
0x180001a4c  jmp     short loc_180001A54
0x180001a4e  mov     rcx, rsi
0x180001a51  mov     eax, r8d
0x180001a54  mov     [rbp+70h+var_98], eax
0x180001a57  mov     rax, [rbp+70h+arg_58]
0x180001a5e  mov     [rbp+70h+var_B0], rax
0x180001a62  mov     rax, [rbp+70h+arg_50]
0x180001a69  mov     [rbp+70h+var_A0], rcx
0x180001a6d  mov     [rbp+70h+var_94], edi
0x180001a70  mov     [rbp+70h+var_A8], 4
0x180001a78  mov     rcx, [rax]
0x180001a7b  test    rcx, rcx
0x180001a7e  jz      short loc_180001A96
0x180001a80  mov     rax, rdx
0x180001a83  inc     rax
0x180001a86  cmp     [rcx+rax*2], di
0x180001a8a  jnz     short loc_180001A83
0x180001a8c  lea     r9d, ds:2[rax*2]
0x180001a94  jmp     short loc_180001A9D
0x180001a96  lea     rcx, byte_180017D50
0x180001a9d  mov     rax, [rbp+70h+arg_48]
0x180001aa4  mov     [rbp+70h+var_D0], rax
0x180001aa8  mov     rax, [rbp+70h+arg_40]
0x180001aaf  mov     [rbp+70h+var_C0], rcx
0x180001ab3  mov     [rbp+70h+var_B8], r9d
0x180001ab7  mov     [rbp+70h+var_B4], edi
0x180001aba  mov     rcx, [rax]
0x180001abd  mov     [rbp+70h+var_C8], 4
0x180001ac5  test    rcx, rcx
0x180001ac8  jz      short loc_180001ADA
0x180001aca  mov     rax, rdx
0x180001acd  inc     rax
0x180001ad0  cmp     [rcx+rax], dil
0x180001ad4  jnz     short loc_180001ACD
0x180001ad6  inc     eax
0x180001ad8  jmp     short loc_180001AE0
0x180001ada  mov     rcx, rsi
0x180001add  mov     eax, r8d
0x180001ae0  mov     [rbp+70h+var_D8], eax
0x180001ae3  mov     rax, [rbp+70h+arg_38]
0x180001aea  mov     [rbp+70h+var_F0], rax
0x180001aee  mov     rax, [rbp+70h+arg_30]
0x180001af5  mov     [rbp+70h+var_E0], rcx
0x180001af9  mov     [rbp+70h+var_D4], edi
0x180001afc  mov     [rbp+70h+var_E8], 4
0x180001b04  mov     rcx, [rax]
0x180001b07  test    rcx, rcx
0x180001b0a  jz      short loc_180001B1B
0x180001b0c  inc     rdx
0x180001b0f  cmp     [rcx+rdx], dil
0x180001b13  jnz     short loc_180001B0C
0x180001b15  lea     r8d, [rdx+1]
0x180001b19  jmp     short loc_180001B1E
0x180001b1b  mov     rcx, rsi
0x180001b1e  mov     rax, [rbp+70h+arg_28]
0x180001b25  xor     r9d, r9d
0x180001b28  mov     [rsp+170h+var_110], rax
0x180001b2d  mov     rdx, r11
0x180001b30  mov     rax, [rbp+70h+arg_20]
0x180001b37  mov     [rsp+170h+var_120], rax
0x180001b3c  lea     rax, [rsp+170h+var_140]
0x180001b41  mov     [rsp+170h+var_100], rcx
0x180001b46  mov     rcx, r10
0x180001b49  mov     [rsp+170h+var_F8], r8d
0x180001b4e  mov     r8, rbx
0x180001b51  mov     [rsp+170h+var_148], rax
0x180001b56  mov     [rsp+170h+var_150], 11h
0x180001b5e  mov     [rsp+170h+var_F4], edi
0x180001b62  mov     [rsp+170h+var_108], 4
0x180001b6b  mov     [rsp+170h+var_118], 8
0x180001b74  call    _tlgWriteTransfer_EventWriteTransfer
0x180001b79  mov     rcx, [rbp+70h+var_30]
0x180001b7d  xor     rcx, rsp; StackCookie
0x180001b80  call    __security_check_cookie
0x180001b85  add     rsp, 150h
0x180001b8c  pop     r14
0x180001b8e  pop     rdi
0x180001b8f  pop     rsi
0x180001b90  pop     rbx
0x180001b91  pop     rbp
0x180001b92  retn
```
