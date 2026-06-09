# EvtFile::EvtFile(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x1800b6088`
- end: `0x1800b65f5`
- name: `??0EvtFile@@QEAA@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z`
- size: `1389`
- prototype: `EvtFile *__fastcall(EvtFile *this, EvtFile **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180076454`

## callees

- `0x180004a3c`
- `0x18002dcc0`
- `0x18002e468`
- `0x18005ff90`
- `0x18007a2d0`
- `0x180092008`
- `0x180092048`
- `0x180098c50`
- `0x1800b6088`
- `0x1800b6618`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b624c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b624c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6327`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800b63c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800b63c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b6224`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b6224`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b630a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b630a`
- `RPCRT4!RpcImpersonateClient` at `0x1800b618a`
- `RPCRT4!RpcImpersonateClient` at `0x1800b618a`
- `RPCRT4!RpcRevertToSelf` at `0x1800b6235`
- `RPCRT4!RpcRevertToSelf` at `0x1800b6235`

## pseudocode

```c
EvtFile *__fastcall EvtFile::EvtFile(EvtFile *this, EvtFile **a2)
{
  LPCWSTR *v3; // rsi
  HANDLE *v4; // r14
  unsigned int v5; // eax
  unsigned int v6; // ebx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  HANDLE FileMappingW; // rax
  DWORD v12; // ebx
  _OWORD *v13; // rax
  PVOID *v14; // rcx
  PVOID *v16; // rcx
  EvtFile *v17; // [rsp+40h] [rbp-59h] BYREF
  EvtFile *v18; // [rsp+48h] [rbp-51h]
  __int128 pExceptionObject; // [rsp+50h] [rbp-49h] BYREF
  __int64 v20; // [rsp+60h] [rbp-39h]
  int v21; // [rsp+68h] [rbp-31h]
  __int64 v22; // [rsp+6Ch] [rbp-2Dh]
  char v23; // [rsp+74h] [rbp-25h]
  struct _SYSTEM_INFO SystemInfo; // [rsp+78h] [rbp-21h] BYREF

  *(_QWORD *)this = &wmi::RefBase::`vftable';
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &EvtFile::`vftable';
  v17 = *a2;
  v18 = a2[1];
  v3 = (LPCWSTR *)((char *)this + 16);
  MakeOrThrowOOM((char *)this + 16);
  v4 = (HANDLE *)((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 15) = &Buffer::`vftable';
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_BYTE *)this + 144) = 1;
  Buffer::SetSize((EvtFile *)((char *)this + 120), 0);
  *((_DWORD *)this + 35) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_BYTE *)this + 188) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_e3af4676036537576a7293a29544b610_Traceguids, *v3);
  }
  v5 = RpcImpersonateClient(0);
  v6 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_e3af4676036537576a7293a29544b610_Traceguids, v5);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v20 = 0;
    v21 = v6;
    v22 = -1;
    v23 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  FileW = CreateFileW(*v3, 0x80000000, 1u, 0, 3u, 0x10000000u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 48, FileW);
  RpcRevertToSelf();
  if ( (unsigned __int64)*v4 + 1 <= 1 )
  {
    LastError = GetLastError();
    v9 = LastError;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)&WPP_e3af4676036537576a7293a29544b610_Traceguids,
        (unsigned int)*v3,
        LastError);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !v9 )
      v9 = 1287;
    if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x200) != 0 && *((_BYTE *)v10 + 25) >= 2u )
      WPP_SF_d(v10[2], 30, &WPP_e3af4676036537576a7293a29544b610_Traceguids, v9);
    pExceptionObject = 0;
    v20 = 0;
    v21 = v9;
    v22 = 0x1EAFFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  FileMappingW = CreateFileMappingW(*v4, 0, 2u, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 56, FileMappingW);
  if ( *((_QWORD *)this + 7) == -1 || *((_QWORD *)this + 7) == 0 )
  {
    v12 = GetLastError();
    if ( !v12 )
      v12 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_e3af4676036537576a7293a29544b610_Traceguids, v12);
    }
    pExceptionObject = 0;
    v20 = 0;
    v21 = v12;
    v22 = 0x1FAFFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  *((_QWORD *)this + 20) = EvtFile::GetFileSize(this);
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  *((_DWORD *)this + 46) = SystemInfo.dwAllocationGranularity;
  if ( !EvtFile::Seek(this, 0, 0x30u) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_e3af4676036537576a7293a29544b610_Traceguids, 13);
    }
    pExceptionObject = 0;
    v20 = 0;
    v21 = 13;
    v22 = 0x211FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  v13 = (_OWORD *)*((_QWORD *)this + 8);
  *(_OWORD *)((char *)this + 72) = *v13;
  *(_OWORD *)((char *)this + 88) = v13[1];
  *(_OWORD *)((char *)this + 104) = v13[2];
  v17 = this;
  LOBYTE(v18) = 1;
  if ( *((_DWORD *)this + 18) != 48
    || *((_DWORD *)this + 29) != 48
    || *((_DWORD *)this + 19) != 1699505740
    || *((_DWORD *)this + 20) != 1 )
  {
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_e3af4676036537576a7293a29544b610_Traceguids, *v3);
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x200) != 0 && *((_BYTE *)v16 + 25) >= 2u )
        WPP_SF_d(v16[2], 34, &WPP_e3af4676036537576a7293a29544b610_Traceguids, 13);
    }
    pExceptionObject = 0;
    v20 = 0;
    v21 = 13;
    v22 = 0x22AFFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (*((_BYTE *)this + 108) & 1) != 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_e3af4676036537576a7293a29544b610_Traceguids, *v3);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x200) != 0 && *((_BYTE *)v14 + 25) >= 2u )
        WPP_SF_d(v14[2], 36, &WPP_e3af4676036537576a7293a29544b610_Traceguids, 13);
    }
    pExceptionObject = 0;
    v20 = 0;
    v21 = 13;
    v22 = 0x236FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  LOBYTE(v18) = 0;
  tlx::_UndoSolo__EvtFile::EvtFile_::_2_::_lambda_2___::__UndoSolo__EvtFile::EvtFile_::_2_::_lambda_2___(&v17);
  return this;
}

```

## disassembly

```asm
0x1800b6088  mov     [rsp-8+arg_0], rcx
0x1800b608d  push    rbp
0x1800b608e  push    rbx
0x1800b608f  push    rsi
0x1800b6090  push    rdi
0x1800b6091  push    r12
0x1800b6093  push    r13
0x1800b6095  push    r14
0x1800b6097  push    r15
0x1800b6099  lea     rbp, [rsp-1Fh]
0x1800b609e  sub     rsp, 0B8h
0x1800b60a5  mov     rdi, rcx
0x1800b60a8  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x1800b60af  mov     [rcx], rax
0x1800b60b2  xor     r12d, r12d
0x1800b60b5  mov     [rcx+8], r12d
0x1800b60b9  lea     rax, ??_7EvtFile@@6B@; const EvtFile::`vftable'
0x1800b60c0  mov     [rcx], rax
0x1800b60c3  mov     rax, [rdx]
0x1800b60c6  mov     [rbp+57h+var_B0], rax
0x1800b60ca  mov     rax, [rdx+8]
0x1800b60ce  mov     [rbp+57h+var_A8], rax
0x1800b60d2  lea     rsi, [rcx+10h]
0x1800b60d6  lea     rdx, [rbp+57h+var_B0]
0x1800b60da  mov     rcx, rsi
0x1800b60dd  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800b60e2  nop
0x1800b60e3  lea     r14, [rdi+30h]
0x1800b60e7  mov     [r14], r12
0x1800b60ea  lea     r15, [rdi+38h]
0x1800b60ee  mov     [r15], r12
0x1800b60f1  mov     [rdi+40h], r12
0x1800b60f5  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x1800b60fc  mov     [rdi+78h], rax
0x1800b6100  mov     [rdi+80h], r12
0x1800b6107  mov     [rdi+88h], r12
0x1800b610e  mov     byte ptr [rdi+90h], 1
0x1800b6115  xor     edx, edx; unsigned int
0x1800b6117  lea     rcx, [rdi+78h]; this
0x1800b611b  call    ?SetSize@Buffer@@QEAAXK@Z; Buffer::SetSize(ulong)
0x1800b6120  nop
0x1800b6121  mov     [rdi+8Ch], r12d
0x1800b6128  mov     [rdi+98h], r12
0x1800b612f  mov     [rdi+0A0h], r12
0x1800b6136  mov     [rdi+0A8h], r12
0x1800b613d  mov     [rdi+0B0h], r12
0x1800b6144  mov     [rdi+0BCh], r12b
0x1800b614b  lea     rax, WPP_GLOBAL_Control
0x1800b6152  mov     r13d, 200h
0x1800b6158  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b615f  cmp     rcx, rax
0x1800b6162  jz      short loc_1800B6188
0x1800b6164  test    [rcx+1Ch], r13d
0x1800b6168  jz      short loc_1800B6188
0x1800b616a  cmp     byte ptr [rcx+19h], 5
0x1800b616e  jb      short loc_1800B6188
0x1800b6170  lea     edx, [r12+1Bh]
0x1800b6175  mov     r9, [rsi]
0x1800b6178  lea     r8, WPP_e3af4676036537576a7293a29544b610_Traceguids
0x1800b617f  mov     rcx, [rcx+10h]
0x1800b6183  call    WPP_SF_S
0x1800b6188  xor     ecx, ecx; BindingHandle
0x1800b618a  call    cs:__imp_RpcImpersonateClient
0x1800b6190  mov     ebx, eax
0x1800b6192  test    eax, eax
0x1800b6194  jz      short loc_1800B6200
0x1800b6196  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b619d  lea     rdi, WPP_GLOBAL_Control
0x1800b61a4  cmp     rcx, rdi
0x1800b61a7  jz      short loc_1800B61CD
0x1800b61a9  test    [rcx+1Ch], r13d
0x1800b61ad  jz      short loc_1800B61CD
0x1800b61af  cmp     byte ptr [rcx+19h], 2
0x1800b61b3  jb      short loc_1800B61CD
0x1800b61b5  mov     edx, 1Ch
0x1800b61ba  mov     r9d, eax
0x1800b61bd  lea     r8, WPP_e3af4676036537576a7293a29544b610_Traceguids
0x1800b61c4  mov     rcx, [rcx+10h]
0x1800b61c8  call    WPP_SF_d
0x1800b61cd  lea     rax, byte_1800EC961
0x1800b61d4  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x1800b61d8  mov     qword ptr [rbp+57h+pExceptionObject+8], r12
0x1800b61dc  mov     [rbp+57h+var_90], r12
0x1800b61e0  mov     [rbp+57h+var_88], ebx
0x1800b61e3  mov     [rbp+57h+var_84], 0FFFFFFFFFFFFFFFFh
0x1800b61eb  mov     [rbp+57h+var_7C], r12b
0x1800b61ef  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b61f6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800b61fa  call    _CxxThrowException_0
0x1800b6200  mov     [rsp+0F0h+hTemplateFile], r12; hTemplateFile
0x1800b6205  mov     [rsp+0F0h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x1800b620d  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800b6215  xor     r9d, r9d; lpSecurityAttributes
0x1800b6218  mov     edx, 80000000h; dwDesiredAccess
0x1800b621d  lea     r8d, [r9+1]; dwShareMode
0x1800b6221  mov     rcx, [rsi]; lpFileName
0x1800b6224  call    cs:__imp_CreateFileW
0x1800b622a  mov     rdx, rax
0x1800b622d  mov     rcx, r14
0x1800b6230  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800b6235  call    cs:__imp_RpcRevertToSelf
0x1800b623b  mov     rcx, [r14]; hFile
0x1800b623e  lea     rax, [rcx+1]
0x1800b6242  cmp     rax, 1
0x1800b6246  ja      loc_1800B62F7
0x1800b624c  call    cs:__imp_GetLastError
0x1800b6252  mov     ebx, eax
0x1800b6254  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b625b  lea     rdi, WPP_GLOBAL_Control
0x1800b6262  cmp     rcx, rdi
0x1800b6265  jz      short loc_1800B6296
0x1800b6267  test    [rcx+1Ch], r13d
0x1800b626b  jz      short loc_1800B6296
0x1800b626d  cmp     byte ptr [rcx+19h], 2
0x1800b6271  jb      short loc_1800B6296
0x1800b6273  mov     edx, 1Dh
0x1800b6278  mov     [rsp+0F0h+dwCreationDisposition], eax
0x1800b627c  mov     r9, [rsi]
0x1800b627f  lea     r8, WPP_e3af4676036537576a7293a29544b610_Traceguids
0x1800b6286  mov     rcx, [rcx+10h]
0x1800b628a  call    WPP_SF_Sd
0x1800b628f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6296  mov     eax, 507h
0x1800b629b  test    ebx, ebx
0x1800b629d  cmovz   ebx, eax
0x1800b62a0  cmp     rcx, rdi
0x1800b62a3  jz      short loc_1800B62C9
0x1800b62a5  test    [rcx+1Ch], r13d
0x1800b62a9  jz      short loc_1800B62C9
0x1800b62ab  cmp     byte ptr [rcx+19h], 2
0x1800b62af  jb      short loc_1800B62C9
0x1800b62b1  mov     edx, 1Eh
0x1800b62b6  mov     r9d, ebx
0x1800b62b9  lea     r8, WPP_e3af4676036537576a7293a29544b610_Traceguids
0x1800b62c0  mov     rcx, [rcx+10h]
0x1800b62c4  call    WPP_SF_d
0x1800b62c9  xorps   xmm0, xmm0
0x1800b62cc  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800b62d1  mov     [rbp+57h+var_90], r12
0x1800b62d5  mov     [rbp+57h+var_88], ebx
0x1800b62d8  mov     dword ptr [rbp+57h+var_84], 0FFFFFFFFh
0x1800b62df  mov     dword ptr [rbp+57h+var_84+4], 1EAh
0x1800b62e6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b62ed  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800b62f1  call    _CxxThrowException_0
0x1800b62f7  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], r12; lpName
0x1800b62fc  mov     [rsp+0F0h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x1800b6301  xor     r9d, r9d; dwMaximumSizeHigh
0x1800b6304  xor     edx, edx; lpFileMappingAttributes
0x1800b6306  lea     r8d, [r9+2]; flProtect
0x1800b630a  call    cs:__imp_CreateFileMappingW
0x1800b6310  mov     rdx, rax
0x1800b6313  mov     rcx, r15
0x1800b6316  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800b631b  mov     rax, [r15]
0x1800b631e  inc     rax
0x1800b6321  cmp     rax, 1
0x1800b6325  ja      short loc_1800B639E
0x1800b6327  call    cs:__imp_GetLastError
0x1800b632d  mov     ebx, eax
0x1800b632f  mov     eax, 507h
0x1800b6334  test    ebx, ebx
0x1800b6336  cmovz   ebx, eax
0x1800b6339  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6340  lea     rdi, WPP_GLOBAL_Control
0x1800b6347  cmp     rcx, rdi
0x1800b634a  jz      short loc_1800B6370
0x1800b634c  test    [rcx+1Ch], r13d
0x1800b6350  jz      short loc_1800B6370
0x1800b6352  cmp     byte ptr [rcx+19h], 2
0x1800b6356  jb      short loc_1800B6370
0x1800b6358  mov     edx, 1Fh
0x1800b635d  mov     r9d, ebx
0x1800b6360  lea     r8, WPP_e3af4676036537576a7293a29544b610_Traceguids
0x1800b6367  mov     rcx, [rcx+10h]
0x1800b636b  call    WPP_SF_d
0x1800b6370  xorps   xmm0, xmm0
0x1800b6373  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800b6378  mov     [rbp+57h+var_90], r12
0x1800b637c  mov     [rbp+57h+var_88], ebx
0x1800b637f  mov     dword ptr [rbp+57h+var_84], 0FFFFFFFFh
0x1800b6386  mov     dword ptr [rbp+57h+var_84+4], 1FAh
0x1800b638d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b6394  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800b6398  call    _CxxThrowException_0
0x1800b639e  mov     rcx, rdi; this
0x1800b63a1  call    ?GetFileSize@EvtFile@@AEAA_KXZ; EvtFile::GetFileSize(void)
0x1800b63a6  mov     [rdi+0A0h], rax
0x1800b63ad  xorps   xmm0, xmm0
0x1800b63b0  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x1800b63b4  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800b63b8  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800b63bc  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x1800b63c0  call    cs:__imp_GetSystemInfo
0x1800b63c6  mov     eax, [rbp+57h+SystemInfo.dwAllocationGranularity]
0x1800b63c9  mov     [rdi+0B8h], eax
0x1800b63cf  xor     edx, edx; unsigned __int64
0x1800b63d1  lea     r8d, [rdx+30h]; unsigned __int64
0x1800b63d5  mov     rcx, rdi; this
0x1800b63d8  call    ?Seek@EvtFile@@AEAAPEAE_K0@Z; EvtFile::Seek(unsigned __int64,unsigned __int64)
0x1800b63dd  test    rax, rax
0x1800b63e0  jnz     short loc_1800B6448
0x1800b63e2  lea     ebx, [rax+0Dh]
0x1800b63e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b63ec  lea     rdi, WPP_GLOBAL_Control
0x1800b63f3  cmp     rcx, rdi
0x1800b63f6  jz      short loc_1800B641A
0x1800b63f8  test    [rcx+1Ch], r13d
0x1800b63fc  jz      short loc_1800B641A
0x1800b63fe  cmp     byte ptr [rcx+19h], 2
0x1800b6402  jb      short loc_1800B641A
0x1800b6404  lea     edx, [rax+20h]
0x1800b6407  mov     r9d, ebx
0x1800b640a  lea     r8, WPP_e3af4676036537576a7293a29544b610_Traceguids
0x1800b6411  mov     rcx, [rcx+10h]
0x1800b6415  call    WPP_SF_d
0x1800b641a  xorps   xmm0, xmm0
0x1800b641d  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800b6422  mov     [rbp+57h+var_90], r12
0x1800b6426  mov     [rbp+57h+var_88], ebx
0x1800b6429  mov     dword ptr [rbp+57h+var_84], 0FFFFFFFFh
0x1800b6430  mov     dword ptr [rbp+57h+var_84+4], 211h
0x1800b6437  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b643e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800b6442  call    _CxxThrowException_0
0x1800b6448  mov     rax, [rdi+40h]
0x1800b644c  movups  xmm0, xmmword ptr [rax]
0x1800b644f  movups  xmmword ptr [rdi+48h], xmm0
0x1800b6453  movups  xmm1, xmmword ptr [rax+10h]
0x1800b6457  movups  xmmword ptr [rdi+58h], xmm1
0x1800b645b  movups  xmm0, xmmword ptr [rax+20h]
0x1800b645f  movups  xmmword ptr [rdi+68h], xmm0
0x1800b6463  mov     [rbp+57h+var_B0], rdi
0x1800b6467  mov     byte ptr [rbp+57h+var_A8], 1
0x1800b646b  cmp     dword ptr [rdi+48h], 30h ; '0'
0x1800b646f  jnz     loc_1800B655D
0x1800b6475  cmp     dword ptr [rdi+74h], 30h ; '0'
0x1800b6479  jnz     loc_1800B655D
0x1800b647f  cmp     dword ptr [rdi+4Ch], 654C664Ch
0x1800b6486  jnz     loc_1800B655D
0x1800b648c  cmp     dword ptr [rdi+50h], 1
0x1800b6490  jnz     loc_1800B655D
0x1800b6496  test    byte ptr [rdi+6Ch], 1
0x1800b649a  jz      loc_1800B6538
0x1800b64a0  mov     ebx, 0Dh
0x1800b64a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b64ac  lea     rdi, WPP_GLOBAL_Control
0x1800b64b3  cmp     rcx, rdi
0x1800b64b6  jz      short loc_1800B650A
0x1800b64b8  test    [rcx+1Ch], r13d
0x1800b64bc  jz      short loc_1800B64E1
0x1800b64be  cmp     byte ptr [rcx+19h], 3
0x1800b64c2  jb      short loc_1800B64E1
0x1800b64c4  lea     edx, [rbx+16h]
0x1800b64c7  mov     r9, [rsi]
0x1800b64ca  lea     r8, WPP_e3af4676036537576a7293a29544b610_Traceguids
0x1800b64d1  mov     rcx, [rcx+10h]
0x1800b64d5  call    WPP_SF_S
0x1800b64da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b64e1  cmp     rcx, rdi
0x1800b64e4  jz      short loc_1800B650A
0x1800b64e6  test    [rcx+1Ch], r13d
0x1800b64ea  jz      short loc_1800B650A
0x1800b64ec  cmp     byte ptr [rcx+19h], 2
0x1800b64f0  jb      short loc_1800B650A
0x1800b64f2  mov     edx, 24h ; '$'
0x1800b64f7  mov     r9d, ebx
0x1800b64fa  lea     r8, WPP_e3af4676036537576a7293a29544b610_Traceguids
0x1800b6501  mov     rcx, [rcx+10h]
0x1800b6505  call    WPP_SF_d
0x1800b650a  xorps   xmm0, xmm0
0x1800b650d  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800b6512  mov     [rbp+57h+var_90], r12
0x1800b6516  mov     [rbp+57h+var_88], ebx
0x1800b6519  mov     dword ptr [rbp+57h+var_84], 0FFFFFFFFh
0x1800b6520  mov     dword ptr [rbp+57h+var_84+4], 236h
0x1800b6527  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b652e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800b6532  call    _CxxThrowException_0
0x1800b6538  mov     byte ptr [rbp+57h+var_A8], r12b
0x1800b653c  lea     rcx, [rbp+57h+var_B0]
0x1800b6540  call    tlx___UndoSolo__EvtFile__EvtFile____2____lambda_2_______UndoSolo__EvtFile__EvtFile____2____lambda_2___
0x1800b6545  nop
0x1800b6546  mov     rax, rdi
0x1800b6549  add     rsp, 0B8h
0x1800b6550  pop     r15
0x1800b6552  pop     r14
0x1800b6554  pop     r13
0x1800b6556  pop     r12
0x1800b6558  pop     rdi
0x1800b6559  pop     rsi
0x1800b655a  pop     rbx
0x1800b655b  pop     rbp
0x1800b655c  retn
0x1800b655d  mov     ebx, 0Dh
0x1800b6562  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6569  lea     rdi, WPP_GLOBAL_Control
0x1800b6570  cmp     rcx, rdi
0x1800b6573  jz      short loc_1800B65C7
0x1800b6575  test    [rcx+1Ch], r13d
  ... truncated ...
```
