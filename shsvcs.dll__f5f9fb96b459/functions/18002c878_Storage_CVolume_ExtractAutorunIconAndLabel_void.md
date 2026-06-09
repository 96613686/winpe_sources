# Storage::CVolume::_ExtractAutorunIconAndLabel(void)

- ea: `0x18002c878`
- end: `0x18002cae7`
- name: `?_ExtractAutorunIconAndLabel@CVolume@Storage@@AEAAJXZ`
- size: `623`
- prototype: `__int64 __fastcall(Storage::CVolume *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002d4d8`

## callees

- `0x1800140f0`
- `0x180014c70`
- `0x180019574`
- `0x18002c878`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002ca1b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002ca37`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002ca1b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002ca37`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18002c94b`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18002c986`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18002c9c5`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18002c9ff`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18002ca80`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18002caae`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18002c94b`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18002c986`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18002c9c5`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18002c9ff`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18002ca80`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18002caae`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18002c90e`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18002c90e`

## pseudocode

```c
__int64 __fastcall Storage::CVolume::_ExtractAutorunIconAndLabel(Storage::CVolume *this)
{
  int v2; // edi
  const WCHAR *v3; // rsi
  unsigned int lpFileName; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v6; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR ReturnedString[4]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR FileName[312]; // [rsp+40h] [rbp-C0h] BYREF

  v6 = 0;
  *(_QWORD *)ReturnedString = 0;
  v2 = StringCchCopyExW(
         FileName,
         0x136u,
         (const unsigned __int16 *)this + 55,
         &v6,
         (unsigned __int64 *)ReturnedString,
         lpFileName);
  if ( v2 >= 0 )
  {
    v2 = StringCchCopyW(v6, *(unsigned __int64 *)ReturnedString, L"Autorun.inf");
    if ( v2 >= 0 )
    {
      WritePrivateProfileStringW(0, 0, 0, FileName);
      v3 = L"AutoRun.Amd64";
      if ( !GetPrivateProfileStringW(L"AutoRun.Amd64", L"Icon", &Default, (LPWSTR)this + 168, 0x110u, FileName) )
      {
        v3 = L"AutoRun";
        Storage::CVolume::_HandleAccessDenied(this);
        if ( !GetPrivateProfileStringW(L"AutoRun", L"Icon", &Default, (LPWSTR)this + 168, 0x110u, FileName) )
        {
          *((_WORD *)this + 168) = 0;
          Storage::CVolume::_HandleAccessDenied(this);
        }
      }
      if ( !GetPrivateProfileStringW(v3, L"Label", &Default, (LPWSTR)this + 440, 0x21u, FileName) )
      {
        *((_WORD *)this + 440) = 0;
        Storage::CVolume::_HandleAccessDenied(this);
      }
      if ( GetPrivateProfileStringW(v3, L"UseAutoPlay", &Default, ReturnedString, 4u, FileName) )
      {
        if ( lstrcmpiW(ReturnedString, L"1") )
        {
          if ( !lstrcmpiW(ReturnedString, L"0") )
            *((_DWORD *)this + 11) |= 0x8000u;
        }
        else
        {
          *((_DWORD *)this + 11) |= 0x100u;
        }
      }
      else
      {
        Storage::CVolume::_HandleAccessDenied(this);
      }
      if ( (*((_BYTE *)this + 52) & 0x10) != 0 )
      {
        if ( GetPrivateProfileStringW(v3, L"Open", &Default, ReturnedString, 4u, FileName)
          || GetPrivateProfileStringW(v3, L"ShellExecute", &Default, ReturnedString, 4u, FileName) )
        {
          *((_DWORD *)this + 11) |= 2u;
        }
        else
        {
          Storage::CVolume::_HandleAccessDenied(this);
        }
      }
      else
      {
        *((_DWORD *)this + 11) |= 0x100u;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002c878  push    rbp
0x18002c87a  push    rbx
0x18002c87b  push    rsi
0x18002c87c  push    rdi
0x18002c87d  push    r14
0x18002c87f  push    r15
0x18002c881  lea     rbp, [rsp-1C8h]
0x18002c889  sub     rsp, 2C8h
0x18002c890  mov     rax, cs:__security_cookie
0x18002c897  xor     rax, rsp
0x18002c89a  mov     [rbp+1F0h+var_40], rax
0x18002c8a1  mov     rbx, rcx
0x18002c8a4  mov     [rsp+2F0h+var_2C0], 0
0x18002c8ad  lea     r8, [rcx+6Eh]; unsigned __int16 *
0x18002c8b1  mov     qword ptr [rsp+2F0h+ReturnedString], 0
0x18002c8ba  lea     rax, [rsp+2F0h+ReturnedString]
0x18002c8bf  mov     edx, 136h; unsigned __int64
0x18002c8c4  lea     rcx, [rsp+2F0h+FileName]; unsigned __int16 *
0x18002c8c9  mov     qword ptr [rsp+2F0h+nSize], rax; unsigned __int64 *
0x18002c8ce  lea     r9, [rsp+2F0h+var_2C0]; unsigned __int16 **
0x18002c8d3  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18002c8d8  mov     edi, eax
0x18002c8da  test    eax, eax
0x18002c8dc  js      loc_18002CAC6
0x18002c8e2  mov     rdx, qword ptr [rsp+2F0h+ReturnedString]; unsigned __int64
0x18002c8e7  lea     r8, aAutorunInf; "Autorun.inf"
0x18002c8ee  mov     rcx, [rsp+2F0h+var_2C0]; unsigned __int16 *
0x18002c8f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c8f8  mov     edi, eax
0x18002c8fa  test    eax, eax
0x18002c8fc  js      loc_18002CAC6
0x18002c902  lea     r9, [rsp+2F0h+FileName]; lpFileName
0x18002c907  xor     r8d, r8d; lpString
0x18002c90a  xor     edx, edx; lpKeyName
0x18002c90c  xor     ecx, ecx; lpAppName
0x18002c90e  call    cs:__imp_WritePrivateProfileStringW
0x18002c914  lea     rax, [rsp+2F0h+FileName]
0x18002c919  mov     [rsp+2F0h+lpFileName], rax; lpFileName
0x18002c91e  lea     r14, [rbx+150h]
0x18002c925  lea     r15, Default
0x18002c92c  mov     [rsp+2F0h+nSize], 110h; nSize
0x18002c934  lea     rsi, AppName; "AutoRun.Amd64"
0x18002c93b  mov     r9, r14; lpReturnedString
0x18002c93e  mov     r8, r15; lpDefault
0x18002c941  lea     rdx, KeyName; "Icon"
0x18002c948  mov     rcx, rsi; lpAppName
0x18002c94b  call    cs:__imp_GetPrivateProfileStringW
0x18002c951  test    eax, eax
0x18002c953  jnz     short loc_18002C99C
0x18002c955  mov     rcx, rbx; this
0x18002c958  lea     rsi, aAutorun; "AutoRun"
0x18002c95f  call    ?_HandleAccessDenied@CVolume@Storage@@AEAAXXZ; Storage::CVolume::_HandleAccessDenied(void)
0x18002c964  lea     rax, [rsp+2F0h+FileName]
0x18002c969  mov     r9, r14; lpReturnedString
0x18002c96c  mov     [rsp+2F0h+lpFileName], rax; lpFileName
0x18002c971  lea     rdx, KeyName; "Icon"
0x18002c978  mov     r8, r15; lpDefault
0x18002c97b  mov     [rsp+2F0h+nSize], 110h; nSize
0x18002c983  mov     rcx, rsi; lpAppName
0x18002c986  call    cs:__imp_GetPrivateProfileStringW
0x18002c98c  test    eax, eax
0x18002c98e  jnz     short loc_18002C99C
0x18002c990  mov     rcx, rbx; this
0x18002c993  mov     [r14], ax
0x18002c997  call    ?_HandleAccessDenied@CVolume@Storage@@AEAAXXZ; Storage::CVolume::_HandleAccessDenied(void)
0x18002c99c  lea     rax, [rsp+2F0h+FileName]
0x18002c9a1  mov     r8, r15; lpDefault
0x18002c9a4  mov     [rsp+2F0h+lpFileName], rax; lpFileName
0x18002c9a9  lea     r14, [rbx+370h]
0x18002c9b0  mov     r9, r14; lpReturnedString
0x18002c9b3  mov     [rsp+2F0h+nSize], 21h ; '!'; nSize
0x18002c9bb  lea     rdx, aLabel; "Label"
0x18002c9c2  mov     rcx, rsi; lpAppName
0x18002c9c5  call    cs:__imp_GetPrivateProfileStringW
0x18002c9cb  test    eax, eax
0x18002c9cd  jnz     short loc_18002C9DB
0x18002c9cf  mov     rcx, rbx; this
0x18002c9d2  mov     [r14], ax
0x18002c9d6  call    ?_HandleAccessDenied@CVolume@Storage@@AEAAXXZ; Storage::CVolume::_HandleAccessDenied(void)
0x18002c9db  lea     rax, [rsp+2F0h+FileName]
0x18002c9e0  mov     r8, r15; lpDefault
0x18002c9e3  mov     [rsp+2F0h+lpFileName], rax; lpFileName
0x18002c9e8  lea     r9, [rsp+2F0h+ReturnedString]; lpReturnedString
0x18002c9ed  lea     rdx, aUseautoplay; "UseAutoPlay"
0x18002c9f4  mov     [rsp+2F0h+nSize], 4; nSize
0x18002c9fc  mov     rcx, rsi; lpAppName
0x18002c9ff  call    cs:__imp_GetPrivateProfileStringW
0x18002ca05  mov     r14d, 100h
0x18002ca0b  test    eax, eax
0x18002ca0d  jz      short loc_18002CA48
0x18002ca0f  lea     rdx, a1; "1"
0x18002ca16  lea     rcx, [rsp+2F0h+ReturnedString]; lpString1
0x18002ca1b  call    cs:__imp_lstrcmpiW
0x18002ca21  test    eax, eax
0x18002ca23  jnz     short loc_18002CA2B
0x18002ca25  or      [rbx+2Ch], r14d
0x18002ca29  jmp     short loc_18002CA50
0x18002ca2b  lea     rdx, a0; "0"
0x18002ca32  lea     rcx, [rsp+2F0h+ReturnedString]; lpString1
0x18002ca37  call    cs:__imp_lstrcmpiW
0x18002ca3d  test    eax, eax
0x18002ca3f  jnz     short loc_18002CA50
0x18002ca41  bts     dword ptr [rbx+2Ch], 0Fh
0x18002ca46  jmp     short loc_18002CA50
0x18002ca48  mov     rcx, rbx; this
0x18002ca4b  call    ?_HandleAccessDenied@CVolume@Storage@@AEAAXXZ; Storage::CVolume::_HandleAccessDenied(void)
0x18002ca50  test    byte ptr [rbx+34h], 10h
0x18002ca54  jnz     short loc_18002CA5C
0x18002ca56  or      [rbx+2Ch], r14d
0x18002ca5a  jmp     short loc_18002CAC6
0x18002ca5c  lea     rax, [rsp+2F0h+FileName]
0x18002ca61  mov     r8, r15; lpDefault
0x18002ca64  mov     [rsp+2F0h+lpFileName], rax; lpFileName
0x18002ca69  lea     r9, [rsp+2F0h+ReturnedString]; lpReturnedString
0x18002ca6e  lea     rdx, aOpen; "Open"
0x18002ca75  mov     [rsp+2F0h+nSize], 4; nSize
0x18002ca7d  mov     rcx, rsi; lpAppName
0x18002ca80  call    cs:__imp_GetPrivateProfileStringW
0x18002ca86  test    eax, eax
0x18002ca88  jnz     short loc_18002CAC2
0x18002ca8a  lea     rax, [rsp+2F0h+FileName]
0x18002ca8f  mov     r8, r15; lpDefault
0x18002ca92  mov     [rsp+2F0h+lpFileName], rax; lpFileName
0x18002ca97  lea     r9, [rsp+2F0h+ReturnedString]; lpReturnedString
0x18002ca9c  lea     rdx, aShellexecute; "ShellExecute"
0x18002caa3  mov     [rsp+2F0h+nSize], 4; nSize
0x18002caab  mov     rcx, rsi; lpAppName
0x18002caae  call    cs:__imp_GetPrivateProfileStringW
0x18002cab4  test    eax, eax
0x18002cab6  jnz     short loc_18002CAC2
0x18002cab8  mov     rcx, rbx; this
0x18002cabb  call    ?_HandleAccessDenied@CVolume@Storage@@AEAAXXZ; Storage::CVolume::_HandleAccessDenied(void)
0x18002cac0  jmp     short loc_18002CAC6
0x18002cac2  or      dword ptr [rbx+2Ch], 2
0x18002cac6  mov     eax, edi
0x18002cac8  mov     rcx, [rbp+1F0h+var_40]
0x18002cacf  xor     rcx, rsp; StackCookie
0x18002cad2  call    __security_check_cookie
0x18002cad7  add     rsp, 2C8h
0x18002cade  pop     r15
0x18002cae0  pop     r14
0x18002cae2  pop     rdi
0x18002cae3  pop     rsi
0x18002cae4  pop     rbx
0x18002cae5  pop     rbp
0x18002cae6  retn
```
