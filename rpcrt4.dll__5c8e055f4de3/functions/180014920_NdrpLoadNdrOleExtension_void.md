# NdrpLoadNdrOleExtension(void)

- ea: `0x180014920`
- end: `0x180014b65`
- name: `?NdrpLoadNdrOleExtension@@YAJXZ`
- size: `581`
- prototype: `__int64(void)`
- caller_count: `65`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001050`
- `0x18000447c`
- `0x180004814`
- `0x180006a30`
- `0x1800082d0`
- `0x180009730`
- `0x18000ab10`
- `0x18000b480`
- `0x180011acc`
- `0x1800120e0`
- `0x180013d50`
- `0x180013fb0`
- `0x180014020`
- `0x180014440`
- `0x1800144b0`
- `0x1800145c0`
- `0x180014600`
- `0x180014650`
- `0x1800146a0`
- `0x1800146f0`
- `0x180014740`
- `0x1800147b0`
- `0x180014810`
- `0x180014890`
- `0x1800148e0`
- `0x180014cf0`
- `0x180014d50`
- `0x180014f10`
- `0x180014f80`
- `0x180014ff0`
- `0x180015050`
- `0x1800150a0`
- `0x180015100`
- `0x180015170`
- `0x1800151c0`
- `0x180015220`
- `0x1800152a0`
- `0x180015310`
- `0x18001dd40`
- `0x1800bf0a0`
- `0x1800bf100`
- `0x1800bf150`
- `0x1800bf1a0`
- `0x1800bf210`
- `0x1800bf260`
- `0x1800bf2e0`
- `0x1800bf350`
- `0x1800bf3a0`
- `0x1800bf420`
- `0x1800bf490`

## callees

- `0x180014920`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!NtClose` at `0x180014a3d`
- `ntdll!NtClose` at `0x180014a3d`
- `ntdll!NtQueryValueKey` at `0x180014a30`
- `ntdll!NtQueryValueKey` at `0x180014a30`
- `ntdll!NtOpenKey` at `0x1800149fb`
- `ntdll!NtOpenKey` at `0x1800149fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b2c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180014b1d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180014b1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014a8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014a8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014a76`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014a76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014acc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014acc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149a1`

## string_xrefs

- `0x180014958`: `\REGISTRY\MACHINE\Software\Microsoft\Rpc\Extensions`
- `0x18001496d`: `NdrOleExtDLL`
- `0x180014a85`: `NdrOleInitializeExtension`

## pseudocode

```c
__int64 NdrpLoadNdrOleExtension(void)
{
  NTSTATUS v0; // eax
  NTSTATUS v1; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v4; // ebx
  DWORD LastError; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v9[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-B0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE KeyValueInformation[8]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v13; // [rsp+98h] [rbp-68h]
  WCHAR ModuleName[266]; // [rsp+9Ch] [rbp-64h] BYREF

  v9[0] = 6815846;
  KeyHandle = 0;
  *(_QWORD *)&ValueName.Length = 1703960;
  v9[1] = L"\\REGISTRY\\MACHINE\\Software\\Microsoft\\Rpc\\Extensions";
  ValueName.Buffer = L"NdrOleExtDLL";
  ResultLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( gNdrOleLoaded != 2 )
  {
    EnterCriticalSection(&NdrOle_CS);
    if ( gNdrOleLoaded == 1 )
    {
      v4 = 0;
    }
    else if ( gNdrOleLoaded == 2 )
    {
      v4 = 1764;
    }
    else
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v9;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v0 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
      if ( v0 < 0 )
      {
        v4 = 1764;
        if ( v0 != -1073741772 )
          v4 = 14;
      }
      else
      {
        v1 = NtQueryValueKey(
               KeyHandle,
               &ValueName,
               KeyValuePartialInformation,
               KeyValueInformation,
               0x21Au,
               &ResultLength);
        NtClose(KeyHandle);
        if ( v1 < 0 )
        {
LABEL_21:
          v4 = 14;
          goto LABEL_28;
        }
        if ( v13 >= 0x104 || !ModuleName[0] || !v13 )
          goto LABEL_25;
        *((_BYTE *)ModuleName + v13 - 1) = 0;
        ModuleHandleW = GetModuleHandleW(ModuleName);
        if ( !ModuleHandleW )
        {
          ModuleHandleW = LoadLibraryExW(ModuleName, 0, 0);
          if ( !ModuleHandleW )
          {
            LastError = GetLastError();
            if ( LastError != 8 && LastError != 1455 )
              goto LABEL_25;
            goto LABEL_21;
          }
        }
        ProcAddress = GetProcAddress(ModuleHandleW, "NdrOleInitializeExtension");
        if ( !ProcAddress )
        {
LABEL_25:
          v4 = 1764;
LABEL_26:
          gNdrOleLoaded = 2;
          goto LABEL_14;
        }
        v4 = ((__int64 (__fastcall *)(const struct _NDROLE_EXTENSION_ROUTINES_TABLE *const *, const struct _NDR_FWD_ROUTINES *const *))ProcAddress)(
               &pNdrOleExtensionsTable,
               &pNdrOleExportForwardTable);
      }
      if ( v4 )
      {
        if ( v4 != 14 )
          goto LABEL_26;
LABEL_28:
        gNdrOleLoaded = 3;
        goto LABEL_14;
      }
      gNdrOleLoaded = 1;
    }
LABEL_14:
    LeaveCriticalSection(&NdrOle_CS);
    return v4;
  }
  return 1764;
}

```

## disassembly

```asm
0x180014920  push    rbp
0x180014922  push    rbx
0x180014923  push    rsi
0x180014924  push    rdi
0x180014925  lea     rbp, [rsp-1C8h]
0x18001492d  sub     rsp, 2C8h
0x180014934  mov     rax, cs:__security_cookie
0x18001493b  xor     rax, rsp
0x18001493e  mov     [rbp+1E0h+var_30], rax
0x180014945  xor     edi, edi
0x180014947  mov     [rsp+2E0h+var_2A0], 680066h
0x180014950  xorps   xmm0, xmm0
0x180014953  mov     [rsp+2E0h+KeyHandle], rdi
0x180014958  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE\\Software\\Microsof"...
0x18001495f  mov     qword ptr [rsp+2E0h+ValueName.Length], 1A0018h
0x180014968  mov     [rsp+2E0h+var_298], rax
0x18001496d  lea     rax, aNdroleextdll; "NdrOleExtDLL"
0x180014974  mov     [rsp+2E0h+ValueName.Buffer], rax
0x180014979  mov     eax, cs:?gNdrOleLoaded@@3W4_NdrOleStatus@@C; _NdrOleStatus volatile gNdrOleLoaded
0x18001497f  mov     [rsp+2E0h+var_2B0], edi
0x180014983  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x180014988  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x18001498d  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180014991  cmp     eax, 2
0x180014994  jz      loc_180014AF3
0x18001499a  lea     rcx, ?NdrOle_CS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800149a1  call    cs:__imp_EnterCriticalSection
0x1800149a7  mov     eax, cs:?gNdrOleLoaded@@3W4_NdrOleStatus@@C; _NdrOleStatus volatile gNdrOleLoaded
0x1800149ad  cmp     eax, 1
0x1800149b0  jz      loc_180014AEF
0x1800149b6  mov     eax, cs:?gNdrOleLoaded@@3W4_NdrOleStatus@@C; _NdrOleStatus volatile gNdrOleLoaded
0x1800149bc  cmp     eax, 2
0x1800149bf  jz      loc_180014AFA
0x1800149c5  lea     rax, [rsp+2E0h+var_2A0]
0x1800149ca  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x1800149d2  xorps   xmm0, xmm0
0x1800149d5  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x1800149da  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x1800149df  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rdi
0x1800149e4  mov     edx, 20019h; DesiredAccess
0x1800149e9  mov     [rsp+2E0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800149f1  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x1800149f6  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800149fb  call    cs:__imp_NtOpenKey
0x180014a01  lea     esi, [rdi+0Eh]
0x180014a04  test    eax, eax
0x180014a06  js      loc_180014B01
0x180014a0c  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x180014a11  lea     rax, [rsp+2E0h+var_2B0]
0x180014a16  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x180014a1b  lea     r9, [rbp+1E0h+KeyValueInformation]; KeyValueInformation
0x180014a1f  lea     r8d, [rdi+2]; KeyValueInformationClass
0x180014a23  mov     [rsp+2E0h+Length], 21Ah; Length
0x180014a2b  lea     rdx, [rsp+2E0h+ValueName]; ValueName
0x180014a30  call    cs:__imp_NtQueryValueKey
0x180014a36  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x180014a3b  mov     ebx, eax
0x180014a3d  call    cs:__imp_NtClose
0x180014a43  test    ebx, ebx
0x180014a45  js      loc_180014B10
0x180014a4b  mov     eax, [rbp+1E0h+var_248]
0x180014a4e  cmp     eax, 104h
0x180014a53  jnb     loc_180014B3E
0x180014a59  cmp     [rbp+1E0h+ModuleName], di
0x180014a5d  jz      loc_180014B3E
0x180014a63  test    eax, eax
0x180014a65  jz      loc_180014B3E
0x180014a6b  dec     eax
0x180014a6d  lea     rcx, [rbp+1E0h+ModuleName]; lpModuleName
0x180014a71  mov     byte ptr [rbp+rax+1E0h+ModuleName], dil
0x180014a76  call    cs:__imp_GetModuleHandleW
0x180014a7c  test    rax, rax
0x180014a7f  jz      loc_180014B14
0x180014a85  lea     rdx, ProcName; "NdrOleInitializeExtension"
0x180014a8c  mov     rcx, rax; hModule
0x180014a8f  call    cs:__imp_GetProcAddress
0x180014a95  test    rax, rax
0x180014a98  jz      loc_180014B3E
0x180014a9e  lea     rdx, ?pNdrOleExportForwardTable@@3PEBU_NDR_FWD_ROUTINES@@EB; _NDR_FWD_ROUTINES const * const pNdrOleExportForwardTable
0x180014aa5  lea     rcx, ?pNdrOleExtensionsTable@@3PEBU_NDROLE_EXTENSION_ROUTINES_TABLE@@EB; _NDROLE_EXTENSION_ROUTINES_TABLE const * const pNdrOleExtensionsTable
0x180014aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ab1  mov     ebx, eax
0x180014ab3  test    ebx, ebx
0x180014ab5  jnz     loc_180014B52
0x180014abb  mov     cs:?gNdrOleLoaded@@3W4_NdrOleStatus@@C, 1; _NdrOleStatus volatile gNdrOleLoaded
0x180014ac5  lea     rcx, ?NdrOle_CS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180014acc  call    cs:__imp_LeaveCriticalSection
0x180014ad2  mov     eax, ebx
0x180014ad4  mov     rcx, [rbp+1E0h+var_30]
0x180014adb  xor     rcx, rsp; StackCookie
0x180014ade  call    __security_check_cookie
0x180014ae3  add     rsp, 2C8h
0x180014aea  pop     rdi
0x180014aeb  pop     rsi
0x180014aec  pop     rbx
0x180014aed  pop     rbp
0x180014aee  retn
0x180014aef  mov     ebx, edi
0x180014af1  jmp     short loc_180014AC5
0x180014af3  mov     eax, 6E4h
0x180014af8  jmp     short loc_180014AD4
0x180014afa  mov     ebx, 6E4h
0x180014aff  jmp     short loc_180014AC5
0x180014b01  cmp     eax, 0C0000034h
0x180014b06  mov     ebx, 6E4h
0x180014b0b  cmovnz  ebx, esi
0x180014b0e  jmp     short loc_180014AB3
0x180014b10  mov     ebx, esi
0x180014b12  jmp     short loc_180014B56
0x180014b14  xor     r8d, r8d; dwFlags
0x180014b17  lea     rcx, [rbp+1E0h+ModuleName]; lpLibFileName
0x180014b1b  xor     edx, edx; hFile
0x180014b1d  call    cs:__imp_LoadLibraryExW
0x180014b23  test    rax, rax
0x180014b26  jnz     loc_180014A85
0x180014b2c  call    cs:__imp_GetLastError
0x180014b32  cmp     eax, 8
0x180014b35  jz      short loc_180014B10
0x180014b37  cmp     eax, 5AFh
0x180014b3c  jz      short loc_180014B10
0x180014b3e  mov     ebx, 6E4h
0x180014b43  mov     cs:?gNdrOleLoaded@@3W4_NdrOleStatus@@C, 2; _NdrOleStatus volatile gNdrOleLoaded
0x180014b4d  jmp     loc_180014AC5
0x180014b52  cmp     ebx, esi
0x180014b54  jnz     short loc_180014B43
0x180014b56  mov     cs:?gNdrOleLoaded@@3W4_NdrOleStatus@@C, 3; _NdrOleStatus volatile gNdrOleLoaded
0x180014b60  jmp     loc_180014AC5
```
