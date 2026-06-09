# _DeleteDirectory

- ea: `0x18001dd98`
- end: `0x18001dfd3`
- name: `_DeleteDirectory`
- size: `571`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001cfc8`
- `0x18001dfe0`

## callees

- `0x18000ea0c`
- `0x180014f70`
- `0x18001586c`
- `0x180015974`
- `0x18001c58c`
- `0x18001cecc`
- `0x18001d2a4`
- `0x18001dd98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001def6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001def6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001df0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dfaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001df0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dfaa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ded7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ded7`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001de5e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001df52`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001de5e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001df52`

## string_xrefs

- `0x18001ddea`: `_DeleteDirectory`

## pseudocode

```c
__int64 __fastcall DeleteDirectory(LPCWSTR lpFileName)
{
  unsigned int v2; // r14d
  int LastFailureAsHRESULT; // edi
  __int64 FileW; // rbx
  __int16 v5; // ax
  __int16 v6; // ax
  int v8; // [rsp+40h] [rbp-40h] BYREF
  __int16 v9; // [rsp+44h] [rbp-3Ch]
  __int16 v10; // [rsp+46h] [rbp-3Ah]
  int v11; // [rsp+48h] [rbp-38h]
  unsigned int v12; // [rsp+A0h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "_DeleteDirectory", 0x774u, 1u);
  v2 = -1;
  v12 = -1;
  if ( !lpFileName )
  {
    LastFailureAsHRESULT = -2147024809;
    v10 = 1913;
    v8 = -2147024809;
    goto LABEL_31;
  }
  v8 = 0;
  v9 = 1913;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids, lpFileName);
  if ( RemoveDirectoryW(lpFileName) )
  {
    v8 = 0;
    v9 = 1919;
    LastFailureAsHRESULT = 0;
    goto LABEL_31;
  }
  FileW = -1;
  if ( GetLastError() == 2 || GetLastError() == 3 )
  {
    LastFailureAsHRESULT = 0;
    v8 = 0;
    v9 = 1924;
LABEL_27:
    if ( v2 != -1 )
    {
      SxSetFileAttributes(lpFileName, v2);
      LastFailureAsHRESULT = v8;
    }
    goto LABEL_29;
  }
  if ( GetLastError() == 5 )
  {
    FileW = (__int64)CreateFileW(lpFileName, 0x100000u, 7u, 0, 3u, 0x2000000u, 0);
    if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      goto LABEL_18;
    if ( GetLastError() == 2 || GetLastError() == 3 )
    {
      v6 = 1938;
      goto LABEL_22;
    }
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
LABEL_18:
      CloseHandle((HANDLE)FileW);
      FileW = -1;
    }
  }
  LastFailureAsHRESULT = SxClearDifficultAttributes(lpFileName, &v12);
  v8 = LastFailureAsHRESULT;
  v5 = 1947;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_20:
    v2 = v12;
    v10 = v5;
    goto LABEL_27;
  }
  v9 = 1947;
  if ( !RemoveDirectoryW(lpFileName) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v8 = LastFailureAsHRESULT;
    v5 = 1952;
    v11 = 1;
    goto LABEL_20;
  }
  v6 = 1952;
LABEL_22:
  LastFailureAsHRESULT = 0;
  v9 = v6;
  v8 = 0;
LABEL_29:
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
LABEL_31:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001dd98  mov     [rsp-18h+arg_8], rbx
0x18001dd9d  mov     [rsp-18h+arg_10], rsi
0x18001dda2  push    rbp
0x18001dda3  push    rdi
0x18001dda4  push    r14
0x18001dda6  mov     rbp, rsp
0x18001dda9  sub     rsp, 80h
0x18001ddb0  mov     rsi, rcx
0x18001ddb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ddba  lea     rbx, WPP_GLOBAL_Control
0x18001ddc1  cmp     rcx, rbx
0x18001ddc4  jz      short loc_18001DDE4
0x18001ddc6  test    dword ptr [rcx+1Ch], 20000000h
0x18001ddcd  jz      short loc_18001DDE4
0x18001ddcf  mov     rcx, [rcx+10h]
0x18001ddd3  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001ddda  mov     edx, 34h ; '4'
0x18001dddf  call    WPP_SF_
0x18001dde4  mov     r9d, 1; unsigned __int16
0x18001ddea  lea     rdx, aDeletedirector_0; "_DeleteDirectory"
0x18001ddf1  mov     r8d, 774h; unsigned __int16
0x18001ddf7  lea     rcx, [rbp+var_40]; this
0x18001ddfb  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001de00  or      r14d, 0FFFFFFFFh
0x18001de04  mov     eax, 779h
0x18001de09  mov     [rbp+arg_0], r14d
0x18001de0d  test    rsi, rsi
0x18001de10  jnz     short loc_18001DE23
0x18001de12  mov     edi, 80070057h
0x18001de17  mov     [rbp+var_3A], ax
0x18001de1b  mov     [rbp+var_40], edi
0x18001de1e  jmp     loc_18001DFB0
0x18001de23  mov     [rbp+var_40], 0
0x18001de2a  mov     [rbp+var_3C], ax
0x18001de2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de35  cmp     rcx, rbx
0x18001de38  jz      short loc_18001DE5B
0x18001de3a  test    dword ptr [rcx+1Ch], 10000000h
0x18001de41  jz      short loc_18001DE5B
0x18001de43  mov     rcx, [rcx+10h]
0x18001de47  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001de4e  mov     edx, 35h ; '5'
0x18001de53  mov     r9, rsi
0x18001de56  call    WPP_SF_S
0x18001de5b  mov     rcx, rsi; lpPathName
0x18001de5e  call    cs:__imp_RemoveDirectoryW
0x18001de64  test    eax, eax
0x18001de66  jz      short loc_18001DE7F
0x18001de68  mov     eax, 77Fh
0x18001de6d  mov     [rbp+var_40], 0
0x18001de74  mov     [rbp+var_3C], ax
0x18001de78  xor     edi, edi
0x18001de7a  jmp     loc_18001DFB0
0x18001de7f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001de83  mov     rbx, rdi
0x18001de86  call    cs:__imp_GetLastError
0x18001de8c  cmp     eax, 2
0x18001de8f  jz      loc_18001DF7B
0x18001de95  call    cs:__imp_GetLastError
0x18001de9b  cmp     eax, 3
0x18001de9e  jz      loc_18001DF7B
0x18001dea4  call    cs:__imp_GetLastError
0x18001deaa  cmp     eax, 5
0x18001dead  jnz     short loc_18001DF17
0x18001deaf  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18001deb8  lea     r8d, [rdi+8]; dwShareMode
0x18001debc  mov     [rsp+80h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18001dec4  xor     r9d, r9d; lpSecurityAttributes
0x18001dec7  mov     edx, 100000h; dwDesiredAccess
0x18001decc  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x18001ded4  mov     rcx, rsi; lpFileName
0x18001ded7  call    cs:__imp_CreateFileW
0x18001dedd  mov     rbx, rax
0x18001dee0  inc     rax
0x18001dee3  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001dee9  jnz     short loc_18001DF0B
0x18001deeb  call    cs:__imp_GetLastError
0x18001def1  cmp     eax, 2
0x18001def4  jz      short loc_18001DF3B
0x18001def6  call    cs:__imp_GetLastError
0x18001defc  cmp     eax, 3
0x18001deff  jz      short loc_18001DF3B
0x18001df01  lea     rax, [rbx-1]
0x18001df05  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001df09  ja      short loc_18001DF17
0x18001df0b  mov     rcx, rbx; hObject
0x18001df0e  call    cs:__imp_CloseHandle
0x18001df14  mov     rbx, rdi
0x18001df17  lea     rdx, [rbp+arg_0]; unsigned int *
0x18001df1b  mov     rcx, rsi; lpFileName
0x18001df1e  call    ?SxClearDifficultAttributes@@YAJPEBGPEAK@Z; SxClearDifficultAttributes(ushort const *,ulong *)
0x18001df23  mov     edi, eax
0x18001df25  mov     [rbp+var_40], eax
0x18001df28  test    eax, eax
0x18001df2a  mov     eax, 79Bh
0x18001df2f  jns     short loc_18001DF4B
0x18001df31  mov     r14d, [rbp+arg_0]
0x18001df35  mov     [rbp+var_3A], ax
0x18001df39  jmp     short loc_18001DF89
0x18001df3b  mov     eax, 792h
0x18001df40  xor     edi, edi
0x18001df42  mov     [rbp+var_3C], ax
0x18001df46  mov     [rbp+var_40], edi
0x18001df49  jmp     short loc_18001DF9D
0x18001df4b  mov     rcx, rsi; lpPathName
0x18001df4e  mov     [rbp+var_3C], ax
0x18001df52  call    cs:__imp_RemoveDirectoryW
0x18001df58  test    eax, eax
0x18001df5a  jnz     short loc_18001DF74
0x18001df5c  call    GetLastFailureAsHRESULT
0x18001df61  mov     edi, eax
0x18001df63  mov     [rbp+var_40], eax
0x18001df66  mov     eax, 7A0h
0x18001df6b  mov     [rbp+var_38], 1
0x18001df72  jmp     short loc_18001DF31
0x18001df74  mov     eax, 7A0h
0x18001df79  jmp     short loc_18001DF40
0x18001df7b  xor     edi, edi
0x18001df7d  mov     eax, 784h
0x18001df82  mov     [rbp+var_40], edi
0x18001df85  mov     [rbp+var_3C], ax
0x18001df89  cmp     r14d, 0FFFFFFFFh
0x18001df8d  jz      short loc_18001DF9D
0x18001df8f  mov     edx, r14d; unsigned int
0x18001df92  mov     rcx, rsi; lpFileName
0x18001df95  call    ?SxSetFileAttributes@@YAJPEBGK@Z; SxSetFileAttributes(ushort const *,ulong)
0x18001df9a  mov     edi, [rbp+var_40]
0x18001df9d  lea     rcx, [rbx-1]
0x18001dfa1  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001dfa5  ja      short loc_18001DFB0
0x18001dfa7  mov     rcx, rbx; hObject
0x18001dfaa  call    cs:__imp_CloseHandle
0x18001dfb0  lea     rcx, [rbp+var_40]; this
0x18001dfb4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001dfb9  lea     r11, [rsp+80h+var_s0]
0x18001dfc1  mov     eax, edi
0x18001dfc3  mov     rbx, [r11+28h]
0x18001dfc7  mov     rsi, [r11+30h]
0x18001dfcb  mov     rsp, r11
0x18001dfce  pop     r14
0x18001dfd0  pop     rdi
0x18001dfd1  pop     rbp
0x18001dfd2  retn
```
