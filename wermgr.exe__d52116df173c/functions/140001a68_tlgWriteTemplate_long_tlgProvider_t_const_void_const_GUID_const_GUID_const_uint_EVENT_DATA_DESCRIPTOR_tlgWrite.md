# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x140001a68`
- end: `0x140001d13`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, int **, __int64, const wchar_t **, __int64, const wchar_t **, int **, __int64, const wchar_t **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400179bc`

## callees

- `0x14000162c`
- `0x140001a68`
- `0x140003200`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const wchar_t **a8,
        __int64 a9,
        const wchar_t **a10,
        __int64 a11,
        int **a12,
        __int64 a13,
        const wchar_t **a14,
        __int64 a15,
        const wchar_t **a16,
        int **a17,
        __int64 a18,
        const wchar_t **a19,
        int **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  int *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const wchar_t *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const wchar_t *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const wchar_t *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rdx
  __int64 v41; // rax
  const wchar_t *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const wchar_t *v45; // rdx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  const wchar_t *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const wchar_t *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  int *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const wchar_t *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const wchar_t *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  int *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const wchar_t *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  int *v85; // [rsp+140h] [rbp+40h]
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
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &dword_1400241F4;
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
    v28 = &qword_140024070;
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
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_1400241F4;
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
    v34 = &qword_140024070;
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
    v37 = &qword_140024070;
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
    while ( *((_WORD *)v40 + v41) );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &dword_1400241F4;
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
    v42 = &qword_140024070;
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
    v45 = &qword_140024070;
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
0x140001a68  mov     [rsp-8+arg_10], rbx
0x140001a6d  push    rbp
0x140001a6e  push    rsi
0x140001a6f  push    rdi
0x140001a70  lea     rbp, [rsp-60h]
0x140001a75  sub     rsp, 160h
0x140001a7c  mov     rax, cs:__security_cookie
0x140001a83  xor     rax, rsp
0x140001a86  mov     [rbp+70h+var_20], rax
0x140001a8a  mov     rax, [rbp+70h+arg_98]
0x140001a91  mov     r11, rdx
0x140001a94  mov     r10, rcx
0x140001a97  xor     ebx, ebx
0x140001a99  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001a9d  mov     r9d, 2
0x140001aa3  mov     rdx, [rax]
0x140001aa6  test    rdx, rdx
0x140001aa9  jz      short loc_140001AC0
0x140001aab  mov     rax, rcx
0x140001aae  inc     rax
0x140001ab1  cmp     [rdx+rax*2], bx
0x140001ab5  jnz     short loc_140001AAE
0x140001ab7  lea     eax, ds:2[rax*2]
0x140001abe  jmp     short loc_140001ACA
0x140001ac0  lea     rdx, dword_1400241F4
0x140001ac7  mov     eax, r9d
0x140001aca  mov     [rbp+70h+var_28], eax
0x140001acd  lea     rdi, qword_140024070
0x140001ad4  mov     rax, [rbp+70h+arg_90]
0x140001adb  mov     r8d, 1
0x140001ae1  mov     [rbp+70h+var_30], rdx
0x140001ae5  mov     [rbp+70h+var_24], ebx
0x140001ae8  mov     rdx, [rax]
0x140001aeb  test    rdx, rdx
0x140001aee  jz      short loc_140001AFF
0x140001af0  mov     rax, rcx
0x140001af3  inc     rax
0x140001af6  cmp     [rdx+rax], bl
0x140001af9  jnz     short loc_140001AF3
0x140001afb  inc     eax
0x140001afd  jmp     short loc_140001B05
0x140001aff  mov     rdx, rdi
0x140001b02  mov     eax, r8d
0x140001b05  mov     [rbp+70h+var_38], eax
0x140001b08  mov     rax, [rbp+70h+arg_88]
0x140001b0f  mov     [rbp+70h+var_50], rax
0x140001b13  mov     rax, [rbp+70h+arg_80]
0x140001b1a  mov     [rbp+70h+var_40], rdx
0x140001b1e  mov     [rbp+70h+var_34], ebx
0x140001b21  mov     [rbp+70h+var_48], 4
0x140001b29  mov     rdx, [rax]
0x140001b2c  test    rdx, rdx
0x140001b2f  jz      short loc_140001B46
0x140001b31  mov     rax, rcx
0x140001b34  inc     rax
0x140001b37  cmp     [rdx+rax*2], bx
0x140001b3b  jnz     short loc_140001B34
0x140001b3d  lea     eax, ds:2[rax*2]
0x140001b44  jmp     short loc_140001B50
0x140001b46  lea     rdx, dword_1400241F4
0x140001b4d  mov     eax, r9d
0x140001b50  mov     [rbp+70h+var_58], eax
0x140001b53  mov     rax, [rbp+70h+arg_78]
0x140001b5a  mov     [rbp+70h+var_60], rdx
0x140001b5e  mov     [rbp+70h+var_54], ebx
0x140001b61  mov     rdx, [rax]
0x140001b64  test    rdx, rdx
0x140001b67  jz      short loc_140001B78
0x140001b69  mov     rax, rcx
0x140001b6c  inc     rax
0x140001b6f  cmp     [rdx+rax], bl
0x140001b72  jnz     short loc_140001B6C
0x140001b74  inc     eax
0x140001b76  jmp     short loc_140001B7E
0x140001b78  mov     rdx, rdi
0x140001b7b  mov     eax, r8d
0x140001b7e  mov     [rbp+70h+var_68], eax
0x140001b81  mov     rax, [rbp+70h+arg_70]
0x140001b88  mov     [rbp+70h+var_80], rax
0x140001b8c  mov     rax, [rbp+70h+arg_68]
0x140001b93  mov     [rbp+70h+var_70], rdx
0x140001b97  mov     [rbp+70h+var_64], ebx
0x140001b9a  mov     [rbp+70h+var_78], 4
0x140001ba2  mov     rdx, [rax]
0x140001ba5  test    rdx, rdx
0x140001ba8  jz      short loc_140001BB9
0x140001baa  mov     rax, rcx
0x140001bad  inc     rax
0x140001bb0  cmp     [rdx+rax], bl
0x140001bb3  jnz     short loc_140001BAD
0x140001bb5  inc     eax
0x140001bb7  jmp     short loc_140001BBF
0x140001bb9  mov     rdx, rdi
0x140001bbc  mov     eax, r8d
0x140001bbf  mov     [rbp+70h+var_88], eax
0x140001bc2  mov     rax, [rbp+70h+arg_60]
0x140001bc9  mov     [rbp+70h+var_A0], rax
0x140001bcd  mov     rax, [rbp+70h+arg_58]
0x140001bd4  mov     [rbp+70h+var_90], rdx
0x140001bd8  mov     [rbp+70h+var_84], ebx
0x140001bdb  mov     [rbp+70h+var_98], 4
0x140001be3  mov     rdx, [rax]
0x140001be6  test    rdx, rdx
0x140001be9  jz      short loc_140001C01
0x140001beb  mov     rax, rcx
0x140001bee  inc     rax
0x140001bf1  cmp     [rdx+rax*2], bx
0x140001bf5  jnz     short loc_140001BEE
0x140001bf7  lea     r9d, ds:2[rax*2]
0x140001bff  jmp     short loc_140001C08
0x140001c01  lea     rdx, dword_1400241F4
0x140001c08  mov     rax, [rbp+70h+arg_50]
0x140001c0f  mov     [rbp+70h+var_C0], rax
0x140001c13  mov     rax, [rbp+70h+arg_48]
0x140001c1a  mov     [rbp+70h+var_B0], rdx
0x140001c1e  mov     [rbp+70h+var_A8], r9d
0x140001c22  mov     [rbp+70h+var_A4], ebx
0x140001c25  mov     rdx, [rax]
0x140001c28  mov     [rbp+70h+var_B8], 4
0x140001c30  test    rdx, rdx
0x140001c33  jz      short loc_140001C44
0x140001c35  mov     rax, rcx
0x140001c38  inc     rax
0x140001c3b  cmp     [rdx+rax], bl
0x140001c3e  jnz     short loc_140001C38
0x140001c40  inc     eax
0x140001c42  jmp     short loc_140001C4A
0x140001c44  mov     rdx, rdi
0x140001c47  mov     eax, r8d
0x140001c4a  mov     [rbp+70h+var_C8], eax
0x140001c4d  mov     rax, [rbp+70h+arg_40]
0x140001c54  mov     [rbp+70h+var_E0], rax
0x140001c58  mov     rax, [rbp+70h+arg_38]
0x140001c5f  mov     [rbp+70h+var_D0], rdx
0x140001c63  mov     [rbp+70h+var_C4], ebx
0x140001c66  mov     [rbp+70h+var_D8], 4
0x140001c6e  mov     rdx, [rax]
0x140001c71  test    rdx, rdx
0x140001c74  jz      short loc_140001C84
0x140001c76  inc     rcx
0x140001c79  cmp     [rdx+rcx], bl
0x140001c7c  jnz     short loc_140001C76
0x140001c7e  lea     r8d, [rcx+1]
0x140001c82  jmp     short loc_140001C87
0x140001c84  mov     rdx, rdi
0x140001c87  mov     rax, [rbp+70h+arg_30]
0x140001c8e  xor     r9d, r9d
0x140001c91  mov     [rsp+170h+var_100], rax
0x140001c96  mov     rcx, r10
0x140001c99  mov     rax, [rbp+70h+arg_28]
0x140001ca0  mov     [rsp+170h+var_110], rax
0x140001ca5  mov     rax, [rbp+70h+arg_20]
0x140001cac  mov     [rsp+170h+var_120], rax
0x140001cb1  lea     rax, [rsp+170h+var_140]
0x140001cb6  mov     [rbp+70h+var_F0], rdx
0x140001cba  mov     rdx, r11
0x140001cbd  mov     [rbp+70h+var_E8], r8d
0x140001cc1  xor     r8d, r8d
0x140001cc4  mov     [rsp+170h+var_148], rax
0x140001cc9  mov     [rsp+170h+var_150], 12h
0x140001cd1  mov     [rbp+70h+var_E4], ebx
0x140001cd4  mov     [rsp+170h+var_F8], 4
0x140001cdd  mov     [rsp+170h+var_108], 8
0x140001ce6  mov     [rsp+170h+var_118], 8
0x140001cef  call    _tlgWriteTransfer_EventWriteTransfer
0x140001cf4  mov     rcx, [rbp+70h+var_20]
0x140001cf8  xor     rcx, rsp; StackCookie
0x140001cfb  call    __security_check_cookie
0x140001d00  mov     rbx, [rsp+170h+arg_10]
0x140001d08  add     rsp, 160h
0x140001d0f  pop     rdi
0x140001d10  pop     rsi
0x140001d11  pop     rbp
0x140001d12  retn
```
