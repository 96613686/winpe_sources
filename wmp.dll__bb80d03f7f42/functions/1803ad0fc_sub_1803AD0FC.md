# sub_1803AD0FC

- ea: `0x1803ad0fc`
- end: `0x1803ad2d0`
- name: `sub_1803AD0FC`
- size: `468`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1803acf74`
- `0x1803cf6d0`

## callees

- `0x1803ac12c`
- `0x1803acdc4`
- `0x1803ad0fc`
- `0x1803ad2d8`
- `0x18074be40`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1803ad1f9`
- `KERNEL32!CreateThread` at `0x1803ad1f9`
- `KERNEL32!CreateEventW` at `0x1803ad15a`
- `KERNEL32!CreateEventW` at `0x1803ad15a`
- `KERNEL32!SetThreadPriority` at `0x1803ad2bf`
- `KERNEL32!SetThreadPriority` at `0x1803ad2bf`
- `KERNEL32!CloseHandle` at `0x1803ad19a`
- `KERNEL32!CloseHandle` at `0x1803ad28e`
- `KERNEL32!CloseHandle` at `0x1803ad19a`
- `KERNEL32!CloseHandle` at `0x1803ad28e`
- `KERNEL32!LeaveCriticalSection` at `0x1803ad1bd`
- `KERNEL32!LeaveCriticalSection` at `0x1803ad1bd`
- `KERNEL32!EnterCriticalSection` at `0x1803ad12b`
- `KERNEL32!EnterCriticalSection` at `0x1803ad12b`
- `KERNEL32!GetLastError` at `0x1803ad26b`
- `KERNEL32!GetLastError` at `0x1803ad26b`
- `KERNEL32!WaitForMultipleObjects` at `0x1803ad257`
- `KERNEL32!WaitForMultipleObjects` at `0x1803ad257`

## string_xrefs

- `0x1803ad214`: `CreateThread`
- `0x1803ad221`: `StartWorkerThread`

## pseudocode

```c
__int64 __fastcall sub_1803AD0FC(__int64 a1)
{
  signed int v3; // ebx
  DWORD v4; // eax
  HANDLE Handles[3]; // [rsp+40h] [rbp-18h] BYREF

  *(_OWORD *)Handles = 0;
  if ( hThread )
    return 0;
  v3 = 0;
  EnterCriticalSection(&stru_1808E13A0);
  if ( !hThread )
  {
    v3 = sub_1803ACDC4(a1);
    if ( v3 < 0 )
      goto LABEL_8;
    qword_1808E13E8 = CreateEventW(0, 1, 0, 0);
    if ( !qword_1808E13E8 )
    {
      v3 = -2147024882;
      if ( a1 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 32LL))(a1, 2147942414LL);
      goto LABEL_8;
    }
    hThread = CreateThread(0, 0, sub_1803AD570, 0, 0, &ThreadId);
    if ( hThread )
    {
      Handles[1] = hThread;
      Handles[0] = qword_1808E13E8;
      v4 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( !v4 )
      {
        SetThreadPriority(hThread, nPriority);
        goto LABEL_10;
      }
      if ( v4 == -1 )
        v3 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v3 = -2147467259;
      CloseHandle(hThread);
      hThread = 0;
    }
    else
    {
      v3 = sub_1803AC12C(a1, L"StartWorkerThread", 328, L"CreateThread");
    }
    if ( v3 < 0 )
    {
LABEL_8:
      if ( qword_1808E13E8 )
      {
        CloseHandle(qword_1808E13E8);
        qword_1808E13E8 = 0;
        sub_1803AD2D8();
      }
    }
  }
LABEL_10:
  LeaveCriticalSection(&stru_1808E13A0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1803ad0fc  mov     [rsp+arg_0], rbx
0x1803ad101  push    rdi
0x1803ad102  sub     rsp, 50h
0x1803ad106  cmp     cs:hThread, 0
0x1803ad10e  xorps   xmm0, xmm0
0x1803ad111  movups  xmmword ptr [rsp+58h+Handles], xmm0
0x1803ad116  mov     rdi, rcx
0x1803ad119  jz      short loc_1803AD122
0x1803ad11b  xor     eax, eax
0x1803ad11d  jmp     loc_1803AD1CB
0x1803ad122  lea     rcx, stru_1808E13A0; lpCriticalSection
0x1803ad129  xor     ebx, ebx
0x1803ad12b  call    cs:EnterCriticalSection
0x1803ad132  nop     dword ptr [rax+rax+00h]
0x1803ad137  cmp     cs:hThread, rbx
0x1803ad13e  jnz     short loc_1803AD1B6
0x1803ad140  mov     rcx, rdi
0x1803ad143  call    sub_1803ACDC4
0x1803ad148  mov     ebx, eax
0x1803ad14a  test    eax, eax
0x1803ad14c  js      short loc_1803AD18E
0x1803ad14e  xor     r9d, r9d; lpName
0x1803ad151  xor     r8d, r8d; bInitialState
0x1803ad154  xor     ecx, ecx; lpEventAttributes
0x1803ad156  lea     edx, [r9+1]; bManualReset
0x1803ad15a  call    cs:CreateEventW
0x1803ad161  nop     dword ptr [rax+rax+00h]
0x1803ad166  mov     cs:qword_1808E13E8, rax
0x1803ad16d  test    rax, rax
0x1803ad170  jnz     short loc_1803AD1D7
0x1803ad172  mov     ebx, 8007000Eh
0x1803ad177  test    rdi, rdi
0x1803ad17a  jz      short loc_1803AD18E
0x1803ad17c  mov     rax, [rdi]
0x1803ad17f  mov     edx, ebx
0x1803ad181  mov     rcx, rdi
0x1803ad184  mov     rax, [rax+20h]
0x1803ad188  call    cs:__guard_dispatch_icall_fptr
0x1803ad18e  mov     rcx, cs:qword_1808E13E8; hObject
0x1803ad195  test    rcx, rcx
0x1803ad198  jz      short loc_1803AD1B6
0x1803ad19a  call    cs:CloseHandle
0x1803ad1a1  nop     dword ptr [rax+rax+00h]
0x1803ad1a6  mov     cs:qword_1808E13E8, 0
0x1803ad1b1  call    sub_1803AD2D8
0x1803ad1b6  lea     rcx, stru_1808E13A0; lpCriticalSection
0x1803ad1bd  call    cs:LeaveCriticalSection
0x1803ad1c4  nop     dword ptr [rax+rax+00h]
0x1803ad1c9  mov     eax, ebx
0x1803ad1cb  mov     rbx, [rsp+58h+arg_0]
0x1803ad1d0  add     rsp, 50h
0x1803ad1d4  pop     rdi
0x1803ad1d5  retn
0x1803ad1d7  lea     rax, ThreadId
0x1803ad1de  xor     r9d, r9d; lpParameter
0x1803ad1e1  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x1803ad1e6  lea     r8, sub_1803AD570; lpStartAddress
0x1803ad1ed  xor     edx, edx; dwStackSize
0x1803ad1ef  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x1803ad1f7  xor     ecx, ecx; lpThreadAttributes
0x1803ad1f9  call    cs:CreateThread
0x1803ad200  nop     dword ptr [rax+rax+00h]
0x1803ad205  mov     cs:hThread, rax
0x1803ad20c  mov     rcx, rax
0x1803ad20f  test    rax, rax
0x1803ad212  jnz     short loc_1803AD234
0x1803ad214  lea     r9, aCreatethread; "CreateThread"
0x1803ad21b  mov     r8d, 148h
0x1803ad221  lea     rdx, aStartworkerthr; "StartWorkerThread"
0x1803ad228  mov     rcx, rdi
0x1803ad22b  call    sub_1803AC12C
0x1803ad230  mov     ebx, eax
0x1803ad232  jmp     short loc_1803AD2A5
0x1803ad234  mov     rax, cs:qword_1808E13E8
0x1803ad23b  lea     rdx, [rsp+58h+Handles]; lpHandles
0x1803ad240  xor     r8d, r8d; bWaitAll
0x1803ad243  mov     [rsp+58h+Handles+8], rcx
0x1803ad248  or      edi, 0FFFFFFFFh
0x1803ad24b  mov     [rsp+58h+Handles], rax
0x1803ad250  mov     r9d, edi; dwMilliseconds
0x1803ad253  lea     ecx, [r8+2]; nCount
0x1803ad257  call    cs:WaitForMultipleObjects
0x1803ad25e  nop     dword ptr [rax+rax+00h]
0x1803ad263  test    eax, eax
0x1803ad265  jz      short loc_1803AD2B2
0x1803ad267  cmp     eax, edi
0x1803ad269  jnz     short loc_1803AD282
0x1803ad26b  call    cs:GetLastError
0x1803ad272  nop     dword ptr [rax+rax+00h]
0x1803ad277  movzx   ebx, ax
0x1803ad27a  or      ebx, 80070000h
0x1803ad280  jmp     short loc_1803AD287
0x1803ad282  mov     ebx, 80004005h
0x1803ad287  mov     rcx, cs:hThread; hObject
0x1803ad28e  call    cs:CloseHandle
0x1803ad295  nop     dword ptr [rax+rax+00h]
0x1803ad29a  mov     cs:hThread, 0
0x1803ad2a5  test    ebx, ebx
0x1803ad2a7  jns     loc_1803AD1B6
0x1803ad2ad  jmp     loc_1803AD18E
0x1803ad2b2  mov     edx, cs:nPriority; nPriority
0x1803ad2b8  mov     rcx, cs:hThread; hThread
0x1803ad2bf  call    cs:SetThreadPriority
0x1803ad2c6  nop     dword ptr [rax+rax+00h]
0x1803ad2cb  jmp     loc_1803AD1B6
```
