# AMovieDllRegisterServer2

- ea: `0x180002f68`
- end: `0x18000312a`
- name: `AMovieDllRegisterServer2`
- size: `450`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002cb0`
- `0x180002d00`

## callees

- `0x180001c00`
- `0x180002e08`
- `0x180002f68`
- `0x180003130`
- `0x1800036a0`
- `0x180006494`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180002ffb`
- `KERNEL32!MultiByteToWideChar` at `0x180002ffb`
- `KERNEL32!GetLastError` at `0x180002fad`
- `KERNEL32!GetLastError` at `0x180002fad`
- `KERNEL32!GetModuleFileNameA` at `0x180002fa3`
- `KERNEL32!GetModuleFileNameA` at `0x180002fa3`
- `ole32!CoFreeUnusedLibraries` at `0x1800030ec`
- `ole32!CoFreeUnusedLibraries` at `0x1800030ec`
- `ole32!CoCreateInstance` at `0x18000305a`
- `ole32!CoCreateInstance` at `0x180003084`
- `ole32!CoCreateInstance` at `0x18000305a`
- `ole32!CoCreateInstance` at `0x180003084`
- `ole32!CoInitializeEx` at `0x180003024`
- `ole32!CoInitializeEx` at `0x180003024`
- `ole32!CoUninitialize` at `0x1800030f2`
- `ole32!CoUninitialize` at `0x1800030f2`

## pseudocode

```c
__int64 __fastcall AMovieDllRegisterServer2(unsigned int a1)
{
  unsigned __int64 v2; // rdx
  __int64 result; // rax
  HRESULT v4; // ebx
  __int64 v5; // rdi
  __int64 v6; // rcx
  HRESULT v7; // eax
  LPVOID v8; // rcx
  LPVOID v9; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  CHAR Filename[272]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+150h] [rbp+50h] BYREF

  if ( !GetModuleFileNameA(g_hInst, Filename, 0x104u) )
    return GetLastError() | 0x80070000;
  v9 = 0;
  result = StringCchLengthA(Filename, v2, (unsigned __int64 *)&v9);
  if ( (int)result >= 0 )
  {
    MultiByteToWideChar(0, 0, Filename, (_DWORD)v9 + 1, WideCharStr, 260);
    if ( !a1 || (v4 = RegisterAllServers(WideCharStr, 1), v4 >= 0) )
    {
      CoInitializeEx(0, 2u);
      ppv = 0;
      v9 = 0;
      v4 = CoCreateInstance(&CLSID_FilterMapper2, 0, 1u, &IID_IFilterMapper2, &ppv);
      if ( v4 >= 0 || (v4 = CoCreateInstance(&CLSID_FilterMapper, 0, 1u, &IID_IFilterMapper, &v9), v4 >= 0) )
      {
        v5 = 0;
        do
        {
          v6 = *((_QWORD *)&off_1800D5780 + 5 * v5);
          if ( v6 )
          {
            if ( ppv )
              v7 = AMovieSetupRegisterFilter2(v6, ppv, a1);
            else
              v7 = AMovieSetupRegisterFilter(v6, v9, a1);
            v4 = v7;
          }
          if ( v4 < 0 )
            break;
          v5 = (unsigned int)(v5 + 1);
        }
        while ( (int)v5 < 19 );
        v8 = ppv;
        if ( !ppv )
          v8 = v9;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
      }
      CoFreeUnusedLibraries();
      CoUninitialize();
      if ( v4 >= 0 && !a1 )
        return (unsigned int)RegisterAllServers(WideCharStr, 0);
    }
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x180002f68  push    rbp
0x180002f6a  push    rbx
0x180002f6b  push    rsi
0x180002f6c  push    rdi
0x180002f6d  lea     rbp, [rsp-278h]
0x180002f75  sub     rsp, 378h
0x180002f7c  mov     rax, cs:__security_cookie
0x180002f83  xor     rax, rsp
0x180002f86  mov     [rbp+290h+var_30], rax
0x180002f8d  mov     esi, ecx
0x180002f8f  lea     rdx, [rsp+390h+Filename]; lpFilename
0x180002f94  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x180002f9b  mov     ebx, 104h
0x180002fa0  mov     r8d, ebx; nSize
0x180002fa3  call    cs:__imp_GetModuleFileNameA
0x180002fa9  test    eax, eax
0x180002fab  jnz     short loc_180002FBD
0x180002fad  call    cs:__imp_GetLastError
0x180002fb3  or      eax, 80070000h
0x180002fb8  jmp     loc_18000310F
0x180002fbd  lea     r8, [rsp+390h+var_360]; unsigned __int64 *
0x180002fc2  mov     [rsp+390h+var_360], 0
0x180002fcb  lea     rcx, [rsp+390h+Filename]; char *
0x180002fd0  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180002fd5  test    eax, eax
0x180002fd7  js      loc_18000310F
0x180002fdd  mov     r9d, dword ptr [rsp+390h+var_360]
0x180002fe2  lea     rax, [rbp+290h+WideCharStr]
0x180002fe6  inc     r9d; cbMultiByte
0x180002fe9  mov     [rsp+390h+cchWideChar], ebx; cchWideChar
0x180002fed  lea     r8, [rsp+390h+Filename]; lpMultiByteStr
0x180002ff2  mov     [rsp+390h+lpWideCharStr], rax; lpWideCharStr
0x180002ff7  xor     edx, edx; dwFlags
0x180002ff9  xor     ecx, ecx; CodePage
0x180002ffb  call    cs:__imp_MultiByteToWideChar
0x180003001  test    esi, esi
0x180003003  jz      short loc_18000301D
0x180003005  mov     edx, 1
0x18000300a  lea     rcx, [rbp+290h+WideCharStr]
0x18000300e  call    RegisterAllServers
0x180003013  mov     ebx, eax
0x180003015  test    eax, eax
0x180003017  js      loc_18000310D
0x18000301d  mov     edx, 2; dwCoInit
0x180003022  xor     ecx, ecx; pvReserved
0x180003024  call    cs:__imp_CoInitializeEx
0x18000302a  xor     edx, edx; pUnkOuter
0x18000302c  mov     [rsp+390h+ppv], 0
0x180003035  lea     rax, [rsp+390h+ppv]
0x18000303a  mov     [rsp+390h+var_360], 0
0x180003043  lea     r9, IID_IFilterMapper2; riid
0x18000304a  mov     [rsp+390h+lpWideCharStr], rax; ppv
0x18000304f  lea     rcx, CLSID_FilterMapper2; rclsid
0x180003056  lea     r8d, [rdx+1]; dwClsContext
0x18000305a  call    cs:__imp_CoCreateInstance
0x180003060  mov     ebx, eax
0x180003062  test    eax, eax
0x180003064  jns     short loc_180003090
0x180003066  xor     edx, edx; pUnkOuter
0x180003068  lea     rax, [rsp+390h+var_360]
0x18000306d  lea     r9, IID_IFilterMapper; riid
0x180003074  mov     [rsp+390h+lpWideCharStr], rax; ppv
0x180003079  lea     rcx, CLSID_FilterMapper; rclsid
0x180003080  lea     r8d, [rdx+1]; dwClsContext
0x180003084  call    cs:__imp_CoCreateInstance
0x18000308a  mov     ebx, eax
0x18000308c  test    eax, eax
0x18000308e  js      short loc_1800030EC
0x180003090  xor     edi, edi
0x180003092  lea     rcx, [rdi+rdi*4]
0x180003096  lea     rax, off_1800D5780
0x18000309d  mov     rcx, [rax+rcx*8]
0x1800030a1  test    rcx, rcx
0x1800030a4  jz      short loc_1800030C6
0x1800030a6  mov     rdx, [rsp+390h+ppv]
0x1800030ab  mov     r8d, esi
0x1800030ae  test    rdx, rdx
0x1800030b1  jz      short loc_1800030BA
0x1800030b3  call    AMovieSetupRegisterFilter2
0x1800030b8  jmp     short loc_1800030C4
0x1800030ba  mov     rdx, [rsp+390h+var_360]
0x1800030bf  call    AMovieSetupRegisterFilter
0x1800030c4  mov     ebx, eax
0x1800030c6  test    ebx, ebx
0x1800030c8  js      short loc_1800030D1
0x1800030ca  inc     edi
0x1800030cc  cmp     edi, 13h
0x1800030cf  jl      short loc_180003092
0x1800030d1  mov     rcx, [rsp+390h+ppv]
0x1800030d6  test    rcx, rcx
0x1800030d9  jnz     short loc_1800030E0
0x1800030db  mov     rcx, [rsp+390h+var_360]
0x1800030e0  mov     rax, [rcx]
0x1800030e3  mov     rax, [rax+10h]
0x1800030e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ec  call    cs:__imp_CoFreeUnusedLibraries
0x1800030f2  call    cs:__imp_CoUninitialize
0x1800030f8  test    ebx, ebx
0x1800030fa  js      short loc_18000310D
0x1800030fc  test    esi, esi
0x1800030fe  jnz     short loc_18000310D
0x180003100  xor     edx, edx
0x180003102  lea     rcx, [rbp+290h+WideCharStr]
0x180003106  call    RegisterAllServers
0x18000310b  mov     ebx, eax
0x18000310d  mov     eax, ebx
0x18000310f  mov     rcx, [rbp+290h+var_30]
0x180003116  xor     rcx, rsp; StackCookie
0x180003119  call    __security_check_cookie
0x18000311e  add     rsp, 378h
0x180003125  pop     rdi
0x180003126  pop     rsi
0x180003127  pop     rbx
0x180003128  pop     rbp
0x180003129  retn
```
