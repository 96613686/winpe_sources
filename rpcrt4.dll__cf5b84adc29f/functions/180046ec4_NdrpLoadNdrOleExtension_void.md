# NdrpLoadNdrOleExtension(void)

- ea: `0x180046ec4`
- end: `0x180047140`
- name: `?NdrpLoadNdrOleExtension@@YAJXZ`
- size: `636`
- prototype: `__int64(void)`
- caller_count: `65`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001050`
- `0x18001ee10`
- `0x180037500`
- `0x1800396e0`
- `0x18003a810`
- `0x18003bca0`
- `0x18003d090`
- `0x18003da20`
- `0x180044040`
- `0x180044660`
- `0x1800462d0`
- `0x180046540`
- `0x1800465b0`
- `0x1800469d0`
- `0x180046a40`
- `0x180046b50`
- `0x180046b90`
- `0x180046bf0`
- `0x180046c40`
- `0x180046c90`
- `0x180046ce0`
- `0x180046d50`
- `0x180046db0`
- `0x180046e30`
- `0x180046e80`
- `0x180047150`
- `0x1800471a4`
- `0x180047210`
- `0x1800473e0`
- `0x180047450`
- `0x1800474c0`
- `0x180047520`
- `0x180047570`
- `0x1800475d0`
- `0x180047640`
- `0x1800476a0`
- `0x180047700`
- `0x180047790`
- `0x180047800`
- `0x1800c3870`
- `0x1800c38d0`
- `0x1800c3920`
- `0x1800c3980`
- `0x1800c39f0`
- `0x1800c3a40`
- `0x1800c3ac0`
- `0x1800c3b30`
- `0x1800c3b80`
- `0x1800c3c00`
- `0x1800c3c70`

## callees

- `0x180046ec4`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!NtClose` at `0x180046ff3`
- `ntdll!NtClose` at `0x180046ff3`
- `ntdll!NtQueryValueKey` at `0x180046fe0`
- `ntdll!NtQueryValueKey` at `0x180046fe0`
- `ntdll!NtOpenKey` at `0x180046fa5`
- `ntdll!NtOpenKey` at `0x180046fa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047101`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800470ec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800470ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047051`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047051`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180047032`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180047032`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047094`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047094`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046f45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046f45`

## string_xrefs

- `0x180046efc`: `\REGISTRY\MACHINE\Software\Microsoft\Rpc\Extensions`
- `0x180046f11`: `NdrOleExtDLL`
- `0x180047047`: `NdrOleInitializeExtension`

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
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
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
0x180046ec4  push    rbp
0x180046ec6  push    rbx
0x180046ec7  push    rsi
0x180046ec8  push    rdi
0x180046ec9  lea     rbp, [rsp-1C8h]
0x180046ed1  sub     rsp, 2C8h
0x180046ed8  mov     rax, cs:__security_cookie
0x180046edf  xor     rax, rsp
0x180046ee2  mov     [rbp+1E0h+var_30], rax
0x180046ee9  xor     edi, edi
0x180046eeb  mov     [rsp+2E0h+var_2A0], 680066h
0x180046ef4  xorps   xmm0, xmm0
0x180046ef7  mov     [rsp+2E0h+KeyHandle], rdi
0x180046efc  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE\\Software\\Microsof"...
0x180046f03  mov     qword ptr [rsp+2E0h+ValueName.Length], 1A0018h
0x180046f0c  mov     [rsp+2E0h+var_298], rax
0x180046f11  lea     rax, aNdroleextdll; "NdrOleExtDLL"
0x180046f18  mov     [rsp+2E0h+ValueName.Buffer], rax
0x180046f1d  mov     eax, cs:?gNdrOleLoaded@@3W4_NdrOleStatus@@C; _NdrOleStatus volatile gNdrOleLoaded
0x180046f23  mov     [rsp+2E0h+var_2B0], edi
0x180046f27  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x180046f2c  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x180046f31  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180046f35  cmp     eax, 2
0x180046f38  jz      loc_1800470C2
0x180046f3e  lea     rcx, ?NdrOle_CS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180046f45  call    cs:__imp_EnterCriticalSection
0x180046f4c  nop     dword ptr [rax+rax+00h]
0x180046f51  mov     eax, cs:?gNdrOleLoaded@@3W4_NdrOleStatus@@C; _NdrOleStatus volatile gNdrOleLoaded
0x180046f57  cmp     eax, 1
0x180046f5a  jz      loc_1800470BE
0x180046f60  mov     eax, cs:?gNdrOleLoaded@@3W4_NdrOleStatus@@C; _NdrOleStatus volatile gNdrOleLoaded
0x180046f66  cmp     eax, 2
0x180046f69  jz      loc_1800470C9
0x180046f6f  lea     rax, [rsp+2E0h+var_2A0]
0x180046f74  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x180046f7c  xorps   xmm0, xmm0
0x180046f7f  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x180046f84  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x180046f89  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rdi
0x180046f8e  mov     edx, 20019h; DesiredAccess
0x180046f93  mov     [rsp+2E0h+ObjectAttributes.Attributes], 40h ; '@'
0x180046f9b  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x180046fa0  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180046fa5  call    cs:__imp_NtOpenKey
0x180046fac  nop     dword ptr [rax+rax+00h]
0x180046fb1  lea     esi, [rdi+0Eh]
0x180046fb4  test    eax, eax
0x180046fb6  js      loc_1800470D0
0x180046fbc  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x180046fc1  lea     rax, [rsp+2E0h+var_2B0]
0x180046fc6  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x180046fcb  lea     r9, [rbp+1E0h+KeyValueInformation]; KeyValueInformation
0x180046fcf  lea     r8d, [rdi+2]; KeyValueInformationClass
0x180046fd3  mov     [rsp+2E0h+Length], 21Ah; Length
0x180046fdb  lea     rdx, [rsp+2E0h+ValueName]; ValueName
0x180046fe0  call    cs:__imp_NtQueryValueKey
0x180046fe7  nop     dword ptr [rax+rax+00h]
0x180046fec  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x180046ff1  mov     ebx, eax
0x180046ff3  call    cs:__imp_NtClose
0x180046ffa  nop     dword ptr [rax+rax+00h]
0x180046fff  test    ebx, ebx
0x180047001  js      loc_1800470DF
0x180047007  mov     eax, [rbp+1E0h+var_248]
0x18004700a  cmp     eax, 104h
0x18004700f  jnb     loc_180047119
0x180047015  cmp     [rbp+1E0h+ModuleName], di
0x180047019  jz      loc_180047119
0x18004701f  test    eax, eax
0x180047021  jz      loc_180047119
0x180047027  dec     eax
0x180047029  lea     rcx, [rbp+1E0h+ModuleName]; lpModuleName
0x18004702d  mov     byte ptr [rbp+rax+1E0h+ModuleName], dil
0x180047032  call    cs:__imp_GetModuleHandleW
0x180047039  nop     dword ptr [rax+rax+00h]
0x18004703e  test    rax, rax
0x180047041  jz      loc_1800470E3
0x180047047  lea     rdx, ProcName; "NdrOleInitializeExtension"
0x18004704e  mov     rcx, rax; hModule
0x180047051  call    cs:__imp_GetProcAddress
0x180047058  nop     dword ptr [rax+rax+00h]
0x18004705d  test    rax, rax
0x180047060  jz      loc_180047119
0x180047066  lea     rdx, ?pNdrOleExportForwardTable@@3PEBU_NDR_FWD_ROUTINES@@EB; _NDR_FWD_ROUTINES const * const pNdrOleExportForwardTable
0x18004706d  lea     rcx, ?pNdrOleExtensionsTable@@3PEBU_NDROLE_EXTENSION_ROUTINES_TABLE@@EB; _NDROLE_EXTENSION_ROUTINES_TABLE const * const pNdrOleExtensionsTable
0x180047074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047079  mov     ebx, eax
0x18004707b  test    ebx, ebx
0x18004707d  jnz     loc_18004712D
0x180047083  mov     cs:?gNdrOleLoaded@@3W4_NdrOleStatus@@C, 1; _NdrOleStatus volatile gNdrOleLoaded
0x18004708d  lea     rcx, ?NdrOle_CS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180047094  call    cs:__imp_LeaveCriticalSection
0x18004709b  nop     dword ptr [rax+rax+00h]
0x1800470a0  mov     eax, ebx
0x1800470a2  mov     rcx, [rbp+1E0h+var_30]
0x1800470a9  xor     rcx, rsp; StackCookie
0x1800470ac  call    __security_check_cookie
0x1800470b1  add     rsp, 2C8h
0x1800470b8  pop     rdi
0x1800470b9  pop     rsi
0x1800470ba  pop     rbx
0x1800470bb  pop     rbp
0x1800470bc  retn
0x1800470be  mov     ebx, edi
0x1800470c0  jmp     short loc_18004708D
0x1800470c2  mov     eax, 6E4h
0x1800470c7  jmp     short loc_1800470A2
0x1800470c9  mov     ebx, 6E4h
0x1800470ce  jmp     short loc_18004708D
0x1800470d0  cmp     eax, 0C0000034h
0x1800470d5  mov     ebx, 6E4h
0x1800470da  cmovnz  ebx, esi
0x1800470dd  jmp     short loc_18004707B
0x1800470df  mov     ebx, esi
0x1800470e1  jmp     short loc_180047131
0x1800470e3  xor     r8d, r8d; dwFlags
0x1800470e6  lea     rcx, [rbp+1E0h+ModuleName]; lpLibFileName
0x1800470ea  xor     edx, edx; hFile
0x1800470ec  call    cs:__imp_LoadLibraryExW
0x1800470f3  nop     dword ptr [rax+rax+00h]
0x1800470f8  test    rax, rax
0x1800470fb  jnz     loc_180047047
0x180047101  call    cs:__imp_GetLastError
0x180047108  nop     dword ptr [rax+rax+00h]
0x18004710d  cmp     eax, 8
0x180047110  jz      short loc_1800470DF
0x180047112  cmp     eax, 5AFh
0x180047117  jz      short loc_1800470DF
0x180047119  mov     ebx, 6E4h
0x18004711e  mov     cs:?gNdrOleLoaded@@3W4_NdrOleStatus@@C, 2; _NdrOleStatus volatile gNdrOleLoaded
0x180047128  jmp     loc_18004708D
0x18004712d  cmp     ebx, esi
0x18004712f  jnz     short loc_18004711E
0x180047131  mov     cs:?gNdrOleLoaded@@3W4_NdrOleStatus@@C, 3; _NdrOleStatus volatile gNdrOleLoaded
0x18004713b  jmp     loc_18004708D
```
