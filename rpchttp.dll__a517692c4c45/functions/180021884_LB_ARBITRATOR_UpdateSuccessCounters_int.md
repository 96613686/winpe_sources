# LB_ARBITRATOR::UpdateSuccessCounters(int)

- ea: `0x180021884`
- end: `0x180021994`
- name: `?UpdateSuccessCounters@LB_ARBITRATOR@@AEAAXH@Z`
- size: `272`
- prototype: `void __fastcall(LB_ARBITRATOR *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180020c3c`

## callees

- `0x18000f074`
- `0x18002184c`
- `0x180021884`
- `0x180025010`

## pseudocode

```c
void __fastcall LB_ARBITRATOR::UpdateSuccessCounters(LB_ARBITRATOR *this, int a2)
{
  int v2; // edi
  __int64 v5; // r8
  unsigned int v6; // ecx
  __int64 v7; // rdx
  unsigned int v8; // edx
  volatile unsigned int *v9; // rcx

  v2 = 0;
  if ( *((_DWORD *)this + 12) )
  {
    v5 = *((_QWORD *)this + 3);
    v6 = 0;
    do
    {
      v7 = 184LL * v6;
      if ( *(_DWORD *)(v7 + v5 + 152) == 2 && *(_DWORD *)(v7 + v5 + 148) != 6 )
        ++v2;
      ++v6;
    }
    while ( v6 < *((_DWORD *)this + 12) );
  }
  (*(void (__fastcall **)(__int64, __int64, __int64))(*((_QWORD *)this + 13) + 56LL))(8, 1, 1);
  if ( !a2 )
    (*(void (__fastcall **)(__int64, __int64, __int64))(*((_QWORD *)this + 13) + 56LL))(9, 1, 1);
  (*(void (__fastcall **)(__int64, __int64, _QWORD))(*((_QWORD *)this + 13) + 56LL))(
    10,
    1,
    *((unsigned int *)this + 12));
  if ( *((_DWORD *)this + 12) != v2 )
    (*(void (__fastcall **)(__int64, __int64))(*((_QWORD *)this + 13) + 56LL))(11, 1);
  _InterlockedAdd64((volatile signed __int64 *)&g_TotalLBSCallsTried, *((int *)this + 12));
  _InterlockedAdd64((volatile signed __int64 *)&g_TotalLBSCallsSucceeded, v2);
  _InterlockedAdd64((volatile signed __int64 *)&g_TotalArbitrationsTried, 1u);
  if ( a2 )
  {
    _InterlockedAdd64((volatile signed __int64 *)&g_TotalArbitrationsSucceeded, 1u);
    if ( !(unsigned int)IsSqmEnabled() )
      return;
    v8 = 2105;
    v9 = &SQMArbitrationsSucceeded;
  }
  else
  {
    if ( !(unsigned int)IsSqmEnabled() )
      return;
    v8 = 2106;
    v9 = &SQMArbitrationsFailed;
  }
  UpdateDataPoint(v9, v8);
}

```

## disassembly

```asm
0x180021884  push    rbx
0x180021886  push    rbp
0x180021887  push    rsi
0x180021888  push    rdi
0x180021889  sub     rsp, 28h
0x18002188d  xor     edi, edi
0x18002188f  mov     esi, edx
0x180021891  mov     rbx, rcx
0x180021894  lea     ebp, [rdi+1]
0x180021897  cmp     [rcx+30h], edi
0x18002189a  jbe     short loc_1800218CA
0x18002189c  mov     r8, [rbx+18h]
0x1800218a0  xor     ecx, ecx
0x1800218a2  mov     eax, ecx
0x1800218a4  imul    rdx, rax, 0B8h
0x1800218ab  cmp     dword ptr [rdx+r8+98h], 2
0x1800218b4  jnz     short loc_1800218C3
0x1800218b6  cmp     dword ptr [rdx+r8+94h], 6
0x1800218bf  jz      short loc_1800218C3
0x1800218c1  add     edi, ebp
0x1800218c3  add     ecx, ebp
0x1800218c5  cmp     ecx, [rbx+30h]
0x1800218c8  jb      short loc_1800218A2
0x1800218ca  mov     rax, [rbx+68h]
0x1800218ce  mov     r8d, ebp
0x1800218d1  mov     edx, ebp
0x1800218d3  mov     ecx, 8
0x1800218d8  mov     rax, [rax+38h]
0x1800218dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218e1  test    esi, esi
0x1800218e3  jnz     short loc_1800218FA
0x1800218e5  mov     rax, [rbx+68h]
0x1800218e9  lea     ecx, [rsi+9]
0x1800218ec  mov     r8d, ebp
0x1800218ef  mov     edx, ebp
0x1800218f1  mov     rax, [rax+38h]
0x1800218f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218fa  mov     rax, [rbx+68h]
0x1800218fe  mov     edx, ebp
0x180021900  mov     r8d, [rbx+30h]
0x180021904  mov     ecx, 0Ah
0x180021909  mov     rax, [rax+38h]
0x18002190d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021912  mov     r8d, [rbx+30h]
0x180021916  sub     r8d, edi
0x180021919  jz      short loc_18002192F
0x18002191b  mov     rax, [rbx+68h]
0x18002191f  mov     edx, ebp
0x180021921  mov     ecx, 0Bh
0x180021926  mov     rax, [rax+38h]
0x18002192a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002192f  movsxd  rax, dword ptr [rbx+30h]
0x180021933  lock add cs:?g_TotalLBSCallsTried@@3_KA, rax; unsigned __int64 g_TotalLBSCallsTried
0x18002193b  movsxd  rax, edi
0x18002193e  lock add cs:?g_TotalLBSCallsSucceeded@@3_KA, rax; unsigned __int64 g_TotalLBSCallsSucceeded
0x180021946  lock add cs:?g_TotalArbitrationsTried@@3_KA, rbp; unsigned __int64 g_TotalArbitrationsTried
0x18002194e  test    esi, esi
0x180021950  jz      short loc_180021971
0x180021952  lock add cs:?g_TotalArbitrationsSucceeded@@3_KA, rbp; unsigned __int64 g_TotalArbitrationsSucceeded
0x18002195a  call    ?IsSqmEnabled@@YAHXZ; IsSqmEnabled(void)
0x18002195f  test    eax, eax
0x180021961  jz      short loc_18002198B
0x180021963  mov     edx, 839h
0x180021968  lea     rcx, ?SQMArbitrationsSucceeded@@3KA; ulong SQMArbitrationsSucceeded
0x18002196f  jmp     short loc_180021986
0x180021971  call    ?IsSqmEnabled@@YAHXZ; IsSqmEnabled(void)
0x180021976  test    eax, eax
0x180021978  jz      short loc_18002198B
0x18002197a  mov     edx, 83Ah; unsigned int
0x18002197f  lea     rcx, ?SQMArbitrationsFailed@@3KA; volatile unsigned int *
0x180021986  call    ?UpdateDataPoint@@YAXPECKK@Z; UpdateDataPoint(ulong volatile *,ulong)
0x18002198b  add     rsp, 28h
0x18002198f  pop     rdi
0x180021990  pop     rsi
0x180021991  pop     rbp
0x180021992  pop     rbx
0x180021993  retn
```
