# TraceVprintfInternalA

- ea: `0x1800017c0`
- end: `0x180001c14`
- name: `TraceVprintfInternalA`
- size: `1108`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180001640`
- `0x1800016c0`
- `0x180001740`

## callees

- `0x1800017c0`
- `0x180003040`
- `0x1800035c0`
- `0x180003bb0`
- `0x180006794`
- `0x180009694`
- `0x180009810`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800019b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800019fa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800019b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800019fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800019a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800019e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001a25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001bc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001be4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800019a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800019e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001a25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001bc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001be4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001a33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bf2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001a33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800018c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ad8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001b27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800018c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ad8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001b27`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180001881`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180001881`

## pseudocode

```c
__int64 __fastcall TraceVprintfInternalA(unsigned int a1, int a2, const char *a3, va_list a4)
{
  va_list v4; // r15
  int v6; // r14d
  LPCRITICAL_SECTION v7; // r13
  __int64 v8; // rdi
  int v9; // eax
  int v11; // eax
  int v12; // edi
  int v13; // esi
  int v14; // ebp
  int v15; // r14d
  int v16; // r15d
  DWORD v17; // eax
  HRESULT v18; // eax
  size_t *v19; // r8
  char *v20; // rdi
  int v21; // ecx
  __int64 v22; // rsi
  unsigned int v23; // ebx
  int v24; // ebp
  size_t *v25; // r8
  char *v26; // r12
  HANDLE ProcessHeap; // rax
  HANDLE v28; // rax
  HANDLE v29; // rax
  HRESULT v30; // eax
  __int64 v31; // rcx
  int v32; // edx
  DWORD v33; // eax
  int wMilliseconds; // edi
  int wSecond; // esi
  int wMinute; // ebp
  int wHour; // r14d
  int wDay; // r15d
  int wMonth; // r12d
  DWORD CurrentThreadId; // eax
  DWORD v41; // eax
  HRESULT v42; // eax
  HANDLE v43; // rax
  HANDLE v44; // rax
  int argList; // [rsp+20h] [rbp-C8h]
  int v46; // [rsp+60h] [rbp-88h]
  int v48; // [rsp+6Ch] [rbp-7Ch]
  char *v49; // [rsp+70h] [rbp-78h]
  __int64 v50; // [rsp+78h] [rbp-70h]
  char *pszDest; // [rsp+80h] [rbp-68h]
  _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-58h] BYREF

  v4 = a4;
  v6 = a2;
  SystemTime = 0;
  if ( !a3 )
    return 0;
  v7 = g_server;
  if ( !g_server || !g_server[2].DebugInfo )
    return 0;
  v8 = a1;
  v9 = *((_DWORD *)&g_server[2].SpinCount + a1);
  if ( (a2 & 2) != 0 )
  {
    if ( (a2 & v9 & 0xFFFF0000) == 0 )
      return 0;
  }
  else if ( !v9 )
  {
    return 0;
  }
  AcquireReadLock(g_server);
  v22 = *(&v7[8].SpinCount + v8);
  v50 = v22;
  if ( !v22 )
  {
LABEL_47:
    ReleaseReadLock(v7);
    return 0;
  }
  AcquireReadLock(v22);
  if ( (*(_BYTE *)(v22 + 56) & 1) != 0 )
  {
LABEL_46:
    ReleaseReadLock(v22);
    goto LABEL_47;
  }
  v26 = (char *)_InterlockedExchange64((volatile __int64 *)&g_FormatBuffer, 0);
  pszDest = v26;
  v48 = 1;
  if ( !v26 )
  {
    v24 = 0;
    v46 = 0;
    ProcessHeap = GetProcessHeap();
    pszDest = (char *)HeapAlloc(ProcessHeap, 0, 0x1388u);
    v26 = pszDest;
    if ( pszDest )
      goto LABEL_21;
    goto LABEL_46;
  }
  v24 = 1;
  v46 = 1;
LABEL_21:
  v20 = (char *)_InterlockedExchange64((volatile __int64 *)&g_PrintBuffer, 0);
  v49 = v20;
  if ( !v20 )
  {
    v48 = 0;
    v28 = GetProcessHeap();
    v49 = (char *)HeapAlloc(v28, 0, 0x1388u);
    v20 = v49;
    if ( !v49 )
    {
      ReleaseReadLock(v22);
      ReleaseReadLock(v7);
      if ( v24 )
      {
        _InterlockedExchange64((volatile __int64 *)&g_FormatBuffer, (__int64)v26);
      }
      else
      {
        v29 = GetProcessHeap();
        HeapFree(v29, 0, v26);
      }
      return 0;
    }
  }
  if ( (v6 & 1) != 0 )
  {
    v30 = StringVPrintfWorkerA(v20, 0x1388u, v25, a3, v4);
    v31 = 0;
    v32 = (unsigned __int16)v30;
    if ( v30 >= 0 )
      v32 = 0;
    goto LABEL_36;
  }
  GetLocalTime(&SystemTime);
  v11 = v6 & 8;
  if ( (v6 & 4) != 0 )
  {
    wMilliseconds = SystemTime.wMilliseconds;
    wSecond = SystemTime.wSecond;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    if ( v11 )
    {
      wDay = SystemTime.wDay;
      wMonth = SystemTime.wMonth;
      CurrentThreadId = GetCurrentThreadId();
      argList = wMonth;
      v26 = pszDest;
      v18 = StringCbPrintfA(
              pszDest,
              0x1388u,
              "\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03u: %s",
              CurrentThreadId,
              argList,
              wDay,
              wHour,
              wMinute,
              wSecond,
              wMilliseconds,
              a3);
      v4 = a4;
    }
    else
    {
      v41 = GetCurrentThreadId();
      v18 = StringCbPrintfA(
              v26,
              0x1388u,
              "\r\n[%03d] %02u:%02u:%02u:%03u: %s",
              v41,
              wHour,
              wMinute,
              wSecond,
              wMilliseconds,
              a3);
    }
  }
  else
  {
    v12 = SystemTime.wSecond;
    v13 = SystemTime.wMinute;
    v14 = SystemTime.wHour;
    if ( (v6 & 8) == 0 )
    {
      v33 = GetCurrentThreadId();
      v18 = StringCbPrintfA(v26, 0x1388u, "\r\n[%03d] %02u:%02u:%02u: %s", v33, v14, v13, v12, a3);
      goto LABEL_11;
    }
    v15 = SystemTime.wDay;
    v16 = SystemTime.wMonth;
    v17 = GetCurrentThreadId();
    v18 = StringCbPrintfA(v26, 0x1388u, "\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s", v17, v16, v15, v14, v13, v12, a3);
    v4 = a4;
  }
  v6 = a2;
LABEL_11:
  v20 = v49;
  v21 = (unsigned __int16)v18;
  if ( v18 >= 0 )
    v21 = 0;
  if ( !v21 )
  {
    v42 = StringVPrintfWorkerA(v49, 0x1388u, v19, v26, v4);
    v22 = v50;
    v24 = v46;
    if ( v42 >= 0 )
      goto LABEL_38;
    v32 = (unsigned __int16)v42;
LABEL_36:
    if ( v32 )
    {
      v23 = 0;
      goto LABEL_39;
    }
LABEL_38:
    v23 = TraceWriteOutputA(v31, v22, v6, v20);
    goto LABEL_39;
  }
  v22 = v50;
  v23 = 0;
  v24 = v46;
LABEL_39:
  ReleaseReadLock(v22);
  ReleaseReadLock(v7);
  if ( v24 )
  {
    _InterlockedExchange64((volatile __int64 *)&g_FormatBuffer, (__int64)v26);
  }
  else
  {
    v43 = GetProcessHeap();
    HeapFree(v43, 0, v26);
  }
  if ( v48 )
  {
    _InterlockedExchange64((volatile __int64 *)&g_PrintBuffer, (__int64)v20);
  }
  else
  {
    v44 = GetProcessHeap();
    HeapFree(v44, 0, v20);
  }
  return v23;
}

```

## disassembly

```asm
0x1800017c0  mov     [rsp+arg_8], rbx
0x1800017c5  push    rbp
0x1800017c6  push    rsi
0x1800017c7  push    rdi
0x1800017c8  push    r12
0x1800017ca  push    r13
0x1800017cc  push    r14
0x1800017ce  push    r15
0x1800017d0  sub     rsp, 0B0h
0x1800017d7  mov     rax, cs:__security_cookie
0x1800017de  xor     rax, rsp
0x1800017e1  mov     [rsp+0E8h+var_48], rax
0x1800017e9  mov     [rsp+0E8h+var_60], r9
0x1800017f1  xorps   xmm0, xmm0
0x1800017f4  mov     [rsp+0E8h+var_84], edx
0x1800017f8  mov     r15, r9
0x1800017fb  mov     rbx, r8
0x1800017fe  mov     r14d, edx
0x180001801  movups  xmmword ptr [rsp+0E8h+SystemTime.wYear], xmm0
0x180001809  test    r8, r8
0x18000180c  jz      short loc_18000183A
0x18000180e  mov     r13, cs:g_server
0x180001815  test    r13, r13
0x180001818  jz      short loc_18000183A
0x18000181a  cmp     qword ptr [r13+50h], 0
0x18000181f  jz      short loc_18000183A
0x180001821  mov     edi, ecx
0x180001823  mov     eax, [r13+rdi*4+70h]
0x180001828  test    r14b, 2
0x18000182c  jnz     loc_180001937
0x180001832  test    eax, eax
0x180001834  jnz     loc_180001945
0x18000183a  xor     eax, eax
0x18000183c  mov     rcx, [rsp+0E8h+var_48]
0x180001844  xor     rcx, rsp; StackCookie
0x180001847  call    __security_check_cookie
0x18000184c  mov     rbx, [rsp+0E8h+arg_8]
0x180001854  add     rsp, 0B0h
0x18000185b  pop     r15
0x18000185d  pop     r14
0x18000185f  pop     r13
0x180001861  pop     r12
0x180001863  pop     rdi
0x180001864  pop     rsi
0x180001865  pop     rbp
0x180001866  retn
0x180001867  mov     [rsp+0E8h+var_80], 0
0x18000186f  test    r14b, 1
0x180001873  jnz     loc_180001A4A
0x180001879  lea     rcx, [rsp+0E8h+SystemTime]; lpSystemTime
0x180001881  call    cs:__imp_GetLocalTime
0x180001887  mov     eax, r14d
0x18000188a  and     eax, 8
0x18000188d  test    r14b, 4
0x180001891  jnz     loc_180001AA1
0x180001897  movzx   edi, [rsp+0E8h+SystemTime.wSecond]
0x18000189f  movzx   esi, [rsp+0E8h+SystemTime.wMinute]
0x1800018a7  movzx   ebp, [rsp+0E8h+SystemTime.wHour]
0x1800018af  test    eax, eax
0x1800018b1  jz      loc_180001A6E
0x1800018b7  movzx   r14d, [rsp+0E8h+SystemTime.wDay]
0x1800018c0  movzx   r15d, [rsp+0E8h+SystemTime.wMonth]
0x1800018c9  call    cs:__imp_GetCurrentThreadId
0x1800018cf  mov     [rsp+0E8h+var_A0], rbx
0x1800018d4  lea     r8, pszFormat; "\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s"
0x1800018db  mov     dword ptr [rsp+0E8h+var_A8], edi
0x1800018df  mov     r9d, eax
0x1800018e2  mov     dword ptr [rsp+0E8h+var_B0], esi
0x1800018e6  mov     edx, 1388h; cbDest
0x1800018eb  mov     [rsp+0E8h+var_B8], ebp
0x1800018ef  mov     rcx, r12; pszDest
0x1800018f2  mov     [rsp+0E8h+var_C0], r14d
0x1800018f7  mov     dword ptr [rsp+0E8h+argList], r15d
0x1800018fc  call    StringCbPrintfA
0x180001901  mov     r15, [rsp+0E8h+var_60]
0x180001909  jmp     loc_180001B5A
0x18000190e  mov     rdi, [rsp+0E8h+var_78]
0x180001913  mov     edx, eax
0x180001915  xor     eax, eax
0x180001917  movzx   ecx, dx
0x18000191a  test    edx, edx
0x18000191c  cmovns  ecx, eax
0x18000191f  test    ecx, ecx
0x180001921  jz      loc_180001B64
0x180001927  mov     rsi, [rsp+0E8h+var_70]
0x18000192c  mov     ebx, eax
0x18000192e  mov     ebp, [rsp+0E8h+var_88]
0x180001932  jmp     loc_180001BA3
0x180001937  and     eax, r14d
0x18000193a  test    eax, 0FFFF0000h
0x18000193f  jz      loc_18000183A
0x180001945  mov     rcx, r13
0x180001948  call    AcquireReadLock
0x18000194d  mov     rsi, [r13+rdi*8+160h]
0x180001955  mov     [rsp+0E8h+var_70], rsi
0x18000195a  test    rsi, rsi
0x18000195d  jz      loc_180001C07
0x180001963  mov     rcx, rsi
0x180001966  call    AcquireReadLock
0x18000196b  test    byte ptr [rsi+38h], 1
0x18000196f  jnz     loc_180001BFF
0x180001975  xor     r12d, r12d
0x180001978  mov     eax, 1
0x18000197d  xchg    r12, cs:g_FormatBuffer
0x180001984  mov     [rsp+0E8h+pszDest], r12
0x18000198c  mov     [rsp+0E8h+var_7C], eax
0x180001990  test    r12, r12
0x180001993  jz      short loc_18000199D
0x180001995  mov     ebp, eax
0x180001997  mov     [rsp+0E8h+var_88], eax
0x18000199b  jmp     short loc_1800019CE
0x18000199d  xor     ebp, ebp
0x18000199f  mov     [rsp+0E8h+var_88], ebp
0x1800019a3  call    cs:__imp_GetProcessHeap
0x1800019a9  xor     edx, edx; dwFlags
0x1800019ab  mov     r8d, 1388h; dwBytes
0x1800019b1  mov     rcx, rax; hHeap
0x1800019b4  call    cs:__imp_HeapAlloc
0x1800019ba  mov     [rsp+0E8h+pszDest], rax
0x1800019c2  mov     r12, rax
0x1800019c5  test    rax, rax
0x1800019c8  jz      loc_180001BFF
0x1800019ce  xor     edi, edi
0x1800019d0  xchg    rdi, cs:g_PrintBuffer
0x1800019d7  mov     [rsp+0E8h+var_78], rdi
0x1800019dc  test    rdi, rdi
0x1800019df  jnz     loc_180001867
0x1800019e5  mov     [rsp+0E8h+var_7C], edi
0x1800019e9  call    cs:__imp_GetProcessHeap
0x1800019ef  xor     edx, edx; dwFlags
0x1800019f1  mov     r8d, 1388h; dwBytes
0x1800019f7  mov     rcx, rax; hHeap
0x1800019fa  call    cs:__imp_HeapAlloc
0x180001a00  mov     [rsp+0E8h+var_78], rax
0x180001a05  mov     rdi, rax
0x180001a08  test    rax, rax
0x180001a0b  jnz     loc_180001867
0x180001a11  mov     rcx, rsi
0x180001a14  call    ReleaseReadLock
0x180001a19  mov     rcx, r13
0x180001a1c  call    ReleaseReadLock
0x180001a21  test    ebp, ebp
0x180001a23  jnz     short loc_180001A3E
0x180001a25  call    cs:__imp_GetProcessHeap
0x180001a2b  mov     r8, r12; lpMem
0x180001a2e  xor     edx, edx; dwFlags
0x180001a30  mov     rcx, rax; hHeap
0x180001a33  call    cs:__imp_HeapFree
0x180001a39  jmp     loc_18000183A
0x180001a3e  xchg    r12, cs:g_FormatBuffer
0x180001a45  jmp     loc_18000183A
0x180001a4a  mov     r9, rbx; pszFormat
0x180001a4d  mov     [rsp+0E8h+argList], r15; argList
0x180001a52  mov     edx, 1388h; cchDest
0x180001a57  mov     rcx, rdi; pszDest
0x180001a5a  call    StringVPrintfWorkerA
0x180001a5f  xor     ecx, ecx
0x180001a61  movzx   edx, ax
0x180001a64  test    eax, eax
0x180001a66  cmovns  edx, ecx
0x180001a69  jmp     loc_180001B89
0x180001a6e  call    cs:__imp_GetCurrentThreadId
0x180001a74  mov     [rsp+0E8h+var_B0], rbx
0x180001a79  lea     r8, a03d02u02u02uS_0; "\r\n[%03d] %02u:%02u:%02u: %s"
0x180001a80  mov     [rsp+0E8h+var_B8], edi
0x180001a84  mov     r9d, eax
0x180001a87  mov     [rsp+0E8h+var_C0], esi
0x180001a8b  mov     edx, 1388h; cbDest
0x180001a90  mov     rcx, r12; pszDest
0x180001a93  mov     dword ptr [rsp+0E8h+argList], ebp
0x180001a97  call    StringCbPrintfA
0x180001a9c  jmp     loc_18000190E
0x180001aa1  movzx   edi, [rsp+0E8h+SystemTime.wMilliseconds]
0x180001aa9  movzx   esi, [rsp+0E8h+SystemTime.wSecond]
0x180001ab1  movzx   ebp, [rsp+0E8h+SystemTime.wMinute]
0x180001ab9  movzx   r14d, [rsp+0E8h+SystemTime.wHour]
0x180001ac2  test    eax, eax
0x180001ac4  jz      short loc_180001B27
0x180001ac6  movzx   r15d, [rsp+0E8h+SystemTime.wDay]
0x180001acf  movzx   r12d, [rsp+0E8h+SystemTime.wMonth]
0x180001ad8  call    cs:__imp_GetCurrentThreadId
0x180001ade  mov     [rsp+0E8h+var_98], rbx
0x180001ae3  lea     r8, a03d02u02u02u02_1; "\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03"...
0x180001aea  mov     dword ptr [rsp+0E8h+var_A0], edi
0x180001aee  mov     r9d, eax
0x180001af1  mov     dword ptr [rsp+0E8h+var_A8], esi
0x180001af5  mov     edx, 1388h; cbDest
0x180001afa  mov     dword ptr [rsp+0E8h+var_B0], ebp
0x180001afe  mov     [rsp+0E8h+var_B8], r14d
0x180001b03  mov     [rsp+0E8h+var_C0], r15d
0x180001b08  mov     dword ptr [rsp+0E8h+argList], r12d
0x180001b0d  mov     r12, [rsp+0E8h+pszDest]
0x180001b15  mov     rcx, r12; pszDest
0x180001b18  call    StringCbPrintfA
0x180001b1d  mov     r15, [rsp+0E8h+var_60]
0x180001b25  jmp     short loc_180001B5A
0x180001b27  call    cs:__imp_GetCurrentThreadId
0x180001b2d  mov     [rsp+0E8h+var_A8], rbx
0x180001b32  lea     r8, a03d02u02u02u03_1; "\r\n[%03d] %02u:%02u:%02u:%03u: %s"
0x180001b39  mov     dword ptr [rsp+0E8h+var_B0], edi
0x180001b3d  mov     r9d, eax
0x180001b40  mov     [rsp+0E8h+var_B8], esi
0x180001b44  mov     edx, 1388h; cbDest
0x180001b49  mov     [rsp+0E8h+var_C0], ebp
0x180001b4d  mov     rcx, r12; pszDest
0x180001b50  mov     dword ptr [rsp+0E8h+argList], r14d
0x180001b55  call    StringCbPrintfA
0x180001b5a  mov     r14d, [rsp+0E8h+var_84]
0x180001b5f  jmp     loc_18000190E
0x180001b64  mov     r9, r12; pszFormat
0x180001b67  mov     [rsp+0E8h+argList], r15; argList
0x180001b6c  mov     edx, 1388h; cchDest
0x180001b71  mov     rcx, rdi; pszDest
0x180001b74  call    StringVPrintfWorkerA
0x180001b79  mov     rsi, [rsp+0E8h+var_70]
0x180001b7e  mov     ebp, [rsp+0E8h+var_88]
0x180001b82  test    eax, eax
0x180001b84  jns     short loc_180001B93
0x180001b86  movzx   edx, ax
0x180001b89  test    edx, edx
0x180001b8b  jz      short loc_180001B93
0x180001b8d  mov     ebx, [rsp+0E8h+var_80]
0x180001b91  jmp     short loc_180001BA3
0x180001b93  mov     r9, rdi
0x180001b96  mov     r8d, r14d
0x180001b99  mov     rdx, rsi
0x180001b9c  call    TraceWriteOutputA
0x180001ba1  mov     ebx, eax
0x180001ba3  mov     rcx, rsi
0x180001ba6  call    ReleaseReadLock
0x180001bab  mov     rcx, r13
0x180001bae  call    ReleaseReadLock
0x180001bb3  test    ebp, ebp
0x180001bb5  jz      short loc_180001BC0
0x180001bb7  xchg    r12, cs:g_FormatBuffer
0x180001bbe  jmp     short loc_180001BD4
0x180001bc0  call    cs:__imp_GetProcessHeap
0x180001bc6  mov     r8, r12; lpMem
0x180001bc9  xor     edx, edx; dwFlags
0x180001bcb  mov     rcx, rax; hHeap
0x180001bce  call    cs:__imp_HeapFree
0x180001bd4  cmp     [rsp+0E8h+var_7C], 0
0x180001bd9  jz      short loc_180001BE4
0x180001bdb  xchg    rdi, cs:g_PrintBuffer
0x180001be2  jmp     short loc_180001BF8
0x180001be4  call    cs:__imp_GetProcessHeap
0x180001bea  mov     r8, rdi; lpMem
0x180001bed  xor     edx, edx; dwFlags
0x180001bef  mov     rcx, rax; hHeap
0x180001bf2  call    cs:__imp_HeapFree
0x180001bf8  mov     eax, ebx
0x180001bfa  jmp     loc_18000183C
0x180001bff  mov     rcx, rsi
0x180001c02  call    ReleaseReadLock
0x180001c07  mov     rcx, r13
0x180001c0a  call    ReleaseReadLock
0x180001c0f  jmp     loc_18000183A
```
