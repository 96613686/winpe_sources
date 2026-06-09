# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001008`
- end: `0x180001117`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z`
- size: `271`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005a30`
- `0x180005e38`

## callees

- `0x180001008`
- `0x180001244`
- `0x18000aea0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        char **a5,
        __int64 a6,
        char **a7,
        __int64 a8,
        char **a9)
{
  __int64 v10; // rcx
  int v11; // r8d
  char *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  char *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  char *v18; // rdx
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-51h] BYREF
  char *v21; // [rsp+50h] [rbp-31h]
  int v22; // [rsp+58h] [rbp-29h]
  int v23; // [rsp+5Ch] [rbp-25h]
  __int64 v24; // [rsp+60h] [rbp-21h]
  __int64 v25; // [rsp+68h] [rbp-19h]
  char *v26; // [rsp+70h] [rbp-11h]
  int v27; // [rsp+78h] [rbp-9h]
  int v28; // [rsp+7Ch] [rbp-5h]
  __int64 v29; // [rsp+80h] [rbp-1h]
  __int64 v30; // [rsp+88h] [rbp+7h]
  char *v31; // [rsp+90h] [rbp+Fh]
  int v32; // [rsp+98h] [rbp+17h]
  int v33; // [rsp+9Ch] [rbp+1Bh]

  v10 = -1;
  v11 = 1;
  v12 = *a9;
  if ( *a9 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    v14 = v13 + 1;
  }
  else
  {
    v12 = byte_18001023D;
    v14 = 1;
  }
  v32 = v14;
  v29 = a8;
  v31 = v12;
  v33 = 0;
  v30 = 4;
  v15 = *a7;
  if ( *a7 )
  {
    v16 = -1;
    do
      ++v16;
    while ( v15[v16] );
    v17 = v16 + 1;
  }
  else
  {
    v15 = byte_18001023D;
    v17 = 1;
  }
  v27 = v17;
  v24 = a6;
  v26 = v15;
  v28 = 0;
  v25 = 4;
  v18 = *a5;
  if ( *a5 )
  {
    do
      ++v10;
    while ( v18[v10] );
    v11 = v10 + 1;
  }
  else
  {
    v18 = byte_18001023D;
  }
  v21 = v18;
  v22 = v11;
  v23 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180013020, a2, 0, 0, 7u, &v20);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-2Fh]
0x18000100f  sub     rsp, 0B0h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+2Fh+var_10], rax
0x180001024  mov     rax, [rbp+2Fh+arg_40]
0x180001028  lea     r11, byte_18001023D
0x18000102f  mov     r10, rdx
0x180001032  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001036  xor     r9d, r9d
0x180001039  mov     r8d, 1
0x18000103f  mov     rdx, [rax]
0x180001042  test    rdx, rdx
0x180001045  jz      short loc_180001057
0x180001047  mov     rax, rcx
0x18000104a  inc     rax
0x18000104d  cmp     [rdx+rax], r9b
0x180001051  jnz     short loc_18000104A
0x180001053  inc     eax
0x180001055  jmp     short loc_18000105D
0x180001057  mov     rdx, r11
0x18000105a  mov     eax, r8d
0x18000105d  mov     [rbp+2Fh+var_18], eax
0x180001060  mov     rax, [rbp+2Fh+arg_38]
0x180001064  mov     [rbp+2Fh+var_30], rax
0x180001068  mov     rax, [rbp+2Fh+arg_30]
0x18000106c  mov     [rbp+2Fh+var_20], rdx
0x180001070  mov     [rbp+2Fh+var_14], r9d
0x180001074  mov     [rbp+2Fh+var_28], 4
0x18000107c  mov     rdx, [rax]
0x18000107f  test    rdx, rdx
0x180001082  jz      short loc_180001094
0x180001084  mov     rax, rcx
0x180001087  inc     rax
0x18000108a  cmp     [rdx+rax], r9b
0x18000108e  jnz     short loc_180001087
0x180001090  inc     eax
0x180001092  jmp     short loc_18000109A
0x180001094  mov     rdx, r11
0x180001097  mov     eax, r8d
0x18000109a  mov     [rbp+2Fh+var_38], eax
0x18000109d  mov     rax, [rbp+2Fh+arg_28]
0x1800010a1  mov     [rbp+2Fh+var_50], rax
0x1800010a5  mov     rax, [rbp+2Fh+arg_20]
0x1800010a9  mov     [rbp+2Fh+var_40], rdx
0x1800010ad  mov     [rbp+2Fh+var_34], r9d
0x1800010b1  mov     [rbp+2Fh+var_48], 4
0x1800010b9  mov     rdx, [rax]
0x1800010bc  test    rdx, rdx
0x1800010bf  jz      short loc_1800010D0
0x1800010c1  inc     rcx
0x1800010c4  cmp     [rdx+rcx], r9b
0x1800010c8  jnz     short loc_1800010C1
0x1800010ca  lea     r8d, [rcx+1]
0x1800010ce  jmp     short loc_1800010D3
0x1800010d0  mov     rdx, r11
0x1800010d3  lea     rax, [rbp+2Fh+var_80]
0x1800010d7  mov     [rbp+2Fh+var_60], rdx
0x1800010db  mov     [rbp+2Fh+var_58], r8d
0x1800010df  lea     rcx, dword_180013020
0x1800010e6  mov     [rsp+0B0h+var_88], rax
0x1800010eb  xor     r8d, r8d
0x1800010ee  mov     rdx, r10
0x1800010f1  mov     [rsp+0B0h+var_90], 7
0x1800010f9  mov     [rbp+2Fh+var_54], r9d
0x1800010fd  call    _tlgWriteTransfer_EventWriteTransfer
0x180001102  mov     rcx, [rbp+2Fh+var_10]
0x180001106  xor     rcx, rsp; StackCookie
0x180001109  call    __security_check_cookie
0x18000110e  add     rsp, 0B0h
0x180001115  pop     rbp
0x180001116  retn
```
