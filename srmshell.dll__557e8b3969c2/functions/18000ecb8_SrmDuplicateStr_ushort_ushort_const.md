# SrmDuplicateStr(ushort * &,ushort const *)

- ea: `0x18000ecb8`
- end: `0x18000eeab`
- name: `?SrmDuplicateStr@@YAXAEAPEAGPEBG@Z`
- size: `499`
- prototype: `void __fastcall(unsigned __int16 **, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000eb40`
- `0x180016f34`

## callees

- `0x1800083e0`
- `0x18000d368`
- `0x18000ecb8`
- `0x18001623c`
- `0x180016564`
- `0x180018f68`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ed7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ed7f`

## pseudocode

```c
void __fastcall SrmDuplicateStr(unsigned __int16 **a1, unsigned __int16 *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // r8
  unsigned __int64 v8; // rdx
  signed int v9; // ecx
  __int64 v10; // rax
  unsigned __int16 v11; // cx
  unsigned __int16 *v12; // rcx
  char Hr; // al
  int v14; // eax
  char v15; // al
  _QWORD v16[3]; // [rsp+28h] [rbp-D8h] BYREF
  int v17; // [rsp+40h] [rbp-C0h]
  int v18; // [rsp+44h] [rbp-BCh]
  int v19; // [rsp+48h] [rbp-B8h]
  char v20[96]; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+B0h] [rbp-50h]
  void **v22; // [rsp+C0h] [rbp-40h] BYREF
  int v23; // [rsp+C8h] [rbp-38h]

  v16[0] = L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h";
  v16[1] = L"SrmDuplicateStr";
  v16[2] = L"INCLSTRH";
  v17 = 78;
  v18 = 17;
  v19 = 255;
  v21 = 0x1000000;
  memset_0(v20, 0, sizeof(v20));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v22, (const struct CSrmDebugInfo *)v16, 0);
  if ( a2 )
  {
    v4 = -1;
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5 + 2);
    v7 = v6;
    *a1 = v6;
    if ( !v6 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v22, -2147024882);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v22);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v22, 0x57u, Hr, 0, v16);
    }
    v23 = 0;
    do
      ++v4;
    while ( a2[v4] );
    v8 = v4 + 1;
    v9 = -2147024809;
    if ( v4 != -1 )
    {
      if ( v8 > 0x7FFFFFFF )
      {
        *v6 = 0;
        v23 = -2147024809;
        goto LABEL_22;
      }
      v10 = 2147483646;
      do
      {
        if ( !v10 )
          break;
        v11 = *a2;
        if ( !*a2 )
          break;
        ++a2;
        *v7++ = v11;
        --v10;
        --v8;
      }
      while ( v8 );
      v12 = v7 - 1;
      if ( v8 )
        v12 = v7;
      *v12 = 0;
      v9 = v8 == 0 ? 0x8007007A : 0;
    }
    v23 = v9;
    if ( v9 >= 0 )
    {
      v23 = v9;
      goto LABEL_19;
    }
LABEL_22:
    v14 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v22);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v22, v14);
    v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v22);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v22, 0x59u, v15, 0, v16);
  }
  *a1 = 0;
LABEL_19:
  v22 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v22);
}

```

## disassembly

```asm
0x18000ecb8  mov     [rsp-8+arg_10], rbx
0x18000ecbd  mov     [rsp-8+arg_18], rsi
0x18000ecc2  push    rbp
0x18000ecc3  push    rdi
0x18000ecc4  push    r14
0x18000ecc6  lea     rbp, [rsp-80h]
0x18000eccb  sub     rsp, 180h
0x18000ecd2  mov     rax, cs:__security_cookie
0x18000ecd9  xor     rax, rsp
0x18000ecdc  mov     [rbp+90h+var_20], rax
0x18000ece0  mov     rdi, rdx
0x18000ece3  mov     rsi, rcx
0x18000ece6  lea     rax, [rsp+190h+var_168]
0x18000eceb  mov     [rsp+190h+var_170], rax
0x18000ecf0  lea     rax, aBaseFsFsrmUtil_0; "base\\fs\\fsrm\\utilities\\inc\\srmstr."...
0x18000ecf7  mov     [rsp+190h+var_168], rax
0x18000ecfc  lea     rax, aSrmduplicatest; "SrmDuplicateStr"
0x18000ed03  mov     [rsp+190h+var_160], rax
0x18000ed08  lea     rax, aInclstrh; "INCLSTRH"
0x18000ed0f  mov     [rsp+190h+var_158], rax
0x18000ed14  mov     [rsp+190h+var_150], 4Eh ; 'N'
0x18000ed1c  mov     [rsp+190h+var_14C], 11h
0x18000ed24  mov     [rsp+190h+var_148], 0FFh
0x18000ed2c  xor     r14d, r14d
0x18000ed2f  mov     [rbp+90h+var_E0], 1000000h
0x18000ed36  xor     edx, edx; Val
0x18000ed38  lea     r8d, [r14+60h]; Size
0x18000ed3c  lea     rcx, [rsp+190h+var_140]; void *
0x18000ed41  call    memset_0
0x18000ed46  nop
0x18000ed47  xor     r8d, r8d
0x18000ed4a  lea     rdx, [rsp+190h+var_168]
0x18000ed4f  lea     rcx, [rbp+90h+var_D0]
0x18000ed53  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000ed58  nop
0x18000ed59  test    rdi, rdi
0x18000ed5c  jnz     short loc_18000ED66
0x18000ed5e  mov     [rsi], r14
0x18000ed61  jmp     loc_18000EE10
0x18000ed66  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ed6a  mov     rcx, rbx
0x18000ed6d  inc     rcx
0x18000ed70  cmp     [rdi+rcx*2], r14w
0x18000ed75  jnz     short loc_18000ED6D
0x18000ed77  lea     rcx, ds:2[rcx*2]; cb
0x18000ed7f  call    cs:__imp_CoTaskMemAlloc
0x18000ed85  mov     r8, rax
0x18000ed88  mov     [rsi], rax
0x18000ed8b  mov     ecx, [rbp+90h+var_C8]
0x18000ed8e  mov     [rbp+90h+var_C8], ecx
0x18000ed91  test    rax, rax
0x18000ed94  jz      loc_18000EE48
0x18000ed9a  mov     [rbp+90h+var_C8], r14d
0x18000ed9e  inc     rbx
0x18000eda1  cmp     [rdi+rbx*2], r14w
0x18000eda6  jnz     short loc_18000ED9E
0x18000eda8  lea     rdx, [rbx+1]
0x18000edac  mov     ecx, 80070057h
0x18000edb1  test    rdx, rdx
0x18000edb4  jz      short loc_18000EE06
0x18000edb6  cmp     rdx, 7FFFFFFFh
0x18000edbd  ja      loc_18000EE73
0x18000edc3  mov     eax, 7FFFFFFEh
0x18000edc8  test    rax, rax
0x18000edcb  jz      short loc_18000EDEA
0x18000edcd  movzx   ecx, word ptr [rdi]
0x18000edd0  test    cx, cx
0x18000edd3  jz      short loc_18000EDEA
0x18000edd5  add     rdi, 2
0x18000edd9  mov     [r8], cx
0x18000eddd  add     r8, 2
0x18000ede1  dec     rax
0x18000ede4  sub     rdx, 1
0x18000ede8  jnz     short loc_18000EDC8
0x18000edea  lea     rcx, [r8-2]
0x18000edee  test    rdx, rdx
0x18000edf1  cmovnz  rcx, r8
0x18000edf5  mov     [rcx], r14w
0x18000edf9  neg     rdx
0x18000edfc  sbb     ecx, ecx
0x18000edfe  not     ecx
0x18000ee00  and     ecx, 8007007Ah
0x18000ee06  mov     [rbp+90h+var_C8], ecx
0x18000ee09  test    ecx, ecx
0x18000ee0b  js      short loc_18000EE7A
0x18000ee0d  mov     [rbp+90h+var_C8], ecx
0x18000ee10  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000ee17  mov     [rbp+90h+var_D0], rax
0x18000ee1b  lea     rcx, [rbp+90h+var_D0]; this
0x18000ee1f  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000ee24  mov     rcx, [rbp+90h+var_20]
0x18000ee28  xor     rcx, rsp; StackCookie
0x18000ee2b  call    __security_check_cookie
0x18000ee30  lea     r11, [rsp+190h+var_10]
0x18000ee38  mov     rbx, [r11+30h]
0x18000ee3c  mov     rsi, [r11+38h]
0x18000ee40  mov     rsp, r11
0x18000ee43  pop     r14
0x18000ee45  pop     rdi
0x18000ee46  pop     rbp
0x18000ee47  retn
0x18000ee48  mov     edx, 8007000Eh; int
0x18000ee4d  lea     rcx, [rbp+90h+var_D0]; this
0x18000ee51  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000ee56  lea     rcx, [rbp+90h+var_D0]; this
0x18000ee5a  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000ee5f  mov     r8d, eax; char
0x18000ee62  xor     r9d, r9d; unsigned __int16 *
0x18000ee65  lea     edx, [r9+57h]; unsigned int
0x18000ee69  lea     rcx, [rbp+90h+var_D0]; this
0x18000ee6d  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000ee73  mov     [rax], r14w
0x18000ee77  mov     [rbp+90h+var_C8], ecx
0x18000ee7a  lea     rcx, [rbp+90h+var_D0]; this
0x18000ee7e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000ee83  mov     edx, eax; int
0x18000ee85  lea     rcx, [rbp+90h+var_D0]; this
0x18000ee89  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000ee8e  lea     rcx, [rbp+90h+var_D0]; this
0x18000ee92  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000ee97  mov     r8d, eax; char
0x18000ee9a  xor     r9d, r9d; unsigned __int16 *
0x18000ee9d  lea     edx, [r9+59h]; unsigned int
0x18000eea1  lea     rcx, [rbp+90h+var_D0]; this
0x18000eea5  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
