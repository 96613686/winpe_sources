# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001614`
- end: `0x1800018bf`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180025740`

## callees

- `0x180001614`
- `0x1800018c8`
- `0x18002a590`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const CHAR **a8,
        __int64 a9,
        const CHAR **a10,
        __int64 a11,
        int **a12,
        __int64 a13,
        const CHAR **a14,
        __int64 a15,
        const CHAR **a16,
        int **a17,
        __int64 a18,
        const CHAR **a19,
        int **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  int *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const CHAR *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const CHAR *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const CHAR *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rdx
  __int64 v41; // rax
  const CHAR *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const CHAR *v45; // rdx
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  const CHAR *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const CHAR *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  int *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const CHAR *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const CHAR *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  int *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const CHAR *v82; // [rsp+130h] [rbp+30h]
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
    v24 = &dword_18002C8C4;
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
    while ( v28[v29] );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &Class;
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
    v31 = &dword_18002C8C4;
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
    while ( v34[v35] );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &Class;
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
    while ( v37[v38] );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &Class;
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
    v40 = &dword_18002C8C4;
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
    while ( v42[v43] );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &Class;
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
    while ( v45[v22] );
    v27 = v22 + 1;
  }
  else
  {
    v45 = &Class;
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
0x180001614  mov     [rsp-8+arg_10], rbx
0x180001619  push    rbp
0x18000161a  push    rsi
0x18000161b  push    rdi
0x18000161c  lea     rbp, [rsp-60h]
0x180001621  sub     rsp, 160h
0x180001628  mov     rax, cs:__security_cookie
0x18000162f  xor     rax, rsp
0x180001632  mov     [rbp+70h+var_20], rax
0x180001636  mov     rax, [rbp+70h+arg_98]
0x18000163d  mov     r11, rdx
0x180001640  mov     r10, rcx
0x180001643  xor     ebx, ebx
0x180001645  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001649  mov     r9d, 2
0x18000164f  mov     rdx, [rax]
0x180001652  test    rdx, rdx
0x180001655  jz      short loc_18000166C
0x180001657  mov     rax, rcx
0x18000165a  inc     rax
0x18000165d  cmp     [rdx+rax*2], bx
0x180001661  jnz     short loc_18000165A
0x180001663  lea     eax, ds:2[rax*2]
0x18000166a  jmp     short loc_180001676
0x18000166c  lea     rdx, dword_18002C8C4
0x180001673  mov     eax, r9d
0x180001676  mov     [rbp+70h+var_28], eax
0x180001679  lea     rdi, Class
0x180001680  mov     rax, [rbp+70h+arg_90]
0x180001687  mov     r8d, 1
0x18000168d  mov     [rbp+70h+var_30], rdx
0x180001691  mov     [rbp+70h+var_24], ebx
0x180001694  mov     rdx, [rax]
0x180001697  test    rdx, rdx
0x18000169a  jz      short loc_1800016AB
0x18000169c  mov     rax, rcx
0x18000169f  inc     rax
0x1800016a2  cmp     [rdx+rax], bl
0x1800016a5  jnz     short loc_18000169F
0x1800016a7  inc     eax
0x1800016a9  jmp     short loc_1800016B1
0x1800016ab  mov     rdx, rdi
0x1800016ae  mov     eax, r8d
0x1800016b1  mov     [rbp+70h+var_38], eax
0x1800016b4  mov     rax, [rbp+70h+arg_88]
0x1800016bb  mov     [rbp+70h+var_50], rax
0x1800016bf  mov     rax, [rbp+70h+arg_80]
0x1800016c6  mov     [rbp+70h+var_40], rdx
0x1800016ca  mov     [rbp+70h+var_34], ebx
0x1800016cd  mov     [rbp+70h+var_48], 4
0x1800016d5  mov     rdx, [rax]
0x1800016d8  test    rdx, rdx
0x1800016db  jz      short loc_1800016F2
0x1800016dd  mov     rax, rcx
0x1800016e0  inc     rax
0x1800016e3  cmp     [rdx+rax*2], bx
0x1800016e7  jnz     short loc_1800016E0
0x1800016e9  lea     eax, ds:2[rax*2]
0x1800016f0  jmp     short loc_1800016FC
0x1800016f2  lea     rdx, dword_18002C8C4
0x1800016f9  mov     eax, r9d
0x1800016fc  mov     [rbp+70h+var_58], eax
0x1800016ff  mov     rax, [rbp+70h+arg_78]
0x180001706  mov     [rbp+70h+var_60], rdx
0x18000170a  mov     [rbp+70h+var_54], ebx
0x18000170d  mov     rdx, [rax]
0x180001710  test    rdx, rdx
0x180001713  jz      short loc_180001724
0x180001715  mov     rax, rcx
0x180001718  inc     rax
0x18000171b  cmp     [rdx+rax], bl
0x18000171e  jnz     short loc_180001718
0x180001720  inc     eax
0x180001722  jmp     short loc_18000172A
0x180001724  mov     rdx, rdi
0x180001727  mov     eax, r8d
0x18000172a  mov     [rbp+70h+var_68], eax
0x18000172d  mov     rax, [rbp+70h+arg_70]
0x180001734  mov     [rbp+70h+var_80], rax
0x180001738  mov     rax, [rbp+70h+arg_68]
0x18000173f  mov     [rbp+70h+var_70], rdx
0x180001743  mov     [rbp+70h+var_64], ebx
0x180001746  mov     [rbp+70h+var_78], 4
0x18000174e  mov     rdx, [rax]
0x180001751  test    rdx, rdx
0x180001754  jz      short loc_180001765
0x180001756  mov     rax, rcx
0x180001759  inc     rax
0x18000175c  cmp     [rdx+rax], bl
0x18000175f  jnz     short loc_180001759
0x180001761  inc     eax
0x180001763  jmp     short loc_18000176B
0x180001765  mov     rdx, rdi
0x180001768  mov     eax, r8d
0x18000176b  mov     [rbp+70h+var_88], eax
0x18000176e  mov     rax, [rbp+70h+arg_60]
0x180001775  mov     [rbp+70h+var_A0], rax
0x180001779  mov     rax, [rbp+70h+arg_58]
0x180001780  mov     [rbp+70h+var_90], rdx
0x180001784  mov     [rbp+70h+var_84], ebx
0x180001787  mov     [rbp+70h+var_98], 4
0x18000178f  mov     rdx, [rax]
0x180001792  test    rdx, rdx
0x180001795  jz      short loc_1800017AD
0x180001797  mov     rax, rcx
0x18000179a  inc     rax
0x18000179d  cmp     [rdx+rax*2], bx
0x1800017a1  jnz     short loc_18000179A
0x1800017a3  lea     r9d, ds:2[rax*2]
0x1800017ab  jmp     short loc_1800017B4
0x1800017ad  lea     rdx, dword_18002C8C4
0x1800017b4  mov     rax, [rbp+70h+arg_50]
0x1800017bb  mov     [rbp+70h+var_C0], rax
0x1800017bf  mov     rax, [rbp+70h+arg_48]
0x1800017c6  mov     [rbp+70h+var_B0], rdx
0x1800017ca  mov     [rbp+70h+var_A8], r9d
0x1800017ce  mov     [rbp+70h+var_A4], ebx
0x1800017d1  mov     rdx, [rax]
0x1800017d4  mov     [rbp+70h+var_B8], 4
0x1800017dc  test    rdx, rdx
0x1800017df  jz      short loc_1800017F0
0x1800017e1  mov     rax, rcx
0x1800017e4  inc     rax
0x1800017e7  cmp     [rdx+rax], bl
0x1800017ea  jnz     short loc_1800017E4
0x1800017ec  inc     eax
0x1800017ee  jmp     short loc_1800017F6
0x1800017f0  mov     rdx, rdi
0x1800017f3  mov     eax, r8d
0x1800017f6  mov     [rbp+70h+var_C8], eax
0x1800017f9  mov     rax, [rbp+70h+arg_40]
0x180001800  mov     [rbp+70h+var_E0], rax
0x180001804  mov     rax, [rbp+70h+arg_38]
0x18000180b  mov     [rbp+70h+var_D0], rdx
0x18000180f  mov     [rbp+70h+var_C4], ebx
0x180001812  mov     [rbp+70h+var_D8], 4
0x18000181a  mov     rdx, [rax]
0x18000181d  test    rdx, rdx
0x180001820  jz      short loc_180001830
0x180001822  inc     rcx
0x180001825  cmp     [rdx+rcx], bl
0x180001828  jnz     short loc_180001822
0x18000182a  lea     r8d, [rcx+1]
0x18000182e  jmp     short loc_180001833
0x180001830  mov     rdx, rdi
0x180001833  mov     rax, [rbp+70h+arg_30]
0x18000183a  xor     r9d, r9d
0x18000183d  mov     [rsp+170h+var_100], rax
0x180001842  mov     rcx, r10
0x180001845  mov     rax, [rbp+70h+arg_28]
0x18000184c  mov     [rsp+170h+var_110], rax
0x180001851  mov     rax, [rbp+70h+arg_20]
0x180001858  mov     [rsp+170h+var_120], rax
0x18000185d  lea     rax, [rsp+170h+var_140]
0x180001862  mov     [rbp+70h+var_F0], rdx
0x180001866  mov     rdx, r11
0x180001869  mov     [rbp+70h+var_E8], r8d
0x18000186d  xor     r8d, r8d
0x180001870  mov     [rsp+170h+var_148], rax
0x180001875  mov     [rsp+170h+var_150], 12h
0x18000187d  mov     [rbp+70h+var_E4], ebx
0x180001880  mov     [rsp+170h+var_F8], 4
0x180001889  mov     [rsp+170h+var_108], 8
0x180001892  mov     [rsp+170h+var_118], 8
0x18000189b  call    _tlgWriteTransfer_EventWriteTransfer
0x1800018a0  mov     rcx, [rbp+70h+var_20]
0x1800018a4  xor     rcx, rsp; StackCookie
0x1800018a7  call    __security_check_cookie
0x1800018ac  mov     rbx, [rsp+170h+arg_10]
0x1800018b4  add     rsp, 160h
0x1800018bb  pop     rdi
0x1800018bc  pop     rsi
0x1800018bd  pop     rbp
0x1800018be  retn
```
