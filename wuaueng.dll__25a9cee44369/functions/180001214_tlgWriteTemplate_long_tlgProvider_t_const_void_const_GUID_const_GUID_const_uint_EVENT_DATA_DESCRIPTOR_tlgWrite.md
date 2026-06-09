# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x180001214`
- end: `0x1800014bf`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const WCHAR **, __int64, const wchar_t **, __int64, const wchar_t **, const WCHAR **, __int64, const wchar_t **, const WCHAR **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005f6c`

## callees

- `0x180001158`
- `0x180001214`
- `0x18000fc90`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        int a1,
        int a2,
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
0x180001214  mov     [rsp-8+arg_10], rbx
0x180001219  push    rbp
0x18000121a  push    rsi
0x18000121b  push    rdi
0x18000121c  lea     rbp, [rsp-60h]
0x180001221  sub     rsp, 160h
0x180001228  mov     rax, cs:__security_cookie
0x18000122f  xor     rax, rsp
0x180001232  mov     [rbp+70h+var_20], rax
0x180001236  mov     rax, [rbp+70h+arg_98]
0x18000123d  mov     r11, rdx
0x180001240  mov     r10, rcx
0x180001243  xor     ebx, ebx
0x180001245  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001249  mov     r9d, 2
0x18000124f  mov     rdx, [rax]
0x180001252  test    rdx, rdx
0x180001255  jz      short loc_18000126C
0x180001257  mov     rax, rcx
0x18000125a  inc     rax
0x18000125d  cmp     [rdx+rax*2], bx
0x180001261  jnz     short loc_18000125A
0x180001263  lea     eax, ds:2[rax*2]
0x18000126a  jmp     short loc_180001276
0x18000126c  lea     rdx, OutputString
0x180001273  mov     eax, r9d
0x180001276  mov     [rbp+70h+var_28], eax
0x180001279  lea     rdi, word_1800189A6
0x180001280  mov     rax, [rbp+70h+arg_90]
0x180001287  mov     r8d, 1
0x18000128d  mov     [rbp+70h+var_30], rdx
0x180001291  mov     [rbp+70h+var_24], ebx
0x180001294  mov     rdx, [rax]
0x180001297  test    rdx, rdx
0x18000129a  jz      short loc_1800012AB
0x18000129c  mov     rax, rcx
0x18000129f  inc     rax
0x1800012a2  cmp     [rdx+rax], bl
0x1800012a5  jnz     short loc_18000129F
0x1800012a7  inc     eax
0x1800012a9  jmp     short loc_1800012B1
0x1800012ab  mov     rdx, rdi
0x1800012ae  mov     eax, r8d
0x1800012b1  mov     [rbp+70h+var_38], eax
0x1800012b4  mov     rax, [rbp+70h+arg_88]
0x1800012bb  mov     [rbp+70h+var_50], rax
0x1800012bf  mov     rax, [rbp+70h+arg_80]
0x1800012c6  mov     [rbp+70h+var_40], rdx
0x1800012ca  mov     [rbp+70h+var_34], ebx
0x1800012cd  mov     [rbp+70h+var_48], 4
0x1800012d5  mov     rdx, [rax]
0x1800012d8  test    rdx, rdx
0x1800012db  jz      short loc_1800012F2
0x1800012dd  mov     rax, rcx
0x1800012e0  inc     rax
0x1800012e3  cmp     [rdx+rax*2], bx
0x1800012e7  jnz     short loc_1800012E0
0x1800012e9  lea     eax, ds:2[rax*2]
0x1800012f0  jmp     short loc_1800012FC
0x1800012f2  lea     rdx, OutputString
0x1800012f9  mov     eax, r9d
0x1800012fc  mov     [rbp+70h+var_58], eax
0x1800012ff  mov     rax, [rbp+70h+arg_78]
0x180001306  mov     [rbp+70h+var_60], rdx
0x18000130a  mov     [rbp+70h+var_54], ebx
0x18000130d  mov     rdx, [rax]
0x180001310  test    rdx, rdx
0x180001313  jz      short loc_180001324
0x180001315  mov     rax, rcx
0x180001318  inc     rax
0x18000131b  cmp     [rdx+rax], bl
0x18000131e  jnz     short loc_180001318
0x180001320  inc     eax
0x180001322  jmp     short loc_18000132A
0x180001324  mov     rdx, rdi
0x180001327  mov     eax, r8d
0x18000132a  mov     [rbp+70h+var_68], eax
0x18000132d  mov     rax, [rbp+70h+arg_70]
0x180001334  mov     [rbp+70h+var_80], rax
0x180001338  mov     rax, [rbp+70h+arg_68]
0x18000133f  mov     [rbp+70h+var_70], rdx
0x180001343  mov     [rbp+70h+var_64], ebx
0x180001346  mov     [rbp+70h+var_78], 4
0x18000134e  mov     rdx, [rax]
0x180001351  test    rdx, rdx
0x180001354  jz      short loc_180001365
0x180001356  mov     rax, rcx
0x180001359  inc     rax
0x18000135c  cmp     [rdx+rax], bl
0x18000135f  jnz     short loc_180001359
0x180001361  inc     eax
0x180001363  jmp     short loc_18000136B
0x180001365  mov     rdx, rdi
0x180001368  mov     eax, r8d
0x18000136b  mov     [rbp+70h+var_88], eax
0x18000136e  mov     rax, [rbp+70h+arg_60]
0x180001375  mov     [rbp+70h+var_A0], rax
0x180001379  mov     rax, [rbp+70h+arg_58]
0x180001380  mov     [rbp+70h+var_90], rdx
0x180001384  mov     [rbp+70h+var_84], ebx
0x180001387  mov     [rbp+70h+var_98], 4
0x18000138f  mov     rdx, [rax]
0x180001392  test    rdx, rdx
0x180001395  jz      short loc_1800013AD
0x180001397  mov     rax, rcx
0x18000139a  inc     rax
0x18000139d  cmp     [rdx+rax*2], bx
0x1800013a1  jnz     short loc_18000139A
0x1800013a3  lea     r9d, ds:2[rax*2]
0x1800013ab  jmp     short loc_1800013B4
0x1800013ad  lea     rdx, OutputString
0x1800013b4  mov     rax, [rbp+70h+arg_50]
0x1800013bb  mov     [rbp+70h+var_C0], rax
0x1800013bf  mov     rax, [rbp+70h+arg_48]
0x1800013c6  mov     [rbp+70h+var_B0], rdx
0x1800013ca  mov     [rbp+70h+var_A8], r9d
0x1800013ce  mov     [rbp+70h+var_A4], ebx
0x1800013d1  mov     rdx, [rax]
0x1800013d4  mov     [rbp+70h+var_B8], 4
0x1800013dc  test    rdx, rdx
0x1800013df  jz      short loc_1800013F0
0x1800013e1  mov     rax, rcx
0x1800013e4  inc     rax
0x1800013e7  cmp     [rdx+rax], bl
0x1800013ea  jnz     short loc_1800013E4
0x1800013ec  inc     eax
0x1800013ee  jmp     short loc_1800013F6
0x1800013f0  mov     rdx, rdi
0x1800013f3  mov     eax, r8d
0x1800013f6  mov     [rbp+70h+var_C8], eax
0x1800013f9  mov     rax, [rbp+70h+arg_40]
0x180001400  mov     [rbp+70h+var_E0], rax
0x180001404  mov     rax, [rbp+70h+arg_38]
0x18000140b  mov     [rbp+70h+var_D0], rdx
0x18000140f  mov     [rbp+70h+var_C4], ebx
0x180001412  mov     [rbp+70h+var_D8], 4
0x18000141a  mov     rdx, [rax]
0x18000141d  test    rdx, rdx
0x180001420  jz      short loc_180001430
0x180001422  inc     rcx
0x180001425  cmp     [rdx+rcx], bl
0x180001428  jnz     short loc_180001422
0x18000142a  lea     r8d, [rcx+1]
0x18000142e  jmp     short loc_180001433
0x180001430  mov     rdx, rdi
0x180001433  mov     rax, [rbp+70h+arg_30]
0x18000143a  xor     r9d, r9d; int
0x18000143d  mov     [rsp+170h+var_100], rax
0x180001442  mov     rcx, r10; int
0x180001445  mov     rax, [rbp+70h+arg_28]
0x18000144c  mov     [rsp+170h+var_110], rax
0x180001451  mov     rax, [rbp+70h+arg_20]
0x180001458  mov     [rsp+170h+var_120], rax
0x18000145d  lea     rax, [rsp+170h+var_140]
0x180001462  mov     [rbp+70h+var_F0], rdx
0x180001466  mov     rdx, r11; int
0x180001469  mov     [rbp+70h+var_E8], r8d
0x18000146d  xor     r8d, r8d; int
0x180001470  mov     [rsp+170h+var_148], rax; PEVENT_DATA_DESCRIPTOR
0x180001475  mov     [rsp+170h+var_150], 12h; ULONG
0x18000147d  mov     [rbp+70h+var_E4], ebx
0x180001480  mov     [rsp+170h+var_F8], 4
0x180001489  mov     [rsp+170h+var_108], 8
0x180001492  mov     [rsp+170h+var_118], 8
0x18000149b  call    _tlgWriteTransfer_EventWriteTransfer
0x1800014a0  mov     rcx, [rbp+70h+var_20]
0x1800014a4  xor     rcx, rsp; StackCookie
0x1800014a7  call    __security_check_cookie
0x1800014ac  mov     rbx, [rsp+170h+arg_10]
0x1800014b4  add     rsp, 160h
0x1800014bb  pop     rdi
0x1800014bc  pop     rsi
0x1800014bd  pop     rbp
0x1800014be  retn
```
