# UtilGetProcessUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x18009c598`
- end: `0x18009c6f6`
- name: `?UtilGetProcessUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18003fbf0`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x18001c368`
- `0x180020680`
- `0x18004b454`
- `0x18004cc30`
- `0x18009c598`
- `0x18009c9e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c60c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c60c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009c632`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009c632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c64e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c64e`

## pseudocode

```c
__int64 __fastcall UtilGetProcessUserSid(HANDLE ProcessHandle, void **a2)
{
  unsigned int TokenUserSid; // ebx
  void *v5; // r8
  void **v6; // rax
  BOOL v7; // ebx
  DWORD LastError; // eax
  _BYTE v10[40]; // [rsp+20h] [rbp-28h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  TokenHandle = 0;
  if ( a2 )
  {
    v5 = *a2;
    *a2 = 0;
    if ( v5 )
      HeapFree(g_hWerheap, 0, v5);
    v6 = (void **)utl::out_ptr<void,tlx::unique_any<tlx::file_handle_traits>,>(v10, &TokenHandle);
    v7 = OpenProcessToken(ProcessHandle, 8u, v6);
    utl::out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>::~out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>(v10);
    if ( v7 )
    {
      TokenUserSid = UtilGetTokenUserSid(TokenHandle, a2);
      if ( (TokenUserSid & 0x80000000) == 0 )
      {
        TokenUserSid = 0;
      }
      else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, TokenUserSid);
      }
    }
    else
    {
      LastError = GetLastError();
      TokenUserSid = ERROR_HR_FROM_WIN32(LastError);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, TokenUserSid);
    }
  }
  else
  {
    TokenUserSid = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
  return TokenUserSid;
}

```

## disassembly

```asm
0x18009c598  mov     [rsp+arg_0], rbx
0x18009c59d  push    rdi
0x18009c59e  sub     rsp, 40h
0x18009c5a2  mov     rdi, rdx
0x18009c5a5  mov     rbx, rcx
0x18009c5a8  mov     [rsp+48h+TokenHandle], 0
0x18009c5b1  test    rdx, rdx
0x18009c5b4  jnz     short loc_18009C5F4
0x18009c5b6  mov     ebx, 80070057h
0x18009c5bb  lea     rax, WPP_GLOBAL_Control
0x18009c5c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c5c9  cmp     rcx, rax
0x18009c5cc  jz      loc_18009C6DE
0x18009c5d2  test    byte ptr [rcx+1Ch], 1
0x18009c5d6  jz      loc_18009C6DE
0x18009c5dc  lea     edx, [rdi+0Fh]
0x18009c5df  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009c5e6  mov     rcx, [rcx+10h]
0x18009c5ea  call    WPP_SF_
0x18009c5ef  jmp     loc_18009C6DE
0x18009c5f4  mov     r8, [rdx]; lpMem
0x18009c5f7  mov     qword ptr [rdx], 0
0x18009c5fe  test    r8, r8
0x18009c601  jz      short loc_18009C618
0x18009c603  xor     edx, edx; dwFlags
0x18009c605  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18009c60c  call    cs:__imp_HeapFree
0x18009c613  nop     dword ptr [rax+rax+00h]
0x18009c618  lea     rdx, [rsp+48h+TokenHandle]
0x18009c61d  lea     rcx, [rsp+48h+var_28]
0x18009c622  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x18009c627  mov     r8, rax; TokenHandle
0x18009c62a  mov     edx, 8; DesiredAccess
0x18009c62f  mov     rcx, rbx; ProcessHandle
0x18009c632  call    cs:__imp_OpenProcessToken
0x18009c639  nop     dword ptr [rax+rax+00h]
0x18009c63e  mov     ebx, eax
0x18009c640  lea     rcx, [rsp+48h+var_28]
0x18009c645  call    ??1?$out_ptr_t@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAX$$V@utl@@QEAA@XZ; utl::out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>::~out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>(void)
0x18009c64a  test    ebx, ebx
0x18009c64c  jnz     short loc_18009C696
0x18009c64e  call    cs:__imp_GetLastError
0x18009c655  nop     dword ptr [rax+rax+00h]
0x18009c65a  mov     ecx, eax; unsigned int
0x18009c65c  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009c661  mov     ebx, eax
0x18009c663  lea     rax, WPP_GLOBAL_Control
0x18009c66a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c671  cmp     rcx, rax
0x18009c674  jz      short loc_18009C6DE
0x18009c676  test    byte ptr [rcx+1Ch], 1
0x18009c67a  jz      short loc_18009C6DE
0x18009c67c  mov     edx, 10h
0x18009c681  mov     r9d, ebx
0x18009c684  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009c68b  mov     rcx, [rcx+10h]
0x18009c68f  call    WPP_SF_d
0x18009c694  jmp     short loc_18009C6DE
0x18009c696  mov     rdx, rdi
0x18009c699  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18009c69e  call    ?UtilGetTokenUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetTokenUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x18009c6a3  mov     ebx, eax
0x18009c6a5  test    eax, eax
0x18009c6a7  jns     short loc_18009C6DC
0x18009c6a9  lea     rax, WPP_GLOBAL_Control
0x18009c6b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c6b7  cmp     rcx, rax
0x18009c6ba  jz      short loc_18009C6DE
0x18009c6bc  test    byte ptr [rcx+1Ch], 1
0x18009c6c0  jz      short loc_18009C6DE
0x18009c6c2  mov     edx, 11h
0x18009c6c7  mov     r9d, ebx
0x18009c6ca  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009c6d1  mov     rcx, [rcx+10h]
0x18009c6d5  call    WPP_SF_d
0x18009c6da  jmp     short loc_18009C6DE
0x18009c6dc  xor     ebx, ebx
0x18009c6de  lea     rcx, [rsp+48h+TokenHandle]
0x18009c6e3  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18009c6e8  mov     eax, ebx
0x18009c6ea  mov     rbx, [rsp+48h+arg_0]
0x18009c6ef  add     rsp, 40h
0x18009c6f3  pop     rdi
0x18009c6f4  retn
```
