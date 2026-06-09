# CSQMUtil::CloseSQMSession(void)

- ea: `0x180017c4c`
- end: `0x180017e2d`
- name: `?CloseSQMSession@CSQMUtil@@SAJXZ`
- size: `481`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180019d10`
- `0x1800417cc`

## callees

- `0x180003f30`
- `0x180017b30`
- `0x180017c4c`
- `0x18001a280`
- `0x18001a8d0`
- `0x18001ad5c`
- `0x180040b20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d82`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180017d78`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180017d78`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180017d3e`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180017d3e`
- `SQMAPI!SqmEndSession` at `0x180017cf2`
- `SQMAPI!SqmEndSession` at `0x180017cf2`
- `RPCRT4!RpcStringFreeW` at `0x180017dc3`
- `RPCRT4!RpcStringFreeW` at `0x180017dc3`

## string_xrefs

- `0x180017da1`: `DeleteFile() failed: 0x%x in %s`

## pseudocode

```c
__int64 CSQMUtil::CloseSQMSession(void)
{
  void *v0; // rdi
  int v1; // eax
  unsigned int v2; // ebx
  signed int LastError; // eax
  signed int v4; // eax
  RPC_STATUS v5; // eax
  void *Block; // [rsp+30h] [rbp-A38h] BYREF
  _BYTE v8[528]; // [rsp+40h] [rbp-A28h] BYREF
  WCHAR FileName[1024]; // [rsp+250h] [rbp-818h] BYREF

  v0 = 0;
  Block = 0;
  memset_0(FileName, 0, sizeof(FileName));
  memset_0(v8, 0, 0x208u);
  if ( CSQMUtil::m_hSQMSession )
  {
    v1 = CSQMUtil::BuildUploadFileNameStr((unsigned __int16 **)&Block);
    v2 = v1;
    if ( v1 < 0 )
    {
      _DbgPrintMessage(8, "BuildUploadFileNameStr() failed: 0x%x in %s", v1, "CSQMUtil::CloseSQMSession");
      v0 = Block;
      goto LABEL_20;
    }
    v0 = Block;
    if ( !(unsigned int)SqmEndSession(CSQMUtil::m_hSQMSession, Block, 1, 25) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      _DbgPrintMessage(4, "SqmEndSession() failed: 0x%x in %s", LastError, "CSQMUtil::CloseSQMSession");
    }
    CSQMUtil::m_hSQMSession = 0;
  }
  GetTempPath2W(260, v8);
  v2 = StringCchPrintfW(FileName, 0x400u, L"%s%s.sqm", v8, L"tsSessEnv");
  if ( !DeleteFileW(FileName) )
  {
    v4 = GetLastError();
    v2 = v4;
    if ( v4 > 0 )
      v2 = (unsigned __int16)v4 | 0x80070000;
    _DbgPrintMessage(4, "DeleteFile() failed: 0x%x in %s", v2, "CSQMUtil::CloseSQMSession");
  }
  if ( CSQMUtil::m_pMachineIdStr )
  {
    v5 = RpcStringFreeW(&CSQMUtil::m_pMachineIdStr);
    if ( v5 )
    {
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
      else
        v2 = v5;
      _DbgPrintMessage(8, "UserId: UuidToString FAILED with error 0x%x", v5);
    }
    else
    {
      CSQMUtil::m_pMachineIdStr = 0;
    }
  }
LABEL_20:
  if ( v0 )
    operator delete(v0);
  return v2;
}

```

## disassembly

```asm
0x180017c4c  mov     [rsp+arg_0], rbx
0x180017c51  push    rdi
0x180017c52  sub     rsp, 0A60h
0x180017c59  mov     rax, cs:__security_cookie
0x180017c60  xor     rax, rsp
0x180017c63  mov     [rsp+0A68h+var_18], rax
0x180017c6b  xor     edi, edi
0x180017c6d  lea     rcx, [rsp+0A68h+FileName]; void *
0x180017c75  xor     edx, edx; Val
0x180017c77  mov     [rsp+0A68h+Block], rdi
0x180017c7c  mov     r8d, 800h; Size
0x180017c82  call    memset_0
0x180017c87  xor     edx, edx; Val
0x180017c89  lea     rcx, [rsp+0A68h+var_A28]; void *
0x180017c8e  mov     r8d, 208h; Size
0x180017c94  call    memset_0
0x180017c99  cmp     cs:?m_hSQMSession@CSQMUtil@@0PEAUHSQMSESSION__@@EA, rdi; HSQMSESSION__ * CSQMUtil::m_hSQMSession
0x180017ca0  jz      loc_180017D34
0x180017ca6  lea     rcx, [rsp+0A68h+Block]; unsigned __int16 **
0x180017cab  call    ?BuildUploadFileNameStr@CSQMUtil@@CAJPEAPEAG@Z; CSQMUtil::BuildUploadFileNameStr(ushort * *)
0x180017cb0  mov     ebx, eax
0x180017cb2  test    eax, eax
0x180017cb4  jns     short loc_180017CD9
0x180017cb6  lea     r9, aCsqmutilCloses; "CSQMUtil::CloseSQMSession"
0x180017cbd  mov     r8d, eax
0x180017cc0  lea     rdx, aBuilduploadfil; "BuildUploadFileNameStr() failed: 0x%x i"...
0x180017cc7  lea     ecx, [rdi+8]; int
0x180017cca  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017ccf  mov     rdi, [rsp+0A68h+Block]
0x180017cd4  jmp     loc_180017DFD
0x180017cd9  mov     rdi, [rsp+0A68h+Block]
0x180017cde  mov     r9d, 19h
0x180017ce4  mov     rcx, cs:?m_hSQMSession@CSQMUtil@@0PEAUHSQMSESSION__@@EA; HSQMSESSION__ * CSQMUtil::m_hSQMSession
0x180017ceb  mov     rdx, rdi
0x180017cee  lea     r8d, [r9-18h]
0x180017cf2  call    cs:__imp_SqmEndSession
0x180017cf8  test    eax, eax
0x180017cfa  jnz     short loc_180017D29
0x180017cfc  call    cs:__imp_GetLastError
0x180017d02  test    eax, eax
0x180017d04  jle     short loc_180017D0E
0x180017d06  movzx   eax, ax
0x180017d09  or      eax, 80070000h
0x180017d0e  lea     r9, aCsqmutilCloses; "CSQMUtil::CloseSQMSession"
0x180017d15  mov     r8d, eax
0x180017d18  lea     rdx, aSqmendsessionF; "SqmEndSession() failed: 0x%x in %s"
0x180017d1f  mov     ecx, 4; int
0x180017d24  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017d29  mov     cs:?m_hSQMSession@CSQMUtil@@0PEAUHSQMSESSION__@@EA, 0; HSQMSESSION__ * CSQMUtil::m_hSQMSession
0x180017d34  lea     rdx, [rsp+0A68h+var_A28]
0x180017d39  mov     ecx, 104h
0x180017d3e  call    cs:__imp_GetTempPath2W
0x180017d44  lea     rax, aTssessenv; "tsSessEnv"
0x180017d4b  mov     edx, 400h; unsigned __int64
0x180017d50  lea     r9, [rsp+0A68h+var_A28]
0x180017d55  mov     [rsp+0A68h+var_A48], rax
0x180017d5a  lea     r8, aSSSqm; "%s%s.sqm"
0x180017d61  lea     rcx, [rsp+0A68h+FileName]; unsigned __int16 *
0x180017d69  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017d6e  lea     rcx, [rsp+0A68h+FileName]; lpFileName
0x180017d76  mov     ebx, eax
0x180017d78  call    cs:__imp_DeleteFileW
0x180017d7e  test    eax, eax
0x180017d80  jnz     short loc_180017DB2
0x180017d82  call    cs:__imp_GetLastError
0x180017d88  mov     ebx, eax
0x180017d8a  test    eax, eax
0x180017d8c  jle     short loc_180017D97
0x180017d8e  movzx   ebx, ax
0x180017d91  or      ebx, 80070000h
0x180017d97  lea     r9, aCsqmutilCloses; "CSQMUtil::CloseSQMSession"
0x180017d9e  mov     r8d, ebx
0x180017da1  lea     rdx, aDeletefileFail_0; "DeleteFile() failed: 0x%x in %s"
0x180017da8  mov     ecx, 4; int
0x180017dad  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017db2  cmp     cs:?m_pMachineIdStr@CSQMUtil@@0PEAGEA, 0; ushort * CSQMUtil::m_pMachineIdStr
0x180017dba  jz      short loc_180017DFD
0x180017dbc  lea     rcx, ?m_pMachineIdStr@CSQMUtil@@0PEAGEA; String
0x180017dc3  call    cs:__imp_RpcStringFreeW
0x180017dc9  test    eax, eax
0x180017dcb  jz      short loc_180017DF2
0x180017dcd  jg      short loc_180017DD3
0x180017dcf  mov     ebx, eax
0x180017dd1  jmp     short loc_180017DDC
0x180017dd3  movzx   ebx, ax
0x180017dd6  or      ebx, 80070000h
0x180017ddc  mov     r8d, eax
0x180017ddf  lea     rdx, aUseridUuidtost; "UserId: UuidToString FAILED with error "...
0x180017de6  mov     ecx, 8; int
0x180017deb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017df0  jmp     short loc_180017DFD
0x180017df2  mov     cs:?m_pMachineIdStr@CSQMUtil@@0PEAGEA, 0; ushort * CSQMUtil::m_pMachineIdStr
0x180017dfd  test    rdi, rdi
0x180017e00  jz      short loc_180017E0A
0x180017e02  mov     rcx, rdi; Block
0x180017e05  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017e0a  mov     eax, ebx
0x180017e0c  mov     rcx, [rsp+0A68h+var_18]
0x180017e14  xor     rcx, rsp; StackCookie
0x180017e17  call    __security_check_cookie
0x180017e1c  mov     rbx, [rsp+0A68h+arg_0]
0x180017e24  add     rsp, 0A60h
0x180017e2b  pop     rdi
0x180017e2c  retn
```
