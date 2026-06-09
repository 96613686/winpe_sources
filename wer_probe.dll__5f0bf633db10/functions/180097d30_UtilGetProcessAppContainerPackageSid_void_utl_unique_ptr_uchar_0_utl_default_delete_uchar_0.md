# UtilGetProcessAppContainerPackageSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x180097d30`
- end: `0x180097e7b`
- name: `?UtilGetProcessAppContainerPackageSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d990`
- `0x180066d90`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x180007e10`
- `0x18001fe24`
- `0x180049310`
- `0x18004acbc`
- `0x180097d30`
- `0x180098320`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097da4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097da4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180097dc4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180097dc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097dda`

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
          &WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
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
          &WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
          TokenAppContainerPackageSid);
    }
  }
  else
  {
    TokenAppContainerPackageSid = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
  return TokenAppContainerPackageSid;
}

```

## disassembly

```asm
0x180097d30  mov     [rsp+arg_0], rbx
0x180097d35  push    rdi
0x180097d36  sub     rsp, 40h
0x180097d3a  mov     rdi, rdx
0x180097d3d  mov     rbx, rcx
0x180097d40  mov     [rsp+48h+TokenHandle], 0
0x180097d49  test    rdx, rdx
0x180097d4c  jnz     short loc_180097D8C
0x180097d4e  mov     ebx, 80070057h
0x180097d53  lea     rax, WPP_GLOBAL_Control
0x180097d5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180097d61  cmp     rcx, rax
0x180097d64  jz      loc_180097E64
0x180097d6a  test    byte ptr [rcx+1Ch], 1
0x180097d6e  jz      loc_180097E64
0x180097d74  lea     edx, [rdi+19h]
0x180097d77  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180097d7e  mov     rcx, [rcx+10h]
0x180097d82  call    WPP_SF_
0x180097d87  jmp     loc_180097E64
0x180097d8c  mov     r8, [rdx]; lpMem
0x180097d8f  mov     qword ptr [rdx], 0
0x180097d96  test    r8, r8
0x180097d99  jz      short loc_180097DAA
0x180097d9b  xor     edx, edx; dwFlags
0x180097d9d  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180097da4  call    cs:__imp_HeapFree
0x180097daa  lea     rdx, [rsp+48h+TokenHandle]
0x180097daf  lea     rcx, [rsp+48h+var_28]
0x180097db4  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x180097db9  mov     r8, rax; TokenHandle
0x180097dbc  mov     edx, 8; DesiredAccess
0x180097dc1  mov     rcx, rbx; ProcessHandle
0x180097dc4  call    cs:__imp_OpenProcessToken
0x180097dca  mov     ebx, eax
0x180097dcc  lea     rcx, [rsp+48h+var_28]
0x180097dd1  call    ??1?$out_ptr_t@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAX$$V@utl@@QEAA@XZ; utl::out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>::~out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>(void)
0x180097dd6  test    ebx, ebx
0x180097dd8  jnz     short loc_180097E1C
0x180097dda  call    cs:__imp_GetLastError
0x180097de0  mov     ecx, eax; unsigned int
0x180097de2  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180097de7  mov     ebx, eax
0x180097de9  lea     rax, WPP_GLOBAL_Control
0x180097df0  mov     rcx, cs:WPP_GLOBAL_Control
0x180097df7  cmp     rcx, rax
0x180097dfa  jz      short loc_180097E64
0x180097dfc  test    byte ptr [rcx+1Ch], 1
0x180097e00  jz      short loc_180097E64
0x180097e02  mov     edx, 1Ah
0x180097e07  mov     r9d, ebx
0x180097e0a  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180097e11  mov     rcx, [rcx+10h]
0x180097e15  call    WPP_SF_d
0x180097e1a  jmp     short loc_180097E64
0x180097e1c  mov     rdx, rdi
0x180097e1f  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180097e24  call    ?UtilGetTokenAppContainerPackageSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetTokenAppContainerPackageSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x180097e29  mov     ebx, eax
0x180097e2b  test    eax, eax
0x180097e2d  jns     short loc_180097E62
0x180097e2f  lea     rax, WPP_GLOBAL_Control
0x180097e36  mov     rcx, cs:WPP_GLOBAL_Control
0x180097e3d  cmp     rcx, rax
0x180097e40  jz      short loc_180097E64
0x180097e42  test    byte ptr [rcx+1Ch], 1
0x180097e46  jz      short loc_180097E64
0x180097e48  mov     edx, 1Bh
0x180097e4d  mov     r9d, ebx
0x180097e50  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180097e57  mov     rcx, [rcx+10h]
0x180097e5b  call    WPP_SF_d
0x180097e60  jmp     short loc_180097E64
0x180097e62  xor     ebx, ebx
0x180097e64  lea     rcx, [rsp+48h+TokenHandle]
0x180097e69  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180097e6e  mov     eax, ebx
0x180097e70  mov     rbx, [rsp+48h+arg_0]
0x180097e75  add     rsp, 40h
0x180097e79  pop     rdi
0x180097e7a  retn
```
