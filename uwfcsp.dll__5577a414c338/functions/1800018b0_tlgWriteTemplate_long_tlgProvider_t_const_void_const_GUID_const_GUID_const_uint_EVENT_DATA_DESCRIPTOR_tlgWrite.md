# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800018b0`
- end: `0x180001b4b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009890`

## callees

- `0x1800018b0`
- `0x180001ecc`
- `0x18001a210`

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
        int **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        int **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        int **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  int *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rcx
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
  int *v62; // [rsp+B0h] [rbp-50h]
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
  int *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  int *v83; // [rsp+130h] [rbp+30h]
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
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &dword_18001F7A4;
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
    v28 = &qword_18001EF80;
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
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_18001F7A4;
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
    v34 = &qword_18001EF80;
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
    v37 = &qword_18001EF80;
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
    while ( *((_WORD *)v40 + v41) );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &dword_18001F7A4;
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
    v42 = &qword_18001EF80;
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
    v45 = &qword_18001EF80;
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
0x1800018b0  push    rbp
0x1800018b2  push    rbx
0x1800018b3  push    rsi
0x1800018b4  push    rdi
0x1800018b5  push    r14
0x1800018b7  lea     rbp, [rsp-50h]
0x1800018bc  sub     rsp, 150h
0x1800018c3  mov     rax, cs:__security_cookie
0x1800018ca  xor     rax, rsp
0x1800018cd  mov     [rbp+70h+var_30], rax
0x1800018d1  mov     rax, [rbp+70h+arg_90]
0x1800018d8  mov     r11, rdx
0x1800018db  mov     r10, rcx
0x1800018de  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800018e2  xor     edi, edi
0x1800018e4  mov     rbx, r8
0x1800018e7  mov     r9d, 2
0x1800018ed  mov     rcx, [rax]
0x1800018f0  test    rcx, rcx
0x1800018f3  jz      short loc_18000190A
0x1800018f5  mov     rax, rdx
0x1800018f8  inc     rax
0x1800018fb  cmp     [rcx+rax*2], di
0x1800018ff  jnz     short loc_1800018F8
0x180001901  lea     eax, ds:2[rax*2]
0x180001908  jmp     short loc_180001914
0x18000190a  lea     rcx, dword_18001F7A4
0x180001911  mov     eax, r9d
0x180001914  mov     [rbp+70h+var_38], eax
0x180001917  lea     rsi, qword_18001EF80
0x18000191e  mov     rax, [rbp+70h+arg_88]
0x180001925  mov     r8d, 1
0x18000192b  mov     [rbp+70h+var_40], rcx
0x18000192f  mov     [rbp+70h+var_34], edi
0x180001932  mov     rcx, [rax]
0x180001935  test    rcx, rcx
0x180001938  jz      short loc_18000194A
0x18000193a  mov     rax, rdx
0x18000193d  inc     rax
0x180001940  cmp     [rcx+rax], dil
0x180001944  jnz     short loc_18000193D
0x180001946  inc     eax
0x180001948  jmp     short loc_180001950
0x18000194a  mov     rcx, rsi
0x18000194d  mov     eax, r8d
0x180001950  mov     [rbp+70h+var_48], eax
0x180001953  mov     rax, [rbp+70h+arg_80]
0x18000195a  mov     [rbp+70h+var_60], rax
0x18000195e  mov     rax, [rbp+70h+arg_78]
0x180001965  mov     [rbp+70h+var_50], rcx
0x180001969  mov     [rbp+70h+var_44], edi
0x18000196c  mov     [rbp+70h+var_58], 4
0x180001974  mov     rcx, [rax]
0x180001977  test    rcx, rcx
0x18000197a  jz      short loc_180001991
0x18000197c  mov     rax, rdx
0x18000197f  inc     rax
0x180001982  cmp     [rcx+rax*2], di
0x180001986  jnz     short loc_18000197F
0x180001988  lea     eax, ds:2[rax*2]
0x18000198f  jmp     short loc_18000199B
0x180001991  lea     rcx, dword_18001F7A4
0x180001998  mov     eax, r9d
0x18000199b  mov     [rbp+70h+var_68], eax
0x18000199e  mov     rax, [rbp+70h+arg_70]
0x1800019a5  mov     [rbp+70h+var_70], rcx
0x1800019a9  mov     [rbp+70h+var_64], edi
0x1800019ac  mov     rcx, [rax]
0x1800019af  test    rcx, rcx
0x1800019b2  jz      short loc_1800019C4
0x1800019b4  mov     rax, rdx
0x1800019b7  inc     rax
0x1800019ba  cmp     [rcx+rax], dil
0x1800019be  jnz     short loc_1800019B7
0x1800019c0  inc     eax
0x1800019c2  jmp     short loc_1800019CA
0x1800019c4  mov     rcx, rsi
0x1800019c7  mov     eax, r8d
0x1800019ca  mov     [rbp+70h+var_78], eax
0x1800019cd  mov     rax, [rbp+70h+arg_68]
0x1800019d4  mov     [rbp+70h+var_90], rax
0x1800019d8  mov     rax, [rbp+70h+arg_60]
0x1800019df  mov     [rbp+70h+var_80], rcx
0x1800019e3  mov     [rbp+70h+var_74], edi
0x1800019e6  mov     [rbp+70h+var_88], 4
0x1800019ee  mov     rcx, [rax]
0x1800019f1  test    rcx, rcx
0x1800019f4  jz      short loc_180001A06
0x1800019f6  mov     rax, rdx
0x1800019f9  inc     rax
0x1800019fc  cmp     [rcx+rax], dil
0x180001a00  jnz     short loc_1800019F9
0x180001a02  inc     eax
0x180001a04  jmp     short loc_180001A0C
0x180001a06  mov     rcx, rsi
0x180001a09  mov     eax, r8d
0x180001a0c  mov     [rbp+70h+var_98], eax
0x180001a0f  mov     rax, [rbp+70h+arg_58]
0x180001a16  mov     [rbp+70h+var_B0], rax
0x180001a1a  mov     rax, [rbp+70h+arg_50]
0x180001a21  mov     [rbp+70h+var_A0], rcx
0x180001a25  mov     [rbp+70h+var_94], edi
0x180001a28  mov     [rbp+70h+var_A8], 4
0x180001a30  mov     rcx, [rax]
0x180001a33  test    rcx, rcx
0x180001a36  jz      short loc_180001A4E
0x180001a38  mov     rax, rdx
0x180001a3b  inc     rax
0x180001a3e  cmp     [rcx+rax*2], di
0x180001a42  jnz     short loc_180001A3B
0x180001a44  lea     r9d, ds:2[rax*2]
0x180001a4c  jmp     short loc_180001A55
0x180001a4e  lea     rcx, dword_18001F7A4
0x180001a55  mov     rax, [rbp+70h+arg_48]
0x180001a5c  mov     [rbp+70h+var_D0], rax
0x180001a60  mov     rax, [rbp+70h+arg_40]
0x180001a67  mov     [rbp+70h+var_C0], rcx
0x180001a6b  mov     [rbp+70h+var_B8], r9d
0x180001a6f  mov     [rbp+70h+var_B4], edi
0x180001a72  mov     rcx, [rax]
0x180001a75  mov     [rbp+70h+var_C8], 4
0x180001a7d  test    rcx, rcx
0x180001a80  jz      short loc_180001A92
0x180001a82  mov     rax, rdx
0x180001a85  inc     rax
0x180001a88  cmp     [rcx+rax], dil
0x180001a8c  jnz     short loc_180001A85
0x180001a8e  inc     eax
0x180001a90  jmp     short loc_180001A98
0x180001a92  mov     rcx, rsi
0x180001a95  mov     eax, r8d
0x180001a98  mov     [rbp+70h+var_D8], eax
0x180001a9b  mov     rax, [rbp+70h+arg_38]
0x180001aa2  mov     [rbp+70h+var_F0], rax
0x180001aa6  mov     rax, [rbp+70h+arg_30]
0x180001aad  mov     [rbp+70h+var_E0], rcx
0x180001ab1  mov     [rbp+70h+var_D4], edi
0x180001ab4  mov     [rbp+70h+var_E8], 4
0x180001abc  mov     rcx, [rax]
0x180001abf  test    rcx, rcx
0x180001ac2  jz      short loc_180001AD3
0x180001ac4  inc     rdx
0x180001ac7  cmp     [rcx+rdx], dil
0x180001acb  jnz     short loc_180001AC4
0x180001acd  lea     r8d, [rdx+1]
0x180001ad1  jmp     short loc_180001AD6
0x180001ad3  mov     rcx, rsi
0x180001ad6  mov     rax, [rbp+70h+arg_28]
0x180001add  xor     r9d, r9d
0x180001ae0  mov     [rsp+170h+var_110], rax
0x180001ae5  mov     rdx, r11
0x180001ae8  mov     rax, [rbp+70h+arg_20]
0x180001aef  mov     [rsp+170h+var_120], rax
0x180001af4  lea     rax, [rsp+170h+var_140]
0x180001af9  mov     [rsp+170h+var_100], rcx
0x180001afe  mov     rcx, r10
0x180001b01  mov     [rsp+170h+var_F8], r8d
0x180001b06  mov     r8, rbx
0x180001b09  mov     [rsp+170h+var_148], rax
0x180001b0e  mov     [rsp+170h+var_150], 11h
0x180001b16  mov     [rsp+170h+var_F4], edi
0x180001b1a  mov     [rsp+170h+var_108], 4
0x180001b23  mov     [rsp+170h+var_118], 8
0x180001b2c  call    _tlgWriteTransfer_EventWriteTransfer
0x180001b31  mov     rcx, [rbp+70h+var_30]
0x180001b35  xor     rcx, rsp; StackCookie
0x180001b38  call    __security_check_cookie
0x180001b3d  add     rsp, 150h
0x180001b44  pop     r14
0x180001b46  pop     rdi
0x180001b47  pop     rsi
0x180001b48  pop     rbx
0x180001b49  pop     rbp
0x180001b4a  retn
```
