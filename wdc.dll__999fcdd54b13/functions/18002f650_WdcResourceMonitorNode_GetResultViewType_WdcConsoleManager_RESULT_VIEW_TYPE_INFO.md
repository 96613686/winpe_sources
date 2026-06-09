# WdcResourceMonitorNode::GetResultViewType(WdcConsoleManager *,_RESULT_VIEW_TYPE_INFO *)

- ea: `0x18002f650`
- end: `0x18002f8c4`
- name: `?GetResultViewType@WdcResourceMonitorNode@@UEAAJPEAVWdcConsoleManager@@PEAU_RESULT_VIEW_TYPE_INFO@@@Z`
- size: `628`
- prototype: `__int64 __fastcall(WdcResourceMonitorNode *__hidden this, struct WdcConsoleManager *, struct _RESULT_VIEW_TYPE_INFO *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18002f650`
- `0x18006691c`
- `0x1800695b0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002f73c`
- `KERNEL32!CreateFileW` at `0x18002f73c`
- `KERNEL32!CloseHandle` at `0x18002f8a2`
- `KERNEL32!CloseHandle` at `0x18002f8a2`
- `KERNEL32!GetLastError` at `0x18002f6f2`
- `KERNEL32!GetLastError` at `0x18002f74a`
- `KERNEL32!GetLastError` at `0x18002f7c9`
- `KERNEL32!GetLastError` at `0x18002f82a`
- `KERNEL32!GetLastError` at `0x18002f6f2`
- `KERNEL32!GetLastError` at `0x18002f74a`
- `KERNEL32!GetLastError` at `0x18002f7c9`
- `KERNEL32!GetLastError` at `0x18002f82a`
- `KERNEL32!GetFileAttributesW` at `0x18002f70d`
- `KERNEL32!GetFileAttributesW` at `0x18002f70d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002f6e2`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002f7f1`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002f6e2`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002f7f1`
- `KERNEL32!WriteFile` at `0x18002f7bf`
- `KERNEL32!WriteFile` at `0x18002f7bf`

## string_xrefs

- `0x18002f7b5`: `<configuration/>\n`
- `0x18002f7e7`: `res://wdc.dll/home.htm?FILE:///%localappdata%/resmon.resmoncfg`

## pseudocode

```c
__int64 __fastcall WdcResourceMonitorNode::GetResultViewType(
        WdcResourceMonitorNode *this,
        struct WdcConsoleManager *a2,
        struct _RESULT_VIEW_TYPE_INFO *a3)
{
  signed int v4; // ebx
  char *v5; // rbp
  const char *v6; // rdx
  int v7; // r8d
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  signed int LastError; // eax
  char *FileW; // rax
  signed int v12; // eax
  const char *v13; // rdx
  int v14; // r8d
  signed int v15; // eax
  signed int v16; // eax
  WCHAR v17; // ax
  WCHAR *v18; // rcx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-58h]
  DWORD NumberOfBytesWritten; // [rsp+90h] [rbp+18h] BYREF

  NumberOfBytesWritten = 0;
  if ( !a3 )
  {
    v4 = -2147467261;
LABEL_3:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\resourcemonitornode.cpp",
      "WdcResourceMonitorNode::GetResultViewType",
      0,
      L"FAILURE: 0x%08x",
      v4);
    return (unsigned int)v4;
  }
  v5 = 0;
  *(_OWORD *)&a3->pstrPersistableViewDescription = 0;
  a3->16 = 0;
  if ( (unsigned int)WdcResourceMonitorNode::UseHTMLContent() )
  {
    v8 = (WCHAR *)WdcAlloc(0x800u, v6, v7);
    v9 = v8;
    if ( !v8 )
    {
      v4 = -2147024882;
      goto LABEL_3;
    }
    *v8 = 0;
    if ( ExpandEnvironmentStringsW(L"%localappdata%\\resmon.resmoncfg", v8, 0x400u) )
      goto LABEL_12;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_12:
        if ( GetFileAttributesW(v9) != -1 )
          goto LABEL_30;
        FileW = (char *)CreateFileW(v9, 0x40000000u, 0, 0, 2u, 0, 0);
        v5 = FileW;
        if ( FileW && FileW != (char *)-1LL )
        {
LABEL_25:
          if ( !WriteFile(v5, "<configuration/>\n", 0x11u, &NumberOfBytesWritten, 0) )
          {
            v15 = GetLastError();
            v4 = v15;
            if ( !v15 )
              goto LABEL_32;
            if ( v15 > 0 )
              v4 = (unsigned __int16)v15 | 0x80070000;
            if ( v4 < 0 )
              goto LABEL_33;
          }
LABEL_30:
          if ( ExpandEnvironmentStringsW(L"res://wdc.dll/home.htm?FILE:///%localappdata%/resmon.resmoncfg", v9, 0x400u) )
          {
            v4 = 0;
LABEL_38:
            v17 = *v9;
            if ( *v9 )
            {
              v18 = v9;
              do
              {
                if ( v17 == 92 )
                  *v18 = 47;
                v17 = *++v18;
              }
              while ( *v18 );
            }
            a3->eViewType = MMC_VIEW_TYPE_HTML;
            a3->pstrURL = WdcTaskAllocString(v9);
            a3->dwMiscOptions = 1;
            goto LABEL_45;
          }
          v16 = GetLastError();
          v4 = v16;
          if ( v16 )
          {
            if ( v16 > 0 )
              v4 = (unsigned __int16)v16 | 0x80070000;
            if ( v4 >= 0 )
              goto LABEL_38;
LABEL_33:
            dwCreationDisposition[0] = v4;
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mmc\\resourcemonitornode.cpp",
              "WdcResourceMonitorNode::GetResultViewType",
              0,
              L"FAILURE: 0x%08x",
              *(_QWORD *)dwCreationDisposition);
            goto LABEL_46;
          }
LABEL_32:
          v4 = -2147467259;
          goto LABEL_33;
        }
        v12 = GetLastError();
        v4 = v12;
        if ( v12 )
        {
          if ( v12 > 0 )
            v4 = (unsigned __int16)v12 | 0x80070000;
          if ( v4 >= 0 )
            goto LABEL_25;
        }
        else
        {
          v4 = -2147467259;
        }
        dwCreationDisposition[0] = v4;
LABEL_21:
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mmc\\resourcemonitornode.cpp",
          "WdcResourceMonitorNode::GetResultViewType",
          0,
          L"FAILURE: 0x%08x",
          *(_QWORD *)dwCreationDisposition);
LABEL_49:
        WdcFree(v9, v13, v14);
        return (unsigned int)v4;
      }
    }
    else
    {
      v4 = -2147467259;
    }
    dwCreationDisposition[0] = v4;
    goto LABEL_21;
  }
  v9 = 0;
  v4 = 0;
LABEL_45:
  a3->pstrPersistableViewDescription = WdcTaskAllocString(L"_home");
LABEL_46:
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  if ( v9 )
    goto LABEL_49;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002f650  mov     rax, rsp
0x18002f653  push    rbx
0x18002f654  push    rbp
0x18002f655  push    rsi
0x18002f656  push    rdi
0x18002f657  push    r14
0x18002f659  push    r15
0x18002f65b  sub     rsp, 48h
0x18002f65f  xor     r15d, r15d
0x18002f662  mov     rsi, r8
0x18002f665  mov     [rax+18h], r15d
0x18002f669  test    r8, r8
0x18002f66c  jnz     short loc_18002F699
0x18002f66e  mov     ebx, 80004003h
0x18002f673  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002f67a  mov     [rsp+78h+dwCreationDisposition], ebx
0x18002f67e  xor     r8d, r8d; int
0x18002f681  lea     rdx, aWdcresourcemon_10; "WdcResourceMonitorNode::GetResultViewTy"...
0x18002f688  lea     rcx, aBaseDiagnosisP_54; "base\\diagnosis\\pdui\\perfmon\\mmc\\re"...
0x18002f68f  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002f694  jmp     loc_18002F8B5
0x18002f699  xorps   xmm0, xmm0
0x18002f69c  mov     rbp, r15
0x18002f69f  movups  xmmword ptr [r8], xmm0
0x18002f6a3  movups  xmmword ptr [r8+10h], xmm0
0x18002f6a8  call    ?UseHTMLContent@WdcResourceMonitorNode@@CAHXZ; WdcResourceMonitorNode::UseHTMLContent(void)
0x18002f6ad  test    eax, eax
0x18002f6af  jz      loc_18002F880
0x18002f6b5  mov     ecx, 800h; dwBytes
0x18002f6ba  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18002f6bf  mov     rdi, rax
0x18002f6c2  test    rax, rax
0x18002f6c5  jnz     short loc_18002F6CE
0x18002f6c7  mov     ebx, 8007000Eh
0x18002f6cc  jmp     short loc_18002F673
0x18002f6ce  mov     r8d, 400h; nSize
0x18002f6d4  mov     [rax], r15w
0x18002f6d8  mov     rdx, rdi; lpDst
0x18002f6db  lea     rcx, Src; "%localappdata%\\resmon.resmoncfg"
0x18002f6e2  call    cs:__imp_ExpandEnvironmentStringsW
0x18002f6e8  mov     r14d, 80070000h
0x18002f6ee  test    eax, eax
0x18002f6f0  jnz     short loc_18002F70A
0x18002f6f2  call    cs:__imp_GetLastError
0x18002f6f8  mov     ebx, eax
0x18002f6fa  test    eax, eax
0x18002f6fc  jz      short loc_18002F764
0x18002f6fe  jle     short loc_18002F706
0x18002f700  movzx   ebx, ax
0x18002f703  or      ebx, r14d
0x18002f706  test    ebx, ebx
0x18002f708  js      short loc_18002F769
0x18002f70a  mov     rcx, rdi; lpFileName
0x18002f70d  call    cs:__imp_GetFileAttributesW
0x18002f713  cmp     eax, 0FFFFFFFFh
0x18002f716  jnz     loc_18002F7E1
0x18002f71c  mov     [rsp+78h+hTemplateFile], r15; hTemplateFile
0x18002f721  xor     r9d, r9d; lpSecurityAttributes
0x18002f724  mov     [rsp+78h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18002f729  xor     r8d, r8d; dwShareMode
0x18002f72c  mov     edx, 40000000h; dwDesiredAccess
0x18002f731  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x18002f739  mov     rcx, rdi; lpFileName
0x18002f73c  call    cs:__imp_CreateFileW
0x18002f742  mov     rbp, rax
0x18002f745  test    rax, rax
0x18002f748  jnz     short loc_18002F79C
0x18002f74a  call    cs:__imp_GetLastError
0x18002f750  mov     ebx, eax
0x18002f752  test    eax, eax
0x18002f754  jz      short loc_18002F791
0x18002f756  jle     short loc_18002F75E
0x18002f758  movzx   ebx, ax
0x18002f75b  or      ebx, r14d
0x18002f75e  test    ebx, ebx
0x18002f760  jns     short loc_18002F7A2
0x18002f762  jmp     short loc_18002F796
0x18002f764  mov     ebx, 80004005h
0x18002f769  mov     eax, ebx
0x18002f76b  mov     [rsp+78h+dwCreationDisposition], ebx
0x18002f76f  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002f776  xor     r8d, r8d; int
0x18002f779  lea     rdx, aWdcresourcemon_10; "WdcResourceMonitorNode::GetResultViewTy"...
0x18002f780  lea     rcx, aBaseDiagnosisP_54; "base\\diagnosis\\pdui\\perfmon\\mmc\\re"...
0x18002f787  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002f78c  jmp     loc_18002F8AD
0x18002f791  mov     ebx, 80004005h
0x18002f796  mov     [rsp+78h+dwCreationDisposition], ebx
0x18002f79a  jmp     short loc_18002F76F
0x18002f79c  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18002f7a0  jz      short loc_18002F74A
0x18002f7a2  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002f7aa  mov     qword ptr [rsp+78h+dwCreationDisposition], r15; lpOverlapped
0x18002f7af  mov     r8d, 11h; nNumberOfBytesToWrite
0x18002f7b5  lea     rdx, aConfiguration_0; "<configuration/>\n"
0x18002f7bc  mov     rcx, rbp; hFile
0x18002f7bf  call    cs:__imp_WriteFile
0x18002f7c5  test    eax, eax
0x18002f7c7  jnz     short loc_18002F7E1
0x18002f7c9  call    cs:__imp_GetLastError
0x18002f7cf  mov     ebx, eax
0x18002f7d1  test    eax, eax
0x18002f7d3  jz      short loc_18002F800
0x18002f7d5  jle     short loc_18002F7DD
0x18002f7d7  movzx   ebx, ax
0x18002f7da  or      ebx, r14d
0x18002f7dd  test    ebx, ebx
0x18002f7df  js      short loc_18002F805
0x18002f7e1  mov     r8d, 400h; nSize
0x18002f7e7  lea     rcx, aResWdcDllHomeH; "res://wdc.dll/home.htm?FILE:///%localap"...
0x18002f7ee  mov     rdx, rdi; lpDst
0x18002f7f1  call    cs:__imp_ExpandEnvironmentStringsW
0x18002f7f7  test    eax, eax
0x18002f7f9  jz      short loc_18002F82A
0x18002f7fb  mov     ebx, r15d
0x18002f7fe  jmp     short loc_18002F842
0x18002f800  mov     ebx, 80004005h
0x18002f805  mov     eax, ebx
0x18002f807  mov     [rsp+78h+dwCreationDisposition], ebx
0x18002f80b  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002f812  xor     r8d, r8d; int
0x18002f815  lea     rdx, aWdcresourcemon_10; "WdcResourceMonitorNode::GetResultViewTy"...
0x18002f81c  lea     rcx, aBaseDiagnosisP_54; "base\\diagnosis\\pdui\\perfmon\\mmc\\re"...
0x18002f823  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002f828  jmp     short loc_18002F895
0x18002f82a  call    cs:__imp_GetLastError
0x18002f830  mov     ebx, eax
0x18002f832  test    eax, eax
0x18002f834  jz      short loc_18002F800
0x18002f836  jle     short loc_18002F83E
0x18002f838  movzx   ebx, ax
0x18002f83b  or      ebx, r14d
0x18002f83e  test    ebx, ebx
0x18002f840  js      short loc_18002F805
0x18002f842  movzx   eax, word ptr [rdi]
0x18002f845  test    ax, ax
0x18002f848  jz      short loc_18002F864
0x18002f84a  mov     rcx, rdi
0x18002f84d  cmp     ax, 5Ch ; '\'
0x18002f851  jnz     short loc_18002F858
0x18002f853  mov     word ptr [rcx], 2Fh ; '/'
0x18002f858  add     rcx, 2
0x18002f85c  movzx   eax, word ptr [rcx]
0x18002f85f  test    ax, ax
0x18002f862  jnz     short loc_18002F84D
0x18002f864  mov     r14d, 1
0x18002f86a  mov     rcx, rdi; unsigned __int16 *
0x18002f86d  mov     [rsi+8], r14d
0x18002f871  call    ?WdcTaskAllocString@@YAPEAGPEBG@Z; WdcTaskAllocString(ushort const *)
0x18002f876  mov     [rsi+18h], rax
0x18002f87a  mov     [rsi+0Ch], r14d
0x18002f87e  jmp     short loc_18002F886
0x18002f880  mov     rdi, r15
0x18002f883  mov     ebx, r15d
0x18002f886  lea     rcx, aHome; "_home"
0x18002f88d  call    ?WdcTaskAllocString@@YAPEAGPEBG@Z; WdcTaskAllocString(ushort const *)
0x18002f892  mov     [rsi], rax
0x18002f895  lea     rax, [rbp-1]
0x18002f899  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f89d  ja      short loc_18002F8A8
0x18002f89f  mov     rcx, rbp; hObject
0x18002f8a2  call    cs:__imp_CloseHandle
0x18002f8a8  test    rdi, rdi
0x18002f8ab  jz      short loc_18002F8B5
0x18002f8ad  mov     rcx, rdi; void *
0x18002f8b0  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18002f8b5  mov     eax, ebx
0x18002f8b7  add     rsp, 48h
0x18002f8bb  pop     r15
0x18002f8bd  pop     r14
0x18002f8bf  pop     rdi
0x18002f8c0  pop     rsi
0x18002f8c1  pop     rbp
0x18002f8c2  pop     rbx
0x18002f8c3  retn
```
