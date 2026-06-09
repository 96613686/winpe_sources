# CompatibilityAdapter::ResetStatus(void)

- ea: `0x18001225c`
- end: `0x1800123ff`
- name: `?ResetStatus@CompatibilityAdapter@@QEAAJXZ`
- size: `419`
- prototype: `__int64 __fastcall(CompatibilityAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011880`

## callees

- `0x180010678`
- `0x18001225c`
- `0x180023e5c`
- `0x180025090`
- `0x18002e572`
- `0x18002e5b0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012399`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012399`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001229a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001229a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001238f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001238f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800123d4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800123d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001230b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001230b`

## pseudocode

```c
signed int __fastcall CompatibilityAdapter::ResetStatus(CompatibilityAdapter *this)
{
  CompatibilityAdapter *v1; // rcx
  HANDLE FirstFileW; // rbp
  signed int result; // eax
  int v4; // ebx
  int v5; // eax
  struct CJob *v6; // rdi
  int v7; // esi
  signed int LastError; // eax
  struct CJob *v9; // [rsp+20h] [rbp-298h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+28h] [rbp-290h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-288h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(g_ptszSearchPath, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result == 2 )
    {
      return 0;
    }
    else if ( result > 0 )
    {
      return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    v4 = 0;
    v9 = 0;
    do
    {
      v5 = CompatibilityAdapter::ActivateJob(v1, FindFileData.cFileName, &v9, 0);
      v6 = v9;
      v7 = v5;
      if ( v5 >= 0 )
      {
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        CJob::UpdateJobState(v6, 0);
        if ( *((_DWORD *)v6 + 21) == 267009 )
        {
          if ( (*((_DWORD *)v6 + 22) & 0x400000) != 0 )
            *((_DWORD *)v6 + 21) = 267012;
          *((_DWORD *)v6 + 22) |= 0x40000000u;
        }
        if ( (*((_DWORD *)v6 + 22) & 0xC000000) != 0 )
        {
          *((_DWORD *)v6 + 22) &= 0xF3FFFFFF;
          *((_DWORD *)v6 + 22) |= 0x40000000u;
        }
        if ( *((_WORD *)v6 + 33) )
        {
          *((_WORD *)v6 + 33) = 0;
          *((_DWORD *)v6 + 22) |= 0x40000000u;
        }
        if ( (*((_DWORD *)v6 + 22) & 0x40000000) != 0 || (*((_DWORD *)v6 + 22) & 0x20000000) == 0 )
        {
          *((_DWORD *)v6 + 22) |= 0x20000000u;
          v7 = CJob::SaveWithRetry(v6, 0, 0, 6u);
          if ( v7 < 0 )
            break;
        }
      }
      else
      {
        v7 = 0;
      }
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        LastError = GetLastError();
        if ( LastError == 18 )
          break;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        else
          v7 = LastError;
      }
    }
    while ( v7 >= 0 );
    if ( v6 )
      (*(void (__fastcall **)(struct CJob *))(*(_QWORD *)v6 + 16LL))(v6);
    FindClose(FirstFileW);
    if ( v7 < 0 )
      return v7;
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18001225c  push    rbx
0x18001225e  push    rbp
0x18001225f  push    rsi
0x180012260  push    rdi
0x180012261  push    r14
0x180012263  sub     rsp, 290h
0x18001226a  mov     rax, cs:__security_cookie
0x180012271  xor     rax, rsp
0x180012274  mov     [rsp+2B8h+var_38], rax
0x18001227c  xor     edx, edx; Val
0x18001227e  lea     rcx, [rsp+2B8h+FindFileData]; void *
0x180012283  mov     r8d, 250h; Size
0x180012289  call    memset_0
0x18001228e  mov     rcx, cs:?g_ptszSearchPath@@3PEAGEA; lpFileName
0x180012295  lea     rdx, [rsp+2B8h+FindFileData]; lpFindFileData
0x18001229a  call    cs:__imp_FindFirstFileW
0x1800122a0  mov     rbp, rax
0x1800122a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800122a7  jnz     short loc_1800122D0
0x1800122a9  call    cs:__imp_GetLastError
0x1800122af  cmp     eax, 2
0x1800122b2  jz      short loc_1800122C9
0x1800122b4  test    eax, eax
0x1800122b6  jle     loc_1800123E1
0x1800122bc  movzx   eax, ax
0x1800122bf  or      eax, 80070000h
0x1800122c4  jmp     loc_1800123E1
0x1800122c9  xor     eax, eax
0x1800122cb  jmp     loc_1800123E1
0x1800122d0  xor     ebx, ebx
0x1800122d2  mov     r14d, 40000000h
0x1800122d8  mov     [rsp+2B8h+var_298], rbx
0x1800122dd  xor     r9d, r9d; int
0x1800122e0  lea     r8, [rsp+2B8h+var_298]; struct CJob **
0x1800122e5  lea     rdx, [rsp+2B8h+FindFileData.cFileName]; unsigned __int16 *
0x1800122ea  call    ?ActivateJob@CompatibilityAdapter@@QEAAJPEBGPEAPEAVCJob@@H@Z; CompatibilityAdapter::ActivateJob(ushort const *,CJob * *,int)
0x1800122ef  mov     rdi, [rsp+2B8h+var_298]
0x1800122f4  mov     esi, eax
0x1800122f6  test    eax, eax
0x1800122f8  jns     short loc_180012301
0x1800122fa  mov     esi, ebx
0x1800122fc  jmp     loc_180012387
0x180012301  lea     rcx, [rsp+2B8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180012306  mov     qword ptr [rsp+2B8h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x18001230b  call    cs:__imp_GetSystemTimeAsFileTime
0x180012311  xor     edx, edx; int
0x180012313  mov     rcx, rdi; this
0x180012316  call    ?UpdateJobState@CJob@@QEAAJH@Z; CJob::UpdateJobState(int)
0x18001231b  cmp     dword ptr [rdi+54h], 41301h
0x180012322  jnz     short loc_180012338
0x180012324  test    dword ptr [rdi+58h], 400000h
0x18001232b  jz      short loc_180012334
0x18001232d  mov     dword ptr [rdi+54h], 41304h
0x180012334  or      [rdi+58h], r14d
0x180012338  test    dword ptr [rdi+58h], 0C000000h
0x18001233f  jz      short loc_18001234C
0x180012341  and     dword ptr [rdi+58h], 0F3FFFFFFh
0x180012348  or      [rdi+58h], r14d
0x18001234c  cmp     [rdi+42h], bx
0x180012350  jz      short loc_18001235A
0x180012352  mov     [rdi+42h], bx
0x180012356  or      [rdi+58h], r14d
0x18001235a  test    [rdi+58h], r14d
0x18001235e  jnz     short loc_180012369
0x180012360  test    dword ptr [rdi+58h], 20000000h
0x180012367  jnz     short loc_180012387
0x180012369  bts     dword ptr [rdi+58h], 1Dh
0x18001236e  mov     r9d, 6; unsigned int
0x180012374  xor     r8d, r8d; int
0x180012377  xor     edx, edx; lpFileName
0x180012379  mov     rcx, rdi; this
0x18001237c  call    ?SaveWithRetry@CJob@@QEAAJPEBGHK@Z; CJob::SaveWithRetry(ushort const *,int,ulong)
0x180012381  mov     esi, eax
0x180012383  test    eax, eax
0x180012385  js      short loc_1800123BD
0x180012387  lea     rdx, [rsp+2B8h+FindFileData]; lpFindFileData
0x18001238c  mov     rcx, rbp; hFindFile
0x18001238f  call    cs:__imp_FindNextFileW
0x180012395  test    eax, eax
0x180012397  jnz     short loc_1800123B5
0x180012399  call    cs:__imp_GetLastError
0x18001239f  cmp     eax, 12h
0x1800123a2  jz      short loc_1800123BD
0x1800123a4  test    eax, eax
0x1800123a6  jg      short loc_1800123AC
0x1800123a8  mov     esi, eax
0x1800123aa  jmp     short loc_1800123B5
0x1800123ac  movzx   esi, ax
0x1800123af  or      esi, 80070000h
0x1800123b5  test    esi, esi
0x1800123b7  jns     loc_1800122DD
0x1800123bd  test    rdi, rdi
0x1800123c0  jz      short loc_1800123D1
0x1800123c2  mov     rdx, [rdi]
0x1800123c5  mov     rcx, rdi
0x1800123c8  mov     rax, [rdx+10h]
0x1800123cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123d1  mov     rcx, rbp; hFindFile
0x1800123d4  call    cs:__imp_FindClose
0x1800123da  test    esi, esi
0x1800123dc  cmovs   ebx, esi
0x1800123df  mov     eax, ebx
0x1800123e1  mov     rcx, [rsp+2B8h+var_38]
0x1800123e9  xor     rcx, rsp; StackCookie
0x1800123ec  call    __security_check_cookie
0x1800123f1  add     rsp, 290h
0x1800123f8  pop     r14
0x1800123fa  pop     rdi
0x1800123fb  pop     rsi
0x1800123fc  pop     rbp
0x1800123fd  pop     rbx
0x1800123fe  retn
```
