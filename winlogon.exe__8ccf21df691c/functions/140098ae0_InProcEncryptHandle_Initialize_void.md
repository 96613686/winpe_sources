# InProcEncryptHandle::_Initialize(void)

- ea: `0x140098ae0`
- end: `0x140098c58`
- name: `?_Initialize@InProcEncryptHandle@@EEAAJXZ`
- size: `376`
- prototype: `__int64 __fastcall(InProcEncryptHandle *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140038250`
- `0x140098ae0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140098af8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140098af8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098b2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098b40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098b55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098b6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098b7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098b94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098ba9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098bbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098b2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098b40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098b55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098b6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098b7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098b94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098ba9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140098b07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140098b07`

## string_xrefs

- `0x140098aeb`: `fveapi.dll`
- `0x140098c1e`: `onecore\ds\security\eas\policyengine\extnlib\encrypthandler.cxx`
- `0x140098b21`: `FveOpenVolumeW`
- `0x140098b13`: `LoadLibraryExW`
- `0x140098b9e`: `FveUpdateDeviceLockoutState`

## pseudocode

```c
__int64 __fastcall InProcEncryptHandle::_Initialize(InProcEncryptHandle *this)
{
  HMODULE Library; // rax
  DWORD LastError; // eax
  int v4; // r8d
  const wchar_t *v5; // r10
  unsigned int v6; // ebx
  FARPROC ProcAddress; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  HMODULE v10; // rcx
  FARPROC v11; // rax
  HMODULE v12; // rcx
  FARPROC v13; // rax
  HMODULE v14; // rcx
  FARPROC v15; // rax
  HMODULE v16; // rcx
  FARPROC v17; // rax
  HMODULE v18; // rcx
  FARPROC v19; // rax
  HMODULE v20; // rcx
  FARPROC v21; // rax
  bool v22; // zf
  int v24; // [rsp+20h] [rbp-28h]

  Library = LoadLibraryExW(L"fveapi.dll", 0, 0x800u);
  *((_QWORD *)this + 9) = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "FveOpenVolumeW");
    v8 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 1) = ProcAddress;
    v9 = GetProcAddress(v8, "FveIsDeviceLockable");
    v10 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 2) = v9;
    v11 = GetProcAddress(v10, "FveGetDeviceLockoutData");
    v12 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 3) = v11;
    v13 = GetProcAddress(v12, "FveValidateDeviceLockoutState");
    v14 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 6) = v13;
    v15 = GetProcAddress(v14, "FveCloseVolume");
    v16 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 4) = v15;
    v17 = GetProcAddress(v16, "FveLockDevice");
    v18 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 5) = v17;
    v19 = GetProcAddress(v18, "FveUpdateDeviceLockoutState");
    v20 = (HMODULE)*((_QWORD *)this + 9);
    *((_QWORD *)this + 7) = v19;
    v21 = GetProcAddress(v20, "FveDisableDeviceLockoutState");
    v22 = *((_QWORD *)this + 1) == 0;
    *((_QWORD *)this + 8) = v21;
    if ( !v22 )
    {
      if ( *((_QWORD *)this + 2) )
      {
        if ( *((_QWORD *)this + 3) )
        {
          if ( *((_QWORD *)this + 6) )
          {
            if ( *((_QWORD *)this + 4) )
            {
              if ( *((_QWORD *)this + 5) )
              {
                if ( *((_QWORD *)this + 7) )
                {
                  v6 = 0;
                  if ( v21 )
                    return v6;
                }
              }
            }
          }
        }
      }
    }
    v6 = 1359;
    v5 = L"Missing FVE functions";
    v4 = 186;
  }
  else
  {
    LastError = GetLastError();
    v4 = 137;
    v5 = L"LoadLibraryExW";
    v6 = LastError;
  }
  v24 = v4;
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    v6,
    L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\encrypthandler.cxx",
    v24,
    v5,
    &pPassword);
  if ( (int)v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return v6;
}

```

## disassembly

```asm
0x140098ae0  push    rbx
0x140098ae2  sub     rsp, 40h
0x140098ae6  mov     rbx, rcx
0x140098ae9  xor     edx, edx; hFile
0x140098aeb  lea     rcx, aFveapiDll; "fveapi.dll"
0x140098af2  mov     r8d, 800h; dwFlags
0x140098af8  call    cs:__imp_LoadLibraryExW
0x140098afe  mov     [rbx+48h], rax
0x140098b02  test    rax, rax
0x140098b05  jnz     short loc_140098B21
0x140098b07  call    cs:__imp_GetLastError
0x140098b0d  mov     r8d, 89h
0x140098b13  lea     r10, aLoadlibraryexw; "LoadLibraryExW"
0x140098b1a  mov     ebx, eax
0x140098b1c  jmp     loc_140098C12
0x140098b21  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x140098b28  mov     rcx, rax; hModule
0x140098b2b  call    cs:__imp_GetProcAddress
0x140098b31  mov     rcx, [rbx+48h]; hModule
0x140098b35  lea     rdx, aFveisdeviceloc; "FveIsDeviceLockable"
0x140098b3c  mov     [rbx+8], rax
0x140098b40  call    cs:__imp_GetProcAddress
0x140098b46  mov     rcx, [rbx+48h]; hModule
0x140098b4a  lea     rdx, aFvegetdevicelo; "FveGetDeviceLockoutData"
0x140098b51  mov     [rbx+10h], rax
0x140098b55  call    cs:__imp_GetProcAddress
0x140098b5b  mov     rcx, [rbx+48h]; hModule
0x140098b5f  lea     rdx, aFvevalidatedev; "FveValidateDeviceLockoutState"
0x140098b66  mov     [rbx+18h], rax
0x140098b6a  call    cs:__imp_GetProcAddress
0x140098b70  mov     rcx, [rbx+48h]; hModule
0x140098b74  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x140098b7b  mov     [rbx+30h], rax
0x140098b7f  call    cs:__imp_GetProcAddress
0x140098b85  mov     rcx, [rbx+48h]; hModule
0x140098b89  lea     rdx, aFvelockdevice; "FveLockDevice"
0x140098b90  mov     [rbx+20h], rax
0x140098b94  call    cs:__imp_GetProcAddress
0x140098b9a  mov     rcx, [rbx+48h]; hModule
0x140098b9e  lea     rdx, aFveupdatedevic; "FveUpdateDeviceLockoutState"
0x140098ba5  mov     [rbx+28h], rax
0x140098ba9  call    cs:__imp_GetProcAddress
0x140098baf  mov     rcx, [rbx+48h]; hModule
0x140098bb3  lea     rdx, aFvedisabledevi; "FveDisableDeviceLockoutState"
0x140098bba  mov     [rbx+38h], rax
0x140098bbe  call    cs:__imp_GetProcAddress
0x140098bc4  cmp     qword ptr [rbx+8], 0
0x140098bc9  mov     [rbx+40h], rax
0x140098bcd  jz      short loc_140098C00
0x140098bcf  cmp     qword ptr [rbx+10h], 0
0x140098bd4  jz      short loc_140098C00
0x140098bd6  cmp     qword ptr [rbx+18h], 0
0x140098bdb  jz      short loc_140098C00
0x140098bdd  cmp     qword ptr [rbx+30h], 0
0x140098be2  jz      short loc_140098C00
0x140098be4  cmp     qword ptr [rbx+20h], 0
0x140098be9  jz      short loc_140098C00
0x140098beb  cmp     qword ptr [rbx+28h], 0
0x140098bf0  jz      short loc_140098C00
0x140098bf2  cmp     qword ptr [rbx+38h], 0
0x140098bf7  jz      short loc_140098C00
0x140098bf9  xor     ebx, ebx
0x140098bfb  test    rax, rax
0x140098bfe  jnz     short loc_140098C50
0x140098c00  mov     ebx, 54Fh
0x140098c05  lea     r10, aMissingFveFunc; "Missing FVE functions"
0x140098c0c  mov     r8d, 0BAh
0x140098c12  lea     rax, pPassword
0x140098c19  mov     ecx, 1; unsigned int
0x140098c1e  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x140098c25  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140098c2c  mov     [rsp+48h+var_18], rax
0x140098c31  mov     [rsp+48h+var_20], r10
0x140098c36  mov     [rsp+48h+var_28], r8d
0x140098c3b  mov     r8d, ebx
0x140098c3e  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140098c43  test    ebx, ebx
0x140098c45  jle     short loc_140098C50
0x140098c47  movzx   ebx, bx
0x140098c4a  or      ebx, 80070000h
0x140098c50  mov     eax, ebx
0x140098c52  add     rsp, 40h
0x140098c56  pop     rbx
0x140098c57  retn
```
