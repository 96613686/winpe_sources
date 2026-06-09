# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001cb8`
- end: `0x180001f64`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `684`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fa60`

## callees

- `0x180001cb8`
- `0x180005a74`
- `0x180008a90`

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
        const unsigned __int16 **a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        __int64 **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        __int64 **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        __int64 **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  __int64 *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  __int64 *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  __int64 *v40; // rdx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rdx
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  __int64 *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  __int64 *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v85; // [rsp+140h] [rbp+40h]
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
    v24 = &qword_180022030;
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
    v28 = &dword_18002202C;
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
    v31 = &qword_180022030;
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
    v34 = &dword_18002202C;
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
    v37 = &dword_18002202C;
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
    v40 = &qword_180022030;
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
    v42 = &dword_18002202C;
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
    v45 = &dword_18002202C;
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
0x180001cb8  mov     [rsp-8+arg_10], rbx
0x180001cbd  push    rbp
0x180001cbe  push    rsi
0x180001cbf  push    rdi
0x180001cc0  lea     rbp, [rsp-60h]
0x180001cc5  sub     rsp, 160h
0x180001ccc  mov     rax, cs:__security_cookie
0x180001cd3  xor     rax, rsp
0x180001cd6  mov     [rbp+70h+var_20], rax
0x180001cda  mov     rax, [rbp+70h+arg_98]
0x180001ce1  mov     r11, rdx
0x180001ce4  mov     r10, rcx
0x180001ce7  xor     ebx, ebx
0x180001ce9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001ced  mov     r9d, 2
0x180001cf3  mov     rdx, [rax]
0x180001cf6  test    rdx, rdx
0x180001cf9  jz      short loc_180001D10
0x180001cfb  mov     rax, rcx
0x180001cfe  inc     rax
0x180001d01  cmp     [rdx+rax*2], bx
0x180001d05  jnz     short loc_180001CFE
0x180001d07  lea     eax, ds:2[rax*2]
0x180001d0e  jmp     short loc_180001D1A
0x180001d10  lea     rdx, qword_180022030
0x180001d17  mov     eax, r9d
0x180001d1a  mov     [rbp+70h+var_28], eax
0x180001d1d  lea     rdi, dword_18002202C
0x180001d24  mov     rax, [rbp+70h+arg_90]
0x180001d2b  mov     r8d, 1
0x180001d31  mov     [rbp+70h+var_30], rdx
0x180001d35  mov     [rbp+70h+var_24], ebx
0x180001d38  mov     rdx, [rax]
0x180001d3b  test    rdx, rdx
0x180001d3e  jz      short loc_180001D4F
0x180001d40  mov     rax, rcx
0x180001d43  inc     rax
0x180001d46  cmp     [rdx+rax], bl
0x180001d49  jnz     short loc_180001D43
0x180001d4b  inc     eax
0x180001d4d  jmp     short loc_180001D55
0x180001d4f  mov     rdx, rdi
0x180001d52  mov     eax, r8d
0x180001d55  mov     [rbp+70h+var_38], eax
0x180001d58  mov     rax, [rbp+70h+arg_88]
0x180001d5f  mov     [rbp+70h+var_50], rax
0x180001d63  mov     rax, [rbp+70h+arg_80]
0x180001d6a  mov     [rbp+70h+var_40], rdx
0x180001d6e  mov     [rbp+70h+var_34], ebx
0x180001d71  mov     [rbp+70h+var_48], 4
0x180001d79  mov     rdx, [rax]
0x180001d7c  test    rdx, rdx
0x180001d7f  jz      short loc_180001D96
0x180001d81  mov     rax, rcx
0x180001d84  inc     rax
0x180001d87  cmp     [rdx+rax*2], bx
0x180001d8b  jnz     short loc_180001D84
0x180001d8d  lea     eax, ds:2[rax*2]
0x180001d94  jmp     short loc_180001DA0
0x180001d96  lea     rdx, qword_180022030
0x180001d9d  mov     eax, r9d
0x180001da0  mov     [rbp+70h+var_58], eax
0x180001da3  mov     rax, [rbp+70h+arg_78]
0x180001daa  mov     [rbp+70h+var_60], rdx
0x180001dae  mov     [rbp+70h+var_54], ebx
0x180001db1  mov     rdx, [rax]
0x180001db4  test    rdx, rdx
0x180001db7  jz      short loc_180001DC8
0x180001db9  mov     rax, rcx
0x180001dbc  inc     rax
0x180001dbf  cmp     [rdx+rax], bl
0x180001dc2  jnz     short loc_180001DBC
0x180001dc4  inc     eax
0x180001dc6  jmp     short loc_180001DCE
0x180001dc8  mov     rdx, rdi
0x180001dcb  mov     eax, r8d
0x180001dce  mov     [rbp+70h+var_68], eax
0x180001dd1  mov     rax, [rbp+70h+arg_70]
0x180001dd8  mov     [rbp+70h+var_80], rax
0x180001ddc  mov     rax, [rbp+70h+arg_68]
0x180001de3  mov     [rbp+70h+var_70], rdx
0x180001de7  mov     [rbp+70h+var_64], ebx
0x180001dea  mov     [rbp+70h+var_78], 4
0x180001df2  mov     rdx, [rax]
0x180001df5  test    rdx, rdx
0x180001df8  jz      short loc_180001E09
0x180001dfa  mov     rax, rcx
0x180001dfd  inc     rax
0x180001e00  cmp     [rdx+rax], bl
0x180001e03  jnz     short loc_180001DFD
0x180001e05  inc     eax
0x180001e07  jmp     short loc_180001E0F
0x180001e09  mov     rdx, rdi
0x180001e0c  mov     eax, r8d
0x180001e0f  mov     [rbp+70h+var_88], eax
0x180001e12  mov     rax, [rbp+70h+arg_60]
0x180001e19  mov     [rbp+70h+var_A0], rax
0x180001e1d  mov     rax, [rbp+70h+arg_58]
0x180001e24  mov     [rbp+70h+var_90], rdx
0x180001e28  mov     [rbp+70h+var_84], ebx
0x180001e2b  mov     [rbp+70h+var_98], 4
0x180001e33  mov     rdx, [rax]
0x180001e36  test    rdx, rdx
0x180001e39  jz      short loc_180001E51
0x180001e3b  mov     rax, rcx
0x180001e3e  inc     rax
0x180001e41  cmp     [rdx+rax*2], bx
0x180001e45  jnz     short loc_180001E3E
0x180001e47  lea     r9d, ds:2[rax*2]
0x180001e4f  jmp     short loc_180001E58
0x180001e51  lea     rdx, qword_180022030
0x180001e58  mov     rax, [rbp+70h+arg_50]
0x180001e5f  mov     [rbp+70h+var_C0], rax
0x180001e63  mov     rax, [rbp+70h+arg_48]
0x180001e6a  mov     [rbp+70h+var_B0], rdx
0x180001e6e  mov     [rbp+70h+var_A8], r9d
0x180001e72  mov     [rbp+70h+var_A4], ebx
0x180001e75  mov     rdx, [rax]
0x180001e78  mov     [rbp+70h+var_B8], 4
0x180001e80  test    rdx, rdx
0x180001e83  jz      short loc_180001E94
0x180001e85  mov     rax, rcx
0x180001e88  inc     rax
0x180001e8b  cmp     [rdx+rax], bl
0x180001e8e  jnz     short loc_180001E88
0x180001e90  inc     eax
0x180001e92  jmp     short loc_180001E9A
0x180001e94  mov     rdx, rdi
0x180001e97  mov     eax, r8d
0x180001e9a  mov     [rbp+70h+var_C8], eax
0x180001e9d  mov     rax, [rbp+70h+arg_40]
0x180001ea4  mov     [rbp+70h+var_E0], rax
0x180001ea8  mov     rax, [rbp+70h+arg_38]
0x180001eaf  mov     [rbp+70h+var_D0], rdx
0x180001eb3  mov     [rbp+70h+var_C4], ebx
0x180001eb6  mov     [rbp+70h+var_D8], 4
0x180001ebe  mov     rdx, [rax]
0x180001ec1  test    rdx, rdx
0x180001ec4  jz      short loc_180001ED4
0x180001ec6  inc     rcx
0x180001ec9  cmp     [rdx+rcx], bl
0x180001ecc  jnz     short loc_180001EC6
0x180001ece  lea     r8d, [rcx+1]
0x180001ed2  jmp     short loc_180001ED7
0x180001ed4  mov     rdx, rdi
0x180001ed7  mov     rax, [rbp+70h+arg_30]
0x180001ede  xor     r9d, r9d; int
0x180001ee1  mov     [rsp+170h+var_100], rax
0x180001ee6  mov     rcx, r10; int
0x180001ee9  mov     rax, [rbp+70h+arg_28]
0x180001ef0  mov     [rsp+170h+var_110], rax
0x180001ef5  mov     rax, [rbp+70h+arg_20]
0x180001efc  mov     [rsp+170h+var_120], rax
0x180001f01  lea     rax, [rsp+170h+var_140]
0x180001f06  mov     [rbp+70h+var_F0], rdx
0x180001f0a  mov     rdx, r11; int
0x180001f0d  mov     [rbp+70h+var_E8], r8d
0x180001f11  xor     r8d, r8d; int
0x180001f14  mov     [rsp+170h+var_148], rax; PEVENT_DATA_DESCRIPTOR
0x180001f19  mov     [rsp+170h+var_150], 12h; ULONG
0x180001f21  mov     [rbp+70h+var_E4], ebx
0x180001f24  mov     [rsp+170h+var_F8], 4
0x180001f2d  mov     [rsp+170h+var_108], 8
0x180001f36  mov     [rsp+170h+var_118], 8
0x180001f3f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001f44  mov     rcx, [rbp+70h+var_20]
0x180001f48  xor     rcx, rsp; StackCookie
0x180001f4b  call    __security_check_cookie
0x180001f50  mov     rbx, [rsp+170h+arg_10]
0x180001f58  add     rsp, 160h
0x180001f5f  pop     rdi
0x180001f60  pop     rsi
0x180001f61  pop     rbp
0x180001f62  retn
```
