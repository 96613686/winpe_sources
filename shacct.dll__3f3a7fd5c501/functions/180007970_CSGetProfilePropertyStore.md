# CSGetProfilePropertyStore

- ea: `0x180007970`
- end: `0x180007bdf`
- name: `CSGetProfilePropertyStore`
- size: `623`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007bf0`
- `0x18000b8e0`
- `0x180014680`

## callees

- `0x180007970`
- `0x18000b960`
- `0x18000bcc0`
- `0x18000c240`
- `0x18000d740`
- `0x18001422c`
- `0x180017010`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180007b30`
- `SHCORE!SHStrDupW` at `0x180007b30`
- `SHCORE!__imp_GUIDFromStringW` at `0x180007b0f`
- `SHCORE!__imp_GUIDFromStringW` at `0x180007b0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007a7e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007ae5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007a7e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007ae5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007a26`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007a26`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800079f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800079f2`

## string_xrefs

- `0x180007a52`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall CSGetProfilePropertyStore(PSID pSourceSid, _QWORD *a2)
{
  CProfilePropStore *v4; // rax
  CProfilePropStore *v5; // rdi
  int Error; // ebx
  LSTATUS v7; // eax
  LSTATUS ValueW; // eax
  LSTATUS v9; // eax
  signed int v10; // ecx
  DWORD pcbData; // [rsp+40h] [rbp-478h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-470h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-468h] BYREF
  __int128 v15; // [rsp+58h] [rbp-460h] BYREF
  _WORD pvData[264]; // [rsp+70h] [rbp-448h] BYREF
  WCHAR psz[264]; // [rsp+280h] [rbp-238h] BYREF

  *a2 = 0;
  v4 = (CProfilePropStore *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
    return 2147942414LL;
  v5 = CProfilePropStore::CProfilePropStore(v4);
  if ( !v5 )
    return 2147942414LL;
  Error = -2147024809;
  if ( pSourceSid )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(pSourceSid, &StringSid) )
    {
      hkey = 0;
      v7 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
             0,
             0x20019u,
             &hkey);
      Error = v7;
      if ( v7 > 0 )
        Error = (unsigned __int16)v7 | 0x80070000;
      if ( Error >= 0 )
      {
        pcbData = 520;
        ValueW = RegGetValueW(hkey, StringSid, L"ProfileImagePath", 2u, 0, psz, &pcbData);
        Error = ValueW;
        if ( ValueW )
        {
          psz[0] = 0;
          if ( ValueW > 0 )
            Error = (unsigned __int16)ValueW | 0x80070000;
        }
        v15 = 0;
        if ( Error >= 0 )
        {
          pcbData = 520;
          v9 = RegGetValueW(hkey, StringSid, L"Guid", 2u, 0, pvData, &pcbData);
          v10 = v9;
          if ( v9 )
          {
            pvData[0] = 0;
            if ( v9 > 0 )
              v10 = (unsigned __int16)v9 | 0x80070000;
          }
          if ( v10 < 0
            || (unsigned int)GUIDFromStringW(pvData, &v15)
            || (Error = ResultFromKnownLastError(), Error >= 0) )
          {
            Error = SHStrDupW(psz, (LPWSTR *)v5 + 2);
            if ( Error >= 0 )
            {
              Error = DupSID(pSourceSid, (void **)v5 + 5);
              if ( Error >= 0 )
                *(_OWORD *)((char *)v5 + 24) = v15;
            }
          }
        }
        RegCloseKey(hkey);
      }
      LocalFree(StringSid);
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    if ( Error >= 0 )
      Error = (**(__int64 (__fastcall ***)(CProfilePropStore *, GUID *, _QWORD *))v5)(
                v5,
                &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                a2);
  }
  (*(void (__fastcall **)(CProfilePropStore *))(*(_QWORD *)v5 + 16LL))(v5);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180007970  push    rbp
0x180007972  push    rsi
0x180007973  push    r14
0x180007975  sub     rsp, 4A0h
0x18000797c  mov     rax, cs:__security_cookie
0x180007983  xor     rax, rsp
0x180007986  mov     [rsp+4B8h+var_28], rax
0x18000798e  mov     r14, rdx
0x180007991  mov     rsi, rcx
0x180007994  xor     ebp, ebp
0x180007996  mov     ecx, 30h ; '0'; unsigned __int64
0x18000799b  mov     [rdx], rbp
0x18000799e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800079a5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800079aa  test    rax, rax
0x1800079ad  jz      loc_180007BD8
0x1800079b3  mov     rcx, rax; this
0x1800079b6  mov     [rsp+4B8h+arg_18], rdi
0x1800079be  call    ??0CProfilePropStore@@QEAA@XZ; CProfilePropStore::CProfilePropStore(void)
0x1800079c3  mov     rdi, rax
0x1800079c6  test    rax, rax
0x1800079c9  jz      loc_180007BD1
0x1800079cf  mov     [rsp+4B8h+arg_10], rbx
0x1800079d7  mov     ebx, 80070057h
0x1800079dc  test    rsi, rsi
0x1800079df  jz      loc_180007B94
0x1800079e5  lea     rdx, [rsp+4B8h+StringSid]; StringSid
0x1800079ea  mov     [rsp+4B8h+StringSid], rbp
0x1800079ef  mov     rcx, rsi; Sid
0x1800079f2  call    cs:__imp_ConvertSidToStringSidW
0x1800079f8  test    eax, eax
0x1800079fa  jz      loc_180007B6F
0x180007a00  lea     rax, [rsp+4B8h+hkey]
0x180007a05  mov     [rsp+4B8h+hkey], rbp
0x180007a0a  mov     r9d, 20019h; samDesired
0x180007a10  mov     [rsp+4B8h+phkResult], rax; phkResult
0x180007a15  xor     r8d, r8d; ulOptions
0x180007a18  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x180007a1f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007a26  call    cs:__imp_RegOpenKeyExW
0x180007a2c  mov     ebx, eax
0x180007a2e  test    eax, eax
0x180007a30  jle     short loc_180007A3B
0x180007a32  movzx   ebx, ax
0x180007a35  or      ebx, 80070000h
0x180007a3b  test    ebx, ebx
0x180007a3d  js      loc_180007B62
0x180007a43  mov     rdx, [rsp+4B8h+StringSid]; lpSubKey
0x180007a48  lea     rax, [rsp+4B8h+var_478]
0x180007a4d  mov     rcx, [rsp+4B8h+hkey]; hkey
0x180007a52  lea     r8, aProfileimagepa; "ProfileImagePath"
0x180007a59  mov     [rsp+4B8h+pcbData], rax; pcbData
0x180007a5e  mov     r9d, 2; dwFlags
0x180007a64  lea     rax, [rsp+4B8h+psz]
0x180007a6c  mov     [rsp+4B8h+var_478], 208h
0x180007a74  mov     [rsp+4B8h+pvData], rax; pvData
0x180007a79  mov     [rsp+4B8h+phkResult], rbp; pdwType
0x180007a7e  call    cs:__imp_RegGetValueW
0x180007a84  mov     ebx, eax
0x180007a86  test    eax, eax
0x180007a88  jz      short loc_180007A9D
0x180007a8a  mov     [rsp+4B8h+psz], bp
0x180007a92  jle     short loc_180007A9D
0x180007a94  movzx   ebx, ax
0x180007a97  or      ebx, 80070000h
0x180007a9d  xorps   xmm0, xmm0
0x180007aa0  movups  [rsp+4B8h+var_460], xmm0
0x180007aa5  test    ebx, ebx
0x180007aa7  js      loc_180007B57
0x180007aad  mov     rdx, [rsp+4B8h+StringSid]; lpSubKey
0x180007ab2  lea     rax, [rsp+4B8h+var_478]
0x180007ab7  mov     rcx, [rsp+4B8h+hkey]; hkey
0x180007abc  lea     r8, aGuid; "Guid"
0x180007ac3  mov     [rsp+4B8h+pcbData], rax; pcbData
0x180007ac8  mov     r9d, 2; dwFlags
0x180007ace  lea     rax, [rsp+4B8h+var_448]
0x180007ad3  mov     [rsp+4B8h+var_478], 208h
0x180007adb  mov     [rsp+4B8h+pvData], rax; pvData
0x180007ae0  mov     [rsp+4B8h+phkResult], rbp; pdwType
0x180007ae5  call    cs:__imp_RegGetValueW
0x180007aeb  mov     ecx, eax
0x180007aed  test    eax, eax
0x180007aef  jz      short loc_180007B01
0x180007af1  mov     [rsp+4B8h+var_448], bp
0x180007af6  jle     short loc_180007B01
0x180007af8  movzx   ecx, ax
0x180007afb  or      ecx, 80070000h
0x180007b01  test    ecx, ecx
0x180007b03  js      short loc_180007B24
0x180007b05  lea     rdx, [rsp+4B8h+var_460]
0x180007b0a  lea     rcx, [rsp+4B8h+var_448]
0x180007b0f  call    cs:__imp_GUIDFromStringW
0x180007b15  test    eax, eax
0x180007b17  jnz     short loc_180007B24
0x180007b19  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180007b1e  mov     ebx, eax
0x180007b20  test    eax, eax
0x180007b22  js      short loc_180007B57
0x180007b24  lea     rdx, [rdi+10h]; ppwsz
0x180007b28  lea     rcx, [rsp+4B8h+psz]; psz
0x180007b30  call    cs:__imp_SHStrDupW
0x180007b36  mov     ebx, eax
0x180007b38  test    eax, eax
0x180007b3a  js      short loc_180007B57
0x180007b3c  lea     rdx, [rdi+28h]; void **
0x180007b40  mov     rcx, rsi; pSourceSid
0x180007b43  call    ?DupSID@@YAJPEAXPEAPEAX@Z; DupSID(void *,void * *)
0x180007b48  mov     ebx, eax
0x180007b4a  test    eax, eax
0x180007b4c  js      short loc_180007B57
0x180007b4e  movups  xmm0, [rsp+4B8h+var_460]
0x180007b53  movups  xmmword ptr [rdi+18h], xmm0
0x180007b57  mov     rcx, [rsp+4B8h+hkey]; hKey
0x180007b5c  call    cs:__imp_RegCloseKey
0x180007b62  mov     rcx, [rsp+4B8h+StringSid]; hMem
0x180007b67  call    cs:__imp_LocalFree
0x180007b6d  jmp     short loc_180007B76
0x180007b6f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180007b74  mov     ebx, eax
0x180007b76  test    ebx, ebx
0x180007b78  js      short loc_180007B94
0x180007b7a  mov     rax, [rdi]
0x180007b7d  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180007b84  mov     r8, r14
0x180007b87  mov     rcx, rdi
0x180007b8a  mov     rax, [rax]
0x180007b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b92  mov     ebx, eax
0x180007b94  mov     rax, [rdi]
0x180007b97  mov     rcx, rdi
0x180007b9a  mov     rax, [rax+10h]
0x180007b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ba3  mov     eax, ebx
0x180007ba5  mov     rbx, [rsp+4B8h+arg_10]
0x180007bad  mov     rdi, [rsp+4B8h+arg_18]
0x180007bb5  mov     rcx, [rsp+4B8h+var_28]
0x180007bbd  xor     rcx, rsp; StackCookie
0x180007bc0  call    __security_check_cookie
0x180007bc5  add     rsp, 4A0h
0x180007bcc  pop     r14
0x180007bce  pop     rsi
0x180007bcf  pop     rbp
0x180007bd0  retn
0x180007bd1  mov     eax, 8007000Eh
0x180007bd6  jmp     short loc_180007BAD
0x180007bd8  mov     eax, 8007000Eh
0x180007bdd  jmp     short loc_180007BB5
```
