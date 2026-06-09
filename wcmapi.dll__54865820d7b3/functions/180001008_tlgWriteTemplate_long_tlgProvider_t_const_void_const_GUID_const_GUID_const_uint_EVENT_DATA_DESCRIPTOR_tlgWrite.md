# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)

- ea: `0x180001008`
- end: `0x18000110f`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@3@Z`
- size: `263`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e514`

## callees

- `0x180001008`
- `0x180005a74`
- `0x180008a90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6,
        __int64 *a7,
        const unsigned __int16 **a8)
{
  __int64 v10; // rdx
  int v11; // r8d
  const unsigned __int16 *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  const unsigned __int16 *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  const unsigned __int16 *v18; // rcx
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-39h] BYREF
  const unsigned __int16 *v21; // [rsp+50h] [rbp-19h]
  int v22; // [rsp+58h] [rbp-11h]
  int v23; // [rsp+5Ch] [rbp-Dh]
  const unsigned __int16 *v24; // [rsp+60h] [rbp-9h]
  int v25; // [rsp+68h] [rbp-1h]
  int v26; // [rsp+6Ch] [rbp+3h]
  __int64 v27; // [rsp+70h] [rbp+7h]
  __int64 v28; // [rsp+78h] [rbp+Fh]
  const unsigned __int16 *v29; // [rsp+80h] [rbp+17h]
  int v30; // [rsp+88h] [rbp+1Fh]
  int v31; // [rsp+8Ch] [rbp+23h]

  v10 = -1;
  v11 = 1;
  v12 = *a8;
  if ( *a8 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_BYTE *)v12 + v13) );
    v14 = v13 + 1;
  }
  else
  {
    v12 = &dword_18002202C;
    v14 = 1;
  }
  v30 = v14;
  v29 = v12;
  v31 = 0;
  v28 = 16;
  v27 = *a7;
  v15 = *a6;
  if ( *a6 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_BYTE *)v15 + v16) );
    v17 = v16 + 1;
  }
  else
  {
    v15 = &dword_18002202C;
    v17 = 1;
  }
  v25 = v17;
  v24 = v15;
  v26 = 0;
  v18 = *a5;
  if ( *a5 )
  {
    do
      ++v10;
    while ( *((_BYTE *)v18 + v10) );
    v11 = v10 + 1;
  }
  else
  {
    v18 = &dword_18002202C;
  }
  v21 = v18;
  v22 = v11;
  v23 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 6u, &v20);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-37h]
0x18000100f  sub     rsp, 0A0h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+37h+var_10], rax
0x180001024  mov     rax, [rbp+37h+arg_38]
0x180001028  mov     r11, rdx
0x18000102b  mov     r10, rcx
0x18000102e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001032  xor     r9d, r9d; int
0x180001035  mov     r8d, 1
0x18000103b  mov     rcx, [rax]
0x18000103e  test    rcx, rcx
0x180001041  jz      short loc_180001053
0x180001043  mov     rax, rdx
0x180001046  inc     rax
0x180001049  cmp     [rcx+rax], r9b
0x18000104d  jnz     short loc_180001046
0x18000104f  inc     eax
0x180001051  jmp     short loc_18000105D
0x180001053  lea     rcx, dword_18002202C
0x18000105a  mov     eax, r8d
0x18000105d  mov     [rbp+37h+var_18], eax
0x180001060  mov     rax, [rbp+37h+arg_30]
0x180001064  mov     [rbp+37h+var_20], rcx
0x180001068  mov     [rbp+37h+var_14], r9d
0x18000106c  mov     [rbp+37h+var_28], 10h
0x180001074  mov     rcx, [rax]
0x180001077  mov     rax, [rbp+37h+arg_28]
0x18000107b  mov     [rbp+37h+var_30], rcx
0x18000107f  mov     rcx, [rax]
0x180001082  test    rcx, rcx
0x180001085  jz      short loc_180001097
0x180001087  mov     rax, rdx
0x18000108a  inc     rax
0x18000108d  cmp     [rcx+rax], r9b
0x180001091  jnz     short loc_18000108A
0x180001093  inc     eax
0x180001095  jmp     short loc_1800010A1
0x180001097  lea     rcx, dword_18002202C
0x18000109e  mov     eax, r8d
0x1800010a1  mov     [rbp+37h+var_38], eax
0x1800010a4  mov     rax, [rbp+37h+arg_20]
0x1800010a8  mov     [rbp+37h+var_40], rcx
0x1800010ac  mov     [rbp+37h+var_34], r9d
0x1800010b0  mov     rcx, [rax]
0x1800010b3  test    rcx, rcx
0x1800010b6  jz      short loc_1800010C7
0x1800010b8  inc     rdx
0x1800010bb  cmp     [rcx+rdx], r9b
0x1800010bf  jnz     short loc_1800010B8
0x1800010c1  lea     r8d, [rdx+1]
0x1800010c5  jmp     short loc_1800010CE
0x1800010c7  lea     rcx, dword_18002202C
0x1800010ce  lea     rax, [rbp+37h+var_70]
0x1800010d2  mov     [rbp+37h+var_50], rcx
0x1800010d6  mov     [rbp+37h+var_48], r8d
0x1800010da  mov     rdx, r11; int
0x1800010dd  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x1800010e2  xor     r8d, r8d; int
0x1800010e5  mov     rcx, r10; int
0x1800010e8  mov     [rsp+0A0h+var_80], 6; ULONG
0x1800010f0  mov     [rbp+37h+var_44], r9d
0x1800010f4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010f9  mov     rcx, [rbp+37h+var_10]
0x1800010fd  xor     rcx, rsp; StackCookie
0x180001100  call    __security_check_cookie
0x180001105  add     rsp, 0A0h
0x18000110c  pop     rbp
0x18000110d  retn
```
