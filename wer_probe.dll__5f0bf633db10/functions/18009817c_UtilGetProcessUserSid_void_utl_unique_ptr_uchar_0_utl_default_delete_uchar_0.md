# UtilGetProcessUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x18009817c`
- end: `0x1800982c7`
- name: `?UtilGetProcessUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18003dbd0`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x180007e10`
- `0x18001fe24`
- `0x180049310`
- `0x18004acbc`
- `0x18009817c`
- `0x180098594`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800981f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800981f0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180098210`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180098210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098226`

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
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
          TokenUserSid);
      }
    }
    else
    {
      LastError = GetLastError();
      TokenUserSid = ERROR_HR_FROM_WIN32(LastError);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
          TokenUserSid);
    }
  }
  else
  {
    TokenUserSid = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
  return TokenUserSid;
}

```

## disassembly

```asm
0x18009817c  mov     [rsp+arg_0], rbx
0x180098181  push    rdi
0x180098182  sub     rsp, 40h
0x180098186  mov     rdi, rdx
0x180098189  mov     rbx, rcx
0x18009818c  mov     [rsp+48h+TokenHandle], 0
0x180098195  test    rdx, rdx
0x180098198  jnz     short loc_1800981D8
0x18009819a  mov     ebx, 80070057h
0x18009819f  lea     rax, WPP_GLOBAL_Control
0x1800981a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800981ad  cmp     rcx, rax
0x1800981b0  jz      loc_1800982B0
0x1800981b6  test    byte ptr [rcx+1Ch], 1
0x1800981ba  jz      loc_1800982B0
0x1800981c0  lea     edx, [rdi+0Fh]
0x1800981c3  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800981ca  mov     rcx, [rcx+10h]
0x1800981ce  call    WPP_SF_
0x1800981d3  jmp     loc_1800982B0
0x1800981d8  mov     r8, [rdx]; lpMem
0x1800981db  mov     qword ptr [rdx], 0
0x1800981e2  test    r8, r8
0x1800981e5  jz      short loc_1800981F6
0x1800981e7  xor     edx, edx; dwFlags
0x1800981e9  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800981f0  call    cs:__imp_HeapFree
0x1800981f6  lea     rdx, [rsp+48h+TokenHandle]
0x1800981fb  lea     rcx, [rsp+48h+var_28]
0x180098200  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x180098205  mov     r8, rax; TokenHandle
0x180098208  mov     edx, 8; DesiredAccess
0x18009820d  mov     rcx, rbx; ProcessHandle
0x180098210  call    cs:__imp_OpenProcessToken
0x180098216  mov     ebx, eax
0x180098218  lea     rcx, [rsp+48h+var_28]
0x18009821d  call    ??1?$out_ptr_t@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAX$$V@utl@@QEAA@XZ; utl::out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>::~out_ptr_t<tlx::unique_any<tlx::file_handle_traits>,void *,>(void)
0x180098222  test    ebx, ebx
0x180098224  jnz     short loc_180098268
0x180098226  call    cs:__imp_GetLastError
0x18009822c  mov     ecx, eax; unsigned int
0x18009822e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180098233  mov     ebx, eax
0x180098235  lea     rax, WPP_GLOBAL_Control
0x18009823c  mov     rcx, cs:WPP_GLOBAL_Control
0x180098243  cmp     rcx, rax
0x180098246  jz      short loc_1800982B0
0x180098248  test    byte ptr [rcx+1Ch], 1
0x18009824c  jz      short loc_1800982B0
0x18009824e  mov     edx, 10h
0x180098253  mov     r9d, ebx
0x180098256  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009825d  mov     rcx, [rcx+10h]
0x180098261  call    WPP_SF_d
0x180098266  jmp     short loc_1800982B0
0x180098268  mov     rdx, rdi
0x18009826b  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180098270  call    ?UtilGetTokenUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetTokenUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x180098275  mov     ebx, eax
0x180098277  test    eax, eax
0x180098279  jns     short loc_1800982AE
0x18009827b  lea     rax, WPP_GLOBAL_Control
0x180098282  mov     rcx, cs:WPP_GLOBAL_Control
0x180098289  cmp     rcx, rax
0x18009828c  jz      short loc_1800982B0
0x18009828e  test    byte ptr [rcx+1Ch], 1
0x180098292  jz      short loc_1800982B0
0x180098294  mov     edx, 11h
0x180098299  mov     r9d, ebx
0x18009829c  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800982a3  mov     rcx, [rcx+10h]
0x1800982a7  call    WPP_SF_d
0x1800982ac  jmp     short loc_1800982B0
0x1800982ae  xor     ebx, ebx
0x1800982b0  lea     rcx, [rsp+48h+TokenHandle]
0x1800982b5  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800982ba  mov     eax, ebx
0x1800982bc  mov     rbx, [rsp+48h+arg_0]
0x1800982c1  add     rsp, 40h
0x1800982c5  pop     rdi
0x1800982c6  retn
```
