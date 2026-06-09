# Storage::CVolumeInfo::_GetMountPoints(ushort const *,ushort * *,ulong *)

- ea: `0x180018c24`
- end: `0x180018d1f`
- name: `?_GetMountPoints@CVolumeInfo@Storage@@CAJPEBGPEAPEAGPEAK@Z`
- size: `251`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180027d80`

## callees

- `0x180018c24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018c8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018cd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018c8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018cd9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018ce7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018ce7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018c9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018c9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cc7`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180018c63`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180018cbd`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180018c63`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180018cbd`

## pseudocode

```c
__int64 __fastcall Storage::CVolumeInfo::_GetMountPoints(
        LPCWSTR lpszVolumeName,
        unsigned __int16 **a2,
        unsigned int *a3)
{
  unsigned int v6; // ebx
  int v7; // edi
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v10; // rax
  unsigned __int16 *v11; // rbx
  DWORD LastError; // eax
  int v13; // ecx
  HANDLE v14; // rax
  DWORD v15; // eax
  DWORD cchReturnLength; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  *a3 = 0;
  cchReturnLength = 0;
  v6 = -2147467259;
  if ( !GetVolumePathNamesForVolumeNameW(lpszVolumeName, 0, 0, &cchReturnLength) && GetLastError() == 234 )
  {
    v7 = 1;
    do
    {
      v8 = 2LL * cchReturnLength;
      ProcessHeap = GetProcessHeap();
      v10 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v8);
      v11 = v10;
      if ( v10 )
      {
        if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v10, cchReturnLength, &cchReturnLength) )
        {
          v15 = cchReturnLength;
          *a2 = v11;
          v6 = 0;
          *a3 = v15;
          return v6;
        }
        LastError = GetLastError();
        v13 = 0;
        if ( LastError == 234 )
          v13 = v7;
        v7 = v13;
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v11);
        v6 = -2147467259;
      }
      else
      {
        v6 = -2147024882;
      }
    }
    while ( v7 );
  }
  return v6;
}

```

## disassembly

```asm
0x180018c24  mov     rax, rsp
0x180018c27  mov     [rax+8], rbx
0x180018c2b  mov     [rax+18h], rbp
0x180018c2f  push    rsi
0x180018c30  push    rdi
0x180018c31  push    r14
0x180018c33  sub     rsp, 20h
0x180018c37  mov     qword ptr [rdx], 0
0x180018c3e  lea     r9, [rax+10h]; lpcchReturnLength
0x180018c42  mov     dword ptr [r8], 0
0x180018c49  mov     rsi, r8
0x180018c4c  mov     r14, rdx
0x180018c4f  mov     dword ptr [rax+10h], 0
0x180018c56  xor     r8d, r8d; cchBufferLength
0x180018c59  xor     edx, edx; lpszVolumePathNames
0x180018c5b  mov     rbp, rcx
0x180018c5e  mov     ebx, 80004005h
0x180018c63  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180018c69  test    eax, eax
0x180018c6b  jnz     loc_180018D0A
0x180018c71  call    cs:__imp_GetLastError
0x180018c77  cmp     eax, 0EAh
0x180018c7c  jnz     loc_180018D0A
0x180018c82  mov     edi, 1
0x180018c87  mov     ebx, [rsp+38h+cchReturnLength]
0x180018c8b  add     rbx, rbx
0x180018c8e  call    cs:__imp_GetProcessHeap
0x180018c94  mov     r8, rbx; dwBytes
0x180018c97  mov     edx, 8; dwFlags
0x180018c9c  mov     rcx, rax; hHeap
0x180018c9f  call    cs:__imp_HeapAlloc
0x180018ca5  mov     rbx, rax
0x180018ca8  test    rax, rax
0x180018cab  jz      short loc_180018CF4
0x180018cad  mov     r8d, [rsp+38h+cchReturnLength]; cchBufferLength
0x180018cb2  lea     r9, [rsp+38h+cchReturnLength]; lpcchReturnLength
0x180018cb7  mov     rdx, rax; lpszVolumePathNames
0x180018cba  mov     rcx, rbp; lpszVolumeName
0x180018cbd  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180018cc3  test    eax, eax
0x180018cc5  jnz     short loc_180018CFF
0x180018cc7  call    cs:__imp_GetLastError
0x180018ccd  xor     ecx, ecx
0x180018ccf  cmp     eax, 0EAh
0x180018cd4  cmovz   ecx, edi
0x180018cd7  mov     edi, ecx
0x180018cd9  call    cs:__imp_GetProcessHeap
0x180018cdf  mov     r8, rbx; lpMem
0x180018ce2  xor     edx, edx; dwFlags
0x180018ce4  mov     rcx, rax; hHeap
0x180018ce7  call    cs:__imp_HeapFree
0x180018ced  mov     ebx, 80004005h
0x180018cf2  jmp     short loc_180018CF9
0x180018cf4  mov     ebx, 8007000Eh
0x180018cf9  test    edi, edi
0x180018cfb  jnz     short loc_180018C87
0x180018cfd  jmp     short loc_180018D0A
0x180018cff  mov     eax, [rsp+38h+cchReturnLength]
0x180018d03  mov     [r14], rbx
0x180018d06  xor     ebx, ebx
0x180018d08  mov     [rsi], eax
0x180018d0a  mov     rbp, [rsp+38h+arg_10]
0x180018d0f  mov     eax, ebx
0x180018d11  mov     rbx, [rsp+38h+arg_0]
0x180018d16  add     rsp, 20h
0x180018d1a  pop     r14
0x180018d1c  pop     rdi
0x180018d1d  pop     rsi
0x180018d1e  retn
```
