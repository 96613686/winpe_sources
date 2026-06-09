# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800016dc`
- end: `0x18000199a`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564563@Z`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b4d4`

## callees

- `0x18000163c`
- `0x1800016dc`
- `0x18000e990`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
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
        char **a20,
        __int64 a21)
{
  __int64 v23; // rdx
  int v25; // r9d
  char *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r8d
  const wchar_t *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  char *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  const wchar_t *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const wchar_t *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  char *v42; // rcx
  __int64 v43; // rax
  const wchar_t *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  const wchar_t *v47; // rcx
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v50; // [rsp+50h] [rbp-B0h]
  __int64 v51; // [rsp+58h] [rbp-A8h]
  __int64 v52; // [rsp+60h] [rbp-A0h]
  __int64 v53; // [rsp+68h] [rbp-98h]
  __int64 v54; // [rsp+70h] [rbp-90h]
  __int64 v55; // [rsp+78h] [rbp-88h]
  const wchar_t *v56; // [rsp+80h] [rbp-80h]
  int v57; // [rsp+88h] [rbp-78h]
  int v58; // [rsp+8Ch] [rbp-74h]
  __int64 v59; // [rsp+90h] [rbp-70h]
  __int64 v60; // [rsp+98h] [rbp-68h]
  const wchar_t *v61; // [rsp+A0h] [rbp-60h]
  int v62; // [rsp+A8h] [rbp-58h]
  int v63; // [rsp+ACh] [rbp-54h]
  __int64 v64; // [rsp+B0h] [rbp-50h]
  __int64 v65; // [rsp+B8h] [rbp-48h]
  char *v66; // [rsp+C0h] [rbp-40h]
  int v67; // [rsp+C8h] [rbp-38h]
  int v68; // [rsp+CCh] [rbp-34h]
  __int64 v69; // [rsp+D0h] [rbp-30h]
  __int64 v70; // [rsp+D8h] [rbp-28h]
  const wchar_t *v71; // [rsp+E0h] [rbp-20h]
  int v72; // [rsp+E8h] [rbp-18h]
  int v73; // [rsp+ECh] [rbp-14h]
  __int64 v74; // [rsp+F0h] [rbp-10h]
  __int64 v75; // [rsp+F8h] [rbp-8h]
  const wchar_t *v76; // [rsp+100h] [rbp+0h]
  int v77; // [rsp+108h] [rbp+8h]
  int v78; // [rsp+10Ch] [rbp+Ch]
  char *v79; // [rsp+110h] [rbp+10h]
  int v80; // [rsp+118h] [rbp+18h]
  int v81; // [rsp+11Ch] [rbp+1Ch]
  __int64 v82; // [rsp+120h] [rbp+20h]
  __int64 v83; // [rsp+128h] [rbp+28h]
  const wchar_t *v84; // [rsp+130h] [rbp+30h]
  int v85; // [rsp+138h] [rbp+38h]
  int v86; // [rsp+13Ch] [rbp+3Ch]
  char *v87; // [rsp+140h] [rbp+40h]
  int v88; // [rsp+148h] [rbp+48h]
  int v89; // [rsp+14Ch] [rbp+4Ch]
  __int64 v90; // [rsp+150h] [rbp+50h]
  __int64 v91; // [rsp+158h] [rbp+58h]

  v90 = a21;
  v23 = -1;
  v91 = 8;
  v25 = 2;
  v26 = *a20;
  if ( *a20 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)&v26[2 * v27] );
    v28 = 2 * v27 + 2;
  }
  else
  {
    v26 = byte_1800138F4;
    v28 = 2;
  }
  v88 = v28;
  v29 = 1;
  v87 = v26;
  v89 = 0;
  v30 = *a19;
  if ( *a19 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_BYTE *)v30 + v31) );
    v32 = v31 + 1;
  }
  else
  {
    v30 = &word_1800138F6;
    v32 = 1;
  }
  v85 = v32;
  v82 = a18;
  v84 = v30;
  v86 = 0;
  v83 = 4;
  v33 = *a17;
  if ( *a17 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *(_WORD *)&v33[2 * v34] );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v33 = byte_1800138F4;
    v35 = 2;
  }
  v80 = v35;
  v79 = v33;
  v81 = 0;
  v36 = *a16;
  if ( *a16 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &word_1800138F6;
    v38 = 1;
  }
  v77 = v38;
  v74 = a15;
  v76 = v36;
  v78 = 0;
  v75 = 4;
  v39 = *a14;
  if ( *a14 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &word_1800138F6;
    v41 = 1;
  }
  v72 = v41;
  v69 = a13;
  v71 = v39;
  v73 = 0;
  v70 = 4;
  v42 = *a12;
  if ( *a12 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *(_WORD *)&v42[2 * v43] );
    v25 = 2 * v43 + 2;
  }
  else
  {
    v42 = byte_1800138F4;
  }
  v64 = a11;
  v66 = v42;
  v67 = v25;
  v68 = 0;
  v44 = *a10;
  v65 = 4;
  if ( v44 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &word_1800138F6;
    v46 = 1;
  }
  v62 = v46;
  v59 = a9;
  v61 = v44;
  v63 = 0;
  v60 = 4;
  v47 = *a8;
  if ( *a8 )
  {
    do
      ++v23;
    while ( *((_BYTE *)v47 + v23) );
    v29 = v23 + 1;
  }
  else
  {
    v47 = &word_1800138F6;
  }
  v54 = a7;
  v52 = a6;
  v50 = a5;
  v56 = v47;
  v57 = v29;
  v58 = 0;
  v55 = 4;
  v53 = 8;
  v51 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x13u, &v49);
}

```

## disassembly

```asm
0x1800016dc  push    rbp
0x1800016de  push    rbx
0x1800016df  push    rsi
0x1800016e0  push    rdi
0x1800016e1  push    r14
0x1800016e3  lea     rbp, [rsp-70h]
0x1800016e8  sub     rsp, 170h
0x1800016ef  mov     rax, cs:__security_cookie
0x1800016f6  xor     rax, rsp
0x1800016f9  mov     [rbp+90h+var_30], rax
0x1800016fd  mov     rax, [rbp+90h+arg_A0]
0x180001704  xor     edi, edi
0x180001706  mov     [rbp+90h+var_40], rax
0x18000170a  mov     r11, rdx
0x18000170d  mov     rax, [rbp+90h+arg_98]
0x180001714  mov     r10, rcx
0x180001717  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000171b  mov     [rbp+90h+var_38], 8
0x180001723  mov     rbx, r8
0x180001726  lea     r9d, [rdi+2]
0x18000172a  mov     rcx, [rax]
0x18000172d  test    rcx, rcx
0x180001730  jz      short loc_180001747
0x180001732  mov     rax, rdx
0x180001735  inc     rax
0x180001738  cmp     [rcx+rax*2], di
0x18000173c  jnz     short loc_180001735
0x18000173e  lea     eax, ds:2[rax*2]
0x180001745  jmp     short loc_180001751
0x180001747  lea     rcx, byte_1800138F4
0x18000174e  mov     eax, r9d
0x180001751  mov     [rbp+90h+var_48], eax
0x180001754  lea     rsi, word_1800138F6
0x18000175b  mov     rax, [rbp+90h+arg_90]
0x180001762  mov     r8d, 1
0x180001768  mov     [rbp+90h+var_50], rcx
0x18000176c  mov     [rbp+90h+var_44], edi
0x18000176f  mov     rcx, [rax]
0x180001772  test    rcx, rcx
0x180001775  jz      short loc_180001787
0x180001777  mov     rax, rdx
0x18000177a  inc     rax
0x18000177d  cmp     [rcx+rax], dil
0x180001781  jnz     short loc_18000177A
0x180001783  inc     eax
0x180001785  jmp     short loc_18000178D
0x180001787  mov     rcx, rsi
0x18000178a  mov     eax, r8d
0x18000178d  mov     [rbp+90h+var_58], eax
0x180001790  mov     rax, [rbp+90h+arg_88]
0x180001797  mov     [rbp+90h+var_70], rax
0x18000179b  mov     rax, [rbp+90h+arg_80]
0x1800017a2  mov     [rbp+90h+var_60], rcx
0x1800017a6  mov     [rbp+90h+var_54], edi
0x1800017a9  mov     [rbp+90h+var_68], 4
0x1800017b1  mov     rcx, [rax]
0x1800017b4  test    rcx, rcx
0x1800017b7  jz      short loc_1800017CE
0x1800017b9  mov     rax, rdx
0x1800017bc  inc     rax
0x1800017bf  cmp     [rcx+rax*2], di
0x1800017c3  jnz     short loc_1800017BC
0x1800017c5  lea     eax, ds:2[rax*2]
0x1800017cc  jmp     short loc_1800017D8
0x1800017ce  lea     rcx, byte_1800138F4
0x1800017d5  mov     eax, r9d
0x1800017d8  mov     [rbp+90h+var_78], eax
0x1800017db  mov     rax, [rbp+90h+arg_78]
0x1800017e2  mov     [rbp+90h+var_80], rcx
0x1800017e6  mov     [rbp+90h+var_74], edi
0x1800017e9  mov     rcx, [rax]
0x1800017ec  test    rcx, rcx
0x1800017ef  jz      short loc_180001801
0x1800017f1  mov     rax, rdx
0x1800017f4  inc     rax
0x1800017f7  cmp     [rcx+rax], dil
0x1800017fb  jnz     short loc_1800017F4
0x1800017fd  inc     eax
0x1800017ff  jmp     short loc_180001807
0x180001801  mov     rcx, rsi
0x180001804  mov     eax, r8d
0x180001807  mov     [rbp+90h+var_88], eax
0x18000180a  mov     rax, [rbp+90h+arg_70]
0x180001811  mov     [rbp+90h+var_A0], rax
0x180001815  mov     rax, [rbp+90h+arg_68]
0x18000181c  mov     [rbp+90h+var_90], rcx
0x180001820  mov     [rbp+90h+var_84], edi
0x180001823  mov     [rbp+90h+var_98], 4
0x18000182b  mov     rcx, [rax]
0x18000182e  test    rcx, rcx
0x180001831  jz      short loc_180001843
0x180001833  mov     rax, rdx
0x180001836  inc     rax
0x180001839  cmp     [rcx+rax], dil
0x18000183d  jnz     short loc_180001836
0x18000183f  inc     eax
0x180001841  jmp     short loc_180001849
0x180001843  mov     rcx, rsi
0x180001846  mov     eax, r8d
0x180001849  mov     [rbp+90h+var_A8], eax
0x18000184c  mov     rax, [rbp+90h+arg_60]
0x180001853  mov     [rbp+90h+var_C0], rax
0x180001857  mov     rax, [rbp+90h+arg_58]
0x18000185e  mov     [rbp+90h+var_B0], rcx
0x180001862  mov     [rbp+90h+var_A4], edi
0x180001865  mov     [rbp+90h+var_B8], 4
0x18000186d  mov     rcx, [rax]
0x180001870  test    rcx, rcx
0x180001873  jz      short loc_18000188B
0x180001875  mov     rax, rdx
0x180001878  inc     rax
0x18000187b  cmp     [rcx+rax*2], di
0x18000187f  jnz     short loc_180001878
0x180001881  lea     r9d, ds:2[rax*2]
0x180001889  jmp     short loc_180001892
0x18000188b  lea     rcx, byte_1800138F4
0x180001892  mov     rax, [rbp+90h+arg_50]
0x180001899  mov     [rbp+90h+var_E0], rax
0x18000189d  mov     rax, [rbp+90h+arg_48]
0x1800018a4  mov     [rbp+90h+var_D0], rcx
0x1800018a8  mov     [rbp+90h+var_C8], r9d
0x1800018ac  mov     [rbp+90h+var_C4], edi
0x1800018af  mov     rcx, [rax]
0x1800018b2  mov     [rbp+90h+var_D8], 4
0x1800018ba  test    rcx, rcx
0x1800018bd  jz      short loc_1800018CF
0x1800018bf  mov     rax, rdx
0x1800018c2  inc     rax
0x1800018c5  cmp     [rcx+rax], dil
0x1800018c9  jnz     short loc_1800018C2
0x1800018cb  inc     eax
0x1800018cd  jmp     short loc_1800018D5
0x1800018cf  mov     rcx, rsi
0x1800018d2  mov     eax, r8d
0x1800018d5  mov     [rbp+90h+var_E8], eax
0x1800018d8  mov     rax, [rbp+90h+arg_40]
0x1800018df  mov     [rbp+90h+var_100], rax
0x1800018e3  mov     rax, [rbp+90h+arg_38]
0x1800018ea  mov     [rbp+90h+var_F0], rcx
0x1800018ee  mov     [rbp+90h+var_E4], edi
0x1800018f1  mov     [rbp+90h+var_F8], 4
0x1800018f9  mov     rcx, [rax]
0x1800018fc  test    rcx, rcx
0x1800018ff  jz      short loc_180001910
0x180001901  inc     rdx
0x180001904  cmp     [rcx+rdx], dil
0x180001908  jnz     short loc_180001901
0x18000190a  lea     r8d, [rdx+1]
0x18000190e  jmp     short loc_180001913
0x180001910  mov     rcx, rsi
0x180001913  mov     rax, [rbp+90h+arg_30]
0x18000191a  xor     r9d, r9d
0x18000191d  mov     [rsp+190h+var_120], rax
0x180001922  mov     rdx, r11
0x180001925  mov     rax, [rbp+90h+arg_28]
0x18000192c  mov     [rsp+190h+var_130], rax
0x180001931  mov     rax, [rbp+90h+arg_20]
0x180001938  mov     [rsp+190h+var_140], rax
0x18000193d  lea     rax, [rsp+190h+var_160]
0x180001942  mov     [rbp+90h+var_110], rcx
0x180001946  mov     rcx, r10
0x180001949  mov     [rbp+90h+var_108], r8d
0x18000194d  mov     r8, rbx
0x180001950  mov     [rsp+190h+var_168], rax
0x180001955  mov     [rsp+190h+var_170], 13h
0x18000195d  mov     [rbp+90h+var_104], edi
0x180001960  mov     [rsp+190h+var_118], 4
0x180001969  mov     [rsp+190h+var_128], 8
0x180001972  mov     [rsp+190h+var_138], 8
0x18000197b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001980  mov     rcx, [rbp+90h+var_30]
0x180001984  xor     rcx, rsp; StackCookie
0x180001987  call    __security_check_cookie
0x18000198c  add     rsp, 170h
0x180001993  pop     r14
0x180001995  pop     rdi
0x180001996  pop     rsi
0x180001997  pop     rbx
0x180001998  pop     rbp
0x180001999  retn
```
