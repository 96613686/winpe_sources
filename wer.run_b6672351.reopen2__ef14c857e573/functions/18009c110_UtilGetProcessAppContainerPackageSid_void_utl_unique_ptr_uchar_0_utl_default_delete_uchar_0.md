# UtilGetProcessAppContainerPackageSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x18009c110`
- end: `0x18009c26e`
- name: `?UtilGetProcessAppContainerPackageSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f9a0`
- `0x180069e50`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x18001c368`
- `0x180020680`
- `0x18004b454`
- `0x18004cc30`
- `0x18009c110`
- `0x18009c74c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c184`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c184`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009c1aa`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009c1aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c1c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c1c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilGetProcessAppContainerPackageSid(HANDLE ProcessHandle, void **a2)
{
  unsigned int TokenAppContainerPackageSid; // ebx
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
      TokenAppContainerPackageSid = UtilGetTokenAppContainerPackageSid(TokenHandle, a2);
      if ( (TokenAppContainerPackageSid & 0x80000000) == 0 )
      {
        TokenAppContainerPackageSid = 0;
      }
      else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
          TokenAppContainerPackageSid);
      }
    }
    else
    {
      LastError = GetLastError();
      TokenAppContainerPackageSid = ERROR_HR_FROM_WIN32(LastError);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
          TokenAppContainerPackageSid);
    }
  }
  else
  {
    TokenAppContainerPackageSid = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
  return TokenAppContainerPackageSid;
}

```

## disassembly

```asm
0x18009c110  mov     [rsp+arg_0], rbx
0x18009c115  push    rdi
0x18009c116  sub     rsp, 40h
0x18009c11a  mov     rdi, rdx
0x18009c11d  mov     rbx, rcx
0x18009c120  mov     [rsp+48h+TokenHandle], 0
0x18009c129  test    rdx, rdx
0x18009c12c  jnz     short loc_18009C16C
0x18009c12e  mov     ebx, 80070057h
0x18009c133  lea     rax, WPP_GLOBAL_Control
0x18009c13a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c141  cmp     rcx, rax
0x18009c144  jz      loc_18009C256
0x18009c14a  test    byte ptr [rcx+1Ch], 1
0x18009c14e  jz      loc_18009C256
0x18009c154  lea     edx, [rdi+19h]
0x18009c157  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009c15e  mov     rcx, [rcx+10h]
0x18009c162  call    WPP_SF_
0x18009c167  jmp     loc_18009C256
0x18009c16c  mov     r8, [rdx]; lpMem
0x18009c16f  mov     qword ptr [rdx], 0
0x18009c176  test    r8, r8
0x18009c179  jz      short loc_18009C190
0x18009c17b  xor     edx, edx; dwFlags
0x18009c17d  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18009c184  call    cs:__imp_HeapFree
0x18009c18b  nop     dword ptr [rax+rax+00h]
0x18009c190  lea     rdx, [rsp+48h+TokenHandle]
0x18009c195  lea     rcx, [rsp+48h+var_28]
0x18009c19a  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x18009c19f  mov     r8, rax; TokenHandle
0x18009c1a2  mov     edx, 8; DesiredAccess
0x18009c1a7  mov     rcx, rbx; ProcessHandle
0x18009c1aa  call    cs:__imp_OpenProcessToken
0x18009c1b1  nop     dword ptr [rax+rax+00h]
0x18009c1b6  mov     ebx, eax
0x18009c1b8  lea     rcx, [rsp+48h+var_28]
0x18009c1bd  call    ??1?$out_ptr_t@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAX$$V@utl@@QEAA@XZ; utl::out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>::~out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>(void)
0x18009c1c2  test    ebx, ebx
0x18009c1c4  jnz     short loc_18009C20E
0x18009c1c6  call    cs:__imp_GetLastError
0x18009c1cd  nop     dword ptr [rax+rax+00h]
0x18009c1d2  mov     ecx, eax; unsigned int
0x18009c1d4  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009c1d9  mov     ebx, eax
0x18009c1db  lea     rax, WPP_GLOBAL_Control
0x18009c1e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c1e9  cmp     rcx, rax
0x18009c1ec  jz      short loc_18009C256
0x18009c1ee  test    byte ptr [rcx+1Ch], 1
0x18009c1f2  jz      short loc_18009C256
0x18009c1f4  mov     edx, 1Ah
0x18009c1f9  mov     r9d, ebx
0x18009c1fc  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009c203  mov     rcx, [rcx+10h]
0x18009c207  call    WPP_SF_d
0x18009c20c  jmp     short loc_18009C256
0x18009c20e  mov     rdx, rdi
0x18009c211  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18009c216  call    ?UtilGetTokenAppContainerPackageSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetTokenAppContainerPackageSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x18009c21b  mov     ebx, eax
0x18009c21d  test    eax, eax
0x18009c21f  jns     short loc_18009C254
0x18009c221  lea     rax, WPP_GLOBAL_Control
0x18009c228  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c22f  cmp     rcx, rax
0x18009c232  jz      short loc_18009C256
0x18009c234  test    byte ptr [rcx+1Ch], 1
0x18009c238  jz      short loc_18009C256
0x18009c23a  mov     edx, 1Bh
0x18009c23f  mov     r9d, ebx
0x18009c242  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009c249  mov     rcx, [rcx+10h]
0x18009c24d  call    WPP_SF_d
0x18009c252  jmp     short loc_18009C256
0x18009c254  xor     ebx, ebx
0x18009c256  lea     rcx, [rsp+48h+TokenHandle]
0x18009c25b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18009c260  mov     eax, ebx
0x18009c262  mov     rbx, [rsp+48h+arg_0]
0x18009c267  add     rsp, 40h
0x18009c26b  pop     rdi
0x18009c26c  retn
```
