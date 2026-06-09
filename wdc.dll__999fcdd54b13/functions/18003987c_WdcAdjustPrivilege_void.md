# WdcAdjustPrivilege(void)

- ea: `0x18003987c`
- end: `0x1800399d1`
- name: `?WdcAdjustPrivilege@@YAJXZ`
- size: `341`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002415c`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18003987c`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x1800398c2`
- `ADVAPI32!OpenProcessToken` at `0x1800398c2`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180039946`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180039946`
- `KERNEL32!CloseHandle` at `0x1800399a8`
- `KERNEL32!CloseHandle` at `0x1800399a8`
- `KERNEL32!GetLastError` at `0x1800398cc`
- `KERNEL32!GetLastError` at `0x180039954`
- `KERNEL32!GetLastError` at `0x1800398cc`
- `KERNEL32!GetLastError` at `0x180039954`
- `KERNEL32!GetCurrentProcess` at `0x1800398af`
- `KERNEL32!GetCurrentProcess` at `0x1800398af`

## string_xrefs

- `0x180039986`: `WdcAdjustPrivilege`

## pseudocode

```c
__int64 __fastcall WdcAdjustPrivilege(__int64 a1, const char *a2, int a3)
{
  struct _TOKEN_PRIVILEGES *v3; // rdi
  signed int v4; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  __int64 *v7; // r8
  unsigned int v8; // edx
  __int64 v9; // rax
  __int64 v10; // rcx
  const char *v11; // rdx
  int v12; // r8d
  signed int v13; // eax
  PTOKEN_PRIVILEGES PreviousState; // [rsp+20h] [rbp-18h]
  void *TokenHandle; // [rsp+40h] [rbp+8h] BYREF

  TokenHandle = 0;
  v3 = (struct _TOKEN_PRIVILEGES *)WdcAlloc(0x3Cu, a2, a3);
  if ( !v3 )
  {
    v4 = -2147024882;
    LODWORD(PreviousState) = -2147024882;
LABEL_19:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\control.cpp",
      "WdcAdjustPrivilege",
      0,
      L"FAILURE: 0x%08x",
      PreviousState);
    goto LABEL_20;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( !LastError )
    {
LABEL_17:
      v4 = -2147467259;
LABEL_18:
      LODWORD(PreviousState) = v4;
      goto LABEL_19;
    }
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_18;
  }
  v3->PrivilegeCount = 3;
  v7 = qword_18009A070;
  v8 = 0;
  do
  {
    v9 = (int)v8++;
    v10 = v9;
    v3->Privileges[v10].Attributes = 2;
    LODWORD(v9) = *(_DWORD *)v7;
    v7 = (__int64 *)((char *)v7 + 4);
    v3->Privileges[v10].Luid = (LUID)(unsigned int)v9;
  }
  while ( v8 < 3 );
  if ( AdjustTokenPrivileges(TokenHandle, 0, v3, 0, 0, 0) )
  {
    v4 = 0;
    goto LABEL_20;
  }
  v13 = GetLastError();
  v4 = v13;
  if ( !v13 )
    goto LABEL_17;
  if ( v13 > 0 )
    v4 = (unsigned __int16)v13 | 0x80070000;
  if ( v4 < 0 )
    goto LABEL_18;
LABEL_20:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v3 )
    WdcFree(v3, v11, v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003987c  mov     [rsp+arg_8], rbx
0x180039881  push    rdi
0x180039882  sub     rsp, 30h
0x180039886  mov     ecx, 3Ch ; '<'; dwBytes
0x18003988b  mov     [rsp+38h+TokenHandle], 0
0x180039894  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180039899  mov     rdi, rax
0x18003989c  test    rax, rax
0x18003989f  jnz     short loc_1800398AF
0x1800398a1  mov     ebx, 8007000Eh
0x1800398a6  mov     dword ptr [rsp+38h+PreviousState], ebx
0x1800398aa  jmp     loc_18003997C
0x1800398af  call    cs:__imp_GetCurrentProcess
0x1800398b5  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800398ba  mov     edx, 20h ; ' '; DesiredAccess
0x1800398bf  mov     rcx, rax; ProcessHandle
0x1800398c2  call    cs:__imp_OpenProcessToken
0x1800398c8  test    eax, eax
0x1800398ca  jnz     short loc_1800398EF
0x1800398cc  call    cs:__imp_GetLastError
0x1800398d2  mov     ebx, eax
0x1800398d4  test    eax, eax
0x1800398d6  jz      loc_180039971
0x1800398dc  jle     short loc_1800398E7
0x1800398de  movzx   ebx, ax
0x1800398e1  or      ebx, 80070000h
0x1800398e7  test    ebx, ebx
0x1800398e9  js      loc_180039976
0x1800398ef  mov     dword ptr [rdi], 3
0x1800398f5  lea     r8, qword_18009A070
0x1800398fc  xor     edx, edx
0x1800398fe  movsxd  rax, edx
0x180039901  inc     edx
0x180039903  lea     rcx, [rax+rax*2]
0x180039907  mov     dword ptr [rdi+rcx*4+0Ch], 2
0x18003990f  mov     eax, [r8]
0x180039912  lea     r8, [r8+4]
0x180039916  mov     [rdi+rcx*4+4], eax
0x18003991a  mov     dword ptr [rdi+rcx*4+8], 0
0x180039922  cmp     edx, 3
0x180039925  jb      short loc_1800398FE
0x180039927  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18003992c  xor     r9d, r9d; BufferLength
0x18003992f  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x180039938  mov     r8, rdi; NewState
0x18003993b  xor     edx, edx; DisableAllPrivileges
0x18003993d  mov     [rsp+38h+PreviousState], 0; PreviousState
0x180039946  call    cs:__imp_AdjustTokenPrivileges
0x18003994c  test    eax, eax
0x18003994e  jz      short loc_180039954
0x180039950  xor     ebx, ebx
0x180039952  jmp     short loc_180039999
0x180039954  call    cs:__imp_GetLastError
0x18003995a  mov     ebx, eax
0x18003995c  test    eax, eax
0x18003995e  jz      short loc_180039971
0x180039960  jle     short loc_18003996B
0x180039962  movzx   ebx, ax
0x180039965  or      ebx, 80070000h
0x18003996b  test    ebx, ebx
0x18003996d  jns     short loc_180039999
0x18003996f  jmp     short loc_180039976
0x180039971  mov     ebx, 80004005h
0x180039976  mov     eax, ebx
0x180039978  mov     dword ptr [rsp+38h+PreviousState], ebx
0x18003997c  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180039983  xor     r8d, r8d; int
0x180039986  lea     rdx, aWdcadjustprivi; "WdcAdjustPrivilege"
0x18003998d  lea     rcx, aBaseDiagnosisP_37; "base\\diagnosis\\pdui\\perfmon\\mon\\co"...
0x180039994  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180039999  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18003999e  lea     rax, [rcx-1]
0x1800399a2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800399a6  ja      short loc_1800399B7
0x1800399a8  call    cs:__imp_CloseHandle
0x1800399ae  mov     [rsp+38h+TokenHandle], 0
0x1800399b7  test    rdi, rdi
0x1800399ba  jz      short loc_1800399C4
0x1800399bc  mov     rcx, rdi; void *
0x1800399bf  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x1800399c4  mov     eax, ebx
0x1800399c6  mov     rbx, [rsp+38h+arg_8]
0x1800399cb  add     rsp, 30h
0x1800399cf  pop     rdi
0x1800399d0  retn
```
