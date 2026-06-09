# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800017ac`
- end: `0x180001988`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$03@@4444444444@Z`
- size: `476`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, char **, char **, char **, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800053e4`

## callees

- `0x180001010`
- `0x1800017ac`
- `0x180002410`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char **a5,
        char **a6,
        char **a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18)
{
  __int64 v19; // rcx
  int v20; // r8d
  char *v21; // rdx
  __int64 v22; // rax
  int v23; // eax
  char *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  char *v27; // rdx
  _BYTE v29[32]; // [rsp+30h] [rbp-D0h] BYREF
  char *v30; // [rsp+50h] [rbp-B0h]
  int v31; // [rsp+58h] [rbp-A8h]
  int v32; // [rsp+5Ch] [rbp-A4h]
  char *v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+6Ch] [rbp-94h]
  char *v36; // [rsp+70h] [rbp-90h]
  int v37; // [rsp+78h] [rbp-88h]
  int v38; // [rsp+7Ch] [rbp-84h]
  __int64 v39; // [rsp+80h] [rbp-80h]
  __int64 v40; // [rsp+88h] [rbp-78h]
  __int64 v41; // [rsp+90h] [rbp-70h]
  __int64 v42; // [rsp+98h] [rbp-68h]
  __int64 v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+A8h] [rbp-58h]
  __int64 v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+B8h] [rbp-48h]
  __int64 v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  __int64 v49; // [rsp+D0h] [rbp-30h]
  __int64 v50; // [rsp+D8h] [rbp-28h]
  __int64 v51; // [rsp+E0h] [rbp-20h]
  __int64 v52; // [rsp+E8h] [rbp-18h]
  __int64 v53; // [rsp+F0h] [rbp-10h]
  __int64 v54; // [rsp+F8h] [rbp-8h]
  __int64 v55; // [rsp+100h] [rbp+0h]
  __int64 v56; // [rsp+108h] [rbp+8h]
  __int64 v57; // [rsp+110h] [rbp+10h]
  __int64 v58; // [rsp+118h] [rbp+18h]
  __int64 v59; // [rsp+120h] [rbp+20h]
  __int64 v60; // [rsp+128h] [rbp+28h]

  v59 = a18;
  v57 = a17;
  v19 = -1;
  v55 = a16;
  v20 = 2;
  v53 = a15;
  v51 = a14;
  v49 = a13;
  v47 = a12;
  v45 = a11;
  v43 = a10;
  v41 = a9;
  v39 = a8;
  v60 = 4;
  v58 = 4;
  v56 = 4;
  v21 = *a7;
  v54 = 4;
  v52 = 4;
  v50 = 4;
  v48 = 4;
  v46 = 4;
  v44 = 4;
  v42 = 4;
  v40 = 4;
  if ( v21 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)&v21[2 * v22] );
    v23 = 2 * v22 + 2;
  }
  else
  {
    v21 = byte_180013A54;
    v23 = 2;
  }
  v37 = v23;
  v36 = v21;
  v38 = 0;
  v24 = *a6;
  if ( *a6 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)&v24[2 * v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = byte_180013A54;
    v26 = 2;
  }
  v34 = v26;
  v33 = v24;
  v35 = 0;
  v27 = *a5;
  if ( *a5 )
  {
    do
      ++v19;
    while ( *(_WORD *)&v27[2 * v19] );
    v20 = 2 * v19 + 2;
  }
  else
  {
    v27 = byte_180013A54;
  }
  v30 = v27;
  v31 = v20;
  v32 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C038, a2, 0, 0, 16, v29);
}

```

## disassembly

```asm
0x1800017ac  push    rbp
0x1800017ae  lea     rbp, [rsp-40h]
0x1800017b3  sub     rsp, 140h
0x1800017ba  mov     rax, cs:__security_cookie
0x1800017c1  xor     rax, rsp
0x1800017c4  mov     [rbp+40h+var_10], rax
0x1800017c8  mov     rax, [rbp+40h+arg_88]
0x1800017cf  lea     r11, byte_180013A54
0x1800017d6  mov     [rbp+40h+var_20], rax
0x1800017da  xor     r9d, r9d
0x1800017dd  mov     rax, [rbp+40h+arg_80]
0x1800017e4  mov     r10, rdx
0x1800017e7  mov     [rbp+40h+var_30], rax
0x1800017eb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800017ef  mov     rax, [rbp+40h+arg_78]
0x1800017f6  mov     [rbp+40h+var_40], rax
0x1800017fa  lea     r8d, [r9+2]
0x1800017fe  mov     rax, [rbp+40h+arg_70]
0x180001805  mov     [rbp+40h+var_50], rax
0x180001809  mov     rax, [rbp+40h+arg_68]
0x180001810  mov     [rbp+40h+var_60], rax
0x180001814  mov     rax, [rbp+40h+arg_60]
0x18000181b  mov     [rbp+40h+var_70], rax
0x18000181f  mov     rax, [rbp+40h+arg_58]
0x180001826  mov     [rbp+40h+var_80], rax
0x18000182a  mov     rax, [rbp+40h+arg_50]
0x180001831  mov     [rbp+40h+var_90], rax
0x180001835  mov     rax, [rbp+40h+arg_48]
0x18000183c  mov     [rbp+40h+var_A0], rax
0x180001840  mov     rax, [rbp+40h+arg_40]
0x180001847  mov     [rbp+40h+var_B0], rax
0x18000184b  mov     rax, [rbp+40h+arg_38]
0x180001852  mov     [rbp+40h+var_C0], rax
0x180001856  mov     rax, [rbp+40h+arg_30]
0x18000185d  mov     [rbp+40h+var_18], 4
0x180001865  mov     [rbp+40h+var_28], 4
0x18000186d  mov     [rbp+40h+var_38], 4
0x180001875  mov     rdx, [rax]
0x180001878  mov     [rbp+40h+var_48], 4
0x180001880  mov     [rbp+40h+var_58], 4
0x180001888  mov     [rbp+40h+var_68], 4
0x180001890  mov     [rbp+40h+var_78], 4
0x180001898  mov     [rbp+40h+var_88], 4
0x1800018a0  mov     [rbp+40h+var_98], 4
0x1800018a8  mov     [rbp+40h+var_A8], 4
0x1800018b0  mov     [rbp+40h+var_B8], 4
0x1800018b8  test    rdx, rdx
0x1800018bb  jz      short loc_1800018D3
0x1800018bd  mov     rax, rcx
0x1800018c0  inc     rax
0x1800018c3  cmp     [rdx+rax*2], r9w
0x1800018c8  jnz     short loc_1800018C0
0x1800018ca  lea     eax, ds:2[rax*2]
0x1800018d1  jmp     short loc_1800018D9
0x1800018d3  mov     rdx, r11
0x1800018d6  mov     eax, r8d
0x1800018d9  mov     [rsp+140h+var_C8], eax
0x1800018dd  mov     rax, [rbp+40h+arg_28]
0x1800018e1  mov     [rsp+140h+var_D0], rdx
0x1800018e6  mov     [rsp+140h+var_C4], r9d
0x1800018eb  mov     rdx, [rax]
0x1800018ee  test    rdx, rdx
0x1800018f1  jz      short loc_180001909
0x1800018f3  mov     rax, rcx
0x1800018f6  inc     rax
0x1800018f9  cmp     [rdx+rax*2], r9w
0x1800018fe  jnz     short loc_1800018F6
0x180001900  lea     eax, ds:2[rax*2]
0x180001907  jmp     short loc_18000190F
0x180001909  mov     rdx, r11
0x18000190c  mov     eax, r8d
0x18000190f  mov     [rsp+140h+var_D8], eax
0x180001913  mov     rax, [rbp+40h+arg_20]
0x180001917  mov     [rsp+140h+var_E0], rdx
0x18000191c  mov     [rsp+140h+var_D4], r9d
0x180001921  mov     rdx, [rax]
0x180001924  test    rdx, rdx
0x180001927  jz      short loc_18000193D
0x180001929  inc     rcx
0x18000192c  cmp     [rdx+rcx*2], r9w
0x180001931  jnz     short loc_180001929
0x180001933  lea     r8d, ds:2[rcx*2]
0x18000193b  jmp     short loc_180001940
0x18000193d  mov     rdx, r11
0x180001940  lea     rax, [rsp+140h+var_110]
0x180001945  mov     [rsp+140h+var_F0], rdx
0x18000194a  mov     [rsp+140h+var_E8], r8d
0x18000194f  lea     rcx, dword_18001C038
0x180001956  mov     [rsp+140h+var_118], rax
0x18000195b  xor     r8d, r8d
0x18000195e  mov     rdx, r10
0x180001961  mov     [rsp+140h+var_120], 10h
0x180001969  mov     [rsp+140h+var_E4], r9d
0x18000196e  call    _tlgWriteTransfer_EventWriteTransfer
0x180001973  mov     rcx, [rbp+40h+var_10]
0x180001977  xor     rcx, rsp; StackCookie
0x18000197a  call    __security_check_cookie
0x18000197f  add     rsp, 140h
0x180001986  pop     rbp
0x180001987  retn
```
