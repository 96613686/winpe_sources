# GetDetachedMessage_(void *,_CRYPT_PROVIDER_DATA *)

- ea: `0x180046d3c`
- end: `0x180046fe9`
- name: `?GetDetachedMessage_@@YAHPEAXPEAU_CRYPT_PROVIDER_DATA@@@Z`
- size: `685`
- prototype: `__int64 __fastcall(HCRYPTMSG hCryptMsg, struct _CRYPT_PROVIDER_DATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18001ca00`

## callees

- `0x180022708`
- `0x180022738`
- `0x180046d3c`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180046e76`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180046e76`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180046e12`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180046e51`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180046f69`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180046fcc`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180046e12`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180046e51`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180046f69`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180046fcc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180046f0c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180046f0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f93`
- `CRYPT32!CryptMsgUpdate` at `0x180046db2`
- `CRYPT32!CryptMsgUpdate` at `0x180046f32`
- `CRYPT32!CryptMsgUpdate` at `0x180046db2`
- `CRYPT32!CryptMsgUpdate` at `0x180046f32`

## pseudocode

```c
__int64 __fastcall GetDetachedMessage_(HCRYPTMSG hCryptMsg, struct _CRYPT_PROVIDER_DATA *a2)
{
  struct WINTRUST_FILE_INFO_ *pFile; // rcx
  __int64 *v5; // rax
  const BYTE *v6; // r14
  __int64 v7; // rsi
  DWORD v8; // r8d
  __int64 v9; // r15
  HANDLE *pcwszFilePath; // rcx
  union _LARGE_INTEGER v11; // rsi
  DWORD LowPart; // r14d
  struct _CRYPT_PROVIDER_FUNCTIONS *psPfns; // rax
  __int64 v14; // rax
  void *v15; // r15
  union _LARGE_INTEGER FileSize; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpBuffer[3]; // [rsp+38h] [rbp-18h] BYREF
  LARGE_INTEGER liDistanceToMove; // [rsp+90h] [rbp+40h] BYREF
  union _LARGE_INTEGER NewFilePointer; // [rsp+98h] [rbp+48h] BYREF

  pFile = a2->pWintrustData->pFile;
  if ( *(&pFile->cbStruct + 1) == 1 )
  {
    NewFilePointer.QuadPart = 0;
    pcwszFilePath = (HANDLE *)pFile->pcwszFilePath;
    liDistanceToMove.QuadPart = 0;
    if ( SetFilePointerEx(*pcwszFilePath, 0, &NewFilePointer, 1u)
      && SetFilePointerEx(*(HANDLE *)a2->pWintrustData->pFile->pcwszFilePath, liDistanceToMove, 0, 0) )
    {
      FileSize.QuadPart = 0;
      if ( GetFileSizeEx(*(HANDLE *)a2->pWintrustData->pFile->pcwszFilePath, &FileSize) )
      {
        v11 = FileSize;
        LowPart = 0x1000000;
        if ( FileSize.QuadPart < 0x1000000 )
          LowPart = FileSize.LowPart;
        psPfns = a2->psPfns;
        lpBuffer[0] = 0;
        lpBuffer[1] = a2;
        v14 = ((__int64 (__fastcall *)(_QWORD))psPfns->pfnAlloc)(LowPart);
        std::unique_ptr<unsigned char,msgprov_deleter>::reset(lpBuffer, v14);
        v15 = lpBuffer[0];
        if ( lpBuffer[0] )
        {
          while ( 1 )
          {
            liDistanceToMove.LowPart = 0;
            if ( !ReadFile(
                    *(HANDLE *)a2->pWintrustData->pFile->pcwszFilePath,
                    v15,
                    LowPart,
                    (LPDWORD)&liDistanceToMove,
                    0)
              || liDistanceToMove.LowPart != LowPart )
            {
              break;
            }
            if ( !CryptMsgUpdate(hCryptMsg, (const BYTE *)v15, liDistanceToMove.LowPart, v11.QuadPart <= LowPart) )
            {
              a2->padwTrustStepErrors[8] = GetLastError();
              a2->padwTrustStepErrors[32] = -2146885619;
              goto LABEL_27;
            }
            v11.QuadPart -= liDistanceToMove.LowPart;
            if ( v11.QuadPart <= 0 )
            {
              std::unique_ptr<unsigned char,msgprov_deleter>::_Delete(lpBuffer);
              SetFilePointerEx(*(HANDLE *)a2->pWintrustData->pFile->pcwszFilePath, NewFilePointer, 0, 0);
              return 1;
            }
          }
        }
        a2->dwError = GetLastError();
        a2->padwTrustStepErrors[32] = -2146869247;
LABEL_27:
        std::unique_ptr<unsigned char,msgprov_deleter>::_Delete(lpBuffer);
      }
      else
      {
        a2->dwError = GetLastError();
        a2->padwTrustStepErrors[32] = -2146869247;
      }
      SetFilePointerEx(*(HANDLE *)a2->pWintrustData->pFile->pcwszFilePath, NewFilePointer, 0, 0);
    }
    else
    {
      a2->dwError = GetLastError();
      a2->padwTrustStepErrors[32] = -2146869247;
    }
  }
  else if ( *(&pFile->cbStruct + 1) == 2 )
  {
    v5 = (__int64 *)pFile->pcwszFilePath;
    v6 = (const BYTE *)v5[1];
    v7 = *v5;
    while ( 1 )
    {
      v8 = v7;
      if ( v7 >= 0x10000000 )
        v8 = 0x10000000;
      v9 = v8;
      if ( !CryptMsgUpdate(hCryptMsg, v6, v8, v7 <= v8) )
        break;
      v7 -= v9;
      if ( v7 <= 0 )
        return 1;
      v6 += v9;
    }
    a2->padwTrustStepErrors[8] = GetLastError();
    a2->padwTrustStepErrors[32] = -2146885619;
  }
  else
  {
    a2->padwTrustStepErrors[32] = 87;
  }
  return 0;
}

```

## disassembly

```asm
0x180046d3c  mov     [rsp-28h+arg_0], rbx
0x180046d41  push    rbp
0x180046d42  push    rsi
0x180046d43  push    r12
0x180046d45  push    r14
0x180046d47  push    r15
0x180046d49  mov     rbp, rsp
0x180046d4c  sub     rsp, 50h
0x180046d50  mov     rax, [rdx+8]
0x180046d54  mov     rbx, rdx
0x180046d57  mov     r12, rcx
0x180046d5a  mov     rcx, [rax+28h]
0x180046d5e  mov     edx, [rcx+4]
0x180046d61  sub     edx, 1
0x180046d64  jz      loc_180046DED
0x180046d6a  cmp     edx, 1
0x180046d6d  jz      short loc_180046D82
0x180046d6f  mov     rax, [rbx+50h]
0x180046d73  mov     dword ptr [rax+80h], 57h ; 'W'
0x180046d7d  jmp     loc_180046FD2
0x180046d82  mov     rax, [rcx+8]
0x180046d86  mov     r14, [rax+8]
0x180046d8a  mov     rsi, [rax]
0x180046d8d  mov     r8d, esi
0x180046d90  cmp     rsi, 10000000h
0x180046d97  jl      short loc_180046D9F
0x180046d99  mov     r8d, 10000000h; cbData
0x180046d9f  xor     r9d, r9d
0x180046da2  mov     r15d, r8d
0x180046da5  cmp     rsi, r15
0x180046da8  mov     rdx, r14; pbData
0x180046dab  mov     rcx, r12; hCryptMsg
0x180046dae  setle   r9b; fFinal
0x180046db2  call    cs:__imp_CryptMsgUpdate
0x180046db8  test    eax, eax
0x180046dba  jz      short loc_180046DCD
0x180046dbc  sub     rsi, r15
0x180046dbf  test    rsi, rsi
0x180046dc2  jle     loc_180046F6F
0x180046dc8  add     r14, r15
0x180046dcb  jmp     short loc_180046D8D
0x180046dcd  call    cs:__imp_GetLastError
0x180046dd3  mov     rcx, [rbx+50h]
0x180046dd7  mov     [rcx+20h], eax
0x180046dda  mov     rax, [rbx+50h]
0x180046dde  mov     dword ptr [rax+80h], 8009200Dh
0x180046de8  jmp     loc_180046FD2
0x180046ded  mov     qword ptr [rbp+NewFilePointer], 0
0x180046df5  lea     r8, [rbp+NewFilePointer]; lpNewFilePointer
0x180046df9  mov     rcx, [rcx+8]
0x180046dfd  mov     r9d, 1; dwMoveMethod
0x180046e03  mov     qword ptr [rbp+liDistanceToMove], 0
0x180046e0b  mov     rdx, qword ptr [rbp+liDistanceToMove]; liDistanceToMove
0x180046e0f  mov     rcx, [rcx]; hFile
0x180046e12  call    cs:__imp_SetFilePointerEx
0x180046e18  test    eax, eax
0x180046e1a  jnz     short loc_180046E38
0x180046e1c  call    cs:__imp_GetLastError
0x180046e22  mov     [rbx+30h], eax
0x180046e25  mov     rax, [rbx+50h]
0x180046e29  mov     dword ptr [rax+80h], 80096001h
0x180046e33  jmp     loc_180046FD2
0x180046e38  mov     rax, [rbx+8]
0x180046e3c  xor     r9d, r9d; dwMoveMethod
0x180046e3f  mov     rdx, qword ptr [rbp+liDistanceToMove]; liDistanceToMove
0x180046e43  xor     r8d, r8d; lpNewFilePointer
0x180046e46  mov     rcx, [rax+28h]
0x180046e4a  mov     rcx, [rcx+8]
0x180046e4e  mov     rcx, [rcx]; hFile
0x180046e51  call    cs:__imp_SetFilePointerEx
0x180046e57  test    eax, eax
0x180046e59  jz      short loc_180046E1C
0x180046e5b  mov     qword ptr [rbp+FileSize], 0
0x180046e63  lea     rdx, [rbp+FileSize]; lpFileSize
0x180046e67  mov     rax, [rbx+8]
0x180046e6b  mov     rcx, [rax+28h]
0x180046e6f  mov     rcx, [rcx+8]
0x180046e73  mov     rcx, [rcx]; hFile
0x180046e76  call    cs:__imp_GetFileSizeEx
0x180046e7c  test    eax, eax
0x180046e7e  jnz     short loc_180046E9C
0x180046e80  call    cs:__imp_GetLastError
0x180046e86  mov     [rbx+30h], eax
0x180046e89  mov     rax, [rbx+50h]
0x180046e8d  mov     dword ptr [rax+80h], 80096001h
0x180046e97  jmp     loc_180046FB3
0x180046e9c  mov     rsi, qword ptr [rbp+FileSize]
0x180046ea0  mov     r14d, 1000000h
0x180046ea6  cmp     rsi, r14
0x180046ea9  jge     short loc_180046EAE
0x180046eab  mov     r14d, esi
0x180046eae  mov     rax, [rbx+40h]
0x180046eb2  mov     ecx, r14d
0x180046eb5  mov     [rbp+lpBuffer], 0
0x180046ebd  mov     [rbp+var_10], rbx
0x180046ec1  mov     rax, [rax+8]
0x180046ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046eca  mov     rdx, rax
0x180046ecd  lea     rcx, [rbp+lpBuffer]
0x180046ed1  call    ?reset@?$unique_ptr@EUmsgprov_deleter@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar,msgprov_deleter>::reset(uchar *)
0x180046ed6  mov     r15, [rbp+lpBuffer]
0x180046eda  test    r15, r15
0x180046edd  jz      loc_180046F93
0x180046ee3  mov     dword ptr [rbp+liDistanceToMove], 0
0x180046eea  lea     r9, [rbp+liDistanceToMove]; lpNumberOfBytesRead
0x180046eee  mov     rax, [rbx+8]
0x180046ef2  mov     r8d, r14d; nNumberOfBytesToRead
0x180046ef5  mov     rdx, r15; lpBuffer
0x180046ef8  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x180046f01  mov     rcx, [rax+28h]
0x180046f05  mov     rcx, [rcx+8]
0x180046f09  mov     rcx, [rcx]; hFile
0x180046f0c  call    cs:__imp_ReadFile
0x180046f12  test    eax, eax
0x180046f14  jz      short loc_180046F93
0x180046f16  mov     r8d, dword ptr [rbp+liDistanceToMove]; cbData
0x180046f1a  cmp     r8d, r14d
0x180046f1d  jnz     short loc_180046F93
0x180046f1f  xor     r9d, r9d
0x180046f22  mov     eax, r14d
0x180046f25  cmp     rsi, rax
0x180046f28  mov     rdx, r15; pbData
0x180046f2b  mov     rcx, r12; hCryptMsg
0x180046f2e  setle   r9b; fFinal
0x180046f32  call    cs:__imp_CryptMsgUpdate
0x180046f38  test    eax, eax
0x180046f3a  jz      short loc_180046F76
0x180046f3c  mov     eax, dword ptr [rbp+liDistanceToMove]
0x180046f3f  sub     rsi, rax
0x180046f42  test    rsi, rsi
0x180046f45  jg      short loc_180046EE3
0x180046f47  lea     rcx, [rbp+lpBuffer]
0x180046f4b  call    ?_Delete@?$unique_ptr@EUmsgprov_deleter@@@std@@AEAAXXZ; std::unique_ptr<uchar,msgprov_deleter>::_Delete(void)
0x180046f50  mov     rcx, [rbx+8]
0x180046f54  xor     r9d, r9d; dwMoveMethod
0x180046f57  xor     r8d, r8d; lpNewFilePointer
0x180046f5a  mov     rdx, [rcx+28h]
0x180046f5e  mov     rcx, [rdx+8]
0x180046f62  mov     rdx, qword ptr [rbp+NewFilePointer]; liDistanceToMove
0x180046f66  mov     rcx, [rcx]; hFile
0x180046f69  call    cs:__imp_SetFilePointerEx
0x180046f6f  mov     eax, 1
0x180046f74  jmp     short loc_180046FD4
0x180046f76  call    cs:__imp_GetLastError
0x180046f7c  mov     rcx, [rbx+50h]
0x180046f80  mov     [rcx+20h], eax
0x180046f83  mov     rax, [rbx+50h]
0x180046f87  mov     dword ptr [rax+80h], 8009200Dh
0x180046f91  jmp     short loc_180046FAA
0x180046f93  call    cs:__imp_GetLastError
0x180046f99  mov     [rbx+30h], eax
0x180046f9c  mov     rax, [rbx+50h]
0x180046fa0  mov     dword ptr [rax+80h], 80096001h
0x180046faa  lea     rcx, [rbp+lpBuffer]
0x180046fae  call    ?_Delete@?$unique_ptr@EUmsgprov_deleter@@@std@@AEAAXXZ; std::unique_ptr<uchar,msgprov_deleter>::_Delete(void)
0x180046fb3  mov     rax, [rbx+8]
0x180046fb7  xor     r9d, r9d; dwMoveMethod
0x180046fba  mov     rdx, qword ptr [rbp+NewFilePointer]; liDistanceToMove
0x180046fbe  xor     r8d, r8d; lpNewFilePointer
0x180046fc1  mov     rcx, [rax+28h]
0x180046fc5  mov     rcx, [rcx+8]
0x180046fc9  mov     rcx, [rcx]; hFile
0x180046fcc  call    cs:__imp_SetFilePointerEx
0x180046fd2  xor     eax, eax
0x180046fd4  mov     rbx, [rsp+50h+arg_0]
0x180046fdc  add     rsp, 50h
0x180046fe0  pop     r15
0x180046fe2  pop     r14
0x180046fe4  pop     r12
0x180046fe6  pop     rsi
0x180046fe7  pop     rbp
0x180046fe8  retn
```
