# CIniParser::WriteToFile(wchar_t const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180005380`
- end: `0x180005800`
- name: `?WriteToFile@CIniParser@@QEAAJPEB_WPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `1152`
- prototype: `int(CIniParser *__hidden this, const wchar_t *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180074114`

## callees

- `0x180004bb4`
- `0x180005380`
- `0x18000716c`
- `0x1800072cc`
- `0x18000bc10`
- `0x18000cc74`
- `0x180014720`
- `0x18001fe24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000547c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000560f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000570e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000547c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000560f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000570e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005745`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057e9`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180005704`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180005704`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180005459`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180005459`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800054a9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800054a9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800054f7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800055f0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800056c4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800054f7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800055f0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800056c4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800053ee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800053ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CIniParser::WriteToFile(CIniParser *this, const wchar_t *a2, struct _SECURITY_ATTRIBUTES *a3)
{
  CIniParser *v5; // r12
  unsigned int v6; // r13d
  char *FileW; // r15
  int v8; // eax
  unsigned int v9; // edi
  DWORD v10; // eax
  DWORD v11; // eax
  int v12; // eax
  wchar_t *v13; // rcx
  __int64 v14; // rdx
  CIniParser *v15; // rbx
  unsigned __int16 *v16; // rax
  int v17; // r8d
  unsigned __int16 *v18; // rcx
  int v19; // r12d
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rcx
  DWORD v22; // eax
  DWORD v23; // eax
  DWORD v24; // eax
  DWORD LastError; // eax
  unsigned int v26; // eax
  int v28; // [rsp+40h] [rbp-30h]
  LPCVOID lpBuffer; // [rsp+48h] [rbp-28h] BYREF
  __int64 v30; // [rsp+50h] [rbp-20h]
  char v31; // [rsp+58h] [rbp-18h] BYREF
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
    FileW = (char *)CreateFileW(a2, 0x40000000u, 0, a3, 4u, 0x80u, 0);
    if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
    {
      LastError = GetLastError();
      v26 = ERROR_HR_FROM_WIN32(LastError);
      v9 = v26;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids,
          (_DWORD)a2,
          v26);
    }
    else
    {
      v8 = UtilVerifyFilePath(a2, FileW);
      v9 = v8;
      if ( v8 >= 0 )
      {
        if ( !SetEndOfFile(FileW)
          && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          v10 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids, v10);
        }
        if ( !SetFileAttributesW(a2, 0x2000u)
          && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids);
        }
        Buffer = -257;
        if ( WriteFile(FileW, &Buffer, 2u, &NumberOfBytesWritten, 0) )
        {
          v15 = *(CIniParser **)v5;
          while ( v15 != v5 )
          {
            v16 = (unsigned __int16 *)*((_QWORD *)v15 + 2);
            v17 = 0;
            v18 = &v16[(__int64)(*((_QWORD *)v15 + 3) - (_QWORD)v16) >> 1];
            while ( v16 != v18 )
              v17 = *v16++ + 65599 * v17;
            v28 = v17;
            v19 = 0;
            v20 = (unsigned __int16 *)*((_QWORD *)v15 + 6);
            v21 = &v20[(__int64)(*((_QWORD *)v15 + 7) - (_QWORD)v20) >> 1];
            while ( v20 != v21 )
              v19 = *v20++ + 65599 * v19;
            v12 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                    &lpBuffer,
                    L"%ls=%ls\r\n",
                    *((_QWORD *)v15 + 2));
            v9 = v12;
            if ( v12 < 0 )
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v14 = 16;
                goto LABEL_20;
              }
              goto LABEL_57;
            }
            if ( !WriteFile(FileW, lpBuffer, 2 * ((v30 - (__int64)lpBuffer) >> 1), &NumberOfBytesWritten, 0) )
            {
              v22 = GetLastError();
              v12 = ERROR_HR_FROM_WIN32(v22);
              v9 = v12;
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v14 = 17;
                goto LABEL_20;
              }
              goto LABEL_57;
            }
            v6 += v19 + v28;
            v15 = *(CIniParser **)v15;
            v5 = this;
          }
          v12 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  &lpBuffer,
                  L"MetadataHash=%ld",
                  v6);
          v9 = v12;
          if ( v12 >= 0 )
          {
            if ( WriteFile(FileW, lpBuffer, 2 * ((v30 - (__int64)lpBuffer) >> 1), &NumberOfBytesWritten, 0) )
            {
              if ( FlushFileBuffers(FileW) )
              {
                v9 = 0;
              }
              else
              {
                v24 = GetLastError();
                v12 = ERROR_HR_FROM_WIN32(v24);
                v9 = v12;
                v13 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  v14 = 20;
                  goto LABEL_20;
                }
              }
            }
            else
            {
              v23 = GetLastError();
              v12 = ERROR_HR_FROM_WIN32(v23);
              v9 = v12;
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v14 = 19;
                goto LABEL_20;
              }
            }
          }
          else
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v14 = 18;
              goto LABEL_20;
            }
          }
        }
        else
        {
          v11 = GetLastError();
          v12 = ERROR_HR_FROM_WIN32(v11);
          v9 = v12;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v14 = 15;
LABEL_20:
            WPP_SF_d(*((_QWORD *)v13 + 2), v14, &WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids, (unsigned int)v12);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          &WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids,
          (unsigned int)v8);
      }
    }
  }
  else
  {
    v9 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids);
  }
LABEL_57:
  if ( lpBuffer != &v31 )
    HeapFree(g_hWerheap, 0, (LPVOID)lpBuffer);
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  return v9;
}

```

## disassembly

```asm
0x180005380  mov     [rsp-38h+arg_0], rcx
0x180005385  push    rbp
0x180005386  push    rbx
0x180005387  push    rsi
0x180005388  push    rdi
0x180005389  push    r12
0x18000538b  push    r13
0x18000538d  push    r15
0x18000538f  mov     rbp, rsp
0x180005392  sub     rsp, 70h
0x180005396  mov     rdi, r8
0x180005399  mov     rbx, rdx
0x18000539c  mov     r12, rcx
0x18000539f  xor     r13d, r13d
0x1800053a2  mov     r15d, r13d
0x1800053a5  mov     [rbp+NumberOfBytesWritten], r13d
0x1800053a9  lea     rcx, [rbp+lpBuffer]; void *
0x1800053ad  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800053b2  nop
0x1800053b3  mov     [rbp+Buffer], r13w
0x1800053b8  test    rbx, rbx
0x1800053bb  jz      loc_18000578B
0x1800053c1  cmp     [rbx], r13w
0x1800053c5  jz      loc_18000578B
0x1800053cb  mov     [rsp+70h+hTemplateFile], r13; hTemplateFile
0x1800053d0  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800053d8  mov     [rsp+70h+dwCreationDisposition], 4; dwCreationDisposition
0x1800053e0  mov     r9, rdi; lpSecurityAttributes
0x1800053e3  xor     r8d, r8d; dwShareMode
0x1800053e6  mov     edx, 40000000h; dwDesiredAccess
0x1800053eb  mov     rcx, rbx; lpFileName
0x1800053ee  call    cs:__imp_CreateFileW
0x1800053f4  mov     r15, rax
0x1800053f7  mov     [rbp+var_30], rax
0x1800053fb  inc     rax
0x1800053fe  cmp     rax, 1
0x180005402  jbe     loc_180005745
0x180005408  mov     rdx, r15; void *
0x18000540b  mov     rcx, rbx; wchar_t *
0x18000540e  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x180005413  mov     edi, eax
0x180005415  test    eax, eax
0x180005417  jns     short loc_180005456
0x180005419  lea     rsi, WPP_GLOBAL_Control
0x180005420  mov     rcx, cs:WPP_GLOBAL_Control
0x180005427  cmp     rcx, rsi
0x18000542a  jz      loc_1800057BF
0x180005430  test    byte ptr [rcx+1Ch], 1
0x180005434  jz      loc_1800057BF
0x18000543a  lea     edx, [r13+0Ch]
0x18000543e  mov     r9d, eax
0x180005441  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x180005448  mov     rcx, [rcx+10h]
0x18000544c  call    WPP_SF_d
0x180005451  jmp     loc_1800057BF
0x180005456  mov     rcx, r15; hFile
0x180005459  call    cs:__imp_SetEndOfFile
0x18000545f  lea     rsi, WPP_GLOBAL_Control
0x180005466  test    eax, eax
0x180005468  jnz     short loc_1800054A1
0x18000546a  mov     rax, cs:WPP_GLOBAL_Control
0x180005471  cmp     rax, rsi
0x180005474  jz      short loc_1800054A1
0x180005476  test    byte ptr [rax+1Ch], 2
0x18000547a  jz      short loc_1800054A1
0x18000547c  call    cs:__imp_GetLastError
0x180005482  mov     edx, 0Dh
0x180005487  mov     r9d, eax
0x18000548a  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x180005491  mov     rcx, cs:WPP_GLOBAL_Control
0x180005498  mov     rcx, [rcx+10h]
0x18000549c  call    WPP_SF_d
0x1800054a1  mov     edx, 2000h; dwFileAttributes
0x1800054a6  mov     rcx, rbx; lpFileName
0x1800054a9  call    cs:__imp_SetFileAttributesW
0x1800054af  test    eax, eax
0x1800054b1  jnz     short loc_1800054D8
0x1800054b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054ba  cmp     rcx, rsi
0x1800054bd  jz      short loc_1800054D8
0x1800054bf  test    byte ptr [rcx+1Ch], 2
0x1800054c3  jz      short loc_1800054D8
0x1800054c5  lea     edx, [rax+0Eh]
0x1800054c8  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x1800054cf  mov     rcx, [rcx+10h]
0x1800054d3  call    WPP_SF_
0x1800054d8  mov     eax, 0FEFFh
0x1800054dd  mov     [rbp+Buffer], ax
0x1800054e1  mov     qword ptr [rsp+70h+dwCreationDisposition], r13; lpOverlapped
0x1800054e6  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800054ea  mov     r8d, 2; nNumberOfBytesToWrite
0x1800054f0  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800054f4  mov     rcx, r15; hFile
0x1800054f7  call    cs:__imp_WriteFile
0x1800054fd  test    eax, eax
0x1800054ff  jnz     short loc_180005547
0x180005501  call    cs:__imp_GetLastError
0x180005507  mov     ecx, eax; unsigned int
0x180005509  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000550e  mov     edi, eax
0x180005510  mov     rcx, cs:WPP_GLOBAL_Control
0x180005517  cmp     rcx, rsi
0x18000551a  jz      loc_1800057BF
0x180005520  test    byte ptr [rcx+1Ch], 1
0x180005524  jz      loc_1800057BF
0x18000552a  mov     edx, 0Fh
0x18000552f  mov     r9d, eax
0x180005532  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x180005539  mov     rcx, [rcx+10h]
0x18000553d  call    WPP_SF_d
0x180005542  jmp     loc_1800057BF
0x180005547  mov     rbx, [r12]
0x18000554b  cmp     rbx, r12
0x18000554e  jz      loc_180005666
0x180005554  mov     rax, [rbx+10h]
0x180005558  xor     r8d, r8d
0x18000555b  mov     rcx, [rbx+18h]
0x18000555f  sub     rcx, rax
0x180005562  sar     rcx, 1
0x180005565  lea     rcx, [rax+rcx*2]
0x180005569  cmp     rax, rcx
0x18000556c  jz      short loc_180005581
0x18000556e  imul    r8d, 1003Fh
0x180005575  movzx   edx, word ptr [rax]
0x180005578  add     r8d, edx
0x18000557b  add     rax, 2
0x18000557f  jmp     short loc_180005569
0x180005581  mov     dword ptr [rbp+var_30], r8d
0x180005585  mov     r9, [rbx+30h]
0x180005589  xor     r12d, r12d
0x18000558c  mov     rax, r9
0x18000558f  mov     rcx, [rbx+38h]
0x180005593  sub     rcx, r9
0x180005596  sar     rcx, 1
0x180005599  lea     rcx, [r9+rcx*2]
0x18000559d  cmp     rax, rcx
0x1800055a0  jz      short loc_1800055B5
0x1800055a2  imul    r12d, 1003Fh
0x1800055a9  movzx   edx, word ptr [rax]
0x1800055ac  add     r12d, edx
0x1800055af  add     rax, 2
0x1800055b3  jmp     short loc_18000559D
0x1800055b5  mov     r8, [rbx+10h]
0x1800055b9  lea     rdx, aLsLs_0; "%ls=%ls\r\n"
0x1800055c0  lea     rcx, [rbp+lpBuffer]
0x1800055c4  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800055c9  mov     edi, eax
0x1800055cb  test    eax, eax
0x1800055cd  js      short loc_180005642
0x1800055cf  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x1800055d3  mov     r8, [rbp+var_20]
0x1800055d7  sub     r8, rdx
0x1800055da  sar     r8, 1
0x1800055dd  add     r8d, r8d; nNumberOfBytesToWrite
0x1800055e0  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x1800055e9  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800055ed  mov     rcx, r15; hFile
0x1800055f0  call    cs:__imp_WriteFile
0x1800055f6  test    eax, eax
0x1800055f8  jz      short loc_18000560F
0x1800055fa  mov     eax, dword ptr [rbp+var_30]
0x1800055fd  add     eax, r12d
0x180005600  add     r13d, eax
0x180005603  mov     rbx, [rbx]
0x180005606  mov     r12, [rbp+arg_0]
0x18000560a  jmp     loc_18000554B
0x18000560f  call    cs:__imp_GetLastError
0x180005615  mov     ecx, eax; unsigned int
0x180005617  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000561c  mov     edi, eax
0x18000561e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005625  cmp     rcx, rsi
0x180005628  jz      loc_1800057BF
0x18000562e  test    byte ptr [rcx+1Ch], 1
0x180005632  jz      loc_1800057BF
0x180005638  mov     edx, 11h
0x18000563d  jmp     loc_18000552F
0x180005642  mov     rcx, cs:WPP_GLOBAL_Control
0x180005649  cmp     rcx, rsi
0x18000564c  jz      loc_1800057BF
0x180005652  test    byte ptr [rcx+1Ch], 1
0x180005656  jz      loc_1800057BF
0x18000565c  mov     edx, 10h
0x180005661  jmp     loc_18000552F
0x180005666  mov     r8d, r13d
0x180005669  lea     rdx, aMetadatahashLd; "MetadataHash=%ld"
0x180005670  lea     rcx, [rbp+lpBuffer]
0x180005674  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180005679  mov     edi, eax
0x18000567b  test    eax, eax
0x18000567d  jns     short loc_1800056A3
0x18000567f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005686  cmp     rcx, rsi
0x180005689  jz      loc_1800057BF
0x18000568f  test    byte ptr [rcx+1Ch], 1
0x180005693  jz      loc_1800057BF
0x180005699  mov     edx, 12h
0x18000569e  jmp     loc_18000552F
0x1800056a3  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x1800056a7  mov     r8, [rbp+var_20]
0x1800056ab  sub     r8, rdx
0x1800056ae  sar     r8, 1
0x1800056b1  add     r8d, r8d; nNumberOfBytesToWrite
0x1800056b4  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x1800056bd  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800056c1  mov     rcx, r15; hFile
0x1800056c4  call    cs:__imp_WriteFile
0x1800056ca  test    eax, eax
0x1800056cc  jnz     short loc_180005701
0x1800056ce  call    cs:__imp_GetLastError
0x1800056d4  mov     ecx, eax; unsigned int
0x1800056d6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800056db  mov     edi, eax
0x1800056dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056e4  cmp     rcx, rsi
0x1800056e7  jz      loc_1800057BF
0x1800056ed  test    byte ptr [rcx+1Ch], 1
0x1800056f1  jz      loc_1800057BF
0x1800056f7  mov     edx, 13h
0x1800056fc  jmp     loc_18000552F
0x180005701  mov     rcx, r15; hFile
0x180005704  call    cs:__imp_FlushFileBuffers
0x18000570a  test    eax, eax
0x18000570c  jnz     short loc_180005741
0x18000570e  call    cs:__imp_GetLastError
0x180005714  mov     ecx, eax; unsigned int
0x180005716  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000571b  mov     edi, eax
0x18000571d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005724  cmp     rcx, rsi
0x180005727  jz      loc_1800057BF
0x18000572d  test    byte ptr [rcx+1Ch], 1
0x180005731  jz      loc_1800057BF
0x180005737  mov     edx, 14h
0x18000573c  jmp     loc_18000552F
0x180005741  xor     edi, edi
0x180005743  jmp     short loc_1800057BF
0x180005745  call    cs:__imp_GetLastError
0x18000574b  mov     ecx, eax; unsigned int
0x18000574d  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180005752  mov     edi, eax
0x180005754  lea     rsi, WPP_GLOBAL_Control
0x18000575b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005762  cmp     rcx, rsi
0x180005765  jz      short loc_1800057BF
0x180005767  test    byte ptr [rcx+1Ch], 1
0x18000576b  jz      short loc_1800057BF
0x18000576d  mov     edx, 0Bh
0x180005772  mov     [rsp+70h+dwCreationDisposition], eax
0x180005776  mov     r9, rbx
0x180005779  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x180005780  mov     rcx, [rcx+10h]
0x180005784  call    WPP_SF_SD
0x180005789  jmp     short loc_1800057BF
0x18000578b  mov     edi, 80070057h
0x180005790  lea     rsi, WPP_GLOBAL_Control
0x180005797  mov     rcx, cs:WPP_GLOBAL_Control
0x18000579e  cmp     rcx, rsi
0x1800057a1  jz      short loc_1800057BF
0x1800057a3  test    byte ptr [rcx+1Ch], 1
0x1800057a7  jz      short loc_1800057BF
0x1800057a9  mov     edx, 0Ah
0x1800057ae  lea     r8, WPP_a1e61a0ed48f3dd532bafd2a8c2fa664_Traceguids
0x1800057b5  mov     rcx, [rcx+10h]
0x1800057b9  call    WPP_SF_
0x1800057be  nop
0x1800057bf  lea     rax, [rbp+var_18]
0x1800057c3  mov     r8, [rbp+lpBuffer]; lpMem
0x1800057c7  cmp     r8, rax
0x1800057ca  jz      short loc_1800057DC
0x1800057cc  xor     edx, edx; dwFlags
0x1800057ce  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800057d5  call    cs:__imp_HeapFree
0x1800057db  nop
0x1800057dc  lea     rax, [r15+1]
0x1800057e0  cmp     rax, 1
0x1800057e4  jbe     short loc_1800057EF
0x1800057e6  mov     rcx, r15; hObject
0x1800057e9  call    cs:__imp_CloseHandle
0x1800057ef  mov     eax, edi
0x1800057f1  add     rsp, 70h
0x1800057f5  pop     r15
0x1800057f7  pop     r13
0x1800057f9  pop     r12
0x1800057fb  pop     rdi
0x1800057fc  pop     rsi
0x1800057fd  pop     rbx
0x1800057fe  pop     rbp
0x1800057ff  retn
```
