# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::OnAllWritesDone(void)

- ea: `0x180027ac0`
- end: `0x180027c0a`
- name: `?OnAllWritesDone@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKXZ`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027580`

## callees

- `0x180027ac0`
- `0x1800283e4`
- `0x1800284e0`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x180027b8b`
- `KERNEL32!SetFilePointerEx` at `0x180027b8b`
- `KERNEL32!SetEndOfFile` at `0x180027bb6`
- `KERNEL32!SetEndOfFile` at `0x180027bb6`
- `KERNEL32!GetLastError` at `0x180027afb`
- `KERNEL32!GetLastError` at `0x180027b9b`
- `KERNEL32!GetLastError` at `0x180027bc6`
- `KERNEL32!GetLastError` at `0x180027afb`
- `KERNEL32!GetLastError` at `0x180027b9b`
- `KERNEL32!GetLastError` at `0x180027bc6`
- `KERNEL32!GetFileSizeEx` at `0x180027aeb`
- `KERNEL32!GetFileSizeEx` at `0x180027aeb`

## string_xrefs

- `0x180027b0f`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x180027bd8`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`

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
0x180027ac0  mov     rax, rsp
0x180027ac3  mov     [rax+10h], rbx
0x180027ac7  mov     [rax+18h], rbp
0x180027acb  mov     [rax+20h], rsi
0x180027acf  push    rdi
0x180027ad0  sub     rsp, 20h
0x180027ad4  mov     rbp, rcx
0x180027ad7  lea     rdx, [rsp+28h+FileSize]; lpFileSize
0x180027adc  mov     rcx, [rcx+30h]; hFile
0x180027ae0  xor     ebx, ebx
0x180027ae2  and     [rax+8], ebx
0x180027ae5  xor     eax, eax
0x180027ae7  mov     dword ptr [rsp+28h+FileSize+4], eax
0x180027aeb  call    cs:__imp_GetFileSizeEx
0x180027af2  nop     dword ptr [rax+rax+00h]
0x180027af7  test    eax, eax
0x180027af9  jnz     short loc_180027B2D
0x180027afb  call    cs:__imp_GetLastError
0x180027b02  nop     dword ptr [rax+rax+00h]
0x180027b07  mov     r9d, 3FAh
0x180027b0d  mov     ecx, eax
0x180027b0f  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180027b16  call    ElValidateWin32_14
0x180027b1b  mov     ebx, eax
0x180027b1d  test    eax, eax
0x180027b1f  jnz     loc_180027BF2
0x180027b25  lea     ebx, [rax+1Fh]
0x180027b28  jmp     loc_180027BF2
0x180027b2d  mov     rsi, qword ptr [rsp+28h+FileSize]
0x180027b32  test    rsi, rsi
0x180027b35  js      short loc_180027B3B
0x180027b37  xor     edi, edi
0x180027b39  jmp     short loc_180027B44
0x180027b3b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180027b3f  mov     edi, 80070216h
0x180027b44  mov     r9d, 3FEh
0x180027b4a  mov     ecx, edi
0x180027b4c  call    ElValidateHr_8
0x180027b51  test    eax, eax
0x180027b53  jns     short loc_180027B73
0x180027b55  test    edi, edi
0x180027b57  jns     short loc_180027B6F
0x180027b59  mov     eax, edi
0x180027b5b  and     eax, 1FFF0000h
0x180027b60  cmp     eax, 70000h
0x180027b65  jnz     short loc_180027B6F
0x180027b67  movzx   ebx, di
0x180027b6a  jmp     loc_180027BF2
0x180027b6f  mov     ebx, edi
0x180027b71  jmp     short loc_180027BF2
0x180027b73  mov     rdx, [rbp+38h]; liDistanceToMove
0x180027b77  cmp     rsi, rdx
0x180027b7a  jz      short loc_180027BF2
0x180027b7c  mov     rcx, [rbp+30h]; hFile
0x180027b80  xor     r9d, r9d; dwMoveMethod
0x180027b83  xor     r8d, r8d; lpNewFilePointer
0x180027b86  mov     qword ptr [rsp+28h+FileSize], rdx
0x180027b8b  call    cs:__imp_SetFilePointerEx
0x180027b92  nop     dword ptr [rax+rax+00h]
0x180027b97  test    eax, eax
0x180027b99  jnz     short loc_180027BB2
0x180027b9b  call    cs:__imp_GetLastError
0x180027ba2  nop     dword ptr [rax+rax+00h]
0x180027ba7  mov     r9d, 410h
0x180027bad  jmp     loc_180027B0D
0x180027bb2  mov     rcx, [rbp+30h]; hFile
0x180027bb6  call    cs:__imp_SetEndOfFile
0x180027bbd  nop     dword ptr [rax+rax+00h]
0x180027bc2  test    eax, eax
0x180027bc4  jnz     short loc_180027BF2
0x180027bc6  call    cs:__imp_GetLastError
0x180027bcd  nop     dword ptr [rax+rax+00h]
0x180027bd2  mov     r9d, 415h
0x180027bd8  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180027bdf  mov     ecx, eax
0x180027be1  call    ElValidateWin32_14
0x180027be6  mov     ebx, 1Fh
0x180027beb  test    eax, eax
0x180027bed  cmovz   eax, ebx
0x180027bf0  mov     ebx, eax
0x180027bf2  mov     rbp, [rsp+28h+arg_10]
0x180027bf7  mov     eax, ebx
0x180027bf9  mov     rbx, [rsp+28h+arg_8]
0x180027bfe  mov     rsi, [rsp+28h+arg_18]
0x180027c03  add     rsp, 20h
0x180027c07  pop     rdi
0x180027c08  retn
```
