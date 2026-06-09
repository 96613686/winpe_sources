# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x180001158`
- end: `0x180001403`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `683`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009c08`

## callees

- `0x180001158`
- `0x18000140c`
- `0x18000fce0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const wchar_t **a8,
        __int64 a9,
        const wchar_t **a10,
        __int64 a11,
        const WCHAR **a12,
        __int64 a13,
        const wchar_t **a14,
        __int64 a15,
        const wchar_t **a16,
        const WCHAR **a17,
        __int64 a18,
        const wchar_t **a19,
        const WCHAR **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  const WCHAR *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const wchar_t *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  const WCHAR *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const wchar_t *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const wchar_t *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  const WCHAR *v40; // rdx
  __int64 v41; // rax
  const wchar_t *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const wchar_t *v45; // rdx
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
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
  const WCHAR *v64; // [rsp+C0h] [rbp-40h]
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
  const WCHAR *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const wchar_t *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  const WCHAR *v85; // [rsp+140h] [rbp+40h]
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
    while ( v24[v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &OutputString;
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
    v28 = &word_1800189A6;
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
    while ( v31[v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &OutputString;
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
    v34 = &word_1800189A6;
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
    v37 = &word_1800189A6;
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
    while ( v40[v41] );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &OutputString;
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
    v42 = &word_1800189A6;
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
    v45 = &word_1800189A6;
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
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x12u, &v47);
}

```

## disassembly

```asm
0x180001158  mov     [rsp-8+arg_10], rbx
0x18000115d  push    rbp
0x18000115e  push    rsi
0x18000115f  push    rdi
0x180001160  lea     rbp, [rsp-60h]
0x180001165  sub     rsp, 160h
0x18000116c  mov     rax, cs:__security_cookie
0x180001173  xor     rax, rsp
0x180001176  mov     [rbp+70h+var_20], rax
0x18000117a  mov     rax, [rbp+70h+arg_98]
0x180001181  mov     r11, rdx
0x180001184  mov     r10, rcx
0x180001187  xor     ebx, ebx
0x180001189  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000118d  mov     r9d, 2
0x180001193  mov     rdx, [rax]
0x180001196  test    rdx, rdx
0x180001199  jz      short loc_1800011B0
0x18000119b  mov     rax, rcx
0x18000119e  inc     rax
0x1800011a1  cmp     [rdx+rax*2], bx
0x1800011a5  jnz     short loc_18000119E
0x1800011a7  lea     eax, ds:2[rax*2]
0x1800011ae  jmp     short loc_1800011BA
0x1800011b0  lea     rdx, OutputString
0x1800011b7  mov     eax, r9d
0x1800011ba  mov     [rbp+70h+var_28], eax
0x1800011bd  lea     rdi, word_1800189A6
0x1800011c4  mov     rax, [rbp+70h+arg_90]
0x1800011cb  mov     r8d, 1
0x1800011d1  mov     [rbp+70h+var_30], rdx
0x1800011d5  mov     [rbp+70h+var_24], ebx
0x1800011d8  mov     rdx, [rax]
0x1800011db  test    rdx, rdx
0x1800011de  jz      short loc_1800011EF
0x1800011e0  mov     rax, rcx
0x1800011e3  inc     rax
0x1800011e6  cmp     [rdx+rax], bl
0x1800011e9  jnz     short loc_1800011E3
0x1800011eb  inc     eax
0x1800011ed  jmp     short loc_1800011F5
0x1800011ef  mov     rdx, rdi
0x1800011f2  mov     eax, r8d
0x1800011f5  mov     [rbp+70h+var_38], eax
0x1800011f8  mov     rax, [rbp+70h+arg_88]
0x1800011ff  mov     [rbp+70h+var_50], rax
0x180001203  mov     rax, [rbp+70h+arg_80]
0x18000120a  mov     [rbp+70h+var_40], rdx
0x18000120e  mov     [rbp+70h+var_34], ebx
0x180001211  mov     [rbp+70h+var_48], 4
0x180001219  mov     rdx, [rax]
0x18000121c  test    rdx, rdx
0x18000121f  jz      short loc_180001236
0x180001221  mov     rax, rcx
0x180001224  inc     rax
0x180001227  cmp     [rdx+rax*2], bx
0x18000122b  jnz     short loc_180001224
0x18000122d  lea     eax, ds:2[rax*2]
0x180001234  jmp     short loc_180001240
0x180001236  lea     rdx, OutputString
0x18000123d  mov     eax, r9d
0x180001240  mov     [rbp+70h+var_58], eax
0x180001243  mov     rax, [rbp+70h+arg_78]
0x18000124a  mov     [rbp+70h+var_60], rdx
0x18000124e  mov     [rbp+70h+var_54], ebx
0x180001251  mov     rdx, [rax]
0x180001254  test    rdx, rdx
0x180001257  jz      short loc_180001268
0x180001259  mov     rax, rcx
0x18000125c  inc     rax
0x18000125f  cmp     [rdx+rax], bl
0x180001262  jnz     short loc_18000125C
0x180001264  inc     eax
0x180001266  jmp     short loc_18000126E
0x180001268  mov     rdx, rdi
0x18000126b  mov     eax, r8d
0x18000126e  mov     [rbp+70h+var_68], eax
0x180001271  mov     rax, [rbp+70h+arg_70]
0x180001278  mov     [rbp+70h+var_80], rax
0x18000127c  mov     rax, [rbp+70h+arg_68]
0x180001283  mov     [rbp+70h+var_70], rdx
0x180001287  mov     [rbp+70h+var_64], ebx
0x18000128a  mov     [rbp+70h+var_78], 4
0x180001292  mov     rdx, [rax]
0x180001295  test    rdx, rdx
0x180001298  jz      short loc_1800012A9
0x18000129a  mov     rax, rcx
0x18000129d  inc     rax
0x1800012a0  cmp     [rdx+rax], bl
0x1800012a3  jnz     short loc_18000129D
0x1800012a5  inc     eax
0x1800012a7  jmp     short loc_1800012AF
0x1800012a9  mov     rdx, rdi
0x1800012ac  mov     eax, r8d
0x1800012af  mov     [rbp+70h+var_88], eax
0x1800012b2  mov     rax, [rbp+70h+arg_60]
0x1800012b9  mov     [rbp+70h+var_A0], rax
0x1800012bd  mov     rax, [rbp+70h+arg_58]
0x1800012c4  mov     [rbp+70h+var_90], rdx
0x1800012c8  mov     [rbp+70h+var_84], ebx
0x1800012cb  mov     [rbp+70h+var_98], 4
0x1800012d3  mov     rdx, [rax]
0x1800012d6  test    rdx, rdx
0x1800012d9  jz      short loc_1800012F1
0x1800012db  mov     rax, rcx
0x1800012de  inc     rax
0x1800012e1  cmp     [rdx+rax*2], bx
0x1800012e5  jnz     short loc_1800012DE
0x1800012e7  lea     r9d, ds:2[rax*2]
0x1800012ef  jmp     short loc_1800012F8
0x1800012f1  lea     rdx, OutputString
0x1800012f8  mov     rax, [rbp+70h+arg_50]
0x1800012ff  mov     [rbp+70h+var_C0], rax
0x180001303  mov     rax, [rbp+70h+arg_48]
0x18000130a  mov     [rbp+70h+var_B0], rdx
0x18000130e  mov     [rbp+70h+var_A8], r9d
0x180001312  mov     [rbp+70h+var_A4], ebx
0x180001315  mov     rdx, [rax]
0x180001318  mov     [rbp+70h+var_B8], 4
0x180001320  test    rdx, rdx
0x180001323  jz      short loc_180001334
0x180001325  mov     rax, rcx
0x180001328  inc     rax
0x18000132b  cmp     [rdx+rax], bl
0x18000132e  jnz     short loc_180001328
0x180001330  inc     eax
0x180001332  jmp     short loc_18000133A
0x180001334  mov     rdx, rdi
0x180001337  mov     eax, r8d
0x18000133a  mov     [rbp+70h+var_C8], eax
0x18000133d  mov     rax, [rbp+70h+arg_40]
0x180001344  mov     [rbp+70h+var_E0], rax
0x180001348  mov     rax, [rbp+70h+arg_38]
0x18000134f  mov     [rbp+70h+var_D0], rdx
0x180001353  mov     [rbp+70h+var_C4], ebx
0x180001356  mov     [rbp+70h+var_D8], 4
0x18000135e  mov     rdx, [rax]
0x180001361  test    rdx, rdx
0x180001364  jz      short loc_180001374
0x180001366  inc     rcx
0x180001369  cmp     [rdx+rcx], bl
0x18000136c  jnz     short loc_180001366
0x18000136e  lea     r8d, [rcx+1]
0x180001372  jmp     short loc_180001377
0x180001374  mov     rdx, rdi
0x180001377  mov     rax, [rbp+70h+arg_30]
0x18000137e  xor     r9d, r9d; int
0x180001381  mov     [rsp+170h+var_100], rax
0x180001386  mov     rcx, r10; int
0x180001389  mov     rax, [rbp+70h+arg_28]
0x180001390  mov     [rsp+170h+var_110], rax
0x180001395  mov     rax, [rbp+70h+arg_20]
0x18000139c  mov     [rsp+170h+var_120], rax
0x1800013a1  lea     rax, [rsp+170h+var_140]
0x1800013a6  mov     [rbp+70h+var_F0], rdx
0x1800013aa  mov     rdx, r11; int
0x1800013ad  mov     [rbp+70h+var_E8], r8d
0x1800013b1  xor     r8d, r8d; int
0x1800013b4  mov     [rsp+170h+var_148], rax; PEVENT_DATA_DESCRIPTOR
0x1800013b9  mov     [rsp+170h+var_150], 12h; ULONG
0x1800013c1  mov     [rbp+70h+var_E4], ebx
0x1800013c4  mov     [rsp+170h+var_F8], 4
0x1800013cd  mov     [rsp+170h+var_108], 8
0x1800013d6  mov     [rsp+170h+var_118], 8
0x1800013df  call    _tlgWriteTransfer_EventWriteTransfer
0x1800013e4  mov     rcx, [rbp+70h+var_20]
0x1800013e8  xor     rcx, rsp; StackCookie
0x1800013eb  call    __security_check_cookie
0x1800013f0  mov     rbx, [rsp+170h+arg_10]
0x1800013f8  add     rsp, 160h
0x1800013ff  pop     rdi
0x180001400  pop     rsi
0x180001401  pop     rbp
0x180001402  retn
```
