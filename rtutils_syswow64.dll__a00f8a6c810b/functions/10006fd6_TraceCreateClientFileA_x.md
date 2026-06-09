# TraceCreateClientFileA(x)

- ea: `0x10006fd6`
- end: `0x1000716e`
- name: `_TraceCreateClientFileA@4`
- size: `408`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x100027e0`
- `0x100075de`

## callees

- `0x10002c90`
- `0x10003c20`
- `0x1000471f`
- `0x100049a9`
- `0x10004ab6`
- `0x10006fd6`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000709f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000712a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10007151`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000709f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000712a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10007151`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x10007019`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x10007019`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1000713b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1000713b`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x10007123`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x10007123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10007023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100070ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10007023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100070ee`
- `api-ms-win-core-file-l1-2-5!CreateFile3` at `0x100070e6`
- `api-ms-win-core-file-l1-2-5!CreateFile3` at `0x100070e6`

## pseudocode

```c
signed int __thiscall TraceCreateClientFileA(int this)
{
  DWORD FullPathNameA; // eax
  signed int result; // eax
  HRESULT v4; // eax
  unsigned __int16 v5; // si
  HRESULT v6; // eax
  void *File3; // esi
  DWORD LastError; // edi
  int IsNotALinkA; // ebx
  size_t v10; // [esp+0h] [ebp-140h]
  size_t v11; // [esp+0h] [ebp-140h]
  size_t v12; // [esp+0h] [ebp-140h]
  const char *v13; // [esp+4h] [ebp-13Ch]
  const char *v14; // [esp+4h] [ebp-13Ch]
  const char *v15; // [esp+4h] [ebp-13Ch]
  char FileInformation; // [esp+Fh] [ebp-131h] BYREF
  HANDLE hObject; // [esp+10h] [ebp-130h] BYREF
  int v18; // [esp+14h] [ebp-12Ch]
  _DWORD v19[6]; // [esp+18h] [ebp-128h] BYREF
  CHAR Buffer[268]; // [esp+30h] [ebp-110h] BYREF

  v18 = this;
  memset(v19, 0, sizeof(v19));
  FullPathNameA = GetFullPathNameA((LPCSTR)(this + 252), 0x104u, Buffer, 0);
  if ( !FullPathNameA )
    return GetLastError();
  if ( FullPathNameA >= 0x104 )
    return 161;
  result = TraceVerifyDirectoryPathA(Buffer);
  if ( !result )
  {
    result = StringCchCatA((STRSAFE_LPSTR)"\\", v10, v13);
    if ( result >= 0 )
    {
      hObject = (HANDLE)-1;
      result = CreateTracingDirectoryA(Buffer, &hObject);
      if ( !result )
      {
        v4 = StringCchCatA((STRSAFE_LPSTR)(this + 40), v11, v14);
        v5 = v4;
        if ( v4 < 0 || (v6 = StringCchCatA((STRSAFE_LPSTR)".LOG", v12, v15), v5 = v6, v6 < 0) )
        {
          CloseHandle(hObject);
          return v5;
        }
        else
        {
          v19[0] = 24;
          v19[2] = 3211392;
          File3 = (void *)CreateFile3(Buffer, -1073676288, 1, 4, v19);
          LastError = GetLastError();
          if ( File3 != (void *)-1 )
          {
            IsNotALinkA = TraceVerifyFileIsNotALinkA(File3);
            if ( IsNotALinkA )
            {
              if ( LastError != 183 )
              {
                FileInformation = 1;
                SetFileInformationByHandle(File3, FileDispositionInfo, &FileInformation, 1u);
              }
              CloseHandle(File3);
              LastError = IsNotALinkA;
            }
            else
            {
              SetFilePointer(File3, 0, 0, 2u);
              LastError = 0;
              *(_DWORD *)(v18 + 232) = File3;
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
0x10006fd6  mov     edi, edi
0x10006fd8  push    ebp
0x10006fd9  mov     ebp, esp
0x10006fdb  and     esp, 0FFFFFFF8h
0x10006fde  sub     esp, 134h
0x10006fe4  mov     eax, ___security_cookie
0x10006fe9  xor     eax, esp
0x10006feb  mov     [esp+134h+var_4], eax
0x10006ff2  push    ebx
0x10006ff3  push    esi; pszSrc
0x10006ff4  push    edi; cchDest
0x10006ff5  push    6
0x10006ff7  mov     ebx, ecx
0x10006ff9  lea     edi, [esp+144h+var_128]
0x10006ffd  pop     ecx
0x10006ffe  xor     eax, eax
0x10007000  mov     [esp+140h+var_12C], ebx
0x10007004  push    eax; lpFilePart
0x10007005  rep stosd
0x10007007  lea     eax, [esp+144h+Buffer]
0x1000700b  mov     edi, 104h
0x10007010  push    eax; lpBuffer
0x10007011  push    edi; nBufferLength
0x10007012  lea     eax, [ebx+0FCh]
0x10007018  push    eax; lpFileName
0x10007019  call    ds:__imp__GetFullPathNameA@16; GetFullPathNameA(x,x,x,x)
0x1000701f  test    eax, eax
0x10007021  jnz     short loc_1000702E
0x10007023  call    ds:__imp__GetLastError@0; GetLastError()
0x10007029  jmp     loc_10007159
0x1000702e  cmp     eax, edi
0x10007030  jb      short loc_1000703C
0x10007032  mov     eax, 0A1h
0x10007037  jmp     loc_10007159
0x1000703c  lea     ecx, [esp+140h+Buffer]; String1
0x10007040  call    _TraceVerifyDirectoryPathA@4; TraceVerifyDirectoryPathA(x)
0x10007045  test    eax, eax
0x10007047  jnz     loc_10007159
0x1000704d  push    offset asc_10001294; "\\"
0x10007052  mov     edx, edi
0x10007054  lea     ecx, [esp+144h+Buffer]
0x10007058  call    _StringCchCatA@12; StringCchCatA(x,x,x)
0x1000705d  test    eax, eax
0x1000705f  jns     short loc_10007069
0x10007061  movzx   eax, ax
0x10007064  jmp     loc_10007159
0x10007069  lea     edx, [esp+140h+hObject]
0x1000706d  mov     [esp+140h+hObject], 0FFFFFFFFh
0x10007075  lea     ecx, [esp+140h+Buffer]
0x10007079  call    _CreateTracingDirectoryA@8; CreateTracingDirectoryA(x,x)
0x1000707e  test    eax, eax
0x10007080  jnz     loc_10007159
0x10007086  lea     eax, [ebx+28h]
0x10007089  mov     edx, edi
0x1000708b  push    eax; pszDest
0x1000708c  lea     ecx, [esp+144h+Buffer]
0x10007090  call    _StringCchCatA@12; StringCchCatA(x,x,x)
0x10007095  mov     esi, eax
0x10007097  test    esi, esi
0x10007099  jns     short loc_100070AD
0x1000709b  push    [esp+140h+hObject]; hObject
0x1000709f  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100070a5  movzx   eax, si
0x100070a8  jmp     loc_10007159
0x100070ad  push    offset aLog_0; ".LOG"
0x100070b2  mov     edx, edi
0x100070b4  lea     ecx, [esp+144h+Buffer]
0x100070b8  call    _StringCchCatA@12; StringCchCatA(x,x,x)
0x100070bd  mov     esi, eax
0x100070bf  test    esi, esi
0x100070c1  js      short loc_1000709B
0x100070c3  lea     eax, [esp+140h+var_128]
0x100070c7  mov     [esp+140h+var_128], 18h
0x100070cf  push    eax
0x100070d0  push    4
0x100070d2  push    1
0x100070d4  push    0C0010000h
0x100070d9  lea     eax, [esp+150h+Buffer]
0x100070dd  mov     [esp+150h+var_120], 310080h
0x100070e5  push    eax
0x100070e6  call    ds:__imp__CreateFile3@20; CreateFile3(x,x,x,x,x)
0x100070ec  mov     esi, eax
0x100070ee  call    ds:__imp__GetLastError@0; GetLastError()
0x100070f4  mov     edi, eax
0x100070f6  cmp     esi, 0FFFFFFFFh
0x100070f9  jz      short loc_1000714D
0x100070fb  lea     edx, [esp+140h+Buffer]
0x100070ff  mov     ecx, esi; hFile
0x10007101  call    _TraceVerifyFileIsNotALinkA@8; TraceVerifyFileIsNotALinkA(x,x)
0x10007106  mov     ebx, eax
0x10007108  test    ebx, ebx
0x1000710a  jz      short loc_10007134
0x1000710c  cmp     edi, 0B7h
0x10007112  jz      short loc_10007129
0x10007114  push    1; dwBufferSize
0x10007116  lea     eax, [esp+144h+FileInformation]
0x1000711a  mov     [esp+144h+FileInformation], 1
0x1000711f  push    eax; lpFileInformation
0x10007120  push    4; FileInformationClass
0x10007122  push    esi; hFile
0x10007123  call    ds:__imp__SetFileInformationByHandle@16; SetFileInformationByHandle(x,x,x,x)
0x10007129  push    esi; hObject
0x1000712a  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10007130  mov     edi, ebx
0x10007132  jmp     short loc_1000714D
0x10007134  push    2; dwMoveMethod
0x10007136  push    0; lpDistanceToMoveHigh
0x10007138  push    0; lDistanceToMove
0x1000713a  push    esi; hFile
0x1000713b  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x10007141  mov     eax, [esp+140h+var_12C]
0x10007145  xor     edi, edi
0x10007147  mov     [eax+0E8h], esi
0x1000714d  push    [esp+140h+hObject]; hObject
0x10007151  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10007157  mov     eax, edi
0x10007159  mov     ecx, [esp+140h+var_4]
0x10007160  pop     edi
0x10007161  pop     esi
0x10007162  pop     ebx
0x10007163  xor     ecx, esp; StackCookie
0x10007165  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000716a  mov     esp, ebp
0x1000716c  pop     ebp
0x1000716d  retn
```
