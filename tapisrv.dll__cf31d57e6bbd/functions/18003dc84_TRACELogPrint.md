# TRACELogPrint

- ea: `0x18003dc84`
- end: `0x18003de3e`
- name: `TRACELogPrint`
- size: `442`
- prototype: `__int64(_QWORD, const char *, ...)`
- caller_count: `126`
- callee_count: `6`
- tags: ``

## callers

- `0x180002b1c`
- `0x1800038cc`
- `0x180003b0c`
- `0x180003d8c`
- `0x180003f58`
- `0x18000469c`
- `0x180004a94`
- `0x180004cd0`
- `0x180004fcc`
- `0x180005378`
- `0x18000678c`
- `0x180006dec`
- `0x180007244`
- `0x1800081d0`
- `0x180009510`
- `0x180009f50`
- `0x18000af50`
- `0x18000b990`
- `0x18000bbc0`
- `0x18000be00`
- `0x18000c5a0`
- `0x18000c8a0`
- `0x18000cd20`
- `0x18000d540`
- `0x18000d980`
- `0x18000dfc0`
- `0x18000ebb0`
- `0x18000f390`
- `0x18000f6a0`
- `0x18000fb70`
- `0x18000fdc0`
- `0x18000fe60`
- `0x180010750`
- `0x180010d40`
- `0x180011820`
- `0x180012480`
- `0x180012a90`
- `0x180012ea0`
- `0x1800132a0`
- `0x180014710`
- `0x180015300`
- `0x180015de0`
- `0x180017500`
- `0x180017adc`
- `0x180017b74`
- `0x180017be0`
- `0x180019e40`
- `0x180019fcc`
- `0x18001a618`
- `0x18001a710`

## callees

- `0x180001600`
- `0x18003db3c`
- `0x18003dbd8`
- `0x18003dc30`
- `0x18003dc84`
- `0x18003e058`

## import_xrefs

- `KERNEL32!GetLocalTime` at `0x18003dceb`
- `KERNEL32!GetLocalTime` at `0x18003dceb`
- `KERNEL32!lstrlenA` at `0x18003dd65`
- `KERNEL32!lstrlenA` at `0x18003dd77`
- `KERNEL32!lstrlenA` at `0x18003dd65`
- `KERNEL32!lstrlenA` at `0x18003dd77`
- `KERNEL32!OutputDebugStringA` at `0x18003ddca`
- `KERNEL32!OutputDebugStringA` at `0x18003ddca`
- `KERNEL32!GetCurrentThreadId` at `0x18003dcf1`
- `KERNEL32!GetCurrentThreadId` at `0x18003dcf1`
- `rtutils!TraceVprintfExA` at `0x18003de1c`
- `rtutils!TraceVprintfExA` at `0x18003de1c`

## pseudocode

```c
void TRACELogPrint(unsigned int a1, const char *a2, ...)
{
  const char *v3; // rax
  int v4; // r10d
  int v5; // edi
  size_t v6; // rdx
  char *v7; // r8
  __int64 v8; // rax
  const char *v9; // rax
  const char *v10; // r8
  _QWORD SystemTime[3]; // [rsp+58h] [rbp-B0h] BYREF
  CHAR pszDest[1040]; // [rsp+78h] [rbp-90h] BYREF
  va_list arglist; // [rsp+4D8h] [rbp+3D0h] BYREF

  va_start(arglist, a2);
  if ( !*(_DWORD *)&sg_dwTracingToDebugger || (a1 & *(_DWORD *)&sg_dwDebuggerMask) == 0 )
    goto LABEL_10;
  *(_OWORD *)&SystemTime[1] = 0;
  GetLocalTime((LPSYSTEMTIME)&SystemTime[1]);
  GetCurrentThreadId();
  v3 = (const char *)TraceLevel(a1);
  StringCbPrintfA(
    pszDest,
    0x401u,
    "%s:[%02u:%02u:%02u.%03u,tid=%x:] [%s] ",
    sg_szTraceName,
    LOWORD(SystemTime[2]),
    WORD1(SystemTime[2]),
    WORD2(SystemTime[2]),
    HIWORD(SystemTime[2]),
    v4,
    v3);
  v5 = 1024 - lstrlenA(pszDest);
  v7 = &pszDest[lstrlenA(pszDest)];
  if ( !v5 )
  {
    v8 = 0;
LABEL_7:
    if ( v8 )
      *v7 = 0;
    goto LABEL_9;
  }
  v8 = v5;
  if ( (unsigned __int64)v5 > 0x7FFFFFFF )
    goto LABEL_7;
  StringVPrintfWorkerA(v7, v5, (size_t *)v7, a2, arglist);
LABEL_9:
  StringCbCatA(pszDest, v6, v7);
  OutputDebugStringA(pszDest);
LABEL_10:
  if ( sg_dwTraceID != -1 )
  {
    v9 = (const char *)TraceLevel(a1);
    StringCbPrintfA(pszDest, 0x401u, "[%s] %s", v9, v10);
    TraceVprintfExA(sg_dwTraceID, a1 | 4, pszDest, arglist);
  }
}

```

## disassembly

```asm
0x18003dc84  mov     rax, rsp
0x18003dc87  mov     [rax+10h], rdx
0x18003dc8b  mov     [rax+18h], r8
0x18003dc8f  mov     [rax+20h], r9
0x18003dc93  push    rbp
0x18003dc94  push    rbx
0x18003dc95  push    rdi
0x18003dc96  push    r15
0x18003dc98  lea     rbp, [rax-3B8h]
0x18003dc9f  sub     rsp, 498h
0x18003dca6  mov     rax, cs:__security_cookie
0x18003dcad  xor     rax, rsp
0x18003dcb0  mov     [rbp+3B0h+var_30], rax
0x18003dcb7  cmp     cs:sg_dwTracingToDebugger, 0
0x18003dcbe  mov     r8, rdx
0x18003dcc1  mov     ebx, ecx
0x18003dcc3  mov     qword ptr [rsp+4B0h+SystemTime], 0
0x18003dccc  jbe     loc_18003DDD7
0x18003dcd2  test    cs:sg_dwDebuggerMask, ecx
0x18003dcd8  jz      loc_18003DDD7
0x18003dcde  xorps   xmm0, xmm0
0x18003dce1  lea     rcx, [rsp+4B0h+SystemTime+8]; lpSystemTime
0x18003dce6  movups  xmmword ptr [rsp+4B0h+SystemTime+8], xmm0
0x18003dceb  call    cs:__imp_GetLocalTime
0x18003dcf1  call    cs:__imp_GetCurrentThreadId
0x18003dcf7  mov     ecx, ebx
0x18003dcf9  mov     r10d, eax
0x18003dcfc  call    TraceLevel
0x18003dd01  movzx   ecx, word ptr [rsp+4B0h+SystemTime+16h]
0x18003dd06  movzx   edx, word ptr [rsp+4B0h+SystemTime+14h]
0x18003dd0b  movzx   r8d, word ptr [rsp+4B0h+SystemTime+12h]
0x18003dd11  movzx   r9d, word ptr [rsp+4B0h+SystemTime+10h]
0x18003dd17  mov     [rsp+4B0h+var_468], rax
0x18003dd1c  mov     dword ptr [rsp+4B0h+var_470], r10d
0x18003dd21  mov     [rsp+4B0h+var_478], ecx
0x18003dd25  lea     rcx, [rsp+4B0h+pszDest]; pszDest
0x18003dd2a  mov     [rsp+4B0h+var_480], edx
0x18003dd2e  mov     edx, 401h; cbDest
0x18003dd33  mov     [rsp+4B0h+var_488], r8d
0x18003dd38  lea     r8, aS02u02u02u03uT; "%s:[%02u:%02u:%02u.%03u,tid=%x:] [%s] "
0x18003dd3f  mov     dword ptr [rsp+4B0h+argList], r9d
0x18003dd44  lea     r9, sg_szTraceName
0x18003dd4b  call    StringCbPrintfA
0x18003dd50  lea     rcx, [rsp+4B0h+pszDest]; lpString
0x18003dd55  mov     qword ptr [rsp+4B0h+SystemTime], 0
0x18003dd5e  lea     r15, [rbp+3B0h+arglist]
0x18003dd65  call    cs:__imp_lstrlenA
0x18003dd6b  mov     edi, 400h
0x18003dd70  lea     rcx, [rsp+4B0h+pszDest]; lpString
0x18003dd75  sub     edi, eax
0x18003dd77  call    cs:__imp_lstrlenA
0x18003dd7d  movsxd  rcx, eax
0x18003dd80  lea     r8, [rsp+4B0h+pszDest]
0x18003dd85  add     r8, rcx; pszSrc
0x18003dd88  test    edi, edi
0x18003dd8a  jz      short loc_18003DDB0
0x18003dd8c  movsxd  rax, edi
0x18003dd8f  cmp     rax, 7FFFFFFFh
0x18003dd95  ja      short loc_18003DDB2
0x18003dd97  mov     r9, [rbp+3B0h+pszFormat]; pszFormat
0x18003dd9e  mov     rdx, rax; cchDest
0x18003dda1  mov     rcx, r8; pszDest
0x18003dda4  mov     [rsp+4B0h+argList], r15; argList
0x18003dda9  call    StringVPrintfWorkerA
0x18003ddae  jmp     short loc_18003DDBB
0x18003ddb0  xor     eax, eax
0x18003ddb2  test    rax, rax
0x18003ddb5  jz      short loc_18003DDBB
0x18003ddb7  mov     byte ptr [r8], 0
0x18003ddbb  lea     rcx, [rsp+4B0h+pszDest]; pszDest
0x18003ddc0  call    StringCbCatA
0x18003ddc5  lea     rcx, [rsp+4B0h+pszDest]; lpOutputString
0x18003ddca  call    cs:__imp_OutputDebugStringA
0x18003ddd0  mov     r8, [rbp+3B0h+pszFormat]
0x18003ddd7  cmp     cs:sg_dwTraceID, 0FFFFFFFFh
0x18003ddde  jz      short loc_18003DE22
0x18003dde0  mov     ecx, ebx
0x18003dde2  call    TraceLevel
0x18003dde7  mov     [rsp+4B0h+argList], r8
0x18003ddec  lea     rcx, [rsp+4B0h+pszDest]; pszDest
0x18003ddf1  mov     r9, rax
0x18003ddf4  lea     r8, aSS; "[%s] %s"
0x18003ddfb  mov     edx, 401h; cbDest
0x18003de00  call    StringCbPrintfA
0x18003de05  mov     ecx, cs:sg_dwTraceID; dwTraceID
0x18003de0b  lea     r9, [rbp+3B0h+arglist]; arglist
0x18003de12  or      ebx, 4
0x18003de15  lea     r8, [rsp+4B0h+pszDest]; lpszFormat
0x18003de1a  mov     edx, ebx; dwFlags
0x18003de1c  call    cs:__imp_TraceVprintfExA
0x18003de22  mov     rcx, [rbp+3B0h+var_30]
0x18003de29  xor     rcx, rsp; StackCookie
0x18003de2c  call    __security_check_cookie
0x18003de31  add     rsp, 498h
0x18003de38  pop     r15
0x18003de3a  pop     rdi
0x18003de3b  pop     rbx
0x18003de3c  pop     rbp
0x18003de3d  retn
```
