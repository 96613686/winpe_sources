# CMountPoint::_GetMountPointsForVolume(ushort const *,_DPA *)

- ea: `0x180541c20`
- end: `0x180541d86`
- name: `?_GetMountPointsForVolume@CMountPoint@@CAJPEBGPEAU_DPA@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(LPCWSTR lpString2, HDPA hdpa)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x180544088`

## callees

- `0x1800265e8`
- `0x180026dc4`
- `0x1800bfb48`
- `0x1800c0c44`
- `0x180541c20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180541cb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180541d5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180541cb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180541d5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180541cc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180541d73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180541cc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180541d73`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180541c93`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180541d38`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180541c93`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180541d38`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180541c7e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180541d2a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180541c7e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180541d2a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541c31`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541c47`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541cbf`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541ccf`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541cdd`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541cfa`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541d6a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541c31`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541c47`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541cbf`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541ccf`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541cdd`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541cfa`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180541d6a`

## pseudocode

```c
__int64 __fastcall CMountPoint::_GetMountPointsForVolume(LPCWSTR lpString2, HDPA hdpa)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned int i; // ebx
  __int64 v7; // rax
  struct CDriveLetterData *DriveLetterData; // rax
  struct CDriveLetterData *v9; // rdi
  PWSTR v10; // rax
  PWSTR v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rcx
  void *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  int *v17; // rsi
  int v18; // esi
  int j; // edi
  __int64 v20; // rax
  const WCHAR *Ptr; // rax
  const WCHAR *v22; // rbx
  PWSTR v23; // rax
  PWSTR v24; // rbx
  struct _RTL_CRITICAL_SECTION *v25; // rax

  v4 = Global_WindowsStorage_Untyped_MountPoint(lpString2);
  CCritSecDelayInitBase::Enter((PVOID)(v4 + 56));
  for ( i = 0; i < 0x1A; ++i )
  {
    v7 = Global_WindowsStorage_Untyped_MountPoint(v5);
    DriveLetterData = CDriveLetterCache::GetDriveLetterData((CDriveLetterCache *)(v7 + 264), i);
    v9 = DriveLetterData;
    if ( DriveLetterData )
    {
      v5 = *(_QWORD *)DriveLetterData;
      if ( *(_QWORD *)DriveLetterData )
      {
        v5 = *(_QWORD *)(v5 + 576);
        if ( v5 )
        {
          if ( !lstrcmpiW(*(LPCWSTR *)(v5 + 112), lpString2) )
          {
            v10 = StrDupW((PCWSTR)(*(_QWORD *)v9 + 52LL));
            v11 = v10;
            if ( v10 && DPA_InsertPtr(hdpa, 0x7FFFFFFF, v10) == -1 )
              LocalFree(v11);
            break;
          }
        }
      }
    }
  }
  v12 = Global_WindowsStorage_Untyped_MountPoint(v5);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 56));
  v14 = (void *)Global_WindowsStorage_Untyped_MountPoint(v13);
  CCritSecDelayInitBase::Enter(v14);
  v17 = *(int **)(Global_WindowsStorage_Untyped_MountPoint(v15) + 240);
  if ( v17 )
  {
    v18 = *v17;
    for ( j = 0; j < v18; ++j )
    {
      v20 = Global_WindowsStorage_Untyped_MountPoint(v16);
      Ptr = (const WCHAR *)DPA_GetPtr(*(HDPA *)(v20 + 240), j);
      v22 = Ptr;
      if ( Ptr )
      {
        v16 = *((_QWORD *)Ptr + 72);
        if ( v16 )
        {
          if ( !lstrcmpiW(*(LPCWSTR *)(v16 + 112), lpString2) )
          {
            v23 = StrDupW(v22 + 26);
            v24 = v23;
            if ( v23 )
            {
              if ( DPA_InsertPtr(hdpa, 0x7FFFFFFF, v23) == -1 )
                LocalFree(v24);
            }
          }
        }
      }
    }
  }
  v25 = (struct _RTL_CRITICAL_SECTION *)Global_WindowsStorage_Untyped_MountPoint(v16);
  LeaveCriticalSection(v25);
  return 0;
}

```

## disassembly

```asm
0x180541c20  push    rbx
0x180541c22  push    rbp
0x180541c23  push    rsi
0x180541c24  push    rdi
0x180541c25  push    r14
0x180541c27  sub     rsp, 20h
0x180541c2b  mov     rbp, rdx
0x180541c2e  mov     r14, rcx
0x180541c31  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180541c37  lea     rcx, [rax+38h]; Parameter
0x180541c3b  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180541c40  xor     ebx, ebx
0x180541c42  cmp     ebx, 1Ah
0x180541c45  jnb     short loc_180541CBF
0x180541c47  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180541c4d  mov     edx, ebx; int
0x180541c4f  lea     rcx, [rax+108h]; this
0x180541c56  call    ?GetDriveLetterData@CDriveLetterCache@@QEAAPEAVCDriveLetterData@@H@Z; CDriveLetterCache::GetDriveLetterData(int)
0x180541c5b  mov     rdi, rax
0x180541c5e  test    rax, rax
0x180541c61  jz      short loc_180541C88
0x180541c63  mov     rcx, [rax]
0x180541c66  test    rcx, rcx
0x180541c69  jz      short loc_180541C88
0x180541c6b  mov     rcx, [rcx+240h]
0x180541c72  test    rcx, rcx
0x180541c75  jz      short loc_180541C88
0x180541c77  mov     rcx, [rcx+70h]; lpString1
0x180541c7b  mov     rdx, r14; lpString2
0x180541c7e  call    cs:__imp_lstrcmpiW
0x180541c84  test    eax, eax
0x180541c86  jz      short loc_180541C8C
0x180541c88  inc     ebx
0x180541c8a  jmp     short loc_180541C42
0x180541c8c  mov     rcx, [rdi]
0x180541c8f  add     rcx, 34h ; '4'; pszSrch
0x180541c93  call    cs:__imp_StrDupW
0x180541c99  mov     rbx, rax
0x180541c9c  test    rax, rax
0x180541c9f  jz      short loc_180541CBF
0x180541ca1  mov     r8, rax; p
0x180541ca4  mov     edx, 7FFFFFFFh; i
0x180541ca9  mov     rcx, rbp; hdpa
0x180541cac  call    DPA_InsertPtr
0x180541cb1  cmp     eax, 0FFFFFFFFh
0x180541cb4  jnz     short loc_180541CBF
0x180541cb6  mov     rcx, rbx; hMem
0x180541cb9  call    cs:__imp_LocalFree
0x180541cbf  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180541cc5  lea     rcx, [rax+38h]; lpCriticalSection
0x180541cc9  call    cs:__imp_LeaveCriticalSection
0x180541ccf  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180541cd5  mov     rcx, rax; Parameter
0x180541cd8  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180541cdd  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180541ce3  mov     rsi, [rax+0F0h]
0x180541cea  test    rsi, rsi
0x180541ced  jz      short loc_180541D6A
0x180541cef  mov     esi, [rsi]
0x180541cf1  xor     edi, edi
0x180541cf3  test    esi, esi
0x180541cf5  jle     short loc_180541D6A
0x180541cf7  movsxd  rbx, edi
0x180541cfa  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180541d00  mov     rdx, rbx; i
0x180541d03  mov     rcx, [rax+0F0h]; hdpa
0x180541d0a  call    DPA_GetPtr
0x180541d0f  mov     rbx, rax
0x180541d12  test    rax, rax
0x180541d15  jz      short loc_180541D64
0x180541d17  mov     rcx, [rax+240h]
0x180541d1e  test    rcx, rcx
0x180541d21  jz      short loc_180541D64
0x180541d23  mov     rcx, [rcx+70h]; lpString1
0x180541d27  mov     rdx, r14; lpString2
0x180541d2a  call    cs:__imp_lstrcmpiW
0x180541d30  test    eax, eax
0x180541d32  jnz     short loc_180541D64
0x180541d34  lea     rcx, [rbx+34h]; pszSrch
0x180541d38  call    cs:__imp_StrDupW
0x180541d3e  mov     rbx, rax
0x180541d41  test    rax, rax
0x180541d44  jz      short loc_180541D64
0x180541d46  mov     r8, rax; p
0x180541d49  mov     edx, 7FFFFFFFh; i
0x180541d4e  mov     rcx, rbp; hdpa
0x180541d51  call    DPA_InsertPtr
0x180541d56  cmp     eax, 0FFFFFFFFh
0x180541d59  jnz     short loc_180541D64
0x180541d5b  mov     rcx, rbx; hMem
0x180541d5e  call    cs:__imp_LocalFree
0x180541d64  inc     edi
0x180541d66  cmp     edi, esi
0x180541d68  jl      short loc_180541CF7
0x180541d6a  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180541d70  mov     rcx, rax; lpCriticalSection
0x180541d73  call    cs:__imp_LeaveCriticalSection
0x180541d79  xor     eax, eax
0x180541d7b  add     rsp, 20h
0x180541d7f  pop     r14
0x180541d81  pop     rdi
0x180541d82  pop     rsi
0x180541d83  pop     rbp
0x180541d84  pop     rbx
0x180541d85  retn
```
