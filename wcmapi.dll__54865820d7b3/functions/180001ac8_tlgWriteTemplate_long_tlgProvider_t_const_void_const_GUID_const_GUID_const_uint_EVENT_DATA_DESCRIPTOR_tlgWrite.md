# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001ac8`
- end: `0x180001bbc`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z`
- size: `244`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180011b10`
- `0x1800130e0`
- `0x180013db0`

## callees

- `0x180001ac8`
- `0x180005a74`
- `0x180008a90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 **a6,
        __int64 **a7)
{
  __int64 v8; // rcx
  int v9; // r8d
  __int64 *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  __int64 *v13; // rdx
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-68h] BYREF
  __int64 v16; // [rsp+50h] [rbp-48h]
  __int64 v17; // [rsp+58h] [rbp-40h]
  __int64 *v18; // [rsp+60h] [rbp-38h]
  int v19; // [rsp+68h] [rbp-30h]
  int v20; // [rsp+6Ch] [rbp-2Ch]
  __int64 *v21; // [rsp+70h] [rbp-28h]
  int v22; // [rsp+78h] [rbp-20h]
  int v23; // [rsp+7Ch] [rbp-1Ch]

  v8 = -1;
  v9 = 2;
  v10 = *a7;
  if ( *a7 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &qword_180022030;
    v12 = 2;
  }
  v22 = v12;
  v21 = v10;
  v23 = 0;
  v13 = *a6;
  if ( *a6 )
  {
    do
      ++v8;
    while ( *((_WORD *)v13 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v13 = &qword_180022030;
  }
  v16 = a5;
  v18 = v13;
  v19 = v9;
  v20 = 0;
  v17 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18002A000, a2, 0, 0, 5u, &v15);
}

```

## disassembly

```asm
0x180001ac8  sub     rsp, 98h
0x180001acf  mov     rax, cs:__security_cookie
0x180001ad6  xor     rax, rsp
0x180001ad9  mov     [rsp+98h+var_18], rax
0x180001ae1  mov     rax, [rsp+98h+arg_30]
0x180001ae9  mov     r10, rdx
0x180001aec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001af0  xor     r9d, r9d; int
0x180001af3  mov     r8d, 2
0x180001af9  mov     rdx, [rax]
0x180001afc  test    rdx, rdx
0x180001aff  jz      short loc_180001B17
0x180001b01  mov     rax, rcx
0x180001b04  inc     rax
0x180001b07  cmp     [rdx+rax*2], r9w
0x180001b0c  jnz     short loc_180001B04
0x180001b0e  lea     eax, ds:2[rax*2]
0x180001b15  jmp     short loc_180001B21
0x180001b17  lea     rdx, qword_180022030
0x180001b1e  mov     eax, r8d
0x180001b21  mov     [rsp+98h+var_20], eax
0x180001b25  mov     rax, [rsp+98h+arg_28]
0x180001b2d  mov     [rsp+98h+var_28], rdx
0x180001b32  mov     [rsp+98h+var_1C], r9d
0x180001b37  mov     rdx, [rax]
0x180001b3a  test    rdx, rdx
0x180001b3d  jz      short loc_180001B53
0x180001b3f  inc     rcx
0x180001b42  cmp     [rdx+rcx*2], r9w
0x180001b47  jnz     short loc_180001B3F
0x180001b49  lea     r8d, ds:2[rcx*2]
0x180001b51  jmp     short loc_180001B5A
0x180001b53  lea     rdx, qword_180022030
0x180001b5a  mov     rax, [rsp+98h+arg_20]
0x180001b62  lea     rcx, dword_18002A000; int
0x180001b69  mov     [rsp+98h+var_48], rax
0x180001b6e  lea     rax, [rsp+98h+var_68]
0x180001b73  mov     [rsp+98h+var_38], rdx
0x180001b78  mov     rdx, r10; int
0x180001b7b  mov     [rsp+98h+var_30], r8d
0x180001b80  xor     r8d, r8d; int
0x180001b83  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x180001b88  mov     [rsp+98h+var_78], 5; ULONG
0x180001b90  mov     [rsp+98h+var_2C], r9d
0x180001b95  mov     [rsp+98h+var_40], 4
0x180001b9e  call    _tlgWriteTransfer_EventWriteTransfer
0x180001ba3  mov     rcx, [rsp+98h+var_18]
0x180001bab  xor     rcx, rsp; StackCookie
0x180001bae  call    __security_check_cookie
0x180001bb3  add     rsp, 98h
0x180001bba  retn
```
