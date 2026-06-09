# CompatibilityAdapter::ResetStatus(void)

- ea: `0x180012d8c`
- end: `0x180012f54`
- name: `?ResetStatus@CompatibilityAdapter@@QEAAJXZ`
- size: `456`
- prototype: `__int64 __fastcall(CompatibilityAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180012360`

## callees

- `0x180011080`
- `0x180012d8c`
- `0x1800254fc`
- `0x1800267fc`
- `0x1800306c2`
- `0x180030700`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ee1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180012dca`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180012dca`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180012ed1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180012ed1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180012f22`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180012f22`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012e47`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012e47`

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
  signed int v7; // esi
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
0x180012d8c  push    rbx
0x180012d8e  push    rbp
0x180012d8f  push    rsi
0x180012d90  push    rdi
0x180012d91  push    r14
0x180012d93  sub     rsp, 290h
0x180012d9a  mov     rax, cs:__security_cookie
0x180012da1  xor     rax, rsp
0x180012da4  mov     [rsp+2B8h+var_38], rax
0x180012dac  xor     edx, edx; Val
0x180012dae  lea     rcx, [rsp+2B8h+FindFileData]; void *
0x180012db3  mov     r8d, 250h; Size
0x180012db9  call    memset_0
0x180012dbe  mov     rcx, cs:?g_ptszSearchPath@@3PEAGEA; lpFileName
0x180012dc5  lea     rdx, [rsp+2B8h+FindFileData]; lpFindFileData
0x180012dca  call    cs:__imp_FindFirstFileW
0x180012dd1  nop     dword ptr [rax+rax+00h]
0x180012dd6  mov     rbp, rax
0x180012dd9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012ddd  jnz     short loc_180012E0C
0x180012ddf  call    cs:__imp_GetLastError
0x180012de6  nop     dword ptr [rax+rax+00h]
0x180012deb  cmp     eax, 2
0x180012dee  jz      short loc_180012E05
0x180012df0  test    eax, eax
0x180012df2  jle     loc_180012F35
0x180012df8  movzx   eax, ax
0x180012dfb  or      eax, 80070000h
0x180012e00  jmp     loc_180012F35
0x180012e05  xor     eax, eax
0x180012e07  jmp     loc_180012F35
0x180012e0c  xor     ebx, ebx
0x180012e0e  mov     r14d, 40000000h
0x180012e14  mov     [rsp+2B8h+var_298], rbx
0x180012e19  xor     r9d, r9d; int
0x180012e1c  lea     r8, [rsp+2B8h+var_298]; struct CJob **
0x180012e21  lea     rdx, [rsp+2B8h+FindFileData.cFileName]; unsigned __int16 *
0x180012e26  call    ?ActivateJob@CompatibilityAdapter@@QEAAJPEBGPEAPEAVCJob@@H@Z; CompatibilityAdapter::ActivateJob(ushort const *,CJob * *,int)
0x180012e2b  mov     rdi, [rsp+2B8h+var_298]
0x180012e30  mov     esi, eax
0x180012e32  test    eax, eax
0x180012e34  jns     short loc_180012E3D
0x180012e36  mov     esi, ebx
0x180012e38  jmp     loc_180012EC9
0x180012e3d  lea     rcx, [rsp+2B8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180012e42  mov     qword ptr [rsp+2B8h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180012e47  call    cs:__imp_GetSystemTimeAsFileTime
0x180012e4e  nop     dword ptr [rax+rax+00h]
0x180012e53  xor     edx, edx; int
0x180012e55  mov     rcx, rdi; this
0x180012e58  call    ?UpdateJobState@CJob@@QEAAJH@Z; CJob::UpdateJobState(int)
0x180012e5d  cmp     dword ptr [rdi+54h], 41301h
0x180012e64  jnz     short loc_180012E7A
0x180012e66  test    dword ptr [rdi+58h], 400000h
0x180012e6d  jz      short loc_180012E76
0x180012e6f  mov     dword ptr [rdi+54h], 41304h
0x180012e76  or      [rdi+58h], r14d
0x180012e7a  test    dword ptr [rdi+58h], 0C000000h
0x180012e81  jz      short loc_180012E8E
0x180012e83  and     dword ptr [rdi+58h], 0F3FFFFFFh
0x180012e8a  or      [rdi+58h], r14d
0x180012e8e  cmp     [rdi+42h], bx
0x180012e92  jz      short loc_180012E9C
0x180012e94  mov     [rdi+42h], bx
0x180012e98  or      [rdi+58h], r14d
0x180012e9c  test    [rdi+58h], r14d
0x180012ea0  jnz     short loc_180012EAB
0x180012ea2  test    dword ptr [rdi+58h], 20000000h
0x180012ea9  jnz     short loc_180012EC9
0x180012eab  bts     dword ptr [rdi+58h], 1Dh
0x180012eb0  mov     r9d, 6; unsigned int
0x180012eb6  xor     r8d, r8d; int
0x180012eb9  xor     edx, edx; lpFileName
0x180012ebb  mov     rcx, rdi; this
0x180012ebe  call    ?SaveWithRetry@CJob@@QEAAJPEBGHK@Z; CJob::SaveWithRetry(ushort const *,int,ulong)
0x180012ec3  mov     esi, eax
0x180012ec5  test    eax, eax
0x180012ec7  js      short loc_180012F0B
0x180012ec9  lea     rdx, [rsp+2B8h+FindFileData]; lpFindFileData
0x180012ece  mov     rcx, rbp; hFindFile
0x180012ed1  call    cs:__imp_FindNextFileW
0x180012ed8  nop     dword ptr [rax+rax+00h]
0x180012edd  test    eax, eax
0x180012edf  jnz     short loc_180012F03
0x180012ee1  call    cs:__imp_GetLastError
0x180012ee8  nop     dword ptr [rax+rax+00h]
0x180012eed  cmp     eax, 12h
0x180012ef0  jz      short loc_180012F0B
0x180012ef2  test    eax, eax
0x180012ef4  jg      short loc_180012EFA
0x180012ef6  mov     esi, eax
0x180012ef8  jmp     short loc_180012F03
0x180012efa  movzx   esi, ax
0x180012efd  or      esi, 80070000h
0x180012f03  test    esi, esi
0x180012f05  jns     loc_180012E19
0x180012f0b  test    rdi, rdi
0x180012f0e  jz      short loc_180012F1F
0x180012f10  mov     rdx, [rdi]
0x180012f13  mov     rcx, rdi
0x180012f16  mov     rax, [rdx+10h]
0x180012f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f1f  mov     rcx, rbp; hFindFile
0x180012f22  call    cs:__imp_FindClose
0x180012f29  nop     dword ptr [rax+rax+00h]
0x180012f2e  test    esi, esi
0x180012f30  cmovs   ebx, esi
0x180012f33  mov     eax, ebx
0x180012f35  mov     rcx, [rsp+2B8h+var_38]
0x180012f3d  xor     rcx, rsp; StackCookie
0x180012f40  call    __security_check_cookie
0x180012f45  add     rsp, 290h
0x180012f4c  pop     r14
0x180012f4e  pop     rdi
0x180012f4f  pop     rsi
0x180012f50  pop     rbp
0x180012f51  pop     rbx
0x180012f52  retn
```
