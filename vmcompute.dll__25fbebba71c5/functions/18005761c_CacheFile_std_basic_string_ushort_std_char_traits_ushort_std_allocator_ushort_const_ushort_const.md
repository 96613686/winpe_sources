# CacheFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *)

- ea: `0x18005761c`
- end: `0x1800577e3`
- name: `?CacheFile@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800577f0`

## callees

- `0x180002f50`
- `0x18005761c`
- `0x180058190`
- `0x1800581f0`
- `0x180058248`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800577bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800577bc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180057668`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180057668`
- `ntdll!NtSetCachedSigningLevel2` at `0x180057714`
- `ntdll!NtSetCachedSigningLevel2` at `0x180057714`

## string_xrefs

- `0x18005768d`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180057777`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x1800577a6`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`

## pseudocode

```c
__int64 __fastcall CacheFile(__int64 *a1, const WCHAR *a2)
{
  char *FileW; // rbx
  unsigned int LastErrorMsg; // edi
  bool v6; // cc
  __int64 *v7; // rcx
  __int16 v8; // ax
  int v9; // eax
  __int64 v10; // rdx
  char *v12; // [rsp+50h] [rbp+7h] BYREF
  __int64 v13; // [rsp+58h] [rbp+Fh] BYREF
  __int128 v14; // [rsp+60h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  FileW = (char *)CreateFileW(a2, 1u, 5u, 0, 3u, 0x80u, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v6 = (unsigned __int64)a1[3] <= 7;
    v14 = 0;
    v12 = FileW;
    v13 = 24;
    if ( v6 )
      v7 = a1;
    else
      v7 = (__int64 *)*a1;
    v8 = 2 * *((_WORD *)a1 + 8);
    *((_QWORD *)&v14 + 1) = v7;
    LOWORD(v14) = v8;
    WORD1(v14) = v8;
    DWORD1(v14) = 0;
    v9 = NtSetCachedSigningLevel2(4, 0, &v12, 1, FileW, &v13);
    if ( (v9 & 0xFFF0000) == 0xE90000 )
    {
      v10 = 201;
LABEL_16:
      wil::details::in1diag3::Log_NtStatusMsg(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
        (const char *)(unsigned int)v9,
        (int)"%ls",
        (const char *)a2);
      goto LABEL_17;
    }
    if ( v9 != -1073741701 && v9 != -1073741279 )
    {
      if ( v9 == -1073740760 )
        goto LABEL_17;
      if ( ((v9 + 1073740285) & 0xFFFFFFFD) != 0 )
      {
        if ( v9 <= -1 )
        {
          LastErrorMsg = wil::details::in1diag3::Return_NtStatusMsg(
                           retaddr,
                           (void *)0xDB,
                           (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
                           (const char *)(unsigned int)v9,
                           (int)"%ls",
                           (const char *)a2);
LABEL_18:
          CloseHandle(FileW);
          return LastErrorMsg;
        }
LABEL_17:
        LastErrorMsg = 0;
        goto LABEL_18;
      }
    }
    v10 = 215;
    goto LABEL_16;
  }
  LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                   retaddr,
                   (void *)0xB5,
                   (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
                   "%ls",
                   (const char *)a2);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_18;
  return LastErrorMsg;
}

```

## disassembly

```asm
0x18005761c  push    rbp
0x18005761e  push    rbx
0x18005761f  push    rsi
0x180057620  push    rdi
0x180057621  lea     rbp, [rsp-3Fh]
0x180057626  sub     rsp, 88h
0x18005762d  mov     rax, cs:__security_cookie
0x180057634  xor     rax, rsp
0x180057637  mov     [rbp+57h+var_30], rax
0x18005763b  xor     r9d, r9d; lpSecurityAttributes
0x18005763e  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x180057647  mov     rsi, rdx
0x18005764a  mov     [rsp+0A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180057652  mov     rdi, rcx
0x180057655  mov     [rsp+0A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18005765d  mov     rcx, rsi; lpFileName
0x180057660  lea     edx, [r9+1]; dwDesiredAccess
0x180057664  lea     r8d, [r9+5]; dwShareMode
0x180057668  call    cs:__imp_CreateFileW
0x18005766f  nop     dword ptr [rax+rax+00h]
0x180057674  mov     rbx, rax
0x180057677  inc     rax
0x18005767a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180057680  jnz     short loc_1800576B8
0x180057682  mov     rcx, [rbp+5Fh]; this
0x180057686  lea     r9, aLs; "%ls"
0x18005768d  lea     r8, aOnecoreVmCompu_17; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180057694  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rsi; char *
0x180057699  mov     edx, 0B5h; void *
0x18005769e  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800576a3  lea     rcx, [rbx-1]
0x1800576a7  mov     edi, eax
0x1800576a9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800576ad  ja      loc_1800577C8
0x1800576b3  jmp     loc_1800577B9
0x1800576b8  cmp     qword ptr [rdi+18h], 7
0x1800576bd  xorps   xmm0, xmm0
0x1800576c0  movups  [rbp+57h+var_40], xmm0
0x1800576c4  mov     [rbp+57h+var_50], rbx
0x1800576c8  mov     [rbp+57h+var_48], 18h
0x1800576d0  jbe     short loc_1800576D7
0x1800576d2  mov     rcx, [rdi]
0x1800576d5  jmp     short loc_1800576DA
0x1800576d7  mov     rcx, rdi
0x1800576da  movzx   eax, word ptr [rdi+10h]
0x1800576de  lea     r8, [rbp+57h+var_50]
0x1800576e2  add     ax, ax
0x1800576e5  mov     qword ptr [rbp+57h+var_40+8], rcx
0x1800576e9  mov     word ptr [rbp+57h+var_40], ax
0x1800576ed  xor     edx, edx
0x1800576ef  mov     word ptr [rbp+57h+var_40+2], ax
0x1800576f3  mov     r9d, 1
0x1800576f9  movups  [rbp+57h+var_60], xmm0
0x1800576fd  mov     eax, dword ptr [rbp+57h+var_60+4]
0x180057700  mov     dword ptr [rbp+57h+var_40+4], eax
0x180057703  lea     ecx, [rdx+4]
0x180057706  lea     rax, [rbp+57h+var_48]
0x18005770a  mov     qword ptr [rsp+0A0h+dwFlagsAndAttributes], rax
0x18005770f  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rbx
0x180057714  call    cs:__imp_NtSetCachedSigningLevel2
0x18005771b  nop     dword ptr [rax+rax+00h]
0x180057720  mov     ecx, eax
0x180057722  mov     r9d, eax; char *
0x180057725  and     ecx, 0FFF0000h
0x18005772b  cmp     ecx, 0E90000h
0x180057731  jnz     short loc_18005773A
0x180057733  mov     edx, 0C9h
0x180057738  jmp     short loc_180057796
0x18005773a  cmp     r9d, 0C000007Bh
0x180057741  jz      short loc_180057791
0x180057743  cmp     r9d, 0C0000221h
0x18005774a  jz      short loc_180057791
0x18005774c  cmp     r9d, 0C0000428h
0x180057753  jz      short loc_1800577B7
0x180057755  add     eax, 3FFFF9FDh
0x18005775a  test    eax, 0FFFFFFFDh
0x18005775f  jz      short loc_180057791
0x180057761  cmp     r9d, 0FFFFFFFFh
0x180057765  jg      short loc_1800577B7
0x180057767  mov     rcx, [rbp+5Fh]; this
0x18005776b  lea     rax, aLs; "%ls"
0x180057772  mov     qword ptr [rsp+0A0h+dwFlagsAndAttributes], rsi; char *
0x180057777  lea     r8, aOnecoreVmCompu_17; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18005777e  mov     edx, 0DBh; void *
0x180057783  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax; int
0x180057788  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18005778d  mov     edi, eax
0x18005778f  jmp     short loc_1800577B9
0x180057791  mov     edx, 0D7h; void *
0x180057796  mov     rcx, [rbp+5Fh]; this
0x18005779a  lea     rax, aLs; "%ls"
0x1800577a1  mov     qword ptr [rsp+0A0h+dwFlagsAndAttributes], rsi; char *
0x1800577a6  lea     r8, aOnecoreVmCompu_17; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x1800577ad  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax; int
0x1800577b2  call    ?Log_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1800577b7  xor     edi, edi
0x1800577b9  mov     rcx, rbx; hObject
0x1800577bc  call    cs:__imp_CloseHandle
0x1800577c3  nop     dword ptr [rax+rax+00h]
0x1800577c8  mov     eax, edi
0x1800577ca  mov     rcx, [rbp+57h+var_30]
0x1800577ce  xor     rcx, rsp; StackCookie
0x1800577d1  call    __security_check_cookie
0x1800577d6  add     rsp, 88h
0x1800577dd  pop     rdi
0x1800577de  pop     rsi
0x1800577df  pop     rbx
0x1800577e0  pop     rbp
0x1800577e1  retn
```
