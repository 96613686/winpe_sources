# LocationDataSource::UpdateMovementThreshold(void)

- ea: `0x1800123b8`
- end: `0x1800124f5`
- name: `?UpdateMovementThreshold@LocationDataSource@@AEAAXXZ`
- size: `317`
- prototype: `void __fastcall(LocationDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18001126c`

## callees

- `0x18000166c`
- `0x18000169c`
- `0x18000cfec`
- `0x180011230`
- `0x180011b0c`
- `0x1800123b8`
- `0x18001b150`
- `0x18001d010`

## pseudocode

```c
void __fastcall LocationDataSource::UpdateMovementThreshold(LocationDataSource *this)
{
  double v2; // xmm6_8
  __int64 v3; // r8
  int v4; // r8d
  __int64 v5; // [rsp+38h] [rbp-D0h] BYREF
  double v6; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v7; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v8[128]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v9; // [rsp+D8h] [rbp-30h] BYREF
  char v10[32]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 *v11; // [rsp+108h] [rbp+0h]
  __int64 v12; // [rsp+110h] [rbp+8h]
  double *v13; // [rsp+118h] [rbp+10h]
  __int64 v14; // [rsp+120h] [rbp+18h]
  __int64 *v15; // [rsp+128h] [rbp+20h]
  __int64 v16; // [rsp+130h] [rbp+28h]

  v2 = (double)*((int *)this + 4);
  Cache::Lock(*(struct Cache **)this, (Cache::Proxy *)v8);
  if ( *(_BYTE *)(v9 + 8) )
    v2 = fmax(*(double *)Cache::ValueProxy<double>::GetValue(&v9), v2);
  v3 = (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 72LL))(*((_QWORD *)this + 4));
  if ( (unsigned int)dword_180030000 > 5
    && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180030000, 0x200000000000LL, v3) )
  {
    LODWORD(v5) = v4;
    v6 = v2;
    v7 = 0x1000000;
    v15 = &v5;
    v16 = 4;
    v13 = &v6;
    v14 = 8;
    v11 = &v7;
    v12 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_180030000, word_18002935A, 0, 0, 5, v10);
  }
  Cache::Proxy::~Proxy((Cache::Proxy *)v8);
}

```

## disassembly

```asm
0x1800123b8  mov     rax, rsp
0x1800123bb  mov     [rax+10h], rbx
0x1800123bf  push    rbp
0x1800123c0  lea     rbp, [rax-58h]
0x1800123c4  sub     rsp, 150h
0x1800123cb  movaps  xmmword ptr [rax-18h], xmm6
0x1800123cf  mov     rax, cs:__security_cookie
0x1800123d6  xor     rax, rsp
0x1800123d9  mov     [rbp+50h+var_20], rax
0x1800123dd  mov     rbx, rcx
0x1800123e0  mov     eax, [rcx+10h]
0x1800123e3  xorps   xmm6, xmm6
0x1800123e6  cvtsi2sd xmm6, rax
0x1800123eb  lea     rdx, [rsp+150h+var_100]
0x1800123f0  mov     rcx, [rcx]
0x1800123f3  call    ?Lock@Cache@@QEAA?AVProxy@1@XZ; Cache::Lock(void)
0x1800123f8  nop
0x1800123f9  mov     rax, [rbp+50h+var_80]
0x1800123fd  cmp     byte ptr [rax+8], 0
0x180012401  jz      short loc_180012417
0x180012403  lea     rcx, [rbp+50h+var_80]
0x180012407  call    ?GetValue@?$ValueProxy@N@Cache@@QEBAAEBNXZ; Cache::ValueProxy<double>::GetValue(void)
0x18001240c  movsd   xmm0, qword ptr [rax]
0x180012410  maxsd   xmm0, xmm6
0x180012414  movaps  xmm6, xmm0
0x180012417  movaps  xmm1, xmm6
0x18001241a  mov     rcx, [rbx+20h]
0x18001241e  mov     rax, [rcx]
0x180012421  mulsd   xmm1, cs:__real@408f400000000000
0x180012429  mov     rax, [rax+48h]
0x18001242d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012432  mov     r8d, eax
0x180012435  mov     ecx, cs:dword_180030000
0x18001243b  cmp     ecx, 5
0x18001243e  jbe     loc_1800124C9
0x180012444  mov     rdx, 200000000000h
0x18001244e  call    _tlgKeywordOn
0x180012453  test    al, al
0x180012455  jz      short loc_1800124C9
0x180012457  mov     dword ptr [rsp+150h+var_120], r8d
0x18001245c  movsd   [rsp+150h+var_118], xmm6
0x180012462  mov     [rsp+150h+var_110], 1000000h
0x18001246b  lea     rax, [rsp+150h+var_120]
0x180012470  mov     [rbp+50h+var_30], rax
0x180012474  mov     [rbp+50h+var_28], 4
0x18001247c  lea     rax, [rsp+150h+var_118]
0x180012481  mov     [rbp+50h+var_40], rax
0x180012485  mov     [rbp+50h+var_38], 8
0x18001248d  lea     rax, [rsp+150h+var_110]
0x180012492  mov     [rbp+50h+var_50], rax
0x180012496  mov     [rbp+50h+var_48], 8
0x18001249e  lea     rax, [rbp+50h+var_70]
0x1800124a2  mov     qword ptr [rsp+150h+var_128], rax
0x1800124a7  mov     dword ptr [rsp+150h+var_130], 5
0x1800124af  xor     r9d, r9d
0x1800124b2  xor     r8d, r8d
0x1800124b5  lea     rdx, word_18002935A
0x1800124bc  lea     rcx, dword_180030000
0x1800124c3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800124c8  nop
0x1800124c9  lea     rcx, [rsp+150h+var_100]; this
0x1800124ce  call    ??1Proxy@Cache@@QEAA@XZ; Cache::Proxy::~Proxy(void)
0x1800124d3  mov     rcx, [rbp+50h+var_20]
0x1800124d7  xor     rcx, rsp; StackCookie
0x1800124da  call    __security_check_cookie
0x1800124df  lea     r11, [rsp+150h+var_s0]
0x1800124e7  mov     rbx, [r11+18h]
0x1800124eb  movaps  xmm6, xmmword ptr [r11-10h]
0x1800124f0  mov     rsp, r11
0x1800124f3  pop     rbp
0x1800124f4  retn
```
