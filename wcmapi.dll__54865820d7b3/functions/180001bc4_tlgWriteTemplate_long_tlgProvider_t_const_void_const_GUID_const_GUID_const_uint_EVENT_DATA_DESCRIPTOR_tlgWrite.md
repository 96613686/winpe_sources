# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001bc4`
- end: `0x180001cb1`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011690`

## callees

- `0x180001bc4`
- `0x180005a74`
- `0x180008a90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 **a6,
        __int64 **a7,
        __int64 a8)
{
  __int64 v9; // rcx
  int v10; // r8d
  __int64 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  __int64 *v14; // rdx
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+30h] [rbp-39h] BYREF
  __int64 v17; // [rsp+50h] [rbp-19h]
  __int64 v18; // [rsp+58h] [rbp-11h]
  __int64 *v19; // [rsp+60h] [rbp-9h]
  int v20; // [rsp+68h] [rbp-1h]
  int v21; // [rsp+6Ch] [rbp+3h]
  __int64 *v22; // [rsp+70h] [rbp+7h]
  int v23; // [rsp+78h] [rbp+Fh]
  int v24; // [rsp+7Ch] [rbp+13h]
  __int64 v25; // [rsp+80h] [rbp+17h]
  __int64 v26; // [rsp+88h] [rbp+1Fh]

  v25 = a8;
  v9 = -1;
  v26 = 8;
  v10 = 2;
  v11 = *a7;
  if ( *a7 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v11 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &qword_180022030;
    v13 = 2;
  }
  v23 = v13;
  v22 = v11;
  v24 = 0;
  v14 = *a6;
  if ( *a6 )
  {
    do
      ++v9;
    while ( *((_WORD *)v14 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v14 = &qword_180022030;
  }
  v17 = a5;
  v19 = v14;
  v20 = v10;
  v21 = 0;
  v18 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18002A000, a2, 0, 0, 6u, &v16);
}

```

## disassembly

```asm
0x180001bc4  push    rbp
0x180001bc6  lea     rbp, [rsp-37h]
0x180001bcb  sub     rsp, 0A0h
0x180001bd2  mov     rax, cs:__security_cookie
0x180001bd9  xor     rax, rsp
0x180001bdc  mov     [rbp+37h+var_10], rax
0x180001be0  mov     rax, [rbp+37h+arg_38]
0x180001be4  xor     r9d, r9d; int
0x180001be7  mov     [rbp+37h+var_20], rax
0x180001beb  mov     r10, rdx
0x180001bee  mov     rax, [rbp+37h+arg_30]
0x180001bf2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001bf6  mov     [rbp+37h+var_18], 8
0x180001bfe  lea     r8d, [r9+2]
0x180001c02  mov     rdx, [rax]
0x180001c05  test    rdx, rdx
0x180001c08  jz      short loc_180001C20
0x180001c0a  mov     rax, rcx
0x180001c0d  inc     rax
0x180001c10  cmp     [rdx+rax*2], r9w
0x180001c15  jnz     short loc_180001C0D
0x180001c17  lea     eax, ds:2[rax*2]
0x180001c1e  jmp     short loc_180001C2A
0x180001c20  lea     rdx, qword_180022030
0x180001c27  mov     eax, r8d
0x180001c2a  mov     [rbp+37h+var_28], eax
0x180001c2d  mov     rax, [rbp+37h+arg_28]
0x180001c31  mov     [rbp+37h+var_30], rdx
0x180001c35  mov     [rbp+37h+var_24], r9d
0x180001c39  mov     rdx, [rax]
0x180001c3c  test    rdx, rdx
0x180001c3f  jz      short loc_180001C55
0x180001c41  inc     rcx
0x180001c44  cmp     [rdx+rcx*2], r9w
0x180001c49  jnz     short loc_180001C41
0x180001c4b  lea     r8d, ds:2[rcx*2]
0x180001c53  jmp     short loc_180001C5C
0x180001c55  lea     rdx, qword_180022030
0x180001c5c  mov     rax, [rbp+37h+arg_20]
0x180001c60  lea     rcx, dword_18002A000; int
0x180001c67  mov     [rbp+37h+var_50], rax
0x180001c6b  lea     rax, [rbp+37h+var_70]
0x180001c6f  mov     [rbp+37h+var_40], rdx
0x180001c73  mov     rdx, r10; int
0x180001c76  mov     [rbp+37h+var_38], r8d
0x180001c7a  xor     r8d, r8d; int
0x180001c7d  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x180001c82  mov     [rsp+0A0h+var_80], 6; ULONG
0x180001c8a  mov     [rbp+37h+var_34], r9d
0x180001c8e  mov     [rbp+37h+var_48], 4
0x180001c96  call    _tlgWriteTransfer_EventWriteTransfer
0x180001c9b  mov     rcx, [rbp+37h+var_10]
0x180001c9f  xor     rcx, rsp; StackCookie
0x180001ca2  call    __security_check_cookie
0x180001ca7  add     rsp, 0A0h
0x180001cae  pop     rbp
0x180001caf  retn
```
