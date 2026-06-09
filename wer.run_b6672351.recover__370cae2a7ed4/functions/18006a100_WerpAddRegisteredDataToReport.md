# WerpAddRegisteredDataToReport

- ea: `0x18006a100`
- end: `0x18006a426`
- name: `WerpAddRegisteredDataToReport`
- size: `806`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030058`

## callees

- `0x180004c64`
- `0x18001c368`
- `0x180020680`
- `0x18003de9c`
- `0x180042734`
- `0x18006a100`
- `0x1800a85c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a301`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b02a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a301`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b02a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006a249`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006a249`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18006a162`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18006a162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a356`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a356`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006a1e4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006a2bc`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006a1e4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006a2bc`

## pseudocode

```c
__int64 __fastcall WerpAddRegisteredDataToReport(void *a1, void *a2)
{
  unsigned int GatherListStart; // ebx
  LPCVOID v5; // rdi
  unsigned int v6; // r15d
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int v10; // eax
  unsigned __int16 v11; // dx
  SIZE_T v12; // r13
  LPCVOID *v13; // r14
  int (*v14)(void *, const wchar_t *, enum _WER_FILE_TYPE, unsigned int, const wchar_t *, const wchar_t *); // r9
  unsigned __int16 v15; // dx
  DWORD LastError; // eax
  int (*lpNumberOfBytesRead)(void *, unsigned int, void *, unsigned int, unsigned int); // [rsp+20h] [rbp-98h]
  int (*v19)(void *, unsigned int, void *, unsigned int, unsigned int); // [rsp+28h] [rbp-90h]
  unsigned int v20; // [rsp+30h] [rbp-88h]
  __int64 Buffer; // [rsp+60h] [rbp-58h] BYREF
  __int128 v22; // [rsp+68h] [rbp-50h]
  __int64 v23; // [rsp+78h] [rbp-40h]
  DWORD ProcessId; // [rsp+C0h] [rbp+8h]
  SIZE_T NumberOfBytesRead; // [rsp+D0h] [rbp+18h] BYREF
  LPCVOID lpBaseAddress; // [rsp+D8h] [rbp+20h] BYREF

  lpBaseAddress = 0;
  if ( a1 && a2 )
  {
    GatherListStart = WerpGetGatherListStart(a2, (struct WER_GATHER **)&lpBaseAddress);
    if ( (GatherListStart & 0x80000000) == 0 )
    {
      v5 = lpBaseAddress;
      if ( lpBaseAddress )
      {
        v6 = 0;
        ProcessId = GetProcessId(a2);
        if ( !ProcessId )
          MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7, v9);
        while ( v5 )
        {
          v10 = v6++;
          if ( v10 >= 0x200 )
            break;
          Buffer = 0;
          v22 = 0;
          v23 = 0;
          NumberOfBytesRead = 0;
          if ( !ReadProcessMemory(a2, v5, &Buffer, 0x20u, &NumberOfBytesRead) || NumberOfBytesRead != 32 )
          {
            LastError = GetLastError();
            GatherListStart = ERROR_HR_FROM_WIN32(LastError);
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids);
            return GatherListStart;
          }
          v11 = v22 & 0x3FFF;
          if ( (unsigned __int16)((v22 & 0x3FFF) - 32) > 0x208u )
          {
            GatherListStart = ERROR_HR_FROM_WIN32(0xDu);
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids, v15);
            return GatherListStart;
          }
          NumberOfBytesRead = 0;
          v12 = v11;
          v13 = (LPCVOID *)HeapAlloc(g_hWerheap, 0, v11);
          if ( !v13 )
          {
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids);
            return (unsigned int)-2147024882;
          }
          if ( ReadProcessMemory(a2, v5, v13, v12, &NumberOfBytesRead) )
          {
            v5 = *v13;
            lpBaseAddress = *v13;
            WerpAddGatherBlockToReport(a1, ProcessId, (struct WER_GATHER *)v13, v14, lpNumberOfBytesRead, v19, v20);
          }
          else
          {
            v5 = 0;
            lpBaseAddress = 0;
          }
          HeapFree(g_hWerheap, 0, v13);
        }
      }
    }
    return GatherListStart;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18006a100  mov     rax, rsp
0x18006a103  push    rbx
0x18006a104  push    rsi
0x18006a105  push    rdi
0x18006a106  push    r12
0x18006a108  push    r13
0x18006a10a  push    r14
0x18006a10c  push    r15
0x18006a10e  sub     rsp, 80h
0x18006a115  mov     rsi, rdx
0x18006a118  mov     r12, rcx
0x18006a11b  mov     qword ptr [rax+20h], 0
0x18006a123  test    rcx, rcx
0x18006a126  jz      loc_18006A3DF
0x18006a12c  test    rdx, rdx
0x18006a12f  jz      loc_18006A3DF
0x18006a135  lea     rdx, [rax+20h]; struct WER_GATHER **
0x18006a139  mov     rcx, rsi; void *
0x18006a13c  call    ?WerpGetGatherListStart@@YAJPEAXPEAPEAUWER_GATHER@@@Z; WerpGetGatherListStart(void *,WER_GATHER * *)
0x18006a141  mov     ebx, eax
0x18006a143  test    eax, eax
0x18006a145  js      loc_18006A3DB
0x18006a14b  mov     rdi, [rsp+0B8h+lpBaseAddress]
0x18006a153  test    rdi, rdi
0x18006a156  jz      loc_18006A3DB
0x18006a15c  xor     r15d, r15d
0x18006a15f  mov     rcx, rsi; Process
0x18006a162  call    cs:__imp_GetProcessId
0x18006a169  nop     dword ptr [rax+rax+00h]
0x18006a16e  mov     [rsp+0B8h+arg_0], eax
0x18006a175  test    eax, eax
0x18006a177  jnz     short loc_18006A17F
0x18006a179  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006a17e  nop
0x18006a17f  mov     r14d, 20h ; ' '
0x18006a185  test    rdi, rdi
0x18006a188  jz      loc_18006A39D
0x18006a18e  mov     eax, r15d
0x18006a191  inc     r15d
0x18006a194  mov     [rsp+0B8h+var_70], r15d
0x18006a199  cmp     eax, 200h
0x18006a19e  jnb     loc_18006A39D
0x18006a1a4  mov     [rsp+0B8h+Buffer], 0
0x18006a1ad  xorps   xmm0, xmm0
0x18006a1b0  xor     eax, eax
0x18006a1b2  movups  [rsp+0B8h+var_50], xmm0
0x18006a1b7  mov     [rsp+0B8h+var_40], rax
0x18006a1bc  mov     [rsp+0B8h+var_78], ax
0x18006a1c1  mov     [rsp+0B8h+NumberOfBytesRead], rax
0x18006a1c9  lea     rax, [rsp+0B8h+NumberOfBytesRead]
0x18006a1d1  mov     [rsp+0B8h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18006a1d6  mov     r9d, r14d; nSize
0x18006a1d9  lea     r8, [rsp+0B8h+Buffer]; lpBuffer
0x18006a1de  mov     rdx, rdi; lpBaseAddress
0x18006a1e1  mov     rcx, rsi; hProcess
0x18006a1e4  call    cs:__imp_ReadProcessMemory
0x18006a1eb  nop     dword ptr [rax+rax+00h]
0x18006a1f0  test    eax, eax
0x18006a1f2  jz      loc_18006A356
0x18006a1f8  cmp     [rsp+0B8h+NumberOfBytesRead], r14
0x18006a200  jnz     loc_18006A356
0x18006a206  mov     eax, 3FFFh
0x18006a20b  movzx   edx, word ptr [rsp+0B8h+var_50]
0x18006a210  and     dx, ax
0x18006a213  mov     [rsp+0B8h+var_78], dx
0x18006a218  movzx   eax, dx
0x18006a21b  sub     ax, r14w
0x18006a21f  mov     ecx, 208h
0x18006a224  cmp     ax, cx
0x18006a227  ja      loc_18006A312
0x18006a22d  mov     [rsp+0B8h+NumberOfBytesRead], 0
0x18006a239  movzx   r13d, dx
0x18006a23d  mov     r8d, r13d; dwBytes
0x18006a240  xor     edx, edx; dwFlags
0x18006a242  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18006a249  call    cs:__imp_HeapAlloc
0x18006a250  nop     dword ptr [rax+rax+00h]
0x18006a255  mov     r14, rax
0x18006a258  mov     [rsp+0B8h+var_68], rax
0x18006a25d  mov     [rsp+0B8h+var_60], rax
0x18006a262  test    rax, rax
0x18006a265  jnz     short loc_18006A2A3
0x18006a267  lea     rax, WPP_GLOBAL_Control
0x18006a26e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a275  cmp     rcx, rax
0x18006a278  jz      short loc_18006A295
0x18006a27a  test    byte ptr [rcx+1Ch], 1
0x18006a27e  jz      short loc_18006A295
0x18006a280  mov     edx, 0ACh
0x18006a285  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x18006a28c  mov     rcx, [rcx+10h]
0x18006a290  call    WPP_SF_
0x18006a295  mov     ebx, 8007000Eh
0x18006a29a  mov     [rsp+0B8h+var_74], ebx
0x18006a29e  jmp     loc_18006A39D
0x18006a2a3  lea     rax, [rsp+0B8h+NumberOfBytesRead]
0x18006a2ab  mov     [rsp+0B8h+lpNumberOfBytesRead], rax; int (*)(void *, unsigned int, void *, unsigned int, unsigned int)
0x18006a2b0  mov     r9, r13; nSize
0x18006a2b3  mov     r8, r14; lpBuffer
0x18006a2b6  mov     rdx, rdi; lpBaseAddress
0x18006a2b9  mov     rcx, rsi; hProcess
0x18006a2bc  call    cs:__imp_ReadProcessMemory
0x18006a2c3  nop     dword ptr [rax+rax+00h]
0x18006a2c8  test    eax, eax
0x18006a2ca  jz      short loc_18006A2EB
0x18006a2cc  mov     rdi, [r14]
0x18006a2cf  mov     [rsp+0B8h+lpBaseAddress], rdi
0x18006a2d7  mov     r8, r14; struct WER_GATHER *
0x18006a2da  mov     edx, [rsp+0B8h+arg_0]; unsigned int
0x18006a2e1  mov     rcx, r12; void *
0x18006a2e4  call    ?WerpAddGatherBlockToReport@@YAJPEAXKPEAUWER_GATHER@@P6AJ0PEB_WW4_WER_FILE_TYPE@@K22@ZP6AJ0K0KK@Z5K@Z; WerpAddGatherBlockToReport(void *,ulong,WER_GATHER *,long (*)(void *,wchar_t const *,_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *),long (*)(void *,ulong,void *,ulong,ulong),long (*)(void *,ulong,void *,ulong,ulong),ulong)
0x18006a2e9  jmp     short loc_18006A2F5
0x18006a2eb  xor     edi, edi
0x18006a2ed  mov     [rsp+0B8h+lpBaseAddress], rdi
0x18006a2f5  mov     r8, r14; lpMem
0x18006a2f8  xor     edx, edx; dwFlags
0x18006a2fa  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18006a301  call    cs:__imp_HeapFree
0x18006a308  nop     dword ptr [rax+rax+00h]
0x18006a30d  jmp     loc_18006A17F
0x18006a312  mov     ecx, 0Dh; unsigned int
0x18006a317  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18006a31c  mov     ebx, eax
0x18006a31e  mov     [rsp+0B8h+var_74], eax
0x18006a322  lea     rax, WPP_GLOBAL_Control
0x18006a329  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a330  cmp     rcx, rax
0x18006a333  jz      short loc_18006A39D
0x18006a335  test    byte ptr [rcx+1Ch], 1
0x18006a339  jz      short loc_18006A39D
0x18006a33b  movzx   r9d, dx
0x18006a33f  mov     edx, 0ADh
0x18006a344  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x18006a34b  mov     rcx, [rcx+10h]
0x18006a34f  call    WPP_SF_d
0x18006a354  jmp     short loc_18006A39D
0x18006a356  call    cs:__imp_GetLastError
0x18006a35d  nop     dword ptr [rax+rax+00h]
0x18006a362  mov     ecx, eax; unsigned int
0x18006a364  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18006a369  mov     ebx, eax
0x18006a36b  mov     [rsp+0B8h+var_74], eax
0x18006a36f  lea     rax, WPP_GLOBAL_Control
0x18006a376  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a37d  cmp     rcx, rax
0x18006a380  jz      short loc_18006A39D
0x18006a382  test    byte ptr [rcx+1Ch], 1
0x18006a386  jz      short loc_18006A39D
0x18006a388  mov     edx, 0ABh
0x18006a38d  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x18006a394  mov     rcx, [rcx+10h]
0x18006a398  call    WPP_SF_
0x18006a39d  jmp     short loc_18006A3DB
0x18006a39f  lea     rax, WPP_GLOBAL_Control
0x18006a3a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a3ad  cmp     rcx, rax
0x18006a3b0  jz      short loc_18006A3CD
0x18006a3b2  test    byte ptr [rcx+1Ch], 1
0x18006a3b6  jz      short loc_18006A3CD
0x18006a3b8  mov     edx, 0AEh
0x18006a3bd  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x18006a3c4  mov     rcx, [rcx+10h]
0x18006a3c8  call    WPP_SF_
0x18006a3cd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006a3d2  mov     ebx, 80004005h
0x18006a3d7  mov     [rsp+0B8h+var_74], ebx
0x18006a3db  mov     eax, ebx
0x18006a3dd  jmp     short loc_18006A412
0x18006a3df  lea     rax, WPP_GLOBAL_Control
0x18006a3e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a3ed  cmp     rcx, rax
0x18006a3f0  jz      short loc_18006A40D
0x18006a3f2  test    byte ptr [rcx+1Ch], 1
0x18006a3f6  jz      short loc_18006A40D
0x18006a3f8  mov     edx, 0AAh
0x18006a3fd  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x18006a404  mov     rcx, [rcx+10h]
0x18006a408  call    WPP_SF_
0x18006a40d  mov     eax, 80070057h
0x18006a412  add     rsp, 80h
0x18006a419  pop     r15
0x18006a41b  pop     r14
0x18006a41d  pop     r13
0x18006a41f  pop     r12
0x18006a421  pop     rdi
0x18006a422  pop     rsi
0x18006a423  pop     rbx
0x18006a424  retn
0x1800b028a  push    rbp
0x1800b028c  sub     rsp, 40h
0x1800b0290  mov     rbp, rdx
0x1800b0293  mov     r8, [rbp+50h]; lpMem
0x1800b0297  xor     edx, edx; dwFlags
0x1800b0299  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800b02a0  call    cs:__imp_HeapFree
0x1800b02a7  nop     dword ptr [rax+rax+00h]
0x1800b02ac  nop
0x1800b02ad  add     rsp, 40h
0x1800b02b1  pop     rbp
0x1800b02b2  retn
```
