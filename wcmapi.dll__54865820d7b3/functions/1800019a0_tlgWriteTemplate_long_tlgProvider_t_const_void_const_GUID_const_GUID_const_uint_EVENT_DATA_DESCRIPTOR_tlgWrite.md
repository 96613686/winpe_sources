# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800019a0`
- end: `0x180001ac1`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@344@Z`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012ee0`

## callees

- `0x1800019a0`
- `0x180005a74`
- `0x180008a90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 **a6,
        __int64 a7,
        __int64 **a8,
        __int64 **a9)
{
  __int64 v10; // rcx
  int v11; // r8d
  __int64 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  __int64 *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  __int64 *v18; // rdx
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-51h] BYREF
  __int64 v21; // [rsp+50h] [rbp-31h]
  __int64 v22; // [rsp+58h] [rbp-29h]
  __int64 *v23; // [rsp+60h] [rbp-21h]
  int v24; // [rsp+68h] [rbp-19h]
  int v25; // [rsp+6Ch] [rbp-15h]
  __int64 v26; // [rsp+70h] [rbp-11h]
  __int64 v27; // [rsp+78h] [rbp-9h]
  __int64 *v28; // [rsp+80h] [rbp-1h]
  int v29; // [rsp+88h] [rbp+7h]
  int v30; // [rsp+8Ch] [rbp+Bh]
  __int64 *v31; // [rsp+90h] [rbp+Fh]
  int v32; // [rsp+98h] [rbp+17h]
  int v33; // [rsp+9Ch] [rbp+1Bh]

  v10 = -1;
  v11 = 2;
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
    v12 = &qword_180022030;
    v14 = 2;
  }
  v32 = v14;
  v31 = v12;
  v33 = 0;
  v15 = *a8;
  if ( *a8 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &qword_180022030;
    v17 = 2;
  }
  v29 = v17;
  v26 = a7;
  v28 = v15;
  v30 = 0;
  v27 = 4;
  v18 = *a6;
  if ( *a6 )
  {
    do
      ++v10;
    while ( *((_WORD *)v18 + v10) );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v18 = &qword_180022030;
  }
  v21 = a5;
  v23 = v18;
  v24 = v11;
  v25 = 0;
  v22 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18002A000, a2, 0, 0, 7u, &v20);
}

```

## disassembly

```asm
0x1800019a0  push    rbp
0x1800019a2  lea     rbp, [rsp-2Fh]
0x1800019a7  sub     rsp, 0B0h
0x1800019ae  mov     rax, cs:__security_cookie
0x1800019b5  xor     rax, rsp
0x1800019b8  mov     [rbp+2Fh+var_10], rax
0x1800019bc  mov     rax, [rbp+2Fh+arg_40]
0x1800019c0  lea     r11, qword_180022030
0x1800019c7  mov     r10, rdx
0x1800019ca  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800019ce  xor     r9d, r9d; int
0x1800019d1  mov     r8d, 2
0x1800019d7  mov     rdx, [rax]
0x1800019da  test    rdx, rdx
0x1800019dd  jz      short loc_1800019F5
0x1800019df  mov     rax, rcx
0x1800019e2  inc     rax
0x1800019e5  cmp     [rdx+rax*2], r9w
0x1800019ea  jnz     short loc_1800019E2
0x1800019ec  lea     eax, ds:2[rax*2]
0x1800019f3  jmp     short loc_1800019FB
0x1800019f5  mov     rdx, r11
0x1800019f8  mov     eax, r8d
0x1800019fb  mov     [rbp+2Fh+var_18], eax
0x1800019fe  mov     rax, [rbp+2Fh+arg_38]
0x180001a02  mov     [rbp+2Fh+var_20], rdx
0x180001a06  mov     [rbp+2Fh+var_14], r9d
0x180001a0a  mov     rdx, [rax]
0x180001a0d  test    rdx, rdx
0x180001a10  jz      short loc_180001A28
0x180001a12  mov     rax, rcx
0x180001a15  inc     rax
0x180001a18  cmp     [rdx+rax*2], r9w
0x180001a1d  jnz     short loc_180001A15
0x180001a1f  lea     eax, ds:2[rax*2]
0x180001a26  jmp     short loc_180001A2E
0x180001a28  mov     rdx, r11
0x180001a2b  mov     eax, r8d
0x180001a2e  mov     [rbp+2Fh+var_28], eax
0x180001a31  mov     rax, [rbp+2Fh+arg_30]
0x180001a35  mov     [rbp+2Fh+var_40], rax
0x180001a39  mov     rax, [rbp+2Fh+arg_28]
0x180001a3d  mov     [rbp+2Fh+var_30], rdx
0x180001a41  mov     [rbp+2Fh+var_24], r9d
0x180001a45  mov     [rbp+2Fh+var_38], 4
0x180001a4d  mov     rdx, [rax]
0x180001a50  test    rdx, rdx
0x180001a53  jz      short loc_180001A69
0x180001a55  inc     rcx
0x180001a58  cmp     [rdx+rcx*2], r9w
0x180001a5d  jnz     short loc_180001A55
0x180001a5f  lea     r8d, ds:2[rcx*2]
0x180001a67  jmp     short loc_180001A6C
0x180001a69  mov     rdx, r11
0x180001a6c  mov     rax, [rbp+2Fh+arg_20]
0x180001a70  lea     rcx, dword_18002A000; int
0x180001a77  mov     [rbp+2Fh+var_60], rax
0x180001a7b  lea     rax, [rbp+2Fh+var_80]
0x180001a7f  mov     [rbp+2Fh+var_50], rdx
0x180001a83  mov     rdx, r10; int
0x180001a86  mov     [rbp+2Fh+var_48], r8d
0x180001a8a  xor     r8d, r8d; int
0x180001a8d  mov     [rsp+0B0h+var_88], rax; PEVENT_DATA_DESCRIPTOR
0x180001a92  mov     [rsp+0B0h+var_90], 7; ULONG
0x180001a9a  mov     [rbp+2Fh+var_44], r9d
0x180001a9e  mov     [rbp+2Fh+var_58], 4
0x180001aa6  call    _tlgWriteTransfer_EventWriteTransfer
0x180001aab  mov     rcx, [rbp+2Fh+var_10]
0x180001aaf  xor     rcx, rsp; StackCookie
0x180001ab2  call    __security_check_cookie
0x180001ab7  add     rsp, 0B0h
0x180001abe  pop     rbp
0x180001abf  retn
```
