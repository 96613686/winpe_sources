# UnBCL::Directory::GetTempPathName(void)

- ea: `0x18002d0e0`
- end: `0x18002d3ac`
- name: `?GetTempPathName@Directory@UnBCL@@SAPEAVString@2@XZ`
- size: `716`
- prototype: `struct UnBCL::String *(void)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180029980`
- `0x18003c1a0`

## callees

- `0x18000225c`
- `0x180002f50`
- `0x180002f90`
- `0x180009e7c`
- `0x180011570`
- `0x18002d0e0`
- `0x18002e7d0`
- `0x1800477d0`
- `0x1800498a0`
- `0x18004b0a0`
- `0x18005b790`
- `0x180064340`
- `0x180069020`
- `0x18006f010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18002d16e`
- `KERNEL32!FreeLibrary` at `0x18002d16e`
- `KERNEL32!GetProcAddress` at `0x18002d140`
- `KERNEL32!GetProcAddress` at `0x18002d140`
- `KERNEL32!GetLastError` at `0x18002d2b4`
- `KERNEL32!GetLastError` at `0x18002d370`
- `KERNEL32!GetLastError` at `0x18002d2b4`
- `KERNEL32!GetLastError` at `0x18002d370`
- `KERNEL32!LoadLibraryExA` at `0x18002d123`
- `KERNEL32!LoadLibraryExA` at `0x18002d123`
- `KERNEL32!GetTempPathW` at `0x18002d14b`
- `KERNEL32!GetFileAttributesW` at `0x18002d190`
- `KERNEL32!GetFileAttributesW` at `0x18002d190`

## string_xrefs

- `0x18002d11c`: `kernelbase.dll`
- `0x18002d136`: `GetTempPath2W`
- `0x18002d2ca`: `class UnBCL::String *__cdecl UnBCL::Directory::GetTempPathName(void)`
- `0x18002d316`: `class UnBCL::String *__cdecl UnBCL::Directory::GetTempPathName(void)`
- `0x18002d386`: `class UnBCL::String *__cdecl UnBCL::Directory::GetTempPathName(void)`
- `0x18002d298`: `<temp>`
- `0x18002d304`: `SecureGetTempPathW requires length more than MAX_PATH.`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
struct UnBCL::String *UnBCL::Directory::GetTempPathName(void)
{
  __int64 v0; // rbx
  HMODULE Library; // rax
  HMODULE v2; // rdi
  __int64 (__fastcall *ProcAddress)(__int64, WCHAR *); // rax
  unsigned int v4; // esi
  UnBCL::String *v5; // rax
  __int64 v6; // rax
  struct UnBCL::String *LongName; // rax
  struct UnBCL::String *v8; // rax
  UnBCL::Win32Exception *v10; // rdi
  const struct UnBCL::String *v11; // rbx
  DWORD LastError; // eax
  UnBCL::PathTooLongException *v13; // rax
  UnBCL::Win32Exception *v14; // rdi
  const struct UnBCL::String *v15; // rbx
  DWORD v16; // eax
  int v17[2]; // [rsp+20h] [rbp-288h] BYREF
  struct UnBCL::String *v18; // [rsp+28h] [rbp-280h]
  int v19; // [rsp+30h] [rbp-278h]
  __int64 pExceptionObject; // [rsp+38h] [rbp-270h] BYREF
  __int64 v21; // [rsp+40h] [rbp-268h] BYREF
  __int64 v22; // [rsp+48h] [rbp-260h] BYREF
  _QWORD v23[4]; // [rsp+50h] [rbp-258h] BYREF
  void (__fastcall ***v24)(_QWORD, __int64); // [rsp+70h] [rbp-238h] BYREF
  WCHAR FileName[264]; // [rsp+80h] [rbp-228h] BYREF

  v23[3] = -2;
  v0 = 0;
  v19 = 0;
  Library = LoadLibraryExA("kernelbase.dll", 0, 0x800u);
  v2 = Library;
  *(_QWORD *)v17 = Library;
  if ( !Library
    || (ProcAddress = (__int64 (__fastcall *)(__int64, WCHAR *))GetProcAddress(Library, "GetTempPath2W")) == 0 )
  {
    ProcAddress = (__int64 (__fastcall *)(__int64, WCHAR *))GetTempPathW;
  }
  v4 = ProcAddress(261, FileName);
  if ( v2 )
    FreeLibrary(v2);
  if ( !v4 )
  {
    v10 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    *(_QWORD *)v17 = v10;
    if ( v10 )
    {
      v11 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v23, L"<temp>");
      v19 = 1;
      LastError = GetLastError();
      v0 = UnBCL::Win32Exception::Win32Exception(v10, LastError, v11);
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v0,
                         "class UnBCL::String *__cdecl UnBCL::Directory::GetTempPathName(void)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  if ( v4 > 0x105 )
  {
    v13 = (UnBCL::PathTooLongException *)UnBCL::Object::operator new(0x38u);
    *(_QWORD *)v17 = v13;
    if ( v13 )
      v0 = UnBCL::PathTooLongException::PathTooLongException(
             v13,
             L"SecureGetTempPathW requires length more than MAX_PATH.");
    v21 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v0,
            "class UnBCL::String *__cdecl UnBCL::Directory::GetTempPathName(void)");
    throw (UnBCL::PathTooLongException **)&v21;
  }
  if ( GetFileAttributesW(FileName) == -1 && UnBCL::Directory::MakeSureDirectoryExists(FileName, v17) )
  {
    v14 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    *(_QWORD *)v17 = v14;
    if ( v14 )
    {
      v15 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v23, FileName);
      v19 = 2;
      v16 = GetLastError();
      v0 = UnBCL::Win32Exception::Win32Exception(v14, v16, v15);
    }
    v22 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v0,
            "class UnBCL::String *__cdecl UnBCL::Directory::GetTempPathName(void)");
    throw (UnBCL::Win32Exception **)&v22;
  }
  v5 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  *(_QWORD *)v17 = v5;
  if ( v5 )
    v6 = UnBCL::String::String(v5, FileName);
  else
    v6 = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v17, v6);
  try
  {
    LongName = UnBCL::Path::GetLongName(v18);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v23, LongName);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(v17, v23[1]);
    v23[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v23);
  }
  catch ( UnBCL::Exception *v24 )
  {
    if ( v24 )
      (**v24)(v24, 1);
    v0 = 0;
  }
  v8 = v18;
  if ( v18 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v18 + 2);
    v18 = 0;
    v0 = (__int64)v8;
  }
  *(_QWORD *)v17 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v17);
  return (struct UnBCL::String *)v0;
}

```

## disassembly

```asm
0x18002d0e0  mov     rax, rsp
0x18002d0e3  push    rdi
0x18002d0e4  sub     rsp, 2A0h
0x18002d0eb  mov     [rsp+2A8h+var_240], 0FFFFFFFFFFFFFFFEh
0x18002d0f4  mov     [rax+8], rbx
0x18002d0f8  mov     [rax+10h], rsi
0x18002d0fc  mov     rax, cs:__security_cookie
0x18002d103  xor     rax, rsp
0x18002d106  mov     [rsp+2A8h+var_18], rax
0x18002d10e  xor     ebx, ebx
0x18002d110  mov     [rsp+2A8h+var_278], ebx
0x18002d114  xor     edx, edx; hFile
0x18002d116  mov     r8d, 800h; dwFlags
0x18002d11c  lea     rcx, LibFileName; "kernelbase.dll"
0x18002d123  call    cs:__imp_LoadLibraryExA
0x18002d129  mov     rdi, rax
0x18002d12c  mov     qword ptr [rsp+2A8h+var_288], rax
0x18002d131  test    rax, rax
0x18002d134  jz      short loc_18002D14B
0x18002d136  lea     rdx, ProcName; "GetTempPath2W"
0x18002d13d  mov     rcx, rax; hModule
0x18002d140  call    cs:__imp_GetProcAddress
0x18002d146  test    rax, rax
0x18002d149  jnz     short loc_18002D152
0x18002d14b  mov     rax, cs:__imp_GetTempPathW
0x18002d152  lea     rdx, [rsp+2A8h+FileName]
0x18002d15a  mov     ecx, 105h
0x18002d15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d164  mov     esi, eax
0x18002d166  test    rdi, rdi
0x18002d169  jz      short loc_18002D174
0x18002d16b  mov     rcx, rdi; hLibModule
0x18002d16e  call    cs:__imp_FreeLibrary
0x18002d174  test    esi, esi
0x18002d176  jz      loc_18002D283
0x18002d17c  cmp     esi, 105h
0x18002d182  ja      loc_18002D2F0
0x18002d188  lea     rcx, [rsp+2A8h+FileName]; lpFileName
0x18002d190  call    cs:__imp_GetFileAttributesW
0x18002d196  cmp     eax, 0FFFFFFFFh
0x18002d199  jnz     short loc_18002D1B5
0x18002d19b  lea     rdx, [rsp+2A8h+var_288]; int *
0x18002d1a0  lea     rcx, [rsp+2A8h+FileName]; unsigned __int16 *
0x18002d1a8  call    ?MakeSureDirectoryExists@Directory@UnBCL@@SAKPEBGPEAH@Z; UnBCL::Directory::MakeSureDirectoryExists(ushort const *,int *)
0x18002d1ad  test    eax, eax
0x18002d1af  jnz     loc_18002D33C
0x18002d1b5  mov     ecx, 18h; unsigned __int64
0x18002d1ba  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002d1bf  mov     qword ptr [rsp+2A8h+var_288], rax
0x18002d1c4  test    rax, rax
0x18002d1c7  jz      short loc_18002D1DB
0x18002d1c9  lea     rdx, [rsp+2A8h+FileName]; unsigned __int16 *
0x18002d1d1  mov     rcx, rax; this
0x18002d1d4  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18002d1d9  jmp     short loc_18002D1DE
0x18002d1db  mov     rax, rbx
0x18002d1de  mov     rdx, rax
0x18002d1e1  lea     rcx, [rsp+2A8h+var_288]
0x18002d1e6  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002d1eb  nop
0x18002d1ec  mov     rcx, [rsp+2A8h+var_280]; struct UnBCL::String *
0x18002d1f1  call    ?GetLongName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetLongName(UnBCL::String const *)
0x18002d1f6  mov     rdx, rax
0x18002d1f9  lea     rcx, [rsp+2A8h+var_258]
0x18002d1fe  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002d203  nop
0x18002d204  mov     rdx, [rsp+2A8h+var_250]
0x18002d209  lea     rcx, [rsp+2A8h+var_288]
0x18002d20e  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002d213  nop
0x18002d214  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002d21b  mov     [rsp+2A8h+var_258], rdi
0x18002d220  lea     rcx, [rsp+2A8h+var_258]
0x18002d225  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002d22a  nop
0x18002d22b  jmp     short loc_18002D236
0x18002d22d  xor     ebx, ebx
0x18002d22f  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002d236  mov     rax, [rsp+2A8h+var_280]
0x18002d23b  test    rax, rax
0x18002d23e  jz      short loc_18002D24C
0x18002d240  lock dec dword ptr [rax+8]
0x18002d244  mov     [rsp+2A8h+var_280], rbx
0x18002d249  mov     rbx, rax
0x18002d24c  mov     qword ptr [rsp+2A8h+var_288], rdi
0x18002d251  lea     rcx, [rsp+2A8h+var_288]
0x18002d256  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002d25b  mov     rax, rbx
0x18002d25e  mov     rcx, [rsp+2A8h+var_18]
0x18002d266  xor     rcx, rsp; StackCookie
0x18002d269  call    __security_check_cookie
0x18002d26e  lea     r11, [rsp+2A8h+var_8]
0x18002d276  mov     rbx, [r11+10h]
0x18002d27a  mov     rsi, [r11+18h]
0x18002d27e  mov     rsp, r11
0x18002d281  pop     rdi
0x18002d282  retn
0x18002d283  lea     ecx, [rsi+40h]; unsigned __int64
0x18002d286  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002d28b  mov     rdi, rax
0x18002d28e  mov     qword ptr [rsp+2A8h+var_288], rax
0x18002d293  test    rax, rax
0x18002d296  jz      short loc_18002D2CA
0x18002d298  lea     rdx, aTemp; "<temp>"
0x18002d29f  lea     rcx, [rsp+2A8h+var_258]; this
0x18002d2a4  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18002d2a9  mov     rbx, rax
0x18002d2ac  mov     [rsp+2A8h+var_278], 1
0x18002d2b4  call    cs:__imp_GetLastError
0x18002d2ba  mov     r8, rbx; struct UnBCL::String *
0x18002d2bd  mov     edx, eax; dwMessageId
0x18002d2bf  mov     rcx, rdi; this
0x18002d2c2  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x18002d2c7  mov     rbx, rax
0x18002d2ca  lea     rdx, aClassUnbclStri_29; "class UnBCL::String *__cdecl UnBCL::Dir"...
0x18002d2d1  mov     rcx, rbx
0x18002d2d4  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002d2d9  mov     [rsp+2A8h+pExceptionObject], rax
0x18002d2de  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18002d2e5  lea     rcx, [rsp+2A8h+pExceptionObject]; pExceptionObject
0x18002d2ea  call    _CxxThrowException_0
0x18002d2f0  mov     ecx, 38h ; '8'; unsigned __int64
0x18002d2f5  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002d2fa  mov     qword ptr [rsp+2A8h+var_288], rax
0x18002d2ff  test    rax, rax
0x18002d302  jz      short loc_18002D316
0x18002d304  lea     rdx, aSecuregettempp; "SecureGetTempPathW requires length more"...
0x18002d30b  mov     rcx, rax; this
0x18002d30e  call    ??0PathTooLongException@UnBCL@@QEAA@PEBG@Z; UnBCL::PathTooLongException::PathTooLongException(ushort const *)
0x18002d313  mov     rbx, rax
0x18002d316  lea     rdx, aClassUnbclStri_29; "class UnBCL::String *__cdecl UnBCL::Dir"...
0x18002d31d  mov     rcx, rbx
0x18002d320  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002d325  mov     [rsp+2A8h+var_268], rax
0x18002d32a  lea     rdx, _TI5PEAVPathTooLongException@UnBCL@@; pThrowInfo
0x18002d331  lea     rcx, [rsp+2A8h+var_268]; pExceptionObject
0x18002d336  call    _CxxThrowException_0
0x18002d33c  mov     ecx, 40h ; '@'; unsigned __int64
0x18002d341  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002d346  mov     rdi, rax
0x18002d349  mov     qword ptr [rsp+2A8h+var_288], rax
0x18002d34e  test    rax, rax
0x18002d351  jz      short loc_18002D386
0x18002d353  lea     rdx, [rsp+2A8h+FileName]; unsigned __int16 *
0x18002d35b  lea     rcx, [rsp+2A8h+var_258]; this
0x18002d360  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18002d365  mov     rbx, rax
0x18002d368  mov     [rsp+2A8h+var_278], 2
0x18002d370  call    cs:__imp_GetLastError
0x18002d376  mov     r8, rbx; struct UnBCL::String *
0x18002d379  mov     edx, eax; dwMessageId
0x18002d37b  mov     rcx, rdi; this
0x18002d37e  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x18002d383  mov     rbx, rax
0x18002d386  lea     rdx, aClassUnbclStri_29; "class UnBCL::String *__cdecl UnBCL::Dir"...
0x18002d38d  mov     rcx, rbx
0x18002d390  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002d395  mov     [rsp+2A8h+var_260], rax
0x18002d39a  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18002d3a1  lea     rcx, [rsp+2A8h+var_260]; pExceptionObject
0x18002d3a6  call    _CxxThrowException_0
```
