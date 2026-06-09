# Settings::CHandlerFromDeviceHandlerEnum::Next(ushort *,ulong)

- ea: `0x180013cc0`
- end: `0x180013f0b`
- name: `?Next@CHandlerFromDeviceHandlerEnum@Settings@@QEAAJPEAGK@Z`
- size: `587`
- prototype: `__int64 __fastcall(PHKEY phkResult, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800056c8`

## callees

- `0x180013cc0`
- `0x180013f20`
- `0x180013fb0`
- `0x1800329cc`
- `0x180032c6a`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013e17`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013e17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013e93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013e93`

## pseudocode

```c
int __fastcall Settings::CHandlerFromDeviceHandlerEnum::Next(_DWORD *phkResult, unsigned __int16 *a2)
{
  unsigned int v4; // edx
  int result; // eax
  int v6; // edi
  DWORD v7; // edx
  HKEY v8; // rcx
  LSTATUS v9; // ecx
  size_t *v10; // r8
  size_t v11; // rdx
  WCHAR *v12; // rax
  HKEY v13; // rcx
  bool v14; // sf
  unsigned int v15; // edx
  HKEY v16; // rcx
  LPDWORD lpReserved; // [rsp+20h] [rbp-2E8h]
  DWORD cchValueName[4]; // [rsp+40h] [rbp-2C8h] BYREF
  WCHAR SubKey[83]; // [rsp+50h] [rbp-2B8h] BYREF
  _BYTE v20[354]; // [rsp+F6h] [rbp-212h] BYREF
  WCHAR ValueName[64]; // [rsp+260h] [rbp-A8h] BYREF

  v4 = phkResult[4];
  phkResult[4] = v4 + 1;
  result = _RegEnumStringValue(*(HKEY *)phkResult, v4, a2, 0x5Au);
  v6 = 0;
  if ( result == 1 )
  {
    while ( !v6 )
    {
      wcscpy(SubKey, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AutoplayHandlers\\EventHandlrs\\");
      memset_0(v20, 0, sizeof(v20));
      v7 = phkResult[5];
      v8 = (HKEY)*((_QWORD *)phkResult + 1);
      phkResult[5] = v7 + 1;
      cchValueName[0] = 64;
      ValueName[0] = 0;
      v9 = RegEnumValueW(v8, v7, ValueName, cchValueName, 0, 0, 0, 0);
      if ( v9 )
      {
        result = -2147467259;
        v6 = 1;
        if ( v9 == 259 )
          result = 1;
      }
      else
      {
        v11 = 260;
        v12 = SubKey;
        while ( *v12 )
        {
          ++v12;
          if ( !--v11 )
          {
            result = -2147024809;
            goto LABEL_17;
          }
        }
        result = StringCopyWorkerW((STRSAFE_LPWSTR)ValueName - v11 + 3, v11, v10, ValueName, (size_t)lpReserved);
        if ( result >= 0 )
        {
          v13 = *(HKEY *)phkResult;
          phkResult[4] = 0;
          if ( v13 )
            _RegCloseKey(v13);
          *(_QWORD *)phkResult = 0;
          result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, (PHKEY)phkResult);
          v14 = result < 0;
          if ( result > 0 )
          {
            result = (unsigned __int16)result | 0x80070000;
            v14 = result < 0;
          }
          if ( v14 )
            return result;
          v15 = phkResult[4];
          v16 = *(HKEY *)phkResult;
          phkResult[4] = v15 + 1;
          result = _RegEnumStringValue(v16, v15, a2, 0x5Au);
        }
      }
LABEL_17:
      if ( result != 1 )
        return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013cc0  mov     [rsp+arg_18], rbx
0x180013cc5  push    rbp
0x180013cc6  push    rsi
0x180013cc7  push    rdi
0x180013cc8  sub     rsp, 2F0h
0x180013ccf  mov     rax, cs:__security_cookie
0x180013cd6  xor     rax, rsp
0x180013cd9  mov     [rsp+308h+var_28], rax
0x180013ce1  mov     rsi, rdx
0x180013ce4  mov     rbx, rcx
0x180013ce7  mov     edx, [rcx+10h]; unsigned int
0x180013cea  mov     r9d, 5Ah ; 'Z'; unsigned int
0x180013cf0  mov     r8, rsi; unsigned __int16 *
0x180013cf3  lea     eax, [rdx+1]
0x180013cf6  mov     [rcx+10h], eax
0x180013cf9  mov     rcx, [rcx]; HKEY
0x180013cfc  call    ?_RegEnumStringValue@@YAJPEAUHKEY__@@KPEAGK@Z; _RegEnumStringValue(HKEY__ *,ulong,ushort *,ulong)
0x180013d01  xor     ebp, ebp
0x180013d03  mov     edi, ebp
0x180013d05  cmp     eax, 1
0x180013d08  jnz     loc_180013EE8
0x180013d0e  mov     [rsp+308h+arg_10], r14
0x180013d16  mov     r14d, eax
0x180013d19  nop     dword ptr [rax+00000000h]
0x180013d20  test    edi, edi
0x180013d22  jnz     loc_180013EE0
0x180013d28  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+10h; "\\Microsoft\\Windows\\CurrentVersion\\E"...
0x180013d2f  lea     rcx, [rsp+308h+var_212]; void *
0x180013d37  movaps  xmm0, xmmword ptr cs:aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180013d3e  xor     edx, edx; Val
0x180013d40  mov     rax, qword ptr cs:aSoftwareMicros+9Eh; "rs\\"
0x180013d47  mov     r8d, 162h; Size
0x180013d4d  movups  [rsp+308h+var_2A8], xmm1
0x180013d52  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+30h; "ws\\CurrentVersion\\Explorer\\AutoplayH"...
0x180013d59  movups  xmmword ptr [rsp+308h+SubKey], xmm0
0x180013d5e  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+20h; "ft\\Windows\\CurrentVersion\\Explorer\\"...
0x180013d65  movups  [rsp+308h+var_288], xmm1
0x180013d6d  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+50h; "n\\Explorer\\AutoplayHandlers\\EventHan"...
0x180013d74  movups  [rsp+308h+var_298], xmm0
0x180013d79  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+40h; "ntVersion\\Explorer\\AutoplayHandlers\\"...
0x180013d80  movups  [rsp+308h+var_268], xmm1
0x180013d88  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+70h; "layHandlers\\EventHandlers\\"
0x180013d8f  movups  [rsp+308h+var_278], xmm0
0x180013d97  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+60h; "er\\AutoplayHandlers\\EventHandlers\\"
0x180013d9e  movups  [rsp+308h+var_248], xmm1
0x180013da6  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+90h; "tHandlers\\"
0x180013dad  movups  [rsp+308h+var_258], xmm0
0x180013db5  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+80h; "ers\\EventHandlers\\"
0x180013dbc  movups  [rsp+308h+var_228], xmm1
0x180013dc4  mov     qword ptr [rsp+308h+var_228+0Eh], rax
0x180013dcc  movups  [rsp+308h+var_238], xmm0
0x180013dd4  call    memset_0
0x180013dd9  mov     edx, [rbx+14h]; dwIndex
0x180013ddc  lea     r9, [rsp+308h+cchValueName]; lpcchValueName
0x180013de1  mov     rcx, [rbx+8]; hKey
0x180013de5  lea     r8, [rsp+308h+ValueName]; lpValueName
0x180013ded  mov     [rsp+308h+lpcbData], rbp; lpcbData
0x180013df2  mov     [rsp+308h+lpData], rbp; lpData
0x180013df7  lea     eax, [rdx+1]
0x180013dfa  mov     [rsp+308h+lpType], rbp; lpType
0x180013dff  mov     [rbx+14h], eax
0x180013e02  mov     [rsp+308h+cchValueName], 40h ; '@'
0x180013e0a  mov     [rsp+308h+ValueName], bp
0x180013e12  mov     [rsp+308h+lpReserved], rbp; cchToCopy
0x180013e17  call    cs:__imp_RegEnumValueW
0x180013e1d  mov     ecx, eax
0x180013e1f  test    eax, eax
0x180013e21  jnz     loc_180013EC5
0x180013e27  mov     edx, 104h; cchDest
0x180013e2c  lea     rax, [rsp+308h+SubKey]
0x180013e31  cmp     [rax], bp
0x180013e34  jz      short loc_180013E49
0x180013e36  add     rax, 2
0x180013e3a  sub     rdx, r14
0x180013e3d  jnz     short loc_180013E31
0x180013e3f  mov     eax, 80070057h
0x180013e44  jmp     loc_180013ED7
0x180013e49  lea     rax, [rdx+rdx]
0x180013e4d  lea     rcx, [rsp+308h+var_B0]
0x180013e55  sub     rcx, rax; pszDest
0x180013e58  lea     r9, [rsp+308h+ValueName]; pszSrc
0x180013e60  call    StringCopyWorkerW
0x180013e65  test    eax, eax
0x180013e67  js      short loc_180013ED7
0x180013e69  mov     rcx, [rbx]; HKEY
0x180013e6c  mov     [rbx+10h], ebp
0x180013e6f  test    rcx, rcx
0x180013e72  jz      short loc_180013E79
0x180013e74  call    ?_RegCloseKey@@YAJPEAUHKEY__@@@Z; _RegCloseKey(HKEY__ *)
0x180013e79  mov     r9d, r14d; samDesired
0x180013e7c  mov     [rbx], rbp
0x180013e7f  xor     r8d, r8d; ulOptions
0x180013e82  mov     [rsp+308h+lpReserved], rbx; phkResult
0x180013e87  lea     rdx, [rsp+308h+SubKey]; lpSubKey
0x180013e8c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013e93  call    cs:__imp_RegOpenKeyExW
0x180013e99  test    eax, eax
0x180013e9b  jle     short loc_180013EA7
0x180013e9d  movzx   eax, ax
0x180013ea0  or      eax, 80070000h
0x180013ea5  test    eax, eax
0x180013ea7  js      short loc_180013EE0
0x180013ea9  mov     edx, [rbx+10h]; unsigned int
0x180013eac  mov     r9d, 5Ah ; 'Z'; unsigned int
0x180013eb2  mov     rcx, [rbx]; HKEY
0x180013eb5  mov     r8, rsi; unsigned __int16 *
0x180013eb8  lea     eax, [rdx+1]
0x180013ebb  mov     [rbx+10h], eax
0x180013ebe  call    ?_RegEnumStringValue@@YAJPEAUHKEY__@@KPEAGK@Z; _RegEnumStringValue(HKEY__ *,ulong,ushort *,ulong)
0x180013ec3  jmp     short loc_180013ED7
0x180013ec5  cmp     ecx, 103h
0x180013ecb  mov     eax, 80004005h
0x180013ed0  mov     edi, r14d
0x180013ed3  cmovz   eax, r14d
0x180013ed7  cmp     eax, r14d
0x180013eda  jz      loc_180013D20
0x180013ee0  mov     r14, [rsp+308h+arg_10]
0x180013ee8  mov     rcx, [rsp+308h+var_28]
0x180013ef0  xor     rcx, rsp; StackCookie
0x180013ef3  call    __security_check_cookie
0x180013ef8  mov     rbx, [rsp+308h+arg_18]
0x180013f00  add     rsp, 2F0h
0x180013f07  pop     rdi
0x180013f08  pop     rsi
0x180013f09  pop     rbp
0x180013f0a  retn
```
