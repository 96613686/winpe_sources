# TraceCreateClientFileA

- ea: `0x180005f70`
- end: `0x18000614f`
- name: `TraceCreateClientFileA`
- size: `479`
- prototype: `signed int __fastcall(__int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180001100`
- `0x180001c20`
- `0x180001fa0`
- `0x180006514`

## callees

- `0x180002830`
- `0x180003614`
- `0x180003bb0`
- `0x180005ba4`
- `0x180005f70`
- `0x180006690`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000604f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006123`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000604f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006123`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800060ee`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800060ee`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000610f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000610f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180005fbe`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180005fbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060ae`
- `api-ms-win-core-file-l1-2-5!CreateFile3` at `0x1800060a5`
- `api-ms-win-core-file-l1-2-5!CreateFile3` at `0x1800060a5`

## pseudocode

```c
signed int __fastcall TraceCreateClientFileA(__int64 a1)
{
  DWORD FullPathNameA; // eax
  signed int result; // eax
  HRESULT v4; // eax
  unsigned __int16 v5; // bx
  HRESULT v6; // eax
  void *File3; // rbx
  DWORD LastError; // edi
  DWORD IsNotALinkA; // esi
  char FileInformation[8]; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v12; // [rsp+40h] [rbp-C0h]
  __int128 v13; // [rsp+50h] [rbp-B0h]
  CHAR Buffer[272]; // [rsp+60h] [rbp-A0h] BYREF

  v12 = 0;
  v13 = 0;
  FullPathNameA = GetFullPathNameA((LPCSTR)(a1 + 284), 0x104u, Buffer, 0);
  if ( !FullPathNameA )
    return GetLastError();
  if ( FullPathNameA >= 0x104 )
    return 161;
  result = TraceVerifyDirectoryPathA(Buffer);
  if ( !result )
  {
    result = StringCchCatA(Buffer, 0x104u, "\\");
    if ( result >= 0 )
    {
      hObject = (HANDLE)-1LL;
      result = CreateTracingDirectoryA(Buffer, &hObject);
      if ( !result )
      {
        v4 = StringCchCatA(Buffer, 0x104u, (STRSAFE_LPCSTR)(a1 + 64));
        v5 = v4;
        if ( v4 < 0 || (v6 = StringCchCatA(Buffer, 0x104u, ".LOG"), v5 = v6, v6 < 0) )
        {
          CloseHandle(hObject);
          return v5;
        }
        else
        {
          LODWORD(v12) = 32;
          DWORD2(v12) = 3211392;
          File3 = (void *)CreateFile3(Buffer, 3221291008LL, 1);
          LastError = GetLastError();
          if ( File3 != (void *)-1LL )
          {
            IsNotALinkA = TraceVerifyFileIsNotALinkA(File3, Buffer);
            if ( IsNotALinkA )
            {
              if ( LastError != 183 )
              {
                FileInformation[0] = 1;
                SetFileInformationByHandle(File3, FileDispositionInfo, FileInformation, 1u);
              }
              CloseHandle(File3);
              LastError = IsNotALinkA;
            }
            else
            {
              SetFilePointer(File3, 0, 0, 2u);
              LastError = 0;
              *(_QWORD *)(a1 + 256) = File3;
            }
          }
          CloseHandle(hObject);
          return LastError;
        }
      }
    }
    else
    {
      return (unsigned __int16)result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005f70  mov     [rsp-8+arg_8], rbx
0x180005f75  mov     [rsp-8+arg_10], rsi
0x180005f7a  push    rbp
0x180005f7b  push    rdi
0x180005f7c  push    r14
0x180005f7e  lea     rbp, [rsp-80h]
0x180005f83  sub     rsp, 180h
0x180005f8a  mov     rax, cs:__security_cookie
0x180005f91  xor     rax, rsp
0x180005f94  mov     [rbp+90h+var_20], rax
0x180005f98  xorps   xmm0, xmm0
0x180005f9b  lea     r8, [rsp+190h+Buffer]; lpBuffer
0x180005fa0  mov     r14, rcx
0x180005fa3  mov     edi, 104h
0x180005fa8  mov     edx, edi; nBufferLength
0x180005faa  add     rcx, 11Ch; lpFileName
0x180005fb1  xor     r9d, r9d; lpFilePart
0x180005fb4  movups  [rsp+190h+var_150], xmm0
0x180005fb9  movups  [rsp+190h+var_140], xmm0
0x180005fbe  call    cs:__imp_GetFullPathNameA
0x180005fc4  test    eax, eax
0x180005fc6  jnz     short loc_180005FD3
0x180005fc8  call    cs:__imp_GetLastError
0x180005fce  jmp     loc_18000612B
0x180005fd3  cmp     eax, edi
0x180005fd5  jb      short loc_180005FE1
0x180005fd7  mov     eax, 0A1h
0x180005fdc  jmp     loc_18000612B
0x180005fe1  lea     rcx, [rsp+190h+Buffer]; String1
0x180005fe6  call    TraceVerifyDirectoryPathA
0x180005feb  test    eax, eax
0x180005fed  jnz     loc_18000612B
0x180005ff3  lea     r8, pszSrc; "\\"
0x180005ffa  mov     rdx, rdi; cchDest
0x180005ffd  lea     rcx, [rsp+190h+Buffer]; pszDest
0x180006002  call    StringCchCatA
0x180006007  test    eax, eax
0x180006009  jns     short loc_180006013
0x18000600b  movzx   eax, ax
0x18000600e  jmp     loc_18000612B
0x180006013  lea     rdx, [rsp+190h+hObject]; FileHandle
0x180006018  mov     [rsp+190h+hObject], 0FFFFFFFFFFFFFFFFh
0x180006021  lea     rcx, [rsp+190h+Buffer]; String1
0x180006026  call    CreateTracingDirectoryA
0x18000602b  test    eax, eax
0x18000602d  jnz     loc_18000612B
0x180006033  lea     r8, [r14+40h]; pszSrc
0x180006037  mov     rdx, rdi; cchDest
0x18000603a  lea     rcx, [rsp+190h+Buffer]; pszDest
0x18000603f  call    StringCchCatA
0x180006044  mov     ebx, eax
0x180006046  test    eax, eax
0x180006048  jns     short loc_18000605D
0x18000604a  mov     rcx, [rsp+190h+hObject]; hObject
0x18000604f  call    cs:__imp_CloseHandle
0x180006055  movzx   eax, bx
0x180006058  jmp     loc_18000612B
0x18000605d  lea     r8, aLog_0; ".LOG"
0x180006064  mov     rdx, rdi; cchDest
0x180006067  lea     rcx, [rsp+190h+Buffer]; pszDest
0x18000606c  call    StringCchCatA
0x180006071  mov     ebx, eax
0x180006073  test    eax, eax
0x180006075  js      short loc_18000604A
0x180006077  mov     r9d, 4
0x18000607d  mov     dword ptr [rsp+190h+var_150], 20h ; ' '
0x180006085  lea     rax, [rsp+190h+var_150]
0x18000608a  mov     dword ptr [rsp+190h+var_150+8], 310080h
0x180006092  mov     edx, 0C0010000h
0x180006097  mov     [rsp+190h+var_170], rax
0x18000609c  lea     rcx, [rsp+190h+Buffer]
0x1800060a1  lea     r8d, [r9-3]
0x1800060a5  call    cs:__imp_CreateFile3
0x1800060ab  mov     rbx, rax
0x1800060ae  call    cs:__imp_GetLastError
0x1800060b4  mov     edi, eax
0x1800060b6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800060ba  jz      short loc_18000611E
0x1800060bc  lea     rdx, [rsp+190h+Buffer]; String1
0x1800060c1  mov     rcx, rbx; hFile
0x1800060c4  call    TraceVerifyFileIsNotALinkA
0x1800060c9  mov     esi, eax
0x1800060cb  test    eax, eax
0x1800060cd  jz      short loc_180006101
0x1800060cf  cmp     edi, 0B7h
0x1800060d5  jz      short loc_1800060F4
0x1800060d7  mov     r9d, 1; dwBufferSize
0x1800060dd  mov     [rsp+190h+FileInformation], 1
0x1800060e2  lea     r8, [rsp+190h+FileInformation]; lpFileInformation
0x1800060e7  mov     rcx, rbx; hFile
0x1800060ea  lea     edx, [r9+3]; FileInformationClass
0x1800060ee  call    cs:__imp_SetFileInformationByHandle
0x1800060f4  mov     rcx, rbx; hObject
0x1800060f7  call    cs:__imp_CloseHandle
0x1800060fd  mov     edi, esi
0x1800060ff  jmp     short loc_18000611E
0x180006101  mov     r9d, 2; dwMoveMethod
0x180006107  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000610a  xor     edx, edx; lDistanceToMove
0x18000610c  mov     rcx, rbx; hFile
0x18000610f  call    cs:__imp_SetFilePointer
0x180006115  xor     edi, edi
0x180006117  mov     [r14+100h], rbx
0x18000611e  mov     rcx, [rsp+190h+hObject]; hObject
0x180006123  call    cs:__imp_CloseHandle
0x180006129  mov     eax, edi
0x18000612b  mov     rcx, [rbp+90h+var_20]
0x18000612f  xor     rcx, rsp; StackCookie
0x180006132  call    __security_check_cookie
0x180006137  lea     r11, [rsp+190h+var_10]
0x18000613f  mov     rbx, [r11+28h]
0x180006143  mov     rsi, [r11+30h]
0x180006147  mov     rsp, r11
0x18000614a  pop     r14
0x18000614c  pop     rdi
0x18000614d  pop     rbp
0x18000614e  retn
```
