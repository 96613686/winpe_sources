# AsrWriteXmlToSifFile(ushort *,ushort *)

- ea: `0x14005cd48`
- end: `0x14005cfba`
- name: `?AsrWriteXmlToSifFile@@YAHPEAG0@Z`
- size: `626`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, _WORD *lpBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x140079a50`

## callees

- `0x140021ca0`
- `0x1400235a8`
- `0x14005cd48`
- `0x1400d257c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005cf9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005cf9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ce3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ce64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cf00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cf21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cf31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cf52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ce3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ce64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cf00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cf21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cf31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cf52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005cf8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005cf8b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14005ce26`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14005ce26`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14005ceb1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14005cee0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14005ceb1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14005cee0`

## string_xrefs

- `0x14005cd60`: `AsrWriteXmlToSifFile`
- `0x14005cf91`: `AsrWriteXmlToSifFile`
- `0x14005cdfd`: `pwszXmlDoc`
- `0x14005cda8`: `pwszXmlFilename`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AsrWriteXmlToSifFile(LPCWSTR lpFileName, _WORD *lpBuffer)
{
  unsigned int v4; // ebx
  DWORD LastError; // edi
  struct _DRIVE_LAYOUT_INFORMATION_EX *v6; // rcx
  int v7; // edx
  const char *v8; // rax
  HANDLE FileW; // rax
  __int64 v10; // rbx
  void *v11; // rsi
  DWORD v12; // eax
  __int64 v13; // rax
  int v14; // ebp
  DWORD v15; // ebx
  DWORD v16; // eax
  int v17; // edx
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  TraceFunctionEnter(L"AsrWriteXmlToSifFile");
  NumberOfBytesWritten = 0;
  if ( !lpFileName )
  {
    v4 = 0;
    LastError = 87;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v7 = 101;
      v8 = "pwszXmlFilename";
LABEL_5:
      WPP_SF_Ds(
        *(_QWORD *)v6->Gpt.DiskId.Data4,
        v7,
        (unsigned int)WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids,
        87,
        (__int64)v8);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  if ( lpBuffer )
  {
    FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0, 0);
    v10 = -1;
    v11 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v4 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v12 = GetLastError();
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          103,
          (unsigned int)WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids,
          v12,
          (__int64)"GetLastError()");
      }
      goto LABEL_32;
    }
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)qword_14014F4D0 + v13) );
    v14 = 2 * v13;
    if ( WriteFile(v11, qword_14014F4D0, 2 * v13, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == v14 )
    {
      do
        ++v10;
      while ( lpBuffer[v10] );
      v15 = 2 * v10;
      if ( WriteFile(v11, lpBuffer, v15, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == v15 )
      {
        LastError = 0;
        v4 = 1;
        goto LABEL_30;
      }
      v4 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v16 = GetLastError();
        v17 = 105;
LABEL_29:
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          v17,
          (unsigned int)WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids,
          v16,
          (__int64)"GetLastError()");
      }
    }
    else
    {
      v4 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v16 = GetLastError();
        v17 = 104;
        goto LABEL_29;
      }
    }
LABEL_30:
    if ( v11 )
      CloseHandle(v11);
    goto LABEL_32;
  }
  v4 = 0;
  LastError = 87;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
  {
    v7 = 102;
    v8 = "pwszXmlDoc";
    goto LABEL_5;
  }
LABEL_32:
  TraceFunctionExit(L"AsrWriteXmlToSifFile");
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x14005cd48  mov     [rsp+arg_8], rbx
0x14005cd4d  mov     [rsp+arg_10], rbp
0x14005cd52  push    rsi
0x14005cd53  push    rdi
0x14005cd54  push    r14
0x14005cd56  sub     rsp, 40h
0x14005cd5a  mov     rdi, rdx
0x14005cd5d  mov     rbx, rcx
0x14005cd60  lea     rcx, aAsrwritexmltos; "AsrWriteXmlToSifFile"
0x14005cd67  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x14005cd6c  xor     r14d, r14d
0x14005cd6f  mov     [rsp+58h+NumberOfBytesWritten], r14d
0x14005cd74  test    rbx, rbx
0x14005cd77  jnz     short loc_14005CDC9
0x14005cd79  lea     r9d, [r14+57h]
0x14005cd7d  mov     ebx, r14d
0x14005cd80  mov     edi, r9d
0x14005cd83  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cd8a  lea     rax, WPP_GLOBAL_Control
0x14005cd91  cmp     rcx, rax
0x14005cd94  jz      loc_14005CF91
0x14005cd9a  test    byte ptr [rcx+1Ch], 8
0x14005cd9e  jz      loc_14005CF91
0x14005cda4  lea     edx, [r14+65h]
0x14005cda8  lea     rax, aPwszxmlfilenam; "pwszXmlFilename"
0x14005cdaf  mov     qword ptr [rsp+58h+dwCreationDisposition], rax
0x14005cdb4  mov     rcx, [rcx+10h]
0x14005cdb8  lea     r8, WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids
0x14005cdbf  call    WPP_SF_Ds
0x14005cdc4  jmp     loc_14005CF91
0x14005cdc9  test    rdi, rdi
0x14005cdcc  jnz     short loc_14005CE06
0x14005cdce  lea     r9d, [rdi+57h]
0x14005cdd2  mov     ebx, r14d
0x14005cdd5  mov     edi, r9d
0x14005cdd8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cddf  lea     rax, WPP_GLOBAL_Control
0x14005cde6  cmp     rcx, rax
0x14005cde9  jz      loc_14005CF91
0x14005cdef  test    byte ptr [rcx+1Ch], 8
0x14005cdf3  jz      loc_14005CF91
0x14005cdf9  lea     edx, [r9+0Fh]
0x14005cdfd  lea     rax, aPwszxmldoc; "pwszXmlDoc"
0x14005ce04  jmp     short loc_14005CDAF
0x14005ce06  mov     [rsp+58h+hTemplateFile], r14; hTemplateFile
0x14005ce0b  xor     r9d, r9d; lpSecurityAttributes
0x14005ce0e  mov     [rsp+58h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x14005ce13  xor     r8d, r8d; dwShareMode
0x14005ce16  mov     edx, 40000000h; dwDesiredAccess
0x14005ce1b  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x14005ce23  mov     rcx, rbx; lpFileName
0x14005ce26  call    cs:__imp_CreateFileW
0x14005ce2c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14005ce30  mov     rsi, rax
0x14005ce33  cmp     rax, rbx
0x14005ce36  jnz     short loc_14005CE8A
0x14005ce38  mov     ebx, r14d
0x14005ce3b  call    cs:__imp_GetLastError
0x14005ce41  mov     edi, eax
0x14005ce43  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ce4a  lea     rax, WPP_GLOBAL_Control
0x14005ce51  cmp     rcx, rax
0x14005ce54  jz      loc_14005CF91
0x14005ce5a  test    byte ptr [rcx+1Ch], 8
0x14005ce5e  jz      loc_14005CF91
0x14005ce64  call    cs:__imp_GetLastError
0x14005ce6a  lea     rcx, aGetlasterror_1; "GetLastError()"
0x14005ce71  mov     edx, 67h ; 'g'
0x14005ce76  mov     qword ptr [rsp+58h+dwCreationDisposition], rcx
0x14005ce7b  mov     r9d, eax
0x14005ce7e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ce85  jmp     loc_14005CDB4
0x14005ce8a  lea     rdx, qword_14014F4D0; lpBuffer
0x14005ce91  mov     rax, rbx
0x14005ce94  inc     rax
0x14005ce97  cmp     [rdx+rax*2], r14w
0x14005ce9c  jnz     short loc_14005CE94
0x14005ce9e  lea     ebp, [rax+rax]
0x14005cea1  mov     qword ptr [rsp+58h+dwCreationDisposition], r14; lpOverlapped
0x14005cea6  mov     r8d, ebp; nNumberOfBytesToWrite
0x14005cea9  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14005ceae  mov     rcx, rsi; hFile
0x14005ceb1  call    cs:__imp_WriteFile
0x14005ceb7  test    eax, eax
0x14005ceb9  jz      short loc_14005CF2E
0x14005cebb  cmp     [rsp+58h+NumberOfBytesWritten], ebp
0x14005cebf  jnz     short loc_14005CF2E
0x14005cec1  inc     rbx
0x14005cec4  cmp     [rdi+rbx*2], r14w
0x14005cec9  jnz     short loc_14005CEC1
0x14005cecb  add     ebx, ebx
0x14005cecd  mov     qword ptr [rsp+58h+dwCreationDisposition], r14; lpOverlapped
0x14005ced2  mov     r8d, ebx; nNumberOfBytesToWrite
0x14005ced5  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14005ceda  mov     rdx, rdi; lpBuffer
0x14005cedd  mov     rcx, rsi; hFile
0x14005cee0  call    cs:__imp_WriteFile
0x14005cee6  test    eax, eax
0x14005cee8  jz      short loc_14005CEFD
0x14005ceea  cmp     [rsp+58h+NumberOfBytesWritten], ebx
0x14005ceee  jnz     short loc_14005CEFD
0x14005cef0  mov     edi, r14d
0x14005cef3  mov     ebx, 1
0x14005cef8  jmp     loc_14005CF83
0x14005cefd  mov     ebx, r14d
0x14005cf00  call    cs:__imp_GetLastError
0x14005cf06  mov     edi, eax
0x14005cf08  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cf0f  lea     rax, WPP_GLOBAL_Control
0x14005cf16  cmp     rcx, rax
0x14005cf19  jz      short loc_14005CF83
0x14005cf1b  test    byte ptr [rcx+1Ch], 8
0x14005cf1f  jz      short loc_14005CF83
0x14005cf21  call    cs:__imp_GetLastError
0x14005cf27  mov     edx, 69h ; 'i'
0x14005cf2c  jmp     short loc_14005CF5D
0x14005cf2e  mov     ebx, r14d
0x14005cf31  call    cs:__imp_GetLastError
0x14005cf37  mov     edi, eax
0x14005cf39  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cf40  lea     rax, WPP_GLOBAL_Control
0x14005cf47  cmp     rcx, rax
0x14005cf4a  jz      short loc_14005CF83
0x14005cf4c  test    byte ptr [rcx+1Ch], 8
0x14005cf50  jz      short loc_14005CF83
0x14005cf52  call    cs:__imp_GetLastError
0x14005cf58  mov     edx, 68h ; 'h'
0x14005cf5d  lea     rcx, aGetlasterror_1; "GetLastError()"
0x14005cf64  mov     r9d, eax
0x14005cf67  mov     qword ptr [rsp+58h+dwCreationDisposition], rcx
0x14005cf6c  lea     r8, WPP_9f6f5f2f4cf839682710d165eb126bc6_Traceguids
0x14005cf73  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cf7a  mov     rcx, [rcx+10h]
0x14005cf7e  call    WPP_SF_Ds
0x14005cf83  test    rsi, rsi
0x14005cf86  jz      short loc_14005CF91
0x14005cf88  mov     rcx, rsi; hObject
0x14005cf8b  call    cs:__imp_CloseHandle
0x14005cf91  lea     rcx, aAsrwritexmltos; "AsrWriteXmlToSifFile"
0x14005cf98  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x14005cf9d  mov     ecx, edi; dwErrCode
0x14005cf9f  call    cs:__imp_SetLastError
0x14005cfa5  mov     rbp, [rsp+58h+arg_10]
0x14005cfaa  mov     eax, ebx
0x14005cfac  mov     rbx, [rsp+58h+arg_8]
0x14005cfb1  add     rsp, 40h
0x14005cfb5  pop     r14
0x14005cfb7  pop     rdi
0x14005cfb8  pop     rsi
0x14005cfb9  retn
```
