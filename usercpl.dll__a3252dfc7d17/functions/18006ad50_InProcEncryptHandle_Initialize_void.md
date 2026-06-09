# InProcEncryptHandle::_Initialize(void)

- ea: `0x18006ad50`
- end: `0x18006aec8`
- name: `?_Initialize@InProcEncryptHandle@@EEAAJXZ`
- size: `376`
- prototype: `__int64 __fastcall(InProcEncryptHandle *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18006a608`
- `0x18006ad50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006ad68`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006ad68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ad9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006adb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006adc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006adda`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006adef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ae04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ae19`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ae2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ad9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006adb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006adc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006adda`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006adef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ae04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ae19`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ae2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ad77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ad77`

## string_xrefs

- `0x18006ad91`: `FveOpenVolumeW`
- `0x18006ad5b`: `fveapi.dll`
- `0x18006ad83`: `LoadLibraryExW`
- `0x18006ae8e`: `onecore\ds\security\eas\policyengine\extnlib\encrypthandler.cxx`
- `0x18006ae0e`: `FveUpdateDeviceLockoutState`

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
    &Class);
  if ( (int)v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return v6;
}

```

## disassembly

```asm
0x18006ad50  push    rbx
0x18006ad52  sub     rsp, 40h
0x18006ad56  mov     rbx, rcx
0x18006ad59  xor     edx, edx; hFile
0x18006ad5b  lea     rcx, aFveapiDll; "fveapi.dll"
0x18006ad62  mov     r8d, 800h; dwFlags
0x18006ad68  call    cs:__imp_LoadLibraryExW
0x18006ad6e  mov     [rbx+48h], rax
0x18006ad72  test    rax, rax
0x18006ad75  jnz     short loc_18006AD91
0x18006ad77  call    cs:__imp_GetLastError
0x18006ad7d  mov     r8d, 89h
0x18006ad83  lea     r10, aLoadlibraryexw; "LoadLibraryExW"
0x18006ad8a  mov     ebx, eax
0x18006ad8c  jmp     loc_18006AE82
0x18006ad91  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x18006ad98  mov     rcx, rax; hModule
0x18006ad9b  call    cs:__imp_GetProcAddress
0x18006ada1  mov     rcx, [rbx+48h]; hModule
0x18006ada5  lea     rdx, aFveisdeviceloc; "FveIsDeviceLockable"
0x18006adac  mov     [rbx+8], rax
0x18006adb0  call    cs:__imp_GetProcAddress
0x18006adb6  mov     rcx, [rbx+48h]; hModule
0x18006adba  lea     rdx, aFvegetdevicelo; "FveGetDeviceLockoutData"
0x18006adc1  mov     [rbx+10h], rax
0x18006adc5  call    cs:__imp_GetProcAddress
0x18006adcb  mov     rcx, [rbx+48h]; hModule
0x18006adcf  lea     rdx, aFvevalidatedev; "FveValidateDeviceLockoutState"
0x18006add6  mov     [rbx+18h], rax
0x18006adda  call    cs:__imp_GetProcAddress
0x18006ade0  mov     rcx, [rbx+48h]; hModule
0x18006ade4  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x18006adeb  mov     [rbx+30h], rax
0x18006adef  call    cs:__imp_GetProcAddress
0x18006adf5  mov     rcx, [rbx+48h]; hModule
0x18006adf9  lea     rdx, aFvelockdevice; "FveLockDevice"
0x18006ae00  mov     [rbx+20h], rax
0x18006ae04  call    cs:__imp_GetProcAddress
0x18006ae0a  mov     rcx, [rbx+48h]; hModule
0x18006ae0e  lea     rdx, aFveupdatedevic; "FveUpdateDeviceLockoutState"
0x18006ae15  mov     [rbx+28h], rax
0x18006ae19  call    cs:__imp_GetProcAddress
0x18006ae1f  mov     rcx, [rbx+48h]; hModule
0x18006ae23  lea     rdx, aFvedisabledevi; "FveDisableDeviceLockoutState"
0x18006ae2a  mov     [rbx+38h], rax
0x18006ae2e  call    cs:__imp_GetProcAddress
0x18006ae34  cmp     qword ptr [rbx+8], 0
0x18006ae39  mov     [rbx+40h], rax
0x18006ae3d  jz      short loc_18006AE70
0x18006ae3f  cmp     qword ptr [rbx+10h], 0
0x18006ae44  jz      short loc_18006AE70
0x18006ae46  cmp     qword ptr [rbx+18h], 0
0x18006ae4b  jz      short loc_18006AE70
0x18006ae4d  cmp     qword ptr [rbx+30h], 0
0x18006ae52  jz      short loc_18006AE70
0x18006ae54  cmp     qword ptr [rbx+20h], 0
0x18006ae59  jz      short loc_18006AE70
0x18006ae5b  cmp     qword ptr [rbx+28h], 0
0x18006ae60  jz      short loc_18006AE70
0x18006ae62  cmp     qword ptr [rbx+38h], 0
0x18006ae67  jz      short loc_18006AE70
0x18006ae69  xor     ebx, ebx
0x18006ae6b  test    rax, rax
0x18006ae6e  jnz     short loc_18006AEC0
0x18006ae70  mov     ebx, 54Fh
0x18006ae75  lea     r10, aMissingFveFunc; "Missing FVE functions"
0x18006ae7c  mov     r8d, 0BAh
0x18006ae82  lea     rax, Class
0x18006ae89  mov     ecx, 1; unsigned int
0x18006ae8e  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x18006ae95  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006ae9c  mov     [rsp+48h+var_18], rax
0x18006aea1  mov     [rsp+48h+var_20], r10
0x18006aea6  mov     [rsp+48h+var_28], r8d
0x18006aeab  mov     r8d, ebx
0x18006aeae  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006aeb3  test    ebx, ebx
0x18006aeb5  jle     short loc_18006AEC0
0x18006aeb7  movzx   ebx, bx
0x18006aeba  or      ebx, 80070000h
0x18006aec0  mov     eax, ebx
0x18006aec2  add     rsp, 40h
0x18006aec6  pop     rbx
0x18006aec7  retn
```
