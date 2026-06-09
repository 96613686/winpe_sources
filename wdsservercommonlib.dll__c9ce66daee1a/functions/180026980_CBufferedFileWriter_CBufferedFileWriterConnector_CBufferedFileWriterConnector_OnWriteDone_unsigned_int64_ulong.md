# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::OnAllWritesDone(void)

- ea: `0x180026980`
- end: `0x180026aca`
- name: `?OnAllWritesDone@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKXZ`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026450`

## callees

- `0x180026980`
- `0x180027294`
- `0x180027390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800269bb`
- `KERNEL32!GetLastError` at `0x180026a5b`
- `KERNEL32!GetLastError` at `0x180026a86`
- `KERNEL32!GetLastError` at `0x1800269bb`
- `KERNEL32!GetLastError` at `0x180026a5b`
- `KERNEL32!GetLastError` at `0x180026a86`
- `KERNEL32!SetEndOfFile` at `0x180026a76`
- `KERNEL32!SetEndOfFile` at `0x180026a76`
- `KERNEL32!SetFilePointerEx` at `0x180026a4b`
- `KERNEL32!SetFilePointerEx` at `0x180026a4b`
- `KERNEL32!GetFileSizeEx` at `0x1800269ab`
- `KERNEL32!GetFileSizeEx` at `0x1800269ab`

## string_xrefs

- `0x1800269cf`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x180026a98`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`

## pseudocode

```c
__int64 __fastcall CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::OnAllWritesDone(
        __int64 a1)
{
  void *v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // r8
  DWORD LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // r9
  union _LARGE_INTEGER v9; // rsi
  int v10; // edi
  LARGE_INTEGER v11; // rdx
  void *v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // eax
  union _LARGE_INTEGER FileSize; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(void **)(a1 + 48);
  v3 = 0;
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(v2, &FileSize) )
  {
    LastError = GetLastError();
    v8 = 1018;
    goto LABEL_3;
  }
  v9 = FileSize;
  if ( FileSize.QuadPart < 0 )
  {
    v9.QuadPart = -1;
    v10 = -2147024362;
  }
  else
  {
    v10 = 0;
  }
  if ( (int)ElValidateHr_8((unsigned int)v10, v4, v5, 1022) < 0 )
  {
    if ( v10 >= 0 )
      return (unsigned int)v10;
    else
      return (unsigned __int16)v10;
  }
  v11 = *(LARGE_INTEGER *)(a1 + 56);
  if ( v9.QuadPart == v11.QuadPart )
    return v3;
  v12 = *(void **)(a1 + 48);
  FileSize = *(union _LARGE_INTEGER *)(a1 + 56);
  if ( !SetFilePointerEx(v12, v11, 0, 0) )
  {
    LastError = GetLastError();
    v8 = 1040;
LABEL_3:
    v3 = ElValidateWin32_14(LastError, v7, "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h", v8);
    if ( !v3 )
      return 31;
    return v3;
  }
  if ( !SetEndOfFile(*(HANDLE *)(a1 + 48)) )
  {
    v13 = GetLastError();
    v15 = ElValidateWin32_14(v13, v14, "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h", 1045);
    if ( !v15 )
      return 31;
    return v15;
  }
  return v3;
}

```

## disassembly

```asm
0x180026980  mov     rax, rsp
0x180026983  mov     [rax+10h], rbx
0x180026987  mov     [rax+18h], rbp
0x18002698b  mov     [rax+20h], rsi
0x18002698f  push    rdi
0x180026990  sub     rsp, 20h
0x180026994  mov     rbp, rcx
0x180026997  lea     rdx, [rsp+28h+FileSize]; lpFileSize
0x18002699c  mov     rcx, [rcx+30h]; hFile
0x1800269a0  xor     ebx, ebx
0x1800269a2  and     [rax+8], ebx
0x1800269a5  xor     eax, eax
0x1800269a7  mov     dword ptr [rsp+28h+FileSize+4], eax
0x1800269ab  call    cs:__imp_GetFileSizeEx
0x1800269b2  nop     dword ptr [rax+rax+00h]
0x1800269b7  test    eax, eax
0x1800269b9  jnz     short loc_1800269ED
0x1800269bb  call    cs:__imp_GetLastError
0x1800269c2  nop     dword ptr [rax+rax+00h]
0x1800269c7  mov     r9d, 3FAh
0x1800269cd  mov     ecx, eax
0x1800269cf  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800269d6  call    ElValidateWin32_14
0x1800269db  mov     ebx, eax
0x1800269dd  test    eax, eax
0x1800269df  jnz     loc_180026AB2
0x1800269e5  lea     ebx, [rax+1Fh]
0x1800269e8  jmp     loc_180026AB2
0x1800269ed  mov     rsi, qword ptr [rsp+28h+FileSize]
0x1800269f2  test    rsi, rsi
0x1800269f5  js      short loc_1800269FB
0x1800269f7  xor     edi, edi
0x1800269f9  jmp     short loc_180026A04
0x1800269fb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800269ff  mov     edi, 80070216h
0x180026a04  mov     r9d, 3FEh
0x180026a0a  mov     ecx, edi
0x180026a0c  call    ElValidateHr_8
0x180026a11  test    eax, eax
0x180026a13  jns     short loc_180026A33
0x180026a15  test    edi, edi
0x180026a17  jns     short loc_180026A2F
0x180026a19  mov     eax, edi
0x180026a1b  and     eax, 1FFF0000h
0x180026a20  cmp     eax, 70000h
0x180026a25  jnz     short loc_180026A2F
0x180026a27  movzx   ebx, di
0x180026a2a  jmp     loc_180026AB2
0x180026a2f  mov     ebx, edi
0x180026a31  jmp     short loc_180026AB2
0x180026a33  mov     rdx, [rbp+38h]; liDistanceToMove
0x180026a37  cmp     rsi, rdx
0x180026a3a  jz      short loc_180026AB2
0x180026a3c  mov     rcx, [rbp+30h]; hFile
0x180026a40  xor     r9d, r9d; dwMoveMethod
0x180026a43  xor     r8d, r8d; lpNewFilePointer
0x180026a46  mov     qword ptr [rsp+28h+FileSize], rdx
0x180026a4b  call    cs:__imp_SetFilePointerEx
0x180026a52  nop     dword ptr [rax+rax+00h]
0x180026a57  test    eax, eax
0x180026a59  jnz     short loc_180026A72
0x180026a5b  call    cs:__imp_GetLastError
0x180026a62  nop     dword ptr [rax+rax+00h]
0x180026a67  mov     r9d, 410h
0x180026a6d  jmp     loc_1800269CD
0x180026a72  mov     rcx, [rbp+30h]; hFile
0x180026a76  call    cs:__imp_SetEndOfFile
0x180026a7d  nop     dword ptr [rax+rax+00h]
0x180026a82  test    eax, eax
0x180026a84  jnz     short loc_180026AB2
0x180026a86  call    cs:__imp_GetLastError
0x180026a8d  nop     dword ptr [rax+rax+00h]
0x180026a92  mov     r9d, 415h
0x180026a98  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180026a9f  mov     ecx, eax
0x180026aa1  call    ElValidateWin32_14
0x180026aa6  mov     ebx, 1Fh
0x180026aab  test    eax, eax
0x180026aad  cmovz   eax, ebx
0x180026ab0  mov     ebx, eax
0x180026ab2  mov     rbp, [rsp+28h+arg_10]
0x180026ab7  mov     eax, ebx
0x180026ab9  mov     rbx, [rsp+28h+arg_8]
0x180026abe  mov     rsi, [rsp+28h+arg_18]
0x180026ac3  add     rsp, 20h
0x180026ac7  pop     rdi
0x180026ac8  retn
```
