# PfSvSuperfetchProcessActions

- ea: `0x18003cda4`
- end: `0x18003cf01`
- name: `PfSvSuperfetchProcessActions`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006a020`

## callees

- `0x18003cda4`
- `0x18003cf08`
- `0x18003cffc`
- `0x18003d1c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cdd1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cdd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ce10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ce10`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003cedd`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003cedd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003cef6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003cef6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cec4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cec4`

## pseudocode

```c
__int64 __fastcall PfSvSuperfetchProcessActions(__int64 a1)
{
  __int64 v2; // rdi
  unsigned __int16 *v3; // r14
  unsigned __int64 CurrentTime; // rbx
  __int64 v5; // rsi
  unsigned __int16 *v6; // rax
  void *v7; // rcx
  _QWORD *v8; // rbx
  int v9; // esi
  unsigned int v10; // ebp
  __int64 v12; // r8
  __int64 v13; // rdx
  void *v14; // r8
  int ThreadPriority; // eax
  int v16; // edx

  while ( 1 )
  {
    v2 = *(_QWORD *)&PfSvcGlobals + 1720LL;
    v3 = *(unsigned __int16 **)(*(_QWORD *)&PfSvcGlobals + 1776LL);
    CurrentTime = PfsActionItemGetCurrentTime(a1);
    EnterCriticalSection((LPCRITICAL_SECTION)v2);
    v5 = 12LL * *v3;
    v6 = &v3[v5];
    if ( *(_QWORD *)&v3[v5 + 8] <= CurrentTime )
    {
      v8 = (_QWORD *)*((_QWORD *)v6 + 1);
      *((_QWORD *)v6 + 1) = 0;
      *((_QWORD *)v6 + 2) = 0x7FFFFFFFFFFFFFFFLL;
      v9 = -1431655765 * ((v5 * 2) >> 3) - 1;
      v12 = 3LL * *v3;
      v13 = v3[12 * *v3];
      v3[12 * v3[12 * *v3 + 1]] = v13;
      v3[12 * v13 + 1] = v3[4 * v12 + 1];
    }
    else
    {
      v7 = *(void **)(v2 + 48);
      v8 = 0;
      v9 = *(_DWORD *)(v2 + 64);
      if ( v7 )
      {
        if ( *(_BYTE *)(v2 + 69) )
        {
          ThreadPriority = GetThreadPriority(v7);
          v16 = *(char *)(v2 + 68);
          *(_BYTE *)(v2 + 69) = 0;
          if ( ThreadPriority != v16 )
            SetThreadPriority(*(HANDLE *)(v2 + 48), v16);
        }
      }
    }
    v10 = PfsActionItemMgrSetTimer(v2);
    LeaveCriticalSection((LPCRITICAL_SECTION)v2);
    if ( v9 >= 58 || v9 >= *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 1784LL) )
      break;
    do
    {
      PfSvSuperfetchProcessAction(a1, v9, (__int64)v8);
      if ( !v8 )
        break;
      v14 = v8;
      v8 = (_QWORD *)*v8;
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v14);
    }
    while ( v8 );
  }
  return v10;
}

```

## disassembly

```asm
0x18003cda4  push    rbx
0x18003cda6  push    rbp
0x18003cda7  push    rsi
0x18003cda8  push    rdi
0x18003cda9  push    r14
0x18003cdab  push    r15
0x18003cdad  sub     rsp, 28h
0x18003cdb1  mov     r15, rcx
0x18003cdb4  mov     rdi, cs:PfSvcGlobals
0x18003cdbb  add     rdi, 6B8h
0x18003cdc2  mov     r14, [rdi+38h]
0x18003cdc6  call    PfsActionItemGetCurrentTime
0x18003cdcb  mov     rcx, rdi; lpCriticalSection
0x18003cdce  mov     rbx, rax
0x18003cdd1  call    cs:__imp_EnterCriticalSection
0x18003cdd7  movzx   edx, word ptr [r14]
0x18003cddb  lea     r8, [rdx+rdx*2]
0x18003cddf  lea     rsi, ds:0[r8*8]
0x18003cde7  lea     rax, [rsi+r14]
0x18003cdeb  cmp     [rax+10h], rbx
0x18003cdef  jbe     short loc_18003CE2A
0x18003cdf1  mov     rcx, [rdi+30h]; hThread
0x18003cdf5  xor     ebx, ebx
0x18003cdf7  mov     esi, [rdi+40h]
0x18003cdfa  test    rcx, rcx
0x18003cdfd  jnz     loc_18003CED4
0x18003ce03  mov     rcx, rdi
0x18003ce06  call    PfsActionItemMgrSetTimer
0x18003ce0b  mov     rcx, rdi; lpCriticalSection
0x18003ce0e  mov     ebp, eax
0x18003ce10  call    cs:__imp_LeaveCriticalSection
0x18003ce16  cmp     esi, 3Ah ; ':'
0x18003ce19  jl      short loc_18003CE89
0x18003ce1b  mov     eax, ebp
0x18003ce1d  add     rsp, 28h
0x18003ce21  pop     r15
0x18003ce23  pop     r14
0x18003ce25  pop     rdi
0x18003ce26  pop     rsi
0x18003ce27  pop     rbp
0x18003ce28  pop     rbx
0x18003ce29  retn
0x18003ce2a  mov     rbx, [rax+8]
0x18003ce2e  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18003ce38  mov     qword ptr [rax+8], 0
0x18003ce40  sar     rsi, 3
0x18003ce44  imul    rsi, rcx
0x18003ce48  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18003ce52  mov     [rax+10h], rcx
0x18003ce56  dec     esi
0x18003ce58  movzx   eax, word ptr [r14]
0x18003ce5c  lea     r8, [rax+rax*2]
0x18003ce60  movzx   eax, word ptr [r14+r8*8+2]
0x18003ce66  movzx   edx, word ptr [r14+r8*8]
0x18003ce6b  lea     rcx, [rax+rax*2]
0x18003ce6f  mov     [r14+rcx*8], dx
0x18003ce74  lea     rcx, [rdx+rdx*2]
0x18003ce78  movzx   eax, word ptr [r14+r8*8+2]
0x18003ce7e  mov     [r14+rcx*8+2], ax
0x18003ce84  jmp     loc_18003CE03
0x18003ce89  mov     rcx, cs:PfSvcGlobals
0x18003ce90  cmp     esi, [rcx+6F8h]
0x18003ce96  jge     short loc_18003CE1B
0x18003ce98  mov     r8, rbx
0x18003ce9b  mov     edx, esi
0x18003ce9d  mov     rcx, r15
0x18003cea0  mov     rdi, rbx
0x18003cea3  call    PfSvSuperfetchProcessAction
0x18003cea8  test    rbx, rbx
0x18003ceab  jz      loc_18003CDB4
0x18003ceb1  mov     rcx, cs:PfSvcGlobals
0x18003ceb8  mov     r8, rdi; lpMem
0x18003cebb  mov     rbx, [rbx]
0x18003cebe  xor     edx, edx; dwFlags
0x18003cec0  mov     rcx, [rcx+58h]; hHeap
0x18003cec4  call    cs:__imp_HeapFree
0x18003ceca  test    rbx, rbx
0x18003cecd  jnz     short loc_18003CE98
0x18003cecf  jmp     loc_18003CDB4
0x18003ced4  cmp     [rdi+45h], bl
0x18003ced7  jz      loc_18003CE03
0x18003cedd  call    cs:__imp_GetThreadPriority
0x18003cee3  movsx   edx, byte ptr [rdi+44h]; nPriority
0x18003cee7  mov     [rdi+45h], bl
0x18003ceea  cmp     eax, edx
0x18003ceec  jz      loc_18003CE03
0x18003cef2  mov     rcx, [rdi+30h]; hThread
0x18003cef6  call    cs:__imp_SetThreadPriority
0x18003cefc  jmp     loc_18003CE03
```
