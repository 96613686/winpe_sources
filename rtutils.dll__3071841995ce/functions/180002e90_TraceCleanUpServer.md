# TraceCleanUpServer

- ea: `0x180002e90`
- end: `0x180002feb`
- name: `TraceCleanUpServer`
- size: `347`
- prototype: `__int64 __fastcall(HGLOBAL hMem)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002dd0`
- `0x180009a30`

## callees

- `0x180002c80`
- `0x180002e90`
- `0x180003000`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fcf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002eeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002efe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002eeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002efe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f69`
- `api-ms-win-core-console-l1-2-0!FreeConsole` at `0x180002f26`
- `api-ms-win-core-console-l1-2-0!FreeConsole` at `0x180002f26`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002f8b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002f8b`

## pseudocode

```c
__int64 __fastcall TraceCleanUpServer(struct _RTL_CRITICAL_SECTION *hMem)
{
  volatile __int64 *p_SpinCount; // rdi
  void *v3; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  char *SpinCount; // rcx
  HANDLE *OwningThread; // r14
  HANDLE *v7; // rax
  HANDLE **v8; // rdx
  HANDLE v9; // rcx
  HANDLE *v10; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v12; // rax
  HANDLE v13; // rax

  if ( *(_QWORD *)&hMem[1].LockCount )
    DeleteReadWriteLock(hMem);
  p_SpinCount = (volatile __int64 *)&hMem[8].SpinCount;
  if ( &hMem[8].SpinCount < &hMem[20].SpinCount )
  {
    do
    {
      if ( *p_SpinCount )
        TraceDeleteClientA((__int64)hMem, p_SpinCount);
      ++p_SpinCount;
    }
    while ( p_SpinCount < (volatile __int64 *)&hMem[20].SpinCount );
  }
  v3 = *(void **)&hMem[2].LockCount;
  LODWORD(hMem[1].LockSemaphore) = 60;
  HIDWORD(hMem[1].OwningThread) = 0;
  if ( v3 )
  {
    CloseHandle(v3);
    *(_QWORD *)&hMem[2].LockCount = 0;
  }
  DebugInfo = hMem[2].DebugInfo;
  if ( DebugInfo )
  {
    CloseHandle(DebugInfo);
    hMem[2].DebugInfo = 0;
  }
  SpinCount = (char *)hMem[1].SpinCount;
  if ( (unsigned __int64)(SpinCount - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(SpinCount);
    hMem[1].SpinCount = 0;
  }
  if ( HIDWORD(hMem[1].LockSemaphore) == 1 )
  {
    FreeConsole();
    HIDWORD(hMem[1].LockSemaphore) = 0;
  }
  LODWORD(hMem[1].OwningThread) = 0;
  OwningThread = (HANDLE *)hMem[2].OwningThread;
  while ( OwningThread != &hMem[2].OwningThread )
  {
    v7 = (HANDLE *)*OwningThread;
    if ( *((HANDLE **)*OwningThread + 1) != OwningThread || (v8 = (HANDLE **)OwningThread[1], *v8 != OwningThread) )
      __fastfail(3u);
    v9 = OwningThread[2];
    v10 = OwningThread;
    *v8 = v7;
    OwningThread = v7;
    v7[1] = v8;
    CloseHandle(v9);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  GlobalFree(hMem);
  if ( g_FormatBuffer )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, g_FormatBuffer);
  }
  if ( g_PrintBuffer )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, g_PrintBuffer);
  }
  return 1;
}

```

## disassembly

```asm
0x180002e90  push    rbx
0x180002e92  push    rsi
0x180002e93  push    rdi
0x180002e94  push    r14
0x180002e96  sub     rsp, 28h
0x180002e9a  cmp     qword ptr [rcx+30h], 0
0x180002e9f  mov     rbx, rcx
0x180002ea2  jz      short loc_180002EA9
0x180002ea4  call    DeleteReadWriteLock
0x180002ea9  lea     rsi, [rbx+340h]
0x180002eb0  lea     rdi, [rbx+160h]
0x180002eb7  cmp     rdi, rsi
0x180002eba  jnb     short loc_180002ED6
0x180002ebc  cmp     qword ptr [rdi], 0
0x180002ec0  jz      short loc_180002ECD
0x180002ec2  mov     rdx, rdi
0x180002ec5  mov     rcx, rbx
0x180002ec8  call    TraceDeleteClientA
0x180002ecd  add     rdi, 8
0x180002ed1  cmp     rdi, rsi
0x180002ed4  jb      short loc_180002EBC
0x180002ed6  mov     rcx, [rbx+58h]; hObject
0x180002eda  xor     edi, edi
0x180002edc  mov     dword ptr [rbx+40h], 3Ch ; '<'
0x180002ee3  mov     [rbx+3Ch], edi
0x180002ee6  test    rcx, rcx
0x180002ee9  jz      short loc_180002EF5
0x180002eeb  call    cs:__imp_CloseHandle
0x180002ef1  mov     [rbx+58h], rdi
0x180002ef5  mov     rcx, [rbx+50h]; hObject
0x180002ef9  test    rcx, rcx
0x180002efc  jz      short loc_180002F08
0x180002efe  call    cs:__imp_CloseHandle
0x180002f04  mov     [rbx+50h], rdi
0x180002f08  mov     rcx, [rbx+48h]; hObject
0x180002f0c  lea     rax, [rcx-1]
0x180002f10  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002f14  ja      short loc_180002F20
0x180002f16  call    cs:__imp_CloseHandle
0x180002f1c  mov     [rbx+48h], rdi
0x180002f20  cmp     dword ptr [rbx+44h], 1
0x180002f24  jnz     short loc_180002F2F
0x180002f26  call    cs:__imp_FreeConsole
0x180002f2c  mov     [rbx+44h], edi
0x180002f2f  lea     rsi, [rbx+60h]
0x180002f33  mov     [rbx+38h], edi
0x180002f36  mov     r14, [rsi]
0x180002f39  cmp     r14, rsi
0x180002f3c  jz      short loc_180002F88
0x180002f3e  mov     rax, [r14]
0x180002f41  cmp     [rax+8], r14
0x180002f45  jnz     loc_180002FE4
0x180002f4b  mov     rdx, [r14+8]
0x180002f4f  cmp     [rdx], r14
0x180002f52  jnz     loc_180002FE4
0x180002f58  mov     rcx, [r14+10h]; hObject
0x180002f5c  mov     rdi, r14
0x180002f5f  mov     [rdx], rax
0x180002f62  mov     r14, rax
0x180002f65  mov     [rax+8], rdx
0x180002f69  call    cs:__imp_CloseHandle
0x180002f6f  call    cs:__imp_GetProcessHeap
0x180002f75  mov     r8, rdi; lpMem
0x180002f78  xor     edx, edx; dwFlags
0x180002f7a  mov     rcx, rax; hHeap
0x180002f7d  call    cs:__imp_HeapFree
0x180002f83  cmp     r14, rsi
0x180002f86  jnz     short loc_180002F3E
0x180002f88  mov     rcx, rbx; hMem
0x180002f8b  call    cs:__imp_GlobalFree
0x180002f91  cmp     cs:g_FormatBuffer, 0
0x180002f99  jz      short loc_180002FB3
0x180002f9b  call    cs:__imp_GetProcessHeap
0x180002fa1  mov     r8, cs:g_FormatBuffer; lpMem
0x180002fa8  xor     edx, edx; dwFlags
0x180002faa  mov     rcx, rax; hHeap
0x180002fad  call    cs:__imp_HeapFree
0x180002fb3  cmp     cs:g_PrintBuffer, 0
0x180002fbb  jz      short loc_180002FD5
0x180002fbd  call    cs:__imp_GetProcessHeap
0x180002fc3  mov     r8, cs:g_PrintBuffer; lpMem
0x180002fca  xor     edx, edx; dwFlags
0x180002fcc  mov     rcx, rax; hHeap
0x180002fcf  call    cs:__imp_HeapFree
0x180002fd5  mov     eax, 1
0x180002fda  add     rsp, 28h
0x180002fde  pop     r14
0x180002fe0  pop     rdi
0x180002fe1  pop     rsi
0x180002fe2  pop     rbx
0x180002fe3  retn
0x180002fe4  mov     ecx, 3
0x180002fe9  int     29h; Win8: RtlFailFast(ecx)
```
