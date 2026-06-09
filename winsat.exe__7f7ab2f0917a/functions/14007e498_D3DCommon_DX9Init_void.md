# D3DCommon::DX9Init(void)

- ea: `0x14007e498`
- end: `0x14007e674`
- name: `?DX9Init@D3DCommon@@YAJXZ`
- size: `476`
- prototype: `__int64 __fastcall(D3DCommon *__hidden this)`
- caller_count: `5`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f3cc`
- `0x14003c484`
- `0x140047084`
- `0x14004dcec`
- `0x1400852f0`

## callees

- `0x140004348`
- `0x14000449c`
- `0x140005cf4`
- `0x14000695c`
- `0x140016d04`
- `0x140017af0`
- `0x14003f698`
- `0x14007e498`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14007e59e`
- `KERNEL32!GetProcAddress` at `0x14007e5f7`
- `KERNEL32!GetProcAddress` at `0x14007e59e`
- `KERNEL32!GetProcAddress` at `0x14007e5f7`
- `KERNEL32!GetTickCount` at `0x14007e50c`
- `KERNEL32!GetTickCount` at `0x14007e531`
- `KERNEL32!GetTickCount` at `0x14007e50c`
- `KERNEL32!GetTickCount` at `0x14007e531`
- `KERNEL32!LoadLibraryW` at `0x14007e564`
- `KERNEL32!LoadLibraryW` at `0x14007e564`
- `KERNEL32!GetLastError` at `0x14007e576`
- `KERNEL32!GetLastError` at `0x14007e576`
- `KERNEL32!Sleep` at `0x14007e52b`
- `KERNEL32!Sleep` at `0x14007e52b`

## string_xrefs

- `0x14007e55d`: `d3d9.dll`
- `0x14007e4ed`: `D3DCommon::DX9Init`
- `0x14007e5e9`: `Direct3DCreate9`
- `0x14007e594`: `Direct3DCreate9Ex`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall D3DCommon::DX9Init(D3DCommon *this)
{
  mlib::MUILoader *v1; // rax
  __int64 *v2; // rax
  __int64 *v3; // rax
  DWORD v4; // ebx
  unsigned int v6; // ebx
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  __int64 v10; // rax
  FARPROC v11; // rax
  _BYTE v12[56]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int64 *v13; // [rsp+70h] [rbp+8h] BYREF

  if ( D3DCommon::g_bVerbose && D3DCommon::g_phStdOut )
  {
    v1 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v12, 101);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      (__int64 *)&v13,
      (__int64)v1);
    v2 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
           (__int64 *)(D3DCommon::g_phStdOut + 240),
           &v13);
    v3 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v2, (__int64)L"D3DCommon::DX9Init");
    std::endl(v3);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v13);
  }
  v4 = GetTickCount() + 10000;
  while ( _InterlockedCompareExchange(&dword_1401CBA20, 1, 0) )
  {
    Sleep(1u);
    if ( GetTickCount() >= v4 )
      return 2147500037LL;
  }
  if ( !qword_1401CBA60 )
  {
    LibraryW = LoadLibraryW(L"d3d9.dll");
    hLibModule = LibraryW;
    if ( !LibraryW )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_22;
    }
    ProcAddress = GetProcAddress(LibraryW, "Direct3DCreate9Ex");
    if ( ProcAddress && ((int (__fastcall *)(__int64, __int64 *))ProcAddress)(32, &qword_1401CBA80) >= 0 )
    {
      (**(void (__fastcall ***)(__int64, GUID *, __int64 *))qword_1401CBA80)(
        qword_1401CBA80,
        &IID_IDirect3D9,
        &qword_1401CBA60);
      v10 = qword_1401CBA60;
    }
    else
    {
      v11 = GetProcAddress(hLibModule, "Direct3DCreate9");
      if ( !v11 )
      {
        v6 = -2147467262;
        goto LABEL_22;
      }
      v10 = ((__int64 (__fastcall *)(__int64))v11)(32);
      qword_1401CBA60 = v10;
    }
    if ( v10
      || (v6 = -2147467262,
          Record_FailingHresult_w(
            "base\\winsat\\d3d\\dx9base.cpp",
            507,
            2147500034LL,
            L"Failed querying interface.",
            &qword_14012B318),
          qword_1401CBA60) )
    {
      v6 = 0;
      _InterlockedAdd(&dword_1401CBA30, 1u);
    }
    goto LABEL_22;
  }
  _InterlockedAdd(&dword_1401CBA30, 1u);
  v6 = 0;
LABEL_22:
  _InterlockedCompareExchange(&dword_1401CBA20, 0, 1);
  return v6;
}

```

## disassembly

```asm
0x14007e498  mov     [rsp+arg_8], rbx
0x14007e49d  push    rsi
0x14007e49e  sub     rsp, 60h
0x14007e4a2  cmp     cs:?g_bVerbose@D3DCommon@@3_NA, 0; bool D3DCommon::g_bVerbose
0x14007e4a9  jz      short loc_14007E50C
0x14007e4ab  cmp     cs:?g_phStdOut@D3DCommon@@3PEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@EA, 0; mlib::handle_ostreamT<ushort,std::char_traits<ushort>> * D3DCommon::g_phStdOut
0x14007e4b3  jz      short loc_14007E50C
0x14007e4b5  mov     edx, 65h ; 'e'; unsigned __int16
0x14007e4ba  lea     rcx, [rsp+68h+var_38]; this
0x14007e4bf  call    ??0MUILoader@mlib@@QEAA@G@Z; mlib::MUILoader::MUILoader(ushort)
0x14007e4c4  mov     rdx, rax
0x14007e4c7  lea     rcx, [rsp+68h+arg_0]
0x14007e4cc  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x14007e4d1  nop
0x14007e4d2  mov     rcx, cs:?g_phStdOut@D3DCommon@@3PEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@EA; mlib::handle_ostreamT<ushort,std::char_traits<ushort>> * D3DCommon::g_phStdOut
0x14007e4d9  add     rcx, 0F0h
0x14007e4e0  lea     rdx, [rsp+68h+arg_0]
0x14007e4e5  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007e4ea  mov     rcx, rax
0x14007e4ed  lea     rdx, aD3dcommonDx9in; "D3DCommon::DX9Init"
0x14007e4f4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007e4f9  mov     rcx, rax
0x14007e4fc  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14007e501  nop
0x14007e502  lea     rcx, [rsp+68h+arg_0]
0x14007e507  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14007e50c  call    cs:__imp_GetTickCount
0x14007e512  lea     ebx, [rax+2710h]
0x14007e518  mov     esi, 1
0x14007e51d  xor     eax, eax
0x14007e51f  lock cmpxchg cs:dword_1401CBA20, esi
0x14007e527  jz      short loc_14007E545
0x14007e529  mov     ecx, esi; dwMilliseconds
0x14007e52b  call    cs:__imp_Sleep
0x14007e531  call    cs:__imp_GetTickCount
0x14007e537  cmp     eax, ebx
0x14007e539  jb      short loc_14007E51D
0x14007e53b  mov     eax, 80004005h
0x14007e540  jmp     loc_14007E669
0x14007e545  cmp     cs:qword_1401CBA60, 0
0x14007e54d  jz      short loc_14007E55D
0x14007e54f  lock add cs:dword_1401CBA30, esi
0x14007e556  xor     ebx, ebx
0x14007e558  jmp     loc_14007E65B
0x14007e55d  lea     rcx, aD3d9Dll_0; "d3d9.dll"
0x14007e564  call    cs:__imp_LoadLibraryW
0x14007e56a  mov     cs:hLibModule, rax
0x14007e571  test    rax, rax
0x14007e574  jnz     short loc_14007E594
0x14007e576  call    cs:__imp_GetLastError
0x14007e57c  mov     ebx, eax
0x14007e57e  test    eax, eax
0x14007e580  jle     loc_14007E65B
0x14007e586  movzx   ebx, ax
0x14007e589  or      ebx, 80070000h
0x14007e58f  jmp     loc_14007E65B
0x14007e594  lea     rdx, aDirect3dcreate_0; "Direct3DCreate9Ex"
0x14007e59b  mov     rcx, rax; hModule
0x14007e59e  call    cs:__imp_GetProcAddress
0x14007e5a4  mov     ebx, 20h ; ' '
0x14007e5a9  test    rax, rax
0x14007e5ac  jz      short loc_14007E5E9
0x14007e5ae  lea     rdx, qword_1401CBA80
0x14007e5b5  mov     ecx, ebx
0x14007e5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e5bc  test    eax, eax
0x14007e5be  js      short loc_14007E5E9
0x14007e5c0  mov     rcx, cs:qword_1401CBA80
0x14007e5c7  mov     rax, [rcx]
0x14007e5ca  lea     r8, qword_1401CBA60
0x14007e5d1  lea     rdx, IID_IDirect3D9
0x14007e5d8  mov     rax, [rax]
0x14007e5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e5e0  mov     rax, cs:qword_1401CBA60
0x14007e5e7  jmp     short loc_14007E617
0x14007e5e9  lea     rdx, aDirect3dcreate; "Direct3DCreate9"
0x14007e5f0  mov     rcx, cs:hLibModule; hModule
0x14007e5f7  call    cs:__imp_GetProcAddress
0x14007e5fd  test    rax, rax
0x14007e600  jnz     short loc_14007E609
0x14007e602  mov     ebx, 80004002h
0x14007e607  jmp     short loc_14007E65B
0x14007e609  mov     ecx, ebx
0x14007e60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e610  mov     cs:qword_1401CBA60, rax
0x14007e617  test    rax, rax
0x14007e61a  jnz     short loc_14007E652
0x14007e61c  lea     rax, qword_14012B318
0x14007e623  mov     [rsp+68h+var_48], rax
0x14007e628  lea     r9, aFailedQuerying; "Failed querying interface."
0x14007e62f  mov     ebx, 80004002h
0x14007e634  mov     r8d, ebx
0x14007e637  mov     edx, 1FBh
0x14007e63c  lea     rcx, aBaseWinsatD3dD; "base\\winsat\\d3d\\dx9base.cpp"
0x14007e643  call    Record_FailingHresult_w
0x14007e648  cmp     cs:qword_1401CBA60, 0
0x14007e650  jz      short loc_14007E65B
0x14007e652  xor     ebx, ebx
0x14007e654  lock add cs:dword_1401CBA30, esi
0x14007e65b  xor     ecx, ecx
0x14007e65d  mov     eax, esi
0x14007e65f  lock cmpxchg cs:dword_1401CBA20, ecx
0x14007e667  mov     eax, ebx
0x14007e669  mov     rbx, [rsp+68h+arg_8]
0x14007e66e  add     rsp, 60h
0x14007e672  pop     rsi
0x14007e673  retn
```
