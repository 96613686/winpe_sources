# VolumeGetVolumeDriverLetter(ushort const *,ushort * *)

- ea: `0x180011738`
- end: `0x18001185e`
- name: `?VolumeGetVolumeDriverLetter@@YAJPEBGPEAPEAG@Z`
- size: `294`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180006c80`

## callees

- `0x180001384`
- `0x1800054d0`
- `0x180011738`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180011831`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180011831`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800117ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800117ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011810`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800117a8`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180011806`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800117a8`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180011806`

## pseudocode

```c
__int64 __fastcall VolumeGetVolumeDriverLetter(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  void *v4; // rdi
  signed int v5; // ebx
  signed int LastError; // eax
  DWORD cchReturnLength[4]; // [rsp+20h] [rbp-98h] BYREF
  WCHAR szVolumeName[56]; // [rsp+30h] [rbp-88h] BYREF

  memset_0(szVolumeName, 0, 0x64u);
  v4 = 0;
  cchReturnLength[0] = 0;
  v5 = StringCchPrintfW(szVolumeName, 0x32u, L"\\\\?\\%s\\", a1);
  if ( v5 < 0 )
    goto LABEL_13;
  if ( !GetVolumePathNamesForVolumeNameW(szVolumeName, 0, 0, cchReturnLength) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 234 )
      goto LABEL_9;
    v4 = operator new[](saturated_mul(cchReturnLength[0], 2u));
    if ( !v4 )
    {
      v5 = -2147024882;
LABEL_13:
      operator delete[](v4);
      return (unsigned int)v5;
    }
    v5 = 0;
    SetLastError(0);
  }
  if ( GetVolumePathNamesForVolumeNameW(szVolumeName, (LPWCH)v4, cchReturnLength[0], cchReturnLength) )
  {
    *a2 = (unsigned __int16 *)v4;
    goto LABEL_12;
  }
  LastError = GetLastError();
  v5 = LastError;
LABEL_9:
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  if ( v5 < 0 )
    goto LABEL_13;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180011738  mov     [rsp+arg_10], rbx
0x18001173d  mov     [rsp+arg_18], rsi
0x180011742  push    rdi
0x180011743  sub     rsp, 0B0h
0x18001174a  mov     rax, cs:__security_cookie
0x180011751  xor     rax, rsp
0x180011754  mov     [rsp+0B8h+var_18], rax
0x18001175c  mov     rsi, rdx
0x18001175f  mov     rbx, rcx
0x180011762  xor     edx, edx; Val
0x180011764  lea     rcx, [rsp+0B8h+szVolumeName]; void *
0x180011769  lea     r8d, [rdx+64h]; Size
0x18001176d  call    memset_0
0x180011772  xor     edi, edi
0x180011774  lea     r8, aS_2; "\\\\?\\%s\\"
0x18001177b  mov     r9, rbx
0x18001177e  mov     [rsp+0B8h+cchReturnLength], edi
0x180011782  lea     rcx, [rsp+0B8h+szVolumeName]; unsigned __int16 *
0x180011787  lea     edx, [rdi+32h]; unsigned __int64
0x18001178a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001178f  mov     ebx, eax
0x180011791  test    eax, eax
0x180011793  js      loc_18001182E
0x180011799  lea     r9, [rsp+0B8h+cchReturnLength]; lpcchReturnLength
0x18001179e  xor     r8d, r8d; cchBufferLength
0x1800117a1  xor     edx, edx; lpszVolumePathNames
0x1800117a3  lea     rcx, [rsp+0B8h+szVolumeName]; lpszVolumeName
0x1800117a8  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1800117ae  test    eax, eax
0x1800117b0  jnz     short loc_1800117F4
0x1800117b2  call    cs:__imp_GetLastError
0x1800117b8  mov     ebx, eax
0x1800117ba  cmp     eax, 0EAh
0x1800117bf  jnz     short loc_180011818
0x1800117c1  mov     ecx, [rsp+0B8h+cchReturnLength]
0x1800117c5  lea     eax, [rdi+2]
0x1800117c8  mul     rcx
0x1800117cb  lea     rcx, [rdi-1]
0x1800117cf  cmovb   rax, rcx
0x1800117d3  mov     rcx, rax; unsigned __int64
0x1800117d6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800117db  mov     rdi, rax
0x1800117de  test    rax, rax
0x1800117e1  jnz     short loc_1800117EA
0x1800117e3  mov     ebx, 8007000Eh
0x1800117e8  jmp     short loc_18001182E
0x1800117ea  xor     ebx, ebx
0x1800117ec  xor     ecx, ecx; dwErrCode
0x1800117ee  call    cs:__imp_SetLastError
0x1800117f4  mov     r8d, [rsp+0B8h+cchReturnLength]; cchBufferLength
0x1800117f9  lea     r9, [rsp+0B8h+cchReturnLength]; lpcchReturnLength
0x1800117fe  mov     rdx, rdi; lpszVolumePathNames
0x180011801  lea     rcx, [rsp+0B8h+szVolumeName]; lpszVolumeName
0x180011806  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18001180c  test    eax, eax
0x18001180e  jnz     short loc_180011827
0x180011810  call    cs:__imp_GetLastError
0x180011816  mov     ebx, eax
0x180011818  test    eax, eax
0x18001181a  jle     short loc_18001182A
0x18001181c  movzx   ebx, ax
0x18001181f  or      ebx, 80070000h
0x180011825  jmp     short loc_18001182A
0x180011827  mov     [rsi], rdi
0x18001182a  test    ebx, ebx
0x18001182c  jns     short loc_180011837
0x18001182e  mov     rcx, rdi
0x180011831  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180011837  mov     eax, ebx
0x180011839  mov     rcx, [rsp+0B8h+var_18]
0x180011841  xor     rcx, rsp; StackCookie
0x180011844  call    __security_check_cookie
0x180011849  lea     r11, [rsp+0B8h+var_8]
0x180011851  mov     rbx, [r11+20h]
0x180011855  mov     rsi, [r11+28h]
0x180011859  mov     rsp, r11
0x18001185c  pop     rdi
0x18001185d  retn
```
