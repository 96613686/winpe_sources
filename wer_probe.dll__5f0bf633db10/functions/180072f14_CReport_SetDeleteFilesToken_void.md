# CReport::SetDeleteFilesToken(void *)

- ea: `0x180072f14`
- end: `0x18007307e`
- name: `?SetDeleteFilesToken@CReport@@IEAAJPEAX@Z`
- size: `362`
- prototype: `int(CReport *__hidden this, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800278f0`
- `0x1800722f0`

## callees

- `0x18000716c`
- `0x180007e34`
- `0x18001fe24`
- `0x18002bed4`
- `0x180072f14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180073018`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180073018`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180073034`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180073034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007304c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007304c`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180072fc5`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180072fc5`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180072f4f`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180072f4f`

## pseudocode

```c
__int64 __fastcall CReport::SetDeleteFilesToken(CReport *this, void *a2)
{
  char *v2; // rdi
  void **v4; // rax
  HANDLE CurrentProcess; // rbx
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  void **v12; // rax
  DWORD LastError; // eax
  void *v14; // [rsp+30h] [rbp+8h] BYREF

  v2 = (char *)this + 46616;
  v14 = 0;
  if ( *((_QWORD *)this + 5827) )
    return 0;
  if ( a2 )
  {
    v4 = (void **)tlx::replace<tlx::file_handle_traits>((char *)this + 46616);
    if ( !DuplicateToken(a2, SecurityImpersonation, v4) )
    {
      tlx::unique_any<tlx::file_handle_traits>::reset(v2, 0);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 303, &WPP_6898268820d636d20e115db2eaa75970_Traceguids, 0);
    }
    return 0;
  }
  CurrentProcess = (HANDLE)*((_QWORD *)this + 830);
  if ( !CurrentProcess )
  {
    v7 = *((_QWORD *)this + 1139);
    if ( v7 )
    {
      v8 = PssQuerySnapshot(v7, 1, &v14, 8);
      v9 = v8;
      if ( v8 )
      {
        if ( v8 > 0 )
          v9 = (unsigned __int16)v8 | 0x80070000;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return v9;
        v11 = 304;
        goto LABEL_16;
      }
      CurrentProcess = v14;
    }
    else
    {
      CurrentProcess = GetCurrentProcess();
    }
  }
  v12 = (void **)tlx::replace<tlx::file_handle_traits>(v2);
  if ( OpenProcessToken(CurrentProcess, 0xAu, v12) )
    return 0;
  tlx::unique_any<tlx::file_handle_traits>::reset(v2, 0);
  LastError = GetLastError();
  v9 = ERROR_HR_FROM_WIN32(LastError);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
    return v9;
  v11 = 305;
LABEL_16:
  WPP_SF_d(*((_QWORD *)v10 + 2), v11, &WPP_6898268820d636d20e115db2eaa75970_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180072f14  mov     [rsp+arg_8], rbx
0x180072f19  push    rdi
0x180072f1a  sub     rsp, 20h
0x180072f1e  lea     rdi, [rcx+0B618h]
0x180072f25  mov     [rsp+28h+arg_0], 0
0x180072f2e  cmp     qword ptr [rdi], 0
0x180072f32  mov     rbx, rdx
0x180072f35  jnz     short loc_180072F94
0x180072f37  test    rdx, rdx
0x180072f3a  jz      short loc_180072FA1
0x180072f3c  mov     rcx, rdi
0x180072f3f  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180072f44  mov     r8, rax; DuplicateTokenHandle
0x180072f47  mov     edx, 2; ImpersonationLevel
0x180072f4c  mov     rcx, rbx; ExistingTokenHandle
0x180072f4f  call    cs:__imp_DuplicateToken
0x180072f55  test    eax, eax
0x180072f57  jnz     short loc_180072F94
0x180072f59  xor     edx, edx
0x180072f5b  mov     rcx, rdi
0x180072f5e  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180072f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f6a  lea     rax, WPP_GLOBAL_Control
0x180072f71  cmp     rcx, rax
0x180072f74  jz      short loc_180072F94
0x180072f76  test    byte ptr [rcx+1Ch], 1
0x180072f7a  jz      short loc_180072F94
0x180072f7c  mov     rcx, [rcx+10h]
0x180072f80  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180072f87  mov     edx, 12Fh
0x180072f8c  xor     r9d, r9d
0x180072f8f  call    WPP_SF_d
0x180072f94  xor     eax, eax
0x180072f96  mov     rbx, [rsp+28h+arg_8]
0x180072f9b  add     rsp, 20h
0x180072f9f  pop     rdi
0x180072fa0  retn
0x180072fa1  mov     rbx, [rcx+19F0h]
0x180072fa8  test    rbx, rbx
0x180072fab  jnz     short loc_180073021
0x180072fad  mov     rcx, [rcx+2398h]
0x180072fb4  test    rcx, rcx
0x180072fb7  jz      short loc_180073018
0x180072fb9  lea     r9d, [rbx+8]
0x180072fbd  lea     r8, [rsp+28h+arg_0]
0x180072fc2  lea     edx, [rbx+1]
0x180072fc5  call    cs:__imp_PssQuerySnapshot
0x180072fcb  mov     ebx, eax
0x180072fcd  test    eax, eax
0x180072fcf  jz      short loc_180073011
0x180072fd1  jle     short loc_180072FDC
0x180072fd3  movzx   ebx, ax
0x180072fd6  or      ebx, 80070000h
0x180072fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180072fe3  lea     rax, WPP_GLOBAL_Control
0x180072fea  cmp     rcx, rax
0x180072fed  jz      short loc_18007300D
0x180072fef  test    byte ptr [rcx+1Ch], 1
0x180072ff3  jz      short loc_18007300D
0x180072ff5  mov     edx, 130h
0x180072ffa  mov     rcx, [rcx+10h]
0x180072ffe  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180073005  mov     r9d, ebx
0x180073008  call    WPP_SF_d
0x18007300d  mov     eax, ebx
0x18007300f  jmp     short loc_180072F96
0x180073011  mov     rbx, [rsp+28h+arg_0]
0x180073016  jmp     short loc_180073021
0x180073018  call    cs:__imp_GetCurrentProcess
0x18007301e  mov     rbx, rax
0x180073021  mov     rcx, rdi
0x180073024  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180073029  mov     r8, rax; TokenHandle
0x18007302c  mov     edx, 0Ah; DesiredAccess
0x180073031  mov     rcx, rbx; ProcessHandle
0x180073034  call    cs:__imp_OpenProcessToken
0x18007303a  test    eax, eax
0x18007303c  jnz     loc_180072F94
0x180073042  xor     edx, edx
0x180073044  mov     rcx, rdi
0x180073047  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18007304c  call    cs:__imp_GetLastError
0x180073052  mov     ecx, eax; unsigned int
0x180073054  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180073059  mov     ebx, eax
0x18007305b  mov     rcx, cs:WPP_GLOBAL_Control
0x180073062  lea     rax, WPP_GLOBAL_Control
0x180073069  cmp     rcx, rax
0x18007306c  jz      short loc_18007300D
0x18007306e  test    byte ptr [rcx+1Ch], 1
0x180073072  jz      short loc_18007300D
0x180073074  mov     edx, 131h
0x180073079  jmp     loc_180072FFA
```
