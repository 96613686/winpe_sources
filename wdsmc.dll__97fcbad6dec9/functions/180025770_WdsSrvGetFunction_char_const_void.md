# WdsSrvGetFunction(char const *,void * *)

- ea: `0x180025770`
- end: `0x18002584a`
- name: `?WdsSrvGetFunction@@YAKPEBDPEAPEAX@Z`
- size: `218`
- prototype: `unsigned int __fastcall(LPCSTR lpProcName, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008ff0`

## callees

- `0x180025770`
- `0x180025850`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18002582c`
- `KERNEL32!FreeLibrary` at `0x18002582c`
- `KERNEL32!GetProcAddress` at `0x1800257ef`
- `KERNEL32!GetProcAddress` at `0x1800257ef`
- `KERNEL32!GetLastError` at `0x1800257ad`
- `KERNEL32!GetLastError` at `0x1800257fa`
- `KERNEL32!GetLastError` at `0x1800257ad`
- `KERNEL32!GetLastError` at `0x1800257fa`
- `KERNEL32!GetModuleHandleExW` at `0x18002579f`
- `KERNEL32!GetModuleHandleExW` at `0x18002579f`

## string_xrefs

- `0x1800257b9`: `onecore\base\eco\wds\wdslib\common\src\wdssrvhelp.cpp`
- `0x1800257d5`: `onecore\base\eco\wds\wdslib\common\src\wdssrvhelp.cpp`
- `0x180025806`: `onecore\base\eco\wds\wdslib\common\src\wdssrvhelp.cpp`
- `0x180025794`: `wdssrv.dll`

## pseudocode

```c
__int64 __fastcall WdsSrvGetFunction(LPCSTR lpProcName, FARPROC *a2)
{
  unsigned int v4; // ebx
  const char *v5; // rdx
  DWORD LastError; // eax
  const char *v7; // rdx
  FARPROC ProcAddress; // rax
  DWORD v9; // eax
  const char *v10; // rdx
  HMODULE hModule; // [rsp+40h] [rbp+18h] BYREF

  hModule = 0;
  v4 = 0;
  if ( !GetModuleHandleExW(0, L"wdssrv.dll", &hModule) )
  {
    LastError = GetLastError();
    v4 = ElValidateWin32(LastError, v7, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdssrvhelp.cpp", 0xA4u);
    if ( !v4 )
      v4 = 31;
  }
  if ( !ElValidateWin32(v4, v5, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdssrvhelp.cpp", 0x76u) )
  {
    ProcAddress = GetProcAddress(hModule, lpProcName);
    if ( ProcAddress )
    {
      *a2 = ProcAddress;
    }
    else
    {
      v9 = GetLastError();
      v4 = ElValidateWin32(v9, v10, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdssrvhelp.cpp", 0x7Bu);
      if ( !v4 )
        v4 = 31;
    }
  }
  if ( hModule )
    FreeLibrary(hModule);
  return v4;
}

```

## disassembly

```asm
0x180025770  mov     rax, rsp
0x180025773  mov     [rax+8], rbx
0x180025777  mov     [rax+10h], rsi
0x18002577b  mov     [rax+20h], rdi
0x18002577f  push    r14
0x180025781  sub     rsp, 20h
0x180025785  and     qword ptr [rax+18h], 0
0x18002578a  lea     r8, [rax+18h]; phModule
0x18002578e  mov     rdi, rdx
0x180025791  mov     rsi, rcx
0x180025794  lea     rdx, aWdssrvDll_0; "wdssrv.dll"
0x18002579b  xor     ecx, ecx; dwFlags
0x18002579d  xor     ebx, ebx
0x18002579f  call    cs:__imp_GetModuleHandleExW
0x1800257a5  lea     r14d, [rbx+1Fh]
0x1800257a9  test    eax, eax
0x1800257ab  jnz     short loc_1800257CF
0x1800257ad  call    cs:__imp_GetLastError
0x1800257b3  mov     r9d, 0A4h; unsigned int
0x1800257b9  lea     r8, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800257c0  mov     ecx, eax; unsigned int
0x1800257c2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800257c7  test    eax, eax
0x1800257c9  mov     ebx, eax
0x1800257cb  cmovz   ebx, r14d
0x1800257cf  mov     r9d, 76h ; 'v'; unsigned int
0x1800257d5  lea     r8, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800257dc  mov     ecx, ebx; unsigned int
0x1800257de  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800257e3  test    eax, eax
0x1800257e5  jnz     short loc_180025822
0x1800257e7  mov     rcx, [rsp+28h+hModule]; hModule
0x1800257ec  mov     rdx, rsi; lpProcName
0x1800257ef  call    cs:__imp_GetProcAddress
0x1800257f5  test    rax, rax
0x1800257f8  jnz     short loc_18002581F
0x1800257fa  call    cs:__imp_GetLastError
0x180025800  mov     r9d, 7Bh ; '{'; unsigned int
0x180025806  lea     r8, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002580d  mov     ecx, eax; unsigned int
0x18002580f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180025814  mov     ebx, eax
0x180025816  test    eax, eax
0x180025818  jnz     short loc_180025822
0x18002581a  mov     ebx, r14d
0x18002581d  jmp     short loc_180025822
0x18002581f  mov     [rdi], rax
0x180025822  mov     rcx, [rsp+28h+hModule]; hLibModule
0x180025827  test    rcx, rcx
0x18002582a  jz      short loc_180025832
0x18002582c  call    cs:__imp_FreeLibrary
0x180025832  mov     rsi, [rsp+28h+arg_8]
0x180025837  mov     eax, ebx
0x180025839  mov     rbx, [rsp+28h+arg_0]
0x18002583e  mov     rdi, [rsp+28h+arg_18]
0x180025843  add     rsp, 20h
0x180025847  pop     r14
0x180025849  retn
```
