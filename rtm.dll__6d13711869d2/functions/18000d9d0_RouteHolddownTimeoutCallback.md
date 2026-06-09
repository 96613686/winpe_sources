# RouteHolddownTimeoutCallback

- ea: `0x18000d9d0`
- end: `0x18000dbbc`
- name: `RouteHolddownTimeoutCallback`
- size: `492`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008ebc`

## callees

- `0x180001de0`
- `0x1800027d8`
- `0x180002bec`
- `0x18000a298`
- `0x18000d9d0`
- `0x180014d2c`
- `0x180015178`
- `0x18001f980`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000daed`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000daed`
- `ntdll!RtlReleaseResource` at `0x18000dac1`
- `ntdll!RtlReleaseResource` at `0x18000db40`
- `ntdll!RtlReleaseResource` at `0x18000dac1`
- `ntdll!RtlReleaseResource` at `0x18000db40`
- `ntdll!RtlAcquireResourceShared` at `0x18000da87`
- `ntdll!RtlAcquireResourceShared` at `0x18000da87`
- `KERNEL32!GetProcessHeap` at `0x18000db76`
- `KERNEL32!GetProcessHeap` at `0x18000db76`
- `KERNEL32!HeapFree` at `0x18000db84`
- `KERNEL32!HeapFree` at `0x18000db84`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000db70`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000db70`

## pseudocode

```c
void __fastcall RouteHolddownTimeoutCallback(HANDLE *a1)
{
  _QWORD *v1; // rdi
  __int64 v3; // rbx
  __int64 v4; // r14
  __int64 v5; // rsi
  unsigned int v6; // ebp
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  int v10; // edx
  void *v11; // rcx
  HANDLE ProcessHeap; // rax
  _DWORD v13[4]; // [rsp+30h] [rbp-68h] BYREF

  v1 = a1[1];
  v3 = v1[6] ^ 0x7754DF32LL;
  v4 = v3 + 32;
  v5 = *(_QWORD *)((v1[7] ^ 0x7754DF32LL) + 0x10);
  AcquireWriteLock(v3 + 32);
  if ( (HANDLE *)v1[5] == a1 )
  {
    v6 = 0;
    if ( *(_DWORD *)(v5 + 44) )
    {
      do
      {
        v7 = *(_QWORD **)(v3 + 24LL * v6 + 136);
        if ( v7 == v1 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 )
            DestroyRoute(v7);
          *(_QWORD *)(v3 + 24LL * v6 + 136) = 0;
        }
        ++v6;
      }
      while ( v6 < *(_DWORD *)(v5 + 44) );
      v4 = v3 + 32;
    }
    RtlAcquireResourceShared((PRTL_RESOURCE)(v5 + 744), 1u);
    v8 = *(unsigned int *)(v3 + 40);
    v13[0] = *(_DWORD *)(v5 + 40);
    v13[1] = v13[0];
    v13[2] = v13[0];
    v9 = ComputeCNsToBeNotified(v5, v8, v13);
    if ( v9 )
      AddToChangedDestLists((char *)v5, v3, v9);
    RtlReleaseResource((PRTL_RESOURCE)(v5 + 744));
    v1[5] = 0;
    if ( *(_DWORD *)(v3 + 52) || *(_WORD *)(v3 + 110) > 1u )
    {
      --*(_WORD *)(v3 + 110);
    }
    else
    {
      ReleaseWriteLock(v4);
      RtlAcquireResourceExclusive((PRTL_RESOURCE)(v5 + 608), 1u);
      AcquireWriteLock(v4);
      --*(_WORD *)(v3 + 110);
      if ( !*(_DWORD *)(v3 + 52) && !*(_WORD *)(v3 + 110) )
      {
        v10 = *(unsigned __int16 *)(v3 + 82);
        *(_WORD *)(v3 + 108) = 1;
        DeleteFromTable(*(_QWORD *)(v5 + 712), v10, v3 + 84, 0, (__int64)v13);
        --*(_DWORD *)(v5 + 720);
      }
      RtlReleaseResource((PRTL_RESOURCE)(v5 + 608));
    }
    ReleaseWriteLock(v4);
    v11 = *(void **)(v5 + 728);
    if ( v11 && *a1 )
      DeleteTimerQueueTimer(v11, *a1, 0);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, a1);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0xFFFFFFFF) == 1 )
      DestroyRoute(v1);
  }
  else
  {
    ReleaseWriteLock(v3 + 32);
  }
}

```

## disassembly

```asm
0x18000d9d0  push    rbx
0x18000d9d2  push    rbp
0x18000d9d3  push    rsi
0x18000d9d4  push    rdi
0x18000d9d5  push    r12
0x18000d9d7  push    r13
0x18000d9d9  push    r14
0x18000d9db  push    r15
0x18000d9dd  sub     rsp, 58h
0x18000d9e1  mov     rax, cs:__security_cookie
0x18000d9e8  xor     rax, rsp
0x18000d9eb  mov     [rsp+98h+var_58], rax
0x18000d9f0  mov     rdi, [rcx+8]
0x18000d9f4  mov     r15, rcx
0x18000d9f7  mov     ecx, 7754DF32h
0x18000d9fc  mov     rbx, [rdi+30h]
0x18000da00  mov     rax, [rdi+38h]
0x18000da04  xor     rbx, rcx
0x18000da07  xor     rax, rcx
0x18000da0a  lea     r14, [rbx+20h]
0x18000da0e  mov     rsi, [rax+10h]
0x18000da12  mov     rcx, r14
0x18000da15  call    AcquireWriteLock
0x18000da1a  cmp     [rdi+28h], r15
0x18000da1e  jz      short loc_18000DA2D
0x18000da20  mov     rcx, r14
0x18000da23  call    ReleaseWriteLock
0x18000da28  jmp     loc_18000DB9E
0x18000da2d  xor     r13d, r13d
0x18000da30  mov     ebp, r13d
0x18000da33  lea     r12d, [r13+1]
0x18000da37  cmp     [rsi+2Ch], r13d
0x18000da3b  jbe     short loc_18000DA7A
0x18000da3d  mov     eax, ebp
0x18000da3f  lea     r12, [rax+rax*2]
0x18000da43  mov     rcx, [rbx+r12*8+88h]; lpMem
0x18000da4b  cmp     rcx, rdi
0x18000da4e  jnz     short loc_18000DA69
0x18000da50  or      eax, 0FFFFFFFFh
0x18000da53  lock xadd [rcx], eax
0x18000da57  cmp     eax, 1
0x18000da5a  jnz     short loc_18000DA61
0x18000da5c  call    DestroyRoute
0x18000da61  mov     [rbx+r12*8+88h], r13
0x18000da69  inc     ebp
0x18000da6b  cmp     ebp, [rsi+2Ch]
0x18000da6e  jb      short loc_18000DA3D
0x18000da70  lea     r14, [rbx+20h]
0x18000da74  mov     r12d, 1
0x18000da7a  lea     rbp, [rsi+2E8h]
0x18000da81  mov     dl, r12b; Wait
0x18000da84  mov     rcx, rbp; Resource
0x18000da87  call    cs:__imp_RtlAcquireResourceShared
0x18000da8d  mov     eax, [rsi+28h]
0x18000da90  lea     r8, [rsp+98h+var_68]
0x18000da95  mov     edx, [rbx+28h]
0x18000da98  mov     rcx, rsi
0x18000da9b  mov     [rsp+98h+var_68], eax
0x18000da9f  mov     [rsp+98h+var_64], eax
0x18000daa3  mov     [rsp+98h+var_60], eax
0x18000daa7  call    ComputeCNsToBeNotified
0x18000daac  test    eax, eax
0x18000daae  jz      short loc_18000DABE
0x18000dab0  mov     r8d, eax
0x18000dab3  mov     rdx, rbx
0x18000dab6  mov     rcx, rsi; Parameter
0x18000dab9  call    AddToChangedDestLists
0x18000dabe  mov     rcx, rbp; Resource
0x18000dac1  call    cs:__imp_RtlReleaseResource
0x18000dac7  mov     [rdi+28h], r13
0x18000dacb  cmp     [rbx+34h], r13d
0x18000dacf  jnz     short loc_18000DB48
0x18000dad1  cmp     [rbx+6Eh], r12w
0x18000dad6  ja      short loc_18000DB48
0x18000dad8  mov     rcx, r14
0x18000dadb  call    ReleaseWriteLock
0x18000dae0  lea     rbp, [rsi+260h]
0x18000dae7  mov     dl, r12b; Wait
0x18000daea  mov     rcx, rbp; Resource
0x18000daed  call    cs:__imp_RtlAcquireResourceExclusive
0x18000daf3  mov     rcx, r14
0x18000daf6  call    AcquireWriteLock
0x18000dafb  mov     eax, 0FFFFh
0x18000db00  add     [rbx+6Eh], ax
0x18000db04  cmp     [rbx+34h], r13d
0x18000db08  jnz     short loc_18000DB3D
0x18000db0a  cmp     [rbx+6Eh], r13w
0x18000db0f  jnz     short loc_18000DB3D
0x18000db11  movzx   edx, word ptr [rbx+52h]
0x18000db15  lea     rax, [rsp+98h+var_68]
0x18000db1a  mov     [rbx+6Ch], r12w
0x18000db1f  lea     r8, [rbx+54h]
0x18000db23  mov     rcx, [rsi+2C8h]
0x18000db2a  xor     r9d, r9d
0x18000db2d  mov     [rsp+98h+var_78], rax
0x18000db32  call    DeleteFromTable
0x18000db37  dec     dword ptr [rsi+2D0h]
0x18000db3d  mov     rcx, rbp; Resource
0x18000db40  call    cs:__imp_RtlReleaseResource
0x18000db46  jmp     short loc_18000DB51
0x18000db48  mov     eax, 0FFFFh
0x18000db4d  add     [rbx+6Eh], ax
0x18000db51  mov     rcx, r14
0x18000db54  call    ReleaseWriteLock
0x18000db59  mov     rcx, [rsi+2D8h]; TimerQueue
0x18000db60  test    rcx, rcx
0x18000db63  jz      short loc_18000DB76
0x18000db65  mov     rdx, [r15]; Timer
0x18000db68  test    rdx, rdx
0x18000db6b  jz      short loc_18000DB76
0x18000db6d  xor     r8d, r8d; CompletionEvent
0x18000db70  call    cs:__imp_DeleteTimerQueueTimer
0x18000db76  call    cs:__imp_GetProcessHeap
0x18000db7c  mov     r8, r15; lpMem
0x18000db7f  xor     edx, edx; dwFlags
0x18000db81  mov     rcx, rax; hHeap
0x18000db84  call    cs:__imp_HeapFree
0x18000db8a  or      eax, 0FFFFFFFFh
0x18000db8d  lock xadd [rdi], eax
0x18000db91  cmp     eax, 1
0x18000db94  jnz     short loc_18000DB9E
0x18000db96  mov     rcx, rdi; lpMem
0x18000db99  call    DestroyRoute
0x18000db9e  mov     rcx, [rsp+98h+var_58]
0x18000dba3  xor     rcx, rsp; StackCookie
0x18000dba6  call    __security_check_cookie
0x18000dbab  add     rsp, 58h
0x18000dbaf  pop     r15
0x18000dbb1  pop     r14
0x18000dbb3  pop     r13
0x18000dbb5  pop     r12
0x18000dbb7  pop     rdi
0x18000dbb8  pop     rsi
0x18000dbb9  pop     rbp
0x18000dbba  pop     rbx
0x18000dbbb  retn
```
