# CMulticastSessionGroup::UpdateBandwidth(unsigned __int64)

- ea: `0x180019ea0`
- end: `0x18001a50b`
- name: `?UpdateBandwidth@CMulticastSessionGroup@@QEAAX_K@Z`
- size: `1643`
- prototype: `void __fastcall(CMulticastSessionGroup *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001853c`
- `0x180019a3c`
- `0x18001a514`

## callees

- `0x180019ea0`
- `0x1800227d4`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001a3f8`
- `KERNEL32!LeaveCriticalSection` at `0x18001a4ae`
- `KERNEL32!LeaveCriticalSection` at `0x18001a4b9`
- `KERNEL32!LeaveCriticalSection` at `0x18001a4c2`
- `KERNEL32!LeaveCriticalSection` at `0x18001a3f8`
- `KERNEL32!LeaveCriticalSection` at `0x18001a4ae`
- `KERNEL32!LeaveCriticalSection` at `0x18001a4b9`
- `KERNEL32!LeaveCriticalSection` at `0x18001a4c2`
- `KERNEL32!LeaveCriticalSection` at `0x18001a504`
- `KERNEL32!EnterCriticalSection` at `0x180019eba`
- `KERNEL32!EnterCriticalSection` at `0x18001a39f`
- `KERNEL32!EnterCriticalSection` at `0x18001a3c9`
- `KERNEL32!EnterCriticalSection` at `0x18001a3d9`
- `KERNEL32!EnterCriticalSection` at `0x18001a492`
- `KERNEL32!EnterCriticalSection` at `0x180019eba`
- `KERNEL32!EnterCriticalSection` at `0x18001a39f`
- `KERNEL32!EnterCriticalSection` at `0x18001a3c9`
- `KERNEL32!EnterCriticalSection` at `0x18001a3d9`
- `KERNEL32!EnterCriticalSection` at `0x18001a492`

## string_xrefs

- `0x18001a468`: `WDSMCTP[0x%x] Bandwidth allocated: %I64uBps, Cache Size=%u`

## pseudocode

```c
void __fastcall CMulticastSessionGroup::UpdateBandwidth(
        struct _RTL_CRITICAL_SECTION *this,
        struct _RTL_CRITICAL_SECTION_DEBUG *a2)
{
  int v4; // r9d
  int SpinCount; // ecx
  int v6; // ecx
  int v7; // ecx
  unsigned int v8; // eax
  _QWORD *LockSemaphore; // rbp
  _QWORD *v10; // rcx
  unsigned int v11; // eax
  _QWORD *v12; // rbp
  _QWORD *v13; // rdx
  unsigned int v14; // eax
  _QWORD *v15; // rbp
  _QWORD *v16; // rcx
  unsigned int i; // ebp
  unsigned int v18; // ecx
  _QWORD *v19; // r9
  char *v20; // r14
  _QWORD *v21; // r14
  int v22; // r15d
  int v23; // r15d
  unsigned int v24; // eax
  char *v25; // r13
  char *v26; // r12
  __int64 v27; // r14
  unsigned __int64 v28; // r12
  __int64 v29; // rbx
  int v30; // r13d
  unsigned __int64 v31; // rdx
  int v32; // eax
  bool v33; // zf
  __int64 v34; // r8
  struct _RTL_CRITICAL_SECTION *v35; // rbx
  int v36[2]; // [rsp+20h] [rbp-48h]
  __int64 v37; // [rsp+70h] [rbp+8h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+78h] [rbp+10h]

  EnterCriticalSection(this);
  SpinCount = this[7].SpinCount;
  this[7].DebugInfo = a2;
  v6 = SpinCount - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        if ( !LODWORD(this[7].SpinCount) )
          WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
        *((_QWORD *)this[7].LockSemaphore + 2) = 0;
        if ( !LODWORD(this[7].SpinCount) )
          WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
        *((_QWORD *)this[7].LockSemaphore + 1) = (unsigned __int64)this[7].DebugInfo / 0x64;
        v8 = this[7].SpinCount;
        if ( !v8 )
        {
          WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
          v8 = this[7].SpinCount;
        }
        LockSemaphore = this[7].LockSemaphore;
        v10 = LockSemaphore;
        if ( v8 <= 1 )
        {
          WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
          v10 = this[7].LockSemaphore;
        }
        v10[5] = LockSemaphore[1];
        if ( LODWORD(this[7].SpinCount) <= 1 )
          WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
        *((_QWORD *)this[7].LockSemaphore + 4) = 10 * (__int64)this[7].DebugInfo / 0x64uLL;
        v11 = this[7].SpinCount;
        if ( v11 <= 1 )
        {
          WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
          v11 = this[7].SpinCount;
        }
        v12 = this[7].LockSemaphore;
        v13 = v12;
        if ( v11 <= 2 )
        {
          WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
          v13 = this[7].LockSemaphore;
        }
        v13[8] = v12[4];
        if ( LODWORD(this[7].SpinCount) <= 2 )
          WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
        *((_QWORD *)this[7].LockSemaphore + 7) = 89 * (__int64)this[7].DebugInfo / 0x64uLL;
      }
      else
      {
        WdsAssert("base\\eco\\wds\\transport\\server\\mc\\mcsessiongroup.cpp", 0x34Fu, "0", v4, 0);
      }
    }
    else
    {
      if ( !LODWORD(this[7].SpinCount) )
        WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
      *((_QWORD *)this[7].LockSemaphore + 2) = 0;
      if ( !LODWORD(this[7].SpinCount) )
        WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
      *((_QWORD *)this[7].LockSemaphore + 1) = 5 * (__int64)this[7].DebugInfo / 0x64uLL;
      v14 = this[7].SpinCount;
      if ( !v14 )
      {
        WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
        v14 = this[7].SpinCount;
      }
      v15 = this[7].LockSemaphore;
      v16 = v15;
      if ( v14 <= 1 )
      {
        WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
        v16 = this[7].LockSemaphore;
      }
      v16[5] = v15[1];
      if ( LODWORD(this[7].SpinCount) <= 1 )
        WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
      *((_QWORD *)this[7].LockSemaphore + 4) = 95 * (__int64)this[7].DebugInfo / 0x64uLL;
    }
  }
  else
  {
    if ( !LODWORD(this[7].SpinCount) )
      WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
    *((_QWORD *)this[7].LockSemaphore + 2) = 0;
    if ( !LODWORD(this[7].SpinCount) )
      WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
    *((_QWORD *)this[7].LockSemaphore + 1) = this[7].DebugInfo;
  }
  for ( i = 0; i < LODWORD(this[7].SpinCount); ++i )
  {
    if ( g_ErrLibTraceFunction )
    {
      v18 = this[7].SpinCount;
      if ( i >= v18 )
      {
        WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
        v18 = this[7].SpinCount;
      }
      v19 = this[7].LockSemaphore;
      v20 = (char *)&v19[3 * i];
      if ( i >= v18 )
      {
        WdsAssert(
          "internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h",
          0x4Au,
          "uIndex < m_uCount",
          (int)v19,
          0);
        v19 = this[7].LockSemaphore;
      }
      g_ErrLibTraceFunction(
        L"MCSG[0x%x] Session %u, LowBw=%I64u, Bw=%I64u",
        LODWORD(this[1].DebugInfo),
        i,
        v19[3 * i + 2],
        *((_QWORD *)v20 + 1));
    }
    if ( i >= LODWORD(this[7].SpinCount) )
      WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
    v21 = this[7].LockSemaphore;
    if ( v21[3 * i] )
    {
      v22 = (i == 0) | 2;
      if ( i + 1 != LODWORD(this[7].SpinCount) )
        v22 = i == 0;
      v23 = (i << 8) | v22;
      v24 = this[7].SpinCount;
      if ( i >= v24 )
      {
        WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
        v24 = this[7].SpinCount;
        v21 = this[7].LockSemaphore;
      }
      v25 = (char *)&v21[3 * i];
      if ( i >= v24 )
      {
        WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
        v24 = this[7].SpinCount;
        v21 = this[7].LockSemaphore;
      }
      v26 = (char *)&v21[3 * i];
      if ( i >= v24 )
      {
        WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\StaticArray.h", 0x4Au, "uIndex < m_uCount", v4, 0);
        v21 = this[7].LockSemaphore;
      }
      v27 = v21[3 * i] + 312LL;
      v28 = *((_QWORD *)v26 + 1);
      v37 = *((_QWORD *)v25 + 2);
      EnterCriticalSection((LPCRITICAL_SECTION)v27);
      *(_QWORD *)(v27 + 14264) = v28;
      *(_QWORD *)(v27 + 14256) = v37;
      *(_DWORD *)(v27 + 14272) = v23;
      lpCriticalSection = *(struct _RTL_CRITICAL_SECTION **)(v27 + 13456);
      EnterCriticalSection(lpCriticalSection);
      v29 = *(_QWORD *)(v27 + 13464);
      EnterCriticalSection((LPCRITICAL_SECTION)v29);
      if ( *(_DWORD *)(v29 + 64) == 16 )
        v30 = *(_DWORD *)(v29 + 2404);
      else
        v30 = *(_DWORD *)(v29 + 2400);
      LeaveCriticalSection((LPCRITICAL_SECTION)v29);
      *(_QWORD *)(v27 + 14032) = v28;
      LODWORD(v31) = -1;
      if ( v28 / (unsigned int)(v30 + 57) < 0xFFFFFFFF )
        v31 = v28 / (unsigned int)(v30 + 57);
      v32 = v31;
      if ( (unsigned int)v31 >= *(_DWORD *)(v27 + 14004) )
        v32 = *(_DWORD *)(v27 + 14004);
      *(_DWORD *)(v27 + 14004) = v32;
      if ( !(_DWORD)v31 )
        LODWORD(v31) = 1;
      v33 = g_ErrLibTraceFunctionEx == 0;
      *(_DWORD *)(v27 + 14000) = v31;
      if ( !v33 )
      {
        v34 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(v27 + 13464) + 2216LL), 0);
        v36[0] = *(_DWORD *)(v27 + 14000);
        g_ErrLibTraceFunctionEx(
          0x10000u,
          L"WDSMCTP[0x%x] Bandwidth allocated: %I64uBps, Cache Size=%u",
          v34,
          v28,
          *(_QWORD *)v36);
      }
      v35 = *(struct _RTL_CRITICAL_SECTION **)(v27 + 13640);
      EnterCriticalSection(v35);
      *(_QWORD *)(v27 + 13744) = v37;
      *(_DWORD *)(v27 + 13752) = v23;
      LeaveCriticalSection(v35);
      LeaveCriticalSection(lpCriticalSection);
      LeaveCriticalSection((LPCRITICAL_SECTION)v27);
    }
  }
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x180019ea0  mov     [rsp+arg_10], rbx
0x180019ea5  push    rbp
0x180019ea6  push    rsi
0x180019ea7  push    rdi
0x180019ea8  push    r12
0x180019eaa  push    r13
0x180019eac  push    r14
0x180019eae  push    r15
0x180019eb0  sub     rsp, 30h
0x180019eb4  mov     rbx, rdx
0x180019eb7  mov     rdi, rcx
0x180019eba  call    cs:__imp_EnterCriticalSection
0x180019ec0  mov     ecx, [rdi+138h]
0x180019ec6  lea     r12, aUindexMUcount; "uIndex < m_uCount"
0x180019ecd  mov     r13d, 4Ah ; 'J'
0x180019ed3  mov     [rdi+118h], rbx
0x180019eda  lea     r15, aInternalOnecor_1; "internal\\onecorebase\\private\\inc\\ec"...
0x180019ee1  lea     r14d, [r13-49h]
0x180019ee5  sub     ecx, r14d
0x180019ee8  jz      loc_18001A1C8
0x180019eee  sub     ecx, r14d
0x180019ef1  jz      loc_18001A0BF
0x180019ef7  xor     esi, esi
0x180019ef9  cmp     ecx, r14d
0x180019efc  jz      short loc_180019F1F
0x180019efe  lea     r8, a0; "0"
0x180019f05  mov     [rsp+68h+var_48], esi; int
0x180019f09  mov     edx, 34Fh; unsigned int
0x180019f0e  lea     rcx, aBaseEcoWdsTran_12; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180019f15  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180019f1a  jmp     loc_18001A21B
0x180019f1f  cmp     [rdi+138h], esi
0x180019f25  ja      short loc_180019F39
0x180019f27  mov     r8, r12; char *
0x180019f2a  mov     [rsp+68h+var_48], esi; int
0x180019f2e  mov     edx, r13d; unsigned int
0x180019f31  mov     rcx, r15; char *
0x180019f34  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180019f39  mov     rax, [rdi+130h]
0x180019f40  mov     [rax+10h], rsi
0x180019f44  cmp     [rdi+138h], esi
0x180019f4a  ja      short loc_180019F5E
0x180019f4c  mov     r8, r12; char *
0x180019f4f  mov     [rsp+68h+var_48], esi; int
0x180019f53  mov     edx, r13d; unsigned int
0x180019f56  mov     rcx, r15; char *
0x180019f59  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180019f5e  mov     rcx, [rdi+118h]
0x180019f65  mov     rbx, 47AE147AE147AE15h
0x180019f6f  mov     rax, rbx
0x180019f72  mul     rcx
0x180019f75  mov     rax, [rdi+130h]
0x180019f7c  sub     rcx, rdx
0x180019f7f  shr     rcx, 1
0x180019f82  add     rcx, rdx
0x180019f85  shr     rcx, 6
0x180019f89  mov     [rax+8], rcx
0x180019f8d  mov     eax, [rdi+138h]
0x180019f93  test    eax, eax
0x180019f95  jnz     short loc_180019FAF
0x180019f97  mov     r8, r12; char *
0x180019f9a  mov     [rsp+68h+var_48], esi; int
0x180019f9e  mov     edx, r13d; unsigned int
0x180019fa1  mov     rcx, r15; char *
0x180019fa4  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180019fa9  mov     eax, [rdi+138h]
0x180019faf  mov     rbp, [rdi+130h]
0x180019fb6  mov     rcx, rbp
0x180019fb9  cmp     eax, r14d
0x180019fbc  ja      short loc_180019FD7
0x180019fbe  mov     r8, r12; char *
0x180019fc1  mov     [rsp+68h+var_48], esi; int
0x180019fc5  mov     edx, r13d; unsigned int
0x180019fc8  mov     rcx, r15; char *
0x180019fcb  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180019fd0  mov     rcx, [rdi+130h]
0x180019fd7  mov     rax, [rbp+8]
0x180019fdb  mov     [rcx+28h], rax
0x180019fdf  cmp     [rdi+138h], r14d
0x180019fe6  ja      short loc_180019FFA
0x180019fe8  mov     r8, r12; char *
0x180019feb  mov     [rsp+68h+var_48], esi; int
0x180019fef  mov     edx, r13d; unsigned int
0x180019ff2  mov     rcx, r15; char *
0x180019ff5  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180019ffa  mov     rax, [rdi+118h]
0x18001a001  lea     rcx, [rax+rax*4]
0x18001a005  mov     rax, rbx
0x18001a008  add     rcx, rcx
0x18001a00b  mul     rcx
0x18001a00e  mov     rax, [rdi+130h]
0x18001a015  sub     rcx, rdx
0x18001a018  shr     rcx, 1
0x18001a01b  add     rcx, rdx
0x18001a01e  shr     rcx, 6
0x18001a022  mov     [rax+20h], rcx
0x18001a026  mov     eax, [rdi+138h]
0x18001a02c  cmp     eax, r14d
0x18001a02f  ja      short loc_18001A049
0x18001a031  mov     r8, r12; char *
0x18001a034  mov     [rsp+68h+var_48], esi; int
0x18001a038  mov     edx, r13d; unsigned int
0x18001a03b  mov     rcx, r15; char *
0x18001a03e  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a043  mov     eax, [rdi+138h]
0x18001a049  mov     rbp, [rdi+130h]
0x18001a050  mov     rdx, rbp
0x18001a053  cmp     eax, 2
0x18001a056  ja      short loc_18001A071
0x18001a058  mov     r8, r12; char *
0x18001a05b  mov     [rsp+68h+var_48], esi; int
0x18001a05f  mov     edx, r13d; unsigned int
0x18001a062  mov     rcx, r15; char *
0x18001a065  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a06a  mov     rdx, [rdi+130h]
0x18001a071  mov     rcx, [rbp+20h]
0x18001a075  mov     [rdx+40h], rcx
0x18001a079  cmp     dword ptr [rdi+138h], 2
0x18001a080  ja      short loc_18001A094
0x18001a082  mov     r8, r12; char *
0x18001a085  mov     [rsp+68h+var_48], esi; int
0x18001a089  mov     edx, r13d; unsigned int
0x18001a08c  mov     rcx, r15; char *
0x18001a08f  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a094  imul    rcx, [rdi+118h], 59h ; 'Y'
0x18001a09c  mov     rax, rbx
0x18001a09f  mul     rcx
0x18001a0a2  mov     rax, [rdi+130h]
0x18001a0a9  sub     rcx, rdx
0x18001a0ac  shr     rcx, 1
0x18001a0af  add     rcx, rdx
0x18001a0b2  shr     rcx, 6
0x18001a0b6  mov     [rax+38h], rcx
0x18001a0ba  jmp     loc_18001A21B
0x18001a0bf  xor     esi, esi
0x18001a0c1  cmp     [rdi+138h], esi
0x18001a0c7  ja      short loc_18001A0DB
0x18001a0c9  mov     r8, r12; char *
0x18001a0cc  mov     [rsp+68h+var_48], esi; int
0x18001a0d0  mov     edx, r13d; unsigned int
0x18001a0d3  mov     rcx, r15; char *
0x18001a0d6  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a0db  mov     rax, [rdi+130h]
0x18001a0e2  mov     [rax+10h], rsi
0x18001a0e6  cmp     [rdi+138h], esi
0x18001a0ec  ja      short loc_18001A100
0x18001a0ee  mov     r8, r12; char *
0x18001a0f1  mov     [rsp+68h+var_48], esi; int
0x18001a0f5  mov     edx, r13d; unsigned int
0x18001a0f8  mov     rcx, r15; char *
0x18001a0fb  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a100  mov     rax, [rdi+118h]
0x18001a107  mov     rbx, 47AE147AE147AE15h
0x18001a111  lea     rcx, [rax+rax*4]
0x18001a115  mov     rax, rbx
0x18001a118  mul     rcx
0x18001a11b  mov     rax, [rdi+130h]
0x18001a122  sub     rcx, rdx
0x18001a125  shr     rcx, 1
0x18001a128  add     rcx, rdx
0x18001a12b  shr     rcx, 6
0x18001a12f  mov     [rax+8], rcx
0x18001a133  mov     eax, [rdi+138h]
0x18001a139  test    eax, eax
0x18001a13b  jnz     short loc_18001A155
0x18001a13d  mov     r8, r12; char *
0x18001a140  mov     [rsp+68h+var_48], esi; int
0x18001a144  mov     edx, r13d; unsigned int
0x18001a147  mov     rcx, r15; char *
0x18001a14a  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a14f  mov     eax, [rdi+138h]
0x18001a155  mov     rbp, [rdi+130h]
0x18001a15c  mov     rcx, rbp
0x18001a15f  cmp     eax, r14d
0x18001a162  ja      short loc_18001A17D
0x18001a164  mov     r8, r12; char *
0x18001a167  mov     [rsp+68h+var_48], esi; int
0x18001a16b  mov     edx, r13d; unsigned int
0x18001a16e  mov     rcx, r15; char *
0x18001a171  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a176  mov     rcx, [rdi+130h]
0x18001a17d  mov     rax, [rbp+8]
0x18001a181  mov     [rcx+28h], rax
0x18001a185  cmp     [rdi+138h], r14d
0x18001a18c  ja      short loc_18001A1A0
0x18001a18e  mov     r8, r12; char *
0x18001a191  mov     [rsp+68h+var_48], esi; int
0x18001a195  mov     edx, r13d; unsigned int
0x18001a198  mov     rcx, r15; char *
0x18001a19b  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a1a0  imul    rcx, [rdi+118h], 5Fh ; '_'
0x18001a1a8  mov     rax, rbx
0x18001a1ab  mul     rcx
0x18001a1ae  mov     rax, [rdi+130h]
0x18001a1b5  sub     rcx, rdx
0x18001a1b8  shr     rcx, 1
0x18001a1bb  add     rcx, rdx
0x18001a1be  shr     rcx, 6
0x18001a1c2  mov     [rax+20h], rcx
0x18001a1c6  jmp     short loc_18001A21B
0x18001a1c8  xor     esi, esi
0x18001a1ca  cmp     [rdi+138h], esi
0x18001a1d0  ja      short loc_18001A1E4
0x18001a1d2  mov     r8, r12; char *
0x18001a1d5  mov     [rsp+68h+var_48], esi; int
0x18001a1d9  mov     edx, r13d; unsigned int
0x18001a1dc  mov     rcx, r15; char *
0x18001a1df  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a1e4  mov     rax, [rdi+130h]
0x18001a1eb  mov     [rax+10h], rsi
0x18001a1ef  cmp     [rdi+138h], esi
0x18001a1f5  ja      short loc_18001A209
0x18001a1f7  mov     r8, r12; char *
0x18001a1fa  mov     [rsp+68h+var_48], esi; int
0x18001a1fe  mov     edx, r13d; unsigned int
0x18001a201  mov     rcx, r15; char *
0x18001a204  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a209  mov     rcx, [rdi+130h]
0x18001a210  mov     rax, [rdi+118h]
0x18001a217  mov     [rcx+8], rax
0x18001a21b  mov     ebp, esi
0x18001a21d  cmp     [rdi+138h], esi
0x18001a223  jbe     loc_18001A4EA
0x18001a229  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, rsi; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001a230  jz      short loc_18001A2AA
0x18001a232  mov     ecx, [rdi+138h]
0x18001a238  cmp     ebp, ecx
0x18001a23a  jb      short loc_18001A254
0x18001a23c  mov     r8, r12; char *
0x18001a23f  mov     [rsp+68h+var_48], esi; int
0x18001a243  mov     edx, r13d; unsigned int
0x18001a246  mov     rcx, r15; char *
0x18001a249  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a24e  mov     ecx, [rdi+138h]
0x18001a254  mov     r9, [rdi+130h]; int
0x18001a25b  mov     eax, ebp
0x18001a25d  lea     rbx, [rax+rax*2]
0x18001a261  lea     r14, [r9+rbx*8]
0x18001a265  cmp     ebp, ecx
0x18001a267  jb      short loc_18001A282
0x18001a269  mov     r8, r12; char *
0x18001a26c  mov     [rsp+68h+var_48], esi; int
0x18001a270  mov     edx, r13d; unsigned int
0x18001a273  mov     rcx, r15; char *
0x18001a276  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a27b  mov     r9, [rdi+130h]
0x18001a282  mov     rcx, [r14+8]
0x18001a286  mov     r8d, ebp
0x18001a289  mov     r9, [r9+rbx*8+10h]
0x18001a28e  mov     edx, [rdi+28h]
0x18001a291  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001a298  mov     qword ptr [rsp+68h+var_48], rcx
0x18001a29d  lea     rcx, aMcsg0xXSession; "MCSG[0x%x] Session %u, LowBw=%I64u, Bw="...
0x18001a2a4  call    cs:__guard_dispatch_icall_fptr
0x18001a2aa  cmp     ebp, [rdi+138h]
0x18001a2b0  jb      short loc_18001A2C4
0x18001a2b2  mov     r8, r12; char *
0x18001a2b5  mov     [rsp+68h+var_48], esi; int
0x18001a2b9  mov     edx, r13d; unsigned int
0x18001a2bc  mov     rcx, r15; char *
0x18001a2bf  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a2c4  mov     r14, [rdi+130h]
0x18001a2cb  mov     eax, ebp
0x18001a2cd  lea     rbx, [rax+rax*2]
0x18001a2d1  cmp     [r14+rbx*8], rsi
0x18001a2d5  jz      loc_18001A4DC
0x18001a2db  test    ebp, ebp
0x18001a2dd  lea     eax, [rbp+1]
0x18001a2e0  mov     ecx, esi
0x18001a2e2  setz    cl
0x18001a2e5  mov     r15d, ecx
0x18001a2e8  or      r15d, 2
0x18001a2ec  cmp     eax, [rdi+138h]
0x18001a2f2  mov     eax, ebp
0x18001a2f4  cmovnz  r15d, ecx
0x18001a2f8  shl     eax, 8
0x18001a2fb  or      r15d, eax
0x18001a2fe  mov     eax, [rdi+138h]
0x18001a304  cmp     ebp, eax
0x18001a306  jb      short loc_18001A32B
0x18001a308  mov     r8, r12; char *
0x18001a30b  mov     [rsp+68h+var_48], esi; int
0x18001a30f  mov     edx, r13d; unsigned int
0x18001a312  lea     rcx, aInternalOnecor_1; "internal\\onecorebase\\private\\inc\\ec"...
0x18001a319  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a31e  mov     eax, [rdi+138h]
0x18001a324  mov     r14, [rdi+130h]
0x18001a32b  lea     r13, [r14+rbx*8]
0x18001a32f  cmp     ebp, eax
0x18001a331  jb      short loc_18001A358
0x18001a333  mov     r8, r12; char *
0x18001a336  mov     [rsp+68h+var_48], esi; int
0x18001a33a  mov     edx, 4Ah ; 'J'; unsigned int
0x18001a33f  lea     rcx, aInternalOnecor_1; "internal\\onecorebase\\private\\inc\\ec"...
0x18001a346  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001a34b  mov     eax, [rdi+138h]
0x18001a351  mov     r14, [rdi+130h]
0x18001a358  lea     r12, [r14+rbx*8]
0x18001a35c  cmp     ebp, eax
0x18001a35e  jb      short loc_18001A383
  ... truncated ...
```
