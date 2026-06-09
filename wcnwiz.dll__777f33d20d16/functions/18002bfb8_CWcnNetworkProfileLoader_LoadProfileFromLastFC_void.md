# CWcnNetworkProfileLoader::LoadProfileFromLastFC(void)

- ea: `0x18002bfb8`
- end: `0x18002c4db`
- name: `?LoadProfileFromLastFC@CWcnNetworkProfileLoader@@IEAAJXZ`
- size: `1315`
- prototype: `__int64 __fastcall(CWcnNetworkProfileLoader *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18002c4f0`
- `0x18002d540`

## callees

- `0x180001820`
- `0x180001844`
- `0x1800028c4`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18001bc88`
- `0x180028a00`
- `0x18002b988`
- `0x18002bfb8`
- `0x18002c914`
- `0x18002de1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c0ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c0fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c18c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c28b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c29f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c32e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c0ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c0fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c18c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c28b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c29f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c32e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c342`
- `KERNEL32!LocalFree` at `0x18002c447`
- `KERNEL32!LocalFree` at `0x18002c447`
- `KERNEL32!CreateFileW` at `0x18002c0a7`
- `KERNEL32!CreateFileW` at `0x18002c0a7`
- `KERNEL32!CloseHandle` at `0x18002c471`
- `KERNEL32!CloseHandle` at `0x18002c471`
- `KERNEL32!GetFileSizeEx` at `0x18002c178`
- `KERNEL32!GetFileSizeEx` at `0x18002c178`
- `KERNEL32!ReadFile` at `0x18002c281`
- `KERNEL32!ReadFile` at `0x18002c281`
- `CRYPT32!CryptUnprotectData` at `0x18002c324`
- `CRYPT32!CryptUnprotectData` at `0x18002c324`

## pseudocode

```c
__int64 __fastcall CWcnNetworkProfileLoader::LoadProfileFromLastFC(CWcnNetworkProfileLoader *this)
{
  BYTE *v1; // rsi
  const char *Indent; // rax
  __int64 v4; // r10
  int LastFcDirectory; // eax
  signed int v6; // ebx
  __int64 v7; // rdi
  _QWORD *v8; // r11
  __int64 v9; // rdx
  HANDLE FileW; // rax
  const char *v11; // rax
  __int64 v12; // rdx
  const char *v13; // r9
  unsigned int LastError; // ebx
  unsigned int v15; // eax
  __int64 v16; // r11
  int v17; // edx
  unsigned int v18; // ebx
  unsigned int v19; // eax
  __int64 v20; // r11
  int v21; // edx
  int v22; // r8d
  char v23; // r10
  BYTE *v24; // rax
  unsigned int v25; // ebx
  unsigned int v26; // eax
  __int64 v27; // r11
  int v28; // edx
  unsigned int v29; // ebx
  unsigned int v30; // eax
  __int64 v31; // r11
  char v32; // r10
  unsigned int v33; // eax
  __int64 v34; // r11
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  DATA_BLOB pDataOut; // [rsp+50h] [rbp-B0h] BYREF
  DATA_BLOB pDataIn; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF

  v1 = 0;
  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  pDataIn = 0;
  pDataOut = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 26, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, Indent);
  }
  LastFcDirectory = WcnGetLastFcDirectory(FileName);
  v6 = LastFcDirectory;
  if ( LastFcDirectory < 0 )
  {
    v7 = -1;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 27;
LABEL_59:
      WPP_SF_d(v8[2], v9, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, (unsigned int)LastFcDirectory);
      goto LABEL_60;
    }
    goto LABEL_61;
  }
  v6 = 1;
  FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 6u, 0);
  v7 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( GetLastError() == 2 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        goto LABEL_61;
      v11 = GetIndent(0);
      v12 = 28;
      v13 = v11;
LABEL_13:
      WPP_SF_s(v8[2], v12, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, v13);
      goto LABEL_60;
    }
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v6 = LastError | 0x80000000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_61;
    v15 = (unsigned int)GetIndent(0);
    v17 = 29;
LABEL_20:
    WPP_SF_sSd(
      *(_QWORD *)(v16 + 16),
      v17,
      (unsigned int)WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids,
      v15,
      (__int64)FileName,
      v6);
    goto LABEL_60;
  }
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    if ( (int)GetLastError() > 0 )
      v18 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v18 = GetLastError();
    v6 = v18 | 0x80000000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_61;
    v15 = (unsigned int)GetIndent(0);
    v17 = 30;
    goto LABEL_20;
  }
  if ( FileSize.QuadPart > 10240 )
  {
    v6 = -2147024846;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_61;
    v19 = (unsigned int)GetIndent(0);
    WPP_SF_sID(*(_QWORD *)(v20 + 16), v21, v22, v19, v23);
    goto LABEL_60;
  }
  v24 = (BYTE *)operator new[](FileSize.LowPart, (const struct std::nothrow_t *)std::nothrow);
  v1 = v24;
  if ( !v24 )
  {
    v6 = -2147024882;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_61;
    v12 = 32;
    v13 = "pbFileBuffer";
    goto LABEL_13;
  }
  if ( !ReadFile((HANDLE)v7, v24, FileSize.LowPart, &NumberOfBytesRead, 0) )
  {
    if ( (int)GetLastError() > 0 )
      v25 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v25 = GetLastError();
    v6 = v25 | 0x80000000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_61;
    v26 = (unsigned int)GetIndent(0);
    v28 = 33;
LABEL_43:
    WPP_SF_sd(*(_QWORD *)(v27 + 16), v28, (unsigned int)WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, v26, v6);
    goto LABEL_60;
  }
  pDataIn.cbData = FileSize.LowPart;
  pDataIn.pbData = v1;
  if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
  {
    if ( (int)GetLastError() > 0 )
      v29 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v29 = GetLastError();
    v6 = v29 | 0x80000000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_61;
    v26 = (unsigned int)GetIndent(0);
    v28 = 34;
    goto LABEL_43;
  }
  if ( pDataOut.cbData < 0xA )
  {
    v6 = -2147023690;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_61;
    v30 = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v31 + 16), 35, (unsigned int)WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, v30, v32);
LABEL_60:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_61;
  }
  pDataOut.pbData[pDataOut.cbData - 2] = 0;
  pDataOut.pbData[pDataOut.cbData - 1] = 0;
  LastFcDirectory = CWcnNetworkProfileLoader::AddProfileToList(
                      this,
                      32,
                      (unsigned __int16 *)pDataOut.pbData,
                      &dword_18003604C,
                      1);
  v6 = LastFcDirectory;
  if ( LastFcDirectory >= 0 )
    goto LABEL_60;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 36;
    goto LABEL_59;
  }
LABEL_61:
  if ( pDataOut.pbData )
  {
    LocalFree(pDataOut.pbData);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v1 )
  {
    operator delete(v1);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v7 != -1 )
  {
    CloseHandle((HANDLE)v7);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (v6 < 0 || *((_BYTE *)v8 + 25) >= 6u) )
  {
    v33 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v34 + 16), 37, (unsigned int)WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, v33, v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002bfb8  mov     [rsp-8+arg_8], rbx
0x18002bfbd  mov     [rsp-8+arg_10], rsi
0x18002bfc2  push    rbp
0x18002bfc3  push    rdi
0x18002bfc4  push    r12
0x18002bfc6  push    r13
0x18002bfc8  push    r14
0x18002bfca  lea     rbp, [rsp-190h]
0x18002bfd2  sub     rsp, 290h
0x18002bfd9  mov     rax, cs:__security_cookie
0x18002bfe0  xor     rax, rsp
0x18002bfe3  mov     [rbp+1B0h+var_30], rax
0x18002bfea  xor     esi, esi
0x18002bfec  mov     qword ptr [rsp+2B0h+FileSize], 0
0x18002bff5  xorps   xmm0, xmm0
0x18002bff8  mov     [rsp+2B0h+NumberOfBytesRead], esi
0x18002bffc  xorps   xmm1, xmm1
0x18002bfff  mov     r14, rcx
0x18002c002  movups  xmmword ptr [rsp+2B0h+pDataIn.cbData], xmm0
0x18002c007  movups  xmmword ptr [rsp+2B0h+pDataOut.cbData], xmm1
0x18002c00c  mov     r10, cs:WPP_GLOBAL_Control
0x18002c013  lea     r12, WPP_GLOBAL_Control
0x18002c01a  lea     r13, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids
0x18002c021  cmp     r10, r12
0x18002c024  jz      short loc_18002C047
0x18002c026  cmp     byte ptr [r10+19h], 6
0x18002c02b  jb      short loc_18002C047
0x18002c02d  lea     ecx, [rsi+1]; int
0x18002c030  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002c035  mov     rcx, [r10+10h]
0x18002c039  lea     edx, [rsi+1Ah]
0x18002c03c  mov     r9, rax
0x18002c03f  mov     r8, r13
0x18002c042  call    WPP_SF_s
0x18002c047  lea     rcx, [rsp+2B0h+FileName]; Buffer
0x18002c04c  call    ?WcnGetLastFcDirectory@@YAJPEAGK@Z; WcnGetLastFcDirectory(ushort *,ulong)
0x18002c051  mov     ebx, eax
0x18002c053  test    eax, eax
0x18002c055  jns     short loc_18002C07E
0x18002c057  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002c05b  mov     r11, cs:WPP_GLOBAL_Control
0x18002c062  cmp     r11, r12
0x18002c065  jz      loc_18002C43D
0x18002c06b  cmp     byte ptr [r11+19h], 2
0x18002c070  jb      loc_18002C43D
0x18002c076  lea     edx, [rdi+1Ch]
0x18002c079  jmp     loc_18002C427
0x18002c07e  xor     r9d, r9d; lpSecurityAttributes
0x18002c081  mov     [rsp+2B0h+hTemplateFile], rsi; hTemplateFile
0x18002c086  mov     [rsp+2B0h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x18002c08e  lea     rcx, [rsp+2B0h+FileName]; lpFileName
0x18002c093  mov     edx, 80000000h; dwDesiredAccess
0x18002c098  mov     [rsp+2B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002c0a0  lea     ebx, [r9+1]
0x18002c0a4  mov     r8d, ebx; dwShareMode
0x18002c0a7  call    cs:__imp_CreateFileW
0x18002c0ad  mov     rdi, rax
0x18002c0b0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c0b4  jnz     loc_18002C170
0x18002c0ba  call    cs:__imp_GetLastError
0x18002c0c0  cmp     eax, 2
0x18002c0c3  jnz     short loc_18002C0FE
0x18002c0c5  mov     r11, cs:WPP_GLOBAL_Control
0x18002c0cc  cmp     r11, r12
0x18002c0cf  jz      loc_18002C43D
0x18002c0d5  cmp     byte ptr [r11+19h], 4
0x18002c0da  jb      loc_18002C43D
0x18002c0e0  xor     ecx, ecx; int
0x18002c0e2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002c0e7  lea     edx, [rbx+1Bh]
0x18002c0ea  mov     r9, rax
0x18002c0ed  mov     rcx, [r11+10h]
0x18002c0f1  mov     r8, r13
0x18002c0f4  call    WPP_SF_s
0x18002c0f9  jmp     loc_18002C436
0x18002c0fe  call    cs:__imp_GetLastError
0x18002c104  test    eax, eax
0x18002c106  jg      short loc_18002C112
0x18002c108  call    cs:__imp_GetLastError
0x18002c10e  mov     ebx, eax
0x18002c110  jmp     short loc_18002C121
0x18002c112  call    cs:__imp_GetLastError
0x18002c118  movzx   ebx, ax
0x18002c11b  or      ebx, 80070000h
0x18002c121  or      ebx, 80000000h
0x18002c127  mov     r11, cs:WPP_GLOBAL_Control
0x18002c12e  cmp     r11, r12
0x18002c131  jz      loc_18002C43D
0x18002c137  cmp     byte ptr [r11+19h], 2
0x18002c13c  jb      loc_18002C43D
0x18002c142  xor     ecx, ecx; int
0x18002c144  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002c149  mov     edx, 1Dh
0x18002c14e  lea     rcx, [rsp+2B0h+FileName]
0x18002c153  mov     [rsp+2B0h+dwFlagsAndAttributes], ebx
0x18002c157  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rcx
0x18002c15c  mov     r9, rax
0x18002c15f  mov     rcx, [r11+10h]
0x18002c163  mov     r8, r13
0x18002c166  call    WPP_SF_sSd
0x18002c16b  jmp     loc_18002C436
0x18002c170  lea     rdx, [rsp+2B0h+FileSize]; lpFileSize
0x18002c175  mov     rcx, rdi; hFile
0x18002c178  call    cs:__imp_GetFileSizeEx
0x18002c17e  test    eax, eax
0x18002c180  jnz     short loc_18002C1D7
0x18002c182  call    cs:__imp_GetLastError
0x18002c188  test    eax, eax
0x18002c18a  jg      short loc_18002C196
0x18002c18c  call    cs:__imp_GetLastError
0x18002c192  mov     ebx, eax
0x18002c194  jmp     short loc_18002C1A5
0x18002c196  call    cs:__imp_GetLastError
0x18002c19c  movzx   ebx, ax
0x18002c19f  or      ebx, 80070000h
0x18002c1a5  or      ebx, 80000000h
0x18002c1ab  mov     r11, cs:WPP_GLOBAL_Control
0x18002c1b2  cmp     r11, r12
0x18002c1b5  jz      loc_18002C43D
0x18002c1bb  cmp     byte ptr [r11+19h], 2
0x18002c1c0  jb      loc_18002C43D
0x18002c1c6  xor     ecx, ecx; int
0x18002c1c8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002c1cd  mov     edx, 1Eh
0x18002c1d2  jmp     loc_18002C14E
0x18002c1d7  mov     r10, qword ptr [rsp+2B0h+FileSize]
0x18002c1dc  cmp     r10, 2800h
0x18002c1e3  jle     short loc_18002C222
0x18002c1e5  mov     ebx, 80070032h
0x18002c1ea  mov     r11, cs:WPP_GLOBAL_Control
0x18002c1f1  cmp     r11, r12
0x18002c1f4  jz      loc_18002C43D
0x18002c1fa  cmp     byte ptr [r11+19h], 2
0x18002c1ff  jb      loc_18002C43D
0x18002c205  xor     ecx, ecx; int
0x18002c207  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002c20c  mov     rcx, [r11+10h]
0x18002c210  mov     r9, rax
0x18002c213  mov     qword ptr [rsp+2B0h+dwCreationDisposition], r10
0x18002c218  call    WPP_SF_sID
0x18002c21d  jmp     loc_18002C436
0x18002c222  mov     ecx, r10d; unsigned __int64
0x18002c225  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002c22c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002c231  mov     rsi, rax
0x18002c234  test    rax, rax
0x18002c237  jnz     short loc_18002C268
0x18002c239  mov     ebx, 8007000Eh
0x18002c23e  mov     r11, cs:WPP_GLOBAL_Control
0x18002c245  cmp     r11, r12
0x18002c248  jz      loc_18002C43D
0x18002c24e  cmp     byte ptr [r11+19h], 2
0x18002c253  jb      loc_18002C43D
0x18002c259  lea     edx, [rax+20h]
0x18002c25c  lea     r9, aPbfilebuffer; "pbFileBuffer"
0x18002c263  jmp     loc_18002C0ED
0x18002c268  mov     r8d, dword ptr [rsp+2B0h+FileSize]; nNumberOfBytesToRead
0x18002c26d  lea     r9, [rsp+2B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002c272  mov     rdx, rsi; lpBuffer
0x18002c275  mov     qword ptr [rsp+2B0h+dwCreationDisposition], 0; lpOverlapped
0x18002c27e  mov     rcx, rdi; hFile
0x18002c281  call    cs:__imp_ReadFile
0x18002c287  test    eax, eax
0x18002c289  jnz     short loc_18002C2F3
0x18002c28b  call    cs:__imp_GetLastError
0x18002c291  test    eax, eax
0x18002c293  jg      short loc_18002C29F
0x18002c295  call    cs:__imp_GetLastError
0x18002c29b  mov     ebx, eax
0x18002c29d  jmp     short loc_18002C2AE
0x18002c29f  call    cs:__imp_GetLastError
0x18002c2a5  movzx   ebx, ax
0x18002c2a8  or      ebx, 80070000h
0x18002c2ae  or      ebx, 80000000h
0x18002c2b4  mov     r11, cs:WPP_GLOBAL_Control
0x18002c2bb  cmp     r11, r12
0x18002c2be  jz      loc_18002C43D
0x18002c2c4  cmp     byte ptr [r11+19h], 2
0x18002c2c9  jb      loc_18002C43D
0x18002c2cf  xor     ecx, ecx; int
0x18002c2d1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002c2d6  mov     edx, 21h ; '!'
0x18002c2db  mov     rcx, [r11+10h]
0x18002c2df  mov     r9, rax
0x18002c2e2  mov     r8, r13
0x18002c2e5  mov     [rsp+2B0h+dwCreationDisposition], ebx
0x18002c2e9  call    WPP_SF_sd
0x18002c2ee  jmp     loc_18002C436
0x18002c2f3  mov     eax, dword ptr [rsp+2B0h+FileSize]
0x18002c2f7  lea     rcx, [rsp+2B0h+pDataIn]; pDataIn
0x18002c2fc  mov     [rsp+2B0h+pDataIn.cbData], eax
0x18002c300  xor     r9d, r9d; pvReserved
0x18002c303  lea     rax, [rsp+2B0h+pDataOut]
0x18002c308  mov     [rsp+2B0h+pDataIn.pbData], rsi
0x18002c30d  mov     [rsp+2B0h+hTemplateFile], rax; pDataOut
0x18002c312  xor     r8d, r8d; pOptionalEntropy
0x18002c315  mov     [rsp+2B0h+dwFlagsAndAttributes], ebx; dwFlags
0x18002c319  xor     edx, edx; ppszDataDescr
0x18002c31b  mov     qword ptr [rsp+2B0h+dwCreationDisposition], 0; pPromptStruct
0x18002c324  call    cs:__imp_CryptUnprotectData
0x18002c32a  test    eax, eax
0x18002c32c  jnz     short loc_18002C383
0x18002c32e  call    cs:__imp_GetLastError
0x18002c334  test    eax, eax
0x18002c336  jg      short loc_18002C342
0x18002c338  call    cs:__imp_GetLastError
0x18002c33e  mov     ebx, eax
0x18002c340  jmp     short loc_18002C351
0x18002c342  call    cs:__imp_GetLastError
0x18002c348  movzx   ebx, ax
0x18002c34b  or      ebx, 80070000h
0x18002c351  or      ebx, 80000000h
0x18002c357  mov     r11, cs:WPP_GLOBAL_Control
0x18002c35e  cmp     r11, r12
0x18002c361  jz      loc_18002C43D
0x18002c367  cmp     byte ptr [r11+19h], 2
0x18002c36c  jb      loc_18002C43D
0x18002c372  xor     ecx, ecx; int
0x18002c374  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002c379  mov     edx, 22h ; '"'
0x18002c37e  jmp     loc_18002C2DB
0x18002c383  mov     r10d, [rsp+2B0h+pDataOut.cbData]
0x18002c388  cmp     r10d, 0Ah
0x18002c38c  jnb     short loc_18002C3D0
0x18002c38e  mov     ebx, 800704B6h
0x18002c393  mov     r11, cs:WPP_GLOBAL_Control
0x18002c39a  cmp     r11, r12
0x18002c39d  jz      loc_18002C43D
0x18002c3a3  cmp     byte ptr [r11+19h], 2
0x18002c3a8  jb      loc_18002C43D
0x18002c3ae  xor     ecx, ecx; int
0x18002c3b0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002c3b5  mov     rcx, [r11+10h]
0x18002c3b9  mov     edx, 23h ; '#'
0x18002c3be  mov     r9, rax
0x18002c3c1  mov     [rsp+2B0h+dwCreationDisposition], r10d
0x18002c3c6  mov     r8, r13
0x18002c3c9  call    WPP_SF_sd
0x18002c3ce  jmp     short loc_18002C436
0x18002c3d0  mov     rax, [rsp+2B0h+pDataOut.pbData]
0x18002c3d5  lea     edx, [r10-2]
0x18002c3d9  lea     r9, dword_18003604C
0x18002c3e0  mov     [rsp+2B0h+dwCreationDisposition], ebx
0x18002c3e4  mov     rcx, r14
0x18002c3e7  mov     byte ptr [rdx+rax], 0
0x18002c3eb  mov     edx, [rsp+2B0h+pDataOut.cbData]
0x18002c3ef  mov     rax, [rsp+2B0h+pDataOut.pbData]
0x18002c3f4  dec     edx
0x18002c3f6  mov     byte ptr [rdx+rax], 0
0x18002c3fa  mov     edx, 20h ; ' '
0x18002c3ff  mov     r8, [rsp+2B0h+pDataOut.pbData]
0x18002c404  call    ?AddProfileToList@CWcnNetworkProfileLoader@@IEAAJKPEBG0W4tagWCN_NETPROFILE_SOURCE@@@Z; CWcnNetworkProfileLoader::AddProfileToList(ulong,ushort const *,ushort const *,tagWCN_NETPROFILE_SOURCE)
0x18002c409  mov     ebx, eax
0x18002c40b  test    eax, eax
0x18002c40d  jns     short loc_18002C436
0x18002c40f  mov     r11, cs:WPP_GLOBAL_Control
0x18002c416  cmp     r11, r12
0x18002c419  jz      short loc_18002C43D
0x18002c41b  cmp     byte ptr [r11+19h], 2
0x18002c420  jb      short loc_18002C43D
0x18002c422  mov     edx, 24h ; '$'
0x18002c427  mov     rcx, [r11+10h]
0x18002c42b  mov     r9d, eax
0x18002c42e  mov     r8, r13
0x18002c431  call    WPP_SF_d
0x18002c436  mov     r11, cs:WPP_GLOBAL_Control
0x18002c43d  mov     rcx, [rsp+2B0h+pDataOut.pbData]; hMem
0x18002c442  test    rcx, rcx
0x18002c445  jz      short loc_18002C454
0x18002c447  call    cs:__imp_LocalFree
0x18002c44d  mov     r11, cs:WPP_GLOBAL_Control
0x18002c454  test    rsi, rsi
0x18002c457  jz      short loc_18002C468
0x18002c459  mov     rcx, rsi; Block
0x18002c45c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c461  mov     r11, cs:WPP_GLOBAL_Control
0x18002c468  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002c46c  jz      short loc_18002C47E
0x18002c46e  mov     rcx, rdi; hObject
0x18002c471  call    cs:__imp_CloseHandle
0x18002c477  mov     r11, cs:WPP_GLOBAL_Control
0x18002c47e  cmp     r11, r12
0x18002c481  jz      short loc_18002C4AE
0x18002c483  test    ebx, ebx
0x18002c485  js      short loc_18002C48E
0x18002c487  cmp     byte ptr [r11+19h], 6
0x18002c48c  jb      short loc_18002C4AE
0x18002c48e  or      ecx, 0FFFFFFFFh; int
0x18002c491  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002c496  mov     rcx, [r11+10h]
0x18002c49a  mov     edx, 25h ; '%'
0x18002c49f  mov     r9, rax
0x18002c4a2  mov     [rsp+2B0h+dwCreationDisposition], ebx
0x18002c4a6  mov     r8, r13
0x18002c4a9  call    WPP_SF_sd
0x18002c4ae  mov     eax, ebx
0x18002c4b0  mov     rcx, [rbp+1B0h+var_30]
0x18002c4b7  xor     rcx, rsp; StackCookie
0x18002c4ba  call    __security_check_cookie
0x18002c4bf  lea     r11, [rsp+2B0h+var_20]
  ... truncated ...
```
