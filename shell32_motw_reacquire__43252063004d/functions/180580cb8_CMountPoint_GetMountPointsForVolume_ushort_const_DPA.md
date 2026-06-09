# CMountPoint::_GetMountPointsForVolume(ushort const *,_DPA *)

- ea: `0x180580cb8`
- end: `0x180580e89`
- name: `?_GetMountPointsForVolume@CMountPoint@@CAJPEBGPEAU_DPA@@@Z`
- size: `465`
- prototype: `__int64 __fastcall(LPCWSTR lpString2, HDPA hdpa)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x1805835c8`

## callees

- `0x18001a2bc`
- `0x180067118`
- `0x180067938`
- `0x18009a838`
- `0x180580cb8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180580d6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180580e4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180580d6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180580e4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180580d89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180580e6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180580d89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180580e6f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180580d41`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180580e1e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180580d41`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180580e1e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180580d26`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180580e0a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180580d26`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180580e0a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580cc9`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580ce9`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580d79`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580d95`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580da9`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580dd4`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580e60`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580cc9`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580ce9`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580d79`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580d95`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580da9`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580dd4`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180580e60`

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
0x180580cb8  push    rbx
0x180580cba  push    rbp
0x180580cbb  push    rsi
0x180580cbc  push    rdi
0x180580cbd  push    r14
0x180580cbf  sub     rsp, 20h
0x180580cc3  mov     rbp, rdx
0x180580cc6  mov     r14, rcx
0x180580cc9  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180580cd0  nop     dword ptr [rax+rax+00h]
0x180580cd5  lea     rcx, [rax+38h]; Parameter
0x180580cd9  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180580cde  xor     ebx, ebx
0x180580ce0  cmp     ebx, 1Ah
0x180580ce3  jnb     loc_180580D79
0x180580ce9  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180580cf0  nop     dword ptr [rax+rax+00h]
0x180580cf5  mov     edx, ebx; int
0x180580cf7  lea     rcx, [rax+108h]; this
0x180580cfe  call    ?GetDriveLetterData@CDriveLetterCache@@QEAAPEAVCDriveLetterData@@H@Z; CDriveLetterCache::GetDriveLetterData(int)
0x180580d03  mov     rdi, rax
0x180580d06  test    rax, rax
0x180580d09  jz      short loc_180580D36
0x180580d0b  mov     rcx, [rax]
0x180580d0e  test    rcx, rcx
0x180580d11  jz      short loc_180580D36
0x180580d13  mov     rcx, [rcx+240h]
0x180580d1a  test    rcx, rcx
0x180580d1d  jz      short loc_180580D36
0x180580d1f  mov     rcx, [rcx+70h]; lpString1
0x180580d23  mov     rdx, r14; lpString2
0x180580d26  call    cs:__imp_lstrcmpiW
0x180580d2d  nop     dword ptr [rax+rax+00h]
0x180580d32  test    eax, eax
0x180580d34  jz      short loc_180580D3A
0x180580d36  inc     ebx
0x180580d38  jmp     short loc_180580CE0
0x180580d3a  mov     rcx, [rdi]
0x180580d3d  add     rcx, 34h ; '4'; pszSrch
0x180580d41  call    cs:__imp_StrDupW
0x180580d48  nop     dword ptr [rax+rax+00h]
0x180580d4d  mov     rbx, rax
0x180580d50  test    rax, rax
0x180580d53  jz      short loc_180580D79
0x180580d55  mov     r8, rax; p
0x180580d58  mov     edx, 7FFFFFFFh; i
0x180580d5d  mov     rcx, rbp; hdpa
0x180580d60  call    DPA_InsertPtr
0x180580d65  cmp     eax, 0FFFFFFFFh
0x180580d68  jnz     short loc_180580D79
0x180580d6a  mov     rcx, rbx; hMem
0x180580d6d  call    cs:__imp_LocalFree
0x180580d74  nop     dword ptr [rax+rax+00h]
0x180580d79  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180580d80  nop     dword ptr [rax+rax+00h]
0x180580d85  lea     rcx, [rax+38h]; lpCriticalSection
0x180580d89  call    cs:__imp_LeaveCriticalSection
0x180580d90  nop     dword ptr [rax+rax+00h]
0x180580d95  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180580d9c  nop     dword ptr [rax+rax+00h]
0x180580da1  mov     rcx, rax; Parameter
0x180580da4  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180580da9  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180580db0  nop     dword ptr [rax+rax+00h]
0x180580db5  mov     rsi, [rax+0F0h]
0x180580dbc  test    rsi, rsi
0x180580dbf  jz      loc_180580E60
0x180580dc5  mov     esi, [rsi]
0x180580dc7  xor     edi, edi
0x180580dc9  test    esi, esi
0x180580dcb  jle     loc_180580E60
0x180580dd1  movsxd  rbx, edi
0x180580dd4  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180580ddb  nop     dword ptr [rax+rax+00h]
0x180580de0  mov     rdx, rbx; i
0x180580de3  mov     rcx, [rax+0F0h]; hdpa
0x180580dea  call    DPA_GetPtr
0x180580def  mov     rbx, rax
0x180580df2  test    rax, rax
0x180580df5  jz      short loc_180580E56
0x180580df7  mov     rcx, [rax+240h]
0x180580dfe  test    rcx, rcx
0x180580e01  jz      short loc_180580E56
0x180580e03  mov     rcx, [rcx+70h]; lpString1
0x180580e07  mov     rdx, r14; lpString2
0x180580e0a  call    cs:__imp_lstrcmpiW
0x180580e11  nop     dword ptr [rax+rax+00h]
0x180580e16  test    eax, eax
0x180580e18  jnz     short loc_180580E56
0x180580e1a  lea     rcx, [rbx+34h]; pszSrch
0x180580e1e  call    cs:__imp_StrDupW
0x180580e25  nop     dword ptr [rax+rax+00h]
0x180580e2a  mov     rbx, rax
0x180580e2d  test    rax, rax
0x180580e30  jz      short loc_180580E56
0x180580e32  mov     r8, rax; p
0x180580e35  mov     edx, 7FFFFFFFh; i
0x180580e3a  mov     rcx, rbp; hdpa
0x180580e3d  call    DPA_InsertPtr
0x180580e42  cmp     eax, 0FFFFFFFFh
0x180580e45  jnz     short loc_180580E56
0x180580e47  mov     rcx, rbx; hMem
0x180580e4a  call    cs:__imp_LocalFree
0x180580e51  nop     dword ptr [rax+rax+00h]
0x180580e56  inc     edi
0x180580e58  cmp     edi, esi
0x180580e5a  jl      loc_180580DD1
0x180580e60  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180580e67  nop     dword ptr [rax+rax+00h]
0x180580e6c  mov     rcx, rax; lpCriticalSection
0x180580e6f  call    cs:__imp_LeaveCriticalSection
0x180580e76  nop     dword ptr [rax+rax+00h]
0x180580e7b  xor     eax, eax
0x180580e7d  add     rsp, 20h
0x180580e81  pop     r14
0x180580e83  pop     rdi
0x180580e84  pop     rsi
0x180580e85  pop     rbp
0x180580e86  pop     rbx
0x180580e87  retn
```
