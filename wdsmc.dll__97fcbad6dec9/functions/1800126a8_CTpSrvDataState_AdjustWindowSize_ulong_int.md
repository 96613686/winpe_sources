# CTpSrvDataState::AdjustWindowSize(ulong,int)

- ea: `0x1800126a8`
- end: `0x180012886`
- name: `?AdjustWindowSize@CTpSrvDataState@@AEAAXKH@Z`
- size: `478`
- prototype: `void __fastcall(CTpSrvDataState *__hidden this, unsigned int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013620`
- `0x180013c10`

## callees

- `0x1800126a8`
- `0x18001288c`
- `0x1800247d4`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001287f`
- `KERNEL32!EnterCriticalSection` at `0x1800126d0`
- `KERNEL32!EnterCriticalSection` at `0x1800126d0`

## string_xrefs

- `0x180012781`: `Holding off window expansion until repairs are complete. McTrail#=%I64u, Lead=%I64u`

## pseudocode

```c
void __fastcall CTpSrvDataState::AdjustWindowSize(CTpSrvDataState *this, int a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r14
  unsigned int v7; // eax
  unsigned int v8; // ecx
  bool v9; // zf
  unsigned __int32 v10; // esi
  LONGLONG v11; // rax
  unsigned int *v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // ecx
  LONGLONG v15; // rax
  __int64 v16; // r8

  v3 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
  EnterCriticalSection(v3);
  if ( a3 )
  {
    CTpSrvDataState::AdjustTargetWindowSize(this, 1);
    v7 = 2;
    v8 = *((_DWORD *)this + 118) >> 1;
    if ( v8 >= 2 )
    {
      v7 = *((_DWORD *)this + 119);
      if ( v8 <= v7 )
        v7 = *((_DWORD *)this + 118) >> 1;
    }
    v9 = g_ErrLibTraceFunctionEx == 0;
    *((_DWORD *)this + 118) = v7;
    if ( !v9 )
    {
      v10 = _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 2) + 2216LL), 0);
      g_ErrLibTraceFunctionEx(
        0x10000u,
        L"WDSMCTP[0x%x] Loss Reported - New Window Size=%u, InFlight=%u",
        v10,
        *((unsigned int *)this + 118),
        *((_DWORD *)this + 121));
    }
    *((_DWORD *)this + 136) = 1;
  }
  else if ( *((_DWORD *)this + 136) && *((_QWORD *)this + 58) < *((_QWORD *)this + 57) )
  {
    if ( g_ErrLibTraceFunctionEx )
      g_ErrLibTraceFunctionEx(
        0x10000u,
        L"Holding off window expansion until repairs are complete. McTrail#=%I64u, Lead=%I64u");
  }
  else
  {
    *((_DWORD *)this + 136) = 0;
    if ( a2 )
    {
      v11 = CStopwatch::CurrentMs((CTpSrvDataState *)((char *)this + 648));
      v12 = (unsigned int *)*((_QWORD *)this + 3);
      if ( v11 - *((_QWORD *)this + 61) >= (unsigned __int64)v12[10] )
      {
        v13 = *((_DWORD *)this + 118);
        if ( v13 >= *v12 )
        {
          CTpSrvDataState::AdjustTargetWindowSize(this, 0);
          *((_DWORD *)this + 118) += a2;
          v14 = *((_DWORD *)this + 118);
          if ( v14 >= *((_DWORD *)this + 119) )
            v14 = *((_DWORD *)this + 119);
        }
        else
        {
          v14 = v13 + 2 * a2;
          *((_DWORD *)this + 118) = v14;
          if ( v14 >= *v12 )
            v14 = *v12;
        }
        *((_DWORD *)this + 118) = v14;
        v15 = CStopwatch::CurrentMs((CTpSrvDataState *)((char *)this + 648));
        v9 = g_ErrLibTraceFunctionEx == 0;
        *((_QWORD *)this + 61) = v15;
        if ( !v9 )
        {
          v16 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 2) + 2216LL), 0);
          g_ErrLibTraceFunctionEx(
            0x10000u,
            L"WDSMCTP[0x%x] New Window Size=%u, Target=%u, ACKed Packets=%u",
            v16,
            *((unsigned int *)this + 118),
            *((_DWORD *)this + 119),
            a2);
        }
      }
    }
  }
  LeaveCriticalSection(v3);
}

```

## disassembly

```asm
0x1800126a8  mov     rax, rsp
0x1800126ab  mov     [rax+8], rbx
0x1800126af  mov     [rax+10h], rbp
0x1800126b3  mov     [rax+18h], rsi
0x1800126b7  mov     [rax+20h], rdi
0x1800126bb  push    r14
0x1800126bd  sub     rsp, 40h
0x1800126c1  mov     r14, [rcx+8]
0x1800126c5  mov     rdi, rcx
0x1800126c8  mov     rcx, r14; lpCriticalSection
0x1800126cb  mov     ebx, r8d
0x1800126ce  mov     ebp, edx
0x1800126d0  call    cs:__imp_EnterCriticalSection
0x1800126d6  xor     esi, esi
0x1800126d8  test    ebx, ebx
0x1800126da  jz      short loc_180012756
0x1800126dc  lea     ebx, [rsi+1]
0x1800126df  mov     rcx, rdi; this
0x1800126e2  mov     edx, ebx; int
0x1800126e4  call    ?AdjustTargetWindowSize@CTpSrvDataState@@AEAAXH@Z; CTpSrvDataState::AdjustTargetWindowSize(int)
0x1800126e9  mov     ecx, [rdi+1D8h]
0x1800126ef  lea     eax, [rsi+2]
0x1800126f2  shr     ecx, 1
0x1800126f4  cmp     ecx, eax
0x1800126f6  jb      short loc_180012703
0x1800126f8  mov     eax, [rdi+1DCh]
0x1800126fe  cmp     ecx, eax
0x180012700  cmovbe  eax, ecx
0x180012703  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rsi; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001270a  mov     [rdi+1D8h], eax
0x180012710  jz      short loc_18001274B
0x180012712  mov     rax, [rdi+10h]
0x180012716  lock xadd [rax+8A8h], esi
0x18001271e  mov     ecx, [rdi+1E4h]
0x180012724  lea     rdx, aWdsmctp0xXLoss; "WDSMCTP[0x%x] Loss Reported - New Windo"...
0x18001272b  mov     r9d, [rdi+1D8h]
0x180012732  mov     r8d, esi
0x180012735  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001273c  mov     [rsp+48h+var_28], ecx
0x180012740  mov     ecx, 10000h
0x180012745  call    cs:__guard_dispatch_icall_fptr
0x18001274b  mov     [rdi+220h], ebx
0x180012751  jmp     loc_180012862
0x180012756  cmp     [rdi+220h], esi
0x18001275c  jz      short loc_180012798
0x18001275e  mov     r8, [rdi+1D0h]
0x180012765  mov     r9, [rdi+1C8h]
0x18001276c  cmp     r8, r9
0x18001276f  jnb     short loc_180012798
0x180012771  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180012778  test    rax, rax
0x18001277b  jz      loc_180012862
0x180012781  lea     rdx, aHoldingOffWind; "Holding off window expansion until repa"...
0x180012788  mov     ecx, 10000h
0x18001278d  call    cs:__guard_dispatch_icall_fptr
0x180012793  jmp     loc_180012862
0x180012798  mov     [rdi+220h], esi
0x18001279e  test    ebp, ebp
0x1800127a0  jz      loc_180012862
0x1800127a6  lea     rbx, [rdi+288h]
0x1800127ad  mov     rcx, rbx; this
0x1800127b0  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x1800127b5  mov     rdx, [rdi+18h]
0x1800127b9  sub     rax, [rdi+1E8h]
0x1800127c0  mov     ecx, [rdx+28h]
0x1800127c3  cmp     rax, rcx
0x1800127c6  jb      loc_180012862
0x1800127cc  mov     eax, [rdi+1D8h]
0x1800127d2  cmp     eax, [rdx]
0x1800127d4  jnb     short loc_1800127E6
0x1800127d6  lea     ecx, [rax+rbp*2]
0x1800127d9  mov     [rdi+1D8h], ecx
0x1800127df  cmp     ecx, [rdx]
0x1800127e1  cmovnb  ecx, [rdx]
0x1800127e4  jmp     short loc_180012807
0x1800127e6  xor     edx, edx; int
0x1800127e8  mov     rcx, rdi; this
0x1800127eb  call    ?AdjustTargetWindowSize@CTpSrvDataState@@AEAAXH@Z; CTpSrvDataState::AdjustTargetWindowSize(int)
0x1800127f0  add     [rdi+1D8h], ebp
0x1800127f6  mov     ecx, [rdi+1D8h]
0x1800127fc  mov     eax, [rdi+1DCh]
0x180012802  cmp     ecx, eax
0x180012804  cmovnb  ecx, eax
0x180012807  mov     [rdi+1D8h], ecx
0x18001280d  mov     rcx, rbx; this
0x180012810  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x180012815  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rsi; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001281c  mov     [rdi+1E8h], rax
0x180012823  jz      short loc_180012862
0x180012825  mov     rax, [rdi+10h]
0x180012829  lock xadd [rax+8A8h], esi
0x180012831  mov     edx, [rdi+1DCh]
0x180012837  mov     r8d, esi
0x18001283a  mov     r9d, [rdi+1D8h]
0x180012841  mov     ecx, 10000h
0x180012846  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001284d  mov     [rsp+48h+var_20], ebp
0x180012851  mov     [rsp+48h+var_28], edx
0x180012855  lea     rdx, aWdsmctp0xXNewW; "WDSMCTP[0x%x] New Window Size=%u, Targe"...
0x18001285c  call    cs:__guard_dispatch_icall_fptr
0x180012862  mov     rcx, r14
0x180012865  mov     rbx, [rsp+48h+arg_0]
0x18001286a  mov     rbp, [rsp+48h+arg_8]
0x18001286f  mov     rsi, [rsp+48h+arg_10]
0x180012874  mov     rdi, [rsp+48h+arg_18]
0x180012879  add     rsp, 40h
0x18001287d  pop     r14
0x18001287f  jmp     cs:__imp_LeaveCriticalSection
```
