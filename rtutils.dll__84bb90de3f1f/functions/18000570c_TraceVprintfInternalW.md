# TraceVprintfInternalW

- ea: `0x18000570c`
- end: `0x180005af5`
- name: `TraceVprintfInternalW`
- size: `1001`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180005040`
- `0x1800050c0`
- `0x1800056a0`

## callees

- `0x180003bb0`
- `0x1800049c8`
- `0x180004bb8`
- `0x18000570c`
- `0x1800078b0`
- `0x180009694`
- `0x180009810`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800057f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005870`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800057f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005870`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000585f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005896`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005aa3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000585f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005896`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005aa3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005ab2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005ab2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005934`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000598a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800059d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005934`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000598a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800059d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800058bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800058bf`

## pseudocode

```c
__int64 __fastcall TraceVprintfInternalW(unsigned int a1, int a2, const wchar_t *a3, va_list a4)
{
  int v5; // r12d
  LPCRITICAL_SECTION v6; // r14
  __int64 v7; // r15
  int v8; // eax
  __int64 v10; // r15
  size_t *v11; // r8
  void *v12; // r13
  int v13; // edi
  HANDLE ProcessHeap; // rax
  wchar_t *v15; // rbx
  HRESULT v16; // eax
  __int64 v17; // rcx
  int v18; // edx
  HANDLE v19; // rax
  HANDLE v20; // rax
  int v21; // ebx
  int v22; // edi
  int v23; // esi
  int v24; // r14d
  int v25; // r15d
  DWORD v26; // eax
  HRESULT v27; // eax
  size_t *v28; // r8
  DWORD v29; // eax
  int wMilliseconds; // ebx
  int wSecond; // edi
  int wMinute; // esi
  int wHour; // r14d
  int wDay; // r15d
  int wMonth; // r12d
  DWORD CurrentThreadId; // eax
  DWORD v37; // eax
  int v38; // edx
  unsigned int v39; // eax
  int v40; // ecx
  HRESULT v41; // eax
  unsigned int v42; // ebx
  HANDLE v43; // rax
  HANDLE v44; // rax
  int v46; // [rsp+64h] [rbp-35h]
  int v47; // [rsp+68h] [rbp-31h]
  wchar_t *pszDest; // [rsp+78h] [rbp-21h]
  LPCRITICAL_SECTION v51; // [rsp+88h] [rbp-11h]
  __int64 v52; // [rsp+90h] [rbp-9h]
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp+7h] BYREF

  v5 = a2;
  SystemTime = 0;
  if ( !a3 )
    return 0;
  v6 = g_server;
  v51 = g_server;
  if ( !g_server || !g_server[2].DebugInfo )
    return 0;
  v7 = a1;
  v8 = *((_DWORD *)&g_server[2].SpinCount + a1);
  if ( (a2 & 2) != 0 ? (a2 & v8 & 0xFFFF0000) == 0 : v8 == 0 )
    return 0;
  AcquireReadLock(g_server);
  v10 = *(&v6[8].SpinCount + v7);
  v52 = v10;
  if ( !v10 )
    goto LABEL_48;
  AcquireReadLock(v10);
  if ( (*(_BYTE *)(v10 + 56) & 1) != 0 )
    goto LABEL_47;
  v12 = (void *)_InterlockedExchange64((volatile __int64 *)&g_FormatBuffer, 0);
  if ( v12 )
  {
    v13 = 1;
    v46 = 1;
    goto LABEL_13;
  }
  v13 = 0;
  v46 = 0;
  ProcessHeap = GetProcessHeap();
  v12 = HeapAlloc(ProcessHeap, 0, 0x1388u);
  if ( !v12 )
  {
LABEL_47:
    ReleaseReadLock(v10);
LABEL_48:
    ReleaseReadLock(v6);
    return 0;
  }
LABEL_13:
  v15 = (wchar_t *)_InterlockedExchange64((volatile __int64 *)&g_PrintBuffer, 0);
  pszDest = v15;
  if ( v15 )
  {
    v47 = 1;
    goto LABEL_15;
  }
  v47 = 0;
  v19 = GetProcessHeap();
  pszDest = (wchar_t *)HeapAlloc(v19, 0, 0x1388u);
  v15 = pszDest;
  if ( !pszDest )
  {
    ReleaseReadLock(v10);
    ReleaseReadLock(v6);
    if ( v13 )
    {
      _InterlockedExchange64((volatile __int64 *)&g_FormatBuffer, (__int64)v12);
    }
    else
    {
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v12);
    }
    return 0;
  }
LABEL_15:
  if ( (v5 & 1) != 0 )
  {
    v16 = StringVPrintfWorkerW(v15, 0x9C4u, v11, a3, a4);
    v17 = 0;
    v18 = (unsigned __int16)v16;
    if ( v16 >= 0 )
      v18 = 0;
LABEL_36:
    if ( v18 )
    {
      v42 = 0;
      goto LABEL_40;
    }
    goto LABEL_37;
  }
  GetLocalTime(&SystemTime);
  if ( (v5 & 4) != 0 )
  {
    wMilliseconds = SystemTime.wMilliseconds;
    wSecond = SystemTime.wSecond;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    if ( (v5 & 8) != 0 )
    {
      wDay = SystemTime.wDay;
      wMonth = SystemTime.wMonth;
      CurrentThreadId = GetCurrentThreadId();
      v27 = StringCbPrintfW(
              (STRSAFE_LPWSTR)v12,
              0x1388u,
              L"\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03u: %s",
              CurrentThreadId,
              wMonth,
              wDay,
              wHour,
              wMinute,
              wSecond,
              wMilliseconds,
              a3);
      v10 = v52;
      v5 = a2;
    }
    else
    {
      v37 = GetCurrentThreadId();
      v27 = StringCbPrintfW(
              (STRSAFE_LPWSTR)v12,
              0x1388u,
              L"\r\n[%03d] %02u:%02u:%02u:%03u: %s",
              v37,
              wHour,
              wMinute,
              wSecond,
              wMilliseconds,
              a3);
    }
  }
  else
  {
    v21 = SystemTime.wSecond;
    v22 = SystemTime.wMinute;
    v23 = SystemTime.wHour;
    if ( (v5 & 8) == 0 )
    {
      v29 = GetCurrentThreadId();
      v27 = StringCbPrintfW((STRSAFE_LPWSTR)v12, 0x1388u, L"\r\n[%03d] %02u:%02u:%02u: %s", v29, v23, v22, v21, a3);
      goto LABEL_31;
    }
    v24 = SystemTime.wDay;
    v25 = SystemTime.wMonth;
    v26 = GetCurrentThreadId();
    v27 = StringCbPrintfW(
            (STRSAFE_LPWSTR)v12,
            0x1388u,
            L"\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s",
            v26,
            v25,
            v24,
            v23,
            v22,
            v21,
            a3);
    v10 = v52;
  }
  v6 = v51;
LABEL_31:
  v38 = v27;
  v39 = 0;
  v40 = (unsigned __int16)v38;
  if ( v38 >= 0 )
    v40 = 0;
  if ( v40 )
    goto LABEL_38;
  v15 = pszDest;
  v41 = StringVPrintfWorkerW(pszDest, 0x9C4u, v28, (STRSAFE_LPCWSTR)v12, a4);
  if ( v41 < 0 )
  {
    v18 = (unsigned __int16)v41;
    goto LABEL_36;
  }
LABEL_37:
  v39 = TraceWriteOutputW(v17, v10, v5, v15);
LABEL_38:
  v42 = v39;
LABEL_40:
  ReleaseReadLock(v10);
  ReleaseReadLock(v6);
  if ( v46 )
  {
    _InterlockedExchange64((volatile __int64 *)&g_FormatBuffer, (__int64)v12);
  }
  else
  {
    v43 = GetProcessHeap();
    HeapFree(v43, 0, v12);
  }
  if ( v47 )
  {
    _InterlockedExchange64((volatile __int64 *)&g_PrintBuffer, (__int64)pszDest);
  }
  else
  {
    v44 = GetProcessHeap();
    HeapFree(v44, 0, pszDest);
  }
  return v42;
}

```

## disassembly

```asm
0x18000570c  mov     [rsp-8+arg_8], rbx
0x180005711  push    rbp
0x180005712  push    rsi
0x180005713  push    rdi
0x180005714  push    r12
0x180005716  push    r13
0x180005718  push    r14
0x18000571a  push    r15
0x18000571c  lea     rbp, [rsp-27h]
0x180005721  sub     rsp, 0C0h
0x180005728  mov     rax, cs:__security_cookie
0x18000572f  xor     rax, rsp
0x180005732  mov     [rbp+57h+var_40], rax
0x180005736  mov     [rbp+57h+var_58], r9
0x18000573a  xorps   xmm0, xmm0
0x18000573d  mov     [rbp+57h+var_80], r8
0x180005741  mov     rsi, r8
0x180005744  mov     [rbp+57h+var_70], edx
0x180005747  mov     r12d, edx
0x18000574a  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18000574e  test    r8, r8
0x180005751  jz      loc_180005ACC
0x180005757  mov     r14, cs:g_server
0x18000575e  mov     [rbp+57h+var_68], r14
0x180005762  test    r14, r14
0x180005765  jz      loc_180005ACC
0x18000576b  cmp     qword ptr [r14+50h], 0
0x180005770  jz      loc_180005ACC
0x180005776  mov     r15d, ecx
0x180005779  mov     eax, [r14+r15*4+70h]
0x18000577e  test    r12b, 2
0x180005782  jz      short loc_18000578D
0x180005784  and     eax, edx
0x180005786  test    eax, 0FFFF0000h
0x18000578b  jmp     short loc_18000578F
0x18000578d  test    eax, eax
0x18000578f  jz      loc_180005ACC
0x180005795  mov     rcx, r14
0x180005798  call    AcquireReadLock
0x18000579d  mov     r15, [r14+r15*8+160h]
0x1800057a5  mov     [rbp+57h+var_60], r15
0x1800057a9  test    r15, r15
0x1800057ac  jz      loc_180005AC4
0x1800057b2  mov     rcx, r15
0x1800057b5  call    AcquireReadLock
0x1800057ba  test    byte ptr [r15+38h], 1
0x1800057bf  jnz     loc_180005ABC
0x1800057c5  xor     r13d, r13d
0x1800057c8  xchg    r13, cs:g_FormatBuffer
0x1800057cf  test    r13, r13
0x1800057d2  jz      short loc_1800057DE
0x1800057d4  mov     edi, 1
0x1800057d9  mov     [rbp+57h+var_8C], edi
0x1800057dc  jmp     short loc_180005806
0x1800057de  xor     edi, edi
0x1800057e0  mov     [rbp+57h+var_8C], edi
0x1800057e3  call    cs:__imp_GetProcessHeap
0x1800057e9  xor     edx, edx; dwFlags
0x1800057eb  mov     r8d, 1388h; dwBytes
0x1800057f1  mov     rcx, rax; hHeap
0x1800057f4  call    cs:__imp_HeapAlloc
0x1800057fa  mov     r13, rax
0x1800057fd  test    rax, rax
0x180005800  jz      loc_180005ABC
0x180005806  xor     ebx, ebx
0x180005808  xchg    rbx, cs:g_PrintBuffer
0x18000580f  mov     [rbp+57h+pszDest], rbx
0x180005813  test    rbx, rbx
0x180005816  jz      short loc_180005858
0x180005818  mov     [rbp+57h+var_88], 1
0x18000581f  mov     [rbp+57h+var_90], 0
0x180005826  test    r12b, 1
0x18000582a  jz      loc_1800058BB
0x180005830  mov     rax, [rbp+57h+var_58]
0x180005834  mov     r9, rsi; pszFormat
0x180005837  mov     edx, 9C4h; cchDest
0x18000583c  mov     [rsp+0F0h+argList], rax; argList
0x180005841  mov     rcx, rbx; pszDest
0x180005844  call    StringVPrintfWorkerW
0x180005849  xor     ecx, ecx
0x18000584b  movzx   edx, ax
0x18000584e  test    eax, eax
0x180005850  cmovns  edx, ecx
0x180005853  jmp     loc_180005A44
0x180005858  mov     [rbp+57h+var_88], 0
0x18000585f  call    cs:__imp_GetProcessHeap
0x180005865  xor     edx, edx; dwFlags
0x180005867  mov     r8d, 1388h; dwBytes
0x18000586d  mov     rcx, rax; hHeap
0x180005870  call    cs:__imp_HeapAlloc
0x180005876  mov     [rbp+57h+pszDest], rax
0x18000587a  mov     rbx, rax
0x18000587d  test    rax, rax
0x180005880  jnz     short loc_18000581F
0x180005882  mov     rcx, r15
0x180005885  call    ReleaseReadLock
0x18000588a  mov     rcx, r14
0x18000588d  call    ReleaseReadLock
0x180005892  test    edi, edi
0x180005894  jnz     short loc_1800058AF
0x180005896  call    cs:__imp_GetProcessHeap
0x18000589c  mov     r8, r13; lpMem
0x18000589f  xor     edx, edx; dwFlags
0x1800058a1  mov     rcx, rax; hHeap
0x1800058a4  call    cs:__imp_HeapFree
0x1800058aa  jmp     loc_180005ACC
0x1800058af  xchg    r13, cs:g_FormatBuffer
0x1800058b6  jmp     loc_180005ACC
0x1800058bb  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800058bf  call    cs:__imp_GetLocalTime
0x1800058c5  mov     eax, r12d
0x1800058c8  and     eax, 8
0x1800058cb  test    r12b, 4
0x1800058cf  jnz     loc_18000596B
0x1800058d5  movzx   ebx, [rbp+57h+SystemTime.wSecond]
0x1800058d9  movzx   edi, [rbp+57h+SystemTime.wMinute]
0x1800058dd  movzx   esi, [rbp+57h+SystemTime.wHour]
0x1800058e1  test    eax, eax
0x1800058e3  jz      short loc_180005934
0x1800058e5  movzx   r14d, [rbp+57h+SystemTime.wDay]
0x1800058ea  movzx   r15d, [rbp+57h+SystemTime.wMonth]
0x1800058ef  call    cs:__imp_GetCurrentThreadId
0x1800058f5  lea     r8, a03d02u02u02u02; "\r\n[%03d] %02u-%02u %02u:%02u:%02u: %s"
0x1800058fc  mov     edx, 1388h; cbDest
0x180005901  mov     r9d, eax
0x180005904  mov     rcx, r13; pszDest
0x180005907  mov     rax, [rbp+57h+var_80]
0x18000590b  mov     [rsp+0F0h+var_A8], rax
0x180005910  mov     dword ptr [rsp+0F0h+var_B0], ebx
0x180005914  mov     dword ptr [rsp+0F0h+var_B8], edi
0x180005918  mov     [rsp+0F0h+var_C0], esi
0x18000591c  mov     [rsp+0F0h+var_C8], r14d
0x180005921  mov     dword ptr [rsp+0F0h+argList], r15d
0x180005926  call    StringCbPrintfW
0x18000592b  mov     r15, [rbp+57h+var_60]
0x18000592f  jmp     loc_180005A0C
0x180005934  call    cs:__imp_GetCurrentThreadId
0x18000593a  lea     r8, a03d02u02u02uS; "\r\n[%03d] %02u:%02u:%02u: %s"
0x180005941  mov     edx, 1388h; cbDest
0x180005946  mov     r9d, eax
0x180005949  mov     rcx, r13; pszDest
0x18000594c  mov     rax, [rbp+57h+var_80]
0x180005950  mov     [rsp+0F0h+var_B8], rax
0x180005955  mov     [rsp+0F0h+var_C0], ebx
0x180005959  mov     [rsp+0F0h+var_C8], edi
0x18000595d  mov     dword ptr [rsp+0F0h+argList], esi
0x180005961  call    StringCbPrintfW
0x180005966  jmp     loc_180005A10
0x18000596b  movzx   ebx, [rbp+57h+SystemTime.wMilliseconds]
0x18000596f  movzx   edi, [rbp+57h+SystemTime.wSecond]
0x180005973  movzx   esi, [rbp+57h+SystemTime.wMinute]
0x180005977  movzx   r14d, [rbp+57h+SystemTime.wHour]
0x18000597c  test    eax, eax
0x18000597e  jz      short loc_1800059D5
0x180005980  movzx   r15d, [rbp+57h+SystemTime.wDay]
0x180005985  movzx   r12d, [rbp+57h+SystemTime.wMonth]
0x18000598a  call    cs:__imp_GetCurrentThreadId
0x180005990  lea     r8, a03d02u02u02u02_0; "\r\n[%03d] %02u-%02u %02u:%02u:%02u:%03"...
0x180005997  mov     edx, 1388h; cbDest
0x18000599c  mov     r9d, eax
0x18000599f  mov     rcx, r13; pszDest
0x1800059a2  mov     rax, [rbp+57h+var_80]
0x1800059a6  mov     [rsp+0F0h+var_A0], rax
0x1800059ab  mov     dword ptr [rsp+0F0h+var_A8], ebx
0x1800059af  mov     dword ptr [rsp+0F0h+var_B0], edi
0x1800059b3  mov     dword ptr [rsp+0F0h+var_B8], esi
0x1800059b7  mov     [rsp+0F0h+var_C0], r14d
0x1800059bc  mov     [rsp+0F0h+var_C8], r15d
0x1800059c1  mov     dword ptr [rsp+0F0h+argList], r12d
0x1800059c6  call    StringCbPrintfW
0x1800059cb  mov     r15, [rbp+57h+var_60]
0x1800059cf  mov     r12d, [rbp+57h+var_70]
0x1800059d3  jmp     short loc_180005A0C
0x1800059d5  call    cs:__imp_GetCurrentThreadId
0x1800059db  lea     r8, a03d02u02u02u03_2; "\r\n[%03d] %02u:%02u:%02u:%03u: %s"
0x1800059e2  mov     edx, 1388h; cbDest
0x1800059e7  mov     r9d, eax
0x1800059ea  mov     rcx, r13; pszDest
0x1800059ed  mov     rax, [rbp+57h+var_80]
0x1800059f1  mov     [rsp+0F0h+var_B0], rax
0x1800059f6  mov     dword ptr [rsp+0F0h+var_B8], ebx
0x1800059fa  mov     [rsp+0F0h+var_C0], edi
0x1800059fe  mov     [rsp+0F0h+var_C8], esi
0x180005a02  mov     dword ptr [rsp+0F0h+argList], r14d
0x180005a07  call    StringCbPrintfW
0x180005a0c  mov     r14, [rbp+57h+var_68]
0x180005a10  mov     edx, eax
0x180005a12  xor     eax, eax
0x180005a14  test    edx, edx
0x180005a16  movzx   ecx, dx
0x180005a19  cmovns  ecx, eax
0x180005a1c  test    ecx, ecx
0x180005a1e  jnz     short loc_180005A56
0x180005a20  mov     rax, [rbp+57h+var_58]
0x180005a24  mov     r9, r13; pszFormat
0x180005a27  mov     rbx, [rbp+57h+pszDest]
0x180005a2b  mov     edx, 9C4h; cchDest
0x180005a30  mov     rcx, rbx; pszDest
0x180005a33  mov     [rsp+0F0h+argList], rax; argList
0x180005a38  call    StringVPrintfWorkerW
0x180005a3d  test    eax, eax
0x180005a3f  jns     short loc_180005A48
0x180005a41  movzx   edx, ax
0x180005a44  test    edx, edx
0x180005a46  jnz     short loc_180005A5A
0x180005a48  mov     r9, rbx
0x180005a4b  mov     r8d, r12d
0x180005a4e  mov     rdx, r15
0x180005a51  call    TraceWriteOutputW
0x180005a56  mov     ebx, eax
0x180005a58  jmp     short loc_180005A5D
0x180005a5a  mov     ebx, [rbp+57h+var_90]
0x180005a5d  mov     rcx, r15
0x180005a60  call    ReleaseReadLock
0x180005a65  mov     rcx, r14
0x180005a68  call    ReleaseReadLock
0x180005a6d  cmp     [rbp+57h+var_8C], 0
0x180005a71  jz      short loc_180005A7C
0x180005a73  xchg    r13, cs:g_FormatBuffer
0x180005a7a  jmp     short loc_180005A90
0x180005a7c  call    cs:__imp_GetProcessHeap
0x180005a82  mov     r8, r13; lpMem
0x180005a85  xor     edx, edx; dwFlags
0x180005a87  mov     rcx, rax; hHeap
0x180005a8a  call    cs:__imp_HeapFree
0x180005a90  cmp     [rbp+57h+var_88], 0
0x180005a94  jz      short loc_180005AA3
0x180005a96  mov     r8, [rbp+57h+pszDest]
0x180005a9a  xchg    r8, cs:g_PrintBuffer
0x180005aa1  jmp     short loc_180005AB8
0x180005aa3  call    cs:__imp_GetProcessHeap
0x180005aa9  mov     r8, [rbp+57h+pszDest]; lpMem
0x180005aad  xor     edx, edx; dwFlags
0x180005aaf  mov     rcx, rax; hHeap
0x180005ab2  call    cs:__imp_HeapFree
0x180005ab8  mov     eax, ebx
0x180005aba  jmp     short loc_180005ACE
0x180005abc  mov     rcx, r15
0x180005abf  call    ReleaseReadLock
0x180005ac4  mov     rcx, r14
0x180005ac7  call    ReleaseReadLock
0x180005acc  xor     eax, eax
0x180005ace  mov     rcx, [rbp+57h+var_40]
0x180005ad2  xor     rcx, rsp; StackCookie
0x180005ad5  call    __security_check_cookie
0x180005ada  mov     rbx, [rsp+0F0h+arg_8]
0x180005ae2  add     rsp, 0C0h
0x180005ae9  pop     r15
0x180005aeb  pop     r14
0x180005aed  pop     r13
0x180005aef  pop     r12
0x180005af1  pop     rdi
0x180005af2  pop     rsi
0x180005af3  pop     rbp
0x180005af4  retn
```
