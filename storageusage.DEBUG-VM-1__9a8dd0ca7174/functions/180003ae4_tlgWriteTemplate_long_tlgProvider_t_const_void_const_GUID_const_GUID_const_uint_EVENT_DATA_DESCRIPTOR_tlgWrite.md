# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180003ae4`
- end: `0x180003bd7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029198`

## callees

- `0x180001010`
- `0x180003ae4`
- `0x1800050f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        int **a9)
{
  __int64 v11; // rcx
  int *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  int v16; // ecx
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-51h] BYREF
  __int64 v19; // [rsp+50h] [rbp-31h]
  __int64 v20; // [rsp+58h] [rbp-29h]
  __int64 v21; // [rsp+60h] [rbp-21h]
  __int64 v22; // [rsp+68h] [rbp-19h]
  __int64 v23; // [rsp+70h] [rbp-11h]
  __int64 v24; // [rsp+78h] [rbp-9h]
  const unsigned __int16 *v25; // [rsp+80h] [rbp-1h]
  int v26; // [rsp+88h] [rbp+7h]
  int v27; // [rsp+8Ch] [rbp+Bh]
  int *v28; // [rsp+90h] [rbp+Fh]
  int v29; // [rsp+98h] [rbp+17h]
  int v30; // [rsp+9Ch] [rbp+1Bh]

  v11 = -1;
  v12 = *a9;
  if ( *a9 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v12 + v13) );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &dword_180031EE4;
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
    v15 = &byte_180031EE0;
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
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 7u, &v18);
}

```

## disassembly

```asm
0x180003ae4  push    rbp
0x180003ae6  lea     rbp, [rsp-2Fh]
0x180003aeb  sub     rsp, 0B0h
0x180003af2  mov     rax, cs:__security_cookie
0x180003af9  xor     rax, rsp
0x180003afc  mov     [rbp+2Fh+var_10], rax
0x180003b00  mov     rax, [rbp+2Fh+arg_40]
0x180003b04  mov     r11, rdx
0x180003b07  mov     r10, rcx
0x180003b0a  xor     r9d, r9d
0x180003b0d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003b11  mov     rdx, [rax]
0x180003b14  test    rdx, rdx
0x180003b17  jz      short loc_180003B2F
0x180003b19  mov     rax, rcx
0x180003b1c  inc     rax
0x180003b1f  cmp     [rdx+rax*2], r9w
0x180003b24  jnz     short loc_180003B1C
0x180003b26  lea     eax, ds:2[rax*2]
0x180003b2d  jmp     short loc_180003B3B
0x180003b2f  lea     rdx, dword_180031EE4
0x180003b36  mov     eax, 2
0x180003b3b  mov     [rbp+2Fh+var_18], eax
0x180003b3e  mov     rax, [rbp+2Fh+arg_38]
0x180003b42  mov     [rbp+2Fh+var_20], rdx
0x180003b46  mov     [rbp+2Fh+var_14], r9d
0x180003b4a  mov     rdx, [rax]
0x180003b4d  test    rdx, rdx
0x180003b50  jz      short loc_180003B5F
0x180003b52  inc     rcx
0x180003b55  cmp     [rdx+rcx], r9b
0x180003b59  jnz     short loc_180003B52
0x180003b5b  inc     ecx
0x180003b5d  jmp     short loc_180003B6B
0x180003b5f  lea     rdx, byte_180031EE0
0x180003b66  mov     ecx, 1
0x180003b6b  mov     rax, [rbp+2Fh+arg_30]
0x180003b6f  mov     [rbp+2Fh+var_40], rax
0x180003b73  mov     rax, [rbp+2Fh+arg_28]
0x180003b77  mov     [rbp+2Fh+var_50], rax
0x180003b7b  mov     rax, [rbp+2Fh+arg_20]
0x180003b7f  mov     [rbp+2Fh+var_60], rax
0x180003b83  lea     rax, [rbp+2Fh+var_80]
0x180003b87  mov     [rbp+2Fh+var_30], rdx
0x180003b8b  mov     rdx, r11
0x180003b8e  mov     [rbp+2Fh+var_28], ecx
0x180003b91  mov     rcx, r10
0x180003b94  mov     [rsp+0B0h+var_88], rax
0x180003b99  mov     [rsp+0B0h+var_90], 7
0x180003ba1  mov     [rbp+2Fh+var_24], r9d
0x180003ba5  mov     [rbp+2Fh+var_38], 4
0x180003bad  mov     [rbp+2Fh+var_48], 4
0x180003bb5  mov     [rbp+2Fh+var_58], 8
0x180003bbd  call    _tlgWriteTransfer_EventWriteTransfer
0x180003bc2  mov     rcx, [rbp+2Fh+var_10]
0x180003bc6  xor     rcx, rsp; StackCookie
0x180003bc9  call    __security_check_cookie
0x180003bce  add     rsp, 0B0h
0x180003bd5  pop     rbp
0x180003bd6  retn
```
