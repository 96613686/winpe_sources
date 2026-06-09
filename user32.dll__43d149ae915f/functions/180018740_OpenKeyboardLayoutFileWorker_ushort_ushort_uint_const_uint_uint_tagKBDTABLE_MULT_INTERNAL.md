# OpenKeyboardLayoutFileWorker(ushort *,ushort *,uint const *,uint *,uint *,tagKBDTABLE_MULT_INTERNAL *)

- ea: `0x180018740`
- end: `0x180018d90`
- name: `?OpenKeyboardLayoutFileWorker@@YAPEAXPEAG0PEBIPEAI2PEAUtagKBDTABLE_MULT_INTERNAL@@@Z`
- size: `1616`
- prototype: `void *__fastcall(unsigned __int16 *, unsigned __int16 *, const unsigned int *, unsigned int *, unsigned int *, struct tagKBDTABLE_MULT_INTERNAL *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001867c`
- `0x180018740`
- `0x1800193b4`

## callees

- `0x180018740`
- `0x18001a2b8`
- `0x1800604ec`
- `0x180096dc5`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `ntdll!RtlGetActiveConsoleId` at `0x180018a0c`
- `ntdll!RtlGetActiveConsoleId` at `0x180018a76`
- `ntdll!RtlGetActiveConsoleId` at `0x180018cee`
- `ntdll!RtlGetActiveConsoleId` at `0x180018a0c`
- `ntdll!RtlGetActiveConsoleId` at `0x180018a76`
- `ntdll!RtlGetActiveConsoleId` at `0x180018cee`
- `ntdll!NtQueryValueKey` at `0x180018c14`
- `ntdll!NtQueryValueKey` at `0x180018c5f`
- `ntdll!NtQueryValueKey` at `0x180018c14`
- `ntdll!NtQueryValueKey` at `0x180018c5f`
- `ntdll!NtClose` at `0x180018c77`
- `ntdll!NtClose` at `0x1800997cd`
- `ntdll!NtClose` at `0x180018c77`
- `ntdll!NtClose` at `0x1800997cd`
- `ntdll!NtOpenKey` at `0x180018bcf`
- `ntdll!NtOpenKey` at `0x180018bcf`
- `ntdll!RtlUnicodeStringToInteger` at `0x1800189a0`
- `ntdll!RtlUnicodeStringToInteger` at `0x1800189a0`
- `ntdll!RtlInitUnicodeString` at `0x18001898c`
- `ntdll!RtlInitUnicodeString` at `0x180018b94`
- `ntdll!RtlInitUnicodeString` at `0x180018be9`
- `ntdll!RtlInitUnicodeString` at `0x180018c37`
- `ntdll!RtlInitUnicodeString` at `0x18001898c`
- `ntdll!RtlInitUnicodeString` at `0x180018b94`
- `ntdll!RtlInitUnicodeString` at `0x180018be9`
- `ntdll!RtlInitUnicodeString` at `0x180018c37`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800188a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018a3c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800188a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018a3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001880c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001887b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800188ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018914`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001893f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001880c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001887b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800188ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018914`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001893f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001889a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001889a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800187e9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018a23`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800187e9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018a23`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800188ce`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800188ce`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800189f3`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180018a59`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180018cd5`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800189f3`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180018a59`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180018cd5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180018b5a`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180018b5a`

## string_xrefs

- `0x1800187a9`: `kbdus.dll`
- `0x180018960`: `kbdus.dll`
- `0x180018b4c`: `System\CurrentControlSet\Services\i8042prt\Parameters`
- `0x180018b69`: `\Registry\Machine\`

## pseudocode

```c
HANDLE __fastcall OpenKeyboardLayoutFileWorker(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        const unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        struct tagKBDTABLE_MULT_INTERNAL *a6)
{
  const unsigned int *v6; // rbx
  HMODULE Library; // rax
  HMODULE v9; // r14
  __int64 (*v10)(void); // rax
  __int64 v11; // r8
  _WORD *v12; // rax
  _WORD *v13; // rcx
  unsigned int *v14; // rbx
  __int64 (*v15)(void); // rax
  FARPROC ProcAddress; // r13
  FARPROC v18; // r12
  FARPROC v19; // rax
  FARPROC v20; // rsi
  ULONG v21; // ebx
  ULONG v22; // ebx
  HMODULE v23; // rbx
  ULONG SessionId; // ebx
  ULONG v25; // ebx
  __int64 v26; // rbx
  void *v27; // rax
  ULONG v28; // ebx
  ULONG v29; // ebx
  int ClientKeyboardType; // eax
  INT_PTR (__stdcall *v31)(); // rcx
  unsigned int i; // ebx
  void *v33; // rcx
  unsigned int v35; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v36; // [rsp+4Ch] [rbp-B4h] BYREF
  ULONG ResultLength; // [rsp+50h] [rbp-B0h] BYREF
  void *KeyHandle; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+60h] [rbp-A0h] BYREF
  FARPROC v40; // [rsp+70h] [rbp-90h]
  ULONG Value[2]; // [rsp+78h] [rbp-88h] BYREF
  INT_PTR (__stdcall *v42)(); // [rsp+80h] [rbp-80h]
  PCWSTR SourceString; // [rsp+88h] [rbp-78h]
  unsigned int *v44; // [rsp+90h] [rbp-70h]
  unsigned int *v45; // [rsp+98h] [rbp-68h]
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v48; // [rsp+E0h] [rbp-20h] BYREF
  int v49; // [rsp+E8h] [rbp-18h]
  __int128 KeyValueInformation; // [rsp+F0h] [rbp-10h] BYREF
  int v51; // [rsp+100h] [rbp+0h]
  __int128 v52; // [rsp+108h] [rbp+8h] BYREF
  int v53; // [rsp+118h] [rbp+18h]
  WCHAR LibFileName[264]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v55[528]; // [rsp+330h] [rbp+230h] BYREF
  WCHAR v56[264]; // [rsp+540h] [rbp+440h] BYREF
  WCHAR Filename[264]; // [rsp+750h] [rbp+650h] BYREF

  v6 = a3;
  SourceString = a2;
  v45 = a5;
  v44 = a4;
  memset_0(Filename, 0, 0x208u);
  KeyHandle = 0;
  v51 = 0;
  v53 = 0;
  ValueName = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyValueInformation = 0;
  v52 = 0;
  while ( 1 )
  {
    Library = LoadLibraryExW(a1, 0, 0);
    v9 = Library;
    if ( !Library )
      return 0;
    if ( a1 != L"kbdus.dll" )
    {
      ProcAddress = GetProcAddress(Library, (LPCSTR)3);
      v42 = ProcAddress;
      v40 = GetProcAddress(v9, (LPCSTR)5);
      v18 = v40;
      if ( a6
        && ((*v6 & 0x20000000) != 0
         || (SessionId = NtCurrentPeb()->SessionId, SessionId == (unsigned int)WTSGetServiceSessionId())
         || (v25 = NtCurrentPeb()->SessionId, v25 == (unsigned int)RtlGetActiveConsoleId())) )
      {
        v19 = GetProcAddress(v9, (LPCSTR)6);
        v20 = v19;
        if ( v19 && ((unsigned int (__fastcall *)(struct tagKBDTABLE_MULT_INTERNAL *))v19)(a6) )
        {
          if ( *(_DWORD *)a6 >= 8u )
          {
            *(_DWORD *)a6 = 0;
          }
          else
          {
            v26 = 0;
            if ( *(_DWORD *)a6 )
            {
              do
              {
                v35 = 0;
                v36 = 0;
                v27 = OpenKeyboardLayoutFileWorker((unsigned __int16 *)a6 + 36 * v26 + 2, 0, a3, &v35, &v36, 0);
                *((_QWORD *)a6 + 2 * (unsigned int)v26 + 81) = v27;
                if ( v27 )
                {
                  *((_DWORD *)a6 + 4 * v26 + 164) = v35;
                  *((_DWORD *)a6 + 4 * (unsigned int)v26 + 165) = v36;
                }
                v26 = (unsigned int)(v26 + 1);
              }
              while ( (unsigned int)v26 < *(_DWORD *)a6 );
              ProcAddress = v42;
            }
            memset_0(v56, 0, 0x208u);
            memset_0(v55, 0, 0x208u);
            GetPersistedRegistryLocationW(
              L"InputSettings",
              L"System\\CurrentControlSet\\Services\\i8042prt\\Parameters",
              v55,
              260,
              0);
            StringCchPrintfW(v56, 0x104u, L"%s%s", L"\\Registry\\Machine\\", v55);
            RtlInitUnicodeString(&ValueName, v56);
            ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = &ValueName;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 64;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
            {
              RtlInitUnicodeString(&ValueName, L"OverrideKeyboardType");
              if ( NtQueryValueKey(
                     KeyHandle,
                     &ValueName,
                     KeyValuePartialInformation,
                     &KeyValueInformation,
                     0x14u,
                     &ResultLength) >= 0 )
                *((_DWORD *)a6 + 195) = HIDWORD(KeyValueInformation);
              if ( *((_DWORD *)a6 + 195) )
              {
                RtlInitUnicodeString(&ValueName, L"OverrideKeyboardSubtype");
                if ( NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &v52, 0x14u, &ResultLength) >= 0 )
                  *((_DWORD *)a6 + 196) = HIDWORD(v52);
              }
              NtClose(KeyHandle);
            }
          }
        }
      }
      else
      {
        v20 = 0;
      }
      if ( v18 )
      {
        v18 = 0;
      }
      else if ( !ProcAddress )
      {
        goto LABEL_20;
      }
      *(_QWORD *)Value = 0;
      v48 = 0;
      DestinationString = 0;
      v49 = 0;
      RtlInitUnicodeString(&DestinationString, SourceString);
      RtlUnicodeStringToInteger(&DestinationString, 0x10u, Value);
      v6 = a3;
      if ( (*a3 & 0x20000000) == 0 )
      {
        v28 = NtCurrentPeb()->SessionId;
        if ( v28 != (unsigned int)WTSGetServiceSessionId() )
        {
          v29 = NtCurrentPeb()->SessionId;
          if ( v29 != (unsigned int)RtlGetActiveConsoleId() )
          {
            ClientKeyboardType = GetClientKeyboardType((struct _CLIENTKEYBOARDTYPE *)&v48);
            v31 = (INT_PTR (__stdcall *)())&v48;
            if ( !ClientKeyboardType )
              v31 = 0;
            v18 = v31;
          }
        }
        v6 = a3;
      }
      if ( v40
        && ((unsigned int (__fastcall *)(_QWORD, WCHAR *, FARPROC, _QWORD))v40)(*(_QWORD *)Value, LibFileName, v18, 0)
        || ProcAddress && ((unsigned int (__fastcall *)(WCHAR *))ProcAddress)(LibFileName) )
      {
        v21 = NtCurrentPeb()->SessionId;
        if ( v21 != (unsigned int)WTSGetServiceSessionId() )
        {
          v22 = NtCurrentPeb()->SessionId;
          if ( v22 != (unsigned int)RtlGetActiveConsoleId() && !v20 )
            *((_DWORD *)a6 + 194) |= 1u;
        }
        v23 = LoadLibraryExW(LibFileName, 0, 0);
        if ( v23 )
        {
          a1 = LibFileName;
          FreeLibrary(v9);
          v9 = v23;
        }
LABEL_20:
        v6 = a3;
      }
    }
    v10 = GetProcAddress(v9, (LPCSTR)1);
    if ( v10 )
      break;
    if ( a6 )
    {
      for ( i = 0; i < *(_DWORD *)a6; ++i )
      {
        if ( i >= 8 )
          break;
        v33 = (void *)*((_QWORD *)a6 + 2 * i + 81);
        if ( v33 )
        {
          NtClose(v33);
          *((_QWORD *)a6 + 2 * i + 81) = 0;
        }
      }
      v6 = a3;
      *(_DWORD *)a6 = 0;
    }
    if ( *(int *)v6 >= 0 || a1 == L"kbdus.dll" )
      return 0;
    a1 = L"kbdus.dll";
  }
  *v44 = v10() - (_DWORD)v9;
  if ( a6 )
  {
    v11 = 32;
    v12 = (_WORD *)((char *)a6 + 580);
    do
    {
      if ( !*a1 )
        break;
      *v12++ = *a1++;
      --v11;
    }
    while ( v11 );
    v13 = v12 - 1;
    if ( v11 )
      v13 = v12;
    *v13 = 0;
    *((_WORD *)a6 + 321) = 0;
  }
  v14 = v45;
  *v45 = 0;
  v15 = GetProcAddress(v9, (LPCSTR)2);
  if ( v15 )
    *v14 = v15() - (_DWORD)v9;
  GetModuleFileNameW(v9, Filename, 0x104u);
  FreeLibrary(v9);
  return CreateFileW(Filename, 0x80000000, 1u, 0, 3u, 0, 0);
}

```

## disassembly

```asm
0x180018740  push    rbp
0x180018742  push    rbx
0x180018743  push    rsi
0x180018744  push    rdi
0x180018745  push    r12
0x180018747  push    r13
0x180018749  push    r14
0x18001874b  push    r15
0x18001874d  lea     rbp, [rsp-878h]
0x180018755  sub     rsp, 978h
0x18001875c  mov     rax, cs:__security_cookie
0x180018763  xor     rax, rsp
0x180018766  mov     [rbp+8B0h+var_50], rax
0x18001876d  mov     rax, [rbp+8B0h+arg_20]
0x180018774  mov     rbx, r8
0x180018777  mov     rdi, [rbp+8B0h+arg_28]
0x18001877e  mov     r15, rcx
0x180018781  mov     [rbp+8B0h+SourceString], rdx
0x180018785  lea     rcx, [rbp+8B0h+Filename]; void *
0x18001878c  xor     edx, edx; Val
0x18001878e  mov     [rsp+9B0h+var_970], rbx
0x180018793  mov     r8d, 208h; Size
0x180018799  mov     [rbp+8B0h+var_918], rax
0x18001879d  mov     [rbp+8B0h+var_920], r9
0x1800187a1  call    memset_0
0x1800187a6  xorps   xmm1, xmm1
0x1800187a9  lea     r13, aKbdusDll; "kbdus.dll"
0x1800187b0  xor     r12d, r12d
0x1800187b3  xorps   xmm0, xmm0
0x1800187b6  xor     eax, eax
0x1800187b8  mov     [rsp+9B0h+KeyHandle], r12
0x1800187bd  mov     [rbp+8B0h+var_8B0], eax
0x1800187c0  mov     [rbp+8B0h+var_898], eax
0x1800187c3  movups  xmmword ptr [rsp+9B0h+ValueName.Length], xmm0
0x1800187c8  mov     [rsp+9B0h+ResultLength], r12d
0x1800187cd  movups  xmmword ptr [rbp+8B0h+ObjectAttributes.Length], xmm1
0x1800187d1  movups  xmmword ptr [rbp+8B0h+ObjectAttributes.ObjectName], xmm1
0x1800187d5  movups  xmmword ptr [rbp+8B0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800187d9  movups  [rbp+8B0h+KeyValueInformation], xmm0
0x1800187dd  movups  [rbp+8B0h+var_8A8], xmm1
0x1800187e1  xor     r8d, r8d; dwFlags
0x1800187e4  xor     edx, edx; hFile
0x1800187e6  mov     rcx, r15; lpLibFileName
0x1800187e9  call    cs:__imp_LoadLibraryExW
0x1800187ef  mov     r14, rax
0x1800187f2  test    rax, rax
0x1800187f5  jz      loc_180018D17
0x1800187fb  cmp     r15, r13
0x1800187fe  jnz     loc_1800188F7
0x180018804  mov     edx, 1; lpProcName
0x180018809  mov     rcx, r14; hModule
0x18001880c  call    cs:__imp_GetProcAddress
0x180018812  test    rax, rax
0x180018815  jz      loc_180018C82
0x18001881b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018820  mov     rcx, [rbp+8B0h+var_920]
0x180018824  sub     eax, r14d
0x180018827  mov     [rcx], eax
0x180018829  test    rdi, rdi
0x18001882c  jz      short loc_18001886C
0x18001882e  mov     r8d, 20h ; ' '
0x180018834  lea     rax, [rdi+244h]
0x18001883b  movzx   ecx, word ptr [r15]
0x18001883f  test    cx, cx
0x180018842  jz      short loc_180018855
0x180018844  mov     [rax], cx
0x180018847  add     r15, 2
0x18001884b  add     rax, 2
0x18001884f  sub     r8, 1
0x180018853  jnz     short loc_18001883B
0x180018855  test    r8, r8
0x180018858  lea     rcx, [rax-2]
0x18001885c  cmovnz  rcx, rax
0x180018860  mov     [rcx], r12w
0x180018864  mov     [rdi+282h], r12w
0x18001886c  mov     rbx, [rbp+8B0h+var_918]
0x180018870  mov     edx, 2; lpProcName
0x180018875  mov     rcx, r14; hModule
0x180018878  mov     [rbx], r12d
0x18001887b  call    cs:__imp_GetProcAddress
0x180018881  test    rax, rax
0x180018884  jnz     loc_180018D3C
0x18001888a  mov     r8d, 104h; nSize
0x180018890  lea     rdx, [rbp+8B0h+Filename]; lpFilename
0x180018897  mov     rcx, r14; hModule
0x18001889a  call    cs:__imp_GetModuleFileNameW
0x1800188a0  mov     rcx, r14; hLibModule
0x1800188a3  call    cs:__imp_FreeLibrary
0x1800188a9  xor     r9d, r9d; lpSecurityAttributes
0x1800188ac  mov     [rsp+9B0h+hTemplateFile], r12; hTemplateFile
0x1800188b1  mov     [rsp+9B0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800188b6  lea     rcx, [rbp+8B0h+Filename]; lpFileName
0x1800188bd  mov     edx, 80000000h; dwDesiredAccess
0x1800188c2  mov     [rsp+9B0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800188ca  lea     r8d, [r9+1]; dwShareMode
0x1800188ce  call    cs:__imp_CreateFileW
0x1800188d4  mov     rcx, [rbp+8B0h+var_50]
0x1800188db  xor     rcx, rsp; StackCookie
0x1800188de  call    __security_check_cookie
0x1800188e3  add     rsp, 978h
0x1800188ea  pop     r15
0x1800188ec  pop     r14
0x1800188ee  pop     r13
0x1800188f0  pop     r12
0x1800188f2  pop     rdi
0x1800188f3  pop     rsi
0x1800188f4  pop     rbx
0x1800188f5  pop     rbp
0x1800188f6  retn
0x1800188f7  mov     edx, 3; lpProcName
0x1800188fc  mov     rcx, r14; hModule
0x1800188ff  call    cs:__imp_GetProcAddress
0x180018905  mov     edx, 5; lpProcName
0x18001890a  mov     rcx, r14; hModule
0x18001890d  mov     r13, rax
0x180018910  mov     [rbp+8B0h+var_930], rax
0x180018914  call    cs:__imp_GetProcAddress
0x18001891a  mov     [rsp+9B0h+var_940], rax
0x18001891f  mov     r12, rax
0x180018922  test    rdi, rdi
0x180018925  jz      loc_180018A84
0x18001892b  test    dword ptr [rbx], 20000000h
0x180018931  jz      loc_180018A4A
0x180018937  mov     edx, 6; lpProcName
0x18001893c  mov     rcx, r14; hModule
0x18001893f  call    cs:__imp_GetProcAddress
0x180018945  mov     rsi, rax
0x180018948  test    rax, rax
0x18001894b  jnz     loc_180018A8B
0x180018951  test    r12, r12
0x180018954  jnz     short loc_18001896C
0x180018956  test    r13, r13
0x180018959  jnz     short loc_18001896F
0x18001895b  mov     rbx, [rsp+9B0h+var_970]
0x180018960  lea     r13, aKbdusDll; "kbdus.dll"
0x180018967  jmp     loc_180018804
0x18001896c  xor     r12d, r12d
0x18001896f  mov     rdx, [rbp+8B0h+SourceString]; SourceString
0x180018973  lea     rcx, [rbp+8B0h+DestinationString]; DestinationString
0x180018977  xor     eax, eax
0x180018979  mov     qword ptr [rsp+9B0h+Value], r12
0x18001897e  xorps   xmm0, xmm0
0x180018981  mov     [rbp+8B0h+var_8D0], rax
0x180018985  movups  xmmword ptr [rbp+8B0h+DestinationString.Length], xmm0
0x180018989  mov     [rbp+8B0h+var_8C8], eax
0x18001898c  call    cs:__imp_RtlInitUnicodeString
0x180018992  lea     r8, [rsp+9B0h+Value]; Value
0x180018997  mov     edx, 10h; Base
0x18001899c  lea     rcx, [rbp+8B0h+DestinationString]; String
0x1800189a0  call    cs:__imp_RtlUnicodeStringToInteger
0x1800189a6  mov     rbx, [rsp+9B0h+var_970]
0x1800189ab  test    dword ptr [rbx], 20000000h
0x1800189b1  jz      loc_180018CC6
0x1800189b7  mov     rax, [rsp+9B0h+var_940]
0x1800189bc  test    rax, rax
0x1800189bf  jz      loc_180018CA1
0x1800189c5  mov     rcx, qword ptr [rsp+9B0h+Value]
0x1800189ca  lea     rdx, [rbp+8B0h+LibFileName]
0x1800189ce  xor     r9d, r9d
0x1800189d1  mov     r8, r12
0x1800189d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189d9  xor     r12d, r12d
0x1800189dc  test    eax, eax
0x1800189de  jz      loc_180018CA4
0x1800189e4  mov     rax, gs:60h
0x1800189ed  mov     ebx, [rax+2C0h]
0x1800189f3  call    cs:__imp_WTSGetServiceSessionId
0x1800189f9  cmp     ebx, eax
0x1800189fb  jz      short loc_180018A1A
0x1800189fd  mov     rax, gs:60h
0x180018a06  mov     ebx, [rax+2C0h]
0x180018a0c  call    cs:__imp_RtlGetActiveConsoleId
0x180018a12  cmp     ebx, eax
0x180018a14  jnz     loc_180018D02
0x180018a1a  xor     r8d, r8d; dwFlags
0x180018a1d  lea     rcx, [rbp+8B0h+LibFileName]; lpLibFileName
0x180018a21  xor     edx, edx; hFile
0x180018a23  call    cs:__imp_LoadLibraryExW
0x180018a29  mov     rbx, rax
0x180018a2c  test    rax, rax
0x180018a2f  jz      loc_18001895B
0x180018a35  mov     rcx, r14; hLibModule
0x180018a38  lea     r15, [rbp+8B0h+LibFileName]
0x180018a3c  call    cs:__imp_FreeLibrary
0x180018a42  mov     r14, rbx
0x180018a45  jmp     loc_18001895B
0x180018a4a  mov     rcx, gs:60h
0x180018a53  mov     ebx, [rcx+2C0h]
0x180018a59  call    cs:__imp_WTSGetServiceSessionId
0x180018a5f  cmp     ebx, eax
0x180018a61  jz      loc_180018937
0x180018a67  mov     rax, gs:60h
0x180018a70  mov     ebx, [rax+2C0h]
0x180018a76  call    cs:__imp_RtlGetActiveConsoleId
0x180018a7c  cmp     ebx, eax
0x180018a7e  jz      loc_180018937
0x180018a84  xor     esi, esi
0x180018a86  jmp     loc_180018951
0x180018a8b  mov     rcx, rdi
0x180018a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a93  test    eax, eax
0x180018a95  jz      loc_180018951
0x180018a9b  cmp     dword ptr [rdi], 8
0x180018a9e  jnb     loc_180018D59
0x180018aa4  xor     ebx, ebx
0x180018aa6  cmp     [rdi], ebx
0x180018aa8  jbe     short loc_180018B0D
0x180018aaa  mov     r13, [rsp+9B0h+var_970]
0x180018aaf  lea     rax, [rbx+rbx*8]
0x180018ab3  mov     qword ptr [rsp+9B0h+dwFlagsAndAttributes], 0; struct tagKBDTABLE_MULT_INTERNAL *
0x180018abc  lea     rcx, [rdi+4]
0x180018ac0  mov     [rsp+9B0h+var_968], 0
0x180018ac8  lea     rcx, [rcx+rax*8]; unsigned __int16 *
0x180018acc  mov     [rsp+9B0h+var_964], 0
0x180018ad4  lea     rax, [rsp+9B0h+var_964]
0x180018ad9  mov     r8, r13; unsigned int *
0x180018adc  lea     r9, [rsp+9B0h+var_968]; unsigned int *
0x180018ae1  mov     qword ptr [rsp+9B0h+dwCreationDisposition], rax; unsigned int *
0x180018ae6  xor     edx, edx; unsigned __int16 *
0x180018ae8  call    ?OpenKeyboardLayoutFileWorker@@YAPEAXPEAG0PEBIPEAI2PEAUtagKBDTABLE_MULT_INTERNAL@@@Z; OpenKeyboardLayoutFileWorker(ushort *,ushort *,uint const *,uint *,uint *,tagKBDTABLE_MULT_INTERNAL *)
0x180018aed  mov     edx, ebx
0x180018aef  add     rdx, rdx
0x180018af2  mov     [rdi+rdx*8+288h], rax
0x180018afa  test    rax, rax
0x180018afd  jnz     loc_180018D1E
0x180018b03  inc     ebx
0x180018b05  cmp     ebx, [rdi]
0x180018b07  jb      short loc_180018AAF
0x180018b09  mov     r13, [rbp+8B0h+var_930]
0x180018b0d  mov     ebx, 208h
0x180018b12  lea     rcx, [rbp+8B0h+var_470]; void *
0x180018b19  mov     r8d, ebx; Size
0x180018b1c  xor     edx, edx; Val
0x180018b1e  call    memset_0
0x180018b23  mov     r8d, ebx; Size
0x180018b26  lea     rcx, [rbp+8B0h+var_680]; void *
0x180018b2d  xor     edx, edx; Val
0x180018b2f  call    memset_0
0x180018b34  mov     ebx, 104h
0x180018b39  mov     qword ptr [rsp+9B0h+dwCreationDisposition], 0
0x180018b42  mov     r9d, ebx
0x180018b45  lea     r8, [rbp+8B0h+var_680]
0x180018b4c  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\i8"...
0x180018b53  lea     rcx, aInputsettings; "InputSettings"
0x180018b5a  call    cs:__imp_GetPersistedRegistryLocationW
0x180018b60  lea     rax, [rbp+8B0h+var_680]
0x180018b67  mov     edx, ebx; unsigned __int64
0x180018b69  lea     r9, aRegistryMachin; "\\Registry\\Machine\\"
0x180018b70  mov     qword ptr [rsp+9B0h+dwCreationDisposition], rax
0x180018b75  lea     r8, aSS; "%s%s"
0x180018b7c  lea     rcx, [rbp+8B0h+var_470]; unsigned __int16 *
0x180018b83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018b88  lea     rdx, [rbp+8B0h+var_470]; SourceString
0x180018b8f  lea     rcx, [rsp+9B0h+ValueName]; DestinationString
0x180018b94  call    cs:__imp_RtlInitUnicodeString
0x180018b9a  lea     rax, [rsp+9B0h+ValueName]
0x180018b9f  mov     [rbp+8B0h+ObjectAttributes.Length], 30h ; '0'
0x180018ba6  xorps   xmm0, xmm0
0x180018ba9  mov     [rbp+8B0h+ObjectAttributes.ObjectName], rax
0x180018bad  lea     r8, [rbp+8B0h+ObjectAttributes]; ObjectAttributes
0x180018bb1  mov     [rbp+8B0h+ObjectAttributes.RootDirectory], 0
0x180018bb9  mov     edx, 20019h; DesiredAccess
0x180018bbe  mov     [rbp+8B0h+ObjectAttributes.Attributes], 40h ; '@'
0x180018bc5  lea     rcx, [rsp+9B0h+KeyHandle]; KeyHandle
0x180018bca  movdqu  xmmword ptr [rbp+8B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180018bcf  call    cs:__imp_NtOpenKey
0x180018bd5  test    eax, eax
0x180018bd7  js      loc_180018951
0x180018bdd  lea     rdx, SourceString; "OverrideKeyboardType"
0x180018be4  lea     rcx, [rsp+9B0h+ValueName]; DestinationString
0x180018be9  call    cs:__imp_RtlInitUnicodeString
0x180018bef  mov     rcx, [rsp+9B0h+KeyHandle]; KeyHandle
0x180018bf4  lea     rax, [rsp+9B0h+ResultLength]
0x180018bf9  mov     ebx, 14h
0x180018bfe  mov     qword ptr [rsp+9B0h+dwFlagsAndAttributes], rax; ResultLength
0x180018c03  lea     r9, [rbp+8B0h+KeyValueInformation]; KeyValueInformation
0x180018c07  mov     [rsp+9B0h+dwCreationDisposition], ebx; Length
0x180018c0b  lea     rdx, [rsp+9B0h+ValueName]; ValueName
0x180018c10  lea     r8d, [rbx-12h]; KeyValueInformationClass
0x180018c14  call    cs:__imp_NtQueryValueKey
0x180018c1a  test    eax, eax
0x180018c1c  jns     loc_180018D4B
0x180018c22  cmp     dword ptr [rdi+30Ch], 0
0x180018c29  jz      short loc_180018C72
0x180018c2b  lea     rdx, aOverridekeyboa_0; "OverrideKeyboardSubtype"
0x180018c32  lea     rcx, [rsp+9B0h+ValueName]; DestinationString
0x180018c37  call    cs:__imp_RtlInitUnicodeString
0x180018c3d  mov     rcx, [rsp+9B0h+KeyHandle]; KeyHandle
0x180018c42  lea     rax, [rsp+9B0h+ResultLength]
0x180018c47  mov     qword ptr [rsp+9B0h+dwFlagsAndAttributes], rax; ResultLength
0x180018c4c  lea     r9, [rbp+8B0h+var_8A8]; KeyValueInformation
0x180018c50  mov     r8d, 2; KeyValueInformationClass
0x180018c56  mov     [rsp+9B0h+dwCreationDisposition], ebx; Length
0x180018c5a  lea     rdx, [rsp+9B0h+ValueName]; ValueName
0x180018c5f  call    cs:__imp_NtQueryValueKey
0x180018c65  test    eax, eax
0x180018c67  js      short loc_180018C72
0x180018c69  mov     eax, dword ptr [rbp+8B0h+var_8A8+0Ch]
0x180018c6c  mov     [rdi+310h], eax
0x180018c72  mov     rcx, [rsp+9B0h+KeyHandle]; Handle
  ... truncated ...
```
