# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x18000109c`
- end: `0x180001349`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `685`
- prototype: `__int64 __fastcall(int, int, int, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, char **, __int64, const wchar_t **, __int64, const wchar_t **, char **, __int64, const wchar_t **, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003d6c`
- `0x18000cbb0`

## callees

- `0x18000109c`
- `0x180001350`
- `0x180010310`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        int a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const wchar_t **a8,
        __int64 a9,
        const wchar_t **a10,
        __int64 a11,
        char **a12,
        __int64 a13,
        const wchar_t **a14,
        __int64 a15,
        const wchar_t **a16,
        char **a17,
        __int64 a18,
        const wchar_t **a19,
        char **a20)
{
  __int64 v22; // rdx
  int v24; // r9d
  char *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  int v28; // r8d
  const wchar_t *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  char *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const wchar_t *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  const wchar_t *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  char *v41; // rcx
  __int64 v42; // rax
  const wchar_t *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const wchar_t *v46; // rcx
  struct _EVENT_DATA_DESCRIPTOR v48; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h]
  __int64 v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h]
  __int64 v52; // [rsp+68h] [rbp-98h]
  __int64 v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h]
  const wchar_t *v55; // [rsp+80h] [rbp-80h]
  int v56; // [rsp+88h] [rbp-78h]
  int v57; // [rsp+8Ch] [rbp-74h]
  __int64 v58; // [rsp+90h] [rbp-70h]
  __int64 v59; // [rsp+98h] [rbp-68h]
  const wchar_t *v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+ACh] [rbp-54h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  char *v65; // [rsp+C0h] [rbp-40h]
  int v66; // [rsp+C8h] [rbp-38h]
  int v67; // [rsp+CCh] [rbp-34h]
  __int64 v68; // [rsp+D0h] [rbp-30h]
  __int64 v69; // [rsp+D8h] [rbp-28h]
  const wchar_t *v70; // [rsp+E0h] [rbp-20h]
  int v71; // [rsp+E8h] [rbp-18h]
  int v72; // [rsp+ECh] [rbp-14h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  __int64 v74; // [rsp+F8h] [rbp-8h]
  const wchar_t *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  char *v78; // [rsp+110h] [rbp+10h]
  int v79; // [rsp+118h] [rbp+18h]
  int v80; // [rsp+11Ch] [rbp+1Ch]
  __int64 v81; // [rsp+120h] [rbp+20h]
  __int64 v82; // [rsp+128h] [rbp+28h]
  const wchar_t *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]
  char *v86; // [rsp+140h] [rbp+40h]
  int v87; // [rsp+148h] [rbp+48h]
  int v88; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v24 = 2;
  v25 = *a20;
  if ( *a20 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)&v25[2 * v26] );
    v27 = 2 * v26 + 2;
  }
  else
  {
    v25 = byte_180018020;
    v27 = 2;
  }
  v87 = v27;
  v28 = 1;
  v86 = v25;
  v88 = 0;
  v29 = *a19;
  if ( *a19 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &word_180018022;
    v31 = 1;
  }
  v84 = v31;
  v81 = a18;
  v83 = v29;
  v85 = 0;
  v82 = 4;
  v32 = *a17;
  if ( *a17 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *(_WORD *)&v32[2 * v33] );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = byte_180018020;
    v34 = 2;
  }
  v79 = v34;
  v78 = v32;
  v80 = 0;
  v35 = *a16;
  if ( *a16 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &word_180018022;
    v37 = 1;
  }
  v76 = v37;
  v73 = a15;
  v75 = v35;
  v77 = 0;
  v74 = 4;
  v38 = *a14;
  if ( *a14 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &word_180018022;
    v40 = 1;
  }
  v71 = v40;
  v68 = a13;
  v70 = v38;
  v72 = 0;
  v69 = 4;
  v41 = *a12;
  if ( *a12 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *(_WORD *)&v41[2 * v42] );
    v24 = 2 * v42 + 2;
  }
  else
  {
    v41 = byte_180018020;
  }
  v63 = a11;
  v65 = v41;
  v66 = v24;
  v67 = 0;
  v43 = *a10;
  v64 = 4;
  if ( v43 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &word_180018022;
    v45 = 1;
  }
  v61 = v45;
  v58 = a9;
  v60 = v43;
  v62 = 0;
  v59 = 4;
  v46 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v46 + v22) );
    v28 = v22 + 1;
  }
  else
  {
    v46 = &word_180018022;
  }
  v53 = a7;
  v51 = a6;
  v49 = a5;
  v55 = v46;
  v56 = v28;
  v57 = 0;
  v54 = 4;
  v52 = 8;
  v50 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x12u, &v48);
}

```

## disassembly

```asm
0x18000109c  push    rbp
0x18000109e  push    rbx
0x18000109f  push    rsi
0x1800010a0  push    rdi
0x1800010a1  push    r14
0x1800010a3  lea     rbp, [rsp-60h]
0x1800010a8  sub     rsp, 160h
0x1800010af  mov     rax, cs:__security_cookie
0x1800010b6  xor     rax, rsp
0x1800010b9  mov     [rbp+80h+var_30], rax
0x1800010bd  mov     rax, [rbp+80h+arg_98]
0x1800010c4  mov     r11, rdx
0x1800010c7  mov     r10, rcx
0x1800010ca  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800010ce  xor     edi, edi
0x1800010d0  mov     rbx, r8
0x1800010d3  mov     r9d, 2
0x1800010d9  mov     rcx, [rax]
0x1800010dc  test    rcx, rcx
0x1800010df  jz      short loc_1800010F6
0x1800010e1  mov     rax, rdx
0x1800010e4  inc     rax
0x1800010e7  cmp     [rcx+rax*2], di
0x1800010eb  jnz     short loc_1800010E4
0x1800010ed  lea     eax, ds:2[rax*2]
0x1800010f4  jmp     short loc_180001100
0x1800010f6  lea     rcx, byte_180018020
0x1800010fd  mov     eax, r9d
0x180001100  mov     [rbp+80h+var_38], eax
0x180001103  lea     rsi, word_180018022
0x18000110a  mov     rax, [rbp+80h+arg_90]
0x180001111  mov     r8d, 1
0x180001117  mov     [rbp+80h+var_40], rcx
0x18000111b  mov     [rbp+80h+var_34], edi
0x18000111e  mov     rcx, [rax]
0x180001121  test    rcx, rcx
0x180001124  jz      short loc_180001136
0x180001126  mov     rax, rdx
0x180001129  inc     rax
0x18000112c  cmp     [rcx+rax], dil
0x180001130  jnz     short loc_180001129
0x180001132  inc     eax
0x180001134  jmp     short loc_18000113C
0x180001136  mov     rcx, rsi
0x180001139  mov     eax, r8d
0x18000113c  mov     [rbp+80h+var_48], eax
0x18000113f  mov     rax, [rbp+80h+arg_88]
0x180001146  mov     [rbp+80h+var_60], rax
0x18000114a  mov     rax, [rbp+80h+arg_80]
0x180001151  mov     [rbp+80h+var_50], rcx
0x180001155  mov     [rbp+80h+var_44], edi
0x180001158  mov     [rbp+80h+var_58], 4
0x180001160  mov     rcx, [rax]
0x180001163  test    rcx, rcx
0x180001166  jz      short loc_18000117D
0x180001168  mov     rax, rdx
0x18000116b  inc     rax
0x18000116e  cmp     [rcx+rax*2], di
0x180001172  jnz     short loc_18000116B
0x180001174  lea     eax, ds:2[rax*2]
0x18000117b  jmp     short loc_180001187
0x18000117d  lea     rcx, byte_180018020
0x180001184  mov     eax, r9d
0x180001187  mov     [rbp+80h+var_68], eax
0x18000118a  mov     rax, [rbp+80h+arg_78]
0x180001191  mov     [rbp+80h+var_70], rcx
0x180001195  mov     [rbp+80h+var_64], edi
0x180001198  mov     rcx, [rax]
0x18000119b  test    rcx, rcx
0x18000119e  jz      short loc_1800011B0
0x1800011a0  mov     rax, rdx
0x1800011a3  inc     rax
0x1800011a6  cmp     [rcx+rax], dil
0x1800011aa  jnz     short loc_1800011A3
0x1800011ac  inc     eax
0x1800011ae  jmp     short loc_1800011B6
0x1800011b0  mov     rcx, rsi
0x1800011b3  mov     eax, r8d
0x1800011b6  mov     [rbp+80h+var_78], eax
0x1800011b9  mov     rax, [rbp+80h+arg_70]
0x1800011c0  mov     [rbp+80h+var_90], rax
0x1800011c4  mov     rax, [rbp+80h+arg_68]
0x1800011cb  mov     [rbp+80h+var_80], rcx
0x1800011cf  mov     [rbp+80h+var_74], edi
0x1800011d2  mov     [rbp+80h+var_88], 4
0x1800011da  mov     rcx, [rax]
0x1800011dd  test    rcx, rcx
0x1800011e0  jz      short loc_1800011F2
0x1800011e2  mov     rax, rdx
0x1800011e5  inc     rax
0x1800011e8  cmp     [rcx+rax], dil
0x1800011ec  jnz     short loc_1800011E5
0x1800011ee  inc     eax
0x1800011f0  jmp     short loc_1800011F8
0x1800011f2  mov     rcx, rsi
0x1800011f5  mov     eax, r8d
0x1800011f8  mov     [rbp+80h+var_98], eax
0x1800011fb  mov     rax, [rbp+80h+arg_60]
0x180001202  mov     [rbp+80h+var_B0], rax
0x180001206  mov     rax, [rbp+80h+arg_58]
0x18000120d  mov     [rbp+80h+var_A0], rcx
0x180001211  mov     [rbp+80h+var_94], edi
0x180001214  mov     [rbp+80h+var_A8], 4
0x18000121c  mov     rcx, [rax]
0x18000121f  test    rcx, rcx
0x180001222  jz      short loc_18000123A
0x180001224  mov     rax, rdx
0x180001227  inc     rax
0x18000122a  cmp     [rcx+rax*2], di
0x18000122e  jnz     short loc_180001227
0x180001230  lea     r9d, ds:2[rax*2]
0x180001238  jmp     short loc_180001241
0x18000123a  lea     rcx, byte_180018020
0x180001241  mov     rax, [rbp+80h+arg_50]
0x180001248  mov     [rbp+80h+var_D0], rax
0x18000124c  mov     rax, [rbp+80h+arg_48]
0x180001253  mov     [rbp+80h+var_C0], rcx
0x180001257  mov     [rbp+80h+var_B8], r9d
0x18000125b  mov     [rbp+80h+var_B4], edi
0x18000125e  mov     rcx, [rax]
0x180001261  mov     [rbp+80h+var_C8], 4
0x180001269  test    rcx, rcx
0x18000126c  jz      short loc_18000127E
0x18000126e  mov     rax, rdx
0x180001271  inc     rax
0x180001274  cmp     [rcx+rax], dil
0x180001278  jnz     short loc_180001271
0x18000127a  inc     eax
0x18000127c  jmp     short loc_180001284
0x18000127e  mov     rcx, rsi
0x180001281  mov     eax, r8d
0x180001284  mov     [rbp+80h+var_D8], eax
0x180001287  mov     rax, [rbp+80h+arg_40]
0x18000128e  mov     [rbp+80h+var_F0], rax
0x180001292  mov     rax, [rbp+80h+arg_38]
0x180001299  mov     [rbp+80h+var_E0], rcx
0x18000129d  mov     [rbp+80h+var_D4], edi
0x1800012a0  mov     [rbp+80h+var_E8], 4
0x1800012a8  mov     rcx, [rax]
0x1800012ab  test    rcx, rcx
0x1800012ae  jz      short loc_1800012BF
0x1800012b0  inc     rdx
0x1800012b3  cmp     [rcx+rdx], dil
0x1800012b7  jnz     short loc_1800012B0
0x1800012b9  lea     r8d, [rdx+1]
0x1800012bd  jmp     short loc_1800012C2
0x1800012bf  mov     rcx, rsi
0x1800012c2  mov     rax, [rbp+80h+arg_30]
0x1800012c9  xor     r9d, r9d; int
0x1800012cc  mov     [rsp+180h+var_110], rax
0x1800012d1  mov     rdx, r11; int
0x1800012d4  mov     rax, [rbp+80h+arg_28]
0x1800012db  mov     [rsp+180h+var_120], rax
0x1800012e0  mov     rax, [rbp+80h+arg_20]
0x1800012e7  mov     [rsp+180h+var_130], rax
0x1800012ec  lea     rax, [rsp+180h+var_150]
0x1800012f1  mov     [rbp+80h+var_100], rcx
0x1800012f5  mov     rcx, r10; int
0x1800012f8  mov     [rbp+80h+var_F8], r8d
0x1800012fc  mov     r8, rbx; int
0x1800012ff  mov     [rsp+180h+var_158], rax; PEVENT_DATA_DESCRIPTOR
0x180001304  mov     [rsp+180h+var_160], 12h; ULONG
0x18000130c  mov     [rbp+80h+var_F4], edi
0x18000130f  mov     [rsp+180h+var_108], 4
0x180001318  mov     [rsp+180h+var_118], 8
0x180001321  mov     [rsp+180h+var_128], 8
0x18000132a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000132f  mov     rcx, [rbp+80h+var_30]
0x180001333  xor     rcx, rsp; StackCookie
0x180001336  call    __security_check_cookie
0x18000133b  add     rsp, 160h
0x180001342  pop     r14
0x180001344  pop     rdi
0x180001345  pop     rsi
0x180001346  pop     rbx
0x180001347  pop     rbp
0x180001348  retn
```
