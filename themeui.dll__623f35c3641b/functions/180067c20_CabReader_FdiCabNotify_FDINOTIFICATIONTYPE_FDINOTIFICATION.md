# CabReader::FdiCabNotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x180067c20`
- end: `0x180067e2c`
- name: `?FdiCabNotify@CabReader@@CA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `524`
- prototype: `INT_PTR __cdecl(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180030f64`
- `0x1800358c0`
- `0x180067c20`
- `0x180068280`
- `0x180068d1c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067d4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067d4c`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180067d1a`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180067d1a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180067cbc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180067cbc`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180067d43`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180067d43`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180067d73`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180067d73`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180067d06`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180067d06`

## pseudocode

```c
INT_PTR __fastcall CabReader::FdiCabNotify(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  INT_PTR result; // rax
  const WCHAR *pv; // rdi
  int v5; // ecx
  int v6; // ecx
  HANDLE FileW; // rbp
  int Error; // ebx
  unsigned __int64 v9; // r9
  bool v10; // zf
  int v11; // eax
  unsigned int (__fastcall *v12)(__int64, unsigned __int16 *, _QWORD, _QWORD); // rax
  __int64 v13; // rcx
  FILETIME CreationTime; // [rsp+40h] [rbp-268h] BYREF
  struct _FILETIME FileTime; // [rsp+48h] [rbp-260h] BYREF
  unsigned __int16 v16[264]; // [rsp+50h] [rbp-258h] BYREF

  result = 0;
  if ( pfdin )
  {
    pv = (const WCHAR *)pfdin->pv;
    if ( pv )
    {
      if ( fdint )
      {
        v5 = fdint - 1;
        if ( v5 )
        {
          v6 = v5 - 1;
          if ( v6 )
          {
            if ( v6 != 1 )
              return result;
            CabReader::FdiFileClose(pfdin->hf);
            FileW = CreateFileW(pv + 790, 0xC0000000, 1u, 0, 3u, 0x80u, 0);
            if ( FileW == (HANDLE)-1LL )
            {
              Error = ResultFromKnownLastError();
              if ( Error < 0 )
                goto LABEL_23;
            }
            else
            {
              Error = 0;
            }
            v10 = (pv[1074] & 1) == 0;
            CreationTime = 0;
            FileTime = 0;
            if ( v10 )
            {
              if ( DosDateTimeToFileTime(pfdin->date, pfdin->time, &FileTime)
                && LocalFileTimeToFileTime(&FileTime, &CreationTime) )
              {
                Error = 0;
LABEL_15:
                SetFileTime(FileW, &CreationTime, 0, &CreationTime);
                goto LABEL_16;
              }
              Error = ResultFromKnownLastError();
              if ( Error >= 0 )
                goto LABEL_15;
            }
LABEL_16:
            if ( !CloseHandle(FileW) )
              Error = ResultFromKnownLastError();
            if ( Error >= 0 && pv[1050] != 128 )
            {
              if ( SetFileAttributesW(pv + 790, pv[1050]) )
                Error = 0;
              else
                Error = ResultFromKnownLastError();
            }
LABEL_23:
            if ( *((_QWORD *)pv + 266) )
            {
              v11 = AnsiToUnicode(0xFDE9u, pfdin->psz1, v16, v9);
              if ( Error < 0 )
              {
                if ( v11 < 0 )
                  return (int)(((Error >> 31) & 0xFFFFFFFE) + 1);
                v12 = (unsigned int (__fastcall *)(__int64, unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)pv + 266);
                if ( !v12 )
                  return (int)(((Error >> 31) & 0xFFFFFFFE) + 1);
                v13 = 3;
                goto LABEL_27;
              }
              if ( v11 >= 0 )
              {
                v12 = (unsigned int (__fastcall *)(__int64, unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)pv + 266);
                v13 = 2;
LABEL_27:
                if ( v12(v13, v16, 0, *((_QWORD *)pv + 267)) == -1 )
                  *((_BYTE *)pv + 2144) = 1;
              }
            }
            return (int)(((Error >> 31) & 0xFFFFFFFE) + 1);
          }
          return (*((__int64 (__fastcall **)(PFDINOTIFICATION))pv + 263))(pfdin);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180067c20  push    rbx
0x180067c22  push    rbp
0x180067c23  push    rsi
0x180067c24  push    rdi
0x180067c25  push    r12
0x180067c27  push    r14
0x180067c29  sub     rsp, 278h
0x180067c30  mov     rax, cs:__security_cookie
0x180067c37  xor     rax, rsp
0x180067c3a  mov     [rsp+2A8h+var_48], rax
0x180067c42  xor     eax, eax
0x180067c44  mov     rsi, rdx
0x180067c47  test    rdx, rdx
0x180067c4a  jz      loc_180067E0C
0x180067c50  mov     rdi, [rdx+20h]
0x180067c54  test    rdi, rdi
0x180067c57  jz      loc_180067E0C
0x180067c5d  test    ecx, ecx
0x180067c5f  jz      loc_180067E0C
0x180067c65  sub     ecx, 1
0x180067c68  jz      loc_180067E0C
0x180067c6e  sub     ecx, 1
0x180067c71  jz      loc_180067DFD
0x180067c77  sub     ecx, 1
0x180067c7a  jnz     loc_180067E0C
0x180067c80  mov     rcx, [rdx+28h]; hf
0x180067c84  call    ?FdiFileClose@CabReader@@CAH_J@Z; CabReader::FdiFileClose(__int64)
0x180067c89  mov     r12d, 80h
0x180067c8f  mov     [rsp+2A8h+hTemplateFile], 0; hTemplateFile
0x180067c98  lea     r14, [rdi+62Ch]
0x180067c9f  mov     [rsp+2A8h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180067ca4  xor     r9d, r9d; lpSecurityAttributes
0x180067ca7  mov     [rsp+2A8h+dwCreationDisposition], 3; dwCreationDisposition
0x180067caf  mov     edx, 0C0000000h; dwDesiredAccess
0x180067cb4  mov     rcx, r14; lpFileName
0x180067cb7  lea     r8d, [r12-7Fh]; dwShareMode
0x180067cbc  call    cs:__imp_CreateFileW
0x180067cc2  mov     rbp, rax
0x180067cc5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180067cc9  jz      short loc_180067CCF
0x180067ccb  xor     ebx, ebx
0x180067ccd  jmp     short loc_180067CDE
0x180067ccf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180067cd4  mov     ebx, eax
0x180067cd6  test    eax, eax
0x180067cd8  js      loc_180067D88
0x180067cde  test    byte ptr [rdi+864h], 1
0x180067ce5  mov     qword ptr [rsp+2A8h+CreationTime.dwLowDateTime], 0
0x180067cee  mov     qword ptr [rsp+2A8h+FileTime.dwLowDateTime], 0
0x180067cf7  jnz     short loc_180067D49
0x180067cf9  movzx   edx, word ptr [rsi+32h]; wFatTime
0x180067cfd  lea     r8, [rsp+2A8h+FileTime]; lpFileTime
0x180067d02  movzx   ecx, word ptr [rsi+30h]; wFatDate
0x180067d06  call    cs:__imp_DosDateTimeToFileTime
0x180067d0c  test    eax, eax
0x180067d0e  jz      short loc_180067D28
0x180067d10  lea     rdx, [rsp+2A8h+CreationTime]; lpFileTime
0x180067d15  lea     rcx, [rsp+2A8h+FileTime]; lpLocalFileTime
0x180067d1a  call    cs:__imp_LocalFileTimeToFileTime
0x180067d20  test    eax, eax
0x180067d22  jz      short loc_180067D28
0x180067d24  xor     ebx, ebx
0x180067d26  jmp     short loc_180067D33
0x180067d28  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180067d2d  mov     ebx, eax
0x180067d2f  test    eax, eax
0x180067d31  js      short loc_180067D49
0x180067d33  lea     r9, [rsp+2A8h+CreationTime]; lpLastWriteTime
0x180067d38  xor     r8d, r8d; lpLastAccessTime
0x180067d3b  lea     rdx, [rsp+2A8h+CreationTime]; lpCreationTime
0x180067d40  mov     rcx, rbp; hFile
0x180067d43  call    cs:__imp_SetFileTime
0x180067d49  mov     rcx, rbp; hObject
0x180067d4c  call    cs:__imp_CloseHandle
0x180067d52  test    eax, eax
0x180067d54  jnz     short loc_180067D5D
0x180067d56  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180067d5b  mov     ebx, eax
0x180067d5d  test    ebx, ebx
0x180067d5f  js      short loc_180067D88
0x180067d61  movzx   eax, word ptr [rdi+834h]
0x180067d68  cmp     ax, r12w
0x180067d6c  jz      short loc_180067D88
0x180067d6e  mov     edx, eax; dwFileAttributes
0x180067d70  mov     rcx, r14; lpFileName
0x180067d73  call    cs:__imp_SetFileAttributesW
0x180067d79  test    eax, eax
0x180067d7b  jz      short loc_180067D81
0x180067d7d  xor     ebx, ebx
0x180067d7f  jmp     short loc_180067D88
0x180067d81  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180067d86  mov     ebx, eax
0x180067d88  cmp     qword ptr [rdi+850h], 0
0x180067d90  jz      short loc_180067DD9
0x180067d92  mov     rdx, [rsi+8]; char *
0x180067d96  lea     r8, [rsp+2A8h+var_258]; unsigned __int16 *
0x180067d9b  mov     ecx, 0FDE9h; unsigned int
0x180067da0  call    ?AnsiToUnicode@@YAJIPEBDPEAG_K@Z; AnsiToUnicode(uint,char const *,ushort *,unsigned __int64)
0x180067da5  test    ebx, ebx
0x180067da7  js      short loc_180067DE6
0x180067da9  test    eax, eax
0x180067dab  js      short loc_180067DD9
0x180067dad  mov     rax, [rdi+850h]
0x180067db4  mov     ecx, 2
0x180067db9  mov     r9, [rdi+858h]
0x180067dc0  lea     rdx, [rsp+2A8h+var_258]
0x180067dc5  xor     r8d, r8d
0x180067dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067dcd  cmp     eax, 0FFFFFFFFh
0x180067dd0  jnz     short loc_180067DD9
0x180067dd2  mov     byte ptr [rdi+860h], 1
0x180067dd9  sar     ebx, 1Fh
0x180067ddc  and     ebx, 0FFFFFFFEh
0x180067ddf  lea     eax, [rbx+1]
0x180067de2  cdqe
0x180067de4  jmp     short loc_180067E0C
0x180067de6  test    eax, eax
0x180067de8  js      short loc_180067DD9
0x180067dea  mov     rax, [rdi+850h]
0x180067df1  test    rax, rax
0x180067df4  jz      short loc_180067DD9
0x180067df6  mov     ecx, 3
0x180067dfb  jmp     short loc_180067DB9
0x180067dfd  mov     rax, [rdi+838h]
0x180067e04  mov     rcx, rsi
0x180067e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e0c  mov     rcx, [rsp+2A8h+var_48]
0x180067e14  xor     rcx, rsp; StackCookie
0x180067e17  call    __security_check_cookie
0x180067e1c  add     rsp, 278h
0x180067e23  pop     r14
0x180067e25  pop     r12
0x180067e27  pop     rdi
0x180067e28  pop     rsi
0x180067e29  pop     rbp
0x180067e2a  pop     rbx
0x180067e2b  retn
```
