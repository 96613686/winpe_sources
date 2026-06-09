# CSession::InitializeDeviceEncryption(bool)

- ea: `0x14007c3f8`
- end: `0x14007c574`
- name: `?InitializeDeviceEncryption@CSession@@QEAAX_N@Z`
- size: `380`
- prototype: `void __fastcall(CSession *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14007c988`

## callees

- `0x1400057f4`
- `0x140041c34`
- `0x14007c3f8`
- `0x1400a1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14007c40d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14007c40d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14007c47b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14007c47b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14007c568`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14007c568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007c449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007c4b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007c449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007c4b4`

## string_xrefs

- `0x14007c400`: `fveapi.dll`

## pseudocode

```c
void __fastcall CSession::InitializeDeviceEncryption(CSession *this)
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  DWORD v3; // eax
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  int v6; // eax

  Library = LoadLibraryExW(L"fveapi.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "FveInitializeDeviceEncryption3");
    if ( ProcAddress )
    {
      v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64 *))ProcAddress)(
             0,
             0,
             FVE_GUID_PROV_SCENARIO_WINLOGON_OOBE_IN_EUS);
      if ( v6 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            85,
            WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids,
            (unsigned int)v6);
        }
      }
      else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          84,
          WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids,
          (unsigned int)v6);
      }
    }
    else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, LastError);
    }
    FreeLibrary(v2);
  }
  else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, v3);
  }
}

```

## disassembly

```asm
0x14007c3f8  push    rbx
0x14007c3fa  sub     rsp, 20h
0x14007c3fe  xor     edx, edx; hFile
0x14007c400  lea     rcx, aFveapiDll; "fveapi.dll"
0x14007c407  mov     r8d, 800h; dwFlags
0x14007c40d  call    cs:__imp_LoadLibraryExW
0x14007c413  mov     rbx, rax
0x14007c416  test    rax, rax
0x14007c419  jnz     short loc_14007C471
0x14007c41b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c422  lea     rax, WPP_GLOBAL_Control
0x14007c429  cmp     rcx, rax
0x14007c42c  jz      loc_14007C56E
0x14007c432  test    dword ptr [rcx+1Ch], 1000h
0x14007c439  jz      loc_14007C56E
0x14007c43f  cmp     byte ptr [rcx+19h], 2
0x14007c443  jb      loc_14007C56E
0x14007c449  call    cs:__imp_GetLastError
0x14007c44f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c456  lea     edx, [rbx+52h]
0x14007c459  mov     r9d, eax
0x14007c45c  lea     r8, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids
0x14007c463  mov     rcx, [rcx+10h]
0x14007c467  add     rsp, 20h
0x14007c46b  pop     rbx
0x14007c46c  jmp     WPP_SF_d
0x14007c471  lea     rdx, aFveinitialized; "FveInitializeDeviceEncryption3"
0x14007c478  mov     rcx, rbx; hModule
0x14007c47b  call    cs:__imp_GetProcAddress
0x14007c481  test    rax, rax
0x14007c484  jnz     short loc_14007C4DE
0x14007c486  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c48d  lea     rax, WPP_GLOBAL_Control
0x14007c494  cmp     rcx, rax
0x14007c497  jz      loc_14007C565
0x14007c49d  test    dword ptr [rcx+1Ch], 1000h
0x14007c4a4  jz      loc_14007C565
0x14007c4aa  cmp     byte ptr [rcx+19h], 2
0x14007c4ae  jb      loc_14007C565
0x14007c4b4  call    cs:__imp_GetLastError
0x14007c4ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c4c1  lea     r8, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids
0x14007c4c8  mov     edx, 53h ; 'S'
0x14007c4cd  mov     r9d, eax
0x14007c4d0  mov     rcx, [rcx+10h]
0x14007c4d4  call    WPP_SF_d
0x14007c4d9  jmp     loc_14007C565
0x14007c4de  lea     r8, FVE_GUID_PROV_SCENARIO_WINLOGON_OOBE_IN_EUS
0x14007c4e5  xor     edx, edx
0x14007c4e7  xor     ecx, ecx
0x14007c4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c4ee  mov     r9d, eax
0x14007c4f1  test    eax, eax
0x14007c4f3  jns     short loc_14007C52E
0x14007c4f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c4fc  lea     rax, WPP_GLOBAL_Control
0x14007c503  cmp     rcx, rax
0x14007c506  jz      short loc_14007C565
0x14007c508  test    dword ptr [rcx+1Ch], 1000h
0x14007c50f  jz      short loc_14007C565
0x14007c511  cmp     byte ptr [rcx+19h], 2
0x14007c515  jb      short loc_14007C565
0x14007c517  mov     rcx, [rcx+10h]
0x14007c51b  lea     r8, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids
0x14007c522  mov     edx, 54h ; 'T'
0x14007c527  call    WPP_SF_d
0x14007c52c  jmp     short loc_14007C565
0x14007c52e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c535  lea     rax, WPP_GLOBAL_Control
0x14007c53c  cmp     rcx, rax
0x14007c53f  jz      short loc_14007C565
0x14007c541  test    dword ptr [rcx+1Ch], 1000h
0x14007c548  jz      short loc_14007C565
0x14007c54a  cmp     byte ptr [rcx+19h], 4
0x14007c54e  jb      short loc_14007C565
0x14007c550  mov     rcx, [rcx+10h]
0x14007c554  lea     r8, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids
0x14007c55b  mov     edx, 55h ; 'U'
0x14007c560  call    WPP_SF_
0x14007c565  mov     rcx, rbx; hLibModule
0x14007c568  call    cs:__imp_FreeLibrary
0x14007c56e  add     rsp, 20h
0x14007c572  pop     rbx
0x14007c573  retn
```
