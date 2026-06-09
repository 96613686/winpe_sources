# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001ab0`
- end: `0x180001b9e`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `238`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014704`

## callees

- `0x18000169c`
- `0x180001ab0`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        __int64 a7,
        const unsigned __int16 **a8)
{
  __int64 v9; // rcx
  int v10; // r8d
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  _BYTE v16[32]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v17; // [rsp+50h] [rbp-19h]
  __int64 v18; // [rsp+58h] [rbp-11h]
  const unsigned __int16 *v19; // [rsp+60h] [rbp-9h]
  int v20; // [rsp+68h] [rbp-1h]
  int v21; // [rsp+6Ch] [rbp+3h]
  __int64 v22; // [rsp+70h] [rbp+7h]
  __int64 v23; // [rsp+78h] [rbp+Fh]
  const unsigned __int16 *v24; // [rsp+80h] [rbp+17h]
  int v25; // [rsp+88h] [rbp+1Fh]
  int v26; // [rsp+8Ch] [rbp+23h]

  v9 = -1;
  v10 = 2;
  v11 = *a8;
  if ( *a8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &qword_180021DC8;
    v13 = 2;
  }
  v25 = v13;
  v22 = a7;
  v24 = v11;
  v26 = 0;
  v23 = 4;
  v14 = *a6;
  if ( *a6 )
  {
    do
      ++v9;
    while ( v14[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v14 = &qword_180021DC8;
  }
  v17 = a5;
  v19 = v14;
  v20 = v10;
  v21 = 0;
  v18 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 6, v16);
}

```

## disassembly

```asm
0x180001ab0  push    rbp
0x180001ab2  lea     rbp, [rsp-37h]
0x180001ab7  sub     rsp, 0A0h
0x180001abe  mov     rax, cs:__security_cookie
0x180001ac5  xor     rax, rsp
0x180001ac8  mov     [rbp+37h+var_10], rax
0x180001acc  mov     rax, [rbp+37h+arg_38]
0x180001ad0  mov     r10, rdx
0x180001ad3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001ad7  xor     r9d, r9d
0x180001ada  mov     r8d, 2
0x180001ae0  mov     rdx, [rax]
0x180001ae3  test    rdx, rdx
0x180001ae6  jz      short loc_180001AFE
0x180001ae8  mov     rax, rcx
0x180001aeb  inc     rax
0x180001aee  cmp     [rdx+rax*2], r9w
0x180001af3  jnz     short loc_180001AEB
0x180001af5  lea     eax, ds:2[rax*2]
0x180001afc  jmp     short loc_180001B08
0x180001afe  lea     rdx, qword_180021DC8
0x180001b05  mov     eax, r8d
0x180001b08  mov     [rbp+37h+var_18], eax
0x180001b0b  mov     rax, [rbp+37h+arg_30]
0x180001b0f  mov     [rbp+37h+var_30], rax
0x180001b13  mov     rax, [rbp+37h+arg_28]
0x180001b17  mov     [rbp+37h+var_20], rdx
0x180001b1b  mov     [rbp+37h+var_14], r9d
0x180001b1f  mov     [rbp+37h+var_28], 4
0x180001b27  mov     rdx, [rax]
0x180001b2a  test    rdx, rdx
0x180001b2d  jz      short loc_180001B43
0x180001b2f  inc     rcx
0x180001b32  cmp     [rdx+rcx*2], r9w
0x180001b37  jnz     short loc_180001B2F
0x180001b39  lea     r8d, ds:2[rcx*2]
0x180001b41  jmp     short loc_180001B4A
0x180001b43  lea     rdx, qword_180021DC8
0x180001b4a  mov     rax, [rbp+37h+arg_20]
0x180001b4e  lea     rcx, dword_180030000
0x180001b55  mov     [rbp+37h+var_50], rax
0x180001b59  lea     rax, [rbp+37h+var_70]
0x180001b5d  mov     [rbp+37h+var_40], rdx
0x180001b61  mov     rdx, r10
0x180001b64  mov     [rbp+37h+var_38], r8d
0x180001b68  xor     r8d, r8d
0x180001b6b  mov     [rsp+0A0h+var_78], rax
0x180001b70  mov     [rsp+0A0h+var_80], 6
0x180001b78  mov     [rbp+37h+var_34], r9d
0x180001b7c  mov     [rbp+37h+var_48], 8
0x180001b84  call    _tlgWriteTransfer_EventWriteTransfer
0x180001b89  mov     rcx, [rbp+37h+var_10]
0x180001b8d  xor     rcx, rsp; StackCookie
0x180001b90  call    __security_check_cookie
0x180001b95  add     rsp, 0A0h
0x180001b9c  pop     rbp
0x180001b9d  retn
```
