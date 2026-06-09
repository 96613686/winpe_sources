# OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x18000f178`
- end: `0x18000f2c5`
- name: `?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `333`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008930`

## callees

- `0x18000f178`
- `0x180010250`
- `0x1800102e0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18000f29e`
- `ADVAPI32!RegOpenKeyExA` at `0x18000f29e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f1c1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f1c1`
- `KERNEL32!GetLastError` at `0x18000f221`
- `KERNEL32!GetLastError` at `0x18000f221`
- `KERNEL32!WideCharToMultiByte` at `0x18000f214`
- `KERNEL32!WideCharToMultiByte` at `0x18000f27c`
- `KERNEL32!WideCharToMultiByte` at `0x18000f214`
- `KERNEL32!WideCharToMultiByte` at `0x18000f27c`

## pseudocode

```c
int __fastcall OpenRegSettings(HKEY a1, const unsigned __int16 *a2, __int64 a3, HKEY *phkResult)
{
  int result; // eax
  bool v6; // cc
  int cbMultiByte; // eax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  CHAR MultiByteStr[16]; // [rsp+40h] [rbp+0h] BYREF

  if ( Global::g_fWindowsNT )
  {
    result = RegOpenKeyExW(
               HKEY_CURRENT_USER,
               (LPCWSTR)L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows",
               0,
               0x20006u,
               phkResult);
  }
  else
  {
    cbMultiByte = WideCharToMultiByte(
                    0,
                    0,
                    (LPCWCH)L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows",
                    -1,
                    0,
                    0,
                    0,
                    0);
    if ( !cbMultiByte )
      goto LABEL_7;
    v8 = cbMultiByte + 15LL;
    if ( v8 < cbMultiByte )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
    v10 = alloca(v9);
    v11 = alloca(v9);
    if ( !WideCharToMultiByte(
            0,
            0,
            (LPCWCH)L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows",
            -1,
            MultiByteStr,
            cbMultiByte,
            0,
            0) )
    {
LABEL_7:
      result = GetLastError();
      v6 = result <= 0;
      goto LABEL_4;
    }
    result = RegOpenKeyExA(HKEY_CURRENT_USER, MultiByteStr, 0, 0x20006u, phkResult);
  }
  v6 = result <= 0;
  if ( !result )
    return 0;
LABEL_4:
  if ( !v6 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000f178  push    rbp
0x18000f17a  sub     rsp, 50h
0x18000f17e  lea     rbp, [rsp+40h]
0x18000f183  mov     [rbp+10h+arg_0], rbx
0x18000f187  mov     [rbp+10h+arg_8], rdi
0x18000f18b  mov     rax, cs:__security_cookie
0x18000f192  xor     rax, rbp
0x18000f195  mov     qword ptr [rbp+10h+MultiByteStr], rax
0x18000f199  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x18000f1a0  mov     rbx, r9
0x18000f1a3  jz      short loc_18000F1E2
0x18000f1a5  mov     r9d, 20006h; samDesired
0x18000f1ab  mov     [rsp+50h+phkResult], rbx; phkResult
0x18000f1b0  xor     r8d, r8d; ulOptions
0x18000f1b3  lea     rdx, WideCharStr; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000f1ba  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000f1c1  call    cs:__imp_RegOpenKeyExW
0x18000f1c7  test    eax, eax
0x18000f1c9  jz      loc_18000F2A9
0x18000f1cf  jle     loc_18000F2AB
0x18000f1d5  movzx   eax, ax
0x18000f1d8  or      eax, 80070000h
0x18000f1dd  jmp     loc_18000F2AB
0x18000f1e2  mov     [rsp+50h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000f1eb  lea     r8, WideCharStr; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000f1f2  mov     [rsp+50h+lpDefaultChar], 0; lpDefaultChar
0x18000f1fb  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000f1ff  mov     [rsp+50h+cbMultiByte], 0; cbMultiByte
0x18000f207  xor     edx, edx; dwFlags
0x18000f209  xor     ecx, ecx; CodePage
0x18000f20b  mov     [rsp+50h+phkResult], 0; lpMultiByteStr
0x18000f214  call    cs:__imp_WideCharToMultiByte
0x18000f21a  movsxd  rdx, eax
0x18000f21d  test    eax, eax
0x18000f21f  jnz     short loc_18000F22B
0x18000f221  call    cs:__imp_GetLastError
0x18000f227  test    eax, eax
0x18000f229  jmp     short loc_18000F1CF
0x18000f22b  lea     rcx, [rdx+0Fh]
0x18000f22f  cmp     rcx, rdx
0x18000f232  ja      short loc_18000F23E
0x18000f234  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000f23e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000f242  mov     rax, rcx
0x18000f245  call    _alloca_probe
0x18000f24a  sub     rsp, rcx
0x18000f24d  lea     r8, WideCharStr; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000f254  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000f258  xor     ecx, ecx; CodePage
0x18000f25a  mov     [rsp+50h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000f263  lea     rdi, [rsp+50h+MultiByteStr]
0x18000f268  mov     [rsp+50h+lpDefaultChar], 0; lpDefaultChar
0x18000f271  mov     [rsp+50h+cbMultiByte], edx; cbMultiByte
0x18000f275  xor     edx, edx; dwFlags
0x18000f277  mov     [rsp+50h+phkResult], rdi; lpMultiByteStr
0x18000f27c  call    cs:__imp_WideCharToMultiByte
0x18000f282  test    eax, eax
0x18000f284  jz      short loc_18000F221
0x18000f286  mov     r9d, 20006h; samDesired
0x18000f28c  mov     [rsp+50h+phkResult], rbx; phkResult
0x18000f291  xor     r8d, r8d; ulOptions
0x18000f294  mov     rdx, rdi; lpSubKey
0x18000f297  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000f29e  call    cs:__imp_RegOpenKeyExA
0x18000f2a4  jmp     loc_18000F1C7
0x18000f2a9  xor     eax, eax
0x18000f2ab  mov     rcx, qword ptr [rbp+10h+MultiByteStr]
0x18000f2af  xor     rcx, rbp; StackCookie
0x18000f2b2  call    __security_check_cookie
0x18000f2b7  mov     rbx, [rbp+10h+arg_0]
0x18000f2bb  mov     rdi, [rbp+10h+arg_8]
0x18000f2bf  lea     rsp, [rbp+10h]
0x18000f2c3  pop     rbp
0x18000f2c4  retn
```
