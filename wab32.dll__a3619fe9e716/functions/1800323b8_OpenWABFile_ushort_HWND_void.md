# OpenWABFile(ushort *,HWND__ *,void * *)

- ea: `0x1800323b8`
- end: `0x180032580`
- name: `?OpenWABFile@@YAJPEAGPEAUHWND__@@PEAPEAX@Z`
- size: `456`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, HWND, void **)`
- caller_count: `9`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800403d8`
- `0x180040930`
- `0x180040e30`
- `0x1800422c0`
- `0x180042810`
- `0x1800430b0`
- `0x180043290`
- `0x180043df0`
- `0x180043ffc`

## callees

- `0x180030b38`
- `0x180030dd0`
- `0x1800323b8`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x1800324a2`
- `KERNEL32!CopyFileW` at `0x1800324a2`
- `KERNEL32!GetLastError` at `0x18003243d`
- `KERNEL32!GetLastError` at `0x18003243d`
- `KERNEL32!CreateFileW` at `0x180032424`
- `KERNEL32!CreateFileW` at `0x1800324c9`
- `KERNEL32!CreateFileW` at `0x180032534`
- `KERNEL32!CreateFileW` at `0x180032424`
- `KERNEL32!CreateFileW` at `0x1800324c9`
- `KERNEL32!CreateFileW` at `0x180032534`
- `KERNEL32!FindFirstFileW` at `0x180032485`
- `KERNEL32!FindFirstFileW` at `0x180032485`
- `KERNEL32!FindClose` at `0x180032551`
- `KERNEL32!FindClose` at `0x180032551`

## pseudocode

```c
__int64 __fastcall OpenWABFile(WCHAR *lpFileName, HWND a2, void **a3)
{
  HANDLE FileW; // rdi
  unsigned int v6; // ebx
  DWORD LastError; // eax
  unsigned int v8; // r8d
  HANDLE FirstFileW; // rbp
  _BYTE Buffer[176]; // [rsp+40h] [rbp-548h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+F0h] [rbp-498h] BYREF
  WCHAR FileName[264]; // [rsp+340h] [rbp-248h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x10000000u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    v6 = 0;
LABEL_3:
    *a3 = FileW;
    return v6;
  }
  LastError = GetLastError();
  if ( LastError == 5 )
  {
    v6 = -2147024891;
    goto LABEL_3;
  }
  if ( LastError != 2 )
  {
    v6 = -2147467259;
    goto LABEL_3;
  }
  FileName[0] = 0;
  GetWABBackupFileName(lpFileName, FileName, v8);
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL
    || (CopyFileW(FileName, lpFileName, 0),
        FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x10000000u, 0),
        FileW == (HANDLE)-1LL) )
  {
    v6 = -2147467259;
    memset_0(Buffer, 0, 0xA4u);
    if ( (unsigned int)CreateMPSWabFile(Buffer, lpFileName, 0x1F4u, 0x800u) )
    {
      FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x10000000u, 0);
      if ( FileW != (HANDLE)-1LL )
        v6 = 0;
    }
  }
  else
  {
    v6 = 0;
  }
  *a3 = FileW;
  if ( FirstFileW )
    FindClose(FirstFileW);
  return v6;
}

```

## disassembly

```asm
0x1800323b8  mov     [rsp+arg_8], rbx
0x1800323bd  push    rbp
0x1800323be  push    rsi
0x1800323bf  push    rdi
0x1800323c0  push    r12
0x1800323c2  push    r14
0x1800323c4  sub     rsp, 560h
0x1800323cb  mov     rax, cs:__security_cookie
0x1800323d2  xor     rax, rsp
0x1800323d5  mov     [rsp+588h+var_38], rax
0x1800323dd  mov     rsi, r8
0x1800323e0  mov     r14, rcx
0x1800323e3  mov     r8d, 250h; Size
0x1800323e9  lea     rcx, [rsp+588h+FindFileData]; void *
0x1800323f1  xor     edx, edx; Val
0x1800323f3  call    memset_0
0x1800323f8  mov     r12d, 3
0x1800323fe  mov     [rsp+588h+hTemplateFile], 0; hTemplateFile
0x180032407  mov     ebx, 0C0000000h
0x18003240c  mov     [rsp+588h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x180032414  mov     r8d, r12d; dwShareMode
0x180032417  mov     [rsp+588h+dwCreationDisposition], r12d; dwCreationDisposition
0x18003241c  mov     edx, ebx; dwDesiredAccess
0x18003241e  xor     r9d, r9d; lpSecurityAttributes
0x180032421  mov     rcx, r14; lpFileName
0x180032424  call    cs:__imp_CreateFileW
0x18003242a  mov     rdi, rax
0x18003242d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032431  jz      short loc_18003243D
0x180032433  xor     ebx, ebx
0x180032435  mov     [rsi], rdi
0x180032438  jmp     loc_180032557
0x18003243d  call    cs:__imp_GetLastError
0x180032443  cmp     eax, 5
0x180032446  jnz     short loc_18003244F
0x180032448  mov     ebx, 80070005h
0x18003244d  jmp     short loc_180032435
0x18003244f  cmp     eax, 2
0x180032452  jz      short loc_18003245B
0x180032454  mov     ebx, 80004005h
0x180032459  jmp     short loc_180032435
0x18003245b  xor     eax, eax
0x18003245d  lea     rdx, [rsp+588h+FileName]; unsigned __int16 *
0x180032465  mov     rcx, r14; unsigned __int16 *
0x180032468  mov     [rsp+588h+FileName], ax
0x180032470  call    ?GetWABBackupFileName@@YAJPEAG0K@Z; GetWABBackupFileName(ushort *,ushort *,ulong)
0x180032475  lea     rdx, [rsp+588h+FindFileData]; lpFindFileData
0x18003247d  lea     rcx, [rsp+588h+FileName]; lpFileName
0x180032485  call    cs:__imp_FindFirstFileW
0x18003248b  mov     rbp, rax
0x18003248e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032492  jz      short loc_1800324DC
0x180032494  xor     r8d, r8d; bFailIfExists
0x180032497  lea     rcx, [rsp+588h+FileName]; lpExistingFileName
0x18003249f  mov     rdx, r14; lpNewFileName
0x1800324a2  call    cs:__imp_CopyFileW
0x1800324a8  mov     [rsp+588h+hTemplateFile], 0; hTemplateFile
0x1800324b1  xor     r9d, r9d; lpSecurityAttributes
0x1800324b4  mov     [rsp+588h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x1800324bc  mov     r8d, r12d; dwShareMode
0x1800324bf  mov     edx, ebx; dwDesiredAccess
0x1800324c1  mov     [rsp+588h+dwCreationDisposition], r12d; dwCreationDisposition
0x1800324c6  mov     rcx, r14; lpFileName
0x1800324c9  call    cs:__imp_CreateFileW
0x1800324cf  mov     rdi, rax
0x1800324d2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800324d6  jz      short loc_1800324DC
0x1800324d8  xor     ebx, ebx
0x1800324da  jmp     short loc_180032546
0x1800324dc  xor     edx, edx; Val
0x1800324de  lea     rcx, [rsp+588h+Buffer]; void *
0x1800324e3  mov     r8d, 0A4h; Size
0x1800324e9  mov     ebx, 80004005h
0x1800324ee  call    memset_0
0x1800324f3  mov     r9d, 800h; unsigned int
0x1800324f9  lea     rcx, [rsp+588h+Buffer]; lpBuffer
0x1800324fe  mov     r8d, 1F4h; unsigned int
0x180032504  mov     rdx, r14; lpFileName
0x180032507  call    ?CreateMPSWabFile@@YAHPEAU_tagMPSWabFileHeader@@PEAGKK@Z; CreateMPSWabFile(_tagMPSWabFileHeader *,ushort *,ulong,ulong)
0x18003250c  test    eax, eax
0x18003250e  jz      short loc_180032546
0x180032510  mov     [rsp+588h+hTemplateFile], 0; hTemplateFile
0x180032519  xor     r9d, r9d; lpSecurityAttributes
0x18003251c  mov     [rsp+588h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x180032524  mov     r8d, r12d; dwShareMode
0x180032527  mov     edx, 0C0000000h; dwDesiredAccess
0x18003252c  mov     [rsp+588h+dwCreationDisposition], r12d; dwCreationDisposition
0x180032531  mov     rcx, r14; lpFileName
0x180032534  call    cs:__imp_CreateFileW
0x18003253a  xor     ecx, ecx
0x18003253c  mov     rdi, rax
0x18003253f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032543  cmovnz  ebx, ecx
0x180032546  mov     [rsi], rdi
0x180032549  test    rbp, rbp
0x18003254c  jz      short loc_180032557
0x18003254e  mov     rcx, rbp; hFindFile
0x180032551  call    cs:__imp_FindClose
0x180032557  mov     eax, ebx
0x180032559  mov     rcx, [rsp+588h+var_38]
0x180032561  xor     rcx, rsp; StackCookie
0x180032564  call    __security_check_cookie
0x180032569  mov     rbx, [rsp+588h+arg_8]
0x180032571  add     rsp, 560h
0x180032578  pop     r14
0x18003257a  pop     r12
0x18003257c  pop     rdi
0x18003257d  pop     rsi
0x18003257e  pop     rbp
0x18003257f  retn
```
