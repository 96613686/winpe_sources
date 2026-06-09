# CContainer::Shutdown(void)

- ea: `0x140006400`
- end: `0x1400064a5`
- name: `?Shutdown@CContainer@@UEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(CContainer *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140005c40`
- `0x140006400`
- `0x14000656c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006413`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006413`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000644f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000644f`

## pseudocode

```c
__int64 __fastcall CContainer::Shutdown(CContainer *this)
{
  signed int Win32Error; // ebx

  Win32Error = 0;
  CContainer::s_hEventShutdown = CreateEventW(0, 1, 0, 0);
  if ( CContainer::s_hEventShutdown || (Win32Error = HrFromLastWin32Error(), Win32Error >= 0) )
  {
    CContainer::s_hThreadShutdown = CreateThread(0, 0, CContainer::ShutdownThread, 0, 0, 0);
    if ( !CContainer::s_hThreadShutdown )
      Win32Error = HrFromLastWin32Error();
  }
  if ( Win32Error
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_5d760b8fc4213c791c7b68ae082a6cff_Traceguids,
      (unsigned int)Win32Error);
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x140006400  push    rbx
0x140006402  sub     rsp, 30h
0x140006406  xor     ebx, ebx
0x140006408  xor     r9d, r9d; lpName
0x14000640b  xor     r8d, r8d; bInitialState
0x14000640e  xor     ecx, ecx; lpEventAttributes
0x140006410  lea     edx, [rbx+1]; bManualReset
0x140006413  call    cs:__imp_CreateEventW
0x140006419  mov     cs:?s_hEventShutdown@CContainer@@0PEAXEA, rax; void * CContainer::s_hEventShutdown
0x140006420  test    rax, rax
0x140006423  jnz     short loc_140006430
0x140006425  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x14000642a  mov     ebx, eax
0x14000642c  test    eax, eax
0x14000642e  js      short loc_140006468
0x140006430  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x140006439  lea     r8, ?ShutdownThread@CContainer@@CAKPEAX@Z; lpStartAddress
0x140006440  xor     r9d, r9d; lpParameter
0x140006443  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14000644b  xor     edx, edx; dwStackSize
0x14000644d  xor     ecx, ecx; lpThreadAttributes
0x14000644f  call    cs:__imp_CreateThread
0x140006455  mov     cs:?s_hThreadShutdown@CContainer@@0PEAXEA, rax; void * CContainer::s_hThreadShutdown
0x14000645c  test    rax, rax
0x14000645f  jnz     short loc_140006468
0x140006461  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x140006466  mov     ebx, eax
0x140006468  test    ebx, ebx
0x14000646a  jz      short loc_14000649D
0x14000646c  mov     rcx, cs:WPP_GLOBAL_Control
0x140006473  lea     rax, WPP_GLOBAL_Control
0x14000647a  cmp     rcx, rax
0x14000647d  jz      short loc_14000649D
0x14000647f  test    byte ptr [rcx+1Ch], 1
0x140006483  jz      short loc_14000649D
0x140006485  mov     rcx, [rcx+10h]
0x140006489  lea     r8, WPP_5d760b8fc4213c791c7b68ae082a6cff_Traceguids
0x140006490  mov     edx, 0Bh
0x140006495  mov     r9d, ebx
0x140006498  call    WPP_SF_d
0x14000649d  mov     eax, ebx
0x14000649f  add     rsp, 30h
0x1400064a3  pop     rbx
0x1400064a4  retn
```
