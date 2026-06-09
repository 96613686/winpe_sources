# UserCrashMain(int,wchar_t const * * const)

- ea: `0x1400101d0`
- end: `0x1400104ed`
- name: `?UserCrashMain@@YAHHQEAPEB_W@Z`
- size: `797`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t **const)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140007634`

## callees

- `0x140003174`
- `0x1400100ac`
- `0x140010188`
- `0x1400101d0`
- `0x1400104f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140010248`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140010280`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400102b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140010248`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140010280`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400102b5`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14001028f`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400102c4`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14001028f`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400102c4`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140010257`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x140010257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001034e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001040c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001046c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001034e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001040c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001046c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001045b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010464`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001045b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010464`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400102fd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001031f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001033b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140010392`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400102fd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001031f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001033b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140010392`
- `faultrep!WerpInitiateCrashReporting` at `0x1400103e3`
- `faultrep!WerpInitiateCrashReporting` at `0x1400103e3`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyComplete` at `0x1400103f7`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyComplete` at `0x1400103f7`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyStart` at `0x1400103b0`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyStart` at `0x1400103b0`

## string_xrefs

- `0x1400101ee`: `Invalid number of command line params passed. Params passed: %d`
- `0x140010486`: `OpenProcess failed for faulting pid %d (0x%x)`
- `0x140010368`: `OpenProcess failed for initiating pid %d (0x%x)`
- `0x140010425`: `OpenProcess failed for self, pid %d (0x%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserCrashMain(const wchar_t *a1, const wchar_t **const a2)
{
  int v3; // ebx
  __int64 v5; // r15
  DWORD v6; // ebp
  DWORD v7; // r14d
  unsigned int v8; // esi
  const char *v9; // rax
  __int64 v10; // rdx
  char *v11; // rdi
  char *v12; // rbx
  signed int v13; // eax
  unsigned int v14; // esi
  const char *v15; // rax
  __int64 v16; // rdx
  signed int v17; // eax
  signed int LastError; // eax
  char *v19; // [rsp+28h] [rbp-50h]
  DWORD v20; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = (int)a1;
  if ( (int)a1 < 6 )
  {
    LODWORD(v19) = (_DWORD)a1;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\userfault.cpp",
      (const char *)0x80070057LL,
      (int)"Invalid number of command line params passed. Params passed: %d",
      v19);
    return 2147942487LL;
  }
  v5 = 0;
  v6 = 0;
  v7 = 0;
  UtilCheckDebugWait(a1);
  v8 = 1;
  if ( v3 - 1 <= 1 )
    goto LABEL_41;
  do
  {
    if ( (unsigned int)_o__wcsicmp(a2[v8], L"-s") )
    {
      if ( (unsigned int)_o__wcsicmp(a2[v8], L"-p") )
      {
        if ( !(unsigned int)_o__wcsicmp(a2[v8], L"-ip") )
        {
          v7 = _o__wtoi(a2[v8 + 1]);
          if ( !v7 )
          {
            v9 = "Invalid initiating process id was passed";
            v10 = 115;
            goto LABEL_42;
          }
        }
      }
      else
      {
        v6 = _o__wtoi(a2[v8 + 1]);
        if ( !v6 )
        {
          v9 = "Invalid process id was passed";
          v10 = 101;
          goto LABEL_42;
        }
      }
    }
    else
    {
      v5 = _wtoi64(a2[v8 + 1]);
      if ( !v5 )
      {
        v9 = "No shared mem handle passed";
        v10 = 87;
        goto LABEL_42;
      }
    }
    ++v8;
  }
  while ( (int)v8 < v3 - 1 );
  if ( !v5 || !v6 )
  {
LABEL_41:
    v9 = "No shared mem handle or process id was passed";
    v10 = 124;
LABEL_42:
    v14 = -2147024809;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\userfault.cpp",
      (const char *)0x80070057LL,
      (int)v9,
      v19);
    return v14;
  }
  v11 = (char *)OpenProcess(0x1FFFFFu, 0, v6);
  if ( v11 == (char *)-1LL || v11 + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    LODWORD(v19) = v6;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\userfault.cpp",
      (const char *)v14,
      (int)"OpenProcess failed for faulting pid %d (0x%x)",
      v19,
      v6);
    return v14;
  }
  if ( !v7 )
  {
    v12 = (char *)OpenProcess(0x1FFFFFu, 0, v6);
    if ( v12 == (char *)-1LL || v12 + 1 == (char *)1 )
    {
      v17 = GetLastError();
      v14 = v17;
      if ( v17 > 0 )
        v14 = (unsigned __int16)v17 | 0x80070000;
      v20 = v6;
      v15 = "OpenProcess failed for self, pid %d (0x%x)";
      LODWORD(v19) = v6;
      v16 = 171;
      goto LABEL_34;
    }
LABEL_25:
    if ( (unsigned __int8)IsXerDumpNotifyStartPresent() )
      XerDumpNotifyStart(v11);
    v14 = WerpInitiateCrashReporting(v11, v12, v5, 0, 0, 0, 0, 0);
    if ( (unsigned __int8)IsXerDumpNotifyStartPresent() )
      XerDumpNotifyComplete(v11);
    if ( v14 == -2147024739 )
      UtilFireWerVerticalDisabledEvent();
    goto LABEL_35;
  }
  v12 = (char *)OpenProcess(0x1FFFFFu, 0, v7);
  if ( v12 == (char *)-1LL || v12 + 1 == (char *)1 )
    v12 = (char *)OpenProcess(0x400u, 0, v7);
  if ( (unsigned __int64)(v12 + 1) > 1 )
    goto LABEL_25;
  v13 = GetLastError();
  v14 = v13;
  if ( v13 > 0 )
    v14 = (unsigned __int16)v13 | 0x80070000;
  v20 = v7;
  v15 = "OpenProcess failed for initiating pid %d (0x%x)";
  LODWORD(v19) = v7;
  v16 = 155;
LABEL_34:
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)v16,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\userfault.cpp",
    (const char *)v14,
    (int)v15,
    v19,
    v20);
LABEL_35:
  if ( (unsigned __int64)(v12 + 1) > 1 )
    CloseHandle(v12);
  CloseHandle(v11);
  return v14;
}

```

## disassembly

```asm
0x1400101d0  push    rbx
0x1400101d2  push    rbp
0x1400101d3  push    rsi
0x1400101d4  push    rdi
0x1400101d5  push    r12
0x1400101d7  push    r14
0x1400101d9  push    r15
0x1400101db  sub     rsp, 40h
0x1400101df  mov     rdi, rdx
0x1400101e2  mov     ebx, ecx
0x1400101e4  cmp     ecx, 6
0x1400101e7  jge     short loc_14001021E
0x1400101e9  mov     rcx, [rsp+78h]; this
0x1400101ee  lea     rax, aInvalidNumberO; "Invalid number of command line params p"...
0x1400101f5  mov     dword ptr [rsp+78h+var_50], ebx; char *
0x1400101f9  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140010200  mov     ebx, 80070057h
0x140010205  mov     qword ptr [rsp+78h+var_58], rax; int
0x14001020a  mov     r9d, ebx; char *
0x14001020d  mov     edx, 3Fh ; '?'; void *
0x140010212  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x140010217  mov     eax, ebx
0x140010219  jmp     loc_1400104DE
0x14001021e  xor     r15d, r15d
0x140010221  xor     ebp, ebp
0x140010223  xor     r14d, r14d
0x140010226  call    ?UtilCheckDebugWait@@YAXPEB_W@Z; UtilCheckDebugWait(wchar_t const *)
0x14001022b  lea     esi, [rbp+1]
0x14001022e  lea     r12d, [rbx-1]
0x140010232  cmp     r12d, esi
0x140010235  jle     loc_1400104B0
0x14001023b  mov     ebx, esi
0x14001023d  lea     rdx, aS; "-s"
0x140010244  mov     rcx, [rdi+rbx*8]
0x140010248  call    cs:__imp__o__wcsicmp
0x14001024e  test    eax, eax
0x140010250  jnz     short loc_140010275
0x140010252  mov     rcx, [rdi+rbx*8+8]; String
0x140010257  call    cs:__imp__wtoi64
0x14001025d  mov     r15, rax
0x140010260  test    rax, rax
0x140010263  jnz     short loc_1400102D5
0x140010265  lea     rax, aNoSharedMemHan_0; "No shared mem handle passed"
0x14001026c  lea     edx, [r15+57h]
0x140010270  jmp     loc_1400104BC
0x140010275  mov     rcx, [rdi+rbx*8]
0x140010279  lea     rdx, aP; "-p"
0x140010280  call    cs:__imp__o__wcsicmp
0x140010286  test    eax, eax
0x140010288  jnz     short loc_1400102AA
0x14001028a  mov     rcx, [rdi+rbx*8+8]
0x14001028f  call    cs:__imp__o__wtoi
0x140010295  mov     ebp, eax
0x140010297  test    eax, eax
0x140010299  jnz     short loc_1400102D5
0x14001029b  lea     rax, aInvalidProcess; "Invalid process id was passed"
0x1400102a2  lea     edx, [rbp+65h]
0x1400102a5  jmp     loc_1400104BC
0x1400102aa  mov     rcx, [rdi+rbx*8]
0x1400102ae  lea     rdx, aIp; "-ip"
0x1400102b5  call    cs:__imp__o__wcsicmp
0x1400102bb  test    eax, eax
0x1400102bd  jnz     short loc_1400102D5
0x1400102bf  mov     rcx, [rdi+rbx*8+8]
0x1400102c4  call    cs:__imp__o__wtoi
0x1400102ca  mov     r14d, eax
0x1400102cd  test    eax, eax
0x1400102cf  jz      loc_14001037E
0x1400102d5  inc     esi
0x1400102d7  cmp     esi, r12d
0x1400102da  jl      loc_14001023B
0x1400102e0  test    r15, r15
0x1400102e3  jz      loc_1400104B0
0x1400102e9  test    ebp, ebp
0x1400102eb  jz      loc_1400104B0
0x1400102f1  mov     ebx, 1FFFFFh
0x1400102f6  mov     r8d, ebp; dwProcessId
0x1400102f9  mov     ecx, ebx; dwDesiredAccess
0x1400102fb  xor     edx, edx; bInheritHandle
0x1400102fd  call    cs:__imp_OpenProcess
0x140010303  mov     rdi, rax
0x140010306  inc     rax
0x140010309  cmp     rax, 1
0x14001030d  jbe     loc_14001046C
0x140010313  xor     edx, edx; bInheritHandle
0x140010315  mov     ecx, ebx; dwDesiredAccess
0x140010317  test    r14d, r14d
0x14001031a  jz      short loc_14001038F
0x14001031c  mov     r8d, r14d; dwProcessId
0x14001031f  call    cs:__imp_OpenProcess
0x140010325  mov     rbx, rax
0x140010328  inc     rax
0x14001032b  cmp     rax, 1
0x14001032f  ja      short loc_140010344
0x140010331  mov     r8d, r14d; dwProcessId
0x140010334  xor     edx, edx; bInheritHandle
0x140010336  mov     ecx, 400h; dwDesiredAccess
0x14001033b  call    cs:__imp_OpenProcess
0x140010341  mov     rbx, rax
0x140010344  lea     rax, [rbx+1]
0x140010348  cmp     rax, 1
0x14001034c  ja      short loc_1400103A4
0x14001034e  call    cs:__imp_GetLastError
0x140010354  mov     esi, eax
0x140010356  test    eax, eax
0x140010358  jle     short loc_140010363
0x14001035a  movzx   esi, ax
0x14001035d  or      esi, 80070000h
0x140010363  mov     [rsp+78h+var_48], r14d
0x140010368  lea     rax, aOpenprocessFai; "OpenProcess failed for initiating pid %"...
0x14001036f  mov     dword ptr [rsp+78h+var_50], r14d
0x140010374  mov     edx, 9Bh
0x140010379  jmp     loc_140010435
0x14001037e  lea     rax, aInvalidInitiat; "Invalid initiating process id was passe"...
0x140010385  mov     edx, 73h ; 's'
0x14001038a  jmp     loc_1400104BC
0x14001038f  mov     r8d, ebp; dwProcessId
0x140010392  call    cs:__imp_OpenProcess
0x140010398  mov     rbx, rax
0x14001039b  inc     rax
0x14001039e  cmp     rax, 1
0x1400103a2  jbe     short loc_14001040C
0x1400103a4  call    IsXerDumpNotifyStartPresent
0x1400103a9  test    al, al
0x1400103ab  jz      short loc_1400103B6
0x1400103ad  mov     rcx, rdi
0x1400103b0  call    cs:__imp_XerDumpNotifyStart
0x1400103b6  mov     [rsp+78h+var_40], 0
0x1400103bf  xor     r9d, r9d
0x1400103c2  mov     [rsp+78h+var_48], 0
0x1400103ca  mov     r8, r15
0x1400103cd  mov     dword ptr [rsp+78h+var_50], 0
0x1400103d5  mov     rdx, rbx
0x1400103d8  mov     rcx, rdi
0x1400103db  mov     [rsp+78h+var_58], 0
0x1400103e3  call    cs:__imp_WerpInitiateCrashReporting
0x1400103e9  mov     esi, eax
0x1400103eb  call    IsXerDumpNotifyStartPresent
0x1400103f0  test    al, al
0x1400103f2  jz      short loc_1400103FD
0x1400103f4  mov     rcx, rdi
0x1400103f7  call    cs:__imp_XerDumpNotifyComplete
0x1400103fd  cmp     esi, 8007009Dh
0x140010403  jnz     short loc_14001044E
0x140010405  call    ?UtilFireWerVerticalDisabledEvent@@YAXQEBU_tlgProvider_t@@PEB_WW4_VERTICAL_DISABLED_REASON@@@Z; UtilFireWerVerticalDisabledEvent(_tlgProvider_t const * const,wchar_t const *,_VERTICAL_DISABLED_REASON)
0x14001040a  jmp     short loc_14001044E
0x14001040c  call    cs:__imp_GetLastError
0x140010412  mov     esi, eax
0x140010414  test    eax, eax
0x140010416  jle     short loc_140010421
0x140010418  movzx   esi, ax
0x14001041b  or      esi, 80070000h
0x140010421  mov     [rsp+78h+var_48], ebp
0x140010425  lea     rax, aOpenprocessFai_0; "OpenProcess failed for self, pid %d (0x"...
0x14001042c  mov     dword ptr [rsp+78h+var_50], ebp; char *
0x140010430  mov     edx, 0ABh; void *
0x140010435  mov     rcx, [rsp+78h]; this
0x14001043a  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140010441  mov     r9d, esi; char *
0x140010444  mov     qword ptr [rsp+78h+var_58], rax; int
0x140010449  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x14001044e  lea     rax, [rbx+1]
0x140010452  cmp     rax, 1
0x140010456  jbe     short loc_140010461
0x140010458  mov     rcx, rbx; hObject
0x14001045b  call    cs:__imp_CloseHandle
0x140010461  mov     rcx, rdi; hObject
0x140010464  call    cs:__imp_CloseHandle
0x14001046a  jmp     short loc_1400104DC
0x14001046c  call    cs:__imp_GetLastError
0x140010472  mov     esi, eax
0x140010474  test    eax, eax
0x140010476  jle     short loc_140010481
0x140010478  movzx   esi, ax
0x14001047b  or      esi, 80070000h
0x140010481  mov     rcx, [rsp+78h]; this
0x140010486  lea     rax, aOpenprocessFai_1; "OpenProcess failed for faulting pid %d "...
0x14001048d  mov     [rsp+78h+var_48], ebp
0x140010491  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140010498  mov     dword ptr [rsp+78h+var_50], ebp; char *
0x14001049c  mov     r9d, esi; char *
0x14001049f  mov     edx, 87h; void *
0x1400104a4  mov     qword ptr [rsp+78h+var_58], rax; int
0x1400104a9  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400104ae  jmp     short loc_1400104DC
0x1400104b0  lea     rax, aNoSharedMemHan; "No shared mem handle or process id was "...
0x1400104b7  mov     edx, 7Ch ; '|'; void *
0x1400104bc  mov     rcx, [rsp+78h]; this
0x1400104c1  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x1400104c8  mov     ebx, 80070057h
0x1400104cd  mov     qword ptr [rsp+78h+var_58], rax; int
0x1400104d2  mov     r9d, ebx; char *
0x1400104d5  mov     esi, ebx
0x1400104d7  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400104dc  mov     eax, esi
0x1400104de  add     rsp, 40h
0x1400104e2  pop     r15
0x1400104e4  pop     r14
0x1400104e6  pop     r12
0x1400104e8  pop     rdi
0x1400104e9  pop     rsi
0x1400104ea  pop     rbp
0x1400104eb  pop     rbx
0x1400104ec  retn
```
