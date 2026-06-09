# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001008`
- end: `0x180001154`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U4@U2@U2@U2@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@533342@Z`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800109f8`

## callees

- `0x180001008`
- `0x1800114e0`
- `0x180012880`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const WCHAR **a7,
        const WCHAR **a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13)
{
  __int64 v14; // rcx
  int v15; // r8d
  const WCHAR *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  const WCHAR *v19; // rdx
  _BYTE v21[32]; // [rsp+30h] [rbp-C1h] BYREF
  __int64 v22; // [rsp+50h] [rbp-A1h]
  __int64 v23; // [rsp+58h] [rbp-99h]
  __int64 v24; // [rsp+60h] [rbp-91h]
  __int64 v25; // [rsp+68h] [rbp-89h]
  __int64 v26; // [rsp+70h] [rbp-81h]
  __int64 v27; // [rsp+78h] [rbp-79h]
  const WCHAR *v28; // [rsp+80h] [rbp-71h]
  int v29; // [rsp+88h] [rbp-69h]
  int v30; // [rsp+8Ch] [rbp-65h]
  const WCHAR *v31; // [rsp+90h] [rbp-61h]
  int v32; // [rsp+98h] [rbp-59h]
  int v33; // [rsp+9Ch] [rbp-55h]
  __int64 v34; // [rsp+A0h] [rbp-51h]
  __int64 v35; // [rsp+A8h] [rbp-49h]
  __int64 v36; // [rsp+B0h] [rbp-41h]
  __int64 v37; // [rsp+B8h] [rbp-39h]
  __int64 v38; // [rsp+C0h] [rbp-31h]
  __int64 v39; // [rsp+C8h] [rbp-29h]
  __int64 v40; // [rsp+D0h] [rbp-21h]
  __int64 v41; // [rsp+D8h] [rbp-19h]
  __int64 v42; // [rsp+E0h] [rbp-11h]
  __int64 v43; // [rsp+E8h] [rbp-9h]

  v42 = a13;
  v14 = -1;
  v40 = a12;
  v15 = 2;
  v38 = a11;
  v36 = a10;
  v34 = a9;
  v43 = 8;
  v41 = 1;
  v39 = 4;
  v16 = *a8;
  v37 = 4;
  v35 = 4;
  if ( v16 )
  {
    v17 = -1;
    do
      ++v17;
    while ( v16[v17] );
    v18 = 2 * v17 + 2;
  }
  else
  {
    v16 = &Class;
    v18 = 2;
  }
  v32 = v18;
  v31 = v16;
  v33 = 0;
  v19 = *a7;
  if ( *a7 )
  {
    do
      ++v14;
    while ( v19[v14] );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v19 = &Class;
  }
  v26 = a6;
  v24 = a5;
  v28 = v19;
  v29 = v15;
  v22 = a4;
  v30 = 0;
  v27 = 1;
  v25 = 4;
  v23 = 8;
  return tlgWriteAgg((unsigned int)&dword_180045008, a2, 0, 12, (__int64)v21);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-0Fh]
0x18000100f  sub     rsp, 100h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+0Fh+var_10], rax
0x180001024  mov     rax, [rbp+0Fh+arg_60]
0x180001028  xor     r11d, r11d
0x18000102b  mov     [rbp+0Fh+var_20], rax
0x18000102f  mov     r10, rdx
0x180001032  mov     rax, [rbp+0Fh+arg_58]
0x180001036  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000103a  mov     [rbp+0Fh+var_30], rax
0x18000103e  mov     rax, [rbp+0Fh+arg_50]
0x180001042  lea     r8d, [r11+2]
0x180001046  mov     [rbp+0Fh+var_40], rax
0x18000104a  mov     rax, [rbp+0Fh+arg_48]
0x18000104e  mov     [rbp+0Fh+var_50], rax
0x180001052  mov     rax, [rbp+0Fh+arg_40]
0x180001056  mov     [rbp+0Fh+var_60], rax
0x18000105a  mov     rax, [rbp+0Fh+arg_38]
0x18000105e  mov     [rbp+0Fh+var_18], 8
0x180001066  mov     [rbp+0Fh+var_28], 1
0x18000106e  mov     [rbp+0Fh+var_38], 4
0x180001076  mov     rdx, [rax]
0x180001079  mov     [rbp+0Fh+var_48], 4
0x180001081  mov     [rbp+0Fh+var_58], 4
0x180001089  test    rdx, rdx
0x18000108c  jz      short loc_1800010A4
0x18000108e  mov     rax, rcx
0x180001091  inc     rax
0x180001094  cmp     [rdx+rax*2], r11w
0x180001099  jnz     short loc_180001091
0x18000109b  lea     eax, ds:2[rax*2]
0x1800010a2  jmp     short loc_1800010AE
0x1800010a4  lea     rdx, Class
0x1800010ab  mov     eax, r8d
0x1800010ae  mov     [rbp+0Fh+var_68], eax
0x1800010b1  mov     rax, [rbp+0Fh+arg_30]
0x1800010b5  mov     [rbp+0Fh+var_70], rdx
0x1800010b9  mov     [rbp+0Fh+var_64], r11d
0x1800010bd  mov     rdx, [rax]
0x1800010c0  test    rdx, rdx
0x1800010c3  jz      short loc_1800010D9
0x1800010c5  inc     rcx
0x1800010c8  cmp     [rdx+rcx*2], r11w
0x1800010cd  jnz     short loc_1800010C5
0x1800010cf  lea     r8d, ds:2[rcx*2]
0x1800010d7  jmp     short loc_1800010E0
0x1800010d9  lea     rdx, Class
0x1800010e0  mov     rax, [rbp+0Fh+arg_28]
0x1800010e4  lea     rcx, dword_180045008
0x1800010eb  mov     [rsp+100h+var_90], rax
0x1800010f0  mov     rax, [rbp+0Fh+arg_20]
0x1800010f4  mov     [rsp+100h+var_A0], rax
0x1800010f9  lea     rax, [rsp+100h+var_D0]
0x1800010fe  mov     [rbp+0Fh+var_80], rdx
0x180001102  mov     rdx, r10
0x180001105  mov     [rbp+0Fh+var_78], r8d
0x180001109  xor     r8d, r8d
0x18000110c  mov     [rsp+100h+var_B0], r9
0x180001111  mov     r9d, 0Ch
0x180001117  mov     [rsp+100h+var_E0], rax
0x18000111c  mov     [rbp+0Fh+var_74], r11d
0x180001120  mov     [rbp+0Fh+var_88], 1
0x180001128  mov     [rsp+100h+var_98], 4
0x180001131  mov     [rsp+100h+var_A8], 8
0x18000113a  call    _tlgWriteAgg
0x18000113f  mov     rcx, [rbp+0Fh+var_10]
0x180001143  xor     rcx, rsp; StackCookie
0x180001146  call    __security_check_cookie
0x18000114b  add     rsp, 100h
0x180001152  pop     rbp
0x180001153  retn
```
