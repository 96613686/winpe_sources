# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800011c8`
- end: `0x1800012e5`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015050`

## callees

- `0x1800011c8`
- `0x18000131c`
- `0x1800155c0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10)
{
  __int64 v11; // rcx
  int v12; // r8d
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v22; // [rsp+50h] [rbp-49h]
  int v23; // [rsp+58h] [rbp-41h]
  int v24; // [rsp+5Ch] [rbp-3Dh]
  __int64 v25; // [rsp+60h] [rbp-39h]
  __int64 v26; // [rsp+68h] [rbp-31h]
  const unsigned __int16 *v27; // [rsp+70h] [rbp-29h]
  int v28; // [rsp+78h] [rbp-21h]
  int v29; // [rsp+7Ch] [rbp-1Dh]
  __int64 v30; // [rsp+80h] [rbp-19h]
  __int64 v31; // [rsp+88h] [rbp-11h]
  const unsigned __int16 *v32; // [rsp+90h] [rbp-9h]
  int v33; // [rsp+98h] [rbp-1h]
  int v34; // [rsp+9Ch] [rbp+3h]
  __int64 v35; // [rsp+A0h] [rbp+7h]
  __int64 v36; // [rsp+A8h] [rbp+Fh]

  v35 = a10;
  v11 = -1;
  v36 = 4;
  v12 = 1;
  v13 = *a9;
  if ( *a9 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)v13 + v14) );
    v15 = v14 + 1;
  }
  else
  {
    v13 = &qword_180018198;
    v15 = 1;
  }
  v33 = v15;
  v30 = a8;
  v32 = v13;
  v34 = 0;
  v31 = 4;
  v16 = *a7;
  if ( *a7 )
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
  v28 = v18;
  v25 = a6;
  v27 = v16;
  v29 = 0;
  v26 = 4;
  v19 = *a5;
  if ( *a5 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v19 + v11) );
    v12 = v11 + 1;
  }
  else
  {
    v19 = &qword_180018198;
  }
  v22 = v19;
  v23 = v12;
  v24 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001F000, a2, 0, 0, 8u, &v21);
}

```

## disassembly

```asm
0x1800011c8  push    rbp
0x1800011ca  lea     rbp, [rsp-27h]
0x1800011cf  sub     rsp, 0C0h
0x1800011d6  mov     rax, cs:__security_cookie
0x1800011dd  xor     rax, rsp
0x1800011e0  mov     [rbp+27h+var_10], rax
0x1800011e4  mov     rax, [rbp+27h+arg_48]
0x1800011e8  lea     r11, qword_180018198
0x1800011ef  xor     r9d, r9d
0x1800011f2  mov     [rbp+27h+var_20], rax
0x1800011f6  mov     rax, [rbp+27h+arg_40]
0x1800011fa  mov     r10, rdx
0x1800011fd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001201  mov     [rbp+27h+var_18], 4
0x180001209  lea     r8d, [r9+1]
0x18000120d  mov     rdx, [rax]
0x180001210  test    rdx, rdx
0x180001213  jz      short loc_180001225
0x180001215  mov     rax, rcx
0x180001218  inc     rax
0x18000121b  cmp     [rdx+rax], r9b
0x18000121f  jnz     short loc_180001218
0x180001221  inc     eax
0x180001223  jmp     short loc_18000122B
0x180001225  mov     rdx, r11
0x180001228  mov     eax, r8d
0x18000122b  mov     [rbp+27h+var_28], eax
0x18000122e  mov     rax, [rbp+27h+arg_38]
0x180001232  mov     [rbp+27h+var_40], rax
0x180001236  mov     rax, [rbp+27h+arg_30]
0x18000123a  mov     [rbp+27h+var_30], rdx
0x18000123e  mov     [rbp+27h+var_24], r9d
0x180001242  mov     [rbp+27h+var_38], 4
0x18000124a  mov     rdx, [rax]
0x18000124d  test    rdx, rdx
0x180001250  jz      short loc_180001262
0x180001252  mov     rax, rcx
0x180001255  inc     rax
0x180001258  cmp     [rdx+rax], r9b
0x18000125c  jnz     short loc_180001255
0x18000125e  inc     eax
0x180001260  jmp     short loc_180001268
0x180001262  mov     rdx, r11
0x180001265  mov     eax, r8d
0x180001268  mov     [rbp+27h+var_48], eax
0x18000126b  mov     rax, [rbp+27h+arg_28]
0x18000126f  mov     [rbp+27h+var_60], rax
0x180001273  mov     rax, [rbp+27h+arg_20]
0x180001277  mov     [rbp+27h+var_50], rdx
0x18000127b  mov     [rbp+27h+var_44], r9d
0x18000127f  mov     [rbp+27h+var_58], 4
0x180001287  mov     rdx, [rax]
0x18000128a  test    rdx, rdx
0x18000128d  jz      short loc_18000129E
0x18000128f  inc     rcx
0x180001292  cmp     [rdx+rcx], r9b
0x180001296  jnz     short loc_18000128F
0x180001298  lea     r8d, [rcx+1]
0x18000129c  jmp     short loc_1800012A1
0x18000129e  mov     rdx, r11
0x1800012a1  lea     rax, [rbp+27h+var_90]
0x1800012a5  mov     [rbp+27h+var_70], rdx
0x1800012a9  mov     [rbp+27h+var_68], r8d
0x1800012ad  lea     rcx, dword_18001F000
0x1800012b4  mov     [rsp+0C0h+var_98], rax
0x1800012b9  xor     r8d, r8d
0x1800012bc  mov     rdx, r10
0x1800012bf  mov     [rsp+0C0h+var_A0], 8
0x1800012c7  mov     [rbp+27h+var_64], r9d
0x1800012cb  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012d0  mov     rcx, [rbp+27h+var_10]
0x1800012d4  xor     rcx, rsp; StackCookie
0x1800012d7  call    __security_check_cookie
0x1800012dc  add     rsp, 0C0h
0x1800012e3  pop     rbp
0x1800012e4  retn
```
