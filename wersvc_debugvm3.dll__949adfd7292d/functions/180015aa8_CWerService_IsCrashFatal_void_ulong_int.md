# CWerService::IsCrashFatal(void *,ulong,int *)

- ea: `0x180015aa8`
- end: `0x180015d0f`
- name: `?IsCrashFatal@CWerService@@AEAAJPEAXKPEAH@Z`
- size: `615`
- prototype: `int(CWerService *__hidden this, void *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001ad28`

## callees

- `0x1800035e8`
- `0x180007cf8`
- `0x180011ef8`
- `0x180014ea4`
- `0x180015aa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015b4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015b4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015be8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015be8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ca2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015c9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015cfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015c9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015cfa`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015b78`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015b78`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180015c91`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180015c91`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180015bda`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180015bda`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180015b28`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180015b28`

## pseudocode

```c
__int64 __fastcall CWerService::IsCrashFatal(CWerService *this, void *a2, DWORD a3, int *a4)
{
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  char *v11; // rbx
  HANDLE *v12; // rdi
  HANDLE CurrentProcess; // rax
  signed int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  const struct _CRASH_SHARED_DATA *v17; // rax
  const struct _CRASH_SHARED_DATA *v18; // rsi
  signed int LastError; // eax
  signed int v20; // eax
  _BYTE v22[296]; // [rsp+40h] [rbp-128h] BYREF
  HANDLE hFileMappingObject; // [rsp+170h] [rbp+8h] BYREF

  hFileMappingObject = 0;
  memset_0(v22, 0, 0xF8u);
  if ( !a4 )
  {
    v7 = -2147024809;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v9 = 185;
      v10 = 2147942487LL;
LABEL_31:
      WPP_SF_d(v8[2], v9, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v10);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  *a4 = 1;
  v11 = (char *)OpenProcess(0x50u, 0, a3);
  if ( v11 != (char *)-1LL && v11 + 1 != (char *)1 )
  {
    v12 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&hFileMappingObject);
    CurrentProcess = GetCurrentProcess();
    if ( DuplicateHandle(v11, a2, CurrentProcess, v12, 0, 1, 2u) )
    {
      v17 = (const struct _CRASH_SHARED_DATA *)MapViewOfFile(hFileMappingObject, 4u, 0, 0, 0);
      v18 = v17;
      if ( v17 )
      {
        v7 = CopyCrashSharedData((struct _CRASH_SHARED_DATA *)v22, v17);
        if ( (v7 & 0x80000000) == 0 )
        {
          *a4 = (v22[236] & 4) == 0;
          v7 = 0;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v7);
        }
        UnmapViewOfFile(v18);
        goto LABEL_25;
      }
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_25:
        CloseHandle(v11);
        goto LABEL_32;
      }
      v16 = 188;
    }
    else
    {
      v14 = GetLastError();
      v7 = v14;
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_25;
      v16 = 187;
    }
    WPP_SF_d(v15[2], v16, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v7);
    goto LABEL_25;
  }
  v20 = GetLastError();
  v7 = v20;
  if ( v20 > 0 )
    v7 = (unsigned __int16)v20 | 0x80070000;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v9 = 186;
    v10 = v7;
    goto LABEL_31;
  }
LABEL_32:
  if ( (unsigned __int64)hFileMappingObject + 1 > 1 )
    CloseHandle(hFileMappingObject);
  return v7;
}

```

## disassembly

```asm
0x180015aa8  mov     rax, rsp
0x180015aab  mov     [rax+8], rcx
0x180015aaf  push    rbx
0x180015ab0  push    rsi
0x180015ab1  push    rdi
0x180015ab2  push    r14
0x180015ab4  sub     rsp, 148h
0x180015abb  mov     ebx, r8d
0x180015abe  mov     qword ptr [rax+8], 0
0x180015ac6  mov     rsi, rdx
0x180015ac9  lea     rcx, [rsp+168h+var_128]; void *
0x180015ace  xor     edx, edx; Val
0x180015ad0  mov     r8d, 0F8h; Size
0x180015ad6  mov     r14, r9
0x180015ad9  call    memset_0
0x180015ade  test    r14, r14
0x180015ae1  jnz     short loc_180015B19
0x180015ae3  mov     edi, 80070057h
0x180015ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180015aef  lea     rax, WPP_GLOBAL_Control
0x180015af6  cmp     rcx, rax
0x180015af9  jz      loc_180015CE8
0x180015aff  test    byte ptr [rcx+1Ch], 2
0x180015b03  jz      loc_180015CE8
0x180015b09  mov     edx, 0B9h
0x180015b0e  mov     r9d, 80070057h
0x180015b14  jmp     loc_180015CD8
0x180015b19  xor     edx, edx; bInheritHandle
0x180015b1b  mov     dword ptr [r14], 1
0x180015b22  mov     r8d, ebx; dwProcessId
0x180015b25  lea     ecx, [rdx+50h]; dwDesiredAccess
0x180015b28  call    cs:__imp_OpenProcess
0x180015b2e  mov     rbx, rax
0x180015b31  inc     rax
0x180015b34  cmp     rax, 1
0x180015b38  jbe     loc_180015CA2
0x180015b3e  lea     rcx, [rsp+168h+hFileMappingObject]
0x180015b46  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180015b4b  mov     rdi, rax
0x180015b4e  call    cs:__imp_GetCurrentProcess
0x180015b54  mov     [rsp+168h+dwOptions], 2; dwOptions
0x180015b5c  mov     r9, rdi; lpTargetHandle
0x180015b5f  mov     r8, rax; hTargetProcessHandle
0x180015b62  mov     [rsp+168h+bInheritHandle], 1; bInheritHandle
0x180015b6a  mov     rdx, rsi; hSourceHandle
0x180015b6d  mov     [rsp+168h+dwDesiredAccess], 0; dwDesiredAccess
0x180015b75  mov     rcx, rbx; hSourceProcessHandle
0x180015b78  call    cs:__imp_DuplicateHandle
0x180015b7e  test    eax, eax
0x180015b80  jnz     short loc_180015BBF
0x180015b82  call    cs:__imp_GetLastError
0x180015b88  mov     edi, eax
0x180015b8a  test    eax, eax
0x180015b8c  jle     short loc_180015B97
0x180015b8e  movzx   edi, ax
0x180015b91  or      edi, 80070000h
0x180015b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b9e  lea     rax, WPP_GLOBAL_Control
0x180015ba5  cmp     rcx, rax
0x180015ba8  jz      loc_180015C97
0x180015bae  test    byte ptr [rcx+1Ch], 2
0x180015bb2  jz      loc_180015C97
0x180015bb8  mov     edx, 0BBh
0x180015bbd  jmp     short loc_180015C1F
0x180015bbf  mov     rcx, [rsp+168h+hFileMappingObject]; hFileMappingObject
0x180015bc7  xor     r9d, r9d; dwFileOffsetLow
0x180015bca  xor     r8d, r8d; dwFileOffsetHigh
0x180015bcd  mov     qword ptr [rsp+168h+dwDesiredAccess], 0; dwNumberOfBytesToMap
0x180015bd6  lea     edx, [r9+4]; dwDesiredAccess
0x180015bda  call    cs:__imp_MapViewOfFile
0x180015be0  mov     rsi, rax
0x180015be3  test    rax, rax
0x180015be6  jnz     short loc_180015C34
0x180015be8  call    cs:__imp_GetLastError
0x180015bee  mov     edi, eax
0x180015bf0  test    eax, eax
0x180015bf2  jle     short loc_180015BFD
0x180015bf4  movzx   edi, ax
0x180015bf7  or      edi, 80070000h
0x180015bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c04  lea     rax, WPP_GLOBAL_Control
0x180015c0b  cmp     rcx, rax
0x180015c0e  jz      loc_180015C97
0x180015c14  test    byte ptr [rcx+1Ch], 2
0x180015c18  jz      short loc_180015C97
0x180015c1a  mov     edx, 0BCh
0x180015c1f  mov     rcx, [rcx+10h]
0x180015c23  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180015c2a  mov     r9d, edi
0x180015c2d  call    WPP_SF_d
0x180015c32  jmp     short loc_180015C97
0x180015c34  mov     rdx, rsi; struct _CRASH_SHARED_DATA *
0x180015c37  lea     rcx, [rsp+168h+var_128]; struct _CRASH_SHARED_DATA *
0x180015c3c  call    ?CopyCrashSharedData@@YAJPEAU_CRASH_SHARED_DATA@@PEBU1@@Z; CopyCrashSharedData(_CRASH_SHARED_DATA *,_CRASH_SHARED_DATA const *)
0x180015c41  mov     edi, eax
0x180015c43  test    eax, eax
0x180015c45  jns     short loc_180015C7A
0x180015c47  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c4e  lea     rax, WPP_GLOBAL_Control
0x180015c55  cmp     rcx, rax
0x180015c58  jz      short loc_180015C8E
0x180015c5a  test    byte ptr [rcx+1Ch], 1
0x180015c5e  jz      short loc_180015C8E
0x180015c60  mov     rcx, [rcx+10h]
0x180015c64  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180015c6b  mov     edx, 0BDh
0x180015c70  mov     r9d, edi
0x180015c73  call    WPP_SF_d
0x180015c78  jmp     short loc_180015C8E
0x180015c7a  mov     eax, [rsp+168h+var_3C]
0x180015c81  shr     eax, 2
0x180015c84  not     eax
0x180015c86  and     eax, 1
0x180015c89  mov     [r14], eax
0x180015c8c  xor     edi, edi
0x180015c8e  mov     rcx, rsi; lpBaseAddress
0x180015c91  call    cs:__imp_UnmapViewOfFile
0x180015c97  mov     rcx, rbx; hObject
0x180015c9a  call    cs:__imp_CloseHandle
0x180015ca0  jmp     short loc_180015CE8
0x180015ca2  call    cs:__imp_GetLastError
0x180015ca8  mov     edi, eax
0x180015caa  test    eax, eax
0x180015cac  jle     short loc_180015CB7
0x180015cae  movzx   edi, ax
0x180015cb1  or      edi, 80070000h
0x180015cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180015cbe  lea     rax, WPP_GLOBAL_Control
0x180015cc5  cmp     rcx, rax
0x180015cc8  jz      short loc_180015CE8
0x180015cca  test    byte ptr [rcx+1Ch], 2
0x180015cce  jz      short loc_180015CE8
0x180015cd0  mov     edx, 0BAh
0x180015cd5  mov     r9d, edi
0x180015cd8  mov     rcx, [rcx+10h]
0x180015cdc  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180015ce3  call    WPP_SF_d
0x180015ce8  mov     rcx, [rsp+168h+hFileMappingObject]; hObject
0x180015cf0  lea     rax, [rcx+1]
0x180015cf4  cmp     rax, 1
0x180015cf8  jbe     short loc_180015D00
0x180015cfa  call    cs:__imp_CloseHandle
0x180015d00  mov     eax, edi
0x180015d02  add     rsp, 148h
0x180015d09  pop     r14
0x180015d0b  pop     rdi
0x180015d0c  pop     rsi
0x180015d0d  pop     rbx
0x180015d0e  retn
```
