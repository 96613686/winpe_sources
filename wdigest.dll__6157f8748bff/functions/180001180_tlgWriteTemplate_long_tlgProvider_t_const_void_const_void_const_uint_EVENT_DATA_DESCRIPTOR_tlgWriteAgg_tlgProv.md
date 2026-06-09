# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001180`
- end: `0x180001331`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U2@U3@U3@U3@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@44344442@Z`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180034cd0`

## callees

- `0x180001180`
- `0x1800114e0`
- `0x180012880`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        const WCHAR **a5,
        const WCHAR **a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        const WCHAR **a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15)
{
  __int64 v16; // rcx
  int v17; // r8d
  const WCHAR *v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  const WCHAR *v21; // rdx
  __int64 v22; // rax
  int v23; // eax
  const WCHAR *v24; // rdx
  _BYTE v26[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  const WCHAR *v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+68h] [rbp-98h]
  int v31; // [rsp+6Ch] [rbp-94h]
  const WCHAR *v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+7Ch] [rbp-84h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int64 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+90h] [rbp-70h]
  __int64 v38; // [rsp+98h] [rbp-68h]
  __int64 v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  const WCHAR *v41; // [rsp+B0h] [rbp-50h]
  int v42; // [rsp+B8h] [rbp-48h]
  int v43; // [rsp+BCh] [rbp-44h]
  __int64 v44; // [rsp+C0h] [rbp-40h]
  __int64 v45; // [rsp+C8h] [rbp-38h]
  __int64 v46; // [rsp+D0h] [rbp-30h]
  __int64 v47; // [rsp+D8h] [rbp-28h]
  __int64 v48; // [rsp+E0h] [rbp-20h]
  __int64 v49; // [rsp+E8h] [rbp-18h]
  __int64 v50; // [rsp+F0h] [rbp-10h]
  __int64 v51; // [rsp+F8h] [rbp-8h]
  __int64 v52; // [rsp+100h] [rbp+0h]
  __int64 v53; // [rsp+108h] [rbp+8h]

  v52 = a15;
  v16 = -1;
  v50 = a14;
  v17 = 2;
  v48 = a13;
  v46 = a12;
  v44 = a11;
  v53 = 8;
  v51 = 4;
  v49 = 4;
  v18 = *a10;
  v47 = 4;
  v45 = 4;
  if ( v18 )
  {
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    v20 = 2 * v19 + 2;
  }
  else
  {
    v18 = &Class;
    v20 = 2;
  }
  v42 = v20;
  v39 = a9;
  v37 = a8;
  v35 = a7;
  v41 = v18;
  v43 = 0;
  v40 = 4;
  v21 = *a6;
  v38 = 4;
  v36 = 4;
  if ( v21 )
  {
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    v23 = 2 * v22 + 2;
  }
  else
  {
    v21 = &Class;
    v23 = 2;
  }
  v33 = v23;
  v32 = v21;
  v34 = 0;
  v24 = *a5;
  if ( *a5 )
  {
    do
      ++v16;
    while ( v24[v16] );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v24 = &Class;
  }
  v29 = v24;
  v30 = v17;
  v27 = a4;
  v31 = 0;
  v28 = 8;
  return tlgWriteAgg((unsigned int)&dword_180045108, a2, 0, 14, (__int64)v26);
}

```

## disassembly

```asm
0x180001180  mov     [rsp-8+arg_0], rbx
0x180001185  push    rbp
0x180001186  lea     rbp, [rsp-20h]
0x18000118b  sub     rsp, 120h
0x180001192  mov     rax, cs:__security_cookie
0x180001199  xor     rax, rsp
0x18000119c  mov     [rbp+20h+var_10], rax
0x1800011a0  mov     rax, [rbp+20h+arg_70]
0x1800011a7  xor     r11d, r11d
0x1800011aa  mov     [rbp+20h+var_20], rax
0x1800011ae  mov     r10, rdx
0x1800011b1  mov     rax, [rbp+20h+arg_68]
0x1800011b8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800011bc  mov     [rbp+20h+var_30], rax
0x1800011c0  mov     rax, [rbp+20h+arg_60]
0x1800011c7  lea     r8d, [r11+2]
0x1800011cb  mov     [rbp+20h+var_40], rax
0x1800011cf  mov     rax, [rbp+20h+arg_58]
0x1800011d6  mov     [rbp+20h+var_50], rax
0x1800011da  mov     rax, [rbp+20h+arg_50]
0x1800011e1  mov     [rbp+20h+var_60], rax
0x1800011e5  mov     rax, [rbp+20h+arg_48]
0x1800011e9  mov     [rbp+20h+var_18], 8
0x1800011f1  mov     [rbp+20h+var_28], 4
0x1800011f9  mov     [rbp+20h+var_38], 4
0x180001201  mov     rdx, [rax]
0x180001204  mov     [rbp+20h+var_48], 4
0x18000120c  mov     [rbp+20h+var_58], 4
0x180001214  test    rdx, rdx
0x180001217  jz      short loc_18000122F
0x180001219  mov     rax, rcx
0x18000121c  inc     rax
0x18000121f  cmp     [rdx+rax*2], r11w
0x180001224  jnz     short loc_18000121C
0x180001226  lea     eax, ds:2[rax*2]
0x18000122d  jmp     short loc_180001239
0x18000122f  lea     rdx, Class
0x180001236  mov     eax, r8d
0x180001239  mov     [rbp+20h+var_68], eax
0x18000123c  mov     rax, [rbp+20h+arg_40]
0x180001240  mov     [rbp+20h+var_80], rax
0x180001244  mov     rax, [rbp+20h+arg_38]
0x180001248  mov     [rbp+20h+var_90], rax
0x18000124c  mov     rax, [rbp+20h+arg_30]
0x180001250  mov     [rbp+20h+var_A0], rax
0x180001254  mov     rax, [rbp+20h+arg_28]
0x180001258  mov     [rbp+20h+var_70], rdx
0x18000125c  mov     [rbp+20h+var_64], r11d
0x180001260  mov     [rbp+20h+var_78], 4
0x180001268  mov     rdx, [rax]
0x18000126b  mov     [rbp+20h+var_88], 4
0x180001273  mov     [rbp+20h+var_98], 4
0x18000127b  test    rdx, rdx
0x18000127e  jz      short loc_180001296
0x180001280  mov     rax, rcx
0x180001283  inc     rax
0x180001286  cmp     [rdx+rax*2], r11w
0x18000128b  jnz     short loc_180001283
0x18000128d  lea     eax, ds:2[rax*2]
0x180001294  jmp     short loc_1800012A0
0x180001296  lea     rdx, Class
0x18000129d  mov     eax, r8d
0x1800012a0  mov     [rsp+120h+var_A8], eax
0x1800012a4  mov     rax, [rbp+20h+arg_20]
0x1800012a8  mov     [rsp+120h+var_B0], rdx
0x1800012ad  mov     [rsp+120h+var_A4], r11d
0x1800012b2  mov     rdx, [rax]
0x1800012b5  test    rdx, rdx
0x1800012b8  jz      short loc_1800012CE
0x1800012ba  inc     rcx
0x1800012bd  cmp     [rdx+rcx*2], r11w
0x1800012c2  jnz     short loc_1800012BA
0x1800012c4  lea     r8d, ds:2[rcx*2]
0x1800012cc  jmp     short loc_1800012D5
0x1800012ce  lea     rdx, Class
0x1800012d5  mov     [rsp+120h+var_C0], rdx
0x1800012da  lea     rax, [rsp+120h+var_F0]
0x1800012df  mov     [rsp+120h+var_B8], r8d
0x1800012e4  lea     rcx, dword_180045108
0x1800012eb  mov     [rsp+120h+var_D0], r9
0x1800012f0  xor     r8d, r8d
0x1800012f3  mov     r9d, 0Eh
0x1800012f9  mov     [rsp+120h+var_100], rax
0x1800012fe  mov     rdx, r10
0x180001301  mov     [rsp+120h+var_B4], r11d
0x180001306  mov     [rsp+120h+var_C8], 8
0x18000130f  call    _tlgWriteAgg
0x180001314  mov     rcx, [rbp+20h+var_10]
0x180001318  xor     rcx, rsp; StackCookie
0x18000131b  call    __security_check_cookie
0x180001320  mov     rbx, [rsp+120h+arg_0]
0x180001328  add     rsp, 120h
0x18000132f  pop     rbp
0x180001330  retn
```
