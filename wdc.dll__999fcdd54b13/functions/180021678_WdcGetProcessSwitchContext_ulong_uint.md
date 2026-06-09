# WdcGetProcessSwitchContext(ulong,uint *)

- ea: `0x180021678`
- end: `0x18002181a`
- name: `?WdcGetProcessSwitchContext@@YAJKPEAI@Z`
- size: `418`
- prototype: `__int64 __fastcall(DWORD dwProcessId, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000d4a0`

## callees

- `0x18000b854`
- `0x180021678`
- `0x18003b0ac`
- `0x180084ac8`
- `0x180084e10`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800216d5`
- `KERNEL32!CloseHandle` at `0x1800216d5`
- `KERNEL32!GetLastError` at `0x1800216e3`
- `KERNEL32!GetLastError` at `0x1800216e3`
- `KERNEL32!OpenProcess` at `0x1800216ab`
- `KERNEL32!OpenProcess` at `0x1800216ab`

## pseudocode

```c
__int64 __fastcall WdcGetProcessSwitchContext(DWORD dwProcessId, unsigned int *a2)
{
  HANDLE v4; // rax
  void *v5; // rsi
  BOOL v6; // ebx
  unsigned int v7; // ebx
  signed int LastError; // eax
  __int128 v10; // [rsp+30h] [rbp-348h] BYREF
  _BYTE Buf2[808]; // [rsp+48h] [rbp-330h] BYREF

  memset_0(&v10, 0, 0x340u);
  v4 = OpenProcess(0x410u, 0, dwProcessId);
  v5 = v4;
  if ( !v4 || (v6 = SbReadProcContextByHandle((__int64)v4, &v10) != 0, CloseHandle(v5), !v6) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (v7 & 0x80000000) == 0 )
        goto LABEL_8;
    }
    else
    {
      v7 = -2147467259;
    }
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
      "WdcGetProcessSwitchContext",
      0,
      L"FAILURE: 0x%08x",
      v7);
    return v7;
  }
  v7 = 0;
LABEL_8:
  if ( !memcmp_0(WINTHRESHOLD_CONTEXT_GUID, Buf2, 0x10u) )
  {
    *a2 = 32265;
  }
  else if ( !memcmp_0(WINBLUE_CONTEXT_GUID, Buf2, 0x10u) )
  {
    *a2 = 32264;
  }
  else if ( !memcmp_0(WIN8_CONTEXT_GUID, Buf2, 0x10u) )
  {
    *a2 = 32263;
  }
  else if ( !memcmp_0(WIN7_CONTEXT_GUID, Buf2, 0x10u) )
  {
    *a2 = 32262;
  }
  else if ( !memcmp_0(VISTA_CONTEXT_GUID, Buf2, 0x10u) )
  {
    *a2 = 32261;
  }
  else if ( !memcmp_0(XP_CONTEXT_GUID, Buf2, 0x10u) )
  {
    *a2 = 32260;
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v7;
}

```

## disassembly

```asm
0x180021678  mov     [rsp+arg_0], rbx
0x18002167d  mov     [rsp+arg_8], rsi
0x180021682  push    rdi
0x180021683  sub     rsp, 370h
0x18002168a  mov     rdi, rdx
0x18002168d  mov     ebx, ecx
0x18002168f  xor     edx, edx; Val
0x180021691  lea     rcx, [rsp+378h+var_348]; void *
0x180021696  mov     r8d, 340h; Size
0x18002169c  call    memset_0
0x1800216a1  mov     r8d, ebx; dwProcessId
0x1800216a4  xor     edx, edx; bInheritHandle
0x1800216a6  mov     ecx, 410h; dwDesiredAccess
0x1800216ab  call    cs:__imp_OpenProcess
0x1800216b1  mov     rsi, rax
0x1800216b4  test    rax, rax
0x1800216b7  jz      short loc_1800216E3
0x1800216b9  lea     rdx, [rsp+378h+var_348]
0x1800216be  mov     rcx, rax
0x1800216c1  call    SbReadProcContextByHandle
0x1800216c6  mov     ebx, eax
0x1800216c8  mov     eax, 1
0x1800216cd  test    ebx, ebx
0x1800216cf  cmovnz  ebx, eax
0x1800216d2  mov     rcx, rsi; hObject
0x1800216d5  call    cs:__imp_CloseHandle
0x1800216db  test    ebx, ebx
0x1800216dd  jz      short loc_1800216E3
0x1800216df  xor     ebx, ebx
0x1800216e1  jmp     short loc_180021706
0x1800216e3  call    cs:__imp_GetLastError
0x1800216e9  mov     ebx, eax
0x1800216eb  test    eax, eax
0x1800216ed  jz      loc_1800217DB
0x1800216f3  jle     short loc_1800216FE
0x1800216f5  movzx   ebx, ax
0x1800216f8  or      ebx, 80070000h
0x1800216fe  test    ebx, ebx
0x180021700  js      loc_1800217E0
0x180021706  mov     esi, 10h
0x18002170b  lea     rdx, [rsp+378h+Buf2]; Buf2
0x180021710  mov     r8d, esi; Size
0x180021713  lea     rcx, WINTHRESHOLD_CONTEXT_GUID; Buf1
0x18002171a  call    memcmp_0
0x18002171f  test    eax, eax
0x180021721  jnz     short loc_18002172E
0x180021723  mov     dword ptr [rdi], 7E09h
0x180021729  jmp     loc_180021803
0x18002172e  mov     r8, rsi; Size
0x180021731  lea     rdx, [rsp+378h+Buf2]; Buf2
0x180021736  lea     rcx, WINBLUE_CONTEXT_GUID; Buf1
0x18002173d  call    memcmp_0
0x180021742  test    eax, eax
0x180021744  jnz     short loc_180021751
0x180021746  mov     dword ptr [rdi], 7E08h
0x18002174c  jmp     loc_180021803
0x180021751  mov     r8, rsi; Size
0x180021754  lea     rdx, [rsp+378h+Buf2]; Buf2
0x180021759  lea     rcx, WIN8_CONTEXT_GUID; Buf1
0x180021760  call    memcmp_0
0x180021765  test    eax, eax
0x180021767  jnz     short loc_180021774
0x180021769  mov     dword ptr [rdi], 7E07h
0x18002176f  jmp     loc_180021803
0x180021774  mov     r8, rsi; Size
0x180021777  lea     rdx, [rsp+378h+Buf2]; Buf2
0x18002177c  lea     rcx, WIN7_CONTEXT_GUID; Buf1
0x180021783  call    memcmp_0
0x180021788  test    eax, eax
0x18002178a  jnz     short loc_180021794
0x18002178c  mov     dword ptr [rdi], 7E06h
0x180021792  jmp     short loc_180021803
0x180021794  mov     r8, rsi; Size
0x180021797  lea     rdx, [rsp+378h+Buf2]; Buf2
0x18002179c  lea     rcx, VISTA_CONTEXT_GUID; Buf1
0x1800217a3  call    memcmp_0
0x1800217a8  test    eax, eax
0x1800217aa  jnz     short loc_1800217B4
0x1800217ac  mov     dword ptr [rdi], 7E05h
0x1800217b2  jmp     short loc_180021803
0x1800217b4  mov     r8, rsi; Size
0x1800217b7  lea     rdx, [rsp+378h+Buf2]; Buf2
0x1800217bc  lea     rcx, XP_CONTEXT_GUID; Buf1
0x1800217c3  call    memcmp_0
0x1800217c8  test    eax, eax
0x1800217ca  jnz     short loc_1800217D4
0x1800217cc  mov     dword ptr [rdi], 7E04h
0x1800217d2  jmp     short loc_180021803
0x1800217d4  mov     ebx, 80004005h
0x1800217d9  jmp     short loc_180021803
0x1800217db  mov     ebx, 80004005h
0x1800217e0  mov     eax, ebx
0x1800217e2  mov     [rsp+378h+var_358], ebx
0x1800217e6  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800217ed  xor     r8d, r8d; int
0x1800217f0  lea     rdx, aWdcgetprocesss; "WdcGetProcessSwitchContext"
0x1800217f7  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x1800217fe  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180021803  lea     r11, [rsp+378h+var_8]
0x18002180b  mov     eax, ebx
0x18002180d  mov     rbx, [r11+10h]
0x180021811  mov     rsi, [r11+18h]
0x180021815  mov     rsp, r11
0x180021818  pop     rdi
0x180021819  retn
```
