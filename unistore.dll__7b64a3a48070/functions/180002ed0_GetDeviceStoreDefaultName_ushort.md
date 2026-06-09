# GetDeviceStoreDefaultName(ushort * *)

- ea: `0x180002ed0`
- end: `0x180002fb6`
- name: `?GetDeviceStoreDefaultName@@YAJPEAPEAG@Z`
- size: `230`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180003598`
- `0x180021fec`

## callees

- `0x180002ed0`
- `0x1800068f0`
- `0x18007b5f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f1b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002ef3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002ef3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002f11`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002f11`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002f58`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002fa3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002f58`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002fa3`
- `UserDataTypeHelperUtil!SafeStrDup` at `0x180002f6f`
- `UserDataTypeHelperUtil!SafeStrDup` at `0x180002f6f`

## string_xrefs

- `0x180002ee8`: `UserDataAccessRes.dll`
- `0x180002f36`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x180002f81`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`

## pseudocode

```c
__int64 __fastcall GetDeviceStoreDefaultName(unsigned __int16 **a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  signed int LastError; // eax
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v9; // eax
  __int64 Buffer; // [rsp+48h] [rbp+10h] BYREF

  Buffer = 0;
  Library = LoadLibraryExW(L"UserDataAccessRes.dll", 0, 2u);
  v3 = Library;
  if ( Library && !LoadStringW(Library, 0x2711u, (LPWSTR)&Buffer, 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    Log_UnistoreHREvent_0(
      v5,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
      1018);
    if ( !v5 )
      Log_AssertionEvent_14(v7, v6, 1018);
LABEL_7:
    FreeLibrary(v3);
    return v5;
  }
  v9 = SafeStrDup(Buffer, 0x7FFFFFFF, a1);
  v5 = v9;
  if ( v9 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v9,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
      1022);
    if ( !v3 )
      return v5;
    goto LABEL_7;
  }
  if ( v3 )
    FreeLibrary(v3);
  return 0;
}

```

## disassembly

```asm
0x180002ed0  mov     [rsp+arg_0], rbx
0x180002ed5  push    rdi
0x180002ed6  sub     rsp, 30h
0x180002eda  xor     edx, edx; hFile
0x180002edc  mov     [rsp+38h+Buffer], 0
0x180002ee5  mov     rdi, rcx
0x180002ee8  lea     rcx, LibFileName; "UserDataAccessRes.dll"
0x180002eef  lea     r8d, [rdx+2]; dwFlags
0x180002ef3  call    cs:__imp_LoadLibraryExW
0x180002ef9  mov     rbx, rax
0x180002efc  test    rax, rax
0x180002eff  jz      short loc_180002F62
0x180002f01  xor     r9d, r9d; cchBufferMax
0x180002f04  lea     r8, [rsp+38h+Buffer]; lpBuffer
0x180002f09  mov     edx, 2711h; uID
0x180002f0e  mov     rcx, rax; hInstance
0x180002f11  call    cs:__imp_LoadStringW
0x180002f17  test    eax, eax
0x180002f19  jnz     short loc_180002F62
0x180002f1b  call    cs:__imp_GetLastError
0x180002f21  mov     edi, eax
0x180002f23  test    eax, eax
0x180002f25  jle     short loc_180002F30
0x180002f27  movzx   edi, ax
0x180002f2a  or      edi, 80070000h
0x180002f30  mov     r9d, 3FAh
0x180002f36  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180002f3d  xor     edx, edx
0x180002f3f  mov     ecx, edi
0x180002f41  call    Log_UnistoreHREvent_0
0x180002f46  test    edi, edi
0x180002f48  jnz     short loc_180002F55
0x180002f4a  mov     r8d, 3FAh
0x180002f50  call    Log_AssertionEvent_14
0x180002f55  mov     rcx, rbx; hLibModule
0x180002f58  call    cs:__imp_FreeLibrary
0x180002f5e  mov     eax, edi
0x180002f60  jmp     short loc_180002FAB
0x180002f62  mov     rcx, [rsp+38h+Buffer]
0x180002f67  mov     r8, rdi
0x180002f6a  mov     edx, 7FFFFFFFh
0x180002f6f  call    cs:__imp_SafeStrDup
0x180002f75  mov     edi, eax
0x180002f77  test    eax, eax
0x180002f79  jns     short loc_180002F9B
0x180002f7b  mov     r9d, 3FEh
0x180002f81  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180002f88  mov     edx, 1
0x180002f8d  mov     ecx, eax
0x180002f8f  call    Log_UnistoreHREvent_0
0x180002f94  test    rbx, rbx
0x180002f97  jz      short loc_180002F5E
0x180002f99  jmp     short loc_180002F55
0x180002f9b  test    rbx, rbx
0x180002f9e  jz      short loc_180002FA9
0x180002fa0  mov     rcx, rbx; hLibModule
0x180002fa3  call    cs:__imp_FreeLibrary
0x180002fa9  xor     eax, eax
0x180002fab  mov     rbx, [rsp+38h+arg_0]
0x180002fb0  add     rsp, 30h
0x180002fb4  pop     rdi
0x180002fb5  retn
```
