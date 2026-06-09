# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180002198`
- end: `0x180002310`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@555554@Z`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017dec`

## callees

- `0x180001010`
- `0x180002198`
- `0x1800050f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int **a6,
        int **a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        int **a14)
{
  __int64 v15; // rcx
  int v16; // r8d
  int *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  int *v20; // rdx
  __int64 v21; // rax
  int v22; // eax
  int *v23; // rdx
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+30h] [rbp-C9h] BYREF
  __int64 v26; // [rsp+50h] [rbp-A9h]
  __int64 v27; // [rsp+58h] [rbp-A1h]
  int *v28; // [rsp+60h] [rbp-99h]
  int v29; // [rsp+68h] [rbp-91h]
  int v30; // [rsp+6Ch] [rbp-8Dh]
  int *v31; // [rsp+70h] [rbp-89h]
  int v32; // [rsp+78h] [rbp-81h]
  int v33; // [rsp+7Ch] [rbp-7Dh]
  __int64 v34; // [rsp+80h] [rbp-79h]
  __int64 v35; // [rsp+88h] [rbp-71h]
  __int64 v36; // [rsp+90h] [rbp-69h]
  __int64 v37; // [rsp+98h] [rbp-61h]
  __int64 v38; // [rsp+A0h] [rbp-59h]
  __int64 v39; // [rsp+A8h] [rbp-51h]
  __int64 v40; // [rsp+B0h] [rbp-49h]
  __int64 v41; // [rsp+B8h] [rbp-41h]
  __int64 v42; // [rsp+C0h] [rbp-39h]
  __int64 v43; // [rsp+C8h] [rbp-31h]
  __int64 v44; // [rsp+D0h] [rbp-29h]
  __int64 v45; // [rsp+D8h] [rbp-21h]
  int *v46; // [rsp+E0h] [rbp-19h]
  int v47; // [rsp+E8h] [rbp-11h]
  int v48; // [rsp+ECh] [rbp-Dh]

  v15 = -1;
  v16 = 2;
  v17 = *a14;
  if ( *a14 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_WORD *)v17 + v18) );
    v19 = 2 * v18 + 2;
  }
  else
  {
    v17 = &dword_180031EE4;
    v19 = 2;
  }
  v47 = v19;
  v44 = a13;
  v42 = a12;
  v40 = a11;
  v38 = a10;
  v36 = a9;
  v34 = a8;
  v46 = v17;
  v48 = 0;
  v45 = 4;
  v20 = *a7;
  v43 = 4;
  v41 = 4;
  v39 = 4;
  v37 = 4;
  v35 = 4;
  if ( v20 )
  {
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)v20 + v21) );
    v22 = 2 * v21 + 2;
  }
  else
  {
    v20 = &dword_180031EE4;
    v22 = 2;
  }
  v32 = v22;
  v31 = v20;
  v33 = 0;
  v23 = *a6;
  if ( *a6 )
  {
    do
      ++v15;
    while ( *((_WORD *)v23 + v15) );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v23 = &dword_180031EE4;
  }
  v26 = a5;
  v28 = v23;
  v29 = v16;
  v30 = 0;
  v27 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180040010, a2, 0, 0, 0xCu, &v25);
}

```

## disassembly

```asm
0x180002198  push    rbp
0x18000219a  lea     rbp, [rsp-7]
0x18000219f  sub     rsp, 100h
0x1800021a6  mov     rax, cs:__security_cookie
0x1800021ad  xor     rax, rsp
0x1800021b0  mov     [rbp+7+var_10], rax
0x1800021b4  mov     rax, [rbp+7+arg_68]
0x1800021b8  lea     r11, dword_180031EE4
0x1800021bf  mov     r10, rdx
0x1800021c2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800021c6  xor     r9d, r9d
0x1800021c9  mov     r8d, 2
0x1800021cf  mov     rdx, [rax]
0x1800021d2  test    rdx, rdx
0x1800021d5  jz      short loc_1800021ED
0x1800021d7  mov     rax, rcx
0x1800021da  inc     rax
0x1800021dd  cmp     [rdx+rax*2], r9w
0x1800021e2  jnz     short loc_1800021DA
0x1800021e4  lea     eax, ds:2[rax*2]
0x1800021eb  jmp     short loc_1800021F3
0x1800021ed  mov     rdx, r11
0x1800021f0  mov     eax, r8d
0x1800021f3  mov     [rbp+7+var_18], eax
0x1800021f6  mov     rax, [rbp+7+arg_60]
0x1800021fa  mov     [rbp+7+var_30], rax
0x1800021fe  mov     rax, [rbp+7+arg_58]
0x180002202  mov     [rbp+7+var_40], rax
0x180002206  mov     rax, [rbp+7+arg_50]
0x18000220a  mov     [rbp+7+var_50], rax
0x18000220e  mov     rax, [rbp+7+arg_48]
0x180002212  mov     [rbp+7+var_60], rax
0x180002216  mov     rax, [rbp+7+arg_40]
0x18000221a  mov     [rbp+7+var_70], rax
0x18000221e  mov     rax, [rbp+7+arg_38]
0x180002222  mov     [rbp+7+var_80], rax
0x180002226  mov     rax, [rbp+7+arg_30]
0x18000222a  mov     [rbp+7+var_20], rdx
0x18000222e  mov     [rbp+7+var_14], r9d
0x180002232  mov     [rbp+7+var_28], 4
0x18000223a  mov     rdx, [rax]
0x18000223d  mov     [rbp+7+var_38], 4
0x180002245  mov     [rbp+7+var_48], 4
0x18000224d  mov     [rbp+7+var_58], 4
0x180002255  mov     [rbp+7+var_68], 4
0x18000225d  mov     [rbp+7+var_78], 4
0x180002265  test    rdx, rdx
0x180002268  jz      short loc_180002280
0x18000226a  mov     rax, rcx
0x18000226d  inc     rax
0x180002270  cmp     [rdx+rax*2], r9w
0x180002275  jnz     short loc_18000226D
0x180002277  lea     eax, ds:2[rax*2]
0x18000227e  jmp     short loc_180002286
0x180002280  mov     rdx, r11
0x180002283  mov     eax, r8d
0x180002286  mov     [rsp+100h+var_88], eax
0x18000228a  mov     rax, [rbp+7+arg_28]
0x18000228e  mov     [rsp+100h+var_90], rdx
0x180002293  mov     [rbp+7+var_84], r9d
0x180002297  mov     rdx, [rax]
0x18000229a  test    rdx, rdx
0x18000229d  jz      short loc_1800022B3
0x18000229f  inc     rcx
0x1800022a2  cmp     [rdx+rcx*2], r9w
0x1800022a7  jnz     short loc_18000229F
0x1800022a9  lea     r8d, ds:2[rcx*2]
0x1800022b1  jmp     short loc_1800022B6
0x1800022b3  mov     rdx, r11
0x1800022b6  mov     rax, [rbp+7+arg_20]
0x1800022ba  lea     rcx, dword_180040010
0x1800022c1  mov     [rsp+100h+var_B0], rax
0x1800022c6  lea     rax, [rsp+100h+var_D0]
0x1800022cb  mov     [rsp+100h+var_A0], rdx
0x1800022d0  mov     rdx, r10
0x1800022d3  mov     [rsp+100h+var_98], r8d
0x1800022d8  xor     r8d, r8d
0x1800022db  mov     [rsp+100h+var_D8], rax
0x1800022e0  mov     [rsp+100h+var_E0], 0Ch
0x1800022e8  mov     [rsp+100h+var_94], r9d
0x1800022ed  mov     [rsp+100h+var_A8], 8
0x1800022f6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800022fb  mov     rcx, [rbp+7+var_10]
0x1800022ff  xor     rcx, rsp; StackCookie
0x180002302  call    __security_check_cookie
0x180002307  add     rsp, 100h
0x18000230e  pop     rbp
0x18000230f  retn
```
