# SetStringValue(HKEY__ *,ushort *,ushort *,IWbemClassObject *,StringType)

- ea: `0x1800136f0`
- end: `0x18001382f`
- name: `?SetStringValue@@YAJPEAUHKEY__@@PEAG1PEAUIWbemClassObject@@W4StringType@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800043c0`

## callees

- `0x180002e10`
- `0x1800136f0`
- `0x180017010`

## import_xrefs

- `wbemcomn!?SetExpandStr@Registry@@QEAAHPEBG0@Z` at `0x1800137f5`
- `wbemcomn!?SetExpandStr@Registry@@QEAAHPEBG0@Z` at `0x1800137f5`
- `wbemcomn!?SetStr@Registry@@QEAAHPEBG0@Z` at `0x1800137ed`
- `wbemcomn!?SetStr@Registry@@QEAAHPEBG0@Z` at `0x1800137ed`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18001381c`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18001381c`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180013714`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180013714`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013800`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013800`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800137ba`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800137ba`
- `OLEAUT32!__imp_VariantInit` at `0x18001373a`
- `OLEAUT32!__imp_VariantInit` at `0x18001373a`
- `OLEAUT32!__imp_VariantClear` at `0x18001377c`
- `OLEAUT32!__imp_VariantClear` at `0x180013811`
- `OLEAUT32!__imp_VariantClear` at `0x18001377c`
- `OLEAUT32!__imp_VariantClear` at `0x180013811`

## pseudocode

```c
__int64 __fastcall SetStringValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, __int64 a4, int a5)
{
  unsigned int v7; // ebx
  __int64 v8; // rcx
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  unsigned int v12; // eax
  VARIANTARG pvarg; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v15[20]; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v16; // [rsp+6Ch] [rbp-4h]

  Registry::Registry((Registry *)v15, a1, 2u, a2);
  v7 = v16;
  if ( !v16 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)a4 + 32LL))(
           a4,
           L"sValue",
           0,
           &pvarg,
           0,
           0);
    if ( !v7 )
    {
      if ( pvarg.vt == 8 )
      {
        v8 = -1;
        do
          ++v8;
        while ( *(_WORD *)(pvarg.llVal + 2 * v8) );
        v9 = 2 * (int)v8 + 2;
        v10 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v9, 2u));
        v11 = v10;
        if ( v10 )
        {
          StringCchCopyW(v10, v9, pvarg.bstrVal);
          v11[v9 - 1] = 0;
          if ( a5 )
            v12 = Registry::SetExpandStr((Registry *)v15, a3, v11);
          else
            v12 = Registry::SetStr((Registry *)v15, a3, v11);
          v7 = v12;
          CWin32DefaultArena::WbemMemFree(v11);
        }
        else
        {
          v7 = -2147217402;
        }
        VariantClear(&pvarg);
      }
      else
      {
        VariantClear(&pvarg);
        v7 = -2147217400;
      }
    }
  }
  Registry::~Registry((Registry *)v15);
  return v7;
}

```

## disassembly

```asm
0x1800136f0  push    rbp
0x1800136f2  push    rbx
0x1800136f3  push    rsi
0x1800136f4  push    rdi
0x1800136f5  push    r14
0x1800136f7  mov     rbp, rsp
0x1800136fa  sub     rsp, 70h
0x1800136fe  mov     rdi, r9
0x180013701  mov     rsi, r8
0x180013704  mov     r9, rdx
0x180013707  mov     r8d, 2
0x18001370d  mov     rdx, rcx
0x180013710  lea     rcx, [rbp+var_18]
0x180013714  call    cs:__imp_??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z; Registry::Registry(HKEY__ *,ulong,ushort const *)
0x18001371a  nop
0x18001371b  mov     ebx, [rbp+var_4]
0x18001371e  xor     r14d, r14d
0x180013721  test    ebx, ebx
0x180013723  jnz     loc_180013818
0x180013729  xorps   xmm0, xmm0
0x18001372c  xor     eax, eax
0x18001372e  movups  xmmword ptr [rbp+pvarg], xmm0
0x180013732  mov     qword ptr [rbp+pvarg+10h], rax
0x180013736  lea     rcx, [rbp+pvarg]; pvarg
0x18001373a  call    cs:__imp_VariantInit
0x180013740  mov     rax, [rdi]
0x180013743  mov     [rsp+70h+var_48], r14
0x180013748  mov     [rsp+70h+var_50], r14
0x18001374d  lea     r9, [rbp+pvarg]
0x180013751  xor     r8d, r8d
0x180013754  lea     rdx, aSvalue; "sValue"
0x18001375b  mov     rcx, rdi
0x18001375e  mov     rax, [rax+20h]
0x180013762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013767  mov     ebx, eax
0x180013769  test    eax, eax
0x18001376b  jnz     loc_180013818
0x180013771  cmp     word ptr [rbp+pvarg], 8
0x180013776  jz      short loc_18001378C
0x180013778  lea     rcx, [rbp+pvarg]; pvarg
0x18001377c  call    cs:__imp_VariantClear
0x180013782  mov     ebx, 80041008h
0x180013787  jmp     loc_180013818
0x18001378c  mov     rdx, qword ptr [rbp+pvarg+8]
0x180013790  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013794  mov     rcx, r8
0x180013797  inc     rcx
0x18001379a  cmp     [rdx+rcx*2], r14w
0x18001379f  jnz     short loc_180013797
0x1800137a1  lea     ecx, ds:2[rcx*2]
0x1800137a8  movsxd  rbx, ecx
0x1800137ab  mov     eax, 2
0x1800137b0  mul     rbx
0x1800137b3  cmovb   rax, r8
0x1800137b7  mov     rcx, rax
0x1800137ba  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800137c0  mov     rdi, rax
0x1800137c3  test    rax, rax
0x1800137c6  jz      short loc_180013808
0x1800137c8  mov     r8, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x1800137cc  mov     rdx, rbx; unsigned __int64
0x1800137cf  mov     rcx, rax; unsigned __int16 *
0x1800137d2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800137d7  mov     [rdi+rbx*2-2], r14w
0x1800137dd  mov     r8, rdi
0x1800137e0  mov     rdx, rsi
0x1800137e3  lea     rcx, [rbp+var_18]
0x1800137e7  cmp     [rbp+arg_20], r14d
0x1800137eb  jnz     short loc_1800137F5
0x1800137ed  call    cs:__imp_?SetStr@Registry@@QEAAHPEBG0@Z; Registry::SetStr(ushort const *,ushort const *)
0x1800137f3  jmp     short loc_1800137FB
0x1800137f5  call    cs:__imp_?SetExpandStr@Registry@@QEAAHPEBG0@Z; Registry::SetExpandStr(ushort const *,ushort const *)
0x1800137fb  mov     ebx, eax
0x1800137fd  mov     rcx, rdi
0x180013800  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013806  jmp     short loc_18001380D
0x180013808  mov     ebx, 80041006h
0x18001380d  lea     rcx, [rbp+pvarg]; pvarg
0x180013811  call    cs:__imp_VariantClear
0x180013817  nop
0x180013818  lea     rcx, [rbp+var_18]
0x18001381c  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180013822  mov     eax, ebx
0x180013824  add     rsp, 70h
0x180013828  pop     r14
0x18001382a  pop     rdi
0x18001382b  pop     rsi
0x18001382c  pop     rbx
0x18001382d  pop     rbp
0x18001382e  retn
```
