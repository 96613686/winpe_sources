# CIniParser::WriteToFile(wchar_t const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18000fc28`
- end: `0x1800100fd`
- name: `?WriteToFile@CIniParser@@QEAAJPEB_WPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `1237`
- prototype: `int(CIniParser *__hidden this, const wchar_t *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007756c`

## callees

- `0x180004c64`
- `0x180009464`
- `0x18000cf50`
- `0x18000e31c`
- `0x18000fc28`
- `0x180018000`
- `0x18001c368`
- `0x180020680`
- `0x18002a758`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800100d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800100d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010040`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000fff0`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000fff0`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000fd0f`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000fd0f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000fd6b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000fd6b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000fdbf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000fec4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000ffa4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000fdbf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000fec4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000ffa4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000fc96`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000fc96`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CIniParser::WriteToFile(CIniParser *this, const wchar_t *a2, struct _SECURITY_ATTRIBUTES *a3)
{
  CIniParser *v5; // r12
  unsigned int v6; // r13d
  HANDLE FileW; // rbx
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // esi
  wchar_t *v11; // rcx
  DWORD v12; // eax
  DWORD v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  CIniParser *v16; // rdi
  unsigned __int16 *v17; // rax
  int v18; // r8d
  unsigned __int16 *v19; // rcx
  int v20; // r12d
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // rcx
  DWORD v23; // eax
  DWORD v24; // eax
  DWORD v25; // eax
  DWORD LastError; // eax
  unsigned int v27; // eax
  int v29; // [rsp+40h] [rbp-30h]
  LPCVOID lpBuffer; // [rsp+48h] [rbp-28h] BYREF
  __int64 v31; // [rsp+50h] [rbp-20h]
  char v32; // [rsp+58h] [rbp-18h] BYREF
  __int16 Buffer; // [rsp+B8h] [rbp+48h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+C8h] [rbp+58h] BYREF

  v5 = this;
  v6 = 0;
  FileW = 0;
  NumberOfBytesWritten = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpBuffer);
  Buffer = 0;
  if ( a2 && *a2 )
  {
    FileW = CreateFileW(a2, 0x40000000u, 0, a3, 4u, 0x80u, 0);
    tlx::file_handle_traits::operator()(v8, 0);
    if ( (unsigned __int64)FileW + 1 <= 1 )
    {
      LastError = GetLastError();
      v27 = ERROR_HR_FROM_WIN32(LastError);
      v10 = v27;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids,
          (_DWORD)a2,
          v27);
    }
    else
    {
      v9 = UtilVerifyFilePath(a2, FileW);
      v10 = v9;
      if ( v9 >= 0 )
      {
        if ( !SetEndOfFile(FileW)
          && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          v12 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids, v12);
        }
        if ( !SetFileAttributesW(a2, 0x2000u)
          && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids);
        }
        Buffer = -257;
        if ( WriteFile(FileW, &Buffer, 2u, &NumberOfBytesWritten, 0) )
        {
          v16 = *(CIniParser **)v5;
          while ( v16 != v5 )
          {
            v17 = (unsigned __int16 *)*((_QWORD *)v16 + 2);
            v18 = 0;
            v19 = &v17[(__int64)(*((_QWORD *)v16 + 3) - (_QWORD)v17) >> 1];
            while ( v17 != v19 )
              v18 = *v17++ + 65599 * v18;
            v29 = v18;
            v20 = 0;
            v21 = (unsigned __int16 *)*((_QWORD *)v16 + 6);
            v22 = &v21[(__int64)(*((_QWORD *)v16 + 7) - (_QWORD)v21) >> 1];
            while ( v21 != v22 )
              v20 = *v21++ + 65599 * v20;
            v14 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                    &lpBuffer,
                    L"%ls=%ls\r\n",
                    *((_QWORD *)v16 + 2));
            v10 = v14;
            if ( v14 < 0 )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v15 = 16;
                goto LABEL_20;
              }
              goto LABEL_57;
            }
            if ( !WriteFile(FileW, lpBuffer, 2 * ((v31 - (__int64)lpBuffer) >> 1), &NumberOfBytesWritten, 0) )
            {
              v23 = GetLastError();
              v14 = ERROR_HR_FROM_WIN32(v23);
              v10 = v14;
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v15 = 17;
                goto LABEL_20;
              }
              goto LABEL_57;
            }
            v6 += v20 + v29;
            v16 = *(CIniParser **)v16;
            v5 = this;
          }
          v14 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  &lpBuffer,
                  L"MetadataHash=%ld",
                  v6);
          v10 = v14;
          if ( v14 >= 0 )
          {
            if ( WriteFile(FileW, lpBuffer, 2 * ((v31 - (__int64)lpBuffer) >> 1), &NumberOfBytesWritten, 0) )
            {
              if ( FlushFileBuffers(FileW) )
              {
                v10 = 0;
              }
              else
              {
                v25 = GetLastError();
                v14 = ERROR_HR_FROM_WIN32(v25);
                v10 = v14;
                v11 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  v15 = 20;
                  goto LABEL_20;
                }
              }
            }
            else
            {
              v24 = GetLastError();
              v14 = ERROR_HR_FROM_WIN32(v24);
              v10 = v14;
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v15 = 19;
                goto LABEL_20;
              }
            }
          }
          else
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v15 = 18;
              goto LABEL_20;
            }
          }
        }
        else
        {
          v13 = GetLastError();
          v14 = ERROR_HR_FROM_WIN32(v13);
          v10 = v14;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v15 = 15;
LABEL_20:
            WPP_SF_d(*((_QWORD *)v11 + 2), v15, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids, (unsigned int)v14);
          }
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids,
            (unsigned int)v9);
      }
    }
  }
  else
  {
    v10 = -2147024809;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids);
  }
LABEL_57:
  if ( lpBuffer != &v32 )
    HeapFree(g_hWerheap, 0, (LPVOID)lpBuffer);
  tlx::file_handle_traits::operator()(v11, FileW);
  return v10;
}

```

## disassembly

```asm
0x18000fc28  mov     [rsp-38h+arg_0], rcx
0x18000fc2d  push    rbp
0x18000fc2e  push    rbx
0x18000fc2f  push    rsi
0x18000fc30  push    rdi
0x18000fc31  push    r12
0x18000fc33  push    r13
0x18000fc35  push    r14
0x18000fc37  mov     rbp, rsp
0x18000fc3a  sub     rsp, 70h
0x18000fc3e  mov     rsi, r8
0x18000fc41  mov     rdi, rdx
0x18000fc44  mov     r12, rcx
0x18000fc47  xor     r13d, r13d
0x18000fc4a  mov     ebx, r13d
0x18000fc4d  mov     [rbp+NumberOfBytesWritten], r13d
0x18000fc51  lea     rcx, [rbp+lpBuffer]; void *
0x18000fc55  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18000fc5a  nop
0x18000fc5b  mov     [rbp+Buffer], r13w
0x18000fc60  test    rdi, rdi
0x18000fc63  jz      loc_18001008C
0x18000fc69  cmp     [rdi], r13w
0x18000fc6d  jz      loc_18001008C
0x18000fc73  mov     [rsp+70h+hTemplateFile], r13; hTemplateFile
0x18000fc78  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000fc80  mov     [rsp+70h+dwCreationDisposition], 4; dwCreationDisposition
0x18000fc88  mov     r9, rsi; lpSecurityAttributes
0x18000fc8b  xor     r8d, r8d; dwShareMode
0x18000fc8e  mov     edx, 40000000h; dwDesiredAccess
0x18000fc93  mov     rcx, rdi; lpFileName
0x18000fc96  call    cs:__imp_CreateFileW
0x18000fc9d  nop     dword ptr [rax+rax+00h]
0x18000fca2  mov     rbx, rax
0x18000fca5  mov     [rbp+var_30], rax
0x18000fca9  xor     edx, edx
0x18000fcab  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18000fcb0  lea     rax, [rbx+1]
0x18000fcb4  cmp     rax, 1
0x18000fcb8  jbe     loc_180010040
0x18000fcbe  mov     rdx, rbx; void *
0x18000fcc1  mov     rcx, rdi; wchar_t *
0x18000fcc4  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x18000fcc9  mov     esi, eax
0x18000fccb  test    eax, eax
0x18000fccd  jns     short loc_18000FD0C
0x18000fccf  lea     r14, WPP_GLOBAL_Control
0x18000fcd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcdd  cmp     rcx, r14
0x18000fce0  jz      loc_1800100C0
0x18000fce6  test    byte ptr [rcx+1Ch], 1
0x18000fcea  jz      loc_1800100C0
0x18000fcf0  lea     edx, [r13+0Ch]
0x18000fcf4  mov     r9d, eax
0x18000fcf7  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x18000fcfe  mov     rcx, [rcx+10h]
0x18000fd02  call    WPP_SF_d
0x18000fd07  jmp     loc_1800100C0
0x18000fd0c  mov     rcx, rbx; hFile
0x18000fd0f  call    cs:__imp_SetEndOfFile
0x18000fd16  nop     dword ptr [rax+rax+00h]
0x18000fd1b  lea     r14, WPP_GLOBAL_Control
0x18000fd22  test    eax, eax
0x18000fd24  jnz     short loc_18000FD63
0x18000fd26  mov     rax, cs:WPP_GLOBAL_Control
0x18000fd2d  cmp     rax, r14
0x18000fd30  jz      short loc_18000FD63
0x18000fd32  test    byte ptr [rax+1Ch], 2
0x18000fd36  jz      short loc_18000FD63
0x18000fd38  call    cs:__imp_GetLastError
0x18000fd3f  nop     dword ptr [rax+rax+00h]
0x18000fd44  mov     edx, 0Dh
0x18000fd49  mov     r9d, eax
0x18000fd4c  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x18000fd53  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd5a  mov     rcx, [rcx+10h]
0x18000fd5e  call    WPP_SF_d
0x18000fd63  mov     edx, 2000h; dwFileAttributes
0x18000fd68  mov     rcx, rdi; lpFileName
0x18000fd6b  call    cs:__imp_SetFileAttributesW
0x18000fd72  nop     dword ptr [rax+rax+00h]
0x18000fd77  test    eax, eax
0x18000fd79  jnz     short loc_18000FDA0
0x18000fd7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd82  cmp     rcx, r14
0x18000fd85  jz      short loc_18000FDA0
0x18000fd87  test    byte ptr [rcx+1Ch], 2
0x18000fd8b  jz      short loc_18000FDA0
0x18000fd8d  lea     edx, [rax+0Eh]
0x18000fd90  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x18000fd97  mov     rcx, [rcx+10h]
0x18000fd9b  call    WPP_SF_
0x18000fda0  mov     eax, 0FEFFh
0x18000fda5  mov     [rbp+Buffer], ax
0x18000fda9  mov     qword ptr [rsp+70h+dwCreationDisposition], r13; lpOverlapped
0x18000fdae  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000fdb2  mov     r8d, 2; nNumberOfBytesToWrite
0x18000fdb8  lea     rdx, [rbp+Buffer]; lpBuffer
0x18000fdbc  mov     rcx, rbx; hFile
0x18000fdbf  call    cs:__imp_WriteFile
0x18000fdc6  nop     dword ptr [rax+rax+00h]
0x18000fdcb  test    eax, eax
0x18000fdcd  jnz     short loc_18000FE1B
0x18000fdcf  call    cs:__imp_GetLastError
0x18000fdd6  nop     dword ptr [rax+rax+00h]
0x18000fddb  mov     ecx, eax; unsigned int
0x18000fddd  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000fde2  mov     esi, eax
0x18000fde4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fdeb  cmp     rcx, r14
0x18000fdee  jz      loc_1800100C0
0x18000fdf4  test    byte ptr [rcx+1Ch], 1
0x18000fdf8  jz      loc_1800100C0
0x18000fdfe  mov     edx, 0Fh
0x18000fe03  mov     r9d, eax
0x18000fe06  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x18000fe0d  mov     rcx, [rcx+10h]
0x18000fe11  call    WPP_SF_d
0x18000fe16  jmp     loc_1800100C0
0x18000fe1b  mov     rdi, [r12]
0x18000fe1f  cmp     rdi, r12
0x18000fe22  jz      loc_18000FF46
0x18000fe28  mov     rax, [rdi+10h]
0x18000fe2c  xor     r8d, r8d
0x18000fe2f  mov     rcx, [rdi+18h]
0x18000fe33  sub     rcx, rax
0x18000fe36  sar     rcx, 1
0x18000fe39  lea     rcx, [rax+rcx*2]
0x18000fe3d  cmp     rax, rcx
0x18000fe40  jz      short loc_18000FE55
0x18000fe42  imul    r8d, 1003Fh
0x18000fe49  movzx   edx, word ptr [rax]
0x18000fe4c  add     r8d, edx
0x18000fe4f  add     rax, 2
0x18000fe53  jmp     short loc_18000FE3D
0x18000fe55  mov     dword ptr [rbp+var_30], r8d
0x18000fe59  mov     r9, [rdi+30h]
0x18000fe5d  xor     r12d, r12d
0x18000fe60  mov     rax, r9
0x18000fe63  mov     rcx, [rdi+38h]
0x18000fe67  sub     rcx, r9
0x18000fe6a  sar     rcx, 1
0x18000fe6d  lea     rcx, [r9+rcx*2]
0x18000fe71  cmp     rax, rcx
0x18000fe74  jz      short loc_18000FE89
0x18000fe76  imul    r12d, 1003Fh
0x18000fe7d  movzx   edx, word ptr [rax]
0x18000fe80  add     r12d, edx
0x18000fe83  add     rax, 2
0x18000fe87  jmp     short loc_18000FE71
0x18000fe89  mov     r8, [rdi+10h]
0x18000fe8d  lea     rdx, aLsLs_0; "%ls=%ls\r\n"
0x18000fe94  lea     rcx, [rbp+lpBuffer]
0x18000fe98  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18000fe9d  mov     esi, eax
0x18000fe9f  test    eax, eax
0x18000fea1  js      short loc_18000FF22
0x18000fea3  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x18000fea7  mov     r8, [rbp+var_20]
0x18000feab  sub     r8, rdx
0x18000feae  sar     r8, 1
0x18000feb1  add     r8d, r8d; nNumberOfBytesToWrite
0x18000feb4  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x18000febd  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000fec1  mov     rcx, rbx; hFile
0x18000fec4  call    cs:__imp_WriteFile
0x18000fecb  nop     dword ptr [rax+rax+00h]
0x18000fed0  test    eax, eax
0x18000fed2  jz      short loc_18000FEE9
0x18000fed4  mov     eax, dword ptr [rbp+var_30]
0x18000fed7  add     eax, r12d
0x18000feda  add     r13d, eax
0x18000fedd  mov     rdi, [rdi]
0x18000fee0  mov     r12, [rbp+arg_0]
0x18000fee4  jmp     loc_18000FE1F
0x18000fee9  call    cs:__imp_GetLastError
0x18000fef0  nop     dword ptr [rax+rax+00h]
0x18000fef5  mov     ecx, eax; unsigned int
0x18000fef7  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000fefc  mov     esi, eax
0x18000fefe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff05  cmp     rcx, r14
0x18000ff08  jz      loc_1800100C0
0x18000ff0e  test    byte ptr [rcx+1Ch], 1
0x18000ff12  jz      loc_1800100C0
0x18000ff18  mov     edx, 11h
0x18000ff1d  jmp     loc_18000FE03
0x18000ff22  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff29  cmp     rcx, r14
0x18000ff2c  jz      loc_1800100C0
0x18000ff32  test    byte ptr [rcx+1Ch], 1
0x18000ff36  jz      loc_1800100C0
0x18000ff3c  mov     edx, 10h
0x18000ff41  jmp     loc_18000FE03
0x18000ff46  mov     r8d, r13d
0x18000ff49  lea     rdx, aMetadatahashLd; "MetadataHash=%ld"
0x18000ff50  lea     rcx, [rbp+lpBuffer]
0x18000ff54  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18000ff59  mov     esi, eax
0x18000ff5b  test    eax, eax
0x18000ff5d  jns     short loc_18000FF83
0x18000ff5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff66  cmp     rcx, r14
0x18000ff69  jz      loc_1800100C0
0x18000ff6f  test    byte ptr [rcx+1Ch], 1
0x18000ff73  jz      loc_1800100C0
0x18000ff79  mov     edx, 12h
0x18000ff7e  jmp     loc_18000FE03
0x18000ff83  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x18000ff87  mov     r8, [rbp+var_20]
0x18000ff8b  sub     r8, rdx
0x18000ff8e  sar     r8, 1
0x18000ff91  add     r8d, r8d; nNumberOfBytesToWrite
0x18000ff94  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x18000ff9d  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000ffa1  mov     rcx, rbx; hFile
0x18000ffa4  call    cs:__imp_WriteFile
0x18000ffab  nop     dword ptr [rax+rax+00h]
0x18000ffb0  test    eax, eax
0x18000ffb2  jnz     short loc_18000FFED
0x18000ffb4  call    cs:__imp_GetLastError
0x18000ffbb  nop     dword ptr [rax+rax+00h]
0x18000ffc0  mov     ecx, eax; unsigned int
0x18000ffc2  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000ffc7  mov     esi, eax
0x18000ffc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffd0  cmp     rcx, r14
0x18000ffd3  jz      loc_1800100C0
0x18000ffd9  test    byte ptr [rcx+1Ch], 1
0x18000ffdd  jz      loc_1800100C0
0x18000ffe3  mov     edx, 13h
0x18000ffe8  jmp     loc_18000FE03
0x18000ffed  mov     rcx, rbx; hFile
0x18000fff0  call    cs:__imp_FlushFileBuffers
0x18000fff7  nop     dword ptr [rax+rax+00h]
0x18000fffc  test    eax, eax
0x18000fffe  jnz     short loc_180010039
0x180010000  call    cs:__imp_GetLastError
0x180010007  nop     dword ptr [rax+rax+00h]
0x18001000c  mov     ecx, eax; unsigned int
0x18001000e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180010013  mov     esi, eax
0x180010015  mov     rcx, cs:WPP_GLOBAL_Control
0x18001001c  cmp     rcx, r14
0x18001001f  jz      loc_1800100C0
0x180010025  test    byte ptr [rcx+1Ch], 1
0x180010029  jz      loc_1800100C0
0x18001002f  mov     edx, 14h
0x180010034  jmp     loc_18000FE03
0x180010039  xor     esi, esi
0x18001003b  jmp     loc_1800100C0
0x180010040  call    cs:__imp_GetLastError
0x180010047  nop     dword ptr [rax+rax+00h]
0x18001004c  mov     ecx, eax; unsigned int
0x18001004e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180010053  mov     esi, eax
0x180010055  lea     r14, WPP_GLOBAL_Control
0x18001005c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010063  cmp     rcx, r14
0x180010066  jz      short loc_1800100C0
0x180010068  test    byte ptr [rcx+1Ch], 1
0x18001006c  jz      short loc_1800100C0
0x18001006e  mov     edx, 0Bh
0x180010073  mov     [rsp+70h+dwCreationDisposition], eax
0x180010077  mov     r9, rdi
0x18001007a  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x180010081  mov     rcx, [rcx+10h]
0x180010085  call    WPP_SF_SD
0x18001008a  jmp     short loc_1800100C0
0x18001008c  mov     esi, 80070057h
0x180010091  lea     r14, WPP_GLOBAL_Control
0x180010098  mov     rcx, cs:WPP_GLOBAL_Control
0x18001009f  cmp     rcx, r14
0x1800100a2  jz      short loc_1800100C0
0x1800100a4  test    byte ptr [rcx+1Ch], 1
0x1800100a8  jz      short loc_1800100C0
0x1800100aa  mov     edx, 0Ah
0x1800100af  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x1800100b6  mov     rcx, [rcx+10h]
0x1800100ba  call    WPP_SF_
0x1800100bf  nop
0x1800100c0  lea     rax, [rbp+var_18]
0x1800100c4  mov     r8, [rbp+lpBuffer]; lpMem
0x1800100c8  cmp     r8, rax
0x1800100cb  jz      short loc_1800100E3
0x1800100cd  xor     edx, edx; dwFlags
0x1800100cf  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800100d6  call    cs:__imp_HeapFree
0x1800100dd  nop     dword ptr [rax+rax+00h]
0x1800100e2  nop
0x1800100e3  mov     rdx, rbx
0x1800100e6  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x1800100eb  mov     eax, esi
0x1800100ed  add     rsp, 70h
0x1800100f1  pop     r14
0x1800100f3  pop     r13
0x1800100f5  pop     r12
0x1800100f7  pop     rdi
0x1800100f8  pop     rsi
0x1800100f9  pop     rbx
  ... truncated ...
```
