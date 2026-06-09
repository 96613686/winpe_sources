# WdsSrvGetFunction(char const *,void * *)

- ea: `0x18003c78c`
- end: `0x18003c884`
- name: `?WdsSrvGetFunction@@YAKPEBDPEAPEAX@Z`
- size: `248`
- prototype: `unsigned int __fastcall(LPCSTR lpProcName, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005b00`

## callees

- `0x18003c78c`
- `0x18003ce78`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003c817`
- `KERNEL32!GetProcAddress` at `0x18003c817`
- `KERNEL32!FreeLibrary` at `0x18003c860`
- `KERNEL32!FreeLibrary` at `0x18003c860`
- `KERNEL32!GetModuleHandleExW` at `0x18003c7bb`
- `KERNEL32!GetModuleHandleExW` at `0x18003c7bb`
- `KERNEL32!GetLastError` at `0x18003c7cf`
- `KERNEL32!GetLastError` at `0x18003c828`
- `KERNEL32!GetLastError` at `0x18003c7cf`
- `KERNEL32!GetLastError` at `0x18003c828`

## string_xrefs

- `0x18003c7e1`: `onecore\base\eco\wds\wdslib\common\src\wdssrvhelp.cpp`
- `0x18003c7fd`: `onecore\base\eco\wds\wdslib\common\src\wdssrvhelp.cpp`
- `0x18003c83a`: `onecore\base\eco\wds\wdslib\common\src\wdssrvhelp.cpp`
- `0x18003c7b0`: `wdssrv.dll`

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
0x18003c78c  mov     rax, rsp
0x18003c78f  mov     [rax+8], rbx
0x18003c793  mov     [rax+10h], rsi
0x18003c797  mov     [rax+20h], rdi
0x18003c79b  push    r14
0x18003c79d  sub     rsp, 20h
0x18003c7a1  and     qword ptr [rax+18h], 0
0x18003c7a6  lea     r8, [rax+18h]; phModule
0x18003c7aa  mov     rdi, rdx
0x18003c7ad  mov     rsi, rcx
0x18003c7b0  lea     rdx, ModuleName; "wdssrv.dll"
0x18003c7b7  xor     ecx, ecx; dwFlags
0x18003c7b9  xor     ebx, ebx
0x18003c7bb  call    cs:__imp_GetModuleHandleExW
0x18003c7c2  nop     dword ptr [rax+rax+00h]
0x18003c7c7  lea     r14d, [rbx+1Fh]
0x18003c7cb  test    eax, eax
0x18003c7cd  jnz     short loc_18003C7F7
0x18003c7cf  call    cs:__imp_GetLastError
0x18003c7d6  nop     dword ptr [rax+rax+00h]
0x18003c7db  mov     r9d, 0A4h; unsigned int
0x18003c7e1  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003c7e8  mov     ecx, eax; unsigned int
0x18003c7ea  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18003c7ef  test    eax, eax
0x18003c7f1  mov     ebx, eax
0x18003c7f3  cmovz   ebx, r14d
0x18003c7f7  mov     r9d, 76h ; 'v'; unsigned int
0x18003c7fd  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003c804  mov     ecx, ebx; unsigned int
0x18003c806  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18003c80b  test    eax, eax
0x18003c80d  jnz     short loc_18003C856
0x18003c80f  mov     rcx, [rsp+28h+hModule]; hModule
0x18003c814  mov     rdx, rsi; lpProcName
0x18003c817  call    cs:__imp_GetProcAddress
0x18003c81e  nop     dword ptr [rax+rax+00h]
0x18003c823  test    rax, rax
0x18003c826  jnz     short loc_18003C853
0x18003c828  call    cs:__imp_GetLastError
0x18003c82f  nop     dword ptr [rax+rax+00h]
0x18003c834  mov     r9d, 7Bh ; '{'; unsigned int
0x18003c83a  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003c841  mov     ecx, eax; unsigned int
0x18003c843  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18003c848  mov     ebx, eax
0x18003c84a  test    eax, eax
0x18003c84c  jnz     short loc_18003C856
0x18003c84e  mov     ebx, r14d
0x18003c851  jmp     short loc_18003C856
0x18003c853  mov     [rdi], rax
0x18003c856  mov     rcx, [rsp+28h+hModule]; hLibModule
0x18003c85b  test    rcx, rcx
0x18003c85e  jz      short loc_18003C86C
0x18003c860  call    cs:__imp_FreeLibrary
0x18003c867  nop     dword ptr [rax+rax+00h]
0x18003c86c  mov     rsi, [rsp+28h+arg_8]
0x18003c871  mov     eax, ebx
0x18003c873  mov     rbx, [rsp+28h+arg_0]
0x18003c878  mov     rdi, [rsp+28h+arg_18]
0x18003c87d  add     rsp, 20h
0x18003c881  pop     r14
0x18003c883  retn
```
