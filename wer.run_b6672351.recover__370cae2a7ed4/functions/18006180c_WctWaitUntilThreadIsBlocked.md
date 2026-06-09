# WctWaitUntilThreadIsBlocked

- ea: `0x18006180c`
- end: `0x18006197c`
- name: `WctWaitUntilThreadIsBlocked`
- size: `368`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180007680`
- `0x18005edfc`

## callees

- `0x180004c64`
- `0x18001e0d0`
- `0x180020680`
- `0x1800288c8`
- `0x180053d3c`
- `0x18006180c`
- `0x180061c48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800618e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800618e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800618a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800618a2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180061874`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006191f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180061874`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006191f`

## pseudocode

```c
__int64 __fastcall WctWaitUntilThreadIsBlocked(unsigned int a1, int a2)
{
  int v4; // edi
  unsigned int v5; // ebx
  DWORD CurrentProcessId; // eax
  unsigned int ThreadWaitStatus; // eax
  void *v8; // r11
  unsigned int v9; // esi
  _BYTE v11[68]; // [rsp+20h] [rbp-C8h] BYREF
  int v12; // [rsp+64h] [rbp-84h]
  int v13; // [rsp+68h] [rbp-80h]
  struct _SYSTEM_PROCESS_INFORMATION *v14; // [rsp+100h] [rbp+18h] BYREF

  memset_0(v11, 0, 0x88u);
  v4 = 10;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  Sleep(0x64u);
  v5 = 1;
  while ( v4 && !(unsigned int)WctCreateSystemSnapshot(&v14) )
  {
    CurrentProcessId = GetCurrentProcessId();
    ThreadWaitStatus = WctGetThreadWaitStatus(
                         CurrentProcessId,
                         a1,
                         v14,
                         (struct _SYSTEM_EXTENDED_THREAD_INFORMATION *)v11);
    v14 = 0;
    v9 = ThreadWaitStatus;
    if ( v8 )
      HeapFree(g_hWerheap, 0, v8);
    if ( v9 )
      break;
    if ( v12 == 5 && a2 == v13 )
      goto LABEL_17;
    if ( (unsigned int)(v12 - 1) > 1 && (v12 != 5 || v13) )
      break;
    --v4;
    Sleep(0x1F4u);
  }
  v5 = 0;
LABEL_17:
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v5);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v14);
  return v5;
}

```

## disassembly

```asm
0x18006180c  push    rbx
0x18006180e  push    rbp
0x18006180f  push    rsi
0x180061810  push    rdi
0x180061811  push    r14
0x180061813  push    r15
0x180061815  sub     rsp, 0B8h
0x18006181c  mov     ebp, edx
0x18006181e  mov     r14d, ecx
0x180061821  xor     edx, edx; Val
0x180061823  lea     rcx, [rsp+0E8h+var_C8]; void *
0x180061828  mov     r8d, 88h; Size
0x18006182e  call    memset_0
0x180061833  mov     edi, 0Ah
0x180061838  mov     [rsp+0E8h+arg_10], 0
0x180061844  mov     rcx, cs:WPP_GLOBAL_Control
0x18006184b  lea     r15, WPP_GLOBAL_Control
0x180061852  cmp     rcx, r15
0x180061855  jz      short loc_18006186F
0x180061857  test    byte ptr [rcx+1Ch], 4
0x18006185b  jz      short loc_18006186F
0x18006185d  mov     rcx, [rcx+10h]
0x180061861  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x180061868  mov     edx, edi
0x18006186a  call    WPP_SF_
0x18006186f  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180061874  call    cs:__imp_Sleep
0x18006187b  nop     dword ptr [rax+rax+00h]
0x180061880  mov     ebx, 1
0x180061885  test    edi, edi
0x180061887  jz      loc_180061930
0x18006188d  lea     rcx, [rsp+0E8h+arg_10]
0x180061895  call    ?WctCreateSystemSnapshot@@YAKPEAV?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@Z; WctCreateSystemSnapshot(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> *)
0x18006189a  test    eax, eax
0x18006189c  jnz     loc_180061930
0x1800618a2  call    cs:__imp_GetCurrentProcessId
0x1800618a9  nop     dword ptr [rax+rax+00h]
0x1800618ae  mov     r11, [rsp+0E8h+arg_10]
0x1800618b6  lea     r9, [rsp+0E8h+var_C8]; struct _SYSTEM_EXTENDED_THREAD_INFORMATION *
0x1800618bb  mov     r8, r11; struct _SYSTEM_PROCESS_INFORMATION *
0x1800618be  mov     edx, r14d; unsigned int
0x1800618c1  mov     ecx, eax; unsigned int
0x1800618c3  call    ?WctGetThreadWaitStatus@@YAKKKPEAU_SYSTEM_PROCESS_INFORMATION@@PEAU_SYSTEM_EXTENDED_THREAD_INFORMATION@@@Z; WctGetThreadWaitStatus(ulong,ulong,_SYSTEM_PROCESS_INFORMATION *,_SYSTEM_EXTENDED_THREAD_INFORMATION *)
0x1800618c8  mov     [rsp+0E8h+arg_10], 0
0x1800618d4  mov     esi, eax
0x1800618d6  test    r11, r11
0x1800618d9  jz      short loc_1800618F3
0x1800618db  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800618e2  mov     r8, r11; lpMem
0x1800618e5  xor     edx, edx; dwFlags
0x1800618e7  call    cs:__imp_HeapFree
0x1800618ee  nop     dword ptr [rax+rax+00h]
0x1800618f3  test    esi, esi
0x1800618f5  jnz     short loc_180061930
0x1800618f7  mov     ecx, [rsp+0E8h+var_84]
0x1800618fb  mov     edx, [rsp+0E8h+var_80]
0x1800618ff  cmp     ecx, 5
0x180061902  jnz     short loc_180061908
0x180061904  cmp     ebp, edx
0x180061906  jz      short loc_180061932
0x180061908  lea     eax, [rcx-1]
0x18006190b  cmp     eax, ebx
0x18006190d  jbe     short loc_180061918
0x18006190f  cmp     ecx, 5
0x180061912  jnz     short loc_180061930
0x180061914  test    edx, edx
0x180061916  jnz     short loc_180061930
0x180061918  dec     edi
0x18006191a  mov     ecx, 1F4h; dwMilliseconds
0x18006191f  call    cs:__imp_Sleep
0x180061926  nop     dword ptr [rax+rax+00h]
0x18006192b  jmp     loc_180061885
0x180061930  xor     ebx, ebx
0x180061932  mov     rcx, cs:WPP_GLOBAL_Control
0x180061939  cmp     rcx, r15
0x18006193c  jz      short loc_18006195C
0x18006193e  test    byte ptr [rcx+1Ch], 4
0x180061942  jz      short loc_18006195C
0x180061944  mov     rcx, [rcx+10h]
0x180061948  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18006194f  mov     edx, 0Bh
0x180061954  mov     r9d, ebx
0x180061957  call    WPP_SF_d
0x18006195c  lea     rcx, [rsp+0E8h+arg_10]; void *
0x180061964  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180061969  mov     eax, ebx
0x18006196b  add     rsp, 0B8h
0x180061972  pop     r15
0x180061974  pop     r14
0x180061976  pop     rdi
0x180061977  pop     rsi
0x180061978  pop     rbp
0x180061979  pop     rbx
0x18006197a  retn
```
