# UtilCreateFile(wchar_t const *,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x18000e0a0`
- end: `0x18000e312`
- name: `?UtilCreateFile@@YAJPEB_W0KKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `626`
- prototype: `__int64 __usercall@<rax>(wchar_t *@<rcx>, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD, DWORD, HANDLE, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013b60`

## callees

- `0x1800029f4`
- `0x18000caf0`
- `0x18000cb10`
- `0x18000e0a0`
- `0x18000f5e0`
- `0x1800101dc`
- `0x1800106f4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e230`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e230`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e26b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e26b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2f1`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x18000e278`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x18000e278`

## string_xrefs

- `0x18000e0d6`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x18000e15d`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x18000e1a8`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x18000e24b`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x18000e29a`: `onecore\windows\feedback\core\common\lib\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UtilCreateFile(
        wchar_t *a1,
        void *a2,
        DWORD a3,
        DWORD a4,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        DWORD a6,
        DWORD dwFlagsAndAttributes,
        HANDLE hTemplateFile,
        void **a9)
{
  __int64 v12; // rdx
  unsigned int v13; // ebx
  void **v15; // rdi
  void *v16; // rcx
  HANDLE v17; // rbx
  DWORD v18; // r14d
  int ParentDirectory; // eax
  int v20; // eax
  const char *v21; // r9
  HANDLE FileW; // r14
  unsigned int LastError; // edi
  int v24; // r8d
  int v25; // r9d
  int v26; // eax
  unsigned int v27; // esi
  void *v28; // rcx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-40h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-40h]
  wchar_t *v31[2]; // [rsp+40h] [rbp-20h] BYREF
  _WORD v32[8]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  HANDLE hObject; // [rsp+98h] [rbp+38h] BYREF

  hObject = a2;
  if ( !a1 )
  {
    v12 = 6072;
LABEL_3:
    v13 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return v13;
  }
  v15 = a9;
  if ( !a9 )
  {
    v12 = 6073;
    goto LABEL_3;
  }
  v16 = *a9;
  *a9 = 0;
  if ( (unsigned __int64)v16 + 1 > 1 )
    CloseHandle(v16);
  v17 = 0;
  hObject = 0;
  v18 = a6;
  if ( a6 != 3 )
  {
    v31[0] = v32;
    v31[1] = v32;
    v32[0] = 0;
    ParentDirectory = UtilGetParentDirectory(a1, v31);
    v13 = ParentDirectory;
    if ( ParentDirectory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17D1,
        (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
        (const char *)(unsigned int)ParentDirectory,
        dwCreationDisposition);
      if ( v31[0] != v32 )
        operator delete(v31[0], (const struct std::nothrow_t *)&std::nothrow);
      return v13;
    }
    v20 = UtilVerifyAndLockDirectory(v31[0], &hObject);
    v13 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17D7,
        (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
        (const char *)(unsigned int)v20,
        dwCreationDisposition);
      if ( v31[0] != v32 )
        operator delete(v31[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( (unsigned __int64)hObject + 1 > 1 )
        CloseHandle(hObject);
      return v13;
    }
    if ( v31[0] != v32 )
      operator delete(v31[0], (const struct std::nothrow_t *)&std::nothrow);
    v17 = hObject;
  }
  FileW = CreateFileW(a1, a3, a4, lpSecurityAttributes, v18, dwFlagsAndAttributes, hTemplateFile);
  if ( (unsigned __int64)FileW + 1 > 1 )
  {
    if ( (unsigned __int8)XerShouldWerManageRootDirectory()
      && (v26 = UtilVerifyFilePath(a1, FileW, v24, v25), v27 = v26, v26 < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17F3,
        (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
        (const char *)(unsigned int)v26,
        dwCreationDispositiona);
      CloseHandle(FileW);
      if ( (unsigned __int64)v17 + 1 > 1 )
        CloseHandle(v17);
      return v27;
    }
    else
    {
      v28 = *v15;
      *v15 = FileW;
      if ( (unsigned __int64)v28 + 1 > 1 )
        CloseHandle(v28);
      if ( (unsigned __int64)v17 + 1 > 1 )
        CloseHandle(v17);
      return 0;
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x17E2,
                  (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
                  v21);
    if ( (unsigned __int64)v17 + 1 > 1 )
      CloseHandle(v17);
    return LastError;
  }
}

```

## disassembly

```asm
0x18000e0a0  mov     [rsp-28h+arg_10], rbx
0x18000e0a5  mov     [rsp-28h+arg_18], rsi
0x18000e0aa  mov     [rsp-28h+hObject], rdx
0x18000e0af  push    rbp
0x18000e0b0  push    rdi
0x18000e0b1  push    r12
0x18000e0b3  push    r14
0x18000e0b5  push    r15
0x18000e0b7  mov     rbp, rsp
0x18000e0ba  sub     rsp, 60h
0x18000e0be  mov     r15d, r9d
0x18000e0c1  mov     r12d, r8d
0x18000e0c4  mov     rsi, rcx
0x18000e0c7  test    rcx, rcx
0x18000e0ca  jnz     short loc_18000E0F0
0x18000e0cc  mov     edx, 17B8h; void *
0x18000e0d1  mov     ebx, 80070057h
0x18000e0d6  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\commo"...
0x18000e0dd  mov     r9d, ebx; char *
0x18000e0e0  mov     rcx, [rbp+28h]; this
0x18000e0e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e0e9  mov     eax, ebx
0x18000e0eb  jmp     loc_18000E2F9
0x18000e0f0  mov     rdi, [rbp+arg_40]
0x18000e0f4  test    rdi, rdi
0x18000e0f7  jnz     short loc_18000E100
0x18000e0f9  mov     edx, 17B9h
0x18000e0fe  jmp     short loc_18000E0D1
0x18000e100  mov     rcx, [rdi]; hObject
0x18000e103  mov     qword ptr [rdi], 0
0x18000e10a  lea     rax, [rcx+1]
0x18000e10e  cmp     rax, 1
0x18000e112  jbe     short loc_18000E11A
0x18000e114  call    cs:__imp_CloseHandle
0x18000e11a  xor     ebx, ebx
0x18000e11c  mov     [rbp+hObject], rbx
0x18000e120  mov     r14d, [rbp+arg_28]
0x18000e124  cmp     r14d, 3
0x18000e128  jz      loc_18000E20E
0x18000e12e  lea     rax, [rbp+var_10]
0x18000e132  mov     [rbp+var_20], rax
0x18000e136  lea     rax, [rbp+var_10]
0x18000e13a  mov     [rbp+var_18], rax
0x18000e13e  xor     eax, eax
0x18000e140  mov     [rbp+var_10], ax
0x18000e144  lea     rdx, [rbp+var_20]
0x18000e148  mov     rcx, rsi
0x18000e14b  call    ?UtilGetParentDirectory@@YAJPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetParentDirectory(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18000e150  mov     ebx, eax
0x18000e152  test    eax, eax
0x18000e154  jns     short loc_18000E18E
0x18000e156  mov     rcx, [rbp+28h]; this
0x18000e15a  mov     r9d, eax; char *
0x18000e15d  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\commo"...
0x18000e164  mov     edx, 17D1h; void *
0x18000e169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e16e  nop
0x18000e16f  lea     rax, [rbp+var_10]
0x18000e173  mov     rcx, [rbp+var_20]; void *
0x18000e177  cmp     rcx, rax
0x18000e17a  jz      short loc_18000E189
0x18000e17c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e183  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e188  nop
0x18000e189  jmp     loc_18000E0E9
0x18000e18e  lea     rdx, [rbp+hObject]
0x18000e192  mov     rcx, [rbp+var_20]; wchar_t *
0x18000e196  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x18000e19b  mov     ebx, eax
0x18000e19d  test    eax, eax
0x18000e19f  jns     short loc_18000E1F1
0x18000e1a1  mov     rcx, [rbp+28h]; this
0x18000e1a5  mov     r9d, eax; char *
0x18000e1a8  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\commo"...
0x18000e1af  mov     edx, 17D7h; void *
0x18000e1b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e1b9  nop
0x18000e1ba  lea     rax, [rbp+var_10]
0x18000e1be  mov     rcx, [rbp+var_20]; void *
0x18000e1c2  cmp     rcx, rax
0x18000e1c5  jz      short loc_18000E1D4
0x18000e1c7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e1ce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e1d3  nop
0x18000e1d4  mov     rcx, [rbp+hObject]; hObject
0x18000e1d8  lea     rax, [rcx+1]
0x18000e1dc  cmp     rax, 1
0x18000e1e0  jbe     loc_18000E0E9
0x18000e1e6  call    cs:__imp_CloseHandle
0x18000e1ec  jmp     loc_18000E0E9
0x18000e1f1  lea     rax, [rbp+var_10]
0x18000e1f5  mov     rcx, [rbp+var_20]; void *
0x18000e1f9  cmp     rcx, rax
0x18000e1fc  jz      short loc_18000E20A
0x18000e1fe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e205  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e20a  mov     rbx, [rbp+hObject]
0x18000e20e  mov     rax, [rbp+arg_38]
0x18000e212  mov     [rsp+60h+hTemplateFile], rax; hTemplateFile
0x18000e217  mov     eax, [rbp+arg_30]
0x18000e21a  mov     [rsp+60h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18000e21e  mov     [rsp+60h+dwCreationDisposition], r14d; int
0x18000e223  mov     r9, [rbp+lpSecurityAttributes]; lpSecurityAttributes
0x18000e227  mov     r8d, r15d; dwShareMode
0x18000e22a  mov     edx, r12d; dwDesiredAccess
0x18000e22d  mov     rcx, rsi; lpFileName
0x18000e230  call    cs:__imp_CreateFileW
0x18000e236  mov     r14, rax
0x18000e239  mov     [rbp+arg_0], rax
0x18000e23d  lea     rcx, [rax+1]
0x18000e241  cmp     rcx, 1
0x18000e245  ja      short loc_18000E278
0x18000e247  mov     rcx, [rbp+28h]; this
0x18000e24b  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\commo"...
0x18000e252  mov     edx, 17E2h; void *
0x18000e257  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e25c  mov     edi, eax
0x18000e25e  lea     rcx, [rbx+1]
0x18000e262  cmp     rcx, 1
0x18000e266  jbe     short loc_18000E271
0x18000e268  mov     rcx, rbx; hObject
0x18000e26b  call    cs:__imp_CloseHandle
0x18000e271  mov     eax, edi
0x18000e273  jmp     loc_18000E2F9
0x18000e278  call    cs:__imp_XerShouldWerManageRootDirectory
0x18000e27e  test    al, al
0x18000e280  jz      short loc_18000E2CD
0x18000e282  mov     rdx, r14; void *
0x18000e285  mov     rcx, rsi; wchar_t *
0x18000e288  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x18000e28d  mov     esi, eax
0x18000e28f  test    eax, eax
0x18000e291  jns     short loc_18000E2CD
0x18000e293  mov     rcx, [rbp+28h]; this
0x18000e297  mov     r9d, eax; char *
0x18000e29a  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\commo"...
0x18000e2a1  mov     edx, 17F3h; void *
0x18000e2a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e2ab  nop
0x18000e2ac  mov     rcx, r14; hObject
0x18000e2af  call    cs:__imp_CloseHandle
0x18000e2b5  nop
0x18000e2b6  lea     rax, [rbx+1]
0x18000e2ba  cmp     rax, 1
0x18000e2be  jbe     short loc_18000E2C9
0x18000e2c0  mov     rcx, rbx; hObject
0x18000e2c3  call    cs:__imp_CloseHandle
0x18000e2c9  mov     eax, esi
0x18000e2cb  jmp     short loc_18000E2F9
0x18000e2cd  mov     rcx, [rdi]; hObject
0x18000e2d0  mov     [rdi], r14
0x18000e2d3  lea     rax, [rcx+1]
0x18000e2d7  cmp     rax, 1
0x18000e2db  jbe     short loc_18000E2E4
0x18000e2dd  call    cs:__imp_CloseHandle
0x18000e2e3  nop
0x18000e2e4  lea     rax, [rbx+1]
0x18000e2e8  cmp     rax, 1
0x18000e2ec  jbe     short loc_18000E2F7
0x18000e2ee  mov     rcx, rbx; hObject
0x18000e2f1  call    cs:__imp_CloseHandle
0x18000e2f7  xor     eax, eax
0x18000e2f9  lea     r11, [rsp+60h+var_s0]
0x18000e2fe  mov     rbx, [r11+40h]
0x18000e302  mov     rsi, [r11+48h]
0x18000e306  mov     rsp, r11
0x18000e309  pop     r15
0x18000e30b  pop     r14
0x18000e30d  pop     r12
0x18000e30f  pop     rdi
0x18000e310  pop     rbp
0x18000e311  retn
```
