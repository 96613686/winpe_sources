# UtilGetFileSecurityDescriptor

- ea: `0x18002b8b4`
- end: `0x18002b9fb`
- name: `UtilGetFileSecurityDescriptor`
- size: `327`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800976cc`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18002b8b4`
- `0x18002cdd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b8f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b982`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b9e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b8f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b982`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b9e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b960`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b947`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002b916`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002b916`

## pseudocode

```c
__int64 __fastcall UtilGetFileSecurityDescriptor(LPCWSTR lpFileName, DWORD a2, void **a3)
{
  void *v3; // rbx
  void *v5; // r8
  int v6; // edi
  int v7; // ebp
  DWORD LastError; // eax
  void *v10; // rax
  void *v11; // r8
  void *v12; // rsi
  DWORD nLengthNeeded; // [rsp+68h] [rbp+10h] BYREF
  void *v15; // [rsp+70h] [rbp+18h] BYREF

  nLengthNeeded = a2;
  v3 = 0;
  v5 = *a3;
  v6 = 0;
  v7 = 0;
  nLengthNeeded = 0;
  v15 = 0;
  *a3 = 0;
  if ( v5 )
    HeapFree(g_hWerheap, 0, v5);
  do
  {
    if ( v7 )
      break;
    if ( GetFileSecurityW(lpFileName, 0x10u, v3, nLengthNeeded, &nLengthNeeded) )
    {
      if ( nLengthNeeded )
      {
        utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
          a3,
          &v15);
        v3 = v15;
      }
      else
      {
        v6 = 1;
      }
      v7 = 1;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError == 122 )
      {
        v10 = HeapAlloc(g_hWerheap, 0, nLengthNeeded);
        v11 = v3;
        v15 = v10;
        v12 = v10;
        v3 = v10;
        if ( v11 )
          HeapFree(g_hWerheap, 0, v11);
        if ( !v12 )
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
          v6 = -2147024882;
        }
      }
      else
      {
        v6 = ERROR_HR_FROM_WIN32(LastError);
      }
    }
  }
  while ( v6 >= 0 );
  if ( v3 )
    HeapFree(g_hWerheap, 0, v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002b8b4  mov     rax, rsp
0x18002b8b7  mov     [rax+8], rbx
0x18002b8bb  mov     [rax+10h], edx
0x18002b8be  push    rbp
0x18002b8bf  push    rsi
0x18002b8c0  push    rdi
0x18002b8c1  push    r14
0x18002b8c3  push    r15
0x18002b8c5  sub     rsp, 30h
0x18002b8c9  xor     ebx, ebx
0x18002b8cb  mov     r14, r8
0x18002b8ce  mov     r8, [r8]; lpMem
0x18002b8d1  xor     edi, edi
0x18002b8d3  xor     ebp, ebp
0x18002b8d5  mov     [rax+10h], edi
0x18002b8d8  mov     [rax+18h], rbx
0x18002b8dc  mov     r15, rcx
0x18002b8df  mov     [r14], rbx
0x18002b8e2  test    r8, r8
0x18002b8e5  jz      short loc_18002B8F6
0x18002b8e7  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002b8ee  xor     edx, edx; dwFlags
0x18002b8f0  call    cs:__imp_HeapFree
0x18002b8f6  test    ebp, ebp
0x18002b8f8  jnz     loc_18002B9D1
0x18002b8fe  mov     r9d, [rsp+58h+nLengthNeeded]; nLength
0x18002b903  lea     rax, [rsp+58h+nLengthNeeded]
0x18002b908  mov     r8, rbx; pSecurityDescriptor
0x18002b90b  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18002b910  lea     edx, [rbp+10h]; RequestedInformation
0x18002b913  mov     rcx, r15; lpFileName
0x18002b916  call    cs:__imp_GetFileSecurityW
0x18002b91c  test    eax, eax
0x18002b91e  jz      short loc_18002B947
0x18002b920  cmp     [rsp+58h+nLengthNeeded], ebp
0x18002b924  jnz     short loc_18002B92B
0x18002b926  lea     edi, [rbp+1]
0x18002b929  jmp     short loc_18002B93D
0x18002b92b  lea     rdx, [rsp+58h+arg_10]
0x18002b930  mov     rcx, r14
0x18002b933  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x18002b938  mov     rbx, [rsp+58h+arg_10]
0x18002b93d  mov     ebp, 1
0x18002b942  jmp     loc_18002B9C9
0x18002b947  call    cs:__imp_GetLastError
0x18002b94d  cmp     eax, 7Ah ; 'z'
0x18002b950  jnz     short loc_18002B9C0
0x18002b952  mov     r8d, [rsp+58h+nLengthNeeded]; dwBytes
0x18002b957  xor     edx, edx; dwFlags
0x18002b959  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002b960  call    cs:__imp_HeapAlloc
0x18002b966  mov     r8, rbx; lpMem
0x18002b969  mov     [rsp+58h+arg_10], rax
0x18002b96e  mov     rsi, rax
0x18002b971  mov     rbx, rax
0x18002b974  test    r8, r8
0x18002b977  jz      short loc_18002B988
0x18002b979  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002b980  xor     edx, edx; dwFlags
0x18002b982  call    cs:__imp_HeapFree
0x18002b988  test    rsi, rsi
0x18002b98b  jnz     short loc_18002B9C9
0x18002b98d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b994  lea     rax, WPP_GLOBAL_Control
0x18002b99b  cmp     rcx, rax
0x18002b99e  jz      short loc_18002B9B9
0x18002b9a0  test    byte ptr [rcx+1Ch], 1
0x18002b9a4  jz      short loc_18002B9B9
0x18002b9a6  mov     rcx, [rcx+10h]
0x18002b9aa  lea     edx, [rsi+13h]
0x18002b9ad  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18002b9b4  call    WPP_SF_
0x18002b9b9  mov     edi, 8007000Eh
0x18002b9be  jmp     short loc_18002B9C9
0x18002b9c0  mov     ecx, eax; unsigned int
0x18002b9c2  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18002b9c7  mov     edi, eax
0x18002b9c9  test    edi, edi
0x18002b9cb  jns     loc_18002B8F6
0x18002b9d1  test    rbx, rbx
0x18002b9d4  jz      short loc_18002B9E8
0x18002b9d6  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002b9dd  mov     r8, rbx; lpMem
0x18002b9e0  xor     edx, edx; dwFlags
0x18002b9e2  call    cs:__imp_HeapFree
0x18002b9e8  mov     rbx, [rsp+58h+arg_0]
0x18002b9ed  mov     eax, edi
0x18002b9ef  add     rsp, 30h
0x18002b9f3  pop     r15
0x18002b9f5  pop     r14
0x18002b9f7  pop     rdi
0x18002b9f8  pop     rsi
0x18002b9f9  pop     rbp
0x18002b9fa  retn
```
