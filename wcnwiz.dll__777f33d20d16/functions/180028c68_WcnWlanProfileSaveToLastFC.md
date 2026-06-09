# WcnWlanProfileSaveToLastFC

- ea: `0x180028c68`
- end: `0x180028fbe`
- name: `WcnWlanProfileSaveToLastFC`
- size: `854`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180028b30`

## callees

- `0x180001820`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18001bc88`
- `0x180028a00`
- `0x180028c68`
- `0x18002de1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ee7`
- `KERNEL32!LocalFree` at `0x180028f3f`
- `KERNEL32!LocalFree` at `0x180028f3f`
- `KERNEL32!CreateFileW` at `0x180028e35`
- `KERNEL32!CreateFileW` at `0x180028e35`
- `KERNEL32!CloseHandle` at `0x180028f54`
- `KERNEL32!CloseHandle` at `0x180028f54`
- `KERNEL32!WriteFile` at `0x180028ec9`
- `KERNEL32!WriteFile` at `0x180028ec9`
- `CRYPT32!CryptProtectData` at `0x180028d6d`
- `CRYPT32!CryptProtectData` at `0x180028d6d`

## string_xrefs

- `0x180028d0d`: `wszWlanXmlProfile`

## pseudocode

```c
__int64 __fastcall WcnWlanProfileSaveToLastFC(BYTE *a1)
{
  _QWORD *v2; // r10
  const char *Indent; // rax
  __int64 v4; // r10
  __int64 v6; // rdi
  __int64 v7; // rax
  unsigned int LastError; // ebx
  signed int v9; // ebx
  _BYTE *v10; // r10
  unsigned int v11; // eax
  __int64 v12; // r10
  int v13; // edx
  int LastFcDirectory; // eax
  HANDLE FileW; // rax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  __int64 v18; // r10
  unsigned int v19; // ebx
  unsigned int v20; // eax
  __int64 v21; // r10
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  DATA_BLOB pDataOut; // [rsp+48h] [rbp-B8h] BYREF
  DATA_BLOB pDataIn; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF

  NumberOfBytesWritten = 0;
  pDataIn = 0;
  pDataOut = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 17, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, Indent);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 2u )
      WPP_SF_s(v2[2], 18, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, "wszWlanXmlProfile");
    return 2147500035LL;
  }
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&a1[2 * v7] );
  pDataIn.pbData = a1;
  pDataIn.cbData = 2 * v7 + 2;
  if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v9 = LastError | 0x80000000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_38;
    v11 = (unsigned int)GetIndent(0);
    v13 = 19;
    goto LABEL_36;
  }
  LastFcDirectory = WcnGetLastFcDirectory(FileName);
  v9 = LastFcDirectory;
  if ( LastFcDirectory >= 0 )
  {
    FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 6u, 0);
    v6 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      if ( (int)GetLastError() > 0 )
        v16 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v16 = GetLastError();
      v9 = v16 | 0x80000000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_38;
      v17 = (unsigned int)GetIndent(0);
      WPP_SF_sSd(
        *(_QWORD *)(v18 + 16),
        21,
        (unsigned int)WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids,
        v17,
        (__int64)FileName,
        v9);
      goto LABEL_37;
    }
    if ( !WriteFile(FileW, pDataOut.pbData, pDataOut.cbData, &NumberOfBytesWritten, 0) )
    {
      if ( (int)GetLastError() > 0 )
        v19 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v19 = GetLastError();
      v9 = v19 | 0x80000000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_38;
      v11 = (unsigned int)GetIndent(0);
      v13 = 22;
LABEL_36:
      WPP_SF_sd(*(_QWORD *)(v12 + 16), v13, (unsigned int)WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, v11, v9);
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_38;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids,
      (unsigned int)LastFcDirectory);
  }
LABEL_37:
  v10 = WPP_GLOBAL_Control;
LABEL_38:
  if ( pDataOut.pbData )
  {
    LocalFree(pDataOut.pbData);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v6 != -1 )
  {
    CloseHandle((HANDLE)v6);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control && (v9 < 0 || v10[25] >= 6u) )
  {
    v20 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v21 + 16), 23, (unsigned int)WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, v20, v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180028c68  mov     [rsp-8+arg_8], rbx
0x180028c6d  mov     [rsp-8+arg_10], rsi
0x180028c72  push    rbp
0x180028c73  push    rdi
0x180028c74  push    r12
0x180028c76  push    r14
0x180028c78  push    r15
0x180028c7a  lea     rbp, [rsp-190h]
0x180028c82  sub     rsp, 290h
0x180028c89  mov     rax, cs:__security_cookie
0x180028c90  xor     rax, rsp
0x180028c93  mov     [rbp+1B0h+var_30], rax
0x180028c9a  xor     esi, esi
0x180028c9c  xorps   xmm0, xmm0
0x180028c9f  xorps   xmm1, xmm1
0x180028ca2  mov     [rsp+2B0h+NumberOfBytesWritten], esi
0x180028ca6  movups  xmmword ptr [rsp+2B0h+pDataIn.cbData], xmm0
0x180028cab  mov     rbx, rcx
0x180028cae  movups  xmmword ptr [rsp+2B0h+var_268.cbData], xmm1
0x180028cb3  mov     r10, cs:WPP_GLOBAL_Control
0x180028cba  lea     r14, WPP_GLOBAL_Control
0x180028cc1  lea     r15, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x180028cc8  cmp     r10, r14
0x180028ccb  jz      short loc_180028CF5
0x180028ccd  cmp     byte ptr [r10+19h], 6
0x180028cd2  jb      short loc_180028CF5
0x180028cd4  lea     ecx, [rsi+1]; int
0x180028cd7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180028cdc  mov     rcx, [r10+10h]
0x180028ce0  lea     edx, [rsi+11h]
0x180028ce3  mov     r9, rax
0x180028ce6  mov     r8, r15
0x180028ce9  call    WPP_SF_s
0x180028cee  mov     r10, cs:WPP_GLOBAL_Control
0x180028cf5  test    rbx, rbx
0x180028cf8  jnz     short loc_180028D26
0x180028cfa  cmp     r10, r14
0x180028cfd  jz      short loc_180028D1C
0x180028cff  cmp     byte ptr [r10+19h], 2
0x180028d04  jb      short loc_180028D1C
0x180028d06  mov     rcx, [r10+10h]
0x180028d0a  lea     edx, [rbx+12h]
0x180028d0d  lea     r9, aWszwlanxmlprof; "wszWlanXmlProfile"
0x180028d14  mov     r8, r15
0x180028d17  call    WPP_SF_s
0x180028d1c  mov     eax, 80004003h
0x180028d21  jmp     loc_180028F93
0x180028d26  or      r12, 0FFFFFFFFFFFFFFFFh
0x180028d2a  mov     rdi, r12
0x180028d2d  mov     rax, r12
0x180028d30  inc     rax
0x180028d33  cmp     [rbx+rax*2], si
0x180028d37  jnz     short loc_180028D30
0x180028d39  lea     eax, ds:2[rax*2]
0x180028d40  mov     [rsp+2B0h+pDataIn.pbData], rbx
0x180028d45  mov     [rsp+2B0h+pDataIn.cbData], eax
0x180028d49  lea     rcx, [rsp+2B0h+pDataIn]; pDataIn
0x180028d4e  lea     rax, [rsp+2B0h+var_268]
0x180028d53  xor     r9d, r9d; pvReserved
0x180028d56  mov     [rsp+2B0h+pDataOut], rax; pDataOut
0x180028d5b  xor     r8d, r8d; pOptionalEntropy
0x180028d5e  mov     [rsp+2B0h+dwFlags], 1; dwFlags
0x180028d66  xor     edx, edx; szDataDescr
0x180028d68  mov     [rsp+2B0h+pPromptStruct], rsi; pPromptStruct
0x180028d6d  call    cs:__imp_CryptProtectData
0x180028d73  test    eax, eax
0x180028d75  jnz     short loc_180028DCC
0x180028d77  call    cs:__imp_GetLastError
0x180028d7d  test    eax, eax
0x180028d7f  jg      short loc_180028D8B
0x180028d81  call    cs:__imp_GetLastError
0x180028d87  mov     ebx, eax
0x180028d89  jmp     short loc_180028D9A
0x180028d8b  call    cs:__imp_GetLastError
0x180028d91  movzx   ebx, ax
0x180028d94  or      ebx, 80070000h
0x180028d9a  or      ebx, 80000000h
0x180028da0  mov     r10, cs:WPP_GLOBAL_Control
0x180028da7  cmp     r10, r14
0x180028daa  jz      loc_180028F35
0x180028db0  cmp     byte ptr [r10+19h], 2
0x180028db5  jb      loc_180028F35
0x180028dbb  xor     ecx, ecx; int
0x180028dbd  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180028dc2  mov     edx, 13h
0x180028dc7  jmp     loc_180028F1B
0x180028dcc  lea     rcx, [rsp+2B0h+FileName]; Buffer
0x180028dd1  call    ?WcnGetLastFcDirectory@@YAJPEAGK@Z; WcnGetLastFcDirectory(ushort *,ulong)
0x180028dd6  mov     ebx, eax
0x180028dd8  test    eax, eax
0x180028dda  jns     short loc_180028E10
0x180028ddc  mov     r10, cs:WPP_GLOBAL_Control
0x180028de3  cmp     r10, r14
0x180028de6  jz      loc_180028F35
0x180028dec  cmp     byte ptr [r10+19h], 2
0x180028df1  jb      loc_180028F35
0x180028df7  mov     rcx, [r10+10h]
0x180028dfb  mov     edx, 14h
0x180028e00  mov     r9d, eax
0x180028e03  mov     r8, r15
0x180028e06  call    WPP_SF_d
0x180028e0b  jmp     loc_180028F2E
0x180028e10  mov     [rsp+2B0h+pDataOut], rsi; hTemplateFile
0x180028e15  lea     rcx, [rsp+2B0h+FileName]; lpFileName
0x180028e1a  mov     [rsp+2B0h+dwFlags], 6; dwFlagsAndAttributes
0x180028e22  xor     r9d, r9d; lpSecurityAttributes
0x180028e25  xor     r8d, r8d; dwShareMode
0x180028e28  mov     dword ptr [rsp+2B0h+pPromptStruct], 2; dwCreationDisposition
0x180028e30  mov     edx, 40000000h; dwDesiredAccess
0x180028e35  call    cs:__imp_CreateFileW
0x180028e3b  mov     rdi, rax
0x180028e3e  cmp     rax, r12
0x180028e41  jnz     short loc_180028EB2
0x180028e43  call    cs:__imp_GetLastError
0x180028e49  test    eax, eax
0x180028e4b  jg      short loc_180028E57
0x180028e4d  call    cs:__imp_GetLastError
0x180028e53  mov     ebx, eax
0x180028e55  jmp     short loc_180028E66
0x180028e57  call    cs:__imp_GetLastError
0x180028e5d  movzx   ebx, ax
0x180028e60  or      ebx, 80070000h
0x180028e66  or      ebx, 80000000h
0x180028e6c  mov     r10, cs:WPP_GLOBAL_Control
0x180028e73  cmp     r10, r14
0x180028e76  jz      loc_180028F35
0x180028e7c  cmp     byte ptr [r10+19h], 2
0x180028e81  jb      loc_180028F35
0x180028e87  xor     ecx, ecx; int
0x180028e89  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180028e8e  lea     rcx, [rsp+2B0h+FileName]
0x180028e93  mov     [rsp+2B0h+dwFlags], ebx
0x180028e97  mov     [rsp+2B0h+pPromptStruct], rcx
0x180028e9c  mov     edx, 15h
0x180028ea1  mov     rcx, [r10+10h]
0x180028ea5  mov     r9, rax
0x180028ea8  mov     r8, r15
0x180028eab  call    WPP_SF_sSd
0x180028eb0  jmp     short loc_180028F2E
0x180028eb2  mov     r8d, [rsp+2B0h+var_268.cbData]; nNumberOfBytesToWrite
0x180028eb7  lea     r9, [rsp+2B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180028ebc  mov     rdx, [rsp+2B0h+var_268.pbData]; lpBuffer
0x180028ec1  mov     rcx, rax; hFile
0x180028ec4  mov     [rsp+2B0h+pPromptStruct], rsi; lpOverlapped
0x180028ec9  call    cs:__imp_WriteFile
0x180028ecf  test    eax, eax
0x180028ed1  jnz     short loc_180028F2E
0x180028ed3  call    cs:__imp_GetLastError
0x180028ed9  test    eax, eax
0x180028edb  jg      short loc_180028EE7
0x180028edd  call    cs:__imp_GetLastError
0x180028ee3  mov     ebx, eax
0x180028ee5  jmp     short loc_180028EF6
0x180028ee7  call    cs:__imp_GetLastError
0x180028eed  movzx   ebx, ax
0x180028ef0  or      ebx, 80070000h
0x180028ef6  or      ebx, 80000000h
0x180028efc  mov     r10, cs:WPP_GLOBAL_Control
0x180028f03  cmp     r10, r14
0x180028f06  jz      short loc_180028F35
0x180028f08  cmp     byte ptr [r10+19h], 2
0x180028f0d  jb      short loc_180028F35
0x180028f0f  xor     ecx, ecx; int
0x180028f11  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180028f16  mov     edx, 16h
0x180028f1b  mov     rcx, [r10+10h]
0x180028f1f  mov     r9, rax
0x180028f22  mov     r8, r15
0x180028f25  mov     dword ptr [rsp+2B0h+pPromptStruct], ebx
0x180028f29  call    WPP_SF_sd
0x180028f2e  mov     r10, cs:WPP_GLOBAL_Control
0x180028f35  mov     rcx, [rsp+2B0h+var_268.pbData]; hMem
0x180028f3a  test    rcx, rcx
0x180028f3d  jz      short loc_180028F4C
0x180028f3f  call    cs:__imp_LocalFree
0x180028f45  mov     r10, cs:WPP_GLOBAL_Control
0x180028f4c  cmp     rdi, r12
0x180028f4f  jz      short loc_180028F61
0x180028f51  mov     rcx, rdi; hObject
0x180028f54  call    cs:__imp_CloseHandle
0x180028f5a  mov     r10, cs:WPP_GLOBAL_Control
0x180028f61  cmp     r10, r14
0x180028f64  jz      short loc_180028F91
0x180028f66  test    ebx, ebx
0x180028f68  js      short loc_180028F71
0x180028f6a  cmp     byte ptr [r10+19h], 6
0x180028f6f  jb      short loc_180028F91
0x180028f71  mov     ecx, r12d; int
0x180028f74  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180028f79  mov     rcx, [r10+10h]
0x180028f7d  mov     edx, 17h
0x180028f82  mov     r9, rax
0x180028f85  mov     dword ptr [rsp+2B0h+pPromptStruct], ebx
0x180028f89  mov     r8, r15
0x180028f8c  call    WPP_SF_sd
0x180028f91  mov     eax, ebx
0x180028f93  mov     rcx, [rbp+1B0h+var_30]
0x180028f9a  xor     rcx, rsp; StackCookie
0x180028f9d  call    __security_check_cookie
0x180028fa2  lea     r11, [rsp+2B0h+var_20]
0x180028faa  mov     rbx, [r11+38h]
0x180028fae  mov     rsi, [r11+40h]
0x180028fb2  mov     rsp, r11
0x180028fb5  pop     r15
0x180028fb7  pop     r14
0x180028fb9  pop     r12
0x180028fbb  pop     rdi
0x180028fbc  pop     rbp
0x180028fbd  retn
```
