# WdsGetTempDir

- ea: `0x18000d1c0`
- end: `0x18000d346`
- name: `WdsGetTempDir`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x180002250`
- `0x180008d30`
- `0x180008e78`
- `0x180009e30`
- `0x18000a288`
- `0x18000bca4`
- `0x18000d1c0`
- `0x18001dc70`
- `0x1800274de`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d281`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d281`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000d267`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000d267`

## string_xrefs

- `0x18000d200`: `WdsGetTempDir`
- `0x18000d29c`: `Module Temp Directory %s is not useable`

## pseudocode

```c
__int64 __fastcall WdsGetTempDir(__int64 a1, unsigned __int16 *a2, _DWORD *a3)
{
  __int64 result; // rax
  BOOL v7; // esi
  unsigned __int64 v8; // rdi
  DWORD LastError; // ebx
  int v10; // eax
  __int64 v11; // rcx
  WCHAR PathName[264]; // [rsp+60h] [rbp-258h] BYREF
  LPCWSTR lpModuleName; // [rsp+2B8h] [rbp+0h]

  memset_0(PathName, 0, 0x208u);
  result = IsWorkQueueAccessible(L"WdsGetTempDir");
  if ( (_DWORD)result )
  {
    v7 = 0;
    v8 = (unsigned int)*a3;
    *a3 = 0;
    if ( !g_WorkingDir || g_TempDir || (unsigned int)pCreateCleanTempDir() )
    {
      if ( (unsigned int)ConstructPathName(&g_TempDir, (STRSAFE_LPCWSTR)(a1 + 44), PathName) )
      {
        CreateDirectoryW(PathName, 0);
        if ( IsDirectoryUseable(PathName) )
        {
          v7 = StringCchCopyW(a2, v8, PathName) >= 0;
          v11 = -1;
          do
            ++v11;
          while ( PathName[v11] );
          *a3 = v11 + 1;
        }
        else
        {
          LastError = GetLastError();
          v10 = (unsigned int)ConstructPartialMsgW(
                                0x3000039u,
                                "Module Temp Directory %s is not useable",
                                (const char *)PathName);
          WdsSetupLogMessageW(
            v10,
            589824,
            (int)L"D",
            0,
            2358,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            (__int64)L"WdsGetTempDir",
            lpModuleName,
            LastError,
            0,
            0);
        }
      }
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18000d1c0  push    rbx
0x18000d1c2  push    rsi
0x18000d1c3  push    rdi
0x18000d1c4  push    r12
0x18000d1c6  push    r13
0x18000d1c8  push    r14
0x18000d1ca  push    r15
0x18000d1cc  sub     rsp, 280h
0x18000d1d3  mov     rax, cs:__security_cookie
0x18000d1da  xor     rax, rsp
0x18000d1dd  mov     [rsp+2B8h+var_48], rax
0x18000d1e5  mov     rbx, r8
0x18000d1e8  mov     r15, rdx
0x18000d1eb  mov     r14, rcx
0x18000d1ee  xor     edx, edx; Val
0x18000d1f0  mov     r8d, 208h; Size
0x18000d1f6  lea     rcx, [rsp+2B8h+PathName]; void *
0x18000d1fb  call    memset_0
0x18000d200  lea     r13, aWdsgettempdir_0; "WdsGetTempDir"
0x18000d207  mov     rcx, r13
0x18000d20a  call    IsWorkQueueAccessible
0x18000d20f  xor     r12d, r12d
0x18000d212  test    eax, eax
0x18000d214  jz      loc_18000D322
0x18000d21a  mov     esi, r12d
0x18000d21d  mov     edi, [rbx]
0x18000d21f  mov     [rbx], r12d
0x18000d222  cmp     cs:?g_WorkingDir@@3PAGA, r12w; ushort near * g_WorkingDir
0x18000d22a  jz      short loc_18000D243
0x18000d22c  cmp     cs:?g_TempDir@@3PAGA, r12w; ushort near * g_TempDir
0x18000d234  jnz     short loc_18000D243
0x18000d236  call    ?pCreateCleanTempDir@@YAHXZ; pCreateCleanTempDir(void)
0x18000d23b  test    eax, eax
0x18000d23d  jz      loc_18000D320
0x18000d243  lea     rdx, [r14+2Ch]; STRSAFE_LPCWSTR
0x18000d247  lea     r8, [rsp+2B8h+PathName]; unsigned __int16 *
0x18000d24c  lea     rcx, ?g_TempDir@@3PAGA; pszSrc
0x18000d253  call    ConstructPathName
0x18000d258  test    eax, eax
0x18000d25a  jz      loc_18000D320
0x18000d260  xor     edx, edx; lpSecurityAttributes
0x18000d262  lea     rcx, [rsp+2B8h+PathName]; lpPathName
0x18000d267  call    cs:__imp_CreateDirectoryW
0x18000d26e  nop     dword ptr [rax+rax+00h]
0x18000d273  lea     rcx, [rsp+2B8h+PathName]
0x18000d278  call    IsDirectoryUseable
0x18000d27d  test    eax, eax
0x18000d27f  jnz     short loc_18000D2F2
0x18000d281  call    cs:__imp_GetLastError
0x18000d288  nop     dword ptr [rax+rax+00h]
0x18000d28d  mov     ebx, eax
0x18000d28f  mov     rdi, [rsp+2B8h]
0x18000d297  lea     r8, [rsp+2B8h+PathName]
0x18000d29c  lea     rdx, aModuleTempDire; "Module Temp Directory %s is not useable"
0x18000d2a3  mov     ecx, 3000039h; unsigned int
0x18000d2a8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d2ad  mov     [rsp+2B8h+var_268], r12d; int
0x18000d2b2  mov     [rsp+2B8h+var_270], r12; __int64
0x18000d2b7  mov     [rsp+2B8h+var_278], ebx; int
0x18000d2bb  mov     [rsp+2B8h+lpModuleName], rdi; lpModuleName
0x18000d2c0  mov     [rsp+2B8h+var_288], r13; __int64
0x18000d2c5  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000d2cc  mov     [rsp+2B8h+var_290], rcx; unsigned __int16 *
0x18000d2d1  mov     [rsp+2B8h+var_298], 936h; int
0x18000d2d9  xor     r9d, r9d; int
0x18000d2dc  lea     r8, aD_1; "D"
0x18000d2e3  mov     edx, 90000h; int
0x18000d2e8  mov     rcx, rax; int
0x18000d2eb  call    WdsSetupLogMessageW
0x18000d2f0  jmp     short loc_18000D320
0x18000d2f2  mov     rdx, rdi; unsigned __int64
0x18000d2f5  lea     r8, [rsp+2B8h+PathName]; unsigned __int16 *
0x18000d2fa  mov     rcx, r15; unsigned __int16 *
0x18000d2fd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d302  mov     esi, eax
0x18000d304  not     esi
0x18000d306  shr     esi, 1Fh
0x18000d309  lea     rax, [rsp+2B8h+PathName]
0x18000d30e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d312  inc     rcx
0x18000d315  cmp     [rax+rcx*2], r12w
0x18000d31a  jnz     short loc_18000D312
0x18000d31c  inc     ecx
0x18000d31e  mov     [rbx], ecx
0x18000d320  mov     eax, esi
0x18000d322  mov     rcx, [rsp+2B8h+var_48]
0x18000d32a  xor     rcx, rsp; StackCookie
0x18000d32d  call    __security_check_cookie
0x18000d332  add     rsp, 280h
0x18000d339  pop     r15
0x18000d33b  pop     r14
0x18000d33d  pop     r13
0x18000d33f  pop     r12
0x18000d341  pop     rdi
0x18000d342  pop     rsi
0x18000d343  pop     rbx
0x18000d344  retn
0x180027ab6  push    rbp
0x180027ab8  sub     rsp, 60h
0x180027abc  mov     rbp, rdx
0x180027abf  add     rsp, 60h
0x180027ac3  pop     rbp
0x180027ac4  retn
```
