# Storage::CVolumeInfo::_UpdateMountPoints(void)

- ea: `0x180007f90`
- end: `0x180008228`
- name: `?_UpdateMountPoints@CVolumeInfo@Storage@@AEAAJXZ`
- size: `664`
- prototype: `__int64 __fastcall(Storage::CVolumeInfo *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, service_task, installer_update`

## callers

- `0x180007b40`

## callees

- `0x180007b04`
- `0x180007b20`
- `0x180007f90`
- `0x1800264d4`
- `0x1800281e4`
- `0x180028268`
- `0x180028310`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008011`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000805e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008011`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000805e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000806c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000806c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008022`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000804e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000804e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800080c2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008140`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800080c2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008140`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180007fe1`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180008042`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180007fe1`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180008042`

## pseudocode

```c
__int64 __fastcall Storage::CVolumeInfo::_UpdateMountPoints(Storage::CVolumeInfo *this)
{
  WCHAR *v2; // r15
  DWORD v3; // r13d
  int v4; // r12d
  BOOL VolumePathNamesForVolumeNameW; // eax
  const unsigned __int16 *v6; // r8
  CRefCounted *v7; // rcx
  int v8; // esi
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rax
  WCHAR *v12; // rbx
  BOOL v13; // eax
  DWORD LastError; // eax
  int v15; // ecx
  HANDLE v16; // rax
  const unsigned __int16 *v17; // rbx
  int v18; // ebp
  const WCHAR *v19; // rsi
  __int64 v20; // rax
  __int64 v21; // rax
  WCHAR *i; // rsi
  const WCHAR *v23; // rbx
  int v24; // ebp
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  DWORD cchReturnLength; // [rsp+60h] [rbp+8h] BYREF
  char *v30; // [rsp+68h] [rbp+10h]

  v30 = (char *)this + 3416;
  CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter((char *)this + 3416);
  cchReturnLength = 0;
  v2 = 0;
  v3 = 0;
  v4 = -2147467259;
  VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW((LPCWSTR)this + 71, 0, 0, &cchReturnLength);
  v7 = 0;
  if ( !VolumePathNamesForVolumeNameW )
  {
    if ( GetLastError() == 234 )
    {
      v8 = 1;
      while ( 1 )
      {
        v9 = 2LL * cchReturnLength;
        ProcessHeap = GetProcessHeap();
        v11 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v9);
        v7 = 0;
        v12 = v11;
        if ( v11 )
        {
          v13 = GetVolumePathNamesForVolumeNameW((LPCWSTR)this + 71, v11, cchReturnLength, &cchReturnLength);
          v7 = 0;
          if ( v13 )
          {
            v3 = cchReturnLength;
            v2 = v12;
            v4 = 0;
            goto LABEL_14;
          }
          LastError = GetLastError();
          v15 = 0;
          if ( LastError == 234 )
            v15 = v8;
          v8 = v15;
          v16 = GetProcessHeap();
          HeapFree(v16, 0, v12);
          v7 = 0;
          v4 = -2147467259;
        }
        else
        {
          v4 = -2147024882;
        }
        if ( !v8 )
          goto LABEL_14;
      }
    }
    v7 = 0;
  }
LABEL_14:
  v17 = (const unsigned __int16 *)*((_QWORD *)this + 425);
  if ( v4 < 0 )
  {
    if ( v17 )
    {
      for ( ; *v17; v17 += v27 + 1 )
      {
        CNamedElemList<Storage::CMtPt>::Remove<unsigned short *>(v7, (__int64)v17);
        Storage::CVolumeInfo::_DispatchEventWithMountPoint(this, &Storage::GUID_IO_MOUNTPOINT_REMOVAL, v17);
        v27 = -1;
        do
          ++v27;
        while ( v17[v27] );
      }
      Storage::CVolumeInfo::_Cleanup(this);
    }
  }
  else
  {
    if ( v17 )
    {
      while ( *v17 )
      {
        v18 = 0;
        v19 = v2;
        while ( *v19 )
        {
          if ( !lstrcmpiW(v19, v17) )
            v18 = 1;
          v20 = -1;
          do
            ++v20;
          while ( v19[v20] );
          v19 += v20 + 1;
          if ( v18 )
            goto LABEL_26;
        }
        CNamedElemList<Storage::CMtPt>::Remove<unsigned short *>(0, (__int64)v17);
        Storage::CVolumeInfo::_DispatchEventWithMountPoint(this, &Storage::GUID_IO_MOUNTPOINT_REMOVAL, v17);
LABEL_26:
        v21 = -1;
        do
          ++v21;
        while ( v17[v21] );
        v17 += v21 + 1;
      }
    }
    for ( i = v2; *i; i += v26 + 1 )
    {
      v23 = (const WCHAR *)*((_QWORD *)this + 425);
      if ( v23 )
      {
        v24 = 0;
        while ( *v23 )
        {
          if ( !lstrcmpiW(i, v23) )
            v24 = 1;
          v25 = -1;
          do
            ++v25;
          while ( v23[v25] );
          v23 += v25 + 1;
          if ( v24 )
            goto LABEL_41;
        }
      }
      Storage::_CreateMtPt((Storage *)i, *((const unsigned __int16 **)this + 1), v6);
      Storage::CVolumeInfo::_DispatchEventWithMountPoint(this, &Storage::GUID_IO_MOUNTPOINT_ARRIVAL, i);
LABEL_41:
      v26 = -1;
      do
        ++v26;
      while ( i[v26] );
    }
    Storage::CVolumeInfo::_Cleanup(this);
    *((_QWORD *)this + 425) = v2;
    *((_DWORD *)this + 852) = v3;
  }
  CCritSectWithResource<CDummyResource>::Leave(v30);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007f90  mov     [rsp+arg_10], rbx
0x180007f95  push    rbp
0x180007f96  push    rsi
0x180007f97  push    rdi
0x180007f98  push    r12
0x180007f9a  push    r13
0x180007f9c  push    r14
0x180007f9e  push    r15
0x180007fa0  sub     rsp, 20h
0x180007fa4  lea     rax, [rcx+0D58h]
0x180007fab  mov     rdi, rcx
0x180007fae  mov     rcx, rax
0x180007fb1  mov     [rsp+58h+arg_8], rax
0x180007fb6  call    ?Enter@?$CCritSectWithResource@V?$CNamedElemList@VCHandleNotif@PnPServices@@@@@@QEAAXXZ; CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(void)
0x180007fbb  xor     eax, eax
0x180007fbd  lea     rbp, [rdi+8Eh]
0x180007fc4  mov     rcx, rbp; lpszVolumeName
0x180007fc7  mov     [rsp+58h+cchReturnLength], eax
0x180007fcb  lea     r9, [rsp+58h+cchReturnLength]; lpcchReturnLength
0x180007fd0  xor     r8d, r8d; cchBufferLength
0x180007fd3  xor     edx, edx; lpszVolumePathNames
0x180007fd5  mov     r15d, eax
0x180007fd8  mov     r13d, eax
0x180007fdb  mov     r12d, 80004005h
0x180007fe1  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180007fe7  xor     ecx, ecx
0x180007fe9  test    eax, eax
0x180007feb  jnz     loc_180008097
0x180007ff1  call    cs:__imp_GetLastError
0x180007ff7  mov     r14d, 0EAh
0x180007ffd  cmp     eax, r14d
0x180008000  jnz     loc_180008095
0x180008006  lea     esi, [r15+1]
0x18000800a  mov     ebx, [rsp+58h+cchReturnLength]
0x18000800e  add     rbx, rbx
0x180008011  call    cs:__imp_GetProcessHeap
0x180008017  mov     r8, rbx; dwBytes
0x18000801a  mov     edx, 8; dwFlags
0x18000801f  mov     rcx, rax; hHeap
0x180008022  call    cs:__imp_HeapAlloc
0x180008028  xor     ecx, ecx
0x18000802a  mov     rbx, rax
0x18000802d  test    rax, rax
0x180008030  jz      short loc_18000807C
0x180008032  mov     r8d, [rsp+58h+cchReturnLength]; cchBufferLength
0x180008037  lea     r9, [rsp+58h+cchReturnLength]; lpcchReturnLength
0x18000803c  mov     rdx, rax; lpszVolumePathNames
0x18000803f  mov     rcx, rbp; lpszVolumeName
0x180008042  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180008048  xor     ecx, ecx
0x18000804a  test    eax, eax
0x18000804c  jnz     short loc_180008088
0x18000804e  call    cs:__imp_GetLastError
0x180008054  xor     ecx, ecx
0x180008056  cmp     eax, r14d
0x180008059  cmovz   ecx, esi
0x18000805c  mov     esi, ecx
0x18000805e  call    cs:__imp_GetProcessHeap
0x180008064  mov     r8, rbx; lpMem
0x180008067  xor     edx, edx; dwFlags
0x180008069  mov     rcx, rax; hHeap
0x18000806c  call    cs:__imp_HeapFree
0x180008072  xor     ecx, ecx
0x180008074  mov     r12d, 80004005h
0x18000807a  jmp     short loc_180008082
0x18000807c  mov     r12d, 8007000Eh
0x180008082  test    esi, esi
0x180008084  jnz     short loc_18000800A
0x180008086  jmp     short loc_180008097
0x180008088  mov     r13d, [rsp+58h+cchReturnLength]
0x18000808d  mov     r15, rbx
0x180008090  mov     r12d, ecx
0x180008093  jmp     short loc_180008097
0x180008095  xor     ecx, ecx
0x180008097  mov     rbx, [rdi+0D48h]
0x18000809e  test    r12d, r12d
0x1800080a1  js      loc_1800081BB
0x1800080a7  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800080ab  test    rbx, rbx
0x1800080ae  jnz     short loc_180008119
0x1800080b0  jmp     short loc_18000811E
0x1800080b2  mov     ebp, ecx
0x1800080b4  mov     rsi, r15
0x1800080b7  mov     rdx, rbx; lpString2
0x1800080ba  cmp     [rsi], cx
0x1800080bd  jz      short loc_1800080EC
0x1800080bf  mov     rcx, rsi; lpString1
0x1800080c2  call    cs:__imp_lstrcmpiW
0x1800080c8  xor     ecx, ecx
0x1800080ca  test    eax, eax
0x1800080cc  lea     eax, [rcx+1]
0x1800080cf  cmovz   ebp, eax
0x1800080d2  mov     rax, r14
0x1800080d5  inc     rax
0x1800080d8  cmp     [rsi+rax*2], cx
0x1800080dc  jnz     short loc_1800080D5
0x1800080de  lea     rsi, [rsi+rax*2]
0x1800080e2  add     rsi, 2
0x1800080e6  test    ebp, ebp
0x1800080e8  jz      short loc_1800080B7
0x1800080ea  jmp     short loc_180008105
0x1800080ec  call    ??$Remove@PEAG@?$CNamedElemList@VCMtPt@Storage@@@@QEAAJQEAG@Z; CNamedElemList<Storage::CMtPt>::Remove<ushort *>(ushort * const)
0x1800080f1  mov     r8, rbx; unsigned __int16 *
0x1800080f4  lea     rdx, ?GUID_IO_MOUNTPOINT_REMOVAL@Storage@@3U_GUID@@B; struct _GUID *
0x1800080fb  mov     rcx, rdi; this
0x1800080fe  call    ?_DispatchEventWithMountPoint@CVolumeInfo@Storage@@AEAAJPEBU_GUID@@PEBG@Z; Storage::CVolumeInfo::_DispatchEventWithMountPoint(_GUID const *,ushort const *)
0x180008103  xor     ecx, ecx
0x180008105  mov     rax, r14
0x180008108  inc     rax
0x18000810b  cmp     [rbx+rax*2], cx
0x18000810f  jnz     short loc_180008108
0x180008111  lea     rbx, [rbx+rax*2]
0x180008115  add     rbx, 2
0x180008119  cmp     [rbx], cx
0x18000811c  jnz     short loc_1800080B2
0x18000811e  mov     rsi, r15
0x180008121  cmp     [r15], cx
0x180008125  jz      short loc_1800081A3
0x180008127  mov     rbx, [rdi+0D48h]
0x18000812e  test    rbx, rbx
0x180008131  jz      short loc_18000816A
0x180008133  mov     ebp, ecx
0x180008135  cmp     [rbx], cx
0x180008138  jz      short loc_18000816A
0x18000813a  mov     rdx, rbx; lpString2
0x18000813d  mov     rcx, rsi; lpString1
0x180008140  call    cs:__imp_lstrcmpiW
0x180008146  xor     ecx, ecx
0x180008148  test    eax, eax
0x18000814a  lea     eax, [rcx+1]
0x18000814d  cmovz   ebp, eax
0x180008150  mov     rax, r14
0x180008153  inc     rax
0x180008156  cmp     [rbx+rax*2], cx
0x18000815a  jnz     short loc_180008153
0x18000815c  lea     rbx, [rbx+rax*2]
0x180008160  add     rbx, 2
0x180008164  test    ebp, ebp
0x180008166  jz      short loc_180008135
0x180008168  jmp     short loc_18000818A
0x18000816a  mov     rdx, [rdi+8]; unsigned __int16 *
0x18000816e  mov     rcx, rsi; this
0x180008171  call    ?_CreateMtPt@Storage@@YAJPEBG0@Z; Storage::_CreateMtPt(ushort const *,ushort const *)
0x180008176  mov     r8, rsi; unsigned __int16 *
0x180008179  lea     rdx, ?GUID_IO_MOUNTPOINT_ARRIVAL@Storage@@3U_GUID@@B; struct _GUID *
0x180008180  mov     rcx, rdi; this
0x180008183  call    ?_DispatchEventWithMountPoint@CVolumeInfo@Storage@@AEAAJPEBU_GUID@@PEBG@Z; Storage::CVolumeInfo::_DispatchEventWithMountPoint(_GUID const *,ushort const *)
0x180008188  xor     ecx, ecx
0x18000818a  mov     rax, r14
0x18000818d  inc     rax
0x180008190  cmp     [rsi+rax*2], cx
0x180008194  jnz     short loc_18000818D
0x180008196  lea     rsi, [rsi+rax*2]
0x18000819a  add     rsi, 2
0x18000819e  cmp     [rsi], cx
0x1800081a1  jnz     short loc_180008127
0x1800081a3  mov     rcx, rdi; this
0x1800081a6  call    ?_Cleanup@CVolumeInfo@Storage@@AEAAXXZ; Storage::CVolumeInfo::_Cleanup(void)
0x1800081ab  mov     [rdi+0D48h], r15
0x1800081b2  mov     [rdi+0D50h], r13d
0x1800081b9  jmp     short loc_180008206
0x1800081bb  test    rbx, rbx
0x1800081be  jz      short loc_180008206
0x1800081c0  cmp     [rbx], cx
0x1800081c3  jz      short loc_1800081FE
0x1800081c5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800081c9  mov     rdx, rbx
0x1800081cc  call    ??$Remove@PEAG@?$CNamedElemList@VCMtPt@Storage@@@@QEAAJQEAG@Z; CNamedElemList<Storage::CMtPt>::Remove<ushort *>(ushort * const)
0x1800081d1  mov     r8, rbx; unsigned __int16 *
0x1800081d4  lea     rdx, ?GUID_IO_MOUNTPOINT_REMOVAL@Storage@@3U_GUID@@B; struct _GUID *
0x1800081db  mov     rcx, rdi; this
0x1800081de  call    ?_DispatchEventWithMountPoint@CVolumeInfo@Storage@@AEAAJPEBU_GUID@@PEBG@Z; Storage::CVolumeInfo::_DispatchEventWithMountPoint(_GUID const *,ushort const *)
0x1800081e3  mov     rdx, r14
0x1800081e6  xor     eax, eax
0x1800081e8  inc     rdx
0x1800081eb  cmp     [rbx+rdx*2], ax
0x1800081ef  jnz     short loc_1800081E8
0x1800081f1  lea     rbx, [rbx+rdx*2]
0x1800081f5  add     rbx, 2
0x1800081f9  cmp     [rbx], ax
0x1800081fc  jnz     short loc_1800081C9
0x1800081fe  mov     rcx, rdi; this
0x180008201  call    ?_Cleanup@CVolumeInfo@Storage@@AEAAXXZ; Storage::CVolumeInfo::_Cleanup(void)
0x180008206  mov     rcx, [rsp+58h+arg_8]
0x18000820b  call    ?Leave@?$CCritSectWithResource@VCDummyResource@@@@QEAAXXZ; CCritSectWithResource<CDummyResource>::Leave(void)
0x180008210  mov     rbx, [rsp+58h+arg_10]
0x180008215  mov     eax, r12d
0x180008218  add     rsp, 20h
0x18000821c  pop     r15
0x18000821e  pop     r14
0x180008220  pop     r13
0x180008222  pop     r12
0x180008224  pop     rdi
0x180008225  pop     rsi
0x180008226  pop     rbp
0x180008227  retn
```
