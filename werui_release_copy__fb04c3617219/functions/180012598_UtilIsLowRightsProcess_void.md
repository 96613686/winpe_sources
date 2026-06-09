# UtilIsLowRightsProcess(void *)

- ea: `0x180012598`
- end: `0x180012608`
- name: `?UtilIsLowRightsProcess@@YAJPEAX@Z`
- size: `112`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180012d68`

## callees

- `0x180005c58`
- `0x180005ddc`
- `0x180012598`
- `0x180012610`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x1800125bf`
- `ADVAPI32!OpenProcessToken` at `0x1800125bf`
- `KERNEL32!GetLastError` at `0x1800125c9`
- `KERNEL32!GetLastError` at `0x1800125c9`

## pseudocode

```c
__int64 __fastcall UtilIsLowRightsProcess(HANDLE ProcessHandle)
{
  void **v2; // rax
  signed int LastError; // eax
  int IsLowRightsToken; // ebx
  HANDLE TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  v2 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
  if ( OpenProcessToken(ProcessHandle, 8u, v2) )
  {
    IsLowRightsToken = UtilIsLowRightsToken(TokenHandle);
  }
  else
  {
    LastError = GetLastError();
    IsLowRightsToken = LastError;
    if ( LastError > 0 )
      IsLowRightsToken = (unsigned __int16)LastError | 0x80070000;
    if ( IsLowRightsToken >= 0 )
      IsLowRightsToken = -2147467259;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
  return (unsigned int)IsLowRightsToken;
}

```

## disassembly

```asm
0x180012598  push    rbx
0x18001259a  sub     rsp, 20h
0x18001259e  mov     rbx, rcx
0x1800125a1  mov     [rsp+28h+TokenHandle], 0
0x1800125aa  lea     rcx, [rsp+28h+TokenHandle]
0x1800125af  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800125b4  mov     r8, rax; TokenHandle
0x1800125b7  mov     edx, 8; DesiredAccess
0x1800125bc  mov     rcx, rbx; ProcessHandle
0x1800125bf  call    cs:__imp_OpenProcessToken
0x1800125c5  test    eax, eax
0x1800125c7  jnz     short loc_1800125EA
0x1800125c9  call    cs:__imp_GetLastError
0x1800125cf  mov     ebx, eax
0x1800125d1  test    eax, eax
0x1800125d3  jle     short loc_1800125DE
0x1800125d5  movzx   ebx, ax
0x1800125d8  or      ebx, 80070000h
0x1800125de  test    ebx, ebx
0x1800125e0  mov     eax, 80004005h
0x1800125e5  cmovns  ebx, eax
0x1800125e8  jmp     short loc_1800125F6
0x1800125ea  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x1800125ef  call    ?UtilIsLowRightsToken@@YAJPEAX@Z; UtilIsLowRightsToken(void *)
0x1800125f4  mov     ebx, eax
0x1800125f6  lea     rcx, [rsp+28h+TokenHandle]
0x1800125fb  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180012600  mov     eax, ebx
0x180012602  add     rsp, 20h
0x180012606  pop     rbx
0x180012607  retn
```
