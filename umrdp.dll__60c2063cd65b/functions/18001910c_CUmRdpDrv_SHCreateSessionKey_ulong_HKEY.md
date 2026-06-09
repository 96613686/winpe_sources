# CUmRdpDrv::_SHCreateSessionKey(ulong,HKEY__ * *)

- ea: `0x18001910c`
- end: `0x180019192`
- name: `?_SHCreateSessionKey@CUmRdpDrv@@AEAAJKPEAPEAUHKEY__@@@Z`
- size: `134`
- prototype: `int(CUmRdpDrv *__hidden this, unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180018624`
- `0x180018b44`

## callees

- `0x180018f64`
- `0x18001910c`
- `0x180019198`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019172`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019152`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019152`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001916a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001916a`

## pseudocode

```c
__int64 __fastcall CUmRdpDrv::_SHCreateSessionKey(WCHAR *this, __int64 a2, HKEY *a3)
{
  signed int SessionKeyName; // ebx
  HKEY v6; // rax
  HKEY v7; // rdi
  LSTATUS v8; // eax
  signed int LastError; // eax

  *a3 = 0;
  SessionKeyName = CUmRdpDrv::_GetSessionKeyName((CUmRdpDrv *)this);
  if ( SessionKeyName >= 0 )
  {
    v6 = _SHGetExplorerHkey();
    v7 = v6;
    if ( v6 )
    {
      v8 = RegOpenKeyExW(v6, this + 512, 0, 0x20006u, a3);
      SessionKeyName = v8;
      if ( v8 > 0 )
        SessionKeyName = (unsigned __int16)v8 | 0x80070000;
      RegCloseKey(v7);
    }
    else
    {
      LastError = GetLastError();
      SessionKeyName = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)SessionKeyName;
}

```

## disassembly

```asm
0x18001910c  push    rbx
0x18001910e  push    rbp
0x18001910f  push    rsi
0x180019110  push    rdi
0x180019111  sub     rsp, 38h
0x180019115  mov     rsi, r8
0x180019118  mov     qword ptr [r8], 0
0x18001911f  mov     rbp, rcx
0x180019122  call    ?_GetSessionKeyName@CUmRdpDrv@@AEAAJXZ; CUmRdpDrv::_GetSessionKeyName(void)
0x180019127  mov     ebx, eax
0x180019129  test    eax, eax
0x18001912b  js      short loc_180019187
0x18001912d  call    ?_SHGetExplorerHkey@@YAPEAUHKEY__@@XZ; _SHGetExplorerHkey(void)
0x180019132  mov     rdi, rax
0x180019135  test    rax, rax
0x180019138  jz      short loc_180019172
0x18001913a  lea     rdx, [rbp+400h]; lpSubKey
0x180019141  mov     [rsp+58h+phkResult], rsi; phkResult
0x180019146  mov     r9d, 20006h; samDesired
0x18001914c  xor     r8d, r8d; ulOptions
0x18001914f  mov     rcx, rax; hKey
0x180019152  call    cs:__imp_RegOpenKeyExW
0x180019158  mov     ebx, eax
0x18001915a  test    eax, eax
0x18001915c  jle     short loc_180019167
0x18001915e  movzx   ebx, ax
0x180019161  or      ebx, 80070000h
0x180019167  mov     rcx, rdi; hKey
0x18001916a  call    cs:__imp_RegCloseKey
0x180019170  jmp     short loc_180019187
0x180019172  call    cs:__imp_GetLastError
0x180019178  mov     ebx, eax
0x18001917a  test    eax, eax
0x18001917c  jle     short loc_180019187
0x18001917e  movzx   ebx, ax
0x180019181  or      ebx, 80070000h
0x180019187  mov     eax, ebx
0x180019189  add     rsp, 38h
0x18001918d  pop     rdi
0x18001918e  pop     rsi
0x18001918f  pop     rbp
0x180019190  pop     rbx
0x180019191  retn
```
