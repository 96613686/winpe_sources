# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001c70`
- end: `0x180001d85`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U4@U1@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@636@Z`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b870`

## callees

- `0x180001010`
- `0x180001c70`
- `0x1800050f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7,
        __int64 a8,
        int **a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13)
{
  int *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-B1h] BYREF
  __int64 v19; // [rsp+50h] [rbp-91h]
  __int64 v20; // [rsp+58h] [rbp-89h]
  __int64 v21; // [rsp+60h] [rbp-81h]
  __int64 v22; // [rsp+68h] [rbp-79h]
  __int64 v23; // [rsp+70h] [rbp-71h]
  __int64 v24; // [rsp+78h] [rbp-69h]
  __int64 v25; // [rsp+80h] [rbp-61h]
  __int64 v26; // [rsp+88h] [rbp-59h]
  int *v27; // [rsp+90h] [rbp-51h]
  int v28; // [rsp+98h] [rbp-49h]
  int v29; // [rsp+9Ch] [rbp-45h]
  __int64 v30; // [rsp+A0h] [rbp-41h]
  __int64 v31; // [rsp+A8h] [rbp-39h]
  __int64 v32; // [rsp+B0h] [rbp-31h]
  __int64 v33; // [rsp+B8h] [rbp-29h]
  __int64 v34; // [rsp+C0h] [rbp-21h]
  __int64 v35; // [rsp+C8h] [rbp-19h]
  __int64 v36; // [rsp+D0h] [rbp-11h]
  __int64 v37; // [rsp+D8h] [rbp-9h]

  v36 = a13;
  v34 = a12;
  v32 = a11;
  v30 = a10;
  v37 = 8;
  v35 = 4;
  v33 = 8;
  v13 = *a9;
  v31 = 8;
  if ( v13 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)v13 + v14) );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v13 = &dword_180031EE4;
    v15 = 2;
  }
  v28 = v15;
  v25 = a8;
  v27 = v13;
  v29 = 0;
  v26 = 4;
  v16 = *a7;
  v21 = a6;
  v19 = a5;
  v23 = v16;
  v24 = 16;
  v22 = 4;
  v20 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180040010, a2, 0, 0, 0xBu, &v18);
}

```

## disassembly

```asm
0x180001c70  push    rbp
0x180001c72  lea     rbp, [rsp-0Fh]
0x180001c77  sub     rsp, 0F0h
0x180001c7e  mov     rax, cs:__security_cookie
0x180001c85  xor     rax, rsp
0x180001c88  mov     [rbp+0Fh+var_10], rax
0x180001c8c  mov     rax, [rbp+0Fh+arg_60]
0x180001c90  xor     r8d, r8d
0x180001c93  mov     [rbp+0Fh+var_20], rax
0x180001c97  mov     rax, [rbp+0Fh+arg_58]
0x180001c9b  mov     [rbp+0Fh+var_30], rax
0x180001c9f  mov     rax, [rbp+0Fh+arg_50]
0x180001ca3  mov     [rbp+0Fh+var_40], rax
0x180001ca7  mov     rax, [rbp+0Fh+arg_48]
0x180001cab  mov     [rbp+0Fh+var_50], rax
0x180001caf  mov     rax, [rbp+0Fh+arg_40]
0x180001cb3  mov     [rbp+0Fh+var_18], 8
0x180001cbb  mov     [rbp+0Fh+var_28], 4
0x180001cc3  mov     [rbp+0Fh+var_38], 8
0x180001ccb  mov     rcx, [rax]
0x180001cce  mov     [rbp+0Fh+var_48], 8
0x180001cd6  test    rcx, rcx
0x180001cd9  jz      short loc_180001CF2
0x180001cdb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001cdf  inc     rax
0x180001ce2  cmp     [rcx+rax*2], r8w
0x180001ce7  jnz     short loc_180001CDF
0x180001ce9  lea     eax, ds:2[rax*2]
0x180001cf0  jmp     short loc_180001CFE
0x180001cf2  lea     rcx, dword_180031EE4
0x180001cf9  mov     eax, 2
0x180001cfe  mov     [rbp+0Fh+var_58], eax
0x180001d01  xor     r9d, r9d
0x180001d04  mov     rax, [rbp+0Fh+arg_38]
0x180001d08  mov     [rbp+0Fh+var_70], rax
0x180001d0c  mov     rax, [rbp+0Fh+arg_30]
0x180001d10  mov     [rbp+0Fh+var_60], rcx
0x180001d14  mov     [rbp+0Fh+var_54], r8d
0x180001d18  mov     [rbp+0Fh+var_68], 4
0x180001d20  mov     rcx, [rax]
0x180001d23  mov     rax, [rbp+0Fh+arg_28]
0x180001d27  mov     [rsp+0F0h+var_90], rax
0x180001d2c  mov     rax, [rbp+0Fh+arg_20]
0x180001d30  mov     [rsp+0F0h+var_A0], rax
0x180001d35  lea     rax, [rsp+0F0h+var_C0]
0x180001d3a  mov     [rbp+0Fh+var_80], rcx
0x180001d3e  lea     rcx, dword_180040010
0x180001d45  mov     [rsp+0F0h+var_C8], rax
0x180001d4a  mov     [rsp+0F0h+var_D0], 0Bh
0x180001d52  mov     [rbp+0Fh+var_78], 10h
0x180001d5a  mov     [rbp+0Fh+var_88], 4
0x180001d62  mov     [rsp+0F0h+var_98], 4
0x180001d6b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001d70  mov     rcx, [rbp+0Fh+var_10]
0x180001d74  xor     rcx, rsp; StackCookie
0x180001d77  call    __security_check_cookie
0x180001d7c  add     rsp, 0F0h
0x180001d83  pop     rbp
0x180001d84  retn
```
