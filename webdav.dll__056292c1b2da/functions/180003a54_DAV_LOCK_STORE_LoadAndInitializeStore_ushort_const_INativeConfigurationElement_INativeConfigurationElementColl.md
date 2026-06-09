# DAV_LOCK_STORE::LoadAndInitializeStore(ushort const *,INativeConfigurationElement *,INativeConfigurationElementCollection *)

- ea: `0x180003a54`
- end: `0x180003be9`
- name: `?LoadAndInitializeStore@DAV_LOCK_STORE@@AEAAJPEBGPEAVINativeConfigurationElement@@PEAVINativeConfigurationElementCollection@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(DAV_LOCK_STORE *this, const unsigned __int16 *, struct INativeConfigurationElement *, struct INativeConfigurationElementCollection *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180003944`

## callees

- `0x180003a54`
- `0x18001bf60`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b1a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003af6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003af6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003bd0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003bd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003b0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003b0f`

## pseudocode

```c
__int64 __fastcall DAV_LOCK_STORE::LoadAndInitializeStore(
        DAV_LOCK_STORE *this,
        const unsigned __int16 *a2,
        struct INativeConfigurationElement *a3,
        struct INativeConfigurationElementCollection *a4)
{
  int CollectionElement; // eax
  struct INativeConfigurationElement *v7; // rsi
  signed int v8; // ebx
  const wchar_t *v9; // rdx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  _QWORD *v13; // r14
  __int64 v14; // rcx
  HMODULE v15; // rcx
  struct INativeConfigurationElement *v17; // [rsp+30h] [rbp-68h] BYREF
  LPCWSTR lpLibFileName; // [rsp+38h] [rbp-60h] BYREF
  _QWORD v19[11]; // [rsp+40h] [rbp-58h] BYREF

  v17 = 0;
  lpLibFileName = 0;
  CollectionElement = FindCollectionElement(a4, a2, a2, &v17);
  v7 = v17;
  v8 = CollectionElement;
  if ( CollectionElement >= 0 )
  {
    v9 = L"image32";
    if ( !*((_DWORD *)DAV_STATIC_CONFIG::sm_StaticConfig + 29) )
      v9 = L"image";
    v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
           v17,
           v9,
           &lpLibFileName,
           0,
           0);
    if ( v8 >= 0 )
    {
      if ( lpLibFileName && *lpLibFileName )
      {
        Library = LoadLibraryExW(lpLibFileName, 0, 0);
        *((_QWORD *)this + 1) = Library;
        if ( Library && (ProcAddress = GetProcAddress(Library, "RegisterLockStore")) != 0 )
        {
          v19[1] = v7;
          v19[0] = &DAV_PROPERTY_STORE_INITIALIZER::`vftable';
          v13 = (_QWORD *)((char *)this + 16);
          v19[2] = a3;
          v8 = ((__int64 (__fastcall *)(__int64, _QWORD *, char *))ProcAddress)(1, v19, (char *)this + 16);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v13 + 24LL))(*v13, v19);
            if ( v8 >= 0 )
              *((_DWORD *)this + 6) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 40LL))(*v13);
          }
        }
        else
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
        v8 = -2147024809;
      }
    }
  }
  if ( v7 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v8 < 0 )
  {
    v14 = *((_QWORD *)this + 2);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      *((_QWORD *)this + 2) = 0;
    }
    v15 = (HMODULE)*((_QWORD *)this + 1);
    if ( v15 )
    {
      FreeLibrary(v15);
      *((_QWORD *)this + 1) = 0;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003a54  push    rbx
0x180003a56  push    rbp
0x180003a57  push    rsi
0x180003a58  push    rdi
0x180003a59  push    r14
0x180003a5b  push    r15
0x180003a5d  sub     rsp, 68h
0x180003a61  mov     rax, r9
0x180003a64  mov     rbp, r8
0x180003a67  mov     rdi, rcx
0x180003a6a  lea     r9, [rsp+98h+var_68]; struct INativeConfigurationElement **
0x180003a6f  xor     r15d, r15d
0x180003a72  mov     rcx, rax; struct INativeConfigurationElementCollection *
0x180003a75  mov     r8, rdx; unsigned __int16 *
0x180003a78  mov     [rsp+98h+var_68], r15
0x180003a7d  mov     [rsp+98h+lpLibFileName], r15
0x180003a82  call    ?FindCollectionElement@@YAJPEAVINativeConfigurationElementCollection@@PEBG1PEAPEAVINativeConfigurationElement@@@Z; FindCollectionElement(INativeConfigurationElementCollection *,ushort const *,ushort const *,INativeConfigurationElement * *)
0x180003a87  mov     rsi, [rsp+98h+var_68]
0x180003a8c  mov     ebx, eax
0x180003a8e  test    eax, eax
0x180003a90  js      loc_180003B96
0x180003a96  mov     rax, cs:?sm_StaticConfig@DAV_STATIC_CONFIG@@0PEAV1@EA; DAV_STATIC_CONFIG * DAV_STATIC_CONFIG::sm_StaticConfig
0x180003a9d  lea     rcx, aImage; "image"
0x180003aa4  mov     r8, [rsi]
0x180003aa7  lea     rdx, aImage32; "image32"
0x180003aae  mov     [rsp+98h+var_78], r15
0x180003ab3  cmp     [rax+74h], r15d
0x180003ab7  mov     rax, [r8+40h]
0x180003abb  lea     r8, [rsp+98h+lpLibFileName]
0x180003ac0  cmovz   rdx, rcx
0x180003ac4  xor     r9d, r9d
0x180003ac7  mov     rcx, rsi
0x180003aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003acf  mov     ebx, eax
0x180003ad1  test    eax, eax
0x180003ad3  js      loc_180003B96
0x180003ad9  mov     rcx, [rsp+98h+lpLibFileName]; lpLibFileName
0x180003ade  test    rcx, rcx
0x180003ae1  jz      loc_180003B91
0x180003ae7  cmp     [rcx], r15w
0x180003aeb  jz      loc_180003B91
0x180003af1  xor     r8d, r8d; dwFlags
0x180003af4  xor     edx, edx; hFile
0x180003af6  call    cs:__imp_LoadLibraryExW
0x180003afc  mov     [rdi+8], rax
0x180003b00  test    rax, rax
0x180003b03  jz      short loc_180003B1A
0x180003b05  lea     rdx, ProcName; "RegisterLockStore"
0x180003b0c  mov     rcx, rax; hModule
0x180003b0f  call    cs:__imp_GetProcAddress
0x180003b15  test    rax, rax
0x180003b18  jnz     short loc_180003B31
0x180003b1a  call    cs:__imp_GetLastError
0x180003b20  mov     ebx, eax
0x180003b22  test    eax, eax
0x180003b24  jle     short loc_180003B96
0x180003b26  movzx   ebx, ax
0x180003b29  or      ebx, 80070000h
0x180003b2f  jmp     short loc_180003B96
0x180003b31  lea     rcx, ??_7DAV_PROPERTY_STORE_INITIALIZER@@6B@; const DAV_PROPERTY_STORE_INITIALIZER::`vftable'
0x180003b38  mov     [rsp+98h+var_50], rsi
0x180003b3d  mov     [rsp+98h+var_58], rcx
0x180003b42  lea     r14, [rdi+10h]
0x180003b46  mov     ecx, 1
0x180003b4b  mov     [rsp+98h+var_48], rbp
0x180003b50  mov     r8, r14
0x180003b53  lea     rdx, [rsp+98h+var_58]
0x180003b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b5d  mov     ebx, eax
0x180003b5f  test    eax, eax
0x180003b61  js      short loc_180003B96
0x180003b63  mov     rcx, [r14]
0x180003b66  lea     rdx, [rsp+98h+var_58]
0x180003b6b  mov     rax, [rcx]
0x180003b6e  mov     rax, [rax+18h]
0x180003b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b77  mov     ebx, eax
0x180003b79  test    eax, eax
0x180003b7b  js      short loc_180003B96
0x180003b7d  mov     rcx, [r14]
0x180003b80  mov     rax, [rcx]
0x180003b83  mov     rax, [rax+28h]
0x180003b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b8c  mov     [rdi+18h], eax
0x180003b8f  jmp     short loc_180003B96
0x180003b91  mov     ebx, 80070057h
0x180003b96  test    rsi, rsi
0x180003b99  jz      short loc_180003BAA
0x180003b9b  mov     rax, [rsi]
0x180003b9e  mov     rcx, rsi
0x180003ba1  mov     rax, [rax+10h]
0x180003ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003baa  test    ebx, ebx
0x180003bac  jns     short loc_180003BDA
0x180003bae  mov     rcx, [rdi+10h]
0x180003bb2  test    rcx, rcx
0x180003bb5  jz      short loc_180003BC7
0x180003bb7  mov     rax, [rcx]
0x180003bba  mov     rax, [rax+10h]
0x180003bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bc3  mov     [rdi+10h], r15
0x180003bc7  mov     rcx, [rdi+8]; hLibModule
0x180003bcb  test    rcx, rcx
0x180003bce  jz      short loc_180003BDA
0x180003bd0  call    cs:__imp_FreeLibrary
0x180003bd6  mov     [rdi+8], r15
0x180003bda  mov     eax, ebx
0x180003bdc  add     rsp, 68h
0x180003be0  pop     r15
0x180003be2  pop     r14
0x180003be4  pop     rdi
0x180003be5  pop     rsi
0x180003be6  pop     rbp
0x180003be7  pop     rbx
0x180003be8  retn
```
