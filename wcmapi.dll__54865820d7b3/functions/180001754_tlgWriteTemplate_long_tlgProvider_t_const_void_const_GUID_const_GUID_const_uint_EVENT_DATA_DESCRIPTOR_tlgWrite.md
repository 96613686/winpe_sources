# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001754`
- end: `0x180001851`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012400`

## callees

- `0x180001754`
- `0x180005a74`
- `0x180008a90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 **a7,
        __int64 **a8,
        __int64 a9)
{
  __int64 v10; // rcx
  int v11; // r8d
  __int64 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  __int64 *v15; // rdx
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+30h] [rbp-51h] BYREF
  __int64 v18; // [rsp+50h] [rbp-31h]
  __int64 v19; // [rsp+58h] [rbp-29h]
  __int64 v20; // [rsp+60h] [rbp-21h]
  __int64 v21; // [rsp+68h] [rbp-19h]
  __int64 *v22; // [rsp+70h] [rbp-11h]
  int v23; // [rsp+78h] [rbp-9h]
  int v24; // [rsp+7Ch] [rbp-5h]
  __int64 *v25; // [rsp+80h] [rbp-1h]
  int v26; // [rsp+88h] [rbp+7h]
  int v27; // [rsp+8Ch] [rbp+Bh]
  __int64 v28; // [rsp+90h] [rbp+Fh]
  __int64 v29; // [rsp+98h] [rbp+17h]

  v28 = a9;
  v10 = -1;
  v29 = 8;
  v11 = 2;
  v12 = *a8;
  if ( *a8 )
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
  v26 = v14;
  v25 = v12;
  v27 = 0;
  v15 = *a7;
  if ( *a7 )
  {
    do
      ++v10;
    while ( *((_WORD *)v15 + v10) );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v15 = &qword_180022030;
  }
  v20 = a6;
  v18 = a5;
  v22 = v15;
  v23 = v11;
  v24 = 0;
  v21 = 4;
  v19 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18002A000, a2, 0, 0, 7u, &v17);
}

```

## disassembly

```asm
0x180001754  push    rbp
0x180001756  lea     rbp, [rsp-2Fh]
0x18000175b  sub     rsp, 0B0h
0x180001762  mov     rax, cs:__security_cookie
0x180001769  xor     rax, rsp
0x18000176c  mov     [rbp+2Fh+var_10], rax
0x180001770  mov     rax, [rbp+2Fh+arg_40]
0x180001774  xor     r9d, r9d; int
0x180001777  mov     [rbp+2Fh+var_20], rax
0x18000177b  mov     r10, rdx
0x18000177e  mov     rax, [rbp+2Fh+arg_38]
0x180001782  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001786  mov     [rbp+2Fh+var_18], 8
0x18000178e  lea     r8d, [r9+2]
0x180001792  mov     rdx, [rax]
0x180001795  test    rdx, rdx
0x180001798  jz      short loc_1800017B0
0x18000179a  mov     rax, rcx
0x18000179d  inc     rax
0x1800017a0  cmp     [rdx+rax*2], r9w
0x1800017a5  jnz     short loc_18000179D
0x1800017a7  lea     eax, ds:2[rax*2]
0x1800017ae  jmp     short loc_1800017BA
0x1800017b0  lea     rdx, qword_180022030
0x1800017b7  mov     eax, r8d
0x1800017ba  mov     [rbp+2Fh+var_28], eax
0x1800017bd  mov     rax, [rbp+2Fh+arg_30]
0x1800017c1  mov     [rbp+2Fh+var_30], rdx
0x1800017c5  mov     [rbp+2Fh+var_24], r9d
0x1800017c9  mov     rdx, [rax]
0x1800017cc  test    rdx, rdx
0x1800017cf  jz      short loc_1800017E5
0x1800017d1  inc     rcx
0x1800017d4  cmp     [rdx+rcx*2], r9w
0x1800017d9  jnz     short loc_1800017D1
0x1800017db  lea     r8d, ds:2[rcx*2]
0x1800017e3  jmp     short loc_1800017EC
0x1800017e5  lea     rdx, qword_180022030
0x1800017ec  mov     rax, [rbp+2Fh+arg_28]
0x1800017f0  lea     rcx, dword_18002A000; int
0x1800017f7  mov     [rbp+2Fh+var_50], rax
0x1800017fb  mov     rax, [rbp+2Fh+arg_20]
0x1800017ff  mov     [rbp+2Fh+var_60], rax
0x180001803  lea     rax, [rbp+2Fh+var_80]
0x180001807  mov     [rbp+2Fh+var_40], rdx
0x18000180b  mov     rdx, r10; int
0x18000180e  mov     [rbp+2Fh+var_38], r8d
0x180001812  xor     r8d, r8d; int
0x180001815  mov     [rsp+0B0h+var_88], rax; PEVENT_DATA_DESCRIPTOR
0x18000181a  mov     [rsp+0B0h+var_90], 7; ULONG
0x180001822  mov     [rbp+2Fh+var_34], r9d
0x180001826  mov     [rbp+2Fh+var_48], 4
0x18000182e  mov     [rbp+2Fh+var_58], 4
0x180001836  call    _tlgWriteTransfer_EventWriteTransfer
0x18000183b  mov     rcx, [rbp+2Fh+var_10]
0x18000183f  xor     rcx, rsp; StackCookie
0x180001842  call    __security_check_cookie
0x180001847  add     rsp, 0B0h
0x18000184e  pop     rbp
0x18000184f  retn
```
