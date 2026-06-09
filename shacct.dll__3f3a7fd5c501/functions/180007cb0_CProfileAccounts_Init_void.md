# CProfileAccounts::_Init(void)

- ea: `0x180007cb0`
- end: `0x180007e32`
- name: `?_Init@CProfileAccounts@@AEAAJXZ`
- size: `386`
- prototype: `__int64 __fastcall(CProfileAccounts *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007bf0`
- `0x18000b8e0`
- `0x1800144b0`
- `0x180014520`

## callees

- `0x180007cb0`
- `0x180008300`
- `0x18000bc90`
- `0x18000c240`
- `0x180017010`

## import_xrefs

- `SHCORE!SHEnumKeyExW` at `0x180007d69`
- `SHCORE!SHEnumKeyExW` at `0x180007d69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007dca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007dca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007df8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007df8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007d25`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007d25`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180007d91`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180007d91`

## pseudocode

```c
int __fastcall CProfileAccounts::_Init(CProfileAccounts *this)
{
  int result; // eax
  bool v3; // sf
  DWORD i; // edi
  LSTATUS v5; // eax
  signed int v6; // ebx
  DWORD pcchName; // [rsp+30h] [rbp-258h] BYREF
  PSID Sid; // [rsp+38h] [rbp-250h] BYREF
  HKEY hkey; // [rsp+40h] [rbp-248h] BYREF
  WCHAR pszName[264]; // [rsp+50h] [rbp-238h] BYREF

  result = 0;
  if ( !*((_DWORD *)this + 6) )
  {
    *((_DWORD *)this + 6) = 1;
    if ( (unsigned int)CDPA_Base<IPropertyStore,CTContainer_PolicyRelease<IPropertyStore>>::Create((char *)this + 16) )
    {
      hkey = 0;
      result = RegOpenKeyExW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
                 0,
                 0x20019u,
                 &hkey);
      v3 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v3 = result < 0;
      }
      if ( !v3 )
      {
        for ( i = 0; ; ++i )
        {
          while ( 1 )
          {
            pcchName = 260;
            v5 = SHEnumKeyExW(hkey, i, pszName, &pcchName);
            v6 = v5;
            if ( v5 > 0 )
              v6 = (unsigned __int16)v5 | 0x80070000;
            if ( v6 >= 0 )
            {
              Sid = 0;
              if ( ConvertStringSidToSidW(pszName, &Sid) )
                break;
            }
            ++i;
            if ( v6 < 0 )
              goto LABEL_16;
          }
          if ( DPA_InsertPtr(*((HDPA *)this + 2), 0x7FFFFFFF, Sid) == -1 )
            break;
        }
        v6 = -2147024882;
        LocalFree(Sid);
LABEL_16:
        if ( v6 == -2147024637 )
          v6 = 0;
        else
          (*(void (__fastcall **)(CProfileAccounts *))(*(_QWORD *)this + 48LL))(this);
        RegCloseKey(hkey);
        return v6;
      }
    }
    else
    {
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007cb0  mov     r11, rsp
0x180007cb3  push    rbp
0x180007cb4  push    r14
0x180007cb6  sub     rsp, 278h
0x180007cbd  mov     rax, cs:__security_cookie
0x180007cc4  xor     rax, rsp
0x180007cc7  mov     [rsp+288h+var_28], rax
0x180007ccf  xor     ebp, ebp
0x180007cd1  mov     r14, rcx
0x180007cd4  mov     eax, ebp
0x180007cd6  cmp     [rcx+18h], eax
0x180007cd9  jnz     loc_180007E17
0x180007cdf  mov     dword ptr [rcx+18h], 1
0x180007ce6  add     rcx, 10h
0x180007cea  mov     [r11+18h], rsi
0x180007cee  mov     [r11+10h], rbx
0x180007cf2  call    ?Create@?$CDPA_Base@UIPropertyStore@@V?$CTContainer_PolicyRelease@UIPropertyStore@@@@@@QEAAHH@Z; CDPA_Base<IPropertyStore,CTContainer_PolicyRelease<IPropertyStore>>::Create(int)
0x180007cf7  test    eax, eax
0x180007cf9  jz      loc_180007E02
0x180007cff  lea     rax, [rsp+288h+hkey]
0x180007d04  mov     [rsp+288h+hkey], rbp
0x180007d09  mov     r9d, 20019h; samDesired
0x180007d0f  mov     [rsp+288h+phkResult], rax; phkResult
0x180007d14  xor     r8d, r8d; ulOptions
0x180007d17  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x180007d1e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007d25  call    cs:__imp_RegOpenKeyExW
0x180007d2b  test    eax, eax
0x180007d2d  jle     short loc_180007D39
0x180007d2f  movzx   eax, ax
0x180007d32  or      eax, 80070000h
0x180007d37  test    eax, eax
0x180007d39  js      loc_180007E07
0x180007d3f  mov     [rsp+288h+var_18], rdi
0x180007d47  mov     edi, ebp
0x180007d49  nop     dword ptr [rax+00000000h]
0x180007d50  mov     rcx, [rsp+288h+hkey]; hkey
0x180007d55  lea     r9, [rsp+288h+pcchName]; pcchName
0x180007d5a  lea     r8, [rsp+288h+pszName]; pszName
0x180007d5f  mov     [rsp+288h+pcchName], 104h
0x180007d67  mov     edx, edi; dwIndex
0x180007d69  call    cs:__imp_SHEnumKeyExW
0x180007d6f  mov     ebx, eax
0x180007d71  test    eax, eax
0x180007d73  jle     short loc_180007D7E
0x180007d75  movzx   ebx, ax
0x180007d78  or      ebx, 80070000h
0x180007d7e  test    ebx, ebx
0x180007d80  js      short loc_180007DB8
0x180007d82  lea     rdx, [rsp+288h+Sid]; Sid
0x180007d87  mov     [rsp+288h+Sid], rbp
0x180007d8c  lea     rcx, [rsp+288h+pszName]; StringSid
0x180007d91  call    cs:__imp_ConvertStringSidToSidW
0x180007d97  test    eax, eax
0x180007d99  jz      short loc_180007DB8
0x180007d9b  mov     r8, [rsp+288h+Sid]; p
0x180007da0  mov     edx, 7FFFFFFFh; i
0x180007da5  mov     rcx, [r14+10h]; hdpa
0x180007da9  call    cs:__imp_DPA_InsertPtr
0x180007daf  cmp     eax, 0FFFFFFFFh
0x180007db2  jz      short loc_180007DC0
0x180007db4  inc     edi
0x180007db6  jmp     short loc_180007D50
0x180007db8  inc     edi
0x180007dba  test    ebx, ebx
0x180007dbc  jns     short loc_180007D50
0x180007dbe  jmp     short loc_180007DD0
0x180007dc0  mov     rcx, [rsp+288h+Sid]; hMem
0x180007dc5  mov     ebx, 8007000Eh
0x180007dca  call    cs:__imp_LocalFree
0x180007dd0  mov     rdi, [rsp+288h+var_18]
0x180007dd8  cmp     ebx, 80070103h
0x180007dde  jnz     short loc_180007DE4
0x180007de0  mov     ebx, ebp
0x180007de2  jmp     short loc_180007DF3
0x180007de4  mov     rax, [r14]
0x180007de7  mov     rcx, r14
0x180007dea  mov     rax, [rax+30h]
0x180007dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007df3  mov     rcx, [rsp+288h+hkey]; hKey
0x180007df8  call    cs:__imp_RegCloseKey
0x180007dfe  mov     eax, ebx
0x180007e00  jmp     short loc_180007E07
0x180007e02  mov     eax, 8007000Eh
0x180007e07  mov     rbx, [rsp+288h+arg_8]
0x180007e0f  mov     rsi, [rsp+288h+arg_10]
0x180007e17  mov     rcx, [rsp+288h+var_28]
0x180007e1f  xor     rcx, rsp; StackCookie
0x180007e22  call    __security_check_cookie
0x180007e27  add     rsp, 278h
0x180007e2e  pop     r14
0x180007e30  pop     rbp
0x180007e31  retn
```
