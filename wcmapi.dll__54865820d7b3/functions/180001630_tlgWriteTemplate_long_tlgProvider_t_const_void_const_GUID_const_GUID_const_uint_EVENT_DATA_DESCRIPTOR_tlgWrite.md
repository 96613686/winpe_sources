# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001630`
- end: `0x18000174e`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800136c0`

## callees

- `0x180001630`
- `0x180005a74`
- `0x180008a90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 **a9,
        __int64 **a10,
        __int64 a11)
{
  __int64 v12; // rcx
  int v13; // r8d
  __int64 *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  __int64 *v17; // rdx
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+30h] [rbp-81h] BYREF
  __int64 v20; // [rsp+50h] [rbp-61h]
  __int64 v21; // [rsp+58h] [rbp-59h]
  __int64 v22; // [rsp+60h] [rbp-51h]
  __int64 v23; // [rsp+68h] [rbp-49h]
  __int64 v24; // [rsp+70h] [rbp-41h]
  __int64 v25; // [rsp+78h] [rbp-39h]
  __int64 v26; // [rsp+80h] [rbp-31h]
  __int64 v27; // [rsp+88h] [rbp-29h]
  __int64 *v28; // [rsp+90h] [rbp-21h]
  int v29; // [rsp+98h] [rbp-19h]
  int v30; // [rsp+9Ch] [rbp-15h]
  __int64 *v31; // [rsp+A0h] [rbp-11h]
  int v32; // [rsp+A8h] [rbp-9h]
  int v33; // [rsp+ACh] [rbp-5h]
  __int64 v34; // [rsp+B0h] [rbp-1h]
  __int64 v35; // [rsp+B8h] [rbp+7h]

  v34 = a11;
  v12 = -1;
  v35 = 8;
  v13 = 2;
  v14 = *a10;
  if ( *a10 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v14 + v15) );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v14 = &qword_180022030;
    v16 = 2;
  }
  v32 = v16;
  v31 = v14;
  v33 = 0;
  v17 = *a9;
  if ( *a9 )
  {
    do
      ++v12;
    while ( *((_WORD *)v17 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v17 = &qword_180022030;
  }
  v26 = a8;
  v24 = a7;
  v22 = a6;
  v20 = a5;
  v28 = v17;
  v29 = v13;
  v30 = 0;
  v27 = 4;
  v25 = 4;
  v23 = 4;
  v21 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18002A000, a2, 0, 0, 9u, &v19);
}

```

## disassembly

```asm
0x180001630  push    rbp
0x180001632  lea     rbp, [rsp-1Fh]
0x180001637  sub     rsp, 0D0h
0x18000163e  mov     rax, cs:__security_cookie
0x180001645  xor     rax, rsp
0x180001648  mov     [rbp+1Fh+var_10], rax
0x18000164c  mov     rax, [rbp+1Fh+arg_50]
0x180001650  xor     r9d, r9d; int
0x180001653  mov     [rbp+1Fh+var_20], rax
0x180001657  mov     r10, rdx
0x18000165a  mov     rax, [rbp+1Fh+arg_48]
0x18000165e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001662  mov     [rbp+1Fh+var_18], 8
0x18000166a  lea     r8d, [r9+2]
0x18000166e  mov     rdx, [rax]
0x180001671  test    rdx, rdx
0x180001674  jz      short loc_18000168C
0x180001676  mov     rax, rcx
0x180001679  inc     rax
0x18000167c  cmp     [rdx+rax*2], r9w
0x180001681  jnz     short loc_180001679
0x180001683  lea     eax, ds:2[rax*2]
0x18000168a  jmp     short loc_180001696
0x18000168c  lea     rdx, qword_180022030
0x180001693  mov     eax, r8d
0x180001696  mov     [rbp+1Fh+var_28], eax
0x180001699  mov     rax, [rbp+1Fh+arg_40]
0x18000169d  mov     [rbp+1Fh+var_30], rdx
0x1800016a1  mov     [rbp+1Fh+var_24], r9d
0x1800016a5  mov     rdx, [rax]
0x1800016a8  test    rdx, rdx
0x1800016ab  jz      short loc_1800016C1
0x1800016ad  inc     rcx
0x1800016b0  cmp     [rdx+rcx*2], r9w
0x1800016b5  jnz     short loc_1800016AD
0x1800016b7  lea     r8d, ds:2[rcx*2]
0x1800016bf  jmp     short loc_1800016C8
0x1800016c1  lea     rdx, qword_180022030
0x1800016c8  mov     rax, [rbp+1Fh+arg_38]
0x1800016cc  lea     rcx, dword_18002A000; int
0x1800016d3  mov     [rbp+1Fh+var_50], rax
0x1800016d7  mov     rax, [rbp+1Fh+arg_30]
0x1800016db  mov     [rbp+1Fh+var_60], rax
0x1800016df  mov     rax, [rbp+1Fh+arg_28]
0x1800016e3  mov     [rbp+1Fh+var_70], rax
0x1800016e7  mov     rax, [rbp+1Fh+arg_20]
0x1800016eb  mov     [rbp+1Fh+var_80], rax
0x1800016ef  lea     rax, [rsp+0D0h+var_A0]
0x1800016f4  mov     [rbp+1Fh+var_40], rdx
0x1800016f8  mov     rdx, r10; int
0x1800016fb  mov     [rbp+1Fh+var_38], r8d
0x1800016ff  xor     r8d, r8d; int
0x180001702  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x180001707  mov     [rsp+0D0h+var_B0], 9; ULONG
0x18000170f  mov     [rbp+1Fh+var_34], r9d
0x180001713  mov     [rbp+1Fh+var_48], 4
0x18000171b  mov     [rbp+1Fh+var_58], 4
0x180001723  mov     [rbp+1Fh+var_68], 4
0x18000172b  mov     [rbp+1Fh+var_78], 4
0x180001733  call    _tlgWriteTransfer_EventWriteTransfer
0x180001738  mov     rcx, [rbp+1Fh+var_10]
0x18000173c  xor     rcx, rsp; StackCookie
0x18000173f  call    __security_check_cookie
0x180001744  add     rsp, 0D0h
0x18000174b  pop     rbp
0x18000174c  retn
```
