# CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)

- ea: `0x18000a8ac`
- end: `0x18000aabc`
- name: `?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007180`
- `0x180007430`
- `0x180007820`
- `0x180008990`
- `0x180008ea0`
- `0x180009170`
- `0x180009380`
- `0x180009960`
- `0x180009bc0`
- `0x18000a090`
- `0x18000a250`

## callees

- `0x180003970`
- `0x1800053ec`
- `0x1800058d0`
- `0x18000a8ac`
- `0x18000c010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000aaa9`
- `KERNEL32!FreeLibrary` at `0x18000aaa9`
- `KERNEL32!GetProcAddress` at `0x18000a9ae`
- `KERNEL32!GetProcAddress` at `0x18000a9ae`
- `KERNEL32!GetLastError` at `0x18000a949`
- `KERNEL32!GetLastError` at `0x18000a986`
- `KERNEL32!GetLastError` at `0x18000a9d8`
- `KERNEL32!GetLastError` at `0x18000aa15`
- `KERNEL32!GetLastError` at `0x18000aa43`
- `KERNEL32!GetLastError` at `0x18000a949`
- `KERNEL32!GetLastError` at `0x18000a986`
- `KERNEL32!GetLastError` at `0x18000a9d8`
- `KERNEL32!GetLastError` at `0x18000aa15`
- `KERNEL32!GetLastError` at `0x18000aa43`
- `KERNEL32!LoadLibraryW` at `0x18000a91c`
- `KERNEL32!LoadLibraryW` at `0x18000a91c`

## string_xrefs

- `0x18000a915`: `userenv.dll`
- `0x18000a9a4`: `GetAppContainerRegistryLocation`

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
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
0x18000a8ac  mov     [rsp+arg_0], rbx
0x18000a8b1  push    rsi
0x18000a8b2  sub     rsp, 30h
0x18000a8b6  mov     rbx, rcx
0x18000a8b9  test    rcx, rcx
0x18000a8bc  jnz     short loc_18000A915
0x18000a8be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8c5  lea     rax, WPP_GLOBAL_Control
0x18000a8cc  cmp     rcx, rax
0x18000a8cf  jz      short loc_18000A90B
0x18000a8d1  test    byte ptr [rcx+1Ch], 8
0x18000a8d5  jz      short loc_18000A90B
0x18000a8d7  cmp     byte ptr [rcx+19h], 2
0x18000a8db  jb      short loc_18000A90B
0x18000a8dd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000a8e2  lea     rcx, aPhkey; "phKey"
0x18000a8e9  mov     r9d, eax
0x18000a8ec  mov     [rsp+38h+var_18], rcx
0x18000a8f1  lea     edx, [rbx+3Ch]
0x18000a8f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8fb  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x18000a902  mov     rcx, [rcx+10h]
0x18000a906  call    WPP_SF_Ds
0x18000a90b  mov     ebx, 80004003h
0x18000a910  jmp     loc_18000AAAF
0x18000a915  lea     rcx, aUserenvDll; "userenv.dll"
0x18000a91c  call    cs:__imp_LoadLibraryW
0x18000a922  mov     rsi, rax
0x18000a925  test    rax, rax
0x18000a928  jnz     short loc_18000A9A4
0x18000a92a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a931  lea     rax, WPP_GLOBAL_Control
0x18000a938  cmp     rcx, rax
0x18000a93b  jz      short loc_18000A986
0x18000a93d  test    byte ptr [rcx+1Ch], 8
0x18000a941  jz      short loc_18000A986
0x18000a943  cmp     byte ptr [rcx+19h], 2
0x18000a947  jb      short loc_18000A986
0x18000a949  call    cs:__imp_GetLastError
0x18000a94f  mov     ebx, eax
0x18000a951  test    eax, eax
0x18000a953  jle     short loc_18000A95E
0x18000a955  movzx   ebx, ax
0x18000a958  or      ebx, 80070000h
0x18000a95e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000a963  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a96a  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x18000a971  mov     edx, 3Dh ; '='
0x18000a976  mov     dword ptr [rsp+38h+var_18], ebx
0x18000a97a  mov     r9d, eax
0x18000a97d  mov     rcx, [rcx+10h]
0x18000a981  call    WPP_SF_Dd
0x18000a986  call    cs:__imp_GetLastError
0x18000a98c  mov     ebx, eax
0x18000a98e  test    eax, eax
0x18000a990  jle     loc_18000AAAF
0x18000a996  movzx   ebx, ax
0x18000a999  or      ebx, 80070000h
0x18000a99f  jmp     loc_18000AAAF
0x18000a9a4  lea     rdx, aGetappcontaine; "GetAppContainerRegistryLocation"
0x18000a9ab  mov     rcx, rsi; hModule
0x18000a9ae  call    cs:__imp_GetProcAddress
0x18000a9b4  test    rax, rax
0x18000a9b7  jnz     short loc_18000AA30
0x18000a9b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9c0  lea     rax, WPP_GLOBAL_Control
0x18000a9c7  cmp     rcx, rax
0x18000a9ca  jz      short loc_18000AA15
0x18000a9cc  test    byte ptr [rcx+1Ch], 8
0x18000a9d0  jz      short loc_18000AA15
0x18000a9d2  cmp     byte ptr [rcx+19h], 2
0x18000a9d6  jb      short loc_18000AA15
0x18000a9d8  call    cs:__imp_GetLastError
0x18000a9de  mov     ebx, eax
0x18000a9e0  test    eax, eax
0x18000a9e2  jle     short loc_18000A9ED
0x18000a9e4  movzx   ebx, ax
0x18000a9e7  or      ebx, 80070000h
0x18000a9ed  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000a9f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9f9  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x18000aa00  mov     edx, 3Eh ; '>'
0x18000aa05  mov     dword ptr [rsp+38h+var_18], ebx
0x18000aa09  mov     r9d, eax
0x18000aa0c  mov     rcx, [rcx+10h]
0x18000aa10  call    WPP_SF_Dd
0x18000aa15  call    cs:__imp_GetLastError
0x18000aa1b  mov     ebx, eax
0x18000aa1d  test    eax, eax
0x18000aa1f  jle     loc_18000AAA6
0x18000aa25  movzx   ebx, ax
0x18000aa28  or      ebx, 80070000h
0x18000aa2e  jmp     short loc_18000AAA6
0x18000aa30  mov     rdx, rbx
0x18000aa33  mov     ecx, 0F003Fh
0x18000aa38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa3d  mov     ebx, eax
0x18000aa3f  test    eax, eax
0x18000aa41  jns     short loc_18000AAA6
0x18000aa43  call    cs:__imp_GetLastError
0x18000aa49  cmp     eax, 7Ah ; 'z'
0x18000aa4c  jz      short loc_18000AAA6
0x18000aa4e  test    eax, eax
0x18000aa50  jg      short loc_18000AA56
0x18000aa52  mov     ebx, eax
0x18000aa54  jmp     short loc_18000AA5F
0x18000aa56  movzx   ebx, ax
0x18000aa59  or      ebx, 80070000h
0x18000aa5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa66  lea     rax, WPP_GLOBAL_Control
0x18000aa6d  cmp     rcx, rax
0x18000aa70  jz      short loc_18000AAA6
0x18000aa72  test    byte ptr [rcx+1Ch], 1
0x18000aa76  jz      short loc_18000AAA6
0x18000aa78  cmp     byte ptr [rcx+19h], 2
0x18000aa7c  jb      short loc_18000AAA6
0x18000aa7e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000aa83  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa8a  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x18000aa91  mov     edx, 3Fh ; '?'
0x18000aa96  mov     dword ptr [rsp+38h+var_18], ebx
0x18000aa9a  mov     r9d, eax
0x18000aa9d  mov     rcx, [rcx+10h]
0x18000aaa1  call    WPP_SF_Dd
0x18000aaa6  mov     rcx, rsi; hLibModule
0x18000aaa9  call    cs:__imp_FreeLibrary
0x18000aaaf  mov     eax, ebx
0x18000aab1  mov     rbx, [rsp+38h+arg_0]
0x18000aab6  add     rsp, 30h
0x18000aaba  pop     rsi
0x18000aabb  retn
```
