# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001608`
- end: `0x180001736`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34344@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010870`

## callees

- `0x18000131c`
- `0x180001608`
- `0x1800155c0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        __int64 a11)
{
  __int64 v12; // rcx
  int v13; // r8d
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  const unsigned __int16 *v20; // rdx
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+30h] [rbp-81h] BYREF
  const unsigned __int16 *v23; // [rsp+50h] [rbp-61h]
  int v24; // [rsp+58h] [rbp-59h]
  int v25; // [rsp+5Ch] [rbp-55h]
  __int64 v26; // [rsp+60h] [rbp-51h]
  __int64 v27; // [rsp+68h] [rbp-49h]
  const unsigned __int16 *v28; // [rsp+70h] [rbp-41h]
  int v29; // [rsp+78h] [rbp-39h]
  int v30; // [rsp+7Ch] [rbp-35h]
  __int64 v31; // [rsp+80h] [rbp-31h]
  __int64 v32; // [rsp+88h] [rbp-29h]
  const unsigned __int16 *v33; // [rsp+90h] [rbp-21h]
  int v34; // [rsp+98h] [rbp-19h]
  int v35; // [rsp+9Ch] [rbp-15h]
  __int64 v36; // [rsp+A0h] [rbp-11h]
  __int64 v37; // [rsp+A8h] [rbp-9h]
  __int64 v38; // [rsp+B0h] [rbp-1h]
  __int64 v39; // [rsp+B8h] [rbp+7h]

  v38 = a11;
  v36 = a10;
  v12 = -1;
  v39 = 4;
  v13 = 1;
  v37 = 4;
  v14 = *a9;
  if ( *a9 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_BYTE *)v14 + v15) );
    v16 = v15 + 1;
  }
  else
  {
    v14 = &qword_180018198;
    v16 = 1;
  }
  v34 = v16;
  v31 = a8;
  v33 = v14;
  v35 = 0;
  v32 = 4;
  v17 = *a7;
  if ( *a7 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_BYTE *)v17 + v18) );
    v19 = v18 + 1;
  }
  else
  {
    v17 = &qword_180018198;
    v19 = 1;
  }
  v29 = v19;
  v26 = a6;
  v28 = v17;
  v30 = 0;
  v27 = 4;
  v20 = *a5;
  if ( *a5 )
  {
    do
      ++v12;
    while ( *((_BYTE *)v20 + v12) );
    v13 = v12 + 1;
  }
  else
  {
    v20 = &qword_180018198;
  }
  v23 = v20;
  v24 = v13;
  v25 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001F000, a2, 0, 0, 9u, &v22);
}

```

## disassembly

```asm
0x180001608  push    rbp
0x18000160a  lea     rbp, [rsp-1Fh]
0x18000160f  sub     rsp, 0D0h
0x180001616  mov     rax, cs:__security_cookie
0x18000161d  xor     rax, rsp
0x180001620  mov     [rbp+1Fh+var_10], rax
0x180001624  mov     rax, [rbp+1Fh+arg_50]
0x180001628  lea     r11, qword_180018198
0x18000162f  mov     [rbp+1Fh+var_20], rax
0x180001633  xor     r9d, r9d
0x180001636  mov     rax, [rbp+1Fh+arg_48]
0x18000163a  mov     r10, rdx
0x18000163d  mov     [rbp+1Fh+var_30], rax
0x180001641  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001645  mov     rax, [rbp+1Fh+arg_40]
0x180001649  mov     [rbp+1Fh+var_18], 4
0x180001651  lea     r8d, [r9+1]
0x180001655  mov     [rbp+1Fh+var_28], 4
0x18000165d  mov     rdx, [rax]
0x180001660  test    rdx, rdx
0x180001663  jz      short loc_180001675
0x180001665  mov     rax, rcx
0x180001668  inc     rax
0x18000166b  cmp     [rdx+rax], r9b
0x18000166f  jnz     short loc_180001668
0x180001671  inc     eax
0x180001673  jmp     short loc_18000167B
0x180001675  mov     rdx, r11
0x180001678  mov     eax, r8d
0x18000167b  mov     [rbp+1Fh+var_38], eax
0x18000167e  mov     rax, [rbp+1Fh+arg_38]
0x180001682  mov     [rbp+1Fh+var_50], rax
0x180001686  mov     rax, [rbp+1Fh+arg_30]
0x18000168a  mov     [rbp+1Fh+var_40], rdx
0x18000168e  mov     [rbp+1Fh+var_34], r9d
0x180001692  mov     [rbp+1Fh+var_48], 4
0x18000169a  mov     rdx, [rax]
0x18000169d  test    rdx, rdx
0x1800016a0  jz      short loc_1800016B2
0x1800016a2  mov     rax, rcx
0x1800016a5  inc     rax
0x1800016a8  cmp     [rdx+rax], r9b
0x1800016ac  jnz     short loc_1800016A5
0x1800016ae  inc     eax
0x1800016b0  jmp     short loc_1800016B8
0x1800016b2  mov     rdx, r11
0x1800016b5  mov     eax, r8d
0x1800016b8  mov     [rbp+1Fh+var_58], eax
0x1800016bb  mov     rax, [rbp+1Fh+arg_28]
0x1800016bf  mov     [rbp+1Fh+var_70], rax
0x1800016c3  mov     rax, [rbp+1Fh+arg_20]
0x1800016c7  mov     [rbp+1Fh+var_60], rdx
0x1800016cb  mov     [rbp+1Fh+var_54], r9d
0x1800016cf  mov     [rbp+1Fh+var_68], 4
0x1800016d7  mov     rdx, [rax]
0x1800016da  test    rdx, rdx
0x1800016dd  jz      short loc_1800016EE
0x1800016df  inc     rcx
0x1800016e2  cmp     [rdx+rcx], r9b
0x1800016e6  jnz     short loc_1800016DF
0x1800016e8  lea     r8d, [rcx+1]
0x1800016ec  jmp     short loc_1800016F1
0x1800016ee  mov     rdx, r11
0x1800016f1  lea     rax, [rsp+0D0h+var_A0]
0x1800016f6  mov     [rbp+1Fh+var_80], rdx
0x1800016fa  mov     [rbp+1Fh+var_78], r8d
0x1800016fe  lea     rcx, dword_18001F000
0x180001705  mov     [rsp+0D0h+var_A8], rax
0x18000170a  xor     r8d, r8d
0x18000170d  mov     rdx, r10
0x180001710  mov     [rsp+0D0h+var_B0], 9
0x180001718  mov     [rbp+1Fh+var_74], r9d
0x18000171c  call    _tlgWriteTransfer_EventWriteTransfer
0x180001721  mov     rcx, [rbp+1Fh+var_10]
0x180001725  xor     rcx, rsp; StackCookie
0x180001728  call    __security_check_cookie
0x18000172d  add     rsp, 0D0h
0x180001734  pop     rbp
0x180001735  retn
```
