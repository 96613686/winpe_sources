# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800017fc`
- end: `0x1800018ef`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, char **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d154`

## callees

- `0x1800017fc`
- `0x180002018`
- `0x1800027f0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        char **a9)
{
  __int64 v11; // rcx
  char *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  int v16; // ecx
  _BYTE v18[32]; // [rsp+30h] [rbp-51h] BYREF
  __int64 v19; // [rsp+50h] [rbp-31h]
  __int64 v20; // [rsp+58h] [rbp-29h]
  __int64 v21; // [rsp+60h] [rbp-21h]
  __int64 v22; // [rsp+68h] [rbp-19h]
  __int64 v23; // [rsp+70h] [rbp-11h]
  __int64 v24; // [rsp+78h] [rbp-9h]
  const unsigned __int16 *v25; // [rsp+80h] [rbp-1h]
  int v26; // [rsp+88h] [rbp+7h]
  int v27; // [rsp+8Ch] [rbp+Bh]
  char *v28; // [rsp+90h] [rbp+Fh]
  int v29; // [rsp+98h] [rbp+17h]
  int v30; // [rsp+9Ch] [rbp+1Bh]

  v11 = -1;
  v12 = *a9;
  if ( *a9 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&v12[2 * v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = byte_180017D50;
    v14 = 2;
  }
  v29 = v14;
  v28 = v12;
  v30 = 0;
  v15 = *a8;
  if ( *a8 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v15 + v11) );
    v16 = v11 + 1;
  }
  else
  {
    v15 = &word_180017D52;
    v16 = 1;
  }
  v23 = a7;
  v21 = a6;
  v19 = a5;
  v25 = v15;
  v26 = v16;
  v27 = 0;
  v24 = 4;
  v22 = 4;
  v20 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 7, v18);
}

```

## disassembly

```asm
0x1800017fc  push    rbp
0x1800017fe  lea     rbp, [rsp-2Fh]
0x180001803  sub     rsp, 0B0h
0x18000180a  mov     rax, cs:__security_cookie
0x180001811  xor     rax, rsp
0x180001814  mov     [rbp+2Fh+var_10], rax
0x180001818  mov     rax, [rbp+2Fh+arg_40]
0x18000181c  mov     r11, rdx
0x18000181f  mov     r10, rcx
0x180001822  xor     r9d, r9d
0x180001825  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001829  mov     rdx, [rax]
0x18000182c  test    rdx, rdx
0x18000182f  jz      short loc_180001847
0x180001831  mov     rax, rcx
0x180001834  inc     rax
0x180001837  cmp     [rdx+rax*2], r9w
0x18000183c  jnz     short loc_180001834
0x18000183e  lea     eax, ds:2[rax*2]
0x180001845  jmp     short loc_180001853
0x180001847  lea     rdx, byte_180017D50
0x18000184e  mov     eax, 2
0x180001853  mov     [rbp+2Fh+var_18], eax
0x180001856  mov     rax, [rbp+2Fh+arg_38]
0x18000185a  mov     [rbp+2Fh+var_20], rdx
0x18000185e  mov     [rbp+2Fh+var_14], r9d
0x180001862  mov     rdx, [rax]
0x180001865  test    rdx, rdx
0x180001868  jz      short loc_180001877
0x18000186a  inc     rcx
0x18000186d  cmp     [rdx+rcx], r9b
0x180001871  jnz     short loc_18000186A
0x180001873  inc     ecx
0x180001875  jmp     short loc_180001883
0x180001877  lea     rdx, word_180017D52
0x18000187e  mov     ecx, 1
0x180001883  mov     rax, [rbp+2Fh+arg_30]
0x180001887  mov     [rbp+2Fh+var_40], rax
0x18000188b  mov     rax, [rbp+2Fh+arg_28]
0x18000188f  mov     [rbp+2Fh+var_50], rax
0x180001893  mov     rax, [rbp+2Fh+arg_20]
0x180001897  mov     [rbp+2Fh+var_60], rax
0x18000189b  lea     rax, [rbp+2Fh+var_80]
0x18000189f  mov     [rbp+2Fh+var_30], rdx
0x1800018a3  mov     rdx, r11
0x1800018a6  mov     [rbp+2Fh+var_28], ecx
0x1800018a9  mov     rcx, r10
0x1800018ac  mov     [rsp+0B0h+var_88], rax
0x1800018b1  mov     [rsp+0B0h+var_90], 7
0x1800018b9  mov     [rbp+2Fh+var_24], r9d
0x1800018bd  mov     [rbp+2Fh+var_38], 4
0x1800018c5  mov     [rbp+2Fh+var_48], 4
0x1800018cd  mov     [rbp+2Fh+var_58], 8
0x1800018d5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800018da  mov     rcx, [rbp+2Fh+var_10]
0x1800018de  xor     rcx, rsp; StackCookie
0x1800018e1  call    __security_check_cookie
0x1800018e6  add     rsp, 0B0h
0x1800018ed  pop     rbp
0x1800018ee  retn
```
