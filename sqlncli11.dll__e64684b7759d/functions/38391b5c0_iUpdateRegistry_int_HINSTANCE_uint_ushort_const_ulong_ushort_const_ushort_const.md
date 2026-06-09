# iUpdateRegistry(int,HINSTANCE__ *,uint,ushort const *,ulong,ushort const * *,ushort const * *)

- ea: `0x38391b5c0`
- end: `0x38391b7c3`
- name: `?iUpdateRegistry@@YAJHPEAUHINSTANCE__@@IPEBGKPEAPEBG2@Z`
- size: `515`
- prototype: `int(int, HINSTANCE, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x38391b820`
- `0x38391b880`

## callees

- `0x3838434c0`
- `0x383844d50`
- `0x38391b5c0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x38391b659`
- `KERNEL32!GetModuleHandleW` at `0x38391b659`
- `KERNEL32!GetModuleFileNameW` at `0x38391b60c`
- `KERNEL32!GetModuleFileNameW` at `0x38391b60c`
- `KERNEL32!lstrlenW` at `0x38391b6b2`
- `KERNEL32!lstrlenW` at `0x38391b6b2`
- `KERNEL32!GetShortPathNameW` at `0x38391b675`
- `KERNEL32!GetShortPathNameW` at `0x38391b675`
- `ole32!CoCreateInstance` at `0x38391b644`
- `ole32!CoCreateInstance` at `0x38391b644`

## string_xrefs

- `0x38391b75d`: `REGISTRY`

## pseudocode

```c
HRESULT __fastcall iUpdateRegistry(int a1, HINSTANCE a2, __int64 a3, const unsigned __int16 *a4)
{
  HRESULT result; // eax
  DWORD ShortPathNameW; // eax
  WCHAR *v8; // rbx
  __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  void *v12; // rsp
  void *v13; // rsp
  WCHAR *v14; // rdx
  LPVOID *v15; // rax
  __int64 v16; // rax
  int v17; // eax
  int v18; // ebx
  LPVOID ppv[2]; // [rsp+30h] [rbp+0h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp+10h] BYREF
  WCHAR szShortPath[264]; // [rsp+250h] [rbp+220h] BYREF

  ppv[0] = 0;
  if ( !GetModuleFileNameW(a2, Filename, 0x103u) )
    return -2147467259;
  Filename[259] = 0;
  result = CoCreateInstance(&CLSID_Registrar, 0, 1u, &IID_IRegistrar, ppv);
  if ( result >= 0 )
  {
    if ( a2 && a2 != GetModuleHandleW(0) )
      goto LABEL_12;
    ShortPathNameW = GetShortPathNameW(Filename, szShortPath, 0x104u);
    if ( ShortPathNameW == 260 )
    {
      if ( ppv[0] )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
      return -2147024882;
    }
    if ( !ShortPathNameW || (v8 = szShortPath, ShortPathNameW == 87) )
LABEL_12:
      v8 = Filename;
    v9 = 2 * lstrlenW(v8) + 1;
    v10 = 2 * v9 + 15;
    if ( v10 <= 2 * v9 )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
    v12 = alloca(v11);
    v13 = alloca(v11);
    v14 = v8;
    v15 = ppv;
    if ( v9 )
    {
      while ( *v14 )
      {
        *(_WORD *)v15 = *v14;
        v15 = (LPVOID *)((char *)v15 + 2);
        --v9;
        if ( *v14 == 39 )
        {
          if ( !v9 )
            return -2147024774;
          *(_WORD *)v15 = 39;
          v15 = (LPVOID *)((char *)v15 + 2);
          --v9;
        }
        ++v14;
        if ( !v9 )
          goto LABEL_21;
      }
    }
    else
    {
LABEL_21:
      if ( *v14 )
        return -2147024774;
    }
    if ( v9 )
    {
      *(_WORD *)v15 = 0;
      result = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, LPVOID *))(*(_QWORD *)ppv[0] + 24LL))(
                 ppv[0],
                 L"Module",
                 ppv);
      if ( result >= 0 )
      {
        v16 = *(_QWORD *)ppv[0];
        if ( a1 )
          v17 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64, const wchar_t *))(v16 + 88))(
                  ppv[0],
                  v8,
                  2018,
                  L"REGISTRY");
        else
          v17 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64, const wchar_t *))(v16 + 96))(
                  ppv[0],
                  v8,
                  2018,
                  L"REGISTRY");
        v18 = v17;
        if ( ppv[0] )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
        return v18;
      }
      return result;
    }
    return -2147024774;
  }
  return result;
}

```

## disassembly

```asm
0x38391b5c0  push    rbp
0x38391b5c2  sub     rsp, 470h
0x38391b5c9  lea     rbp, [rsp+30h]
0x38391b5ce  mov     [rbp+440h+arg_0], rbx
0x38391b5d5  mov     [rbp+440h+arg_10], rsi
0x38391b5dc  mov     [rbp+440h+arg_18], rdi
0x38391b5e3  mov     rax, cs:__security_cookie
0x38391b5ea  xor     rax, rbp
0x38391b5ed  mov     [rbp+440h+var_10], rax
0x38391b5f4  mov     rbx, rdx
0x38391b5f7  mov     edi, ecx
0x38391b5f9  lea     rdx, [rbp+440h+Filename]; lpFilename
0x38391b5fd  xor     esi, esi
0x38391b5ff  mov     r8d, 103h; nSize
0x38391b605  mov     rcx, rbx; hModule
0x38391b608  mov     [rbp+440h+var_440], rsi
0x38391b60c  call    cs:__imp_GetModuleFileNameW
0x38391b612  test    eax, eax
0x38391b614  jnz     short loc_38391B620
0x38391b616  mov     eax, 80004005h
0x38391b61b  jmp     loc_38391B796
0x38391b620  xor     edx, edx; pUnkOuter
0x38391b622  lea     rax, [rbp+440h+var_440]
0x38391b626  lea     r9, IID_IRegistrar; riid
0x38391b62d  lea     rcx, CLSID_Registrar; rclsid
0x38391b634  lea     r8d, [rdx+1]; dwClsContext
0x38391b638  mov     [rbp+440h+var_22A], si
0x38391b63f  mov     [rsp+470h+ppv], rax; ppv
0x38391b644  call    cs:__imp_CoCreateInstance
0x38391b64a  test    eax, eax
0x38391b64c  js      loc_38391B796
0x38391b652  test    rbx, rbx
0x38391b655  jz      short loc_38391B664
0x38391b657  xor     ecx, ecx; lpModuleName
0x38391b659  call    cs:__imp_GetModuleHandleW
0x38391b65f  cmp     rbx, rax
0x38391b662  jnz     short loc_38391B6AB
0x38391b664  lea     rdx, [rbp+440h+szShortPath]; lpszShortPath
0x38391b66b  lea     rcx, [rbp+440h+Filename]; lpszLongPath
0x38391b66f  mov     r8d, 104h; cchBuffer
0x38391b675  call    cs:__imp_GetShortPathNameW
0x38391b67b  cmp     eax, 104h
0x38391b680  jnz     short loc_38391B69B
0x38391b682  mov     rcx, [rbp+440h+var_440]
0x38391b686  test    rcx, rcx
0x38391b689  jz      short loc_38391B691
0x38391b68b  mov     rax, [rcx]
0x38391b68e  call    qword ptr [rax+10h]
0x38391b691  mov     eax, 8007000Eh
0x38391b696  jmp     loc_38391B796
0x38391b69b  test    eax, eax
0x38391b69d  jz      short loc_38391B6AB
0x38391b69f  lea     rbx, [rbp+440h+szShortPath]
0x38391b6a6  cmp     eax, 57h ; 'W'
0x38391b6a9  jnz     short loc_38391B6AF
0x38391b6ab  lea     rbx, [rbp+440h+Filename]
0x38391b6af  mov     rcx, rbx; lpString
0x38391b6b2  call    cs:__imp_lstrlenW
0x38391b6b8  lea     eax, ds:1[rax*2]
0x38391b6bf  movsxd  rcx, eax
0x38391b6c2  lea     rax, [rcx+rcx]
0x38391b6c6  lea     rdx, [rax+0Fh]
0x38391b6ca  cmp     rdx, rax
0x38391b6cd  ja      short loc_38391B6D9
0x38391b6cf  mov     rdx, 0FFFFFFFFFFFFFF0h
0x38391b6d9  and     rdx, 0FFFFFFFFFFFFFFF0h
0x38391b6dd  mov     rax, rdx
0x38391b6e0  call    _alloca_probe
0x38391b6e5  sub     rsp, rdx
0x38391b6e8  mov     rdx, rbx
0x38391b6eb  lea     r9, [rsp+470h+var_440]
0x38391b6f0  mov     rax, r9
0x38391b6f3  test    rcx, rcx
0x38391b6f6  jz      short loc_38391B734
0x38391b6f8  mov     r10d, 27h ; '''
0x38391b6fe  xchg    ax, ax
0x38391b700  movzx   r8d, word ptr [rdx]
0x38391b704  test    r8w, r8w
0x38391b708  jz      short loc_38391B739
0x38391b70a  mov     [rax], r8w
0x38391b70e  add     rax, 2
0x38391b712  dec     rcx
0x38391b715  cmp     [rdx], r10w
0x38391b719  jnz     short loc_38391B72B
0x38391b71b  test    rcx, rcx
0x38391b71e  jz      short loc_38391B791
0x38391b720  mov     [rax], r10w
0x38391b724  add     rax, 2
0x38391b728  dec     rcx
0x38391b72b  add     rdx, 2
0x38391b72f  test    rcx, rcx
0x38391b732  jnz     short loc_38391B700
0x38391b734  cmp     [rdx], si
0x38391b737  jnz     short loc_38391B791
0x38391b739  test    rcx, rcx
0x38391b73c  jz      short loc_38391B791
0x38391b73e  mov     [rax], si
0x38391b741  mov     rcx, [rbp+440h+var_440]
0x38391b745  lea     rdx, aModule; "Module"
0x38391b74c  mov     rax, [rcx]
0x38391b74f  mov     r8, r9
0x38391b752  call    qword ptr [rax+18h]
0x38391b755  test    eax, eax
0x38391b757  js      short loc_38391B796
0x38391b759  mov     rcx, [rbp+440h+var_440]
0x38391b75d  lea     r9, aRegistry; "REGISTRY"
0x38391b764  mov     r8d, 7E2h
0x38391b76a  mov     rax, [rcx]
0x38391b76d  mov     rdx, rbx
0x38391b770  test    edi, edi
0x38391b772  jz      short loc_38391B779
0x38391b774  call    qword ptr [rax+58h]
0x38391b777  jmp     short loc_38391B77C
0x38391b779  call    qword ptr [rax+60h]
0x38391b77c  mov     rcx, [rbp+440h+var_440]
0x38391b780  mov     ebx, eax
0x38391b782  test    rcx, rcx
0x38391b785  jz      short loc_38391B78D
0x38391b787  mov     rax, [rcx]
0x38391b78a  call    qword ptr [rax+10h]
0x38391b78d  mov     eax, ebx
0x38391b78f  jmp     short loc_38391B796
0x38391b791  mov     eax, 8007007Ah
0x38391b796  mov     rcx, [rbp+440h+var_10]
0x38391b79d  xor     rcx, rbp; StackCookie
0x38391b7a0  call    __security_check_cookie
0x38391b7a5  mov     rbx, [rbp+440h+arg_0]
0x38391b7ac  mov     rsi, [rbp+440h+arg_10]
0x38391b7b3  mov     rdi, [rbp+440h+arg_18]
0x38391b7ba  lea     rsp, [rbp+440h]
0x38391b7c1  pop     rbp
0x38391b7c2  retn
```
