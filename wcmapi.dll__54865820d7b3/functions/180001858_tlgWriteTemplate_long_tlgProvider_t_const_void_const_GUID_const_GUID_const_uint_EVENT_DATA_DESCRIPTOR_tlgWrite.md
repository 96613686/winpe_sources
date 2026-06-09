# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001858`
- end: `0x180001998`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@U1@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3344AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012670`

## callees

- `0x180001858`
- `0x180005a74`
- `0x180008a90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 **a6,
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
  __int64 v18; // rax
  int v19; // eax
  __int64 *v20; // rdx
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+30h] [rbp-81h] BYREF
  __int64 v23; // [rsp+50h] [rbp-61h]
  __int64 v24; // [rsp+58h] [rbp-59h]
  __int64 *v25; // [rsp+60h] [rbp-51h]
  int v26; // [rsp+68h] [rbp-49h]
  int v27; // [rsp+6Ch] [rbp-45h]
  __int64 v28; // [rsp+70h] [rbp-41h]
  __int64 v29; // [rsp+78h] [rbp-39h]
  __int64 v30; // [rsp+80h] [rbp-31h]
  __int64 v31; // [rsp+88h] [rbp-29h]
  __int64 *v32; // [rsp+90h] [rbp-21h]
  int v33; // [rsp+98h] [rbp-19h]
  int v34; // [rsp+9Ch] [rbp-15h]
  __int64 *v35; // [rsp+A0h] [rbp-11h]
  int v36; // [rsp+A8h] [rbp-9h]
  int v37; // [rsp+ACh] [rbp-5h]
  __int64 v38; // [rsp+B0h] [rbp-1h]
  __int64 v39; // [rsp+B8h] [rbp+7h]

  v38 = a11;
  v12 = -1;
  v39 = 8;
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
  v36 = v16;
  v35 = v14;
  v37 = 0;
  v17 = *a9;
  if ( *a9 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_WORD *)v17 + v18) );
    v19 = 2 * v18 + 2;
  }
  else
  {
    v17 = &qword_180022030;
    v19 = 2;
  }
  v33 = v19;
  v30 = a8;
  v28 = a7;
  v32 = v17;
  v34 = 0;
  v31 = 4;
  v20 = *a6;
  v29 = 4;
  if ( v20 )
  {
    do
      ++v12;
    while ( *((_WORD *)v20 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v20 = &qword_180022030;
  }
  v23 = a5;
  v25 = v20;
  v26 = v13;
  v27 = 0;
  v24 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18002A000, a2, 0, 0, 9u, &v22);
}

```

## disassembly

```asm
0x180001858  push    rbp
0x18000185a  lea     rbp, [rsp-1Fh]
0x18000185f  sub     rsp, 0D0h
0x180001866  mov     rax, cs:__security_cookie
0x18000186d  xor     rax, rsp
0x180001870  mov     [rbp+1Fh+var_10], rax
0x180001874  mov     rax, [rbp+1Fh+arg_50]
0x180001878  lea     r11, qword_180022030
0x18000187f  xor     r9d, r9d; int
0x180001882  mov     [rbp+1Fh+var_20], rax
0x180001886  mov     rax, [rbp+1Fh+arg_48]
0x18000188a  mov     r10, rdx
0x18000188d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001891  mov     [rbp+1Fh+var_18], 8
0x180001899  lea     r8d, [r9+2]
0x18000189d  mov     rdx, [rax]
0x1800018a0  test    rdx, rdx
0x1800018a3  jz      short loc_1800018BB
0x1800018a5  mov     rax, rcx
0x1800018a8  inc     rax
0x1800018ab  cmp     [rdx+rax*2], r9w
0x1800018b0  jnz     short loc_1800018A8
0x1800018b2  lea     eax, ds:2[rax*2]
0x1800018b9  jmp     short loc_1800018C1
0x1800018bb  mov     rdx, r11
0x1800018be  mov     eax, r8d
0x1800018c1  mov     [rbp+1Fh+var_28], eax
0x1800018c4  mov     rax, [rbp+1Fh+arg_40]
0x1800018c8  mov     [rbp+1Fh+var_30], rdx
0x1800018cc  mov     [rbp+1Fh+var_24], r9d
0x1800018d0  mov     rdx, [rax]
0x1800018d3  test    rdx, rdx
0x1800018d6  jz      short loc_1800018EE
0x1800018d8  mov     rax, rcx
0x1800018db  inc     rax
0x1800018de  cmp     [rdx+rax*2], r9w
0x1800018e3  jnz     short loc_1800018DB
0x1800018e5  lea     eax, ds:2[rax*2]
0x1800018ec  jmp     short loc_1800018F4
0x1800018ee  mov     rdx, r11
0x1800018f1  mov     eax, r8d
0x1800018f4  mov     [rbp+1Fh+var_38], eax
0x1800018f7  mov     rax, [rbp+1Fh+arg_38]
0x1800018fb  mov     [rbp+1Fh+var_50], rax
0x1800018ff  mov     rax, [rbp+1Fh+arg_30]
0x180001903  mov     [rbp+1Fh+var_60], rax
0x180001907  mov     rax, [rbp+1Fh+arg_28]
0x18000190b  mov     [rbp+1Fh+var_40], rdx
0x18000190f  mov     [rbp+1Fh+var_34], r9d
0x180001913  mov     [rbp+1Fh+var_48], 4
0x18000191b  mov     rdx, [rax]
0x18000191e  mov     [rbp+1Fh+var_58], 4
0x180001926  test    rdx, rdx
0x180001929  jz      short loc_18000193F
0x18000192b  inc     rcx
0x18000192e  cmp     [rdx+rcx*2], r9w
0x180001933  jnz     short loc_18000192B
0x180001935  lea     r8d, ds:2[rcx*2]
0x18000193d  jmp     short loc_180001942
0x18000193f  mov     rdx, r11
0x180001942  mov     rax, [rbp+1Fh+arg_20]
0x180001946  lea     rcx, dword_18002A000; int
0x18000194d  mov     [rbp+1Fh+var_80], rax
0x180001951  lea     rax, [rsp+0D0h+var_A0]
0x180001956  mov     [rbp+1Fh+var_70], rdx
0x18000195a  mov     rdx, r10; int
0x18000195d  mov     [rbp+1Fh+var_68], r8d
0x180001961  xor     r8d, r8d; int
0x180001964  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x180001969  mov     [rsp+0D0h+var_B0], 9; ULONG
0x180001971  mov     [rbp+1Fh+var_64], r9d
0x180001975  mov     [rbp+1Fh+var_78], 4
0x18000197d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001982  mov     rcx, [rbp+1Fh+var_10]
0x180001986  xor     rcx, rsp; StackCookie
0x180001989  call    __security_check_cookie
0x18000198e  add     rsp, 0D0h
0x180001995  pop     rbp
0x180001996  retn
```
