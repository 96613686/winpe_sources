# DestroyAddressFamily

- ea: `0x18000995c`
- end: `0x180009ad3`
- name: `DestroyAddressFamily`
- size: `375`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007c50`
- `0x180009118`
- `0x1800094a8`
- `0x180009adc`

## callees

- `0x180001f00`
- `0x18000995c`
- `0x180009c18`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x1800099f5`
- `ntdll!RtlDeleteResource` at `0x180009a32`
- `ntdll!RtlDeleteResource` at `0x1800099f5`
- `ntdll!RtlDeleteResource` at `0x180009a32`
- `KERNEL32!GetProcessHeap` at `0x1800099d1`
- `KERNEL32!GetProcessHeap` at `0x180009a44`
- `KERNEL32!GetProcessHeap` at `0x180009aa6`
- `KERNEL32!GetProcessHeap` at `0x1800099d1`
- `KERNEL32!GetProcessHeap` at `0x180009a44`
- `KERNEL32!GetProcessHeap` at `0x180009aa6`
- `KERNEL32!HeapFree` at `0x1800099df`
- `KERNEL32!HeapFree` at `0x180009a52`
- `KERNEL32!HeapFree` at `0x180009ab4`
- `KERNEL32!HeapFree` at `0x1800099df`
- `KERNEL32!HeapFree` at `0x180009a52`
- `KERNEL32!HeapFree` at `0x180009ab4`
- `KERNEL32!DeleteCriticalSection` at `0x1800099b6`
- `KERNEL32!DeleteCriticalSection` at `0x180009a0b`
- `KERNEL32!DeleteCriticalSection` at `0x1800099b6`
- `KERNEL32!DeleteCriticalSection` at `0x180009a0b`
- `KERNEL32!DeleteTimerQueueEx` at `0x180009981`
- `KERNEL32!DeleteTimerQueueEx` at `0x180009996`
- `KERNEL32!DeleteTimerQueueEx` at `0x180009981`
- `KERNEL32!DeleteTimerQueueEx` at `0x180009996`

## pseudocode

```c
__int64 __fastcall DestroyAddressFamily(char *lpMem)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 i; // rdi
  void *v5; // rdi
  HANDLE ProcessHeap; // rax
  void *v7; // rcx
  void *v8; // rdi
  HANDLE v9; // rax
  char **v10; // rcx
  LPVOID *v11; // rdx
  _DWORD *v12; // rdi
  HANDLE v13; // rax

  v2 = (void *)*((_QWORD *)lpMem + 91);
  if ( v2 )
    DeleteTimerQueueEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v3 = (void *)*((_QWORD *)lpMem + 92);
  if ( v3 )
    DeleteTimerQueueEx(v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  for ( i = 0; i != 16; ++i )
  {
    if ( *(_DWORD *)&lpMem[72 * i + 1128] )
      DeleteCriticalSection((LPCRITICAL_SECTION)&lpMem[72 * i + 1088]);
  }
  v5 = (void *)*((_QWORD *)lpMem + 107);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  if ( *((_DWORD *)lpMem + 210) )
    RtlDeleteResource((PRTL_RESOURCE)(lpMem + 744));
  if ( *((_DWORD *)lpMem + 264) )
    DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 1016));
  v7 = (void *)*((_QWORD *)lpMem + 89);
  if ( v7 )
    DestroyTable(v7);
  if ( *((_DWORD *)lpMem + 176) )
    RtlDeleteResource((PRTL_RESOURCE)(lpMem + 608));
  v8 = (void *)*((_QWORD *)lpMem + 40);
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
  }
  v10 = (char **)*((_QWORD *)lpMem + 3);
  if ( v10[1] != lpMem + 24 || (v11 = (LPVOID *)*((_QWORD *)lpMem + 4), *v11 != lpMem + 24) )
    __fastfail(3u);
  v12 = (_DWORD *)*((_QWORD *)lpMem + 2);
  *v11 = v10;
  v10[1] = (char *)v11;
  --v12[6];
  if ( _InterlockedExchangeAdd(v12, 0xFFFFFFFF) == 1 )
    DestroyInstance(v12);
  if ( !v12[6] && _InterlockedExchangeAdd(v12, 0xFFFFFFFF) == 1 )
    DestroyInstance(v12);
  v13 = GetProcessHeap();
  HeapFree(v13, 0, lpMem);
  return 0;
}

```

## disassembly

```asm
0x18000995c  mov     [rsp+arg_8], rbx
0x180009961  mov     [rsp+arg_10], rbp
0x180009966  push    rdi
0x180009967  sub     rsp, 20h
0x18000996b  mov     rbx, rcx
0x18000996e  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180009972  mov     rcx, [rcx+2D8h]; TimerQueue
0x180009979  test    rcx, rcx
0x18000997c  jz      short loc_180009987
0x18000997e  mov     rdx, rbp; CompletionEvent
0x180009981  call    cs:__imp_DeleteTimerQueueEx
0x180009987  mov     rcx, [rbx+2E0h]; TimerQueue
0x18000998e  test    rcx, rcx
0x180009991  jz      short loc_18000999C
0x180009993  mov     rdx, rbp; CompletionEvent
0x180009996  call    cs:__imp_DeleteTimerQueueEx
0x18000999c  xor     edi, edi
0x18000999e  lea     rax, [rdi+rdi*8]
0x1800099a2  cmp     dword ptr [rbx+rax*8+468h], 0
0x1800099aa  jz      short loc_1800099BC
0x1800099ac  add     rax, 88h
0x1800099b2  lea     rcx, [rbx+rax*8]; lpCriticalSection
0x1800099b6  call    cs:__imp_DeleteCriticalSection
0x1800099bc  inc     rdi
0x1800099bf  cmp     rdi, 10h
0x1800099c3  jnz     short loc_18000999E
0x1800099c5  mov     rdi, [rbx+358h]
0x1800099cc  test    rdi, rdi
0x1800099cf  jz      short loc_1800099E5
0x1800099d1  call    cs:__imp_GetProcessHeap
0x1800099d7  mov     r8, rdi; lpMem
0x1800099da  xor     edx, edx; dwFlags
0x1800099dc  mov     rcx, rax; hHeap
0x1800099df  call    cs:__imp_HeapFree
0x1800099e5  cmp     dword ptr [rbx+348h], 0
0x1800099ec  jz      short loc_1800099FB
0x1800099ee  lea     rcx, [rbx+2E8h]; Resource
0x1800099f5  call    cs:__imp_RtlDeleteResource
0x1800099fb  cmp     dword ptr [rbx+420h], 0
0x180009a02  jz      short loc_180009A11
0x180009a04  lea     rcx, [rbx+3F8h]; lpCriticalSection
0x180009a0b  call    cs:__imp_DeleteCriticalSection
0x180009a11  mov     rcx, [rbx+2C8h]; lpMem
0x180009a18  test    rcx, rcx
0x180009a1b  jz      short loc_180009A22
0x180009a1d  call    DestroyTable
0x180009a22  cmp     dword ptr [rbx+2C0h], 0
0x180009a29  jz      short loc_180009A38
0x180009a2b  lea     rcx, [rbx+260h]; Resource
0x180009a32  call    cs:__imp_RtlDeleteResource
0x180009a38  mov     rdi, [rbx+140h]
0x180009a3f  test    rdi, rdi
0x180009a42  jz      short loc_180009A58
0x180009a44  call    cs:__imp_GetProcessHeap
0x180009a4a  mov     r8, rdi; lpMem
0x180009a4d  xor     edx, edx; dwFlags
0x180009a4f  mov     rcx, rax; hHeap
0x180009a52  call    cs:__imp_HeapFree
0x180009a58  lea     rax, [rbx+18h]
0x180009a5c  mov     rcx, [rax]
0x180009a5f  cmp     [rcx+8], rax
0x180009a63  jnz     short loc_180009ACC
0x180009a65  mov     rdx, [rax+8]
0x180009a69  cmp     [rdx], rax
0x180009a6c  jnz     short loc_180009ACC
0x180009a6e  mov     rdi, [rbx+10h]
0x180009a72  mov     eax, ebp
0x180009a74  mov     [rdx], rcx
0x180009a77  mov     [rcx+8], rdx
0x180009a7b  dec     dword ptr [rdi+18h]
0x180009a7e  lock xadd [rdi], eax
0x180009a82  add     eax, ebp
0x180009a84  jnz     short loc_180009A8E
0x180009a86  mov     rcx, rdi; lpMem
0x180009a89  call    DestroyInstance
0x180009a8e  cmp     dword ptr [rdi+18h], 0
0x180009a92  jnz     short loc_180009AA6
0x180009a94  mov     eax, ebp
0x180009a96  lock xadd [rdi], eax
0x180009a9a  add     eax, ebp
0x180009a9c  jnz     short loc_180009AA6
0x180009a9e  mov     rcx, rdi; lpMem
0x180009aa1  call    DestroyInstance
0x180009aa6  call    cs:__imp_GetProcessHeap
0x180009aac  mov     r8, rbx; lpMem
0x180009aaf  xor     edx, edx; dwFlags
0x180009ab1  mov     rcx, rax; hHeap
0x180009ab4  call    cs:__imp_HeapFree
0x180009aba  mov     rbx, [rsp+28h+arg_8]
0x180009abf  xor     eax, eax
0x180009ac1  mov     rbp, [rsp+28h+arg_10]
0x180009ac6  add     rsp, 20h
0x180009aca  pop     rdi
0x180009acb  retn
0x180009acc  mov     ecx, 3
0x180009ad1  int     29h; Win8: RtlFailFast(ecx)
```
