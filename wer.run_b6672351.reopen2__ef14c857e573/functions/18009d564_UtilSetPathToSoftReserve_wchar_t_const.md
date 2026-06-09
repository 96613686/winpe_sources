# UtilSetPathToSoftReserve(wchar_t const *)

- ea: `0x18009d564`
- end: `0x18009d67f`
- name: `?UtilSetPathToSoftReserve@@YAJPEB_W@Z`
- size: `283`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18001d718`
- `0x180079e2c`

## callees

- `0x180007fd8`
- `0x180008004`
- `0x18001c368`
- `0x180020680`
- `0x18009d564`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d5cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d5cc`
- `ntdll!NtSetInformationFile` at `0x18009d621`
- `ntdll!NtSetInformationFile` at `0x18009d621`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009d5a4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009d5a4`

## pseudocode

```c
__int64 __fastcall UtilSetPathToSoftReserve(const wchar_t *a1)
{
  HANDLE FileW; // rax
  DWORD LastError; // eax
  unsigned int v3; // ebx
  wchar_t *v4; // rcx
  __int64 v5; // rdx
  NTSTATUS v6; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-18h] BYREF
  int FileInformation; // [rsp+68h] [rbp+10h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp+18h] BYREF

  FileHandle = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  FileW = CreateFileW(a1, 0x180u, 7u, 0, 3u, 0x2000080u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&FileHandle, FileW);
  if ( (unsigned __int64)FileHandle + 1 > 1 )
  {
    FileInformation = 2;
    v6 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 4u, FileRenameInformation|0x40);
    if ( v6 >= 0 )
    {
      v3 = 0;
      goto LABEL_11;
    }
    v3 = v6 | 0x10000000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
    {
      v5 = 185;
      goto LABEL_9;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = ERROR_HR_FROM_WIN32(LastError);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
    {
      v5 = 184;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, v3);
    }
  }
LABEL_11:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&FileHandle);
  return v3;
}

```

## disassembly

```asm
0x18009d564  mov     rax, rsp
0x18009d567  push    rbx
0x18009d568  sub     rsp, 50h
0x18009d56c  mov     qword ptr [rax-28h], 0
0x18009d574  xor     r9d, r9d; lpSecurityAttributes
0x18009d577  xorps   xmm0, xmm0
0x18009d57a  mov     dword ptr [rax-30h], 2000080h
0x18009d581  mov     edx, 180h; dwDesiredAccess
0x18009d586  mov     qword ptr [rax+18h], 0
0x18009d58e  movups  xmmword ptr [rax-18h], xmm0
0x18009d592  lea     r8d, [r9+7]; dwShareMode
0x18009d596  mov     dword ptr [rax+10h], 0
0x18009d59d  mov     dword ptr [rax-38h], 3
0x18009d5a4  call    cs:__imp_CreateFileW
0x18009d5ab  nop     dword ptr [rax+rax+00h]
0x18009d5b0  mov     rdx, rax
0x18009d5b3  lea     rcx, [rsp+58h+FileHandle]
0x18009d5b8  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009d5bd  mov     rcx, [rsp+58h+FileHandle]; FileHandle
0x18009d5c2  lea     rax, [rcx+1]
0x18009d5c6  cmp     rax, 1
0x18009d5ca  ja      short loc_18009D601
0x18009d5cc  call    cs:__imp_GetLastError
0x18009d5d3  nop     dword ptr [rax+rax+00h]
0x18009d5d8  mov     ecx, eax; unsigned int
0x18009d5da  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009d5df  mov     ebx, eax
0x18009d5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d5e8  lea     rax, WPP_GLOBAL_Control
0x18009d5ef  cmp     rcx, rax
0x18009d5f2  jz      short loc_18009D66C
0x18009d5f4  test    byte ptr [rcx+1Ch], 2
0x18009d5f8  jz      short loc_18009D66C
0x18009d5fa  mov     edx, 0B8h
0x18009d5ff  jmp     short loc_18009D655
0x18009d601  mov     r9d, 4; Length
0x18009d607  mov     [rsp+58h+FileInformation], 2
0x18009d60f  lea     r8, [rsp+58h+FileInformation]; FileInformation
0x18009d614  mov     [rsp+58h+FileInformationClass], 4Ah ; 'J'; FileInformationClass
0x18009d61c  lea     rdx, [rsp+58h+IoStatusBlock]; IoStatusBlock
0x18009d621  call    cs:__imp_NtSetInformationFile
0x18009d628  nop     dword ptr [rax+rax+00h]
0x18009d62d  mov     ebx, eax
0x18009d62f  test    eax, eax
0x18009d631  jns     short loc_18009D66A
0x18009d633  bts     ebx, 1Ch
0x18009d637  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d63e  lea     rax, WPP_GLOBAL_Control
0x18009d645  cmp     rcx, rax
0x18009d648  jz      short loc_18009D66C
0x18009d64a  test    byte ptr [rcx+1Ch], 2
0x18009d64e  jz      short loc_18009D66C
0x18009d650  mov     edx, 0B9h
0x18009d655  mov     rcx, [rcx+10h]
0x18009d659  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009d660  mov     r9d, ebx
0x18009d663  call    WPP_SF_d
0x18009d668  jmp     short loc_18009D66C
0x18009d66a  xor     ebx, ebx
0x18009d66c  lea     rcx, [rsp+58h+FileHandle]
0x18009d671  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18009d676  mov     eax, ebx
0x18009d678  add     rsp, 50h
0x18009d67c  pop     rbx
0x18009d67d  retn
```
