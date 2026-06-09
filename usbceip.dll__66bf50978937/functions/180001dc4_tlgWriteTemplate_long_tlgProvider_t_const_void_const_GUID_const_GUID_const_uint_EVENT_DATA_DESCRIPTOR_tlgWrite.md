# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)

- ea: `0x180001dc4`
- end: `0x180001fe5`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U1@U1@U1@U1@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33333333AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z`
- size: `545`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int16 **, __int16 **, __int16 **, __int16 **, __int16 **, __int16 **, __int16 **, __int16 **, __int16 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007b44`

## callees

- `0x180001010`
- `0x180001dc4`
- `0x180002410`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int16 **a5,
        __int16 **a6,
        __int16 **a7,
        __int16 **a8,
        __int16 **a9,
        __int16 **a10,
        __int16 **a11,
        __int16 **a12,
        __int16 **a13,
        __int64 a14,
        __int64 a15)
{
  __int64 v16; // rdx
  int v17; // ecx
  __int16 *v18; // r8
  __int64 v19; // rax
  int v20; // eax
  __int16 *v21; // r8
  __int64 v22; // rax
  int v23; // eax
  __int16 *v24; // r8
  __int64 v25; // rax
  int v26; // eax
  __int16 *v27; // r8
  __int64 v28; // rax
  int v29; // eax
  __int16 *v30; // r8
  __int64 v31; // rax
  int v32; // eax
  __int16 *v33; // r8
  __int64 v34; // rax
  int v35; // eax
  __int16 *v36; // r8
  __int64 v37; // rax
  int v38; // eax
  __int16 *v39; // r8
  __int64 v40; // rax
  int v41; // eax
  __int16 *v42; // r8
  _BYTE v44[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 *v45; // [rsp+50h] [rbp-B0h]
  int v46; // [rsp+58h] [rbp-A8h]
  int v47; // [rsp+5Ch] [rbp-A4h]
  __int16 *v48; // [rsp+60h] [rbp-A0h]
  int v49; // [rsp+68h] [rbp-98h]
  int v50; // [rsp+6Ch] [rbp-94h]
  __int16 *v51; // [rsp+70h] [rbp-90h]
  int v52; // [rsp+78h] [rbp-88h]
  int v53; // [rsp+7Ch] [rbp-84h]
  __int16 *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int16 *v57; // [rsp+90h] [rbp-70h]
  int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+9Ch] [rbp-64h]
  __int16 *v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+ACh] [rbp-54h]
  __int16 *v63; // [rsp+B0h] [rbp-50h]
  int v64; // [rsp+B8h] [rbp-48h]
  int v65; // [rsp+BCh] [rbp-44h]
  __int16 *v66; // [rsp+C0h] [rbp-40h]
  int v67; // [rsp+C8h] [rbp-38h]
  int v68; // [rsp+CCh] [rbp-34h]
  __int16 *v69; // [rsp+D0h] [rbp-30h]
  int v70; // [rsp+D8h] [rbp-28h]
  int v71; // [rsp+DCh] [rbp-24h]
  __int64 v72; // [rsp+E0h] [rbp-20h]
  __int64 v73; // [rsp+E8h] [rbp-18h]
  __int64 v74; // [rsp+F0h] [rbp-10h]
  __int64 v75; // [rsp+F8h] [rbp-8h]

  v74 = a15;
  v72 = a14;
  v16 = -1;
  v17 = 1;
  v75 = 1;
  v73 = 4;
  v18 = *a13;
  if ( *a13 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_BYTE *)v18 + v19) );
    v20 = v19 + 1;
  }
  else
  {
    v18 = &word_180013A56;
    v20 = 1;
  }
  v70 = v20;
  v69 = v18;
  v71 = 0;
  v21 = *a12;
  if ( *a12 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *((_BYTE *)v21 + v22) );
    v23 = v22 + 1;
  }
  else
  {
    v21 = &word_180013A56;
    v23 = 1;
  }
  v67 = v23;
  v66 = v21;
  v68 = 0;
  v24 = *a11;
  if ( *a11 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_BYTE *)v24 + v25) );
    v26 = v25 + 1;
  }
  else
  {
    v24 = &word_180013A56;
    v26 = 1;
  }
  v64 = v26;
  v63 = v24;
  v65 = 0;
  v27 = *a10;
  if ( *a10 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &word_180013A56;
    v29 = 1;
  }
  v61 = v29;
  v60 = v27;
  v62 = 0;
  v30 = *a9;
  if ( *a9 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_BYTE *)v30 + v31) );
    v32 = v31 + 1;
  }
  else
  {
    v30 = &word_180013A56;
    v32 = 1;
  }
  v58 = v32;
  v57 = v30;
  v59 = 0;
  v33 = *a8;
  if ( *a8 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &word_180013A56;
    v35 = 1;
  }
  v55 = v35;
  v54 = v33;
  v56 = 0;
  v36 = *a7;
  if ( *a7 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &word_180013A56;
    v38 = 1;
  }
  v52 = v38;
  v51 = v36;
  v53 = 0;
  v39 = *a6;
  if ( *a6 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &word_180013A56;
    v41 = 1;
  }
  v49 = v41;
  v48 = v39;
  v50 = 0;
  v42 = *a5;
  if ( *a5 )
  {
    do
      ++v16;
    while ( *((_BYTE *)v42 + v16) );
    v17 = v16 + 1;
  }
  else
  {
    v42 = &word_180013A56;
  }
  v45 = v42;
  v46 = v17;
  v47 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C038, a2, 0, 0, 13, v44);
}

```

## disassembly

```asm
0x180001dc4  push    rbp
0x180001dc6  lea     rbp, [rsp-10h]
0x180001dcb  sub     rsp, 110h
0x180001dd2  mov     rax, cs:__security_cookie
0x180001dd9  xor     rax, rsp
0x180001ddc  mov     [rbp+10h+var_10], rax
0x180001de0  mov     rax, [rbp+10h+arg_70]
0x180001de7  lea     r11, word_180013A56
0x180001dee  mov     [rbp+10h+var_20], rax
0x180001df2  mov     r10, rdx
0x180001df5  mov     rax, [rbp+10h+arg_68]
0x180001dfc  xor     r9d, r9d
0x180001dff  mov     [rbp+10h+var_30], rax
0x180001e03  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001e07  mov     rax, [rbp+10h+arg_60]
0x180001e0e  mov     ecx, 1
0x180001e13  mov     [rbp+10h+var_18], rcx
0x180001e17  mov     [rbp+10h+var_28], 4
0x180001e1f  mov     r8, [rax]
0x180001e22  test    r8, r8
0x180001e25  jz      short loc_180001E37
0x180001e27  mov     rax, rdx
0x180001e2a  inc     rax
0x180001e2d  cmp     [r8+rax], r9b
0x180001e31  jnz     short loc_180001E2A
0x180001e33  inc     eax
0x180001e35  jmp     short loc_180001E3C
0x180001e37  mov     r8, r11
0x180001e3a  mov     eax, ecx
0x180001e3c  mov     [rbp+10h+var_38], eax
0x180001e3f  mov     rax, [rbp+10h+arg_58]
0x180001e43  mov     [rbp+10h+var_40], r8
0x180001e47  mov     [rbp+10h+var_34], r9d
0x180001e4b  mov     r8, [rax]
0x180001e4e  test    r8, r8
0x180001e51  jz      short loc_180001E63
0x180001e53  mov     rax, rdx
0x180001e56  inc     rax
0x180001e59  cmp     [r8+rax], r9b
0x180001e5d  jnz     short loc_180001E56
0x180001e5f  inc     eax
0x180001e61  jmp     short loc_180001E68
0x180001e63  mov     r8, r11
0x180001e66  mov     eax, ecx
0x180001e68  mov     [rbp+10h+var_48], eax
0x180001e6b  mov     rax, [rbp+10h+arg_50]
0x180001e6f  mov     [rbp+10h+var_50], r8
0x180001e73  mov     [rbp+10h+var_44], r9d
0x180001e77  mov     r8, [rax]
0x180001e7a  test    r8, r8
0x180001e7d  jz      short loc_180001E8F
0x180001e7f  mov     rax, rdx
0x180001e82  inc     rax
0x180001e85  cmp     [r8+rax], r9b
0x180001e89  jnz     short loc_180001E82
0x180001e8b  inc     eax
0x180001e8d  jmp     short loc_180001E94
0x180001e8f  mov     r8, r11
0x180001e92  mov     eax, ecx
0x180001e94  mov     [rbp+10h+var_58], eax
0x180001e97  mov     rax, [rbp+10h+arg_48]
0x180001e9b  mov     [rbp+10h+var_60], r8
0x180001e9f  mov     [rbp+10h+var_54], r9d
0x180001ea3  mov     r8, [rax]
0x180001ea6  test    r8, r8
0x180001ea9  jz      short loc_180001EBB
0x180001eab  mov     rax, rdx
0x180001eae  inc     rax
0x180001eb1  cmp     [r8+rax], r9b
0x180001eb5  jnz     short loc_180001EAE
0x180001eb7  inc     eax
0x180001eb9  jmp     short loc_180001EC0
0x180001ebb  mov     r8, r11
0x180001ebe  mov     eax, ecx
0x180001ec0  mov     [rbp+10h+var_68], eax
0x180001ec3  mov     rax, [rbp+10h+arg_40]
0x180001ec7  mov     [rbp+10h+var_70], r8
0x180001ecb  mov     [rbp+10h+var_64], r9d
0x180001ecf  mov     r8, [rax]
0x180001ed2  test    r8, r8
0x180001ed5  jz      short loc_180001EE7
0x180001ed7  mov     rax, rdx
0x180001eda  inc     rax
0x180001edd  cmp     [r8+rax], r9b
0x180001ee1  jnz     short loc_180001EDA
0x180001ee3  inc     eax
0x180001ee5  jmp     short loc_180001EEC
0x180001ee7  mov     r8, r11
0x180001eea  mov     eax, ecx
0x180001eec  mov     [rbp+10h+var_78], eax
0x180001eef  mov     rax, [rbp+10h+arg_38]
0x180001ef3  mov     [rbp+10h+var_80], r8
0x180001ef7  mov     [rbp+10h+var_74], r9d
0x180001efb  mov     r8, [rax]
0x180001efe  test    r8, r8
0x180001f01  jz      short loc_180001F13
0x180001f03  mov     rax, rdx
0x180001f06  inc     rax
0x180001f09  cmp     [r8+rax], r9b
0x180001f0d  jnz     short loc_180001F06
0x180001f0f  inc     eax
0x180001f11  jmp     short loc_180001F18
0x180001f13  mov     r8, r11
0x180001f16  mov     eax, ecx
0x180001f18  mov     [rbp+10h+var_88], eax
0x180001f1b  mov     rax, [rbp+10h+arg_30]
0x180001f1f  mov     [rbp+10h+var_90], r8
0x180001f23  mov     [rbp+10h+var_84], r9d
0x180001f27  mov     r8, [rax]
0x180001f2a  test    r8, r8
0x180001f2d  jz      short loc_180001F3F
0x180001f2f  mov     rax, rdx
0x180001f32  inc     rax
0x180001f35  cmp     [r8+rax], r9b
0x180001f39  jnz     short loc_180001F32
0x180001f3b  inc     eax
0x180001f3d  jmp     short loc_180001F44
0x180001f3f  mov     r8, r11
0x180001f42  mov     eax, ecx
0x180001f44  mov     [rsp+110h+var_98], eax
0x180001f48  mov     rax, [rbp+10h+arg_28]
0x180001f4c  mov     [rsp+110h+var_A0], r8
0x180001f51  mov     [rsp+110h+var_94], r9d
0x180001f56  mov     r8, [rax]
0x180001f59  test    r8, r8
0x180001f5c  jz      short loc_180001F6E
0x180001f5e  mov     rax, rdx
0x180001f61  inc     rax
0x180001f64  cmp     [r8+rax], r9b
0x180001f68  jnz     short loc_180001F61
0x180001f6a  inc     eax
0x180001f6c  jmp     short loc_180001F73
0x180001f6e  mov     r8, r11
0x180001f71  mov     eax, ecx
0x180001f73  mov     [rsp+110h+var_A8], eax
0x180001f77  mov     rax, [rbp+10h+arg_20]
0x180001f7b  mov     [rsp+110h+var_B0], r8
0x180001f80  mov     [rsp+110h+var_A4], r9d
0x180001f85  mov     r8, [rax]
0x180001f88  test    r8, r8
0x180001f8b  jz      short loc_180001F9B
0x180001f8d  inc     rdx
0x180001f90  cmp     [r8+rdx], r9b
0x180001f94  jnz     short loc_180001F8D
0x180001f96  lea     ecx, [rdx+1]
0x180001f99  jmp     short loc_180001F9E
0x180001f9b  mov     r8, r11
0x180001f9e  lea     rax, [rsp+110h+var_E0]
0x180001fa3  mov     [rsp+110h+var_C0], r8
0x180001fa8  mov     [rsp+110h+var_B8], ecx
0x180001fac  xor     r8d, r8d
0x180001faf  mov     [rsp+110h+var_E8], rax
0x180001fb4  lea     rcx, dword_18001C038
0x180001fbb  mov     rdx, r10
0x180001fbe  mov     [rsp+110h+var_F0], 0Dh
0x180001fc6  mov     [rsp+110h+var_B4], r9d
0x180001fcb  call    _tlgWriteTransfer_EventWriteTransfer
0x180001fd0  mov     rcx, [rbp+10h+var_10]
0x180001fd4  xor     rcx, rsp; StackCookie
0x180001fd7  call    __security_check_cookie
0x180001fdc  add     rsp, 110h
0x180001fe3  pop     rbp
0x180001fe4  retn
```
