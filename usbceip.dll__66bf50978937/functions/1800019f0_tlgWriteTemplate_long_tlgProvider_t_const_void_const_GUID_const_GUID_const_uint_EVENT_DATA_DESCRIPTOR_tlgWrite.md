# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800019f0`
- end: `0x180001ab8`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@D@@3@Z`
- size: `200`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005b1c`

## callees

- `0x180001010`
- `0x1800019f0`
- `0x180002410`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int16 **a8,
        __int64 a9)
{
  __int16 *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  _BYTE v13[32]; // [rsp+30h] [rbp-51h] BYREF
  __int64 v14; // [rsp+50h] [rbp-31h]
  __int64 v15; // [rsp+58h] [rbp-29h]
  __int64 v16; // [rsp+60h] [rbp-21h]
  __int64 v17; // [rsp+68h] [rbp-19h]
  __int64 v18; // [rsp+70h] [rbp-11h]
  __int64 v19; // [rsp+78h] [rbp-9h]
  __int16 *v20; // [rsp+80h] [rbp-1h]
  int v21; // [rsp+88h] [rbp+7h]
  int v22; // [rsp+8Ch] [rbp+Bh]
  __int64 v23; // [rsp+90h] [rbp+Fh]
  __int64 v24; // [rsp+98h] [rbp+17h]

  v23 = a9;
  v24 = 4;
  v9 = *a8;
  if ( *a8 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_BYTE *)v9 + v10) );
    v11 = v10 + 1;
  }
  else
  {
    v9 = &word_180013A56;
    v11 = 1;
  }
  v21 = v11;
  v18 = a7;
  v16 = a6;
  v14 = a5;
  v20 = v9;
  v22 = 0;
  v19 = 4;
  v17 = 4;
  v15 = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C038, a2, 0, 0, 7, v13);
}

```

## disassembly

```asm
0x1800019f0  push    rbp
0x1800019f2  lea     rbp, [rsp-2Fh]
0x1800019f7  sub     rsp, 0B0h
0x1800019fe  mov     rax, cs:__security_cookie
0x180001a05  xor     rax, rsp
0x180001a08  mov     [rbp+2Fh+var_10], rax
0x180001a0c  mov     rax, [rbp+2Fh+arg_40]
0x180001a10  xor     r8d, r8d
0x180001a13  mov     [rbp+2Fh+var_20], rax
0x180001a17  mov     rax, [rbp+2Fh+arg_38]
0x180001a1b  mov     [rbp+2Fh+var_18], 4
0x180001a23  mov     rcx, [rax]
0x180001a26  test    rcx, rcx
0x180001a29  jz      short loc_180001A3C
0x180001a2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001a2f  inc     rax
0x180001a32  cmp     [rcx+rax], r8b
0x180001a36  jnz     short loc_180001A2F
0x180001a38  inc     eax
0x180001a3a  jmp     short loc_180001A48
0x180001a3c  lea     rcx, word_180013A56
0x180001a43  mov     eax, 1
0x180001a48  mov     [rbp+2Fh+var_28], eax
0x180001a4b  xor     r9d, r9d
0x180001a4e  mov     rax, [rbp+2Fh+arg_30]
0x180001a52  mov     [rbp+2Fh+var_40], rax
0x180001a56  mov     rax, [rbp+2Fh+arg_28]
0x180001a5a  mov     [rbp+2Fh+var_50], rax
0x180001a5e  mov     rax, [rbp+2Fh+arg_20]
0x180001a62  mov     [rbp+2Fh+var_60], rax
0x180001a66  lea     rax, [rbp+2Fh+var_80]
0x180001a6a  mov     [rbp+2Fh+var_30], rcx
0x180001a6e  lea     rcx, dword_18001C038
0x180001a75  mov     [rsp+0B0h+var_88], rax
0x180001a7a  mov     [rsp+0B0h+var_90], 7
0x180001a82  mov     [rbp+2Fh+var_24], r8d
0x180001a86  mov     [rbp+2Fh+var_38], 4
0x180001a8e  mov     [rbp+2Fh+var_48], 4
0x180001a96  mov     [rbp+2Fh+var_58], 4
0x180001a9e  call    _tlgWriteTransfer_EventWriteTransfer
0x180001aa3  mov     rcx, [rbp+2Fh+var_10]
0x180001aa7  xor     rcx, rsp; StackCookie
0x180001aaa  call    __security_check_cookie
0x180001aaf  add     rsp, 0B0h
0x180001ab6  pop     rbp
0x180001ab7  retn
```
