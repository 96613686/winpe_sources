# IniRegCreateKeyExW

- ea: `0x1004463c0`
- end: `0x100446616`
- name: `IniRegCreateKeyExW`
- size: `598`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD, REGSAM, LPSECURITY_ATTRIBUTES, PHKEY, LPDWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x100446360`

## callees

- `0x100401800`
- `0x100401970`
- `0x100401a40`
- `0x100401b70`
- `0x1004463c0`
- `0x100448120`
- `0x100448270`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x1004463f3`
- `KERNEL32!DebugBreak` at `0x100446404`
- `KERNEL32!DebugBreak` at `0x1004463f3`
- `KERNEL32!DebugBreak` at `0x100446404`
- `ADVAPI32!RegCreateKeyExW` at `0x10044656d`
- `ADVAPI32!RegCreateKeyExW` at `0x100446608`
- `ADVAPI32!RegCreateKeyExW` at `0x10044656d`
- `ADVAPI32!RegCreateKeyExW` at `0x100446608`

## pseudocode

```c
LSTATUS __fastcall IniRegCreateKeyExW(
        HKEY a1,
        const WCHAR *a2,
        DWORD a3,
        WCHAR *a4,
        DWORD dwOptions,
        REGSAM samDesired,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        PHKEY phkResult,
        LPDWORD lpdwDisposition)
{
  unsigned int Key; // [rsp+54h] [rbp-34h]
  HKEY Path; // [rsp+58h] [rbp-30h]
  HKEY hKey[2]; // [rsp+60h] [rbp-28h] BYREF
  int v13; // [rsp+70h] [rbp-18h]

  if ( dword_10049F370 )
  {
    if ( a4 )
      DebugBreak();
    if ( lpSecurityAttributes )
      DebugBreak();
    if ( (unsigned int)IniRegOpenKeyExW((int)a1, (int)a2, dwOptions, samDesired, phkResult) )
    {
      Path = (HKEY)IniRegMakePath(a1, a2);
      if ( !Path )
        return 8;
      *phkResult = Path;
      if ( lpdwDisposition )
        *lpdwDisposition = 1;
    }
    else if ( lpdwDisposition )
    {
      *lpdwDisposition = 2;
    }
    return IniRegReturnErrorCode(0);
  }
  else if ( dword_10049F378 || (unsigned int)IsIniRegSetupInitialized() )
  {
    ConfRegCrackHandle(a1, hKey);
    if ( v13 )
    {
      return IniRegReturnErrorCode(5);
    }
    else
    {
      Key = RegCreateKeyExW(
              hKey[0],
              a2,
              a3,
              a4,
              dwOptions,
              samDesired,
              lpSecurityAttributes,
              phkResult,
              lpdwDisposition);
      if ( !Key )
        Key = WrapHKEYHandleW(a1, a2, phkResult);
      return IniRegReturnErrorCode(Key);
    }
  }
  else
  {
    return RegCreateKeyExW(a1, a2, a3, a4, dwOptions, samDesired, lpSecurityAttributes, phkResult, lpdwDisposition);
  }
}

```

## disassembly

```asm
0x1004463c0  mov     [rsp+lpClass], r9
0x1004463c5  mov     [rsp+Reserved], r8d
0x1004463ca  mov     [rsp+lpSubKey], rdx
0x1004463cf  mov     [rsp+arg_0], rcx
0x1004463d4  sub     rsp, 88h
0x1004463db  cmp     cs:dword_10049F370, 0
0x1004463e2  jz      loc_1004464D5
0x1004463e8  cmp     [rsp+88h+lpClass], 0
0x1004463f1  jz      short loc_1004463F9
0x1004463f3  call    cs:__imp_DebugBreak
0x1004463f9  cmp     [rsp+88h+arg_30], 0
0x100446402  jz      short loc_10044640A
0x100446404  call    cs:__imp_DebugBreak
0x10044640a  mov     rax, [rsp+88h+arg_38]
0x100446412  mov     qword ptr [rsp+88h+dwOptions], rax; PHKEY
0x100446417  mov     r9d, [rsp+88h+arg_28]; int
0x10044641f  mov     r8d, [rsp+88h+arg_20]; int
0x100446427  mov     rdx, [rsp+88h+lpSubKey]; int
0x10044642f  mov     rcx, [rsp+88h+arg_0]; int
0x100446437  call    IniRegOpenKeyExW
0x10044643c  mov     [rsp+88h+var_38], eax
0x100446440  cmp     [rsp+88h+var_38], 0
0x100446445  jnz     short loc_100446462
0x100446447  cmp     [rsp+88h+arg_40], 0
0x100446450  jz      short loc_100446460
0x100446452  mov     rax, [rsp+88h+arg_40]
0x10044645a  mov     dword ptr [rax], 2
0x100446460  jmp     short loc_1004464C6
0x100446462  mov     [rsp+88h+var_38], 0
0x10044646a  cmp     [rsp+88h+var_38], 0
0x10044646f  jnz     short loc_1004464C6
0x100446471  mov     rdx, [rsp+88h+lpSubKey]
0x100446479  mov     rcx, [rsp+88h+arg_0]
0x100446481  call    IniRegMakePath
0x100446486  mov     [rsp+88h+var_30], rax
0x10044648b  cmp     [rsp+88h+var_30], 0
0x100446491  jnz     short loc_10044649D
0x100446493  mov     eax, 8
0x100446498  jmp     loc_10044660E
0x10044649d  mov     rax, [rsp+88h+arg_38]
0x1004464a5  mov     rcx, [rsp+88h+var_30]
0x1004464aa  mov     [rax], rcx
0x1004464ad  cmp     [rsp+88h+arg_40], 0
0x1004464b6  jz      short loc_1004464C6
0x1004464b8  mov     rax, [rsp+88h+arg_40]
0x1004464c0  mov     dword ptr [rax], 1
0x1004464c6  mov     ecx, [rsp+88h+var_38]
0x1004464ca  call    IniRegReturnErrorCode
0x1004464cf  jmp     loc_10044660E
0x1004464d5  cmp     cs:dword_10049F378, 0
0x1004464dc  jnz     short loc_1004464EB
0x1004464de  call    IsIniRegSetupInitialized
0x1004464e3  test    eax, eax
0x1004464e5  jz      loc_1004465AB
0x1004464eb  lea     rdx, [rsp+88h+hKey]
0x1004464f0  mov     rcx, [rsp+88h+arg_0]
0x1004464f8  call    ConfRegCrackHandle
0x1004464fd  cmp     [rsp+88h+var_18], 0
0x100446502  jz      short loc_100446513
0x100446504  mov     ecx, 5
0x100446509  call    IniRegReturnErrorCode
0x10044650e  jmp     loc_10044660E
0x100446513  mov     rax, [rsp+88h+arg_40]
0x10044651b  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x100446520  mov     rax, [rsp+88h+arg_38]
0x100446528  mov     [rsp+88h+phkResult], rax; phkResult
0x10044652d  mov     rax, [rsp+88h+arg_30]
0x100446535  mov     [rsp+88h+lpSecurityAttributes], rax; lpSecurityAttributes
0x10044653a  mov     eax, [rsp+88h+arg_28]
0x100446541  mov     [rsp+88h+samDesired], eax; samDesired
0x100446545  mov     eax, [rsp+88h+arg_20]
0x10044654c  mov     [rsp+88h+dwOptions], eax; dwOptions
0x100446550  mov     r9, [rsp+88h+lpClass]; lpClass
0x100446558  mov     r8d, [rsp+88h+Reserved]; Reserved
0x100446560  mov     rdx, [rsp+88h+lpSubKey]; lpSubKey
0x100446568  mov     rcx, [rsp+88h+hKey]; hKey
0x10044656d  call    cs:__imp_RegCreateKeyExW
0x100446573  mov     [rsp+88h+var_34], eax
0x100446577  cmp     [rsp+88h+var_34], 0
0x10044657c  jnz     short loc_10044659F
0x10044657e  mov     r8, [rsp+88h+arg_38]
0x100446586  mov     rdx, [rsp+88h+lpSubKey]
0x10044658e  mov     rcx, [rsp+88h+arg_0]
0x100446596  call    WrapHKEYHandleW
0x10044659b  mov     [rsp+88h+var_34], eax
0x10044659f  mov     ecx, [rsp+88h+var_34]
0x1004465a3  call    IniRegReturnErrorCode
0x1004465a8  jmp     short loc_10044660E
0x1004465ab  mov     rax, [rsp+88h+arg_40]
0x1004465b3  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x1004465b8  mov     rax, [rsp+88h+arg_38]
0x1004465c0  mov     [rsp+88h+phkResult], rax; phkResult
0x1004465c5  mov     rax, [rsp+88h+arg_30]
0x1004465cd  mov     [rsp+88h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1004465d2  mov     eax, [rsp+88h+arg_28]
0x1004465d9  mov     [rsp+88h+samDesired], eax; samDesired
0x1004465dd  mov     eax, [rsp+88h+arg_20]
0x1004465e4  mov     [rsp+88h+dwOptions], eax; dwOptions
0x1004465e8  mov     r9, [rsp+88h+lpClass]; lpClass
0x1004465f0  mov     r8d, [rsp+88h+Reserved]; Reserved
0x1004465f8  mov     rdx, [rsp+88h+lpSubKey]; lpSubKey
0x100446600  mov     rcx, [rsp+88h+arg_0]; hKey
0x100446608  call    cs:__imp_RegCreateKeyExW
0x10044660e  add     rsp, 88h
0x100446615  retn
```
