# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001cb0`
- end: `0x180001dbc`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333333AEBU?$_tlgWrapSz@D@@3@Z`
- size: `268`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006f18`

## callees

- `0x180001010`
- `0x180001cb0`
- `0x180002410`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int16 **a12,
        __int64 a13)
{
  __int16 *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  _BYTE v17[32]; // [rsp+30h] [rbp-B1h] BYREF
  __int64 v18; // [rsp+50h] [rbp-91h]
  __int64 v19; // [rsp+58h] [rbp-89h]
  __int64 v20; // [rsp+60h] [rbp-81h]
  __int64 v21; // [rsp+68h] [rbp-79h]
  __int64 v22; // [rsp+70h] [rbp-71h]
  __int64 v23; // [rsp+78h] [rbp-69h]
  __int64 v24; // [rsp+80h] [rbp-61h]
  __int64 v25; // [rsp+88h] [rbp-59h]
  __int64 v26; // [rsp+90h] [rbp-51h]
  __int64 v27; // [rsp+98h] [rbp-49h]
  __int64 v28; // [rsp+A0h] [rbp-41h]
  __int64 v29; // [rsp+A8h] [rbp-39h]
  __int64 v30; // [rsp+B0h] [rbp-31h]
  __int64 v31; // [rsp+B8h] [rbp-29h]
  __int16 *v32; // [rsp+C0h] [rbp-21h]
  int v33; // [rsp+C8h] [rbp-19h]
  int v34; // [rsp+CCh] [rbp-15h]
  __int64 v35; // [rsp+D0h] [rbp-11h]
  __int64 v36; // [rsp+D8h] [rbp-9h]

  v35 = a13;
  v36 = 4;
  v13 = *a12;
  if ( *a12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)v13 + v14) );
    v15 = v14 + 1;
  }
  else
  {
    v13 = &word_180013A56;
    v15 = 1;
  }
  v33 = v15;
  v30 = a11;
  v28 = a10;
  v26 = a9;
  v24 = a8;
  v22 = a7;
  v20 = a6;
  v18 = a5;
  v32 = v13;
  v34 = 0;
  v31 = 4;
  v29 = 4;
  v27 = 4;
  v25 = 4;
  v23 = 4;
  v21 = 4;
  v19 = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C038, a2, 0, 0, 11, v17);
}

```

## disassembly

```asm
0x180001cb0  push    rbp
0x180001cb2  lea     rbp, [rsp-0Fh]
0x180001cb7  sub     rsp, 0F0h
0x180001cbe  mov     rax, cs:__security_cookie
0x180001cc5  xor     rax, rsp
0x180001cc8  mov     [rbp+0Fh+var_10], rax
0x180001ccc  mov     rax, [rbp+0Fh+arg_60]
0x180001cd0  xor     r8d, r8d
0x180001cd3  mov     [rbp+0Fh+var_20], rax
0x180001cd7  mov     rax, [rbp+0Fh+arg_58]
0x180001cdb  mov     [rbp+0Fh+var_18], 4
0x180001ce3  mov     rcx, [rax]
0x180001ce6  test    rcx, rcx
0x180001ce9  jz      short loc_180001CFC
0x180001ceb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001cef  inc     rax
0x180001cf2  cmp     [rcx+rax], r8b
0x180001cf6  jnz     short loc_180001CEF
0x180001cf8  inc     eax
0x180001cfa  jmp     short loc_180001D08
0x180001cfc  lea     rcx, word_180013A56
0x180001d03  mov     eax, 1
0x180001d08  mov     [rbp+0Fh+var_28], eax
0x180001d0b  xor     r9d, r9d
0x180001d0e  mov     rax, [rbp+0Fh+arg_50]
0x180001d12  mov     [rbp+0Fh+var_40], rax
0x180001d16  mov     rax, [rbp+0Fh+arg_48]
0x180001d1a  mov     [rbp+0Fh+var_50], rax
0x180001d1e  mov     rax, [rbp+0Fh+arg_40]
0x180001d22  mov     [rbp+0Fh+var_60], rax
0x180001d26  mov     rax, [rbp+0Fh+arg_38]
0x180001d2a  mov     [rbp+0Fh+var_70], rax
0x180001d2e  mov     rax, [rbp+0Fh+arg_30]
0x180001d32  mov     [rbp+0Fh+var_80], rax
0x180001d36  mov     rax, [rbp+0Fh+arg_28]
0x180001d3a  mov     [rsp+0F0h+var_90], rax
0x180001d3f  mov     rax, [rbp+0Fh+arg_20]
0x180001d43  mov     [rsp+0F0h+var_A0], rax
0x180001d48  lea     rax, [rsp+0F0h+var_C0]
0x180001d4d  mov     [rbp+0Fh+var_30], rcx
0x180001d51  lea     rcx, dword_18001C038
0x180001d58  mov     [rsp+0F0h+var_C8], rax
0x180001d5d  mov     [rsp+0F0h+var_D0], 0Bh
0x180001d65  mov     [rbp+0Fh+var_24], r8d
0x180001d69  mov     [rbp+0Fh+var_38], 4
0x180001d71  mov     [rbp+0Fh+var_48], 4
0x180001d79  mov     [rbp+0Fh+var_58], 4
0x180001d81  mov     [rbp+0Fh+var_68], 4
0x180001d89  mov     [rbp+0Fh+var_78], 4
0x180001d91  mov     [rbp+0Fh+var_88], 4
0x180001d99  mov     [rsp+0F0h+var_98], 4
0x180001da2  call    _tlgWriteTransfer_EventWriteTransfer
0x180001da7  mov     rcx, [rbp+0Fh+var_10]
0x180001dab  xor     rcx, rsp; StackCookie
0x180001dae  call    __security_check_cookie
0x180001db3  add     rsp, 0F0h
0x180001dba  pop     rbp
0x180001dbb  retn
```
