# CommonUtilities::DeleteDirectory(ushort const *)

- ea: `0x1400aed48`
- end: `0x1400aefde`
- name: `?DeleteDirectory@CommonUtilities@@YAJPEBG@Z`
- size: `662`
- prototype: `__int64 __fastcall(CommonUtilities *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400ae8c8`
- `0x1400aed48`

## callees

- `0x140005360`
- `0x140006098`
- `0x140008760`
- `0x14000ddac`
- `0x14000ea60`
- `0x1400341ac`
- `0x140041ff0`
- `0x1400aed48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400aeec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400aeec4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400aeeb6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400aeeb6`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400aef17`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400aef17`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1400aedac`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1400aedac`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1400aee67`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1400aeedb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1400aee67`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1400aeedb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400aee8e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400aee8e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1400aeef4`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1400aeef4`

## string_xrefs

- `0x1400aef55`: `onecore\vm\inc\CommonUtilities.h`
- `0x1400aef6a`: `onecore\vm\inc\CommonUtilities.h`
- `0x1400aef7b`: `onecore\vm\inc\CommonUtilities.h`
- `0x1400aef8c`: `onecore\vm\inc\CommonUtilities.h`
- `0x1400aefa9`: `onecore\vm\inc\CommonUtilities.h`
- `0x1400aefba`: `onecore\vm\inc\CommonUtilities.h`
- `0x1400aefcb`: `onecore\vm\inc\CommonUtilities.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CommonUtilities::DeleteDirectory(const WCHAR *this, const unsigned __int16 *a2)
{
  const WCHAR *v3; // rcx
  char *FirstFileW; // rbx
  const char *v5; // r9
  const unsigned __int16 *v6; // rdx
  LPCWSTR *v7; // rcx
  int v8; // eax
  const char *v9; // r9
  const WCHAR *v10; // rcx
  const char *v11; // r9
  DWORD LastError; // eax
  const char *v13; // r9
  const char *v14; // r9
  const char *v15; // r9
  __int64 result; // rax
  LPCWSTR lpPathName[3]; // [rsp+28h] [rbp-2B0h] BYREF
  unsigned __int64 v18; // [rsp+40h] [rbp-298h]
  LPCWSTR lpFileName[5]; // [rsp+48h] [rbp-290h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  try
  {
    CommonUtilities::CombineFilePath(lpFileName, this, L"*");
    v3 = (const WCHAR *)lpFileName;
    if ( lpFileName[3] > (LPCWSTR)7 )
      v3 = lpFileName[0];
    FirstFileW = (char *)FindFirstFileW(v3, &FindFileData);
    if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x15A,
        (unsigned int)"onecore\\vm\\inc\\CommonUtilities.h",
        v5);
    do
    {
      if ( FindFileData.cFileName[0] != 46
        || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
      {
        CommonUtilities::CombineFilePath(lpPathName, this, FindFileData.cFileName);
        v7 = lpPathName;
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          if ( v18 > 7 )
            v7 = (LPCWSTR *)lpPathName[0];
          v8 = CommonUtilities::DeleteDirectory((CommonUtilities *)v7, v6);
          if ( v8 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x169,
              (unsigned int)"onecore\\vm\\inc\\CommonUtilities.h",
              (const char *)(unsigned int)v8,
              (int)FirstFileW);
        }
        else
        {
          if ( v18 > 7 )
            v7 = (LPCWSTR *)lpPathName[0];
          if ( !SetFileAttributesW((LPCWSTR)v7, 0x80u) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x16D,
              (unsigned int)"onecore\\vm\\inc\\CommonUtilities.h",
              v9);
          v10 = (const WCHAR *)lpPathName;
          if ( v18 > 7 )
            v10 = lpPathName[0];
          if ( !DeleteFileW(v10) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x16E,
              (unsigned int)"onecore\\vm\\inc\\CommonUtilities.h",
              v11);
        }
        std::wstring::~wstring(lpPathName);
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    LastError = GetLastError();
    if ( LastError != 18 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x177,
        (unsigned int)"onecore\\vm\\inc\\CommonUtilities.h",
        (const char *)LastError,
        (unsigned int)FirstFileW);
    if ( !SetFileAttributesW(this, 0x80u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x17E,
        (unsigned int)"onecore\\vm\\inc\\CommonUtilities.h",
        v13);
    if ( !RemoveDirectoryW(this) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x17F,
        (unsigned int)"onecore\\vm\\inc\\CommonUtilities.h",
        v14);
    if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      FindClose(FirstFileW);
    std::wstring::~wstring(lpFileName);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x182,
                           (unsigned int)"onecore\\vm\\inc\\CommonUtilities.h",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x1400aed48  mov     [rsp+arg_8], rbx
0x1400aed4d  mov     [rsp+arg_10], rsi
0x1400aed52  push    rdi
0x1400aed53  sub     rsp, 2D0h
0x1400aed5a  mov     rax, cs:__security_cookie
0x1400aed61  xor     rax, rsp
0x1400aed64  mov     [rsp+2D8h+var_18], rax
0x1400aed6c  mov     rdi, rcx
0x1400aed6f  xor     edx, edx; Val
0x1400aed71  mov     r8d, 250h; Size
0x1400aed77  lea     rcx, [rsp+2D8h+FindFileData]; void *
0x1400aed7c  call    memset_0
0x1400aed81  lea     r8, asc_140125394; "*"
0x1400aed88  mov     rdx, rdi; pszPathIn
0x1400aed8b  lea     rcx, [rsp+2D8h+lpFileName]; Src
0x1400aed90  call    ?CombineFilePath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CommonUtilities::CombineFilePath(ushort const *,ushort const *)
0x1400aed95  nop
0x1400aed96  lea     rcx, [rsp+2D8h+lpFileName]
0x1400aed9b  cmp     [rsp+2D8h+var_278], 7
0x1400aeda1  cmova   rcx, [rsp+2D8h+lpFileName]; lpFileName
0x1400aeda7  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x1400aedac  call    cs:__imp_FindFirstFileW
0x1400aedb2  mov     rbx, rax
0x1400aedb5  mov     qword ptr [rsp+2D8h+var_2B8], rax; unsigned int
0x1400aedba  dec     rax
0x1400aedbd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400aedc1  setnbe  al
0x1400aedc4  mov     rcx, [rsp+2D8h]; this
0x1400aedcc  xor     esi, esi
0x1400aedce  test    al, al
0x1400aedd0  jnz     loc_1400AEF55
0x1400aedd6  movzx   eax, [rsp+2D8h+FindFileData.cFileName+2]
0x1400aedde  cmp     [rsp+2D8h+FindFileData.cFileName], 2Eh ; '.'
0x1400aede7  jnz     short loc_1400AEE11
0x1400aede9  test    ax, ax
0x1400aedec  jz      loc_1400AEEAE
0x1400aedf2  cmp     [rsp+2D8h+FindFileData.cFileName], 2Eh ; '.'
0x1400aedfb  jnz     short loc_1400AEE11
0x1400aedfd  cmp     ax, 2Eh ; '.'
0x1400aee01  jnz     short loc_1400AEE11
0x1400aee03  cmp     [rsp+2D8h+FindFileData.cFileName+4], si
0x1400aee0b  jz      loc_1400AEEAE
0x1400aee11  lea     r8, [rsp+2D8h+FindFileData.cFileName]; pszMore
0x1400aee19  mov     rdx, rdi; pszPathIn
0x1400aee1c  lea     rcx, [rsp+2D8h+lpPathName]; Src
0x1400aee21  call    ?CombineFilePath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CommonUtilities::CombineFilePath(ushort const *,ushort const *)
0x1400aee26  nop
0x1400aee27  lea     rcx, [rsp+2D8h+lpPathName]
0x1400aee2c  test    byte ptr [rsp+2D8h+FindFileData.dwFileAttributes], 10h
0x1400aee31  jz      short loc_1400AEE56
0x1400aee33  cmp     [rsp+2D8h+var_298], 7
0x1400aee39  cmova   rcx, [rsp+2D8h+lpPathName]; this
0x1400aee3f  call    ?DeleteDirectory@CommonUtilities@@YAJPEBG@Z; CommonUtilities::DeleteDirectory(ushort const *)
0x1400aee44  mov     rcx, [rsp+2D8h]; this
0x1400aee4c  test    eax, eax
0x1400aee4e  js      loc_1400AEF67
0x1400aee54  jmp     short loc_1400AEEA4
0x1400aee56  cmp     [rsp+2D8h+var_298], 7
0x1400aee5c  cmova   rcx, [rsp+2D8h+lpPathName]; lpFileName
0x1400aee62  mov     edx, 80h; dwFileAttributes
0x1400aee67  call    cs:__imp_SetFileAttributesW
0x1400aee6d  mov     rcx, [rsp+2D8h]; this
0x1400aee75  test    eax, eax
0x1400aee77  jz      loc_1400AEF7B
0x1400aee7d  lea     rcx, [rsp+2D8h+lpPathName]
0x1400aee82  cmp     [rsp+2D8h+var_298], 7
0x1400aee88  cmova   rcx, [rsp+2D8h+lpPathName]; lpFileName
0x1400aee8e  call    cs:__imp_DeleteFileW
0x1400aee94  mov     rcx, [rsp+2D8h]; this
0x1400aee9c  test    eax, eax
0x1400aee9e  jz      loc_1400AEF8C
0x1400aeea4  lea     rcx, [rsp+2D8h+lpPathName]; void *
0x1400aeea9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400aeeae  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x1400aeeb3  mov     rcx, rbx; hFindFile
0x1400aeeb6  call    cs:__imp_FindNextFileW
0x1400aeebc  test    eax, eax
0x1400aeebe  jnz     loc_1400AEDD6
0x1400aeec4  call    cs:__imp_GetLastError
0x1400aeeca  cmp     eax, 12h
0x1400aeecd  jnz     loc_1400AEF9E
0x1400aeed3  mov     edx, 80h; dwFileAttributes
0x1400aeed8  mov     rcx, rdi; lpFileName
0x1400aeedb  call    cs:__imp_SetFileAttributesW
0x1400aeee1  mov     rcx, [rsp+2D8h]; this
0x1400aeee9  test    eax, eax
0x1400aeeeb  jz      loc_1400AEFBA
0x1400aeef1  mov     rcx, rdi; lpPathName
0x1400aeef4  call    cs:__imp_RemoveDirectoryW
0x1400aeefa  mov     rcx, [rsp+2D8h]; this
0x1400aef02  test    eax, eax
0x1400aef04  jz      loc_1400AEFCB
0x1400aef0a  lea     rax, [rbx-1]
0x1400aef0e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400aef12  ja      short loc_1400AEF1E
0x1400aef14  mov     rcx, rbx; hFindFile
0x1400aef17  call    cs:__imp_FindClose
0x1400aef1d  nop
0x1400aef1e  lea     rcx, [rsp+2D8h+lpFileName]; void *
0x1400aef23  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400aef28  xor     eax, eax
0x1400aef2a  jmp     short loc_1400AEF30
0x1400aef2c  mov     eax, [rsp+2D8h+var_2B8]
0x1400aef30  mov     rcx, [rsp+2D8h+var_18]
0x1400aef38  xor     rcx, rsp; StackCookie
0x1400aef3b  call    __security_check_cookie
0x1400aef40  lea     r11, [rsp+2D8h+var_8]
0x1400aef48  mov     rbx, [r11+18h]
0x1400aef4c  mov     rsi, [r11+20h]
0x1400aef50  mov     rsp, r11
0x1400aef53  pop     rdi
0x1400aef54  retn
0x1400aef55  lea     r8, aOnecoreVmIncCo; "onecore\\vm\\inc\\CommonUtilities.h"
0x1400aef5c  mov     edx, 15Ah; void *
0x1400aef61  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400aef67  mov     r9d, eax; char *
0x1400aef6a  lea     r8, aOnecoreVmIncCo; "onecore\\vm\\inc\\CommonUtilities.h"
0x1400aef71  mov     edx, 169h; void *
0x1400aef76  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400aef7b  lea     r8, aOnecoreVmIncCo; "onecore\\vm\\inc\\CommonUtilities.h"
0x1400aef82  mov     edx, 16Dh; void *
0x1400aef87  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400aef8c  lea     r8, aOnecoreVmIncCo; "onecore\\vm\\inc\\CommonUtilities.h"
0x1400aef93  mov     edx, 16Eh; void *
0x1400aef98  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400aef9e  mov     rcx, [rsp+2D8h]; this
0x1400aefa6  mov     r9d, eax; char *
0x1400aefa9  lea     r8, aOnecoreVmIncCo; "onecore\\vm\\inc\\CommonUtilities.h"
0x1400aefb0  mov     edx, 177h; void *
0x1400aefb5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400aefba  lea     r8, aOnecoreVmIncCo; "onecore\\vm\\inc\\CommonUtilities.h"
0x1400aefc1  mov     edx, 17Eh; void *
0x1400aefc6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400aefcb  lea     r8, aOnecoreVmIncCo; "onecore\\vm\\inc\\CommonUtilities.h"
0x1400aefd2  mov     edx, 17Fh; void *
0x1400aefd7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
