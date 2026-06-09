# StackLockFileWin32Writer::PreOpen(std::filesystem::path const &)

- ea: `0x18000bdc0`
- end: `0x18000bef0`
- name: `?PreOpen@StackLockFileWin32Writer@@UEAA_NAEBVpath@filesystem@std@@@Z`
- size: `304`
- prototype: `bool __fastcall(StackLockFileWin32Writer *this, const struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015af8`

## callees

- `0x180005450`
- `0x180006424`
- `0x18000bdc0`
- `0x18002564c`
- `0x1800427d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be8c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000be69`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000be69`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000be0b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000be0b`

## string_xrefs

- `0x18000be1e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall StackLockFileWin32Writer::PreOpen(
        StackLockFileWin32Writer *this,
        const struct std::filesystem::path *a2)
{
  int LastErrorFailHr; // edi
  const char *v5; // r9
  int LastError; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  HANDLE FileW; // rax
  wil::details *v10; // rcx
  void *v11; // rsi
  HANDLE v12; // rbp
  DWORD v13; // ebx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-48h]
  int v16; // [rsp+40h] [rbp-28h] BYREF
  DWORD v17; // [rsp+44h] [rbp-24h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  LastErrorFailHr = 0;
  v16 = 0;
  v17 = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &v16, 4u, &v17) )
  {
    if ( v16 )
      return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x298,
                  (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wi"
                                "l\\token_helpers.h",
                  v5);
    if ( LastError < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, v7, v8, (const char *)(unsigned int)LastError, dwCreationDisposition);
  }
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const struct std::filesystem::path **)a2;
  FileW = CreateFileW((LPCWSTR)a2, 0xC0000000, 0, 0, 4u, 0x80u, 0);
  v11 = (void *)*((_QWORD *)this + 1);
  v12 = FileW;
  if ( v11 != (void *)-1LL && v11 )
  {
    v13 = GetLastError();
    CloseHandle(v11);
    SetLastError(v13);
  }
  *((_QWORD *)this + 1) = v12;
  if ( (((unsigned __int64)v12 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v10);
  return LastErrorFailHr >= 0;
}

```

## disassembly

```asm
0x18000bdc0  mov     r11, rsp
0x18000bdc3  mov     [r11+18h], rbx
0x18000bdc7  mov     [r11+20h], rbp
0x18000bdcb  push    rsi
0x18000bdcc  push    rdi
0x18000bdcd  push    r14
0x18000bdcf  sub     rsp, 50h
0x18000bdd3  mov     rax, cs:__security_cookie
0x18000bdda  xor     rax, rsp
0x18000bddd  mov     [rsp+68h+var_20], rax
0x18000bde2  xor     edi, edi
0x18000bde4  lea     rax, [r11-24h]
0x18000bde8  mov     rbx, rdx
0x18000bdeb  mov     [rsp+68h+var_28], edi
0x18000bdef  mov     r14, rcx
0x18000bdf2  mov     [rsp+68h+var_24], edi
0x18000bdf6  lea     r8, [r11-28h]; TokenInformation
0x18000bdfa  mov     [r11-48h], rax
0x18000bdfe  lea     esi, [rdi+4]
0x18000be01  mov     r9d, esi; TokenInformationLength
0x18000be04  lea     edx, [rdi+1Dh]; TokenInformationClass
0x18000be07  lea     rcx, [rdi-6]; TokenHandle
0x18000be0b  call    cs:__imp_GetTokenInformation
0x18000be11  test    eax, eax
0x18000be13  jnz     loc_18000BEDD
0x18000be19  mov     rcx, [rsp+68h]; this
0x18000be1e  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000be25  mov     edx, 298h; void *
0x18000be2a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000be2f  test    eax, eax
0x18000be31  jns     short loc_18000BE40
0x18000be33  mov     rcx, [rsp+68h]; this
0x18000be38  mov     r9d, eax; char *
0x18000be3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000be40  cmp     qword ptr [rbx+18h], 7
0x18000be45  jbe     short loc_18000BE4A
0x18000be47  mov     rbx, [rbx]
0x18000be4a  mov     [rsp+68h+hTemplateFile], rdi; hTemplateFile
0x18000be4f  xor     r9d, r9d; lpSecurityAttributes
0x18000be52  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000be5a  xor     r8d, r8d; dwShareMode
0x18000be5d  mov     edx, 0C0000000h; dwDesiredAccess
0x18000be62  mov     [rsp+68h+dwCreationDisposition], esi; dwCreationDisposition
0x18000be66  mov     rcx, rbx; lpFileName
0x18000be69  call    cs:__imp_CreateFileW
0x18000be6f  mov     rsi, [r14+8]
0x18000be73  mov     rbp, rax
0x18000be76  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000be7a  jz      short loc_18000BE9A
0x18000be7c  test    rsi, rsi
0x18000be7f  jz      short loc_18000BE9A
0x18000be81  call    cs:__imp_GetLastError
0x18000be87  mov     rcx, rsi; hObject
0x18000be8a  mov     ebx, eax
0x18000be8c  call    cs:__imp_CloseHandle
0x18000be92  mov     ecx, ebx; dwErrCode
0x18000be94  call    cs:__imp_SetLastError
0x18000be9a  lea     rax, [rbp+1]
0x18000be9e  mov     [r14+8], rbp
0x18000bea2  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000bea8  jnz     short loc_18000BEB1
0x18000beaa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000beaf  mov     edi, eax
0x18000beb1  shr     edi, 1Fh
0x18000beb4  xor     dil, 1
0x18000beb8  mov     al, dil
0x18000bebb  mov     rcx, [rsp+68h+var_20]
0x18000bec0  xor     rcx, rsp; StackCookie
0x18000bec3  call    __security_check_cookie
0x18000bec8  lea     r11, [rsp+68h+var_18]
0x18000becd  mov     rbx, [r11+30h]
0x18000bed1  mov     rbp, [r11+38h]
0x18000bed5  mov     rsp, r11
0x18000bed8  pop     r14
0x18000beda  pop     rdi
0x18000bedb  pop     rsi
0x18000bedc  retn
0x18000bedd  cmp     [rsp+68h+var_28], edi
0x18000bee1  setnz   al
0x18000bee4  test    al, al
0x18000bee6  jz      loc_18000BE40
0x18000beec  xor     al, al
0x18000beee  jmp     short loc_18000BEBB
```
