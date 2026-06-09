# CSrmDebugControl::BreakIfNeeded(ushort const *,ushort const *)

- ea: `0x1800b0298`
- end: `0x1800b04b4`
- name: `?BreakIfNeeded@CSrmDebugControl@@SAXPEBG0@Z`
- size: `540`
- prototype: `void __fastcall(const unsigned __int16 *, LPCWSTR lpOutputString)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ac354`
- `0x1800ad918`
- `0x1800af008`
- `0x1800af8f0`

## callees

- `0x18006febc`
- `0x1800700b8`
- `0x180075510`
- `0x180075eb8`
- `0x1800762f0`
- `0x18007691c`
- `0x1800b0298`
- `0x1800b04bc`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800b03fd`
- `msvcrt!_wcsicmp` at `0x1800b03fd`
- `ole32!CoTaskMemFree` at `0x1800b044c`
- `ole32!CoTaskMemFree` at `0x1800b044c`
- `KERNEL32!GetCurrentProcess` at `0x1800b034d`
- `KERNEL32!GetCurrentProcess` at `0x1800b034d`
- `KERNEL32!OutputDebugStringW` at `0x1800b040e`
- `KERNEL32!OutputDebugStringW` at `0x1800b0417`
- `KERNEL32!OutputDebugStringW` at `0x1800b0424`
- `KERNEL32!OutputDebugStringW` at `0x1800b042d`
- `KERNEL32!OutputDebugStringW` at `0x1800b043a`
- `KERNEL32!OutputDebugStringW` at `0x1800b040e`
- `KERNEL32!OutputDebugStringW` at `0x1800b0417`
- `KERNEL32!OutputDebugStringW` at `0x1800b0424`
- `KERNEL32!OutputDebugStringW` at `0x1800b042d`
- `KERNEL32!OutputDebugStringW` at `0x1800b043a`
- `KERNEL32!DebugBreak` at `0x1800b0440`
- `KERNEL32!DebugBreak` at `0x1800b0440`

## string_xrefs

- `0x1800b02e7`: `SRMPATHH`
- `0x1800b039e`: `System\CurrentControlSet\Services\Srmsvc\Settings\ModuleDebug`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CSrmDebugControl::BreakIfNeeded(const unsigned __int16 *a1, LPCWSTR lpOutputString)
{
  HANDLE CurrentProcess; // rax
  unsigned int v5; // edx
  wchar_t *String2; // [rsp+40h] [rbp-198h] BYREF
  unsigned int v7; // [rsp+48h] [rbp-190h] BYREF
  LPVOID v8[3]; // [rsp+50h] [rbp-188h] BYREF
  int v9; // [rsp+68h] [rbp-170h] BYREF
  _com_error *v10; // [rsp+70h] [rbp-168h] BYREF
  const exception *v11; // [rsp+78h] [rbp-160h] BYREF
  _QWORD v12[3]; // [rsp+80h] [rbp-158h] BYREF
  int v13; // [rsp+98h] [rbp-140h]
  int v14; // [rsp+9Ch] [rbp-13Ch]
  int v15; // [rsp+A0h] [rbp-138h]
  _DWORD v16[26]; // [rsp+A8h] [rbp-130h] BYREF
  _QWORD v17[5]; // [rsp+110h] [rbp-C8h] BYREF
  unsigned int v18; // [rsp+13Ch] [rbp-9Ch]

  String2 = (wchar_t *)v12;
  v12[0] = L"base\\fs\\fsrm\\utilities\\misc\\dbgutil.cpp";
  v12[1] = L"CSrmDebugControl::BreakIfNeeded";
  v12[2] = L"SRMPATHH";
  v13 = 168;
  v14 = 17;
  v15 = 255;
  v16[24] = 0x1000000;
  memset_0(v16, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v17, (const struct CSrmDebugInfo *)v12, 0);
  CurrentProcess = GetCurrentProcess();
  if ( CSrmDebugControl::WaitForDebugger(CurrentProcess, v5) )
  {
    try
    {
      v8[2] = 0;
      v8[1] = 0;
      v8[0] = (LPVOID)257;
      String2 = 0;
      v7 = 0;
      if ( CSrmRegistryKey::Open(
             (CSrmRegistryKey *)v8,
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\Srmsvc\\Settings\\ModuleDebug")
        && CSrmRegistryKey::GetValue((HKEY *)v8, a1, &v7)
        && v7
        && CSrmRegistryKey::GetValue((HKEY *)v8, L"ModuleName", &String2)
        && !_wcsicmp(lpOutputString, String2) )
      {
        OutputDebugStringW(L"FSRM Debug support: break before '");
        OutputDebugStringW(a1);
        OutputDebugStringW(L"' in module '");
        OutputDebugStringW(lpOutputString);
        OutputDebugStringW(L"'\n");
        DebugBreak();
      }
      CoTaskMemFree(String2);
      String2 = 0;
      CSrmRegistryKey::~CSrmRegistryKey(v8);
    }
    catch ( long v9 )
    {
      CSrmFunctionTracer::HandleHresultException(
        (CSrmFunctionTracer *)v17,
        v9,
        L"base\\fs\\fsrm\\utilities\\misc\\dbgutil.cpp",
        L"SRMPATHH",
        L"CSrmDebugControl::BreakIfNeeded",
        0xC7u,
        v18);
    }
    catch ( _com_error *v10 )
    {
      CSrmFunctionTracer::HandleComException(
        (CSrmFunctionTracer *)v17,
        v10,
        L"base\\fs\\fsrm\\utilities\\misc\\dbgutil.cpp",
        L"SRMPATHH",
        L"CSrmDebugControl::BreakIfNeeded",
        0xC7u,
        v18);
    }
    catch ( std::bad_alloc )
    {
      CSrmFunctionTracer::HandleStdBadAllocException(
        (CSrmFunctionTracer *)v17,
        L"base\\fs\\fsrm\\utilities\\misc\\dbgutil.cpp",
        L"SRMPATHH",
        L"CSrmDebugControl::BreakIfNeeded",
        0xC7u,
        v18);
    }
    catch ( const exception *v11 )
    {
      CSrmFunctionTracer::HandleStdGenericException(
        (CSrmFunctionTracer *)v17,
        v11,
        L"base\\fs\\fsrm\\utilities\\misc\\dbgutil.cpp",
        L"SRMPATHH",
        L"CSrmDebugControl::BreakIfNeeded",
        0xC7u,
        v18);
    }
  }
  v17[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v17);
}

```

## disassembly

```asm
0x1800b0298  mov     r11, rsp
0x1800b029b  mov     [r11+18h], rbx
0x1800b029f  push    rdi
0x1800b02a0  sub     rsp, 1D0h
0x1800b02a7  mov     rax, cs:__security_cookie
0x1800b02ae  xor     rax, rsp
0x1800b02b1  mov     [rsp+1D8h+var_18], rax
0x1800b02b9  mov     rbx, rdx
0x1800b02bc  mov     rdi, rcx
0x1800b02bf  lea     rax, [r11-158h]
0x1800b02c6  mov     [rsp+1D8h+String2], rax
0x1800b02cb  lea     rax, aBaseFsFsrmUtil_4; "base\\fs\\fsrm\\utilities\\misc\\dbguti"...
0x1800b02d2  mov     [r11-158h], rax
0x1800b02d9  lea     rax, aCsrmdebugcontr_0; "CSrmDebugControl::BreakIfNeeded"
0x1800b02e0  mov     [r11-150h], rax
0x1800b02e7  lea     rax, aSrmpathh; "SRMPATHH"
0x1800b02ee  mov     [r11-148h], rax
0x1800b02f5  mov     [rsp+1D8h+var_140], 0A8h
0x1800b0300  mov     [rsp+1D8h+var_13C], 11h
0x1800b030b  mov     [rsp+1D8h+var_138], 0FFh
0x1800b0316  mov     [rsp+1D8h+var_D0], 1000000h
0x1800b0321  xor     edx, edx; Val
0x1800b0323  lea     r8d, [rdx+60h]; Size
0x1800b0327  lea     rcx, [r11-130h]; void *
0x1800b032e  call    memset_0
0x1800b0333  nop
0x1800b0334  xor     r8d, r8d
0x1800b0337  lea     rdx, [rsp+1D8h+var_158]
0x1800b033f  lea     rcx, [rsp+1D8h+var_C8]
0x1800b0347  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800b034c  nop
0x1800b034d  call    cs:__imp_GetCurrentProcess
0x1800b0353  mov     rcx, rax; hProcess
0x1800b0356  call    ?WaitForDebugger@CSrmDebugControl@@SA_NPEAXK@Z; CSrmDebugControl::WaitForDebugger(void *,ulong)
0x1800b035b  test    al, al
0x1800b035d  jz      loc_1800B046F
0x1800b0363  mov     [rsp+1D8h+var_178], 0
0x1800b036c  mov     [rsp+1D8h+var_180], 0
0x1800b0375  mov     [rsp+1D8h+var_184], 0
0x1800b037d  mov     [rsp+1D8h+var_188], 1
0x1800b0385  mov     [rsp+1D8h+var_188], 101h
0x1800b038d  mov     [rsp+1D8h+String2], 0
0x1800b0396  mov     [rsp+1D8h+var_190], 0
0x1800b039e  lea     r8, ?x_pwszDebugKeyModules@@3QBGB; "System\\CurrentControlSet\\Services\\Sr"...
0x1800b03a5  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800b03ac  lea     rcx, [rsp+1D8h+var_188]; this
0x1800b03b1  call    ?Open@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Open(HKEY__ *,ushort const *,...)
0x1800b03b6  test    al, al
0x1800b03b8  jz      loc_1800B0447
0x1800b03be  lea     r8, [rsp+1D8h+var_190]; unsigned int *
0x1800b03c3  mov     rdx, rdi; unsigned __int16 *
0x1800b03c6  lea     rcx, [rsp+1D8h+var_188]; this
0x1800b03cb  call    ?GetValue@CSrmRegistryKey@@QEAA_NPEBGPEAK_N@Z; CSrmRegistryKey::GetValue(ushort const *,ulong *,bool)
0x1800b03d0  test    al, al
0x1800b03d2  jz      short loc_1800B0447
0x1800b03d4  cmp     [rsp+1D8h+var_190], 0
0x1800b03d9  jz      short loc_1800B0447
0x1800b03db  lea     r8, [rsp+1D8h+String2]; unsigned __int16 **
0x1800b03e0  lea     rdx, aModulename; "ModuleName"
0x1800b03e7  lea     rcx, [rsp+1D8h+var_188]; this
0x1800b03ec  call    ?GetValue@CSrmRegistryKey@@QEAA_NPEBGPEAPEAG_NPEA_N@Z; CSrmRegistryKey::GetValue(ushort const *,ushort * *,bool,bool *)
0x1800b03f1  test    al, al
0x1800b03f3  jz      short loc_1800B0447
0x1800b03f5  mov     rdx, [rsp+1D8h+String2]; String2
0x1800b03fa  mov     rcx, rbx; String1
0x1800b03fd  call    cs:__imp__wcsicmp
0x1800b0403  test    eax, eax
0x1800b0405  jnz     short loc_1800B0447
0x1800b0407  lea     rcx, aFsrmDebugSuppo; "FSRM Debug support: break before '"
0x1800b040e  call    cs:__imp_OutputDebugStringW
0x1800b0414  mov     rcx, rdi; lpOutputString
0x1800b0417  call    cs:__imp_OutputDebugStringW
0x1800b041d  lea     rcx, aInModule; "' in module '"
0x1800b0424  call    cs:__imp_OutputDebugStringW
0x1800b042a  mov     rcx, rbx; lpOutputString
0x1800b042d  call    cs:__imp_OutputDebugStringW
0x1800b0433  lea     rcx, asc_1800F8934; "'\n"
0x1800b043a  call    cs:__imp_OutputDebugStringW
0x1800b0440  call    cs:__imp_DebugBreak
0x1800b0446  nop
0x1800b0447  mov     rcx, [rsp+1D8h+String2]; pv
0x1800b044c  call    cs:__imp_CoTaskMemFree
0x1800b0452  mov     [rsp+1D8h+String2], 0
0x1800b045b  mov     [rsp+1D8h+String2], 0
0x1800b0464  lea     rcx, [rsp+1D8h+var_188]; this
0x1800b0469  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x1800b046e  nop
0x1800b046f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800b0476  mov     [rsp+1D8h+var_C8], rax
0x1800b047e  lea     rcx, [rsp+1D8h+var_C8]; this
0x1800b0486  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800b048b  nop
0x1800b048c  mov     rcx, [rsp+1D8h+var_18]
0x1800b0494  xor     rcx, rsp; StackCookie
0x1800b0497  call    __security_check_cookie
0x1800b049c  mov     rbx, [rsp+1D8h+arg_10]
0x1800b04a4  add     rsp, 1D0h
0x1800b04ab  pop     rdi
0x1800b04ac  retn
0x1800b04ad  jmp     short loc_1800B046F
0x1800b04af  jmp     short loc_1800B046F
0x1800b04b1  jmp     short loc_1800B046F
```
