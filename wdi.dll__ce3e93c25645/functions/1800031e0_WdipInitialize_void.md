# WdipInitialize(void)

- ea: `0x1800031e0`
- end: `0x18000340b`
- name: `?WdipInitialize@@YAHXZ`
- size: `555`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800030c0`

## callees

- `0x180002ba0`
- `0x1800031e0`
- `0x180007280`
- `0x18000f1c2`

## import_xrefs

- `ntdll!AlpcMaxAllowedMessageLength` at `0x180003202`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180003202`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033e6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033e6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800032f8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800032f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003302`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003251`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003251`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000320b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000337d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000339f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000320b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000337d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000339f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000321c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800032b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000321c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800032b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000338b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000338b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033ad`

## string_xrefs

- `0x180003285`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`

## pseudocode

```c
__int64 WdipInitialize(void)
{
  SIZE_T v0; // rbx
  HANDLE ProcessHeap; // rax
  int v2; // r8d
  char v3; // di
  signed int Args; // eax
  bool v5; // sf
  HANDLE v6; // rax
  void *v7; // rax
  void *v8; // rbx
  signed int LastError; // eax
  bool v10; // sf
  void *v11; // rbx
  HANDLE v12; // rax
  void *v13; // rbx
  HANDLE v14; // rax
  size_t Size; // [rsp+60h] [rbp+8h] BYREF

  LODWORD(Size) = 0;
  g_pLocalServSid = 0;
  dword_1800176A8 = 0;
  dword_180017670 = 0;
  v0 = AlpcMaxAllowedMessageLength();
  ProcessHeap = GetProcessHeap();
  g_PreAllocatedBuffer = HeapAlloc(ProcessHeap, 8u, v0);
  if ( g_PreAllocatedBuffer )
  {
    Args = EventRegister(&WDI_LIBRARY_PROVIDER, 0, 0, &g_hETW);
    v5 = Args < 0;
    if ( Args > 0 )
    {
      Args = (unsigned __int16)Args | 0x80070000;
      v5 = Args < 0;
    }
    if ( v5 )
    {
      v3 = Args;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
        (int)L"WdipETWRegister",
        772,
        (int)L"Error = %d",
        Args);
      v2 = 425;
    }
    else
    {
      LODWORD(Size) = 68;
      v6 = GetProcessHeap();
      v7 = HeapAlloc(v6, 8u, 0x44u);
      g_pLocalServSid = v7;
      v8 = v7;
      if ( v7 )
      {
        memset_0(v7, 0, (unsigned int)Size);
        if ( CreateWellKnownSid(WinLocalServiceSid, 0, v8, (DWORD *)&Size) )
          goto LABEL_14;
        LastError = GetLastError();
        v10 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v10 = LastError < 0;
        }
        if ( !v10 )
        {
LABEL_14:
          LastError = WdipInitializeCriticalSection(&g_csWDI);
          if ( LastError >= 0 )
          {
            LastError = WdipInitializeCriticalSection(&g_csPreAllocated);
            if ( LastError >= 0 )
              return 1;
            v2 = 447;
          }
          else
          {
            v2 = 444;
          }
        }
        else
        {
          v2 = 441;
        }
        v3 = LastError;
      }
      else
      {
        v2 = 433;
        v3 = 14;
      }
    }
  }
  else
  {
    v2 = 419;
    v3 = 14;
  }
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
    (int)L"WdipInitialize",
    v2,
    (int)L"Error = %d",
    v3);
  v11 = g_PreAllocatedBuffer;
  v12 = GetProcessHeap();
  HeapFree(v12, 0, v11);
  v13 = g_pLocalServSid;
  g_PreAllocatedBuffer = 0;
  v14 = GetProcessHeap();
  HeapFree(v14, 0, v13);
  g_pLocalServSid = 0;
  if ( dword_1800176A8 == 1 )
  {
    DeleteCriticalSection(&g_csWDI);
    dword_1800176A8 = 0;
  }
  if ( dword_180017670 == 1 )
  {
    DeleteCriticalSection(&g_csPreAllocated);
    dword_180017670 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800031e0  push    rbx
0x1800031e2  push    rbp
0x1800031e3  push    rsi
0x1800031e4  push    rdi
0x1800031e5  sub     rsp, 38h
0x1800031e9  xor     ebp, ebp
0x1800031eb  mov     dword ptr [rsp+58h+Size], ebp
0x1800031ef  mov     cs:g_pLocalServSid, rbp
0x1800031f6  mov     cs:dword_1800176A8, ebp
0x1800031fc  mov     cs:dword_180017670, ebp
0x180003202  call    cs:__imp_AlpcMaxAllowedMessageLength
0x180003208  mov     rbx, rax
0x18000320b  call    cs:__imp_GetProcessHeap
0x180003211  mov     r8, rbx; dwBytes
0x180003214  mov     edx, 8; dwFlags
0x180003219  mov     rcx, rax; hHeap
0x18000321c  call    cs:__imp_HeapAlloc
0x180003222  mov     cs:g_PreAllocatedBuffer, rax
0x180003229  test    rax, rax
0x18000322c  jnz     short loc_18000323E
0x18000322e  mov     r8d, 1A3h
0x180003234  mov     edi, 0Eh
0x180003239  jmp     loc_180003355
0x18000323e  lea     r9, g_hETW; RegHandle
0x180003245  xor     r8d, r8d; CallbackContext
0x180003248  xor     edx, edx; EnableCallback
0x18000324a  lea     rcx, WDI_LIBRARY_PROVIDER; ProviderId
0x180003251  call    cs:__imp_EventRegister
0x180003257  test    eax, eax
0x180003259  jle     short loc_180003265
0x18000325b  movzx   eax, ax
0x18000325e  or      eax, 80070000h
0x180003263  test    eax, eax
0x180003265  jns     short loc_18000329C
0x180003267  movzx   edi, ax
0x18000326a  lea     rbx, aErrorD_0; "Error = %d"
0x180003271  mov     r9, rbx; int
0x180003274  mov     dword ptr [rsp+58h+Args], edi; Args
0x180003278  mov     r8d, 304h; int
0x18000327e  lea     rdx, aWdipetwregiste; "WdipETWRegister"
0x180003285  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000328c  call    WdipTraceError
0x180003291  mov     r8d, 1A9h
0x180003297  jmp     loc_18000335C
0x18000329c  mov     dword ptr [rsp+58h+Size], 44h ; 'D'
0x1800032a4  call    cs:__imp_GetProcessHeap
0x1800032aa  mov     edx, 8; dwFlags
0x1800032af  mov     r8d, 44h ; 'D'; dwBytes
0x1800032b5  mov     rcx, rax; hHeap
0x1800032b8  call    cs:__imp_HeapAlloc
0x1800032be  mov     cs:g_pLocalServSid, rax
0x1800032c5  mov     rbx, rax
0x1800032c8  test    rax, rax
0x1800032cb  jnz     short loc_1800032DA
0x1800032cd  mov     r8d, 1B1h
0x1800032d3  mov     edi, 0Eh
0x1800032d8  jmp     short loc_180003355
0x1800032da  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x1800032df  xor     edx, edx; Val
0x1800032e1  mov     rcx, rbx; void *
0x1800032e4  call    memset_0
0x1800032e9  lea     r9, [rsp+58h+Size]; cbSid
0x1800032ee  mov     r8, rbx; pSid
0x1800032f1  xor     edx, edx; DomainSid
0x1800032f3  mov     ecx, 17h; WellKnownSidType
0x1800032f8  call    cs:__imp_CreateWellKnownSid
0x1800032fe  test    eax, eax
0x180003300  jnz     short loc_180003320
0x180003302  call    cs:__imp_GetLastError
0x180003308  test    eax, eax
0x18000330a  jle     short loc_180003316
0x18000330c  movzx   eax, ax
0x18000330f  or      eax, 80070000h
0x180003314  test    eax, eax
0x180003316  jns     short loc_180003320
0x180003318  mov     r8d, 1B9h
0x18000331e  jmp     short loc_180003352
0x180003320  lea     rcx, g_csWDI
0x180003327  call    WdipInitializeCriticalSection
0x18000332c  test    eax, eax
0x18000332e  jns     short loc_180003338
0x180003330  mov     r8d, 1BCh
0x180003336  jmp     short loc_180003352
0x180003338  lea     rcx, g_csPreAllocated
0x18000333f  call    WdipInitializeCriticalSection
0x180003344  test    eax, eax
0x180003346  jns     loc_1800033FD
0x18000334c  mov     r8d, 1BFh; int
0x180003352  movzx   edi, ax
0x180003355  lea     rbx, aErrorD_0; "Error = %d"
0x18000335c  lea     rdx, aWdipinitialize_0; "WdipInitialize"
0x180003363  mov     dword ptr [rsp+58h+Args], edi; Args
0x180003367  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000336e  mov     r9, rbx; int
0x180003371  call    WdipTraceError
0x180003376  mov     rbx, cs:g_PreAllocatedBuffer
0x18000337d  call    cs:__imp_GetProcessHeap
0x180003383  mov     r8, rbx; lpMem
0x180003386  xor     edx, edx; dwFlags
0x180003388  mov     rcx, rax; hHeap
0x18000338b  call    cs:__imp_HeapFree
0x180003391  mov     rbx, cs:g_pLocalServSid
0x180003398  mov     cs:g_PreAllocatedBuffer, rbp
0x18000339f  call    cs:__imp_GetProcessHeap
0x1800033a5  mov     r8, rbx; lpMem
0x1800033a8  xor     edx, edx; dwFlags
0x1800033aa  mov     rcx, rax; hHeap
0x1800033ad  call    cs:__imp_HeapFree
0x1800033b3  cmp     cs:dword_1800176A8, 1
0x1800033ba  mov     cs:g_pLocalServSid, rbp
0x1800033c1  jnz     short loc_1800033D6
0x1800033c3  lea     rcx, g_csWDI; lpCriticalSection
0x1800033ca  call    cs:__imp_DeleteCriticalSection
0x1800033d0  mov     cs:dword_1800176A8, ebp
0x1800033d6  cmp     cs:dword_180017670, 1
0x1800033dd  jnz     short loc_1800033F2
0x1800033df  lea     rcx, g_csPreAllocated; lpCriticalSection
0x1800033e6  call    cs:__imp_DeleteCriticalSection
0x1800033ec  mov     cs:dword_180017670, ebp
0x1800033f2  mov     eax, ebp
0x1800033f4  add     rsp, 38h
0x1800033f8  pop     rdi
0x1800033f9  pop     rsi
0x1800033fa  pop     rbp
0x1800033fb  pop     rbx
0x1800033fc  retn
0x1800033fd  mov     eax, 1
0x180003402  add     rsp, 38h
0x180003406  pop     rdi
0x180003407  pop     rsi
0x180003408  pop     rbp
0x180003409  pop     rbx
0x18000340a  retn
```
