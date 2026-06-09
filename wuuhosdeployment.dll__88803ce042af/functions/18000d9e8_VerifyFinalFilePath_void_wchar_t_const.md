# VerifyFinalFilePath(void *,wchar_t const *)

- ea: `0x18000d9e8`
- end: `0x18000dd43`
- name: `?VerifyFinalFilePath@@YAJPEAXPEB_W@Z`
- size: `859`
- prototype: `__int64 __fastcall(HANDLE hFile, PCNZWCH lpString1)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18000c714`
- `0x18000dd4c`

## callees

- `0x180003950`
- `0x180003974`
- `0x180005f64`
- `0x18000956c`
- `0x18000a6d0`
- `0x18000aa74`
- `0x18000ac44`
- `0x18000ad4c`
- `0x18000b658`
- `0x18000c0e4`
- `0x18000d9e8`
- `0x1800425d8`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000db8f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000dc05`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000db8f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000dc05`

## string_xrefs

- `0x18000db26`: `Input path: %ws, is not under the secure SusBaseDirectory path for this system. Performing redirection checks.`
- `0x18000dc7c`: `Unexpected path detected! Input path: %ws ; Final resolved path: %ws`

## pseudocode

```c
int __fastcall VerifyFinalFilePath(HANDLE hFile, PCNZWCH lpString1)
{
  unsigned __int64 v2; // rbx
  __int64 v5; // rdx
  DWORD v6; // r12d
  __int64 v7; // rdx
  unsigned int *v8; // r9
  int SusBaseDirectoryW; // ebx
  BOOL v10; // ecx
  WCHAR *p_String1; // rdx
  DWORD FinalPathNameByHandleW; // eax
  const char *v14; // r9
  unsigned int v15; // r14d
  WCHAR *v16; // rbx
  unsigned int v17; // esi
  const char *v18; // r9
  int LastError; // eax
  const WCHAR *v20; // rsi
  unsigned int v21; // [rsp+20h] [rbp-E0h]
  unsigned int v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t v23[12]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String1; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v25; // [rsp+68h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v2 = -1;
  if ( hFile == (HANDLE)-1LL )
  {
    v5 = 1642;
LABEL_45:
    SusBaseDirectoryW = -2147024809;
    goto LABEL_46;
  }
  if ( !lpString1 || !*lpString1 )
  {
    v5 = 1643;
    goto LABEL_45;
  }
  v6 = 0;
  wcscpy(v23, L"\\\\?\\");
  do
    ++v2;
  while ( lpString1[v2] );
  if ( v2 < 2 || (unsigned int)WUCompareStringCchI(lpString1, v23, 4u) == 2 && v2 - 4 < 2 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x678,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
             (const char *)0xA1,
             v21);
  SusBaseDirectoryW = GetSusBaseDirectoryW(&String1, v7, 0, v8);
  if ( SusBaseDirectoryW >= 0 )
  {
    *(_QWORD *)v22 = 0;
    v10 = SusStrCchLen(v23, 0x7FFFFFFFu, (unsigned __int64 *)v22) >= 0
       && WUCompareStringCchI(&String1, v23, v22[0]) == 2;
    p_String1 = &String1;
    if ( v10 )
      p_String1 = &v25;
    if ( (int)WUStringContainsI(lpString1, p_String1) >= 0 )
      return 0;
    WUTrace(0, 0, 32, 5);
    if ( ((unsigned int)WUCompareStringCchI(lpString1, v23, 4u) != 2 || !iswalpha(lpString1[4]) || lpString1[5] != 58)
      && (!iswalpha(*lpString1) || lpString1[1] != 58) )
    {
      v6 = 4;
    }
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, v6);
    v15 = FinalPathNameByHandleW;
    if ( !FinalPathNameByHandleW )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x6A7,
               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
               v14);
    v16 = (WCHAR *)SafeSusAllocArray(FinalPathNameByHandleW, 2u);
    v17 = v16 == 0 ? 0x8007000E : 0;
    if ( v16 )
    {
      if ( GetFinalPathNameByHandleW(hFile, v16, v15, v6) )
      {
        v20 = v16;
        if ( iswalpha(*lpString1) && lpString1[1] == 58 && (unsigned int)WUCompareStringCchI(v16, v23, 4u) == 2 )
        {
          v20 = v16 + 4;
          v15 -= 4;
        }
        if ( (unsigned int)WUCompareStringCchI(v20, lpString1, v15) == 2 )
        {
          v17 = 0;
          goto LABEL_41;
        }
        WUTrace(0, 0, 32, 3);
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x6C1,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
                      (const char *)0xA1,
                      0);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x6AC,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
                      v18);
      }
      v17 = LastError;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6AB,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
        (const char *)v17,
        0);
    }
    if ( !v16 )
      return v17;
LABEL_41:
    CSusBaseAllocTag<942762101>::operator delete(v16);
    return v17;
  }
  v5 = 1666;
LABEL_46:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
    (const char *)(unsigned int)SusBaseDirectoryW,
    v21);
  return SusBaseDirectoryW;
}

```

## disassembly

```asm
0x18000d9e8  mov     [rsp-8+arg_10], rbx
0x18000d9ed  push    rbp
0x18000d9ee  push    rsi
0x18000d9ef  push    rdi
0x18000d9f0  push    r12
0x18000d9f2  push    r13
0x18000d9f4  push    r14
0x18000d9f6  push    r15
0x18000d9f8  lea     rbp, [rsp-180h]
0x18000da00  sub     rsp, 280h
0x18000da07  mov     rax, cs:__security_cookie
0x18000da0e  xor     rax, rsp
0x18000da11  mov     [rbp+1B0h+var_40], rax
0x18000da18  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000da1c  mov     rdi, rdx
0x18000da1f  mov     r15, rcx
0x18000da22  cmp     rcx, rbx
0x18000da25  jnz     short loc_18000DA31
0x18000da27  mov     edx, 66Ah
0x18000da2c  jmp     loc_18000DCFC
0x18000da31  xor     r13d, r13d
0x18000da34  test    rdi, rdi
0x18000da37  jz      loc_18000DCF7
0x18000da3d  cmp     [rdx], r13w
0x18000da41  jz      loc_18000DCF7
0x18000da47  movsd   xmm0, qword ptr cs:asc_18004FB60; "\\\\?\\"
0x18000da4f  mov     r12d, r13d
0x18000da52  movzx   eax, word ptr cs:asc_18004FB60+8; ""
0x18000da59  movsd   qword ptr [rsp+2B0h+var_268], xmm0
0x18000da5f  mov     [rsp+2B0h+var_260], ax
0x18000da64  inc     rbx
0x18000da67  cmp     [rdx+rbx*2], r13w
0x18000da6c  jnz     short loc_18000DA64
0x18000da6e  mov     esi, 2
0x18000da73  cmp     rbx, rsi
0x18000da76  jb      loc_18000DCD7
0x18000da7c  lea     r14d, [rsi+2]
0x18000da80  mov     rcx, rdi; lpString1
0x18000da83  mov     r8d, r14d; unsigned int
0x18000da86  lea     rdx, [rsp+2B0h+var_268]; wchar_t *
0x18000da8b  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x18000da90  cmp     eax, esi
0x18000da92  jnz     short loc_18000DAA1
0x18000da94  lea     rax, [rbx-4]
0x18000da98  cmp     rax, rsi
0x18000da9b  jb      loc_18000DCD7
0x18000daa1  xor     r8d, r8d; wchar_t *
0x18000daa4  lea     rcx, [rsp+2B0h+String1]; wchar_t *
0x18000daa9  call    ?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z; GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)
0x18000daae  mov     ebx, eax
0x18000dab0  test    eax, eax
0x18000dab2  jns     short loc_18000DABE
0x18000dab4  mov     edx, 682h
0x18000dab9  jmp     loc_18000DD01
0x18000dabe  lea     r8, [rsp+2B0h+var_270]; unsigned __int64 *
0x18000dac3  mov     qword ptr [rsp+2B0h+var_270], r13
0x18000dac8  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000dacd  lea     rcx, [rsp+2B0h+var_268]; wchar_t *
0x18000dad2  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18000dad7  test    eax, eax
0x18000dad9  jns     short loc_18000DAE0
0x18000dadb  mov     ecx, r13d
0x18000dade  jmp     short loc_18000DAFC
0x18000dae0  mov     r8d, [rsp+2B0h+var_270]; unsigned int
0x18000dae5  lea     rdx, [rsp+2B0h+var_268]; wchar_t *
0x18000daea  lea     rcx, [rsp+2B0h+String1]; lpString1
0x18000daef  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x18000daf4  cmp     eax, esi
0x18000daf6  mov     ecx, r13d
0x18000daf9  setz    cl
0x18000dafc  test    ecx, ecx
0x18000dafe  lea     rax, [rsp+2B0h+var_248]
0x18000db03  lea     rdx, [rsp+2B0h+String1]
0x18000db08  mov     rcx, rdi; lpString1
0x18000db0b  cmovnz  rdx, rax; wchar_t *
0x18000db0f  call    ?WUStringContainsI@@YAHPEB_W0@Z; WUStringContainsI(wchar_t const *,wchar_t const *)
0x18000db14  test    eax, eax
0x18000db16  js      short loc_18000DB1F
0x18000db18  xor     eax, eax
0x18000db1a  jmp     loc_18000DD19
0x18000db1f  xor     edx, edx
0x18000db21  mov     [rsp+2B0h+var_280], rdi
0x18000db26  lea     rax, aInputPathWsIsN; "Input path: %ws, is not under the secur"...
0x18000db2d  xor     ecx, ecx
0x18000db2f  mov     [rsp+2B0h+var_288], rax
0x18000db34  mov     qword ptr [rsp+2B0h+var_290], r13; int
0x18000db39  lea     r9d, [rdx+5]
0x18000db3d  lea     r8d, [rdx+20h]
0x18000db41  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18000db46  mov     r8d, r14d; unsigned int
0x18000db49  lea     rdx, [rsp+2B0h+var_268]; wchar_t *
0x18000db4e  mov     rcx, rdi; lpString1
0x18000db51  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x18000db56  cmp     eax, esi
0x18000db58  jnz     short loc_18000DB6E
0x18000db5a  movzx   ecx, word ptr [rdi+8]; C
0x18000db5e  call    iswalpha
0x18000db63  test    eax, eax
0x18000db65  jz      short loc_18000DB6E
0x18000db67  cmp     word ptr [rdi+0Ah], 3Ah ; ':'
0x18000db6c  jz      short loc_18000DB84
0x18000db6e  movzx   ecx, word ptr [rdi]; C
0x18000db71  call    iswalpha
0x18000db76  test    eax, eax
0x18000db78  jz      short loc_18000DB81
0x18000db7a  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18000db7f  jz      short loc_18000DB84
0x18000db81  mov     r12d, r14d
0x18000db84  mov     r9d, r12d; dwFlags
0x18000db87  xor     r8d, r8d; cchFilePath
0x18000db8a  xor     edx, edx; lpszFilePath
0x18000db8c  mov     rcx, r15; hFile
0x18000db8f  call    cs:__imp_GetFinalPathNameByHandleW
0x18000db95  mov     r14d, eax
0x18000db98  test    eax, eax
0x18000db9a  jnz     short loc_18000DBB9
0x18000db9c  mov     rcx, [rbp+1B8h]; this
0x18000dba3  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000dbaa  mov     edx, 6A7h; void *
0x18000dbaf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dbb4  jmp     loc_18000DD19
0x18000dbb9  mov     rcx, r14; unsigned __int64
0x18000dbbc  mov     rdx, rsi; unsigned __int64
0x18000dbbf  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18000dbc4  mov     rbx, rax
0x18000dbc7  neg     rax
0x18000dbca  sbb     esi, esi
0x18000dbcc  not     esi
0x18000dbce  and     esi, 8007000Eh
0x18000dbd4  test    rbx, rbx
0x18000dbd7  jnz     short loc_18000DBF9
0x18000dbd9  mov     rcx, [rbp+1B8h]; this
0x18000dbe0  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000dbe7  mov     r9d, esi; char *
0x18000dbea  mov     edx, 6ABh; void *
0x18000dbef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dbf4  jmp     loc_18000DCC1
0x18000dbf9  mov     r9d, r12d; dwFlags
0x18000dbfc  mov     r8d, r14d; cchFilePath
0x18000dbff  mov     rdx, rbx; lpszFilePath
0x18000dc02  mov     rcx, r15; hFile
0x18000dc05  call    cs:__imp_GetFinalPathNameByHandleW
0x18000dc0b  test    eax, eax
0x18000dc0d  jnz     short loc_18000DC2C
0x18000dc0f  mov     rcx, [rbp+1B8h]; this
0x18000dc16  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000dc1d  mov     edx, 6ACh; void *
0x18000dc22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dc27  jmp     loc_18000DCBF
0x18000dc2c  movzx   ecx, word ptr [rdi]; C
0x18000dc2f  mov     rsi, rbx
0x18000dc32  call    iswalpha
0x18000dc37  test    eax, eax
0x18000dc39  jz      short loc_18000DC62
0x18000dc3b  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18000dc40  jnz     short loc_18000DC62
0x18000dc42  mov     r8d, 4; unsigned int
0x18000dc48  lea     rdx, [rsp+2B0h+var_268]; wchar_t *
0x18000dc4d  mov     rcx, rbx; lpString1
0x18000dc50  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x18000dc55  cmp     eax, 2
0x18000dc58  jnz     short loc_18000DC62
0x18000dc5a  lea     rsi, [rbx+8]
0x18000dc5e  add     r14d, 0FFFFFFFCh
0x18000dc62  mov     r8d, r14d; unsigned int
0x18000dc65  mov     rdx, rdi; wchar_t *
0x18000dc68  mov     rcx, rsi; lpString1
0x18000dc6b  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x18000dc70  cmp     eax, 2
0x18000dc73  jz      short loc_18000DCC8
0x18000dc75  xor     edx, edx
0x18000dc77  mov     [rsp+2B0h+var_278], rsi
0x18000dc7c  lea     rax, aUnexpectedPath; "Unexpected path detected! Input path: %"...
0x18000dc83  mov     [rsp+2B0h+var_280], rdi
0x18000dc88  mov     [rsp+2B0h+var_288], rax
0x18000dc8d  xor     ecx, ecx
0x18000dc8f  mov     qword ptr [rsp+2B0h+var_290], r13; unsigned int
0x18000dc94  lea     r9d, [rdx+3]
0x18000dc98  lea     r8d, [rdx+20h]
0x18000dc9c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18000dca1  mov     rcx, [rbp+1B8h]; this
0x18000dca8  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000dcaf  mov     r9d, 0A1h; char *
0x18000dcb5  mov     edx, 6C1h; void *
0x18000dcba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000dcbf  mov     esi, eax
0x18000dcc1  test    rbx, rbx
0x18000dcc4  jz      short loc_18000DCD3
0x18000dcc6  jmp     short loc_18000DCCB
0x18000dcc8  mov     esi, r13d
0x18000dccb  mov     rcx, rbx; lpMem
0x18000dcce  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18000dcd3  mov     eax, esi
0x18000dcd5  jmp     short loc_18000DD19
0x18000dcd7  mov     rcx, [rbp+1B8h]; this
0x18000dcde  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000dce5  mov     r9d, 0A1h; char *
0x18000dceb  mov     edx, 678h; void *
0x18000dcf0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000dcf5  jmp     short loc_18000DD19
0x18000dcf7  mov     edx, 66Bh; void *
0x18000dcfc  mov     ebx, 80070057h
0x18000dd01  mov     rcx, [rbp+1B8h]; this
0x18000dd08  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000dd0f  mov     r9d, ebx; char *
0x18000dd12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd17  mov     eax, ebx
0x18000dd19  mov     rcx, [rbp+1B0h+var_40]
0x18000dd20  xor     rcx, rsp; StackCookie
0x18000dd23  call    __security_check_cookie
0x18000dd28  mov     rbx, [rsp+2B0h+arg_10]
0x18000dd30  add     rsp, 280h
0x18000dd37  pop     r15
0x18000dd39  pop     r14
0x18000dd3b  pop     r13
0x18000dd3d  pop     r12
0x18000dd3f  pop     rdi
0x18000dd40  pop     rsi
0x18000dd41  pop     rbp
0x18000dd42  retn
```
