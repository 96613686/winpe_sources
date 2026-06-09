# mlib::WinSQMApis::LoadLibraryW(void)

- ea: `0x140056e08`
- end: `0x140056eff`
- name: `?LoadLibraryW@WinSQMApis@mlib@@QEAAKXZ`
- size: `247`
- prototype: `unsigned int __fastcall(mlib::WinSQMApis *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140001830`

## callees

- `0x140056e08`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140056e3a`
- `KERNEL32!GetProcAddress` at `0x140056e5a`
- `KERNEL32!GetProcAddress` at `0x140056e7a`
- `KERNEL32!GetProcAddress` at `0x140056e9a`
- `KERNEL32!GetProcAddress` at `0x140056ebe`
- `KERNEL32!GetProcAddress` at `0x140056ee2`
- `KERNEL32!GetProcAddress` at `0x140056e3a`
- `KERNEL32!GetProcAddress` at `0x140056e5a`
- `KERNEL32!GetProcAddress` at `0x140056e7a`
- `KERNEL32!GetProcAddress` at `0x140056e9a`
- `KERNEL32!GetProcAddress` at `0x140056ebe`
- `KERNEL32!GetProcAddress` at `0x140056ee2`
- `KERNEL32!LoadLibraryW` at `0x140056e13`
- `KERNEL32!LoadLibraryW` at `0x140056e13`
- `KERNEL32!GetLastError` at `0x140056e29`

## string_xrefs

- `0x140056e0c`: `ntdll.dll`

## pseudocode

```c
DWORD __fastcall mlib::WinSQMApis::LoadLibraryW(mlib::WinSQMApis *this)
{
  HMODULE LibraryW; // rax

  LibraryW = LoadLibraryW(L"ntdll.dll");
  g_SQM = LibraryW;
  if ( LibraryW
    && (qword_1401C6668 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetProcAddress(LibraryW, "WinSqmSetDWORD")) != 0
    && (qword_1401C6670 = (__int64)GetProcAddress(g_SQM, "WinSqmStartSession")) != 0
    && (qword_1401C6678 = (__int64)GetProcAddress(g_SQM, "WinSqmEndSession")) != 0
    && (qword_1401C6680 = (__int64)GetProcAddress(g_SQM, "WinSqmIncrementDWORD")) != 0
    && (qword_1401C6688 = (__int64)GetProcAddress(g_SQM, "WinSqmSetString")) != 0
    && (qword_1401C6690 = (__int64)GetProcAddress(g_SQM, "WinSqmAddToStream")) != 0 )
  {
    return 0;
  }
  else
  {
    return GetLastError();
  }
}

```

## disassembly

```asm
0x140056e08  sub     rsp, 28h
0x140056e0c  lea     rcx, ModuleName; "ntdll.dll"
0x140056e13  call    cs:__imp_LoadLibraryW
0x140056e19  mov     cs:?g_SQM@@3VSQM@@A, rax; SQM g_SQM
0x140056e20  test    rax, rax
0x140056e23  jnz     short loc_140056E30
0x140056e25  add     rsp, 28h
0x140056e29  jmp     cs:__imp_GetLastError
0x140056e30  lea     rdx, aWinsqmsetdword; "WinSqmSetDWORD"
0x140056e37  mov     rcx, rax; hModule
0x140056e3a  call    cs:__imp_GetProcAddress
0x140056e40  mov     cs:qword_1401C6668, rax
0x140056e47  test    rax, rax
0x140056e4a  jz      short loc_140056E25
0x140056e4c  mov     rcx, cs:?g_SQM@@3VSQM@@A; hModule
0x140056e53  lea     rdx, aWinsqmstartses; "WinSqmStartSession"
0x140056e5a  call    cs:__imp_GetProcAddress
0x140056e60  mov     cs:qword_1401C6670, rax
0x140056e67  test    rax, rax
0x140056e6a  jz      short loc_140056E25
0x140056e6c  mov     rcx, cs:?g_SQM@@3VSQM@@A; hModule
0x140056e73  lea     rdx, aWinsqmendsessi; "WinSqmEndSession"
0x140056e7a  call    cs:__imp_GetProcAddress
0x140056e80  mov     cs:qword_1401C6678, rax
0x140056e87  test    rax, rax
0x140056e8a  jz      short loc_140056E25
0x140056e8c  mov     rcx, cs:?g_SQM@@3VSQM@@A; hModule
0x140056e93  lea     rdx, aWinsqmincremen; "WinSqmIncrementDWORD"
0x140056e9a  call    cs:__imp_GetProcAddress
0x140056ea0  mov     cs:qword_1401C6680, rax
0x140056ea7  test    rax, rax
0x140056eaa  jz      loc_140056E25
0x140056eb0  mov     rcx, cs:?g_SQM@@3VSQM@@A; hModule
0x140056eb7  lea     rdx, aWinsqmsetstrin; "WinSqmSetString"
0x140056ebe  call    cs:__imp_GetProcAddress
0x140056ec4  mov     cs:qword_1401C6688, rax
0x140056ecb  test    rax, rax
0x140056ece  jz      loc_140056E25
0x140056ed4  mov     rcx, cs:?g_SQM@@3VSQM@@A; hModule
0x140056edb  lea     rdx, aWinsqmaddtostr; "WinSqmAddToStream"
0x140056ee2  call    cs:__imp_GetProcAddress
0x140056ee8  mov     cs:qword_1401C6690, rax
0x140056eef  test    rax, rax
0x140056ef2  jz      loc_140056E25
0x140056ef8  xor     eax, eax
0x140056efa  add     rsp, 28h
0x140056efe  retn
```
