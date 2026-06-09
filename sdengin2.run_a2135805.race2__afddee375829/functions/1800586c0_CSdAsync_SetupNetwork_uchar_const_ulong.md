# CSdAsync::SetupNetwork(uchar const *,ulong)

- ea: `0x1800586c0`
- end: `0x180058887`
- name: `?SetupNetwork@CSdAsync@@UEAAJPEBEK@Z`
- size: `455`
- prototype: `int(CSdAsync *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800586c0`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180058783`
- `KERNEL32!GetCurrentThread` at `0x180058783`
- `KERNEL32!CloseHandle` at `0x18005876f`
- `KERNEL32!CloseHandle` at `0x1800587df`
- `KERNEL32!CloseHandle` at `0x18005885e`
- `KERNEL32!CloseHandle` at `0x18005876f`
- `KERNEL32!CloseHandle` at `0x1800587df`
- `KERNEL32!CloseHandle` at `0x18005885e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18005872b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18005872b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005879f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005879f`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "CSdAsync::SetupNetwork", 0x558u, 1u);
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
0x1800586c0  push    rbp
0x1800586c2  push    rbx
0x1800586c3  push    rsi
0x1800586c4  push    rdi
0x1800586c5  mov     rbp, rsp
0x1800586c8  sub     rsp, 68h
0x1800586cc  mov     esi, r8d
0x1800586cf  mov     rdi, rdx
0x1800586d2  mov     rbx, rcx
0x1800586d5  mov     r9d, 1; unsigned __int16
0x1800586db  mov     r8d, 558h; unsigned __int16
0x1800586e1  lea     rdx, aCsdasyncSetupn; "CSdAsync::SetupNetwork"
0x1800586e8  lea     rcx, [rbp+var_48]; this
0x1800586ec  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800586f1  mov     [rbp+hObject], 0
0x1800586f9  test    rdi, rdi
0x1800586fc  jz      loc_180058783
0x180058702  mov     eax, 55Fh
0x180058707  cmp     esi, 44h ; 'D'
0x18005870a  jz      short loc_18005871D
0x18005870c  mov     ebx, 80070057h
0x180058711  mov     [rbp+var_48], ebx
0x180058714  mov     [rbp+var_42], ax
0x180058718  jmp     loc_180058872
0x18005871d  mov     [rbp+var_48], 0
0x180058724  mov     [rbp+var_44], ax
0x180058728  mov     rcx, rdi; pSid
0x18005872b  call    cs:__imp_IsValidSid
0x180058732  nop     dword ptr [rax+rax+00h]
0x180058737  test    eax, eax
0x180058739  jnz     short loc_180058751
0x18005873b  call    GetLastFailureAsHRESULT
0x180058740  mov     [rbp+var_48], eax
0x180058743  mov     eax, 560h
0x180058748  mov     [rbp+var_42], ax
0x18005874c  jmp     loc_18005884D
0x180058751  mov     [rbp+var_48], 0
0x180058758  mov     eax, 560h
0x18005875d  mov     [rbp+var_44], ax
0x180058761  mov     rcx, [rbp+hObject]; hObject
0x180058765  lea     rax, [rcx-1]
0x180058769  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005876d  ja      short loc_180058783
0x18005876f  call    cs:__imp_CloseHandle
0x180058776  nop     dword ptr [rax+rax+00h]
0x18005877b  mov     [rbp+hObject], 0
0x180058783  call    cs:__imp_GetCurrentThread
0x18005878a  nop     dword ptr [rax+rax+00h]
0x18005878f  lea     r9, [rbp+hObject]; TokenHandle
0x180058793  mov     edx, 0Eh; DesiredAccess
0x180058798  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x18005879c  mov     rcx, rax; ThreadHandle
0x18005879f  call    cs:__imp_OpenThreadToken
0x1800587a6  nop     dword ptr [rax+rax+00h]
0x1800587ab  test    eax, eax
0x1800587ad  jnz     short loc_1800587BE
0x1800587af  call    GetLastFailureAsHRESULT
0x1800587b4  mov     [rbp+var_48], eax
0x1800587b7  mov     eax, 568h
0x1800587bc  jmp     short loc_180058748
0x1800587be  mov     [rbp+var_48], 0
0x1800587c5  mov     eax, 568h
0x1800587ca  mov     [rbp+var_44], ax
0x1800587ce  mov     rcx, [rbx+0C8h]; hObject
0x1800587d5  lea     rax, [rcx-1]
0x1800587d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800587dd  ja      short loc_1800587F6
0x1800587df  call    cs:__imp_CloseHandle
0x1800587e6  nop     dword ptr [rax+rax+00h]
0x1800587eb  mov     qword ptr [rbx+0C8h], 0
0x1800587f6  mov     rax, [rbp+hObject]
0x1800587fa  mov     [rbx+0C8h], rax
0x180058801  mov     [rbp+hObject], 0
0x180058809  test    rdi, rdi
0x18005880c  jz      short loc_180058842
0x18005880e  lea     rcx, [rbx+0D0h]
0x180058815  mov     [rbx+118h], rcx
0x18005881c  movups  xmm0, xmmword ptr [rdi]
0x18005881f  movups  xmmword ptr [rcx], xmm0
0x180058822  movups  xmm1, xmmword ptr [rdi+10h]
0x180058826  movups  xmmword ptr [rcx+10h], xmm1
0x18005882a  movups  xmm0, xmmword ptr [rdi+20h]
0x18005882e  movups  xmmword ptr [rcx+20h], xmm0
0x180058832  movups  xmm1, xmmword ptr [rdi+30h]
0x180058836  movups  xmmword ptr [rcx+30h], xmm1
0x18005883a  mov     eax, [rdi+40h]
0x18005883d  mov     [rcx+40h], eax
0x180058840  jmp     short loc_18005884D
0x180058842  mov     qword ptr [rbx+118h], 0
0x18005884d  mov     ebx, [rbp+var_48]
0x180058850  mov     rcx, [rbp+hObject]; hObject
0x180058854  lea     rdx, [rcx-1]
0x180058858  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005885c  ja      short loc_180058872
0x18005885e  call    cs:__imp_CloseHandle
0x180058865  nop     dword ptr [rax+rax+00h]
0x18005886a  mov     [rbp+hObject], 0
0x180058872  lea     rcx, [rbp+var_48]; this
0x180058876  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18005887b  mov     eax, ebx
0x18005887d  add     rsp, 68h
0x180058881  pop     rdi
0x180058882  pop     rsi
0x180058883  pop     rbx
0x180058884  pop     rbp
0x180058885  retn
```
