# ReadTextFile(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x14001d38c`
- end: `0x14001d820`
- name: `?ReadTextFile@@YAXPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `1172`
- prototype: `__int64 __fastcall(wchar_t *Src)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14001c6b0`
- `0x14001cfd0`

## callees

- `0x140002bd0`
- `0x140010450`
- `0x140015898`
- `0x1400165d4`
- `0x14001c368`
- `0x14001c510`
- `0x14001d38c`
- `0x140022cec`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d3ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d4ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d79d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d3ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d4ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d79d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14001d47b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14001d47b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001d3cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001d3cf`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14001d4bc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14001d4bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ReadTextFile(wchar_t *Src, __int64 a2)
{
  HANDLE FileW; // rax
  void *v5; // rdi
  DWORD LastError; // ebx
  DWORD FileSize; // eax
  _BYTE *v8; // rbx
  DWORD v9; // ebx
  unsigned __int64 v10; // r8
  _BYTE *v11; // rdx
  DWORD v13; // edi
  const char *dwCreationDisposition; // [rsp+28h] [rbp-29h]
  const char *dwCreationDispositiona; // [rsp+28h] [rbp-29h]
  _BYTE *v16; // [rsp+48h] [rbp-9h] BYREF
  HANDLE v17; // [rsp+50h] [rbp-1h] BYREF
  _BYTE *v18; // [rsp+58h] [rbp+7h] BYREF
  __int64 v19; // [rsp+60h] [rbp+Fh]
  _BYTE pExceptionObject[48]; // [rsp+68h] [rbp+17h] BYREF
  DWORD nNumberOfBytesToRead; // [rsp+C8h] [rbp+77h] BYREF
  DWORD FileSizeHigh; // [rsp+D0h] [rbp+7Fh] BYREF

  FileW = CreateFileW(Src, 0x80000000, 1u, 0, 3u, 0, 0);
  v5 = FileW;
  v17 = FileW;
  if ( (unsigned __int64)FileW + 1 <= 1 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids, LastError);
    }
    EvtException::EvtException(
      (EvtException *)pExceptionObject,
      LastError,
      0,
      0,
      dwCreationDisposition,
      135,
      0x41u,
      Src);
    throw (EvtException *)pExceptionObject;
  }
  FileSizeHigh = 0;
  FileSize = GetFileSize(FileW, &FileSizeHigh);
  nNumberOfBytesToRead = FileSize;
  if ( FileSize == -1 || FileSizeHigh )
  {
    v13 = GetLastError();
    if ( !v13 )
      v13 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids, v13);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v13, 0, 0, dwCreationDisposition, 143, 0x41u, Src);
    throw (EvtException *)pExceptionObject;
  }
  v8 = operator new(FileSize);
  v16 = v8;
  if ( !ReadFile(v5, v8, nNumberOfBytesToRead, &nNumberOfBytesToRead, 0) )
  {
    v9 = GetLastError();
    if ( !v9 )
      v9 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids, v9);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v9, 0, 0, dwCreationDispositiona, 150, 0x41u, Src);
    throw (EvtException *)pExceptionObject;
  }
  if ( nNumberOfBytesToRead >= 2 && *v8 == 0xFF && v8[1] == 0xFE )
  {
    if ( (nNumberOfBytesToRead & 1) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, 0, 0, dwCreationDispositiona, 159, 0x41u, Src);
      throw (EvtException *)pExceptionObject;
    }
    v10 = nNumberOfBytesToRead - 2;
    v11 = v8 + 2;
    goto LABEL_45;
  }
  if ( nNumberOfBytesToRead >= 3 && *v8 == 0xEF && v8[1] == 0xBB && v8[2] == 0xBF )
  {
    v18 = v8 + 3;
    v19 = nNumberOfBytesToRead - 3;
    if ( (int)tlx::assign_mbcs<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,std::string_view,char,0>(
                a2,
                &v18,
                65001) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, 0, 0, dwCreationDispositiona, 172, 0x41u, Src);
      throw (EvtException *)pExceptionObject;
    }
  }
  else
  {
    if ( nNumberOfBytesToRead >= 4 && *v8 == 60 && !v8[1] && v8[2] == 63 && !v8[3] )
    {
      v10 = nNumberOfBytesToRead;
      v11 = v8;
LABEL_45:
      std::wstring::_Assign<wchar_t>(a2, v11, v10 >> 1);
      goto LABEL_46;
    }
    v18 = v8;
    v19 = nNumberOfBytesToRead;
    if ( (int)tlx::assign_mbcs<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,std::string_view,char,0>(
                a2,
                &v18,
                0) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, 0, 0, dwCreationDispositiona, 188, 0x41u, Src);
      throw (EvtException *)pExceptionObject;
    }
  }
LABEL_46:
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&v16);
  return tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v17);
}

```

## disassembly

```asm
0x14001d38c  mov     rax, rsp
0x14001d38f  mov     [rax+8], rbx
0x14001d393  mov     [rax+10h], rsi
0x14001d397  push    rbp
0x14001d398  push    rdi
0x14001d399  push    r14
0x14001d39b  lea     rbp, [rax-5Fh]
0x14001d39f  sub     rsp, 90h
0x14001d3a6  mov     r14, rdx
0x14001d3a9  mov     rsi, rcx
0x14001d3ac  mov     qword ptr [rax-78h], 0
0x14001d3b4  mov     dword ptr [rax-80h], 0
0x14001d3bb  mov     dword ptr [rsp+0A0h+dwCreationDisposition], 3; char *
0x14001d3c3  xor     r9d, r9d; lpSecurityAttributes
0x14001d3c6  mov     edx, 80000000h; dwDesiredAccess
0x14001d3cb  lea     r8d, [r9+1]; dwShareMode
0x14001d3cf  call    cs:__imp_CreateFileW
0x14001d3d5  mov     rdi, rax
0x14001d3d8  mov     [rbp+57h+var_58], rax
0x14001d3dc  lea     rcx, [rax+1]
0x14001d3e0  cmp     rcx, 1
0x14001d3e4  ja      loc_14001D46D
0x14001d3ea  call    cs:__imp_GetLastError
0x14001d3f0  mov     ebx, eax
0x14001d3f2  mov     eax, 507h
0x14001d3f7  test    ebx, ebx
0x14001d3f9  cmovz   ebx, eax
0x14001d3fc  lea     rax, WPP_GLOBAL_Control
0x14001d403  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d40a  cmp     rcx, rax
0x14001d40d  jz      short loc_14001D436
0x14001d40f  test    dword ptr [rcx+1Ch], 400000h
0x14001d416  jz      short loc_14001D436
0x14001d418  cmp     byte ptr [rcx+19h], 2
0x14001d41c  jb      short loc_14001D436
0x14001d41e  mov     edx, 0Ch
0x14001d423  mov     r9d, ebx
0x14001d426  lea     r8, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids
0x14001d42d  mov     rcx, [rcx+10h]
0x14001d431  call    WPP_SF_d
0x14001d436  mov     [rsp+0A0h+Src], rsi; Src
0x14001d43b  mov     [rsp+0A0h+var_70], 41h ; 'A'; unsigned int
0x14001d443  mov     [rsp+0A0h+var_78], 87h; int
0x14001d44b  xor     r9d, r9d; unsigned int
0x14001d44e  xor     r8d, r8d; unsigned int
0x14001d451  mov     edx, ebx; unsigned int
0x14001d453  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14001d457  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001d45c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001d463  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001d467  call    _CxxThrowException_0
0x14001d46d  mov     [rbp+57h+FileSizeHigh], 0
0x14001d474  lea     rdx, [rbp+57h+FileSizeHigh]; lpFileSizeHigh
0x14001d478  mov     rcx, rdi; hFile
0x14001d47b  call    cs:__imp_GetFileSize
0x14001d481  mov     [rbp+57h+nNumberOfBytesToRead], eax
0x14001d484  cmp     eax, 0FFFFFFFFh
0x14001d487  jz      loc_14001D79D
0x14001d48d  cmp     [rbp+57h+FileSizeHigh], 0
0x14001d491  jnz     loc_14001D79D
0x14001d497  mov     ecx, eax; dwBytes
0x14001d499  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d49e  mov     rbx, rax
0x14001d4a1  mov     [rbp+57h+var_60], rax
0x14001d4a5  mov     [rsp+0A0h+dwCreationDisposition], 0; char *
0x14001d4ae  lea     r9, [rbp+57h+nNumberOfBytesToRead]; lpNumberOfBytesRead
0x14001d4b2  mov     r8d, [rbp+57h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x14001d4b6  mov     rdx, rax; lpBuffer
0x14001d4b9  mov     rcx, rdi; hFile
0x14001d4bc  call    cs:__imp_ReadFile
0x14001d4c2  test    eax, eax
0x14001d4c4  jnz     loc_14001D54D
0x14001d4ca  call    cs:__imp_GetLastError
0x14001d4d0  mov     ebx, eax
0x14001d4d2  mov     eax, 507h
0x14001d4d7  test    ebx, ebx
0x14001d4d9  cmovz   ebx, eax
0x14001d4dc  lea     rax, WPP_GLOBAL_Control
0x14001d4e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d4ea  cmp     rcx, rax
0x14001d4ed  jz      short loc_14001D516
0x14001d4ef  test    dword ptr [rcx+1Ch], 400000h
0x14001d4f6  jz      short loc_14001D516
0x14001d4f8  cmp     byte ptr [rcx+19h], 2
0x14001d4fc  jb      short loc_14001D516
0x14001d4fe  mov     edx, 0Eh
0x14001d503  mov     r9d, ebx
0x14001d506  lea     r8, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids
0x14001d50d  mov     rcx, [rcx+10h]
0x14001d511  call    WPP_SF_d
0x14001d516  mov     [rsp+0A0h+Src], rsi; Src
0x14001d51b  mov     [rsp+0A0h+var_70], 41h ; 'A'; unsigned int
0x14001d523  mov     [rsp+0A0h+var_78], 96h; int
0x14001d52b  xor     r9d, r9d; unsigned int
0x14001d52e  xor     r8d, r8d; unsigned int
0x14001d531  mov     edx, ebx; unsigned int
0x14001d533  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14001d537  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001d53c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001d543  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001d547  call    _CxxThrowException_0
0x14001d54d  mov     ecx, [rbp+57h+nNumberOfBytesToRead]
0x14001d550  cmp     ecx, 2
0x14001d553  jb      loc_14001D5F2
0x14001d559  cmp     byte ptr [rbx], 0FFh
0x14001d55c  jnz     loc_14001D5F2
0x14001d562  cmp     byte ptr [rbx+1], 0FEh
0x14001d566  jnz     loc_14001D5F2
0x14001d56c  test    cl, 1
0x14001d56f  jz      short loc_14001D5E5
0x14001d571  lea     rax, WPP_GLOBAL_Control
0x14001d578  mov     ebx, 0Dh
0x14001d57d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d584  cmp     rcx, rax
0x14001d587  jz      short loc_14001D5AE
0x14001d589  test    dword ptr [rcx+1Ch], 400000h
0x14001d590  jz      short loc_14001D5AE
0x14001d592  cmp     byte ptr [rcx+19h], 2
0x14001d596  jb      short loc_14001D5AE
0x14001d598  lea     edx, [rbx+2]
0x14001d59b  mov     r9d, ebx
0x14001d59e  lea     r8, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids
0x14001d5a5  mov     rcx, [rcx+10h]
0x14001d5a9  call    WPP_SF_d
0x14001d5ae  mov     [rsp+0A0h+Src], rsi; Src
0x14001d5b3  mov     [rsp+0A0h+var_70], 41h ; 'A'; unsigned int
0x14001d5bb  mov     [rsp+0A0h+var_78], 9Fh; int
0x14001d5c3  xor     r9d, r9d; unsigned int
0x14001d5c6  xor     r8d, r8d; unsigned int
0x14001d5c9  mov     edx, ebx; unsigned int
0x14001d5cb  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14001d5cf  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001d5d4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001d5db  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001d5df  call    _CxxThrowException_0
0x14001d5e5  lea     r8d, [rcx-2]
0x14001d5e9  lea     rdx, [rbx+2]
0x14001d5ed  jmp     loc_14001D6D7
0x14001d5f2  cmp     ecx, 3
0x14001d5f5  jb      loc_14001D6B5
0x14001d5fb  cmp     byte ptr [rbx], 0EFh
0x14001d5fe  jnz     loc_14001D6B5
0x14001d604  cmp     byte ptr [rbx+1], 0BBh
0x14001d608  jnz     loc_14001D6B5
0x14001d60e  cmp     byte ptr [rbx+2], 0BFh
0x14001d612  jnz     loc_14001D6B5
0x14001d618  lea     rax, [rbx+3]
0x14001d61c  mov     [rbp+57h+var_50], rax
0x14001d620  add     ecx, 0FFFFFFFDh
0x14001d623  mov     [rbp+57h+var_48], rcx
0x14001d627  mov     r8d, 0FDE9h
0x14001d62d  lea     rdx, [rbp+57h+var_50]
0x14001d631  mov     rcx, r14
0x14001d634  call    ??$assign_mbcs@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V?$basic_string_view@DU?$char_traits@D@std@@@2@D$0A@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@DU?$char_traits@D@std@@@2@II@Z; tlx::assign_mbcs<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,std::string_view,char,0>(std::wstring &,std::string_view const &,uint,uint)
0x14001d639  test    eax, eax
0x14001d63b  jns     loc_14001D6E3
0x14001d641  lea     rax, WPP_GLOBAL_Control
0x14001d648  mov     ebx, 0Dh
0x14001d64d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d654  cmp     rcx, rax
0x14001d657  jz      short loc_14001D67E
0x14001d659  test    dword ptr [rcx+1Ch], 400000h
0x14001d660  jz      short loc_14001D67E
0x14001d662  cmp     byte ptr [rcx+19h], 2
0x14001d666  jb      short loc_14001D67E
0x14001d668  lea     edx, [rbx+3]
0x14001d66b  mov     r9d, ebx
0x14001d66e  lea     r8, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids
0x14001d675  mov     rcx, [rcx+10h]
0x14001d679  call    WPP_SF_d
0x14001d67e  mov     [rsp+0A0h+Src], rsi; Src
0x14001d683  mov     [rsp+0A0h+var_70], 41h ; 'A'; unsigned int
0x14001d68b  mov     [rsp+0A0h+var_78], 0ACh; int
0x14001d693  xor     r9d, r9d; unsigned int
0x14001d696  xor     r8d, r8d; unsigned int
0x14001d699  mov     edx, ebx; unsigned int
0x14001d69b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14001d69f  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001d6a4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001d6ab  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001d6af  call    _CxxThrowException_0
0x14001d6b5  cmp     ecx, 4
0x14001d6b8  jb      short loc_14001D70E
0x14001d6ba  cmp     byte ptr [rbx], 3Ch ; '<'
0x14001d6bd  jnz     short loc_14001D70E
0x14001d6bf  cmp     byte ptr [rbx+1], 0
0x14001d6c3  jnz     short loc_14001D70E
0x14001d6c5  cmp     byte ptr [rbx+2], 3Fh ; '?'
0x14001d6c9  jnz     short loc_14001D70E
0x14001d6cb  cmp     byte ptr [rbx+3], 0
0x14001d6cf  jnz     short loc_14001D70E
0x14001d6d1  mov     r8, rcx
0x14001d6d4  mov     rdx, rbx
0x14001d6d7  shr     r8, 1
0x14001d6da  mov     rcx, r14
0x14001d6dd  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x14001d6e2  nop
0x14001d6e3  lea     rcx, [rbp+57h+var_60]
0x14001d6e7  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x14001d6ec  nop
0x14001d6ed  lea     rcx, [rbp+57h+var_58]
0x14001d6f1  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x14001d6f6  lea     r11, [rsp+0A0h+var_10]
0x14001d6fe  mov     rbx, [r11+20h]
0x14001d702  mov     rsi, [r11+28h]
0x14001d706  mov     rsp, r11
0x14001d709  pop     r14
0x14001d70b  pop     rdi
0x14001d70c  pop     rbp
0x14001d70d  retn
0x14001d70e  mov     [rbp+57h+var_50], rbx
0x14001d712  mov     [rbp+57h+var_48], rcx
0x14001d716  xor     r8d, r8d
0x14001d719  lea     rdx, [rbp+57h+var_50]
0x14001d71d  mov     rcx, r14
0x14001d720  call    ??$assign_mbcs@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V?$basic_string_view@DU?$char_traits@D@std@@@2@D$0A@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@DU?$char_traits@D@std@@@2@II@Z; tlx::assign_mbcs<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,std::string_view,char,0>(std::wstring &,std::string_view const &,uint,uint)
0x14001d725  test    eax, eax
0x14001d727  jns     short loc_14001D6E3
0x14001d729  lea     rax, WPP_GLOBAL_Control
0x14001d730  mov     ebx, 0Dh
0x14001d735  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d73c  cmp     rcx, rax
0x14001d73f  jz      short loc_14001D766
0x14001d741  test    dword ptr [rcx+1Ch], 400000h
0x14001d748  jz      short loc_14001D766
0x14001d74a  cmp     byte ptr [rcx+19h], 2
0x14001d74e  jb      short loc_14001D766
0x14001d750  lea     edx, [rbx+4]
0x14001d753  mov     r9d, ebx
0x14001d756  lea     r8, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids
0x14001d75d  mov     rcx, [rcx+10h]
0x14001d761  call    WPP_SF_d
0x14001d766  mov     [rsp+0A0h+Src], rsi; Src
0x14001d76b  mov     [rsp+0A0h+var_70], 41h ; 'A'; unsigned int
0x14001d773  mov     [rsp+0A0h+var_78], 0BCh; int
0x14001d77b  xor     r9d, r9d; unsigned int
0x14001d77e  xor     r8d, r8d; unsigned int
0x14001d781  mov     edx, ebx; unsigned int
0x14001d783  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14001d787  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001d78c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001d793  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001d797  call    _CxxThrowException_0
0x14001d79d  call    cs:__imp_GetLastError
0x14001d7a3  mov     edi, eax
0x14001d7a5  mov     eax, 507h
0x14001d7aa  test    edi, edi
0x14001d7ac  cmovz   edi, eax
0x14001d7af  lea     rax, WPP_GLOBAL_Control
0x14001d7b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d7bd  cmp     rcx, rax
0x14001d7c0  jz      short loc_14001D7E9
0x14001d7c2  test    dword ptr [rcx+1Ch], 400000h
0x14001d7c9  jz      short loc_14001D7E9
0x14001d7cb  cmp     byte ptr [rcx+19h], 2
0x14001d7cf  jb      short loc_14001D7E9
0x14001d7d1  mov     edx, 0Dh
0x14001d7d6  mov     r9d, edi
0x14001d7d9  lea     r8, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids
0x14001d7e0  mov     rcx, [rcx+10h]
0x14001d7e4  call    WPP_SF_d
0x14001d7e9  mov     [rsp+0A0h+Src], rsi; Src
0x14001d7ee  mov     [rsp+0A0h+var_70], 41h ; 'A'; unsigned int
0x14001d7f6  mov     [rsp+0A0h+var_78], 8Fh; int
0x14001d7fe  xor     r9d, r9d; unsigned int
0x14001d801  xor     r8d, r8d; unsigned int
0x14001d804  mov     edx, edi; unsigned int
0x14001d806  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14001d80a  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001d80f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001d816  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001d81a  call    _CxxThrowException_0
```
