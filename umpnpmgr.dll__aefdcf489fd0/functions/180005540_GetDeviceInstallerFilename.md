# GetDeviceInstallerFilename

- ea: `0x180005540`
- end: `0x1800056bf`
- name: `GetDeviceInstallerFilename`
- size: `383`
- prototype: `_BOOL8 __fastcall(_WORD *)`
- caller_count: `7`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180001190`
- `0x1800027a0`
- `0x180004180`
- `0x1800056d0`
- `0x1800126cc`
- `0x180014a84`
- `0x1800156c0`

## callees

- `0x1800040f0`
- `0x180005540`
- `0x1800135f0`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000568d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000568d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180005588`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180005588`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005685`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005685`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800055e9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800055e9`

## pseudocode

```c
_BOOL8 __fastcall GetDeviceInstallerFilename(_WORD *a1)
{
  __int64 v2; // rbx
  UINT SystemDirectoryW; // eax
  DWORD LastError; // edi
  HANDLE FirstFileW; // r8
  int v6; // r8d
  WCHAR *v7; // rdx
  __int64 v8; // rax
  _WORD *v9; // rcx
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-688h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp-438h] BYREF
  WCHAR Buffer[264]; // [rsp+490h] [rbp-228h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v2 = 260;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( SystemDirectoryW )
  {
    if ( SystemDirectoryW > 0x104 || (int)RtlStringCchPrintfW(FileName, 260, L"%ws\\%ws", Buffer, L"DrvInst.exe") < 0 )
    {
      LastError = 123;
    }
    else
    {
      FirstFileW = FindFirstFileW(FileName, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        {
          WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v6, (unsigned int)FileName, LastError);
        }
      }
      else
      {
        LastError = 0;
        v7 = FileName;
        v8 = 2147483646;
        do
        {
          if ( !v8 )
            break;
          if ( !*v7 )
            break;
          *a1++ = *v7++;
          --v8;
          --v2;
        }
        while ( v2 );
        v9 = a1 - 1;
        if ( v2 )
          v9 = a1;
        *v9 = 0;
        if ( !v2 )
          LastError = 122;
        FindClose(FirstFileW);
      }
    }
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180005540  mov     [rsp+arg_8], rbx
0x180005545  mov     [rsp+arg_10], rsi
0x18000554a  push    rdi
0x18000554b  sub     rsp, 6B0h
0x180005552  mov     rax, cs:__security_cookie
0x180005559  xor     rax, rsp
0x18000555c  mov     [rsp+6B8h+var_18], rax
0x180005564  mov     rsi, rcx
0x180005567  xor     edx, edx; Val
0x180005569  lea     rcx, [rsp+6B8h+FindFileData]; void *
0x18000556e  mov     r8d, 250h; Size
0x180005574  call    memset_0
0x180005579  mov     ebx, 104h
0x18000557e  lea     rcx, [rsp+6B8h+Buffer]; lpBuffer
0x180005586  mov     edx, ebx; uSize
0x180005588  call    cs:__imp_GetSystemDirectoryW
0x18000558e  test    eax, eax
0x180005590  jnz     short loc_18000559F
0x180005592  call    cs:__imp_GetLastError
0x180005598  mov     edi, eax
0x18000559a  jmp     loc_18000568B
0x18000559f  cmp     eax, ebx
0x1800055a1  jbe     short loc_1800055AD
0x1800055a3  mov     edi, 7Bh ; '{'
0x1800055a8  jmp     loc_18000568B
0x1800055ad  lea     rax, aDrvinstExe; "DrvInst.exe"
0x1800055b4  mov     rdx, rbx
0x1800055b7  lea     r9, [rsp+6B8h+Buffer]
0x1800055bf  mov     [rsp+6B8h+var_698], rax
0x1800055c4  lea     r8, aWsWs; "%ws\\%ws"
0x1800055cb  lea     rcx, [rsp+6B8h+FileName]
0x1800055d3  call    RtlStringCchPrintfW
0x1800055d8  test    eax, eax
0x1800055da  js      short loc_1800055A3
0x1800055dc  lea     rdx, [rsp+6B8h+FindFileData]; lpFindFileData
0x1800055e1  lea     rcx, [rsp+6B8h+FileName]; lpFileName
0x1800055e9  call    cs:__imp_FindFirstFileW
0x1800055ef  mov     r8, rax
0x1800055f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800055f6  jnz     short loc_180005638
0x1800055f8  call    cs:__imp_GetLastError
0x1800055fe  mov     edi, eax
0x180005600  mov     rcx, cs:WPP_GLOBAL_Control
0x180005607  lea     rax, WPP_GLOBAL_Control
0x18000560e  cmp     rcx, rax
0x180005611  jz      short loc_18000568B
0x180005613  test    dword ptr [rcx+1Ch], 40000h
0x18000561a  jz      short loc_18000568B
0x18000561c  mov     rcx, [rcx+10h]
0x180005620  lea     r9, [rsp+6B8h+FileName]
0x180005628  mov     edx, 1Eh
0x18000562d  mov     dword ptr [rsp+6B8h+var_698], edi
0x180005631  call    WPP_SF_Sd
0x180005636  jmp     short loc_18000568B
0x180005638  xor     edi, edi
0x18000563a  lea     rdx, [rsp+6B8h+FileName]
0x180005642  mov     eax, 7FFFFFFEh
0x180005647  test    rax, rax
0x18000564a  jz      short loc_180005668
0x18000564c  movzx   ecx, word ptr [rdx]
0x18000564f  test    cx, cx
0x180005652  jz      short loc_180005668
0x180005654  mov     [rsi], cx
0x180005657  add     rdx, 2
0x18000565b  add     rsi, 2
0x18000565f  dec     rax
0x180005662  sub     rbx, 1
0x180005666  jnz     short loc_180005647
0x180005668  test    rbx, rbx
0x18000566b  lea     rcx, [rsi-2]
0x18000566f  cmovnz  rcx, rsi
0x180005673  xor     eax, eax
0x180005675  mov     [rcx], ax
0x180005678  test    rbx, rbx
0x18000567b  jnz     short loc_180005682
0x18000567d  mov     edi, 7Ah ; 'z'
0x180005682  mov     rcx, r8; hFindFile
0x180005685  call    cs:__imp_FindClose
0x18000568b  mov     ecx, edi; dwErrCode
0x18000568d  call    cs:__imp_SetLastError
0x180005693  xor     eax, eax
0x180005695  test    edi, edi
0x180005697  setz    al
0x18000569a  mov     rcx, [rsp+6B8h+var_18]
0x1800056a2  xor     rcx, rsp; StackCookie
0x1800056a5  call    __security_check_cookie
0x1800056aa  lea     r11, [rsp+6B8h+var_8]
0x1800056b2  mov     rbx, [r11+18h]
0x1800056b6  mov     rsi, [r11+20h]
0x1800056ba  mov     rsp, r11
0x1800056bd  pop     rdi
0x1800056be  retn
```
