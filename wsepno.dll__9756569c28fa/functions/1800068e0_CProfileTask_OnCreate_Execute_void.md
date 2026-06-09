# CProfileTask_OnCreate::Execute(void)

- ea: `0x1800068e0`
- end: `0x180006b44`
- name: `?Execute@CProfileTask_OnCreate@@UEAAJXZ`
- size: `612`
- prototype: `__int64 __fastcall(CProfileTask_OnCreate *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001770`
- `0x180001794`
- `0x180001b9c`
- `0x180003714`
- `0x1800068e0`
- `0x18000c9d8`
- `0x18000cd50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a0e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006a04`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006a04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006ad3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006ad3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006af1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006afc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006af1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006afc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b07`

## string_xrefs

- `0x180006a47`: `SOFTWARE\Microsoft\Windows Search\UninstalledStoreApps`

## pseudocode

```c
__int64 __fastcall CProfileTask_OnCreate::Execute(CProfileTask_OnCreate *this)
{
  wchar_t *v2; // rdx
  const wchar_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rax
  wchar_t *v9; // rax
  WCHAR *v10; // rsi
  signed int v11; // ebx
  HKEY v12; // rcx
  unsigned int v13; // r8d
  signed int LastError; // eax
  int v15; // eax
  const wchar_t *v16; // rcx
  const wchar_t *v17; // rbx
  HKEY v18; // rdi
  bool v19; // al
  wchar_t *v20; // rdx
  LSTATUS v21; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v26; // [rsp+78h] [rbp-88h]
  wchar_t v27[136]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t v28[264]; // [rsp+190h] [rbp+90h] BYREF

  v2 = v27;
  v3 = L"D:(A;;GRGXDC;;;SY)(A;;GRGX;;;BA)(A;;GRGX;;;BU)(A;;LC;;;%s)(A;;GA;;;S-1-5-80-117416528-2204451360-1913602512-13550"
        "18040-1234992034)";
  v4 = 2;
  do
  {
    *(_OWORD *)v2 = *(_OWORD *)v3;
    *((_OWORD *)v2 + 1) = *((_OWORD *)v3 + 1);
    *((_OWORD *)v2 + 2) = *((_OWORD *)v3 + 2);
    *((_OWORD *)v2 + 3) = *((_OWORD *)v3 + 3);
    *((_OWORD *)v2 + 4) = *((_OWORD *)v3 + 4);
    *((_OWORD *)v2 + 5) = *((_OWORD *)v3 + 5);
    *((_OWORD *)v2 + 6) = *((_OWORD *)v3 + 6);
    *((_OWORD *)v2 + 7) = *((_OWORD *)v3 + 7);
    v2 += 64;
    v3 += 64;
    --v4;
  }
  while ( v4 );
  *(_QWORD *)(v2 - 1) = *(_QWORD *)(v3 - 1);
  v5 = *((_QWORD *)this + 1);
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(v5 + 2 * v6) );
  v7 = v6 + 131;
  v8 = 2 * (v6 + 131);
  if ( !is_mul_ok(v6 + 131, 2u) )
    v8 = -1;
  v9 = (wchar_t *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  v26 = v9;
  if ( v9 )
  {
    v11 = StringCchPrintfW(v9, v7, v27, *((_QWORD *)this + 1));
    if ( v11 >= 0 )
    {
      memset(&SecurityDescriptor, 0, sizeof(SecurityDescriptor));
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v10, 1u, &SecurityDescriptor.lpSecurityDescriptor, 0) )
      {
        hKey = 0;
        v15 = WSearchRegOpenKey(v12, L"SOFTWARE\\Microsoft\\Windows Search\\UninstalledStoreApps", v13, 4u, &hKey);
        v11 = v15;
        if ( v15 > 0 )
          v11 = (unsigned __int16)v15 | 0x80070000;
        if ( v11 >= 0 )
        {
          phkResult = 0;
          SecurityDescriptor.nLength = 24;
          SecurityDescriptor.bInheritHandle = 0;
          v17 = (const wchar_t *)*((_QWORD *)this + 1);
          v18 = hKey;
          v19 = MapRegistryKeyPath(v16, hKey, v17, v28);
          v20 = v28;
          if ( !v19 )
            v20 = (wchar_t *)v17;
          v21 = RegCreateKeyExW(v18, v20, 0, 0, 0, 0x20019u, &SecurityDescriptor, &phkResult, 0);
          v11 = v21;
          if ( v21 > 0 )
            v11 = (unsigned __int16)v21 | 0x80070000;
          if ( v11 >= 0 )
            RegCloseKey(phkResult);
          RegCloseKey(hKey);
        }
        LocalFree(SecurityDescriptor.lpSecurityDescriptor);
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        if ( v11 >= 0 )
          v11 = -2147467259;
      }
    }
  }
  else
  {
    v11 = -2147024882;
  }
  if ( v10 )
    operator delete(v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800068e0  mov     [rsp-8+arg_8], rbx
0x1800068e5  mov     [rsp-8+arg_10], rsi
0x1800068ea  push    rbp
0x1800068eb  push    rdi
0x1800068ec  push    r15
0x1800068ee  lea     rbp, [rsp-2B0h]
0x1800068f6  sub     rsp, 3B0h
0x1800068fd  mov     rax, cs:__security_cookie
0x180006904  xor     rax, rsp
0x180006907  mov     [rbp+2C0h+var_20], rax
0x18000690e  mov     rdi, rcx
0x180006911  lea     rdx, [rbp+2C0h+var_340]
0x180006915  lea     rax, aDAGrgxdcSyAGrg; "D:(A;;GRGXDC;;;SY)(A;;GRGX;;;BA)(A;;GRG"...
0x18000691c  mov     r9d, 2
0x180006922  mov     r8d, r9d
0x180006925  lea     ecx, [r9+7Eh]
0x180006929  movups  xmm0, xmmword ptr [rax]
0x18000692c  movups  xmmword ptr [rdx], xmm0
0x18000692f  movups  xmm1, xmmword ptr [rax+10h]
0x180006933  movups  xmmword ptr [rdx+10h], xmm1
0x180006937  movups  xmm0, xmmword ptr [rax+20h]
0x18000693b  movups  xmmword ptr [rdx+20h], xmm0
0x18000693f  movups  xmm1, xmmword ptr [rax+30h]
0x180006943  movups  xmmword ptr [rdx+30h], xmm1
0x180006947  movups  xmm0, xmmword ptr [rax+40h]
0x18000694b  movups  xmmword ptr [rdx+40h], xmm0
0x18000694f  movups  xmm1, xmmword ptr [rax+50h]
0x180006953  movups  xmmword ptr [rdx+50h], xmm1
0x180006957  movups  xmm0, xmmword ptr [rax+60h]
0x18000695b  movups  xmmword ptr [rdx+60h], xmm0
0x18000695f  movups  xmm1, xmmword ptr [rax+70h]
0x180006963  movups  xmmword ptr [rdx+70h], xmm1
0x180006967  add     rdx, rcx
0x18000696a  add     rax, rcx
0x18000696d  sub     r8, 1
0x180006971  jnz     short loc_180006929
0x180006973  mov     rax, [rax-2]
0x180006977  mov     [rdx-2], rax
0x18000697b  mov     rdx, [rdi+8]
0x18000697f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006983  mov     rcx, r8
0x180006986  xor     r15d, r15d
0x180006989  inc     rcx
0x18000698c  cmp     [rdx+rcx*2], r15w
0x180006991  jnz     short loc_180006989
0x180006993  lea     rbx, [rcx+83h]
0x18000699a  mov     rax, r9
0x18000699d  mul     rbx
0x1800069a0  cmovb   rax, r8
0x1800069a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800069ab  mov     rcx, rax; unsigned __int64
0x1800069ae  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800069b3  mov     rsi, rax
0x1800069b6  mov     [rsp+3C0h+var_348], rax
0x1800069bb  test    rax, rax
0x1800069be  jnz     short loc_1800069CA
0x1800069c0  mov     ebx, 8007000Eh
0x1800069c5  jmp     loc_180006B0E
0x1800069ca  mov     r9, [rdi+8]
0x1800069ce  lea     r8, [rbp+2C0h+var_340]; wchar_t *
0x1800069d2  mov     rdx, rbx; unsigned __int64
0x1800069d5  mov     rcx, rsi; wchar_t *
0x1800069d8  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800069dd  mov     ebx, eax
0x1800069df  test    eax, eax
0x1800069e1  js      loc_180006B0E
0x1800069e7  xorps   xmm0, xmm0
0x1800069ea  xor     eax, eax
0x1800069ec  movups  xmmword ptr [rsp+3C0h+SecurityDescriptor], xmm0
0x1800069f1  mov     [rsp+3C0h+var_350], rax
0x1800069f6  xor     r9d, r9d; SecurityDescriptorSize
0x1800069f9  lea     r8, [rsp+3C0h+SecurityDescriptor+8]; SecurityDescriptor
0x1800069fe  lea     edx, [rax+1]; StringSDRevision
0x180006a01  mov     rcx, rsi; StringSecurityDescriptor
0x180006a04  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180006a0a  test    eax, eax
0x180006a0c  jnz     short loc_180006A32
0x180006a0e  call    cs:__imp_GetLastError
0x180006a14  mov     ebx, eax
0x180006a16  test    eax, eax
0x180006a18  jle     short loc_180006A23
0x180006a1a  movzx   ebx, ax
0x180006a1d  or      ebx, 80070000h
0x180006a23  mov     eax, 80004005h
0x180006a28  test    ebx, ebx
0x180006a2a  cmovns  ebx, eax
0x180006a2d  jmp     loc_180006B0E
0x180006a32  mov     [rsp+3C0h+hKey], r15
0x180006a37  lea     rax, [rsp+3C0h+hKey]
0x180006a3c  mov     qword ptr [rsp+3C0h+dwOptions], rax; unsigned int
0x180006a41  mov     r9d, 4; unsigned int
0x180006a47  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows Search\\Un"...
0x180006a4e  call    ?WSearchRegOpenKey@@YAJPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; WSearchRegOpenKey(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x180006a53  mov     ebx, eax
0x180006a55  test    eax, eax
0x180006a57  jle     short loc_180006A62
0x180006a59  movzx   ebx, ax
0x180006a5c  or      ebx, 80070000h
0x180006a62  test    ebx, ebx
0x180006a64  js      loc_180006B02
0x180006a6a  mov     [rsp+3C0h+var_368], r15
0x180006a6f  mov     dword ptr [rsp+3C0h+SecurityDescriptor], 18h
0x180006a77  mov     dword ptr [rsp+3C0h+var_350], r15d
0x180006a7c  mov     rbx, [rdi+8]
0x180006a80  mov     rdi, [rsp+3C0h+hKey]
0x180006a85  lea     r9, [rbp+2C0h+var_230]; wchar_t *
0x180006a8c  mov     r8, rbx; wchar_t *
0x180006a8f  mov     rdx, rdi; HKEY
0x180006a92  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x180006a97  lea     rdx, [rbp+2C0h+var_230]
0x180006a9e  test    al, al
0x180006aa0  cmovz   rdx, rbx; lpSubKey
0x180006aa4  mov     [rsp+3C0h+lpdwDisposition], r15; lpdwDisposition
0x180006aa9  lea     rax, [rsp+3C0h+var_368]
0x180006aae  mov     [rsp+3C0h+phkResult], rax; phkResult
0x180006ab3  lea     rax, [rsp+3C0h+SecurityDescriptor]
0x180006ab8  mov     [rsp+3C0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180006abd  mov     [rsp+3C0h+samDesired], 20019h; samDesired
0x180006ac5  mov     [rsp+3C0h+dwOptions], r15d; dwOptions
0x180006aca  xor     r9d, r9d; lpClass
0x180006acd  xor     r8d, r8d; Reserved
0x180006ad0  mov     rcx, rdi; hKey
0x180006ad3  call    cs:__imp_RegCreateKeyExW
0x180006ad9  mov     ebx, eax
0x180006adb  test    eax, eax
0x180006add  jle     short loc_180006AE8
0x180006adf  movzx   ebx, ax
0x180006ae2  or      ebx, 80070000h
0x180006ae8  test    ebx, ebx
0x180006aea  js      short loc_180006AF7
0x180006aec  mov     rcx, [rsp+3C0h+var_368]; hKey
0x180006af1  call    cs:__imp_RegCloseKey
0x180006af7  mov     rcx, [rsp+3C0h+hKey]; hKey
0x180006afc  call    cs:__imp_RegCloseKey
0x180006b02  mov     rcx, [rsp+3C0h+SecurityDescriptor+8]; hMem
0x180006b07  call    cs:__imp_LocalFree
0x180006b0d  nop
0x180006b0e  test    rsi, rsi
0x180006b11  jz      short loc_180006B1B
0x180006b13  mov     rcx, rsi; Block
0x180006b16  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006b1b  mov     eax, ebx
0x180006b1d  mov     rcx, [rbp+2C0h+var_20]
0x180006b24  xor     rcx, rsp; StackCookie
0x180006b27  call    __security_check_cookie
0x180006b2c  lea     r11, [rsp+3C0h+var_10]
0x180006b34  mov     rbx, [r11+28h]
0x180006b38  mov     rsi, [r11+30h]
0x180006b3c  mov     rsp, r11
0x180006b3f  pop     r15
0x180006b41  pop     rdi
0x180006b42  pop     rbp
0x180006b43  retn
```
