# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001288`
- end: `0x1800013d8`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `336`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e5b0`

## callees

- `0x180001288`
- `0x180005a74`
- `0x180008a90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6,
        __int64 *a7,
        __int64 **a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  __int64 v14; // rdx
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  int v18; // r8d
  const unsigned __int16 *v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  const unsigned __int16 *v22; // rcx
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+30h] [rbp-99h] BYREF
  const unsigned __int16 *v25; // [rsp+50h] [rbp-79h]
  int v26; // [rsp+58h] [rbp-71h]
  int v27; // [rsp+5Ch] [rbp-6Dh]
  const unsigned __int16 *v28; // [rsp+60h] [rbp-69h]
  int v29; // [rsp+68h] [rbp-61h]
  int v30; // [rsp+6Ch] [rbp-5Dh]
  __int64 v31; // [rsp+70h] [rbp-59h]
  __int64 v32; // [rsp+78h] [rbp-51h]
  __int64 *v33; // [rsp+80h] [rbp-49h]
  int v34; // [rsp+88h] [rbp-41h]
  int v35; // [rsp+8Ch] [rbp-3Dh]
  __int64 v36; // [rsp+90h] [rbp-39h]
  __int64 v37; // [rsp+98h] [rbp-31h]
  __int64 v38; // [rsp+A0h] [rbp-29h]
  __int64 v39; // [rsp+A8h] [rbp-21h]
  __int64 v40; // [rsp+B0h] [rbp-19h]
  __int64 v41; // [rsp+B8h] [rbp-11h]
  __int64 v42; // [rsp+C0h] [rbp-9h]
  __int64 v43; // [rsp+C8h] [rbp-1h]

  v42 = a12;
  v40 = a11;
  v14 = -1;
  v38 = a10;
  v36 = a9;
  v43 = 8;
  v41 = 4;
  v39 = 4;
  v15 = *a8;
  v37 = 4;
  if ( v15 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &qword_180022030;
    v17 = 2;
  }
  v34 = v17;
  v18 = 1;
  v33 = v15;
  v35 = 0;
  v32 = 16;
  v31 = *a7;
  v19 = *a6;
  if ( *a6 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *((_BYTE *)v19 + v20) );
    v21 = v20 + 1;
  }
  else
  {
    v19 = &dword_18002202C;
    v21 = 1;
  }
  v29 = v21;
  v28 = v19;
  v30 = 0;
  v22 = *a5;
  if ( *a5 )
  {
    do
      ++v14;
    while ( *((_BYTE *)v22 + v14) );
    v18 = v14 + 1;
  }
  else
  {
    v22 = &dword_18002202C;
  }
  v25 = v22;
  v26 = v18;
  v27 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0xAu, &v24);
}

```

## disassembly

```asm
0x180001288  push    rbp
0x18000128a  lea     rbp, [rsp-17h]
0x18000128f  sub     rsp, 0E0h
0x180001296  mov     rax, cs:__security_cookie
0x18000129d  xor     rax, rsp
0x1800012a0  mov     [rbp+17h+var_10], rax
0x1800012a4  mov     rax, [rbp+17h+arg_58]
0x1800012a8  mov     r11, rdx
0x1800012ab  mov     [rbp+17h+var_20], rax
0x1800012af  mov     r10, rcx
0x1800012b2  mov     rax, [rbp+17h+arg_50]
0x1800012b6  xor     r9d, r9d; int
0x1800012b9  mov     [rbp+17h+var_30], rax
0x1800012bd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800012c1  mov     rax, [rbp+17h+arg_48]
0x1800012c5  mov     [rbp+17h+var_40], rax
0x1800012c9  mov     rax, [rbp+17h+arg_40]
0x1800012cd  mov     [rbp+17h+var_50], rax
0x1800012d1  mov     rax, [rbp+17h+arg_38]
0x1800012d5  mov     [rbp+17h+var_18], 8
0x1800012dd  mov     [rbp+17h+var_28], 4
0x1800012e5  mov     [rbp+17h+var_38], 4
0x1800012ed  mov     rcx, [rax]
0x1800012f0  mov     [rbp+17h+var_48], 4
0x1800012f8  test    rcx, rcx
0x1800012fb  jz      short loc_180001313
0x1800012fd  mov     rax, rdx
0x180001300  inc     rax
0x180001303  cmp     [rcx+rax*2], r9w
0x180001308  jnz     short loc_180001300
0x18000130a  lea     eax, ds:2[rax*2]
0x180001311  jmp     short loc_18000131F
0x180001313  lea     rcx, qword_180022030
0x18000131a  mov     eax, 2
0x18000131f  mov     [rbp+17h+var_58], eax
0x180001322  mov     r8d, 1
0x180001328  mov     rax, [rbp+17h+arg_30]
0x18000132c  mov     [rbp+17h+var_60], rcx
0x180001330  mov     [rbp+17h+var_54], r9d
0x180001334  mov     [rbp+17h+var_68], 10h
0x18000133c  mov     rcx, [rax]
0x18000133f  mov     rax, [rbp+17h+arg_28]
0x180001343  mov     [rbp+17h+var_70], rcx
0x180001347  mov     rcx, [rax]
0x18000134a  test    rcx, rcx
0x18000134d  jz      short loc_18000135F
0x18000134f  mov     rax, rdx
0x180001352  inc     rax
0x180001355  cmp     [rcx+rax], r9b
0x180001359  jnz     short loc_180001352
0x18000135b  inc     eax
0x18000135d  jmp     short loc_180001369
0x18000135f  lea     rcx, dword_18002202C
0x180001366  mov     eax, r8d
0x180001369  mov     [rbp+17h+var_78], eax
0x18000136c  mov     rax, [rbp+17h+arg_20]
0x180001370  mov     [rbp+17h+var_80], rcx
0x180001374  mov     [rbp+17h+var_74], r9d
0x180001378  mov     rcx, [rax]
0x18000137b  test    rcx, rcx
0x18000137e  jz      short loc_18000138F
0x180001380  inc     rdx
0x180001383  cmp     [rcx+rdx], r9b
0x180001387  jnz     short loc_180001380
0x180001389  lea     r8d, [rdx+1]
0x18000138d  jmp     short loc_180001396
0x18000138f  lea     rcx, dword_18002202C
0x180001396  lea     rax, [rsp+0E0h+var_B0]
0x18000139b  mov     [rbp+17h+var_90], rcx
0x18000139f  mov     [rbp+17h+var_88], r8d
0x1800013a3  mov     rdx, r11; int
0x1800013a6  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x1800013ab  xor     r8d, r8d; int
0x1800013ae  mov     rcx, r10; int
0x1800013b1  mov     [rsp+0E0h+var_C0], 0Ah; ULONG
0x1800013b9  mov     [rbp+17h+var_84], r9d
0x1800013bd  call    _tlgWriteTransfer_EventWriteTransfer
0x1800013c2  mov     rcx, [rbp+17h+var_10]
0x1800013c6  xor     rcx, rsp; StackCookie
0x1800013c9  call    __security_check_cookie
0x1800013ce  add     rsp, 0E0h
0x1800013d5  pop     rbp
0x1800013d6  retn
```
