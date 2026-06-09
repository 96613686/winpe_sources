# UninstallSdbEntry(ushort const *,ushort const *,int)

- ea: `0x1400075a8`
- end: `0x140007926`
- name: `?UninstallSdbEntry@@YAHPEBG0H@Z`
- size: `894`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140004df8`
- `0x140006480`

## callees

- `0x140006238`
- `0x140006f60`
- `0x140007098`
- `0x1400075a8`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x1400076df`
- `ADVAPI32!RegDeleteValueW` at `0x140007768`
- `ADVAPI32!RegDeleteValueW` at `0x1400076df`
- `ADVAPI32!RegDeleteValueW` at `0x140007768`
- `ADVAPI32!RegOpenKeyExW` at `0x1400076b9`
- `ADVAPI32!RegOpenKeyExW` at `0x14000786d`
- `ADVAPI32!RegOpenKeyExW` at `0x1400078aa`
- `ADVAPI32!RegOpenKeyExW` at `0x1400076b9`
- `ADVAPI32!RegOpenKeyExW` at `0x14000786d`
- `ADVAPI32!RegOpenKeyExW` at `0x1400078aa`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400077c1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400077c1`
- `ADVAPI32!RegCloseKey` at `0x1400077e1`
- `ADVAPI32!RegCloseKey` at `0x140007801`
- `ADVAPI32!RegCloseKey` at `0x1400078c6`
- `ADVAPI32!RegCloseKey` at `0x1400078f3`
- `ADVAPI32!RegCloseKey` at `0x1400077e1`
- `ADVAPI32!RegCloseKey` at `0x140007801`
- `ADVAPI32!RegCloseKey` at `0x1400078c6`
- `ADVAPI32!RegCloseKey` at `0x1400078f3`
- `ntdll!NtDeleteKey` at `0x1400078b9`
- `ntdll!NtDeleteKey` at `0x1400078b9`

## string_xrefs

- `0x140007678`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Custom`
- `0x14000781d`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Custom`

## pseudocode

```c
__int64 __fastcall UninstallSdbEntry(LPCWSTR lpSubKey, const unsigned __int16 *a2, __int64 a3)
{
  WCHAR *v3; // rax
  __int64 v4; // rdi
  const unsigned __int16 *v5; // r9
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  int v10; // r14d
  WCHAR *v11; // rcx
  const unsigned __int16 *v12; // r8
  LSTATUS v13; // eax
  __int64 v14; // rdx
  LSTATUS v15; // eax
  WCHAR *v16; // rcx
  WCHAR *v17; // rax
  WCHAR *v18; // rcx
  const unsigned __int16 *v19; // r8
  NTSTATUS v20; // ebx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[520]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR v27[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v3 = ValueName;
  v4 = 2147483646;
  hKey = 0;
  cValues = 0;
  v5 = a2;
  v7 = 0;
  v8 = 2147483646;
  v9 = 260;
  v10 = a3;
  do
  {
    if ( !v8 )
      break;
    a3 = *v5;
    if ( !(_WORD)a3 )
      break;
    *v3 = a3;
    ++v5;
    ++v3;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v3 - 1;
  if ( v9 )
    v11 = v3;
  *v11 = 0;
  if ( v9 && (int)StringCchCatW(ValueName, 260, L".sdb") >= 0 )
  {
    v12 = L"%s\\Layers\\%s";
    if ( !v10 )
      v12 = L"%s\\%s";
    if ( (int)StringCchPrintfW(
                SubKey,
                0x208u,
                v12,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Custom",
                lpSubKey) >= 0 )
    {
      v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x103u, &hKey);
      if ( v13 )
      {
        if ( v13 == 5 )
        {
LABEL_16:
          PrintMessage(0x3F5u, v14, a3, v5);
          goto LABEL_43;
        }
        goto LABEL_42;
      }
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( !v15 )
      {
LABEL_30:
        if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0) )
        {
          PrintMessage(0x41Au, SubKey);
          RegCloseKey(hKey);
          hKey = 0;
        }
        else if ( !cValues )
        {
          RegCloseKey(hKey);
          hKey = 0;
          v19 = L"%s\\Layers";
          if ( !v10 )
            v19 = L"%s";
          if ( (int)StringCchPrintfW(
                      SubKey,
                      0x208u,
                      v19,
                      L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Custom") >= 0 )
          {
            if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x102u, &hKey) )
            {
              PrintMessage(0x3F6u, SubKey);
            }
            else
            {
              phkResult = 0;
              if ( RegOpenKeyExW(hKey, lpSubKey, 0, 0x10100u, &phkResult)
                || (v20 = NtDeleteKey(phkResult), RegCloseKey(phkResult), v20) )
              {
                PrintMessage(0x3F7u, lpSubKey, SubKey);
              }
            }
          }
          else
          {
            PrintMessage(0x409u);
          }
        }
LABEL_42:
        v7 = 1;
        goto LABEL_43;
      }
      if ( v15 == 5 )
        goto LABEL_16;
      if ( v15 != 2 )
      {
LABEL_29:
        PrintMessage(0x3F8u, ValueName, SubKey);
        goto LABEL_30;
      }
      v16 = ValueName;
      v9 = 260;
      v17 = v27;
      do
      {
        if ( !v4 )
          break;
        a3 = *v16;
        if ( !(_WORD)a3 )
          break;
        *v17 = a3;
        ++v16;
        ++v17;
        --v4;
        --v9;
      }
      while ( v9 );
      v18 = v17 - 1;
      if ( v9 )
        v18 = v17;
      *v18 = 0;
      if ( v9 && (int)StringCchCatW(v27, 260, L".sdb") >= 0 )
      {
        if ( !RegDeleteValueW(hKey, v27) )
          goto LABEL_30;
        goto LABEL_29;
      }
    }
  }
  PrintMessage(0x409u, v9, a3, v5);
LABEL_43:
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x1400075a8  mov     [rsp-8+arg_10], rbx
0x1400075ad  mov     [rsp-8+arg_18], rsi
0x1400075b2  push    rbp
0x1400075b3  push    rdi
0x1400075b4  push    r12
0x1400075b6  push    r14
0x1400075b8  push    r15
0x1400075ba  lea     rbp, [rsp-7C0h]
0x1400075c2  sub     rsp, 8C0h
0x1400075c9  mov     rax, cs:__security_cookie
0x1400075d0  xor     rax, rsp
0x1400075d3  mov     [rbp+7E0h+var_30], rax
0x1400075da  xor     r15d, r15d
0x1400075dd  lea     rax, [rbp+7E0h+ValueName]
0x1400075e1  mov     edi, 7FFFFFFEh
0x1400075e6  mov     [rsp+8E0h+hKey], r15
0x1400075eb  mov     r12d, 104h
0x1400075f1  mov     [rsp+8E0h+cValues], r15d
0x1400075f6  mov     r9, rdx
0x1400075f9  mov     rsi, rcx
0x1400075fc  mov     ebx, r15d
0x1400075ff  mov     ecx, edi
0x140007601  mov     edx, r12d
0x140007604  mov     r14d, r8d
0x140007607  test    rcx, rcx
0x14000760a  jz      short loc_14000762B
0x14000760c  movzx   r8d, word ptr [r9]
0x140007610  test    r8w, r8w
0x140007614  jz      short loc_14000762B
0x140007616  mov     [rax], r8w
0x14000761a  add     r9, 2
0x14000761e  add     rax, 2
0x140007622  dec     rcx
0x140007625  sub     rdx, 1
0x140007629  jnz     short loc_140007607
0x14000762b  test    rdx, rdx
0x14000762e  lea     rcx, [rax-2]
0x140007632  cmovnz  rcx, rax
0x140007636  mov     [rcx], r15w
0x14000763a  jnz     short loc_14000764B
0x14000763c  mov     ecx, 409h; unsigned int
0x140007641  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140007646  jmp     loc_1400078E9
0x14000764b  lea     r8, aSdb; ".sdb"
0x140007652  mov     rdx, r12; unsigned __int64
0x140007655  lea     rcx, [rbp+7E0h+ValueName]; unsigned __int16 *
0x140007659  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000765e  test    eax, eax
0x140007660  js      short loc_14000763C
0x140007662  lea     rax, aSS_0; "%s\\%s"
0x140007669  mov     [rsp+8E0h+phkResult], rsi
0x14000766e  test    r14d, r14d
0x140007671  lea     r8, aSLayersS; "%s\\Layers\\%s"
0x140007678  lea     r9, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x14000767f  mov     edx, 208h; unsigned __int64
0x140007684  cmovz   r8, rax; unsigned __int16 *
0x140007688  lea     rcx, [rbp+7E0h+SubKey]; unsigned __int16 *
0x14000768f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007694  test    eax, eax
0x140007696  js      short loc_14000763C
0x140007698  lea     rax, [rsp+8E0h+hKey]
0x14000769d  mov     r9d, 103h; samDesired
0x1400076a3  xor     r8d, r8d; ulOptions
0x1400076a6  mov     [rsp+8E0h+phkResult], rax; phkResult
0x1400076ab  lea     rdx, [rbp+7E0h+SubKey]; lpSubKey
0x1400076b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400076b9  call    cs:__imp_RegOpenKeyExW
0x1400076bf  test    eax, eax
0x1400076c1  jz      short loc_1400076D6
0x1400076c3  cmp     eax, 5
0x1400076c6  jnz     loc_1400078E4
0x1400076cc  mov     ecx, 3F5h
0x1400076d1  jmp     loc_140007641
0x1400076d6  mov     rcx, [rsp+8E0h+hKey]; hKey
0x1400076db  lea     rdx, [rbp+7E0h+ValueName]; lpValueName
0x1400076df  call    cs:__imp_RegDeleteValueW
0x1400076e5  test    eax, eax
0x1400076e7  jz      loc_140007787
0x1400076ed  cmp     eax, 5
0x1400076f0  jz      short loc_1400076CC
0x1400076f2  cmp     eax, 2
0x1400076f5  jnz     short loc_140007772
0x1400076f7  lea     rcx, [rbp+7E0h+ValueName]
0x1400076fb  mov     rdx, r12
0x1400076fe  lea     rax, [rbp+7E0h+var_240]
0x140007705  test    rdi, rdi
0x140007708  jz      short loc_140007729
0x14000770a  movzx   r8d, word ptr [rcx]
0x14000770e  test    r8w, r8w
0x140007712  jz      short loc_140007729
0x140007714  mov     [rax], r8w
0x140007718  add     rcx, 2
0x14000771c  add     rax, 2
0x140007720  dec     rdi
0x140007723  sub     rdx, 1
0x140007727  jnz     short loc_140007705
0x140007729  test    rdx, rdx
0x14000772c  lea     rcx, [rax-2]
0x140007730  cmovnz  rcx, rax
0x140007734  mov     [rcx], r15w
0x140007738  jz      loc_14000763C
0x14000773e  lea     r8, aSdb; ".sdb"
0x140007745  mov     rdx, r12; unsigned __int64
0x140007748  lea     rcx, [rbp+7E0h+var_240]; unsigned __int16 *
0x14000774f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007754  test    eax, eax
0x140007756  js      loc_14000763C
0x14000775c  mov     rcx, [rsp+8E0h+hKey]; hKey
0x140007761  lea     rdx, [rbp+7E0h+var_240]; lpValueName
0x140007768  call    cs:__imp_RegDeleteValueW
0x14000776e  test    eax, eax
0x140007770  jz      short loc_140007787
0x140007772  lea     r8, [rbp+7E0h+SubKey]
0x140007779  mov     ecx, 3F8h; unsigned int
0x14000777e  lea     rdx, [rbp+7E0h+ValueName]
0x140007782  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140007787  mov     rcx, [rsp+8E0h+hKey]; hKey
0x14000778c  lea     rax, [rsp+8E0h+cValues]
0x140007791  mov     [rsp+8E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x140007796  xor     r9d, r9d; lpReserved
0x140007799  mov     [rsp+8E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x14000779e  xor     r8d, r8d; lpcchClass
0x1400077a1  mov     [rsp+8E0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1400077a6  xor     edx, edx; lpClass
0x1400077a8  mov     [rsp+8E0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1400077ad  mov     [rsp+8E0h+lpcValues], rax; lpcValues
0x1400077b2  mov     [rsp+8E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1400077b7  mov     [rsp+8E0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1400077bc  mov     [rsp+8E0h+phkResult], r15; lpcSubKeys
0x1400077c1  call    cs:__imp_RegQueryInfoKeyW
0x1400077c7  test    eax, eax
0x1400077c9  jz      short loc_1400077F1
0x1400077cb  lea     rdx, [rbp+7E0h+SubKey]
0x1400077d2  mov     ecx, 41Ah; unsigned int
0x1400077d7  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400077dc  mov     rcx, [rsp+8E0h+hKey]; hKey
0x1400077e1  call    cs:__imp_RegCloseKey
0x1400077e7  mov     [rsp+8E0h+hKey], r15
0x1400077ec  jmp     loc_1400078E4
0x1400077f1  cmp     [rsp+8E0h+cValues], r15d
0x1400077f6  jnz     loc_1400078E4
0x1400077fc  mov     rcx, [rsp+8E0h+hKey]; hKey
0x140007801  call    cs:__imp_RegCloseKey
0x140007807  lea     rax, aS; "%s"
0x14000780e  mov     [rsp+8E0h+hKey], r15
0x140007813  test    r14d, r14d
0x140007816  lea     r8, aSLayers; "%s\\Layers"
0x14000781d  lea     r9, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x140007824  mov     edx, 208h; unsigned __int64
0x140007829  cmovz   r8, rax; unsigned __int16 *
0x14000782d  lea     rcx, [rbp+7E0h+SubKey]; unsigned __int16 *
0x140007834  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007839  test    eax, eax
0x14000783b  jns     short loc_14000784C
0x14000783d  mov     ecx, 409h; unsigned int
0x140007842  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140007847  jmp     loc_1400078E4
0x14000784c  lea     rax, [rsp+8E0h+hKey]
0x140007851  mov     r9d, 102h; samDesired
0x140007857  xor     r8d, r8d; ulOptions
0x14000785a  mov     [rsp+8E0h+phkResult], rax; phkResult
0x14000785f  lea     rdx, [rbp+7E0h+SubKey]; lpSubKey
0x140007866  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000786d  call    cs:__imp_RegOpenKeyExW
0x140007873  test    eax, eax
0x140007875  jz      short loc_14000788A
0x140007877  lea     rdx, [rbp+7E0h+SubKey]
0x14000787e  mov     ecx, 3F6h; unsigned int
0x140007883  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140007888  jmp     short loc_1400078E4
0x14000788a  mov     rcx, [rsp+8E0h+hKey]; hKey
0x14000788f  lea     rax, [rsp+8E0h+var_870]
0x140007894  mov     r9d, 10100h; samDesired
0x14000789a  mov     [rsp+8E0h+phkResult], rax; phkResult
0x14000789f  xor     r8d, r8d; ulOptions
0x1400078a2  mov     [rsp+8E0h+var_870], r15
0x1400078a7  mov     rdx, rsi; lpSubKey
0x1400078aa  call    cs:__imp_RegOpenKeyExW
0x1400078b0  test    eax, eax
0x1400078b2  jnz     short loc_1400078D0
0x1400078b4  mov     rcx, [rsp+8E0h+var_870]; KeyHandle
0x1400078b9  call    cs:__imp_NtDeleteKey
0x1400078bf  mov     rcx, [rsp+8E0h+var_870]; hKey
0x1400078c4  mov     ebx, eax
0x1400078c6  call    cs:__imp_RegCloseKey
0x1400078cc  test    ebx, ebx
0x1400078ce  jz      short loc_1400078E4
0x1400078d0  lea     r8, [rbp+7E0h+SubKey]
0x1400078d7  mov     rdx, rsi
0x1400078da  mov     ecx, 3F7h; unsigned int
0x1400078df  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400078e4  mov     ebx, 1
0x1400078e9  mov     rcx, [rsp+8E0h+hKey]; hKey
0x1400078ee  test    rcx, rcx
0x1400078f1  jz      short loc_1400078F9
0x1400078f3  call    cs:__imp_RegCloseKey
0x1400078f9  mov     eax, ebx
0x1400078fb  mov     rcx, [rbp+7E0h+var_30]
0x140007902  xor     rcx, rsp; StackCookie
0x140007905  call    __security_check_cookie
0x14000790a  lea     r11, [rsp+8E0h+var_20]
0x140007912  mov     rbx, [r11+40h]
0x140007916  mov     rsi, [r11+48h]
0x14000791a  mov     rsp, r11
0x14000791d  pop     r15
0x14000791f  pop     r14
0x140007921  pop     r12
0x140007923  pop     rdi
0x140007924  pop     rbp
0x140007925  retn
```
