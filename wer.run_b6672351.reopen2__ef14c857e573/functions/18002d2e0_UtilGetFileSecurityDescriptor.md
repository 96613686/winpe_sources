# UtilGetFileSecurityDescriptor

- ea: `0x18002d2e0`
- end: `0x18002d44c`
- name: `UtilGetFileSecurityDescriptor`
- size: `364`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009ba70`

## callees

- `0x180004c64`
- `0x18001c368`
- `0x18002d2e0`
- `0x18002e94c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d31c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d3c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d42c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d31c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d3c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d42c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d39e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d39e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d37f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d37f`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002d348`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002d348`

## pseudocode

```c
__int64 __fastcall UtilGetFileSecurityDescriptor(LPCWSTR lpFileName, DWORD a2, void **a3)
{
  void *v3; // rbx
  void *v5; // r8
  int v6; // edi
  int v7; // ebp
  DWORD LastError; // eax
  LPVOID v10; // rax
  void *v11; // r8
  LPVOID v12; // rsi
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
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
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
0x18002d2e0  mov     rax, rsp
0x18002d2e3  mov     [rax+8], rbx
0x18002d2e7  mov     [rax+10h], edx
0x18002d2ea  push    rbp
0x18002d2eb  push    rsi
0x18002d2ec  push    rdi
0x18002d2ed  push    r14
0x18002d2ef  push    r15
0x18002d2f1  sub     rsp, 30h
0x18002d2f5  xor     ebx, ebx
0x18002d2f7  mov     r14, r8
0x18002d2fa  mov     r8, [r8]; lpMem
0x18002d2fd  xor     edi, edi
0x18002d2ff  xor     ebp, ebp
0x18002d301  mov     [rax+10h], edi
0x18002d304  mov     [rax+18h], rbx
0x18002d308  mov     r15, rcx
0x18002d30b  mov     [r14], rbx
0x18002d30e  test    r8, r8
0x18002d311  jz      short loc_18002D328
0x18002d313  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002d31a  xor     edx, edx; dwFlags
0x18002d31c  call    cs:__imp_HeapFree
0x18002d323  nop     dword ptr [rax+rax+00h]
0x18002d328  test    ebp, ebp
0x18002d32a  jnz     loc_18002D41B
0x18002d330  mov     r9d, [rsp+58h+nLengthNeeded]; nLength
0x18002d335  lea     rax, [rsp+58h+nLengthNeeded]
0x18002d33a  mov     r8, rbx; pSecurityDescriptor
0x18002d33d  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18002d342  lea     edx, [rbp+10h]; RequestedInformation
0x18002d345  mov     rcx, r15; lpFileName
0x18002d348  call    cs:__imp_GetFileSecurityW
0x18002d34f  nop     dword ptr [rax+rax+00h]
0x18002d354  test    eax, eax
0x18002d356  jz      short loc_18002D37F
0x18002d358  cmp     [rsp+58h+nLengthNeeded], ebp
0x18002d35c  jnz     short loc_18002D363
0x18002d35e  lea     edi, [rbp+1]
0x18002d361  jmp     short loc_18002D375
0x18002d363  lea     rdx, [rsp+58h+arg_10]
0x18002d368  mov     rcx, r14
0x18002d36b  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x18002d370  mov     rbx, [rsp+58h+arg_10]
0x18002d375  mov     ebp, 1
0x18002d37a  jmp     loc_18002D413
0x18002d37f  call    cs:__imp_GetLastError
0x18002d386  nop     dword ptr [rax+rax+00h]
0x18002d38b  cmp     eax, 7Ah ; 'z'
0x18002d38e  jnz     short loc_18002D40A
0x18002d390  mov     r8d, [rsp+58h+nLengthNeeded]; dwBytes
0x18002d395  xor     edx, edx; dwFlags
0x18002d397  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002d39e  call    cs:__imp_HeapAlloc
0x18002d3a5  nop     dword ptr [rax+rax+00h]
0x18002d3aa  mov     r8, rbx; lpMem
0x18002d3ad  mov     [rsp+58h+arg_10], rax
0x18002d3b2  mov     rsi, rax
0x18002d3b5  mov     rbx, rax
0x18002d3b8  test    r8, r8
0x18002d3bb  jz      short loc_18002D3D2
0x18002d3bd  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002d3c4  xor     edx, edx; dwFlags
0x18002d3c6  call    cs:__imp_HeapFree
0x18002d3cd  nop     dword ptr [rax+rax+00h]
0x18002d3d2  test    rsi, rsi
0x18002d3d5  jnz     short loc_18002D413
0x18002d3d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3de  lea     rax, WPP_GLOBAL_Control
0x18002d3e5  cmp     rcx, rax
0x18002d3e8  jz      short loc_18002D403
0x18002d3ea  test    byte ptr [rcx+1Ch], 1
0x18002d3ee  jz      short loc_18002D403
0x18002d3f0  mov     rcx, [rcx+10h]
0x18002d3f4  lea     edx, [rsi+13h]
0x18002d3f7  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18002d3fe  call    WPP_SF_
0x18002d403  mov     edi, 8007000Eh
0x18002d408  jmp     short loc_18002D413
0x18002d40a  mov     ecx, eax; unsigned int
0x18002d40c  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18002d411  mov     edi, eax
0x18002d413  test    edi, edi
0x18002d415  jns     loc_18002D328
0x18002d41b  test    rbx, rbx
0x18002d41e  jz      short loc_18002D438
0x18002d420  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002d427  mov     r8, rbx; lpMem
0x18002d42a  xor     edx, edx; dwFlags
0x18002d42c  call    cs:__imp_HeapFree
0x18002d433  nop     dword ptr [rax+rax+00h]
0x18002d438  mov     rbx, [rsp+58h+arg_0]
0x18002d43d  mov     eax, edi
0x18002d43f  add     rsp, 30h
0x18002d443  pop     r15
0x18002d445  pop     r14
0x18002d447  pop     rdi
0x18002d448  pop     rsi
0x18002d449  pop     rbp
0x18002d44a  retn
```
