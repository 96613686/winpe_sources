# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001338`
- end: `0x180001498`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U2@U2@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@443342@Z`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180034b20`

## callees

- `0x180001338`
- `0x1800114e0`
- `0x180012880`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        const WCHAR **a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        const WCHAR **a9,
        const WCHAR **a10,
        __int64 a11,
        __int64 a12)
{
  __int64 v13; // rcx
  int v14; // r8d
  const WCHAR *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  const WCHAR *v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  const WCHAR *v21; // rdx
  _BYTE v23[32]; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v24; // [rsp+50h] [rbp-89h]
  __int64 v25; // [rsp+58h] [rbp-81h]
  const WCHAR *v26; // [rsp+60h] [rbp-79h]
  int v27; // [rsp+68h] [rbp-71h]
  int v28; // [rsp+6Ch] [rbp-6Dh]
  __int64 v29; // [rsp+70h] [rbp-69h]
  __int64 v30; // [rsp+78h] [rbp-61h]
  __int64 v31; // [rsp+80h] [rbp-59h]
  __int64 v32; // [rsp+88h] [rbp-51h]
  __int64 v33; // [rsp+90h] [rbp-49h]
  __int64 v34; // [rsp+98h] [rbp-41h]
  const WCHAR *v35; // [rsp+A0h] [rbp-39h]
  int v36; // [rsp+A8h] [rbp-31h]
  int v37; // [rsp+ACh] [rbp-2Dh]
  const WCHAR *v38; // [rsp+B0h] [rbp-29h]
  int v39; // [rsp+B8h] [rbp-21h]
  int v40; // [rsp+BCh] [rbp-1Dh]
  __int64 v41; // [rsp+C0h] [rbp-19h]
  __int64 v42; // [rsp+C8h] [rbp-11h]
  __int64 v43; // [rsp+D0h] [rbp-9h]
  __int64 v44; // [rsp+D8h] [rbp-1h]

  v43 = a12;
  v13 = -1;
  v41 = a11;
  v14 = 2;
  v44 = 8;
  v42 = 4;
  v15 = *a10;
  if ( *a10 )
  {
    v16 = -1;
    do
      ++v16;
    while ( v15[v16] );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &Class;
    v17 = 2;
  }
  v39 = v17;
  v38 = v15;
  v40 = 0;
  v18 = *a9;
  if ( *a9 )
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
  v36 = v20;
  v33 = a8;
  v31 = a7;
  v29 = a6;
  v35 = v18;
  v37 = 0;
  v34 = 4;
  v21 = *a5;
  v32 = 4;
  v30 = 4;
  if ( v21 )
  {
    do
      ++v13;
    while ( v21[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v21 = &Class;
  }
  v26 = v21;
  v27 = v14;
  v24 = a4;
  v28 = 0;
  v25 = 8;
  return tlgWriteAgg((unsigned int)&dword_180045108, a2, 0, 11, (__int64)v23);
}

```

## disassembly

```asm
0x180001338  push    rbp
0x18000133a  lea     rbp, [rsp-17h]
0x18000133f  sub     rsp, 0F0h
0x180001346  mov     rax, cs:__security_cookie
0x18000134d  xor     rax, rsp
0x180001350  mov     [rbp+17h+var_10], rax
0x180001354  mov     rax, [rbp+17h+arg_58]
0x180001358  xor     r11d, r11d
0x18000135b  mov     [rbp+17h+var_20], rax
0x18000135f  mov     r10, rdx
0x180001362  mov     rax, [rbp+17h+arg_50]
0x180001366  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000136a  mov     [rbp+17h+var_30], rax
0x18000136e  mov     rax, [rbp+17h+arg_48]
0x180001372  lea     r8d, [r11+2]
0x180001376  mov     [rbp+17h+var_18], 8
0x18000137e  mov     [rbp+17h+var_28], 4
0x180001386  mov     rdx, [rax]
0x180001389  test    rdx, rdx
0x18000138c  jz      short loc_1800013A4
0x18000138e  mov     rax, rcx
0x180001391  inc     rax
0x180001394  cmp     [rdx+rax*2], r11w
0x180001399  jnz     short loc_180001391
0x18000139b  lea     eax, ds:2[rax*2]
0x1800013a2  jmp     short loc_1800013AE
0x1800013a4  lea     rdx, Class
0x1800013ab  mov     eax, r8d
0x1800013ae  mov     [rbp+17h+var_38], eax
0x1800013b1  mov     rax, [rbp+17h+arg_40]
0x1800013b5  mov     [rbp+17h+var_40], rdx
0x1800013b9  mov     [rbp+17h+var_34], r11d
0x1800013bd  mov     rdx, [rax]
0x1800013c0  test    rdx, rdx
0x1800013c3  jz      short loc_1800013DB
0x1800013c5  mov     rax, rcx
0x1800013c8  inc     rax
0x1800013cb  cmp     [rdx+rax*2], r11w
0x1800013d0  jnz     short loc_1800013C8
0x1800013d2  lea     eax, ds:2[rax*2]
0x1800013d9  jmp     short loc_1800013E5
0x1800013db  lea     rdx, Class
0x1800013e2  mov     eax, r8d
0x1800013e5  mov     [rbp+17h+var_48], eax
0x1800013e8  mov     rax, [rbp+17h+arg_38]
0x1800013ec  mov     [rbp+17h+var_60], rax
0x1800013f0  mov     rax, [rbp+17h+arg_30]
0x1800013f4  mov     [rbp+17h+var_70], rax
0x1800013f8  mov     rax, [rbp+17h+arg_28]
0x1800013fc  mov     [rbp+17h+var_80], rax
0x180001400  mov     rax, [rbp+17h+arg_20]
0x180001404  mov     [rbp+17h+var_50], rdx
0x180001408  mov     [rbp+17h+var_44], r11d
0x18000140c  mov     [rbp+17h+var_58], 4
0x180001414  mov     rdx, [rax]
0x180001417  mov     [rbp+17h+var_68], 4
0x18000141f  mov     [rbp+17h+var_78], 4
0x180001427  test    rdx, rdx
0x18000142a  jz      short loc_180001440
0x18000142c  inc     rcx
0x18000142f  cmp     [rdx+rcx*2], r11w
0x180001434  jnz     short loc_18000142C
0x180001436  lea     r8d, ds:2[rcx*2]
0x18000143e  jmp     short loc_180001447
0x180001440  lea     rdx, Class
0x180001447  mov     [rbp+17h+var_90], rdx
0x18000144b  lea     rax, [rsp+0F0h+var_C0]
0x180001450  mov     [rbp+17h+var_88], r8d
0x180001454  lea     rcx, dword_180045108
0x18000145b  mov     [rsp+0F0h+var_A0], r9
0x180001460  xor     r8d, r8d
0x180001463  mov     r9d, 0Bh
0x180001469  mov     [rsp+0F0h+var_D0], rax
0x18000146e  mov     rdx, r10
0x180001471  mov     [rbp+17h+var_84], r11d
0x180001475  mov     [rsp+0F0h+var_98], 8
0x18000147e  call    _tlgWriteAgg
0x180001483  mov     rcx, [rbp+17h+var_10]
0x180001487  xor     rcx, rsp; StackCookie
0x18000148a  call    __security_check_cookie
0x18000148f  add     rsp, 0F0h
0x180001496  pop     rbp
0x180001497  retn
```
