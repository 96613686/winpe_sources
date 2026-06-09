# CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)

- ea: `0x180087938`
- end: `0x180087b48`
- name: `?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800816b0`
- `0x180081960`
- `0x180081d60`
- `0x180082870`
- `0x180082d80`
- `0x180083050`
- `0x180083260`
- `0x180083820`
- `0x180083a80`
- `0x180083f50`
- `0x180084110`

## callees

- `0x18000b1d8`
- `0x18000ec94`
- `0x180010ba4`
- `0x180087938`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180087b35`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180087b35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180087a3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180087a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800879d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087acf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800879d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087acf`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800879a8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800879a8`

## string_xrefs

- `0x1800879a1`: `userenv.dll`
- `0x180087a30`: `GetAppContainerRegistryLocation`

## pseudocode

```c
__int64 __fastcall CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY *a1)
{
  unsigned int v2; // eax
  signed int v3; // ebx
  HMODULE LibraryW; // rax
  HMODULE v5; // rsi
  signed int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  signed int v9; // eax
  FARPROC ProcAddress; // rax
  signed int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  signed int v14; // eax
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax

  if ( a1 )
  {
    LibraryW = LoadLibraryW(L"userenv.dll");
    v5 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "GetAppContainerRegistryLocation");
      if ( ProcAddress )
      {
        v3 = ((__int64 (__fastcall *)(__int64, HKEY *))ProcAddress)(983103, a1);
        if ( v3 < 0 )
        {
          LastError = GetLastError();
          if ( LastError != 122 )
          {
            v3 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                63,
                WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
                CurrentThreadActivityIdPrefix,
                v3);
            }
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = GetLastError();
          v12 = v11;
          if ( v11 > 0 )
            v12 = (unsigned __int16)v11 | 0x80070000;
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids, v13, v12);
        }
        v14 = GetLastError();
        v3 = v14;
        if ( v14 > 0 )
          v3 = (unsigned __int16)v14 | 0x80070000;
      }
      FreeLibrary(v5);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = GetLastError();
        v7 = v6;
        if ( v6 > 0 )
          v7 = (unsigned __int16)v6 | 0x80070000;
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids, v8, v7);
      }
      v9 = GetLastError();
      v3 = v9;
      if ( v9 > 0 )
        return (unsigned __int16)v9 | 0x80070000;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
        v2,
        (__int64)"phKey");
    }
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180087938  mov     [rsp+arg_0], rbx
0x18008793d  push    rsi
0x18008793e  sub     rsp, 30h
0x180087942  mov     rbx, rcx
0x180087945  test    rcx, rcx
0x180087948  jnz     short loc_1800879A1
0x18008794a  mov     rcx, cs:WPP_GLOBAL_Control
0x180087951  lea     rax, WPP_GLOBAL_Control
0x180087958  cmp     rcx, rax
0x18008795b  jz      short loc_180087997
0x18008795d  test    byte ptr [rcx+1Ch], 8
0x180087961  jz      short loc_180087997
0x180087963  cmp     byte ptr [rcx+19h], 2
0x180087967  jb      short loc_180087997
0x180087969  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008796e  lea     rcx, aPhkey; "phKey"
0x180087975  mov     r9d, eax
0x180087978  mov     [rsp+38h+var_18], rcx
0x18008797d  lea     edx, [rbx+3Ch]
0x180087980  mov     rcx, cs:WPP_GLOBAL_Control
0x180087987  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x18008798e  mov     rcx, [rcx+10h]
0x180087992  call    WPP_SF_Ds
0x180087997  mov     ebx, 80004003h
0x18008799c  jmp     loc_180087B3B
0x1800879a1  lea     rcx, aUserenvDll; "userenv.dll"
0x1800879a8  call    cs:__imp_LoadLibraryW
0x1800879ae  mov     rsi, rax
0x1800879b1  test    rax, rax
0x1800879b4  jnz     short loc_180087A30
0x1800879b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800879bd  lea     rax, WPP_GLOBAL_Control
0x1800879c4  cmp     rcx, rax
0x1800879c7  jz      short loc_180087A12
0x1800879c9  test    byte ptr [rcx+1Ch], 8
0x1800879cd  jz      short loc_180087A12
0x1800879cf  cmp     byte ptr [rcx+19h], 2
0x1800879d3  jb      short loc_180087A12
0x1800879d5  call    cs:__imp_GetLastError
0x1800879db  mov     ebx, eax
0x1800879dd  test    eax, eax
0x1800879df  jle     short loc_1800879EA
0x1800879e1  movzx   ebx, ax
0x1800879e4  or      ebx, 80070000h
0x1800879ea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800879ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800879f6  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1800879fd  mov     edx, 3Dh ; '='
0x180087a02  mov     dword ptr [rsp+38h+var_18], ebx
0x180087a06  mov     r9d, eax
0x180087a09  mov     rcx, [rcx+10h]
0x180087a0d  call    WPP_SF_Dd
0x180087a12  call    cs:__imp_GetLastError
0x180087a18  mov     ebx, eax
0x180087a1a  test    eax, eax
0x180087a1c  jle     loc_180087B3B
0x180087a22  movzx   ebx, ax
0x180087a25  or      ebx, 80070000h
0x180087a2b  jmp     loc_180087B3B
0x180087a30  lea     rdx, aGetappcontaine; "GetAppContainerRegistryLocation"
0x180087a37  mov     rcx, rsi; hModule
0x180087a3a  call    cs:__imp_GetProcAddress
0x180087a40  test    rax, rax
0x180087a43  jnz     short loc_180087ABC
0x180087a45  mov     rcx, cs:WPP_GLOBAL_Control
0x180087a4c  lea     rax, WPP_GLOBAL_Control
0x180087a53  cmp     rcx, rax
0x180087a56  jz      short loc_180087AA1
0x180087a58  test    byte ptr [rcx+1Ch], 8
0x180087a5c  jz      short loc_180087AA1
0x180087a5e  cmp     byte ptr [rcx+19h], 2
0x180087a62  jb      short loc_180087AA1
0x180087a64  call    cs:__imp_GetLastError
0x180087a6a  mov     ebx, eax
0x180087a6c  test    eax, eax
0x180087a6e  jle     short loc_180087A79
0x180087a70  movzx   ebx, ax
0x180087a73  or      ebx, 80070000h
0x180087a79  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180087a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180087a85  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x180087a8c  mov     edx, 3Eh ; '>'
0x180087a91  mov     dword ptr [rsp+38h+var_18], ebx
0x180087a95  mov     r9d, eax
0x180087a98  mov     rcx, [rcx+10h]
0x180087a9c  call    WPP_SF_Dd
0x180087aa1  call    cs:__imp_GetLastError
0x180087aa7  mov     ebx, eax
0x180087aa9  test    eax, eax
0x180087aab  jle     loc_180087B32
0x180087ab1  movzx   ebx, ax
0x180087ab4  or      ebx, 80070000h
0x180087aba  jmp     short loc_180087B32
0x180087abc  mov     rdx, rbx
0x180087abf  mov     ecx, 0F003Fh
0x180087ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087ac9  mov     ebx, eax
0x180087acb  test    eax, eax
0x180087acd  jns     short loc_180087B32
0x180087acf  call    cs:__imp_GetLastError
0x180087ad5  cmp     eax, 7Ah ; 'z'
0x180087ad8  jz      short loc_180087B32
0x180087ada  test    eax, eax
0x180087adc  jg      short loc_180087AE2
0x180087ade  mov     ebx, eax
0x180087ae0  jmp     short loc_180087AEB
0x180087ae2  movzx   ebx, ax
0x180087ae5  or      ebx, 80070000h
0x180087aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180087af2  lea     rax, WPP_GLOBAL_Control
0x180087af9  cmp     rcx, rax
0x180087afc  jz      short loc_180087B32
0x180087afe  test    byte ptr [rcx+1Ch], 1
0x180087b02  jz      short loc_180087B32
0x180087b04  cmp     byte ptr [rcx+19h], 2
0x180087b08  jb      short loc_180087B32
0x180087b0a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180087b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180087b16  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x180087b1d  mov     edx, 3Fh ; '?'
0x180087b22  mov     dword ptr [rsp+38h+var_18], ebx
0x180087b26  mov     r9d, eax
0x180087b29  mov     rcx, [rcx+10h]
0x180087b2d  call    WPP_SF_Dd
0x180087b32  mov     rcx, rsi; hLibModule
0x180087b35  call    cs:__imp_FreeLibrary
0x180087b3b  mov     eax, ebx
0x180087b3d  mov     rbx, [rsp+38h+arg_0]
0x180087b42  add     rsp, 30h
0x180087b46  pop     rsi
0x180087b47  retn
```
