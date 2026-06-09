# SetW32TimeServer(ushort const *)

- ea: `0x180014ebc`
- end: `0x18001500c`
- name: `?SetW32TimeServer@@YAJPEBG@Z`
- size: `336`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x18001493c`

## callees

- `0x1800089c8`
- `0x180013c58`
- `0x180014c14`
- `0x180014ebc`
- `0x180015700`
- `0x1800166b0`
- `0x180028f60`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!SHSetValueW` at `0x180014fc7`
- `SHLWAPI!SHSetValueW` at `0x180014fc7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014fdf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014fdf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014f6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014f6b`

## string_xrefs

- `0x180014f26`: `w32time.DLL`
- `0x180014fc0`: `System\CurrentControlSet\Services\W32Time\Parameters`

## pseudocode

```c
__int64 __fastcall SetW32TimeServer(const unsigned __int16 *a1)
{
  unsigned int v1; // edx
  int v2; // ebx
  HMODULE LibraryW; // rdi
  FARPROC ProcAddress; // rax
  DWORD cbData; // esi
  LSTATUS v6; // eax
  unsigned __int64 v8; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 pvData[264]; // [rsp+40h] [rbp-228h] BYREF

  v2 = StringCchCopyW(pvData, 0x104u, a1);
  if ( v2 >= 0 )
  {
    v2 = AddTerminators(pvData, v1);
    if ( v2 >= 0 )
    {
      v2 = RemoveDuplicateServers(pvData);
      if ( v2 >= 0 )
      {
        v2 = -2147467259;
        LibraryW = IsolationAwareLoadLibraryW(L"w32time.DLL");
        if ( LibraryW )
        {
          v8 = 0;
          v2 = StringCchLengthW(pvData, 0x104u, &v8);
          if ( v2 >= 0 )
          {
            ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0x18);
            if ( ProcAddress )
            {
              cbData = 2 * v8 + 2;
              v2 = ((__int64 (__fastcall *)(__int64, __int64, unsigned __int16 *, _QWORD))ProcAddress)(
                     1,
                     1,
                     pvData,
                     cbData);
              if ( v2 == -2147024769 )
              {
                v6 = SHSetValueW(
                       HKEY_LOCAL_MACHINE,
                       L"System\\CurrentControlSet\\Services\\W32Time\\Parameters",
                       L"NtpServer",
                       1u,
                       pvData,
                       cbData);
                v2 = v6;
                if ( v6 > 0 )
                  v2 = (unsigned __int16)v6 | 0x80070000;
              }
            }
          }
          FreeLibrary(LibraryW);
        }
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180014ebc  mov     [rsp+arg_8], rbx
0x180014ec1  mov     [rsp+arg_10], rsi
0x180014ec6  push    rdi
0x180014ec7  sub     rsp, 260h
0x180014ece  mov     rax, cs:__security_cookie
0x180014ed5  xor     rax, rsp
0x180014ed8  mov     [rsp+268h+var_18], rax
0x180014ee0  mov     r8, rcx; unsigned __int16 *
0x180014ee3  mov     esi, 104h
0x180014ee8  mov     edx, esi; unsigned __int64
0x180014eea  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180014eef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014ef4  mov     ebx, eax
0x180014ef6  test    eax, eax
0x180014ef8  js      loc_180014FE5
0x180014efe  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180014f03  call    ?AddTerminators@@YAJPEAGK@Z; AddTerminators(ushort *,ulong)
0x180014f08  mov     ebx, eax
0x180014f0a  test    eax, eax
0x180014f0c  js      loc_180014FE5
0x180014f12  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180014f17  call    ?RemoveDuplicateServers@@YAJPEAGK@Z; RemoveDuplicateServers(ushort *,ulong)
0x180014f1c  mov     ebx, eax
0x180014f1e  test    eax, eax
0x180014f20  js      loc_180014FE5
0x180014f26  lea     rcx, aW32timeDll; "w32time.DLL"
0x180014f2d  mov     ebx, 80004005h
0x180014f32  call    IsolationAwareLoadLibraryW
0x180014f37  mov     rdi, rax
0x180014f3a  test    rax, rax
0x180014f3d  jz      loc_180014FE5
0x180014f43  lea     r8, [rsp+268h+var_238]; unsigned __int64 *
0x180014f48  mov     [rsp+268h+var_238], 0
0x180014f51  mov     edx, esi; unsigned __int64
0x180014f53  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180014f58  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180014f5d  mov     ebx, eax
0x180014f5f  test    eax, eax
0x180014f61  js      short loc_180014FDC
0x180014f63  mov     edx, 18h; lpProcName
0x180014f68  mov     rcx, rdi; hModule
0x180014f6b  call    cs:__imp_GetProcAddress
0x180014f71  test    rax, rax
0x180014f74  jz      short loc_180014FDC
0x180014f76  mov     ecx, dword ptr [rsp+268h+var_238]
0x180014f7a  lea     r8, [rsp+268h+var_228]
0x180014f7f  mov     edx, 1
0x180014f84  lea     esi, ds:2[rcx*2]
0x180014f8b  mov     ecx, edx
0x180014f8d  mov     r9d, esi
0x180014f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f95  mov     ebx, eax
0x180014f97  cmp     eax, 8007007Fh
0x180014f9c  jnz     short loc_180014FDC
0x180014f9e  lea     rax, [rsp+268h+var_228]
0x180014fa3  mov     [rsp+268h+cbData], esi; cbData
0x180014fa7  mov     r9d, 1; dwType
0x180014fad  mov     [rsp+268h+pvData], rax; pvData
0x180014fb2  lea     r8, aNtpserver; "NtpServer"
0x180014fb9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180014fc0  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\W3"...
0x180014fc7  call    cs:__imp_SHSetValueW
0x180014fcd  mov     ebx, eax
0x180014fcf  test    eax, eax
0x180014fd1  jle     short loc_180014FDC
0x180014fd3  movzx   ebx, ax
0x180014fd6  or      ebx, 80070000h
0x180014fdc  mov     rcx, rdi; hLibModule
0x180014fdf  call    cs:__imp_FreeLibrary
0x180014fe5  mov     eax, ebx
0x180014fe7  mov     rcx, [rsp+268h+var_18]
0x180014fef  xor     rcx, rsp; StackCookie
0x180014ff2  call    __security_check_cookie
0x180014ff7  lea     r11, [rsp+268h+var_8]
0x180014fff  mov     rbx, [r11+18h]
0x180015003  mov     rsi, [r11+20h]
0x180015007  mov     rsp, r11
0x18001500a  pop     rdi
0x18001500b  retn
```
