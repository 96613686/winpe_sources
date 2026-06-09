# DavRestoreEncryptedFile

- ea: `0x18001bbe0`
- end: `0x18001bd6b`
- name: `DavRestoreEncryptedFile`
- size: `395`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180016d24`

## callees

- `0x18000b81c`
- `0x18000ba14`
- `0x18001bbe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc6c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001bc5d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001bc5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd40`
- `ADVAPI32!WriteEncryptedFileRaw` at `0x18001bcf4`
- `ADVAPI32!WriteEncryptedFileRaw` at `0x18001bcf4`
- `ADVAPI32!CloseEncryptedFileRaw` at `0x18001bd50`
- `ADVAPI32!CloseEncryptedFileRaw` at `0x18001bd50`
- `ADVAPI32!OpenEncryptedFileRawW` at `0x18001bcbd`
- `ADVAPI32!OpenEncryptedFileRawW` at `0x18001bcbd`

## pseudocode

```c
__int64 __fastcall DavRestoreEncryptedFile(LPCWSTR lpFileName, LPCWSTR a2)
{
  HANDLE FileW; // rbp
  DWORD LastError; // eax
  unsigned int v6; // ebx
  DWORD v7; // eax
  _QWORD *v8; // rcx
  int v9; // edx
  DWORD v10; // r9d
  DWORD v11; // eax
  PVOID pvContext; // [rsp+70h] [rbp+18h] BYREF

  pvContext = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      223,
      (unsigned int)WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
      (_DWORD)lpFileName,
      (__int64)a2);
  FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 3u, 0x20u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    v7 = OpenEncryptedFileRawW(a2, 1u, &pvContext);
    v6 = v7;
    if ( v7 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v9 = 225;
      v10 = v7;
    }
    else
    {
      v11 = WriteEncryptedFileRaw(DavWriteRawCallback, FileW, pvContext);
      v6 = v11;
      if ( v11 == 1917 )
      {
        v6 = 5;
      }
      else if ( !v11 )
      {
LABEL_19:
        CloseHandle(FileW);
        goto LABEL_20;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v9 = 226;
      v10 = v6;
    }
    WPP_SF_dS(v8[2], v9, (unsigned int)WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v10, (__int64)a2);
    goto LABEL_19;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      224,
      (unsigned int)WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
      LastError,
      (__int64)lpFileName);
LABEL_20:
  if ( pvContext )
    CloseEncryptedFileRaw(pvContext);
  return v6;
}

```

## disassembly

```asm
0x18001bbe0  mov     rax, rsp
0x18001bbe3  mov     [rax+8], rbx
0x18001bbe7  mov     [rax+10h], rbp
0x18001bbeb  push    rsi
0x18001bbec  push    rdi
0x18001bbed  push    r14
0x18001bbef  sub     rsp, 40h
0x18001bbf3  mov     rsi, rdx
0x18001bbf6  mov     qword ptr [rax+18h], 0
0x18001bbfe  mov     rdi, rcx
0x18001bc01  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc08  lea     r14, WPP_GLOBAL_Control
0x18001bc0f  cmp     rcx, r14
0x18001bc12  jz      short loc_18001BC36
0x18001bc14  test    byte ptr [rcx+1Ch], 2
0x18001bc18  jz      short loc_18001BC36
0x18001bc1a  mov     rcx, [rcx+10h]
0x18001bc1e  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x18001bc25  mov     edx, 0DFh
0x18001bc2a  mov     [rax-38h], rsi
0x18001bc2e  mov     r9, rdi
0x18001bc31  call    WPP_SF_SS
0x18001bc36  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18001bc3f  xor     r9d, r9d; lpSecurityAttributes
0x18001bc42  mov     [rsp+58h+dwFlagsAndAttributes], 20h ; ' '; dwFlagsAndAttributes
0x18001bc4a  xor     r8d, r8d; dwShareMode
0x18001bc4d  mov     edx, 0C0000000h; dwDesiredAccess
0x18001bc52  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18001bc5a  mov     rcx, rdi; lpFileName
0x18001bc5d  call    cs:__imp_CreateFileW
0x18001bc63  mov     rbp, rax
0x18001bc66  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bc6a  jnz     short loc_18001BCB0
0x18001bc6c  call    cs:__imp_GetLastError
0x18001bc72  mov     ebx, eax
0x18001bc74  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc7b  cmp     rcx, r14
0x18001bc7e  jz      loc_18001BD46
0x18001bc84  test    byte ptr [rcx+1Ch], 1
0x18001bc88  jz      loc_18001BD46
0x18001bc8e  mov     rcx, [rcx+10h]
0x18001bc92  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x18001bc99  mov     edx, 0E0h
0x18001bc9e  mov     qword ptr [rsp+58h+dwCreationDisposition], rdi
0x18001bca3  mov     r9d, eax
0x18001bca6  call    WPP_SF_dS
0x18001bcab  jmp     loc_18001BD46
0x18001bcb0  lea     r8, [rsp+58h+pvContext]; pvContext
0x18001bcb5  mov     edx, 1; ulFlags
0x18001bcba  mov     rcx, rsi; lpFileName
0x18001bcbd  call    cs:__imp_OpenEncryptedFileRawW
0x18001bcc3  mov     ebx, eax
0x18001bcc5  test    eax, eax
0x18001bcc7  jz      short loc_18001BCE5
0x18001bcc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcd0  cmp     rcx, r14
0x18001bcd3  jz      short loc_18001BD3D
0x18001bcd5  test    byte ptr [rcx+1Ch], 1
0x18001bcd9  jz      short loc_18001BD3D
0x18001bcdb  mov     edx, 0E1h
0x18001bce0  mov     r9d, eax
0x18001bce3  jmp     short loc_18001BD28
0x18001bce5  mov     r8, [rsp+58h+pvContext]; pvContext
0x18001bcea  lea     rcx, DavWriteRawCallback; pfImportCallback
0x18001bcf1  mov     rdx, rbp; pvCallbackContext
0x18001bcf4  call    cs:__imp_WriteEncryptedFileRaw
0x18001bcfa  mov     ebx, eax
0x18001bcfc  cmp     eax, 77Dh
0x18001bd01  jnz     short loc_18001BD0A
0x18001bd03  mov     ebx, 5
0x18001bd08  jmp     short loc_18001BD0E
0x18001bd0a  test    eax, eax
0x18001bd0c  jz      short loc_18001BD3D
0x18001bd0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd15  cmp     rcx, r14
0x18001bd18  jz      short loc_18001BD3D
0x18001bd1a  test    byte ptr [rcx+1Ch], 1
0x18001bd1e  jz      short loc_18001BD3D
0x18001bd20  mov     edx, 0E2h
0x18001bd25  mov     r9d, ebx
0x18001bd28  mov     rcx, [rcx+10h]
0x18001bd2c  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x18001bd33  mov     qword ptr [rsp+58h+dwCreationDisposition], rsi
0x18001bd38  call    WPP_SF_dS
0x18001bd3d  mov     rcx, rbp; hObject
0x18001bd40  call    cs:__imp_CloseHandle
0x18001bd46  mov     rcx, [rsp+58h+pvContext]; pvContext
0x18001bd4b  test    rcx, rcx
0x18001bd4e  jz      short loc_18001BD56
0x18001bd50  call    cs:__imp_CloseEncryptedFileRaw
0x18001bd56  mov     rbp, [rsp+58h+arg_8]
0x18001bd5b  mov     eax, ebx
0x18001bd5d  mov     rbx, [rsp+58h+arg_0]
0x18001bd62  add     rsp, 40h
0x18001bd66  pop     r14
0x18001bd68  pop     rdi
0x18001bd69  pop     rsi
0x18001bd6a  retn
```
