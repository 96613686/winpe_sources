# windiag::_dynamic_initializer_for__system_error_modules__

- ea: `0x1800022d0`
- end: `0x1800023cb`
- name: `windiag::_dynamic_initializer_for__system_error_modules__`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004510`
- `0x1800048c0`
- `0x18000491c`
- `0x180005508`
- `0x18003afd8`

## string_xrefs

- `0x1800022fc`: `wbem\wmiutils.dll`
- `0x18000230a`: `wbem\wbemcore.dll`
- `0x180002315`: `wbem\wbemcntl.dll`
- `0x180002320`: `wininet.dll`
- `0x18000232b`: `windowsperformancerecordercontrol.dll`
- `0x180002336`: `msxml6r.dll`

## pseudocode

```c
int windiag::_dynamic_initializer_for__system_error_modules__()
{
  __int64 v0; // rbx
  __int64 v2; // [rsp+20h] [rbp-29h] BYREF
  int Src; // [rsp+30h] [rbp-19h] BYREF
  const char *v4; // [rsp+38h] [rbp-11h]
  int v5; // [rsp+40h] [rbp-9h]
  const char *v6; // [rsp+48h] [rbp-1h]
  int v7; // [rsp+50h] [rbp+7h]
  const char *v8; // [rsp+58h] [rbp+Fh]
  int v9; // [rsp+60h] [rbp+17h]
  const char *v10; // [rsp+68h] [rbp+1Fh]
  int v11; // [rsp+70h] [rbp+27h]
  const char *v12; // [rsp+78h] [rbp+2Fh]
  int v13; // [rsp+80h] [rbp+37h]
  const char *v14; // [rsp+88h] [rbp+3Fh]

  v9 = 0;
  Src = 4;
  v4 = "wbem\\wmiutils.dll";
  v6 = "wbem\\wbemcore.dll";
  v8 = "wbem\\wbemcntl.dll";
  v10 = "wininet.dll";
  v12 = "windowsperformancerecordercontrol.dll";
  v5 = 4;
  v7 = 4;
  v14 = "msxml6r.dll";
  v11 = 1368;
  v13 = 12;
  windiag::system_error_modules = (__int64)operator new(0x60u);
  qword_1800BECE0 = windiag::system_error_modules;
  v0 = windiag::system_error_modules + 96;
  qword_1800BECE8 = windiag::system_error_modules + 96;
  memmove_0((void *)windiag::system_error_modules, &Src, 0x60u);
  qword_1800BECE0 = v0;
  v2 = 0;
  std::_Tidy_guard<std::vector<std::pair<int,char const *>>>::~_Tidy_guard<std::vector<std::pair<int,char const *>>>(&v2);
  return atexit(windiag::_dynamic_atexit_destructor_for__system_error_modules__);
}

```

## disassembly

```asm
0x1800022d0  mov     [rsp-8+arg_0], rbx
0x1800022d5  push    rbp
0x1800022d6  lea     rbp, [rsp-57h]
0x1800022db  sub     rsp, 0A0h
0x1800022e2  mov     rax, cs:__security_cookie
0x1800022e9  xor     rax, rsp
0x1800022ec  mov     [rbp+57h+var_10], rax
0x1800022f0  mov     ecx, 4
0x1800022f5  mov     [rbp+57h+var_40], 0
0x1800022fc  lea     rax, aWbemWmiutilsDl; "wbem\\wmiutils.dll"
0x180002303  mov     [rbp+57h+Src], ecx
0x180002306  mov     [rbp+57h+var_68], rax
0x18000230a  lea     rax, aWbemWbemcoreDl; "wbem\\wbemcore.dll"
0x180002311  mov     [rbp+57h+var_58], rax
0x180002315  lea     rax, aWbemWbemcntlDl; "wbem\\wbemcntl.dll"
0x18000231c  mov     [rbp+57h+var_48], rax
0x180002320  lea     rax, aWininetDll_0; "wininet.dll"
0x180002327  mov     [rbp+57h+var_38], rax
0x18000232b  lea     rax, aWindowsperform; "windowsperformancerecordercontrol.dll"
0x180002332  mov     [rbp+57h+var_28], rax
0x180002336  lea     rax, aMsxml6rDll; "msxml6r.dll"
0x18000233d  mov     [rbp+57h+var_60], ecx
0x180002340  mov     [rbp+57h+var_50], ecx
0x180002343  mov     ecx, 60h ; '`'; Size
0x180002348  mov     [rbp+57h+var_18], rax
0x18000234c  mov     [rbp+57h+var_30], 558h
0x180002353  mov     [rbp+57h+var_20], 0Ch
0x18000235a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000235f  mov     r8d, 60h ; '`'; Size
0x180002365  mov     cs:?system_error_modules@windiag@@3V?$vector@U?$pair@HPEBD@std@@V?$allocator@U?$pair@HPEBD@std@@@2@@std@@B, rax; std::vector<std::pair<int,char const *>> const windiag::system_error_modules
0x18000236c  lea     rdx, [rbp+57h+Src]; Src
0x180002370  mov     cs:qword_1800BECE0, rax
0x180002377  mov     rcx, rax; void *
0x18000237a  lea     rbx, [rax+60h]
0x18000237e  mov     cs:qword_1800BECE8, rbx
0x180002385  call    memmove_0
0x18000238a  lea     rcx, [rbp+57h+var_80]
0x18000238e  mov     cs:qword_1800BECE0, rbx
0x180002395  mov     [rbp+57h+var_80], 0
0x18000239d  call    ??1?$_Tidy_guard@V?$vector@U?$pair@HPEBD@std@@V?$allocator@U?$pair@HPEBD@std@@@2@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<std::pair<int,char const *>>>::~_Tidy_guard<std::vector<std::pair<int,char const *>>>(void)
0x1800023a2  lea     rcx, windiag___dynamic_atexit_destructor_for__system_error_modules__; void (__cdecl *)()
0x1800023a9  call    atexit
0x1800023ae  mov     rcx, [rbp+57h+var_10]
0x1800023b2  xor     rcx, rsp; StackCookie
0x1800023b5  call    __security_check_cookie
0x1800023ba  mov     rbx, [rsp+0A0h+arg_0]
0x1800023c2  add     rsp, 0A0h
0x1800023c9  pop     rbp
0x1800023ca  retn
```
