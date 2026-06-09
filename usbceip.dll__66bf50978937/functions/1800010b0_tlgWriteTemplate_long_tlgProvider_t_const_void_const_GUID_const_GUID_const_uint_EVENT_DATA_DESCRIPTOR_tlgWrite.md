# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800010b0`
- end: `0x180001213`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$03@@4444AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, char **, char **, char **, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003dc4`

## callees

- `0x180001010`
- `0x1800010b0`
- `0x180002410`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
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
        __int64 a13)
{
  __int64 v14; // rcx
  int v15; // r8d
  char *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  char *v19; // rdx
  __int64 v20; // rax
  int v21; // eax
  char *v22; // rdx
  _BYTE v24[32]; // [rsp+30h] [rbp-B1h] BYREF
  char *v25; // [rsp+50h] [rbp-91h]
  int v26; // [rsp+58h] [rbp-89h]
  int v27; // [rsp+5Ch] [rbp-85h]
  char *v28; // [rsp+60h] [rbp-81h]
  int v29; // [rsp+68h] [rbp-79h]
  int v30; // [rsp+6Ch] [rbp-75h]
  char *v31; // [rsp+70h] [rbp-71h]
  int v32; // [rsp+78h] [rbp-69h]
  int v33; // [rsp+7Ch] [rbp-65h]
  __int64 v34; // [rsp+80h] [rbp-61h]
  __int64 v35; // [rsp+88h] [rbp-59h]
  __int64 v36; // [rsp+90h] [rbp-51h]
  __int64 v37; // [rsp+98h] [rbp-49h]
  __int64 v38; // [rsp+A0h] [rbp-41h]
  __int64 v39; // [rsp+A8h] [rbp-39h]
  __int64 v40; // [rsp+B0h] [rbp-31h]
  __int64 v41; // [rsp+B8h] [rbp-29h]
  __int64 v42; // [rsp+C0h] [rbp-21h]
  __int64 v43; // [rsp+C8h] [rbp-19h]
  __int64 v44; // [rsp+D0h] [rbp-11h]
  __int64 v45; // [rsp+D8h] [rbp-9h]

  v44 = a13;
  v42 = a12;
  v14 = -1;
  v40 = a11;
  v15 = 2;
  v38 = a10;
  v36 = a9;
  v34 = a8;
  v45 = 8;
  v43 = 4;
  v41 = 4;
  v16 = *a7;
  v39 = 4;
  v37 = 4;
  v35 = 4;
  if ( v16 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)&v16[2 * v17] );
    v18 = 2 * v17 + 2;
  }
  else
  {
    v16 = byte_180013A54;
    v18 = 2;
  }
  v32 = v18;
  v31 = v16;
  v33 = 0;
  v19 = *a6;
  if ( *a6 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)&v19[2 * v20] );
    v21 = 2 * v20 + 2;
  }
  else
  {
    v19 = byte_180013A54;
    v21 = 2;
  }
  v29 = v21;
  v28 = v19;
  v30 = 0;
  v22 = *a5;
  if ( *a5 )
  {
    do
      ++v14;
    while ( *(_WORD *)&v22[2 * v14] );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v22 = byte_180013A54;
  }
  v25 = v22;
  v26 = v15;
  v27 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C038, a2, 0, 0, 11, v24);
}

```

## disassembly

```asm
0x1800010b0  push    rbp
0x1800010b2  lea     rbp, [rsp-0Fh]
0x1800010b7  sub     rsp, 0F0h
0x1800010be  mov     rax, cs:__security_cookie
0x1800010c5  xor     rax, rsp
0x1800010c8  mov     [rbp+0Fh+var_10], rax
0x1800010cc  mov     rax, [rbp+0Fh+arg_60]
0x1800010d0  lea     r11, byte_180013A54
0x1800010d7  mov     [rbp+0Fh+var_20], rax
0x1800010db  xor     r9d, r9d
0x1800010de  mov     rax, [rbp+0Fh+arg_58]
0x1800010e2  mov     r10, rdx
0x1800010e5  mov     [rbp+0Fh+var_30], rax
0x1800010e9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800010ed  mov     rax, [rbp+0Fh+arg_50]
0x1800010f1  mov     [rbp+0Fh+var_40], rax
0x1800010f5  lea     r8d, [r9+2]
0x1800010f9  mov     rax, [rbp+0Fh+arg_48]
0x1800010fd  mov     [rbp+0Fh+var_50], rax
0x180001101  mov     rax, [rbp+0Fh+arg_40]
0x180001105  mov     [rbp+0Fh+var_60], rax
0x180001109  mov     rax, [rbp+0Fh+arg_38]
0x18000110d  mov     [rbp+0Fh+var_70], rax
0x180001111  mov     rax, [rbp+0Fh+arg_30]
0x180001115  mov     [rbp+0Fh+var_18], 8
0x18000111d  mov     [rbp+0Fh+var_28], 4
0x180001125  mov     [rbp+0Fh+var_38], 4
0x18000112d  mov     rdx, [rax]
0x180001130  mov     [rbp+0Fh+var_48], 4
0x180001138  mov     [rbp+0Fh+var_58], 4
0x180001140  mov     [rbp+0Fh+var_68], 4
0x180001148  test    rdx, rdx
0x18000114b  jz      short loc_180001163
0x18000114d  mov     rax, rcx
0x180001150  inc     rax
0x180001153  cmp     [rdx+rax*2], r9w
0x180001158  jnz     short loc_180001150
0x18000115a  lea     eax, ds:2[rax*2]
0x180001161  jmp     short loc_180001169
0x180001163  mov     rdx, r11
0x180001166  mov     eax, r8d
0x180001169  mov     [rbp+0Fh+var_78], eax
0x18000116c  mov     rax, [rbp+0Fh+arg_28]
0x180001170  mov     [rbp+0Fh+var_80], rdx
0x180001174  mov     [rbp+0Fh+var_74], r9d
0x180001178  mov     rdx, [rax]
0x18000117b  test    rdx, rdx
0x18000117e  jz      short loc_180001196
0x180001180  mov     rax, rcx
0x180001183  inc     rax
0x180001186  cmp     [rdx+rax*2], r9w
0x18000118b  jnz     short loc_180001183
0x18000118d  lea     eax, ds:2[rax*2]
0x180001194  jmp     short loc_18000119C
0x180001196  mov     rdx, r11
0x180001199  mov     eax, r8d
0x18000119c  mov     [rbp+0Fh+var_88], eax
0x18000119f  mov     rax, [rbp+0Fh+arg_20]
0x1800011a3  mov     [rsp+0F0h+var_90], rdx
0x1800011a8  mov     [rbp+0Fh+var_84], r9d
0x1800011ac  mov     rdx, [rax]
0x1800011af  test    rdx, rdx
0x1800011b2  jz      short loc_1800011C8
0x1800011b4  inc     rcx
0x1800011b7  cmp     [rdx+rcx*2], r9w
0x1800011bc  jnz     short loc_1800011B4
0x1800011be  lea     r8d, ds:2[rcx*2]
0x1800011c6  jmp     short loc_1800011CB
0x1800011c8  mov     rdx, r11
0x1800011cb  lea     rax, [rsp+0F0h+var_C0]
0x1800011d0  mov     [rsp+0F0h+var_A0], rdx
0x1800011d5  mov     [rsp+0F0h+var_98], r8d
0x1800011da  lea     rcx, dword_18001C038
0x1800011e1  mov     [rsp+0F0h+var_C8], rax
0x1800011e6  xor     r8d, r8d
0x1800011e9  mov     rdx, r10
0x1800011ec  mov     [rsp+0F0h+var_D0], 0Bh
0x1800011f4  mov     [rsp+0F0h+var_94], r9d
0x1800011f9  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011fe  mov     rcx, [rbp+0Fh+var_10]
0x180001202  xor     rcx, rsp; StackCookie
0x180001205  call    __security_check_cookie
0x18000120a  add     rsp, 0F0h
0x180001211  pop     rbp
0x180001212  retn
```
