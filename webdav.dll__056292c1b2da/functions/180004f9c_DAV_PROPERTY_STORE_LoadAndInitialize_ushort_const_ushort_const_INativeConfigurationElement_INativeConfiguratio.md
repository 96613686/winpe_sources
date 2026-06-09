# DAV_PROPERTY_STORE::LoadAndInitialize(ushort const *,ushort const *,INativeConfigurationElement *,INativeConfigurationElement *)

- ea: `0x180004f9c`
- end: `0x18000517d`
- name: `?LoadAndInitialize@DAV_PROPERTY_STORE@@QEAAJPEBG0PEAVINativeConfigurationElement@@1@Z`
- size: `481`
- prototype: `__int64 __fastcall(DAV_PROPERTY_STORE *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct INativeConfigurationElement *, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180005184`

## callees

- `0x180004f9c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050e4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800050a2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800050a2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005164`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005164`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800050d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800050d6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004fda`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004ff1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004fda`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004ff1`

## pseudocode

```c
__int64 __fastcall DAV_PROPERTY_STORE::LoadAndInitialize(
        DAV_PROPERTY_STORE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct INativeConfigurationElement *a4,
        struct INativeConfigurationElement *a5)
{
  signed int v8; // ebx
  LPCWSTR v9; // rcx
  HMODULE Library; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rsi
  signed int v13; // eax
  __int64 v14; // rcx
  HMODULE v15; // rcx
  _QWORD v17[11]; // [rsp+30h] [rbp-58h] BYREF
  LPCWSTR lpLibFileName; // [rsp+90h] [rbp+8h] BYREF

  v17[1] = a4;
  v17[0] = &DAV_PROPERTY_STORE_INITIALIZER::`vftable';
  v17[2] = a5;
  lpLibFileName = 0;
  v8 = STRU::Copy((DAV_PROPERTY_STORE *)((char *)this + 32), a2);
  if ( v8 < 0 )
    goto LABEL_23;
  v8 = STRU::Copy((DAV_PROPERTY_STORE *)((char *)this + 88), a3);
  if ( v8 < 0 )
    goto LABEL_23;
  *(_QWORD *)this = *((_QWORD *)this + 15);
  if ( *((_DWORD *)DAV_STATIC_CONFIG::sm_StaticConfig + 29)
    && (*(int (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)a4 + 64LL))(
         a4,
         L"image32",
         &lpLibFileName,
         0,
         0) < 0
    || (v9 = lpLibFileName) == 0
    || !*lpLibFileName )
  {
    v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)a4 + 64LL))(
           a4,
           L"image",
           &lpLibFileName,
           0,
           0);
    if ( v8 < 0 )
    {
LABEL_23:
      v14 = *((_QWORD *)this + 18);
      if ( v14 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        *((_QWORD *)this + 18) = 0;
      }
      v15 = (HMODULE)*((_QWORD *)this + 3);
      if ( v15 )
      {
        FreeLibrary(v15);
        *((_QWORD *)this + 3) = 0;
      }
      return (unsigned int)v8;
    }
    v9 = lpLibFileName;
  }
  if ( !v9 || !*v9 )
  {
    v8 = -2147024809;
    goto LABEL_23;
  }
  Library = LoadLibraryExW(v9, 0, 0);
  *((_QWORD *)this + 3) = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_23;
  }
  ProcAddress = GetProcAddress(*((HMODULE *)this + 3), "RegisterPropertyStore");
  if ( !ProcAddress )
  {
    v13 = GetLastError();
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_23;
  }
  v8 = ((__int64 (__fastcall *)(__int64, _QWORD *, char *))ProcAddress)(1, v17, (char *)this + 144);
  if ( v8 < 0 )
    goto LABEL_23;
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 18) + 24LL))(*((_QWORD *)this + 18), v17);
  if ( v8 < 0 )
    goto LABEL_23;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004f9c  mov     r11, rsp
0x180004f9f  push    rbx
0x180004fa0  push    rbp
0x180004fa1  push    rsi
0x180004fa2  push    rdi
0x180004fa3  push    r14
0x180004fa5  push    r15
0x180004fa7  sub     rsp, 58h
0x180004fab  lea     rax, ??_7DAV_PROPERTY_STORE_INITIALIZER@@6B@; const DAV_PROPERTY_STORE_INITIALIZER::`vftable'
0x180004fb2  mov     [r11-50h], r9
0x180004fb6  mov     [r11-58h], rax
0x180004fba  mov     rdi, rcx
0x180004fbd  mov     rax, [rsp+88h+arg_20]
0x180004fc5  xor     r15d, r15d
0x180004fc8  add     rcx, 20h ; ' '
0x180004fcc  mov     [r11-48h], rax
0x180004fd0  mov     rsi, r9
0x180004fd3  mov     [r11+8], r15
0x180004fd7  mov     rbp, r8
0x180004fda  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004fe0  mov     ebx, eax
0x180004fe2  test    eax, eax
0x180004fe4  js      loc_18000513C
0x180004fea  lea     rcx, [rdi+58h]
0x180004fee  mov     rdx, rbp
0x180004ff1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004ff7  mov     ebx, eax
0x180004ff9  test    eax, eax
0x180004ffb  js      loc_18000513C
0x180005001  mov     rax, [rdi+78h]
0x180005005  mov     [rdi], rax
0x180005008  mov     rax, cs:?sm_StaticConfig@DAV_STATIC_CONFIG@@0PEAV1@EA; DAV_STATIC_CONFIG * DAV_STATIC_CONFIG::sm_StaticConfig
0x18000500f  cmp     [rax+74h], r15d
0x180005013  jz      short loc_18000503F
0x180005015  mov     rax, [rsi]
0x180005018  lea     r8, [rsp+88h+lpLibFileName]
0x180005020  xor     r9d, r9d
0x180005023  mov     [rsp+88h+var_68], r15
0x180005028  lea     rdx, aImage32; "image32"
0x18000502f  mov     rcx, rsi
0x180005032  mov     rax, [rax+40h]
0x180005036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000503b  test    eax, eax
0x18000503d  js      short loc_180005052
0x18000503f  mov     rcx, [rsp+88h+lpLibFileName]
0x180005047  test    rcx, rcx
0x18000504a  jz      short loc_180005052
0x18000504c  cmp     [rcx], r15w
0x180005050  jnz     short loc_18000508A
0x180005052  mov     rax, [rsi]
0x180005055  lea     r8, [rsp+88h+lpLibFileName]
0x18000505d  xor     r9d, r9d
0x180005060  mov     [rsp+88h+var_68], r15
0x180005065  lea     rdx, aImage; "image"
0x18000506c  mov     rcx, rsi
0x18000506f  mov     rax, [rax+40h]
0x180005073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005078  mov     ebx, eax
0x18000507a  test    eax, eax
0x18000507c  js      loc_18000513C
0x180005082  mov     rcx, [rsp+88h+lpLibFileName]; lpLibFileName
0x18000508a  test    rcx, rcx
0x18000508d  jz      loc_180005137
0x180005093  cmp     [rcx], r15w
0x180005097  jz      loc_180005137
0x18000509d  xor     r8d, r8d; dwFlags
0x1800050a0  xor     edx, edx; hFile
0x1800050a2  call    cs:__imp_LoadLibraryExW
0x1800050a8  mov     [rdi+18h], rax
0x1800050ac  mov     ebp, 80070000h
0x1800050b1  test    rax, rax
0x1800050b4  jnz     short loc_1800050CB
0x1800050b6  call    cs:__imp_GetLastError
0x1800050bc  mov     ebx, eax
0x1800050be  test    eax, eax
0x1800050c0  jle     short loc_1800050C7
0x1800050c2  movzx   ebx, ax
0x1800050c5  or      ebx, ebp
0x1800050c7  test    ebx, ebx
0x1800050c9  js      short loc_18000513C
0x1800050cb  mov     rcx, [rdi+18h]; hModule
0x1800050cf  lea     rdx, aRegisterproper; "RegisterPropertyStore"
0x1800050d6  call    cs:__imp_GetProcAddress
0x1800050dc  mov     rsi, rax
0x1800050df  test    rax, rax
0x1800050e2  jnz     short loc_1800050F9
0x1800050e4  call    cs:__imp_GetLastError
0x1800050ea  mov     ebx, eax
0x1800050ec  test    eax, eax
0x1800050ee  jle     short loc_1800050F5
0x1800050f0  movzx   ebx, ax
0x1800050f3  or      ebx, ebp
0x1800050f5  test    ebx, ebx
0x1800050f7  js      short loc_18000513C
0x1800050f9  lea     r14, [rdi+90h]
0x180005100  mov     ecx, 1
0x180005105  mov     r8, r14
0x180005108  lea     rdx, [rsp+88h+var_58]
0x18000510d  mov     rax, rsi
0x180005110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005115  mov     ebx, eax
0x180005117  test    eax, eax
0x180005119  js      short loc_18000513C
0x18000511b  mov     rcx, [r14]
0x18000511e  lea     rdx, [rsp+88h+var_58]
0x180005123  mov     rax, [rcx]
0x180005126  mov     rax, [rax+18h]
0x18000512a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000512f  mov     ebx, eax
0x180005131  test    eax, eax
0x180005133  jns     short loc_18000516E
0x180005135  jmp     short loc_18000513C
0x180005137  mov     ebx, 80070057h
0x18000513c  mov     rcx, [rdi+90h]
0x180005143  test    rcx, rcx
0x180005146  jz      short loc_18000515B
0x180005148  mov     rax, [rcx]
0x18000514b  mov     rax, [rax+10h]
0x18000514f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005154  mov     [rdi+90h], r15
0x18000515b  mov     rcx, [rdi+18h]; hLibModule
0x18000515f  test    rcx, rcx
0x180005162  jz      short loc_18000516E
0x180005164  call    cs:__imp_FreeLibrary
0x18000516a  mov     [rdi+18h], r15
0x18000516e  mov     eax, ebx
0x180005170  add     rsp, 58h
0x180005174  pop     r15
0x180005176  pop     r14
0x180005178  pop     rdi
0x180005179  pop     rsi
0x18000517a  pop     rbp
0x18000517b  pop     rbx
0x18000517c  retn
```
