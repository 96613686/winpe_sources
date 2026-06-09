# UtilSetFileSecurity(wchar_t const *,ulong,void *)

- ea: `0x18002a5f8`
- end: `0x18002a74f`
- name: `?UtilSetFileSecurity@@YAJPEB_WKPEAX@Z`
- size: `343`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d718`

## callees

- `0x180018000`
- `0x18001c368`
- `0x18002a5f8`
- `0x18002a758`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a72d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a72d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a632`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a632`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18002a6c9`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18002a6c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilSetFileSecurity(WCHAR *a1, __int64 a2, void *a3)
{
  HANDLE FileW; // rax
  void *v6; // rdi
  unsigned __int64 v7; // r14
  DWORD v8; // eax
  int v9; // ebx
  wchar_t *v10; // rcx
  int v11; // edx
  DWORD LastError; // eax

  FileW = CreateFileW(a1, 0x60000u, 3u, 0, 3u, 0x2200080u, 0);
  v6 = FileW;
  v7 = (unsigned __int64)FileW + 1;
  if ( (unsigned __int64)FileW + 1 > 1 )
  {
    v9 = UtilVerifyFilePath(a1, FileW);
    if ( v9 >= 0 )
    {
      if ( !SetKernelObjectSecurity(v6, 4u, a3) )
      {
        LastError = GetLastError();
        v9 = ERROR_HR_FROM_WIN32(LastError);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v11 = 16;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v11 = 15;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v8 = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(v8);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 14;
LABEL_13:
      WPP_SF_SD(
        *((_QWORD *)v10 + 2),
        v11,
        (unsigned int)WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
        (_DWORD)a1,
        v9);
    }
  }
  if ( v7 > 1 )
    CloseHandle(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002a5f8  mov     rax, rsp
0x18002a5fb  mov     [rax+8], rbx
0x18002a5ff  mov     [rax+10h], rbp
0x18002a603  push    rsi
0x18002a604  push    rdi
0x18002a605  push    r14
0x18002a607  sub     rsp, 40h
0x18002a60b  mov     rbp, r8
0x18002a60e  mov     rsi, rcx
0x18002a611  mov     qword ptr [rax-28h], 0
0x18002a619  mov     dword ptr [rax-30h], 2200080h
0x18002a620  mov     r8d, 3; dwShareMode
0x18002a626  mov     [rax-38h], r8d
0x18002a62a  xor     r9d, r9d; lpSecurityAttributes
0x18002a62d  mov     edx, 60000h; dwDesiredAccess
0x18002a632  call    cs:__imp_CreateFileW
0x18002a639  nop     dword ptr [rax+rax+00h]
0x18002a63e  mov     rdi, rax
0x18002a641  mov     [rsp+58h+arg_18], rax
0x18002a646  lea     r14, [rax+1]
0x18002a64a  cmp     r14, 1
0x18002a64e  ja      short loc_18002A68D
0x18002a650  call    cs:__imp_GetLastError
0x18002a657  nop     dword ptr [rax+rax+00h]
0x18002a65c  mov     ecx, eax; unsigned int
0x18002a65e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18002a663  mov     ebx, eax
0x18002a665  lea     rax, WPP_GLOBAL_Control
0x18002a66c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a673  cmp     rcx, rax
0x18002a676  jz      loc_18002A724
0x18002a67c  test    byte ptr [rcx+1Ch], 1
0x18002a680  jz      loc_18002A724
0x18002a686  mov     edx, 0Eh
0x18002a68b  jmp     short loc_18002A70C
0x18002a68d  mov     rdx, rdi; void *
0x18002a690  mov     rcx, rsi; wchar_t *
0x18002a693  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x18002a698  mov     ebx, eax
0x18002a69a  test    eax, eax
0x18002a69c  jns     short loc_18002A6BE
0x18002a69e  lea     rax, WPP_GLOBAL_Control
0x18002a6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6ac  cmp     rcx, rax
0x18002a6af  jz      short loc_18002A724
0x18002a6b1  test    byte ptr [rcx+1Ch], 1
0x18002a6b5  jz      short loc_18002A724
0x18002a6b7  mov     edx, 0Fh
0x18002a6bc  jmp     short loc_18002A70C
0x18002a6be  mov     r8, rbp; SecurityDescriptor
0x18002a6c1  mov     edx, 4; SecurityInformation
0x18002a6c6  mov     rcx, rdi; Handle
0x18002a6c9  call    cs:__imp_SetKernelObjectSecurity
0x18002a6d0  nop     dword ptr [rax+rax+00h]
0x18002a6d5  test    eax, eax
0x18002a6d7  jnz     short loc_18002A724
0x18002a6d9  call    cs:__imp_GetLastError
0x18002a6e0  nop     dword ptr [rax+rax+00h]
0x18002a6e5  mov     ecx, eax; unsigned int
0x18002a6e7  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18002a6ec  mov     ebx, eax
0x18002a6ee  lea     rax, WPP_GLOBAL_Control
0x18002a6f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6fc  cmp     rcx, rax
0x18002a6ff  jz      short loc_18002A724
0x18002a701  test    byte ptr [rcx+1Ch], 1
0x18002a705  jz      short loc_18002A724
0x18002a707  mov     edx, 10h
0x18002a70c  mov     [rsp+58h+var_38], ebx
0x18002a710  mov     r9, rsi
0x18002a713  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18002a71a  mov     rcx, [rcx+10h]
0x18002a71e  call    WPP_SF_SD
0x18002a723  nop
0x18002a724  cmp     r14, 1
0x18002a728  jbe     short loc_18002A739
0x18002a72a  mov     rcx, rdi; hObject
0x18002a72d  call    cs:__imp_CloseHandle
0x18002a734  nop     dword ptr [rax+rax+00h]
0x18002a739  mov     eax, ebx
0x18002a73b  mov     rbx, [rsp+58h+arg_0]
0x18002a740  mov     rbp, [rsp+58h+arg_8]
0x18002a745  add     rsp, 40h
0x18002a749  pop     r14
0x18002a74b  pop     rdi
0x18002a74c  pop     rsi
0x18002a74d  retn
```
