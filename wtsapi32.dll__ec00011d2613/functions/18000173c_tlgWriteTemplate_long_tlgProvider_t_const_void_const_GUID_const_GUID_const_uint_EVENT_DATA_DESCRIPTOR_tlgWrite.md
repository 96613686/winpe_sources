# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)

- ea: `0x18000173c`
- end: `0x180001898`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByRef@$0BA@@@@Z`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014c74`

## callees

- `0x18000131c`
- `0x18000173c`
- `0x1800155c0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        const unsigned __int16 **a8,
        unsigned __int16 **a9,
        __int64 a10,
        __int64 a11,
        __int64 *a12)
{
  __int64 v13; // rcx
  int v14; // r8d
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rax
  int v21; // eax
  const unsigned __int16 *v22; // rdx
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+30h] [rbp-A9h] BYREF
  const unsigned __int16 *v25; // [rsp+50h] [rbp-89h]
  int v26; // [rsp+58h] [rbp-81h]
  int v27; // [rsp+5Ch] [rbp-7Dh]
  __int64 v28; // [rsp+60h] [rbp-79h]
  __int64 v29; // [rsp+68h] [rbp-71h]
  const unsigned __int16 *v30; // [rsp+70h] [rbp-69h]
  int v31; // [rsp+78h] [rbp-61h]
  int v32; // [rsp+7Ch] [rbp-5Dh]
  const unsigned __int16 *v33; // [rsp+80h] [rbp-59h]
  int v34; // [rsp+88h] [rbp-51h]
  int v35; // [rsp+8Ch] [rbp-4Dh]
  _DWORD *v36; // [rsp+90h] [rbp-49h]
  __int64 v37; // [rsp+98h] [rbp-41h]
  __int64 v38; // [rsp+A0h] [rbp-39h]
  _DWORD v39[2]; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v40; // [rsp+B0h] [rbp-29h]
  __int64 v41; // [rsp+B8h] [rbp-21h]
  __int64 v42; // [rsp+C0h] [rbp-19h]
  __int64 v43; // [rsp+C8h] [rbp-11h]
  __int64 v44; // [rsp+D0h] [rbp-9h]
  __int64 v45; // [rsp+D8h] [rbp-1h]

  v45 = 16;
  v43 = 4;
  v41 = 4;
  v13 = *a12;
  v14 = 1;
  v42 = a11;
  v40 = a10;
  v36 = v39;
  v44 = v13;
  v37 = 2;
  LODWORD(v13) = **a9;
  v38 = *((_QWORD *)*a9 + 1);
  v39[0] = v13;
  v15 = -1;
  v39[1] = 0;
  v16 = *a8;
  if ( *a8 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_BYTE *)v16 + v17) );
    v18 = v17 + 1;
  }
  else
  {
    v16 = &qword_180018198;
    v18 = 1;
  }
  v34 = v18;
  v33 = v16;
  v35 = 0;
  v19 = *a7;
  if ( *a7 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *((_BYTE *)v19 + v20) );
    v21 = v20 + 1;
  }
  else
  {
    v19 = &qword_180018198;
    v21 = 1;
  }
  v31 = v21;
  v28 = a6;
  v30 = v19;
  v32 = 0;
  v29 = 8;
  v22 = *a5;
  if ( *a5 )
  {
    do
      ++v15;
    while ( *((_BYTE *)v22 + v15) );
    v14 = v15 + 1;
  }
  else
  {
    v22 = &qword_180018198;
  }
  v25 = v22;
  v26 = v14;
  v27 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001F000, a2, 0, 0, 0xBu, &v24);
}

```

## disassembly

```asm
0x18000173c  push    rbp
0x18000173e  lea     rbp, [rsp-17h]
0x180001743  sub     rsp, 0F0h
0x18000174a  mov     rax, cs:__security_cookie
0x180001751  xor     rax, rsp
0x180001754  mov     [rbp+17h+var_10], rax
0x180001758  mov     rax, [rbp+17h+arg_58]
0x18000175c  lea     r11, qword_180018198
0x180001763  xor     r9d, r9d
0x180001766  mov     [rbp+17h+var_18], 10h
0x18000176e  mov     [rbp+17h+var_28], 4
0x180001776  mov     r10, rdx
0x180001779  mov     [rbp+17h+var_38], 4
0x180001781  mov     rcx, [rax]
0x180001784  mov     rax, [rbp+17h+arg_50]
0x180001788  lea     r8d, [r9+1]
0x18000178c  mov     [rbp+17h+var_30], rax
0x180001790  mov     rax, [rbp+17h+arg_48]
0x180001794  mov     [rbp+17h+var_40], rax
0x180001798  lea     rax, [rbp+17h+var_48]
0x18000179c  mov     [rbp+17h+var_60], rax
0x1800017a0  mov     rax, [rbp+17h+arg_40]
0x1800017a4  mov     [rbp+17h+var_20], rcx
0x1800017a8  mov     [rbp+17h+var_58], 2
0x1800017b0  mov     rax, [rax]
0x1800017b3  movzx   ecx, word ptr [rax]
0x1800017b6  mov     rax, [rax+8]
0x1800017ba  mov     [rbp+17h+var_50], rax
0x1800017be  mov     rax, [rbp+17h+arg_38]
0x1800017c2  mov     [rbp+17h+var_48], ecx
0x1800017c5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800017c9  mov     [rbp+17h+var_44], r9d
0x1800017cd  mov     rdx, [rax]
0x1800017d0  test    rdx, rdx
0x1800017d3  jz      short loc_1800017E5
0x1800017d5  mov     rax, rcx
0x1800017d8  inc     rax
0x1800017db  cmp     [rdx+rax], r9b
0x1800017df  jnz     short loc_1800017D8
0x1800017e1  inc     eax
0x1800017e3  jmp     short loc_1800017EB
0x1800017e5  mov     rdx, r11
0x1800017e8  mov     eax, r8d
0x1800017eb  mov     [rbp+17h+var_68], eax
0x1800017ee  mov     rax, [rbp+17h+arg_30]
0x1800017f2  mov     [rbp+17h+var_70], rdx
0x1800017f6  mov     [rbp+17h+var_64], r9d
0x1800017fa  mov     rdx, [rax]
0x1800017fd  test    rdx, rdx
0x180001800  jz      short loc_180001812
0x180001802  mov     rax, rcx
0x180001805  inc     rax
0x180001808  cmp     [rdx+rax], r9b
0x18000180c  jnz     short loc_180001805
0x18000180e  inc     eax
0x180001810  jmp     short loc_180001818
0x180001812  mov     rdx, r11
0x180001815  mov     eax, r8d
0x180001818  mov     [rbp+17h+var_78], eax
0x18000181b  mov     rax, [rbp+17h+arg_28]
0x18000181f  mov     [rbp+17h+var_90], rax
0x180001823  mov     rax, [rbp+17h+arg_20]
0x180001827  mov     [rbp+17h+var_80], rdx
0x18000182b  mov     [rbp+17h+var_74], r9d
0x18000182f  mov     [rbp+17h+var_88], 8
0x180001837  mov     rdx, [rax]
0x18000183a  test    rdx, rdx
0x18000183d  jz      short loc_18000184E
0x18000183f  inc     rcx
0x180001842  cmp     [rdx+rcx], r9b
0x180001846  jnz     short loc_18000183F
0x180001848  lea     r8d, [rcx+1]
0x18000184c  jmp     short loc_180001851
0x18000184e  mov     rdx, r11
0x180001851  lea     rax, [rsp+0F0h+var_C0]
0x180001856  mov     [rsp+0F0h+var_A0], rdx
0x18000185b  mov     [rsp+0F0h+var_98], r8d
0x180001860  lea     rcx, dword_18001F000
0x180001867  mov     [rsp+0F0h+var_C8], rax
0x18000186c  xor     r8d, r8d
0x18000186f  mov     rdx, r10
0x180001872  mov     [rsp+0F0h+var_D0], 0Bh
0x18000187a  mov     [rbp+17h+var_94], r9d
0x18000187e  call    _tlgWriteTransfer_EventWriteTransfer
0x180001883  mov     rcx, [rbp+17h+var_10]
0x180001887  xor     rcx, rsp; StackCookie
0x18000188a  call    __security_check_cookie
0x18000188f  add     rsp, 0F0h
0x180001896  pop     rbp
0x180001897  retn
```
