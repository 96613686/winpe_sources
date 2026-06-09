# CSdAsync::SetupNetwork(uchar const *,ulong)

- ea: `0x1800562d0`
- end: `0x18005646e`
- name: `?SetupNetwork@CSdAsync@@UEAAJPEBEK@Z`
- size: `414`
- prototype: `int(CSdAsync *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800562d0`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180056383`
- `KERNEL32!GetCurrentThread` at `0x180056383`
- `KERNEL32!CloseHandle` at `0x180056375`
- `KERNEL32!CloseHandle` at `0x1800563d3`
- `KERNEL32!CloseHandle` at `0x18005644c`
- `KERNEL32!CloseHandle` at `0x180056375`
- `KERNEL32!CloseHandle` at `0x1800563d3`
- `KERNEL32!CloseHandle` at `0x18005644c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180056337`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180056337`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180056399`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180056399`

## pseudocode

```c
__int64 __fastcall CSdAsync::SetupNetwork(CSdAsync *this, unsigned __int8 *a2, int a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int16 v8; // ax
  HANDLE CurrentThread; // rax
  __int64 v10; // rcx
  char *v11; // rcx
  int LastFailureAsHRESULT; // [rsp+20h] [rbp-48h] BYREF
  __int16 v14; // [rsp+24h] [rbp-44h]
  __int16 v15; // [rsp+26h] [rbp-42h]
  HANDLE hObject; // [rsp+98h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "CSdAsync::SetupNetwork", 1368, 1);
  hObject = 0;
  if ( a2 )
  {
    if ( a3 != 68 )
    {
      v6 = -2147024809;
      LastFailureAsHRESULT = -2147024809;
      v15 = 1375;
      goto LABEL_18;
    }
    LastFailureAsHRESULT = 0;
    v14 = 1375;
    if ( !IsValidSid(a2) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
      v8 = 1376;
      goto LABEL_6;
    }
    LastFailureAsHRESULT = 0;
    v14 = 1376;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, &hObject) )
  {
    LastFailureAsHRESULT = 0;
    v14 = 1384;
    v11 = (char *)*((_QWORD *)this + 25);
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v11);
      *((_QWORD *)this + 25) = 0;
    }
    *((_QWORD *)this + 25) = hObject;
    hObject = 0;
    if ( a2 )
    {
      *((_QWORD *)this + 35) = (char *)this + 208;
      *((_OWORD *)this + 13) = *(_OWORD *)a2;
      *((_OWORD *)this + 14) = *((_OWORD *)a2 + 1);
      *((_OWORD *)this + 15) = *((_OWORD *)a2 + 2);
      *((_OWORD *)this + 16) = *((_OWORD *)a2 + 3);
      *((_DWORD *)this + 68) = *((_DWORD *)a2 + 16);
    }
    else
    {
      *((_QWORD *)this + 35) = 0;
    }
    goto LABEL_16;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
  v8 = 1384;
LABEL_6:
  v15 = v8;
LABEL_16:
  v6 = LastFailureAsHRESULT;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
LABEL_18:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v6;
}

```

## disassembly

```asm
0x1800562d0  push    rbp
0x1800562d2  push    rbx
0x1800562d3  push    rsi
0x1800562d4  push    rdi
0x1800562d5  mov     rbp, rsp
0x1800562d8  sub     rsp, 68h
0x1800562dc  mov     esi, r8d
0x1800562df  mov     rdi, rdx
0x1800562e2  mov     rbx, rcx
0x1800562e5  mov     r9d, 1; unsigned __int16
0x1800562eb  mov     r8d, 558h; unsigned __int16
0x1800562f1  lea     rdx, aCsdasyncSetupn; "CSdAsync::SetupNetwork"
0x1800562f8  lea     rcx, [rbp+var_48]; this
0x1800562fc  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180056301  mov     [rbp+hObject], 0
0x180056309  test    rdi, rdi
0x18005630c  jz      short loc_180056383
0x18005630e  mov     eax, 55Fh
0x180056313  cmp     esi, 44h ; 'D'
0x180056316  jz      short loc_180056329
0x180056318  mov     ebx, 80070057h
0x18005631d  mov     [rbp+var_48], ebx
0x180056320  mov     [rbp+var_42], ax
0x180056324  jmp     loc_18005645A
0x180056329  mov     [rbp+var_48], 0
0x180056330  mov     [rbp+var_44], ax
0x180056334  mov     rcx, rdi; pSid
0x180056337  call    cs:__imp_IsValidSid
0x18005633d  test    eax, eax
0x18005633f  jnz     short loc_180056357
0x180056341  call    GetLastFailureAsHRESULT
0x180056346  mov     [rbp+var_48], eax
0x180056349  mov     eax, 560h
0x18005634e  mov     [rbp+var_42], ax
0x180056352  jmp     loc_18005643B
0x180056357  mov     [rbp+var_48], 0
0x18005635e  mov     eax, 560h
0x180056363  mov     [rbp+var_44], ax
0x180056367  mov     rcx, [rbp+hObject]; hObject
0x18005636b  lea     rax, [rcx-1]
0x18005636f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180056373  ja      short loc_180056383
0x180056375  call    cs:__imp_CloseHandle
0x18005637b  mov     [rbp+hObject], 0
0x180056383  call    cs:__imp_GetCurrentThread
0x180056389  lea     r9, [rbp+hObject]; TokenHandle
0x18005638d  mov     edx, 0Eh; DesiredAccess
0x180056392  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180056396  mov     rcx, rax; ThreadHandle
0x180056399  call    cs:__imp_OpenThreadToken
0x18005639f  test    eax, eax
0x1800563a1  jnz     short loc_1800563B2
0x1800563a3  call    GetLastFailureAsHRESULT
0x1800563a8  mov     [rbp+var_48], eax
0x1800563ab  mov     eax, 568h
0x1800563b0  jmp     short loc_18005634E
0x1800563b2  mov     [rbp+var_48], 0
0x1800563b9  mov     eax, 568h
0x1800563be  mov     [rbp+var_44], ax
0x1800563c2  mov     rcx, [rbx+0C8h]; hObject
0x1800563c9  lea     rax, [rcx-1]
0x1800563cd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800563d1  ja      short loc_1800563E4
0x1800563d3  call    cs:__imp_CloseHandle
0x1800563d9  mov     qword ptr [rbx+0C8h], 0
0x1800563e4  mov     rax, [rbp+hObject]
0x1800563e8  mov     [rbx+0C8h], rax
0x1800563ef  mov     [rbp+hObject], 0
0x1800563f7  test    rdi, rdi
0x1800563fa  jz      short loc_180056430
0x1800563fc  lea     rcx, [rbx+0D0h]
0x180056403  mov     [rbx+118h], rcx
0x18005640a  movups  xmm0, xmmword ptr [rdi]
0x18005640d  movups  xmmword ptr [rcx], xmm0
0x180056410  movups  xmm1, xmmword ptr [rdi+10h]
0x180056414  movups  xmmword ptr [rcx+10h], xmm1
0x180056418  movups  xmm0, xmmword ptr [rdi+20h]
0x18005641c  movups  xmmword ptr [rcx+20h], xmm0
0x180056420  movups  xmm1, xmmword ptr [rdi+30h]
0x180056424  movups  xmmword ptr [rcx+30h], xmm1
0x180056428  mov     eax, [rdi+40h]
0x18005642b  mov     [rcx+40h], eax
0x18005642e  jmp     short loc_18005643B
0x180056430  mov     qword ptr [rbx+118h], 0
0x18005643b  mov     ebx, [rbp+var_48]
0x18005643e  mov     rcx, [rbp+hObject]; hObject
0x180056442  lea     rdx, [rcx-1]
0x180056446  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005644a  ja      short loc_18005645A
0x18005644c  call    cs:__imp_CloseHandle
0x180056452  mov     [rbp+hObject], 0
0x18005645a  lea     rcx, [rbp+var_48]; this
0x18005645e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180056463  mov     eax, ebx
0x180056465  add     rsp, 68h
0x180056469  pop     rdi
0x18005646a  pop     rsi
0x18005646b  pop     rbx
0x18005646c  pop     rbp
0x18005646d  retn
```
