# CTpSrvDataState::AdjustTargetWindowSize(int)

- ea: `0x18001288c`
- end: `0x180012a59`
- name: `?AdjustTargetWindowSize@CTpSrvDataState@@AEAAXH@Z`
- size: `461`
- prototype: `void __fastcall(CTpSrvDataState *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800126a8`

## callees

- `0x18001288c`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180012942`
- `KERNEL32!LeaveCriticalSection` at `0x180012942`
- `KERNEL32!LeaveCriticalSection` at `0x180012a52`
- `KERNEL32!EnterCriticalSection` at `0x1800128b1`
- `KERNEL32!EnterCriticalSection` at `0x180012925`
- `KERNEL32!EnterCriticalSection` at `0x1800128b1`
- `KERNEL32!EnterCriticalSection` at `0x180012925`

## string_xrefs

- `0x180012a28`: `WDSMCTP[0x%x] Target Window Size=%u, BW=%u, Bandwidth=%I64u LinkRTT=%f Packet=%u, Link=%f`

## pseudocode

```c
void __fastcall CTpSrvDataState::AdjustTargetWindowSize(CTpSrvDataState *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  int v5; // eax
  bool v6; // zf
  unsigned __int32 v7; // esi
  __int64 v8; // rbx
  int v9; // ebp
  __int64 v10; // rax
  int v11; // ebp
  double v12; // xmm2_8
  unsigned int *v13; // rdx
  double v14; // xmm2_8
  unsigned int v15; // ecx
  unsigned int v16; // eax
  unsigned int v17; // edx
  int v18; // eax
  unsigned int v19; // ecx
  __int64 v20; // r8

  v2 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
  EnterCriticalSection(v2);
  if ( a2 )
  {
    v5 = 2;
    if ( *((_DWORD *)this + 119) >> 1 > 2u )
      v5 = *((_DWORD *)this + 119) >> 1;
    v6 = g_ErrLibTraceFunctionEx == 0;
    *((_DWORD *)this + 119) = v5;
    if ( !v6 )
    {
      v7 = _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 2) + 2216LL), 0);
      g_ErrLibTraceFunctionEx(
        0x10000u,
        L"WDSMCTP[0x%x] Target Window Size Decreased=%u BW=%u",
        v7,
        *((unsigned int *)this + 119),
        *((_DWORD *)this + 120));
    }
  }
  else
  {
    v8 = *((_QWORD *)this + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)v8);
    if ( *(_DWORD *)(v8 + 64) == 16 )
      v9 = *(_DWORD *)(v8 + 2404);
    else
      v9 = *(_DWORD *)(v8 + 2400);
    LeaveCriticalSection((LPCRITICAL_SECTION)v8);
    v10 = *((_QWORD *)this + 73);
    v11 = v9 + 57;
    v12 = (double)(int)v10;
    if ( v10 < 0 )
      v12 = v12 + 1.844674407370955e19;
    v13 = (unsigned int *)*((_QWORD *)this + 3);
    v14 = v12 * *((double *)this + 64) / 1000.0;
    v15 = *v13;
    v16 = (int)(v14 / (double)v11);
    if ( v16 >= *v13 )
    {
      v15 = v13[1];
      if ( v16 <= v15 )
        v15 = (int)(v14 / (double)v11);
    }
    v17 = *((_DWORD *)this + 119);
    *((_DWORD *)this + 120) = v15;
    if ( v17 <= v15 )
    {
      if ( v17 < v15 )
      {
        v18 = 1;
        v19 = (v15 - v17) >> 1;
        if ( v19 )
          v18 = v19;
        *((_DWORD *)this + 119) = v17 + v18;
      }
    }
    else
    {
      *((_DWORD *)this + 119) = v15;
    }
    if ( g_ErrLibTraceFunctionEx )
    {
      v20 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 2) + 2216LL), 0);
      g_ErrLibTraceFunctionEx(
        0x10000u,
        L"WDSMCTP[0x%x] Target Window Size=%u, BW=%u, Bandwidth=%I64u LinkRTT=%f Packet=%u, Link=%f",
        v20,
        *((unsigned int *)this + 119),
        *((_DWORD *)this + 120),
        *((_QWORD *)this + 73),
        *((_QWORD *)this + 64),
        v11,
        v14);
    }
  }
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x18001288c  mov     rax, rsp
0x18001288f  mov     [rax+8], rbx
0x180012893  mov     [rax+10h], rbp
0x180012897  mov     [rax+18h], rsi
0x18001289b  mov     [rax+20h], rdi
0x18001289f  push    r14
0x1800128a1  sub     rsp, 50h
0x1800128a5  mov     r14, [rcx+8]
0x1800128a9  mov     rdi, rcx
0x1800128ac  mov     rcx, r14; lpCriticalSection
0x1800128af  mov     ebx, edx
0x1800128b1  call    cs:__imp_EnterCriticalSection
0x1800128b7  xor     esi, esi
0x1800128b9  test    ebx, ebx
0x1800128bb  jz      short loc_18001291E
0x1800128bd  mov     edx, [rdi+1DCh]
0x1800128c3  lea     eax, [rsi+2]
0x1800128c6  shr     edx, 1
0x1800128c8  cmp     edx, eax
0x1800128ca  cmova   eax, edx
0x1800128cd  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rsi; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800128d4  mov     [rdi+1DCh], eax
0x1800128da  jz      loc_180012A35
0x1800128e0  mov     rax, [rdi+10h]
0x1800128e4  lock xadd [rax+8A8h], esi
0x1800128ec  mov     ecx, [rdi+1E0h]
0x1800128f2  lea     rdx, aWdsmctp0xXTarg; "WDSMCTP[0x%x] Target Window Size Decrea"...
0x1800128f9  mov     r9d, [rdi+1DCh]
0x180012900  mov     r8d, esi
0x180012903  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001290a  mov     [rsp+58h+var_38], ecx
0x18001290e  mov     ecx, 10000h
0x180012913  call    cs:__guard_dispatch_icall_fptr
0x180012919  jmp     loc_180012A35
0x18001291e  mov     rbx, [rdi+10h]
0x180012922  mov     rcx, rbx; lpCriticalSection
0x180012925  call    cs:__imp_EnterCriticalSection
0x18001292b  cmp     dword ptr [rbx+40h], 10h
0x18001292f  jnz     short loc_180012939
0x180012931  mov     ebp, [rbx+964h]
0x180012937  jmp     short loc_18001293F
0x180012939  mov     ebp, [rbx+960h]
0x18001293f  mov     rcx, rbx; lpCriticalSection
0x180012942  call    cs:__imp_LeaveCriticalSection
0x180012948  mov     rax, [rdi+248h]
0x18001294f  add     ebp, 39h ; '9'
0x180012952  xorps   xmm2, xmm2
0x180012955  cvtsi2sd xmm2, rax
0x18001295a  test    rax, rax
0x18001295d  jns     short loc_180012967
0x18001295f  addsd   xmm2, cs:__real@43f0000000000000
0x180012967  mulsd   xmm2, qword ptr [rdi+200h]
0x18001296f  xorps   xmm0, xmm0
0x180012972  mov     rdx, [rdi+18h]
0x180012976  mov     eax, ebp
0x180012978  divsd   xmm2, cs:__real@408f400000000000
0x180012980  mov     ecx, [rdx]
0x180012982  cvtsi2sd xmm0, rax
0x180012987  movaps  xmm1, xmm2
0x18001298a  divsd   xmm1, xmm0
0x18001298e  cvttsd2si rax, xmm1
0x180012993  cmp     eax, ecx
0x180012995  jb      short loc_18001299F
0x180012997  mov     ecx, [rdx+4]
0x18001299a  cmp     eax, ecx
0x18001299c  cmovbe  ecx, eax
0x18001299f  mov     edx, [rdi+1DCh]
0x1800129a5  mov     [rdi+1E0h], ecx
0x1800129ab  cmp     edx, ecx
0x1800129ad  jbe     short loc_1800129B7
0x1800129af  mov     [rdi+1DCh], ecx
0x1800129b5  jmp     short loc_1800129CF
0x1800129b7  jnb     short loc_1800129CF
0x1800129b9  sub     ecx, edx
0x1800129bb  mov     eax, 1
0x1800129c0  shr     ecx, 1
0x1800129c2  cmp     ecx, eax
0x1800129c4  cmovnb  eax, ecx
0x1800129c7  add     eax, edx
0x1800129c9  mov     [rdi+1DCh], eax
0x1800129cf  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rsi; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800129d6  jz      short loc_180012A35
0x1800129d8  mov     rax, [rdi+10h]
0x1800129dc  lock xadd [rax+8A8h], esi
0x1800129e4  mov     rdx, [rdi+248h]
0x1800129eb  mov     r8d, esi
0x1800129ee  movsd   xmm0, qword ptr [rdi+200h]
0x1800129f6  mov     ecx, 10000h
0x1800129fb  mov     r9d, [rdi+1DCh]
0x180012a02  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180012a09  movsd   [rsp+58h+var_18], xmm2
0x180012a0f  mov     [rsp+58h+var_20], ebp
0x180012a13  movsd   [rsp+58h+var_28], xmm0
0x180012a19  mov     [rsp+58h+var_30], rdx
0x180012a1e  mov     edx, [rdi+1E0h]
0x180012a24  mov     [rsp+58h+var_38], edx
0x180012a28  lea     rdx, aWdsmctp0xXTarg_0; "WDSMCTP[0x%x] Target Window Size=%u, BW"...
0x180012a2f  call    cs:__guard_dispatch_icall_fptr
0x180012a35  mov     rcx, r14
0x180012a38  mov     rbx, [rsp+58h+arg_0]
0x180012a3d  mov     rbp, [rsp+58h+arg_8]
0x180012a42  mov     rsi, [rsp+58h+arg_10]
0x180012a47  mov     rdi, [rsp+58h+arg_18]
0x180012a4c  add     rsp, 50h
0x180012a50  pop     r14
0x180012a52  jmp     cs:__imp_LeaveCriticalSection
```
