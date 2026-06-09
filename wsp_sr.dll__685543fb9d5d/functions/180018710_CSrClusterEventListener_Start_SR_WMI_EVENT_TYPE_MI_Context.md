# CSrClusterEventListener::Start(_SR_WMI_EVENT_TYPE,_MI_Context *)

- ea: `0x180018710`
- end: `0x180018813`
- name: `?Start@CSrClusterEventListener@@QEAAKW4_SR_WMI_EVENT_TYPE@@PEAU_MI_Context@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001881c`

## callees

- `0x1800067cc`
- `0x1800067fc`
- `0x180018710`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187a4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001878f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001878f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001875a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001875a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800187cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800187cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSrClusterEventListener::Start(__int64 a1, int a2, __int64 a3)
{
  DWORD LastError; // edi
  HANDLE Thread; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids);
  LastError = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  if ( !*(_BYTE *)(a1 + 28) )
  {
    *(_QWORD *)(a1 + 16) = a3;
    *(_BYTE *)(a1 + 28) = 1;
    *(_DWORD *)(a1 + 24) = a2;
    Thread = CreateThread(0, 0, SrClusterEventsWorkerThread, (LPVOID)a1, 0, 0);
    *(_QWORD *)(a1 + 32) = Thread;
    if ( !Thread )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        *(_BYTE *)(a1 + 28) = 0;
        *(_QWORD *)(a1 + 16) = 0;
        *(_DWORD *)(a1 + 24) = 0;
      }
    }
  }
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 8));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180018710  push    rbx
0x180018712  push    rbp
0x180018713  push    rsi
0x180018714  push    rdi
0x180018715  push    r12
0x180018717  push    r14
0x180018719  sub     rsp, 38h
0x18001871d  mov     rbp, r8
0x180018720  mov     r14d, edx
0x180018723  mov     rbx, rcx
0x180018726  mov     rcx, cs:WPP_GLOBAL_Control
0x18001872d  lea     r12, WPP_GLOBAL_Control
0x180018734  cmp     rcx, r12
0x180018737  jz      short loc_180018754
0x180018739  test    byte ptr [rcx+1Ch], 4
0x18001873d  jz      short loc_180018754
0x18001873f  mov     rcx, [rcx+10h]
0x180018743  lea     r8, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids
0x18001874a  mov     edx, 18h
0x18001874f  call    WPP_SF_
0x180018754  lea     rcx, [rbx+8]; SRWLock
0x180018758  xor     edi, edi
0x18001875a  call    cs:__imp_AcquireSRWLockExclusive
0x180018761  nop     dword ptr [rax+rax+00h]
0x180018766  cmp     [rbx+1Ch], dil
0x18001876a  jnz     short loc_1800187C9
0x18001876c  mov     [rsp+68h+lpThreadId], rdi; lpThreadId
0x180018771  lea     r8, ?SrClusterEventsWorkerThread@@YAKPEAX@Z; lpStartAddress
0x180018778  mov     r9, rbx; lpParameter
0x18001877b  mov     [rsp+68h+dwCreationFlags], edi; dwCreationFlags
0x18001877f  xor     edx, edx; dwStackSize
0x180018781  mov     [rbx+10h], rbp
0x180018785  xor     ecx, ecx; lpThreadAttributes
0x180018787  mov     byte ptr [rbx+1Ch], 1
0x18001878b  mov     [rbx+18h], r14d
0x18001878f  call    cs:__imp_CreateThread
0x180018796  nop     dword ptr [rax+rax+00h]
0x18001879b  mov     [rbx+20h], rax
0x18001879f  test    rax, rax
0x1800187a2  jnz     short loc_1800187C9
0x1800187a4  call    cs:__imp_GetLastError
0x1800187ab  nop     dword ptr [rax+rax+00h]
0x1800187b0  mov     edi, eax
0x1800187b2  test    eax, eax
0x1800187b4  jz      short loc_1800187C9
0x1800187b6  mov     byte ptr [rbx+1Ch], 0
0x1800187ba  mov     qword ptr [rbx+10h], 0
0x1800187c2  mov     dword ptr [rbx+18h], 0
0x1800187c9  lea     rcx, [rbx+8]; SRWLock
0x1800187cd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800187d4  nop     dword ptr [rax+rax+00h]
0x1800187d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187e0  cmp     rcx, r12
0x1800187e3  jz      short loc_180018803
0x1800187e5  test    byte ptr [rcx+1Ch], 1
0x1800187e9  jz      short loc_180018803
0x1800187eb  mov     rcx, [rcx+10h]
0x1800187ef  lea     r8, WPP_2842f3940e023d3d9a1de50e7181de48_Traceguids
0x1800187f6  mov     edx, 19h
0x1800187fb  mov     r9d, edi
0x1800187fe  call    WPP_SF_d
0x180018803  mov     eax, edi
0x180018805  add     rsp, 38h
0x180018809  pop     r14
0x18001880b  pop     r12
0x18001880d  pop     rdi
0x18001880e  pop     rsi
0x18001880f  pop     rbp
0x180018810  pop     rbx
0x180018811  retn
```
