# IO::Directory::Create(IO::Path const &,SecurityDescriptor const *)

- ea: `0x14006ba34`
- end: `0x14006bbb4`
- name: `?Create@Directory@IO@@SA?AV12@AEBVPath@2@PEBVSecurityDescriptor@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006ba34`
- `0x1400843fc`
- `0x140086198`
- `0x14009a234`

## callees

- `0x140005530`
- `0x140006338`
- `0x14000ccac`
- `0x14001c804`
- `0x140060e60`
- `0x140060f58`
- `0x14006b5ec`
- `0x14006ba34`
- `0x14006bbbc`
- `0x14007aaf4`
- `0x140081ed0`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x14006baf2`
- `KERNEL32!CreateDirectoryW` at `0x14006baf2`
- `KERNEL32!GetLastError` at `0x14006bafc`
- `KERNEL32!GetLastError` at `0x14006bafc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006ba9d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006ba9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
IO::Directory *__fastcall IO::Directory::Create(IO::Directory *a1, const WCHAR *a2, _QWORD *a3)
{
  const WCHAR *v6; // rdx
  WCHAR *v7; // rcx
  struct _SECURITY_ATTRIBUTES *p_pExceptionObject; // rdx
  const WCHAR *v9; // rcx
  signed int LastError; // eax
  signed int v11; // ebx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // r10
  __int64 pExceptionObject; // [rsp+40h] [rbp-9h] BYREF
  __int128 v17; // [rsp+48h] [rbp-1h]
  WCHAR PathName[4]; // [rsp+68h] [rbp+1Fh] BYREF
  unsigned __int64 v19; // [rsp+80h] [rbp+37h]

  if ( !IO::Directory::Exists((const struct Path *)a2) )
  {
    IO::Path::GetParent(a2, PathName);
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v6 = a2;
    else
      v6 = *(const WCHAR **)a2;
    v7 = PathName;
    if ( v19 > 7 )
      v7 = *(WCHAR **)PathName;
    if ( (unsigned int)_o__wcsicmp(v7, v6) )
    {
      IO::Directory::Create(&pExceptionObject, PathName, 0);
      std::wstring::~wstring((char **)&pExceptionObject);
    }
    if ( a3 )
    {
      pExceptionObject = 24;
      v17 = 0;
      *(_QWORD *)&v17 = *a3;
      p_pExceptionObject = (struct _SECURITY_ATTRIBUTES *)&pExceptionObject;
    }
    else
    {
      p_pExceptionObject = 0;
    }
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v9 = a2;
    else
      v9 = *(const WCHAR **)a2;
    if ( !CreateDirectoryW(v9, p_pExceptionObject) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError != 183 )
      {
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        if ( v11 < 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = std::array<unsigned short,16>::data(a2);
            v14 = std::wstring::c_str(v13);
            WPP_SF_Sd(
              *(_QWORD *)(v15 + 16),
              12,
              (unsigned int)WPP_7674bc77c88135f0ee99d8137a75c6ac_Traceguids,
              v14,
              v11);
          }
          ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v11);
          throw (ErrorCodeException *)&pExceptionObject;
        }
      }
    }
    std::wstring::~wstring((char **)PathName);
  }
  IO::Directory::Directory(a1, (const struct Path *)a2);
  return a1;
}

```

## disassembly

```asm
0x14006ba34  mov     [rsp-8+arg_10], rbx
0x14006ba39  push    rbp
0x14006ba3a  push    rsi
0x14006ba3b  push    rdi
0x14006ba3c  lea     rbp, [rsp-47h]
0x14006ba41  sub     rsp, 90h
0x14006ba48  mov     rax, cs:__security_cookie
0x14006ba4f  xor     rax, rsp
0x14006ba52  mov     [rbp+57h+var_18], rax
0x14006ba56  mov     rbx, r8
0x14006ba59  mov     rdi, rdx
0x14006ba5c  mov     rsi, rcx
0x14006ba5f  mov     [rbp+57h+var_68], rcx
0x14006ba63  mov     rcx, rdx; struct Path *
0x14006ba66  call    ?Exists@Directory@IO@@SA_NAEBVPath@2@@Z; IO::Directory::Exists(IO::Path const &)
0x14006ba6b  test    al, al
0x14006ba6d  jnz     loc_14006BB25
0x14006ba73  lea     rdx, [rbp+57h+PathName]
0x14006ba77  mov     rcx, rdi
0x14006ba7a  call    ?GetParent@Path@IO@@QEBA?AV12@XZ; IO::Path::GetParent(void)
0x14006ba7f  nop
0x14006ba80  cmp     qword ptr [rdi+18h], 7
0x14006ba85  jbe     short loc_14006BA8C
0x14006ba87  mov     rdx, [rdi]
0x14006ba8a  jmp     short loc_14006BA8F
0x14006ba8c  mov     rdx, rdi
0x14006ba8f  lea     rcx, [rbp+57h+PathName]
0x14006ba93  cmp     [rbp+57h+var_20], 7
0x14006ba98  cmova   rcx, qword ptr [rbp+57h+PathName]
0x14006ba9d  call    cs:__imp__o__wcsicmp
0x14006baa3  test    eax, eax
0x14006baa5  jz      short loc_14006BAC0
0x14006baa7  xor     r8d, r8d
0x14006baaa  lea     rdx, [rbp+57h+PathName]
0x14006baae  lea     rcx, [rbp+57h+pExceptionObject]
0x14006bab2  call    ?Create@Directory@IO@@SA?AV12@AEBVPath@2@PEBVSecurityDescriptor@@@Z; IO::Directory::Create(IO::Path const &,SecurityDescriptor const *)
0x14006bab7  lea     rcx, [rbp+57h+pExceptionObject]
0x14006babb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14006bac0  test    rbx, rbx
0x14006bac3  jz      short loc_14006BAE1
0x14006bac5  mov     [rbp+57h+pExceptionObject], 18h
0x14006bacd  xorps   xmm0, xmm0
0x14006bad0  movups  [rbp+57h+var_58], xmm0
0x14006bad4  mov     rax, [rbx]
0x14006bad7  mov     qword ptr [rbp+57h+var_58], rax
0x14006badb  lea     rdx, [rbp+57h+pExceptionObject]
0x14006badf  jmp     short loc_14006BAE3
0x14006bae1  xor     edx, edx; lpSecurityAttributes
0x14006bae3  cmp     qword ptr [rdi+18h], 7
0x14006bae8  jbe     short loc_14006BAEF
0x14006baea  mov     rcx, [rdi]
0x14006baed  jmp     short loc_14006BAF2
0x14006baef  mov     rcx, rdi; lpPathName
0x14006baf2  call    cs:__imp_CreateDirectoryW
0x14006baf8  test    eax, eax
0x14006bafa  jnz     short loc_14006BB1C
0x14006bafc  call    cs:__imp_GetLastError
0x14006bb02  mov     ebx, eax
0x14006bb04  cmp     eax, 0B7h
0x14006bb09  jz      short loc_14006BB1C
0x14006bb0b  test    eax, eax
0x14006bb0d  jle     short loc_14006BB18
0x14006bb0f  movzx   ebx, ax
0x14006bb12  or      ebx, 80070000h
0x14006bb18  test    ebx, ebx
0x14006bb1a  js      short loc_14006BB52
0x14006bb1c  lea     rcx, [rbp+57h+PathName]
0x14006bb20  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14006bb25  mov     rdx, rdi; struct Path *
0x14006bb28  mov     rcx, rsi; this
0x14006bb2b  call    ??0Directory@IO@@QEAA@AEBVPath@1@@Z; IO::Directory::Directory(IO::Path const &)
0x14006bb30  mov     rax, rsi
0x14006bb33  mov     rcx, [rbp+57h+var_18]
0x14006bb37  xor     rcx, rsp; StackCookie
0x14006bb3a  call    __security_check_cookie
0x14006bb3f  mov     rbx, [rsp+0A0h+arg_10]
0x14006bb47  add     rsp, 90h
0x14006bb4e  pop     rdi
0x14006bb4f  pop     rsi
0x14006bb50  pop     rbp
0x14006bb51  retn
0x14006bb52  lea     rax, WPP_GLOBAL_Control
0x14006bb59  mov     r10, cs:WPP_GLOBAL_Control
0x14006bb60  cmp     r10, rax
0x14006bb63  jz      short loc_14006BB98
0x14006bb65  test    byte ptr [r10+1Ch], 1
0x14006bb6a  jz      short loc_14006BB98
0x14006bb6c  mov     rcx, rdi
0x14006bb6f  call    ?data@?$array@G$0BA@@std@@QEAAPEAGXZ; std::array<ushort,16>::data(void)
0x14006bb74  mov     rcx, rax
0x14006bb77  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x14006bb7c  mov     edx, 0Ch
0x14006bb81  mov     [rsp+0A0h+var_80], ebx
0x14006bb85  mov     r9, rax
0x14006bb88  lea     r8, WPP_7674bc77c88135f0ee99d8137a75c6ac_Traceguids
0x14006bb8f  mov     rcx, [r10+10h]
0x14006bb93  call    WPP_SF_Sd
0x14006bb98  mov     edx, ebx; int
0x14006bb9a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14006bb9e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14006bba3  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14006bbaa  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14006bbae  call    _CxxThrowException_0
```
