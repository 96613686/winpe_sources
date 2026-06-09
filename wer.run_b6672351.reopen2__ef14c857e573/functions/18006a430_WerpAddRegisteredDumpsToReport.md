# WerpAddRegisteredDumpsToReport

- ea: `0x18006a430`
- end: `0x18006a5f0`
- name: `WerpAddRegisteredDumpsToReport`
- size: `448`
- prototype: `__int64 __fastcall(HREPORT hReportHandle, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180030058`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x180008004`
- `0x180053300`
- `0x180062fa0`
- `0x18006a430`
- `0x1800a8848`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18006a536`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18006a536`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006a504`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006a504`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006a4cd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006a4cd`

## pseudocode

```c
__int64 __fastcall WerpAddRegisteredDumpsToReport(HREPORT hReportHandle, void *a2)
{
  __int64 result; // rax
  LPCVOID v5; // rdi
  unsigned int v6; // r14d
  char *v7; // rbx
  void *v8; // r8
  HANDLE v9; // rax
  LPCVOID lpBaseAddress; // [rsp+40h] [rbp-30h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+48h] [rbp-28h] BYREF
  char *v12; // [rsp+50h] [rbp-20h] BYREF
  __int128 Buffer; // [rsp+58h] [rbp-18h] BYREF

  lpBaseAddress = 0;
  if ( hReportHandle && a2 )
  {
    result = WerpGetDumpCollectionListStart(a2, (struct _WER_DUMP_COLLECTION **)&lpBaseAddress);
    if ( (int)result >= 0 )
    {
      v5 = lpBaseAddress;
      if ( lpBaseAddress )
      {
        v6 = 0;
        do
        {
          if ( v6 >= 0x200 )
            break;
          NumberOfBytesRead = 0;
          Buffer = 0;
          ++v6;
          if ( ReadProcessMemory(a2, v5, &Buffer, 0x10u, &NumberOfBytesRead) )
          {
            if ( NumberOfBytesRead == 16 )
            {
              v5 = (LPCVOID)Buffer;
              if ( DWORD2(Buffer) )
              {
                v7 = (char *)OpenProcess(0x100450u, 0, DWORD2(Buffer));
                v12 = v7;
                if ( v7 != (char *)-1LL && v7 + 1 != (char *)1 )
                {
                  v8 = 0;
                  lpBaseAddress = 0;
                  if ( HIDWORD(Buffer) )
                  {
                    v9 = OpenThread(0x48u, 0, HIDWORD(Buffer));
                    tlx::unique_any<tlx::file_handle_traits>::reset(&lpBaseAddress, v9);
                    v8 = (void *)lpBaseAddress;
                  }
                  WerReportAddDump(hReportHandle, v7, v8, WerDumpTypeTriageDump, 0, 0, 0x80000002);
                  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&lpBaseAddress);
                }
                tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v12);
              }
            }
          }
        }
        while ( v5 );
        return 0;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18006a430  mov     [rsp-28h+arg_10], rbx
0x18006a435  push    rbp
0x18006a436  push    rsi
0x18006a437  push    rdi
0x18006a438  push    r14
0x18006a43a  push    r15
0x18006a43c  mov     rbp, rsp
0x18006a43f  sub     rsp, 70h
0x18006a443  mov     rax, cs:__security_cookie
0x18006a44a  xor     rax, rsp
0x18006a44d  mov     [rbp+var_8], rax
0x18006a451  mov     [rbp+lpBaseAddress], 0
0x18006a459  mov     rsi, rdx
0x18006a45c  mov     r15, rcx
0x18006a45f  test    rcx, rcx
0x18006a462  jz      loc_18006A59C
0x18006a468  test    rdx, rdx
0x18006a46b  jz      loc_18006A59C
0x18006a471  lea     rdx, [rbp+lpBaseAddress]; struct _WER_DUMP_COLLECTION **
0x18006a475  mov     rcx, rsi; void *
0x18006a478  call    ?WerpGetDumpCollectionListStart@@YAJPEAXPEAPEAU_WER_DUMP_COLLECTION@@@Z; WerpGetDumpCollectionListStart(void *,_WER_DUMP_COLLECTION * *)
0x18006a47d  test    eax, eax
0x18006a47f  js      loc_18006A5CF
0x18006a485  mov     rdi, [rbp+lpBaseAddress]
0x18006a489  test    rdi, rdi
0x18006a48c  jz      loc_18006A5CF
0x18006a492  xor     r14d, r14d
0x18006a495  cmp     r14d, 200h
0x18006a49c  jnb     loc_18006A598
0x18006a4a2  xorps   xmm0, xmm0
0x18006a4a5  mov     [rbp+NumberOfBytesRead], 0
0x18006a4ad  lea     rax, [rbp+NumberOfBytesRead]
0x18006a4b1  mov     r9d, 10h; nSize
0x18006a4b7  lea     r8, [rbp+Buffer]; lpBuffer
0x18006a4bb  mov     [rsp+70h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18006a4c0  mov     rdx, rdi; lpBaseAddress
0x18006a4c3  mov     rcx, rsi; hProcess
0x18006a4c6  movups  [rbp+Buffer], xmm0
0x18006a4ca  inc     r14d
0x18006a4cd  call    cs:__imp_ReadProcessMemory
0x18006a4d4  nop     dword ptr [rax+rax+00h]
0x18006a4d9  test    eax, eax
0x18006a4db  jz      loc_18006A58F
0x18006a4e1  cmp     [rbp+NumberOfBytesRead], 10h
0x18006a4e6  jnz     loc_18006A58F
0x18006a4ec  mov     r8d, dword ptr [rbp+Buffer+8]; dwProcessId
0x18006a4f0  mov     rdi, qword ptr [rbp+Buffer]
0x18006a4f4  test    r8d, r8d
0x18006a4f7  jz      loc_18006A58F
0x18006a4fd  xor     edx, edx; bInheritHandle
0x18006a4ff  mov     ecx, 100450h; dwDesiredAccess
0x18006a504  call    cs:__imp_OpenProcess
0x18006a50b  nop     dword ptr [rax+rax+00h]
0x18006a510  mov     rbx, rax
0x18006a513  mov     [rbp+var_20], rax
0x18006a517  inc     rax
0x18006a51a  cmp     rax, 1
0x18006a51e  jbe     short loc_18006A586
0x18006a520  mov     eax, dword ptr [rbp+Buffer+0Ch]
0x18006a523  xor     r8d, r8d
0x18006a526  mov     [rbp+lpBaseAddress], r8
0x18006a52a  test    eax, eax
0x18006a52c  jz      short loc_18006A552
0x18006a52e  xor     edx, edx; bInheritHandle
0x18006a530  mov     r8d, eax; dwThreadId
0x18006a533  lea     ecx, [rdx+48h]; dwDesiredAccess
0x18006a536  call    cs:__imp_OpenThread
0x18006a53d  nop     dword ptr [rax+rax+00h]
0x18006a542  mov     rdx, rax
0x18006a545  lea     rcx, [rbp+lpBaseAddress]
0x18006a549  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18006a54e  mov     r8, [rbp+lpBaseAddress]; hThread
0x18006a552  mov     [rsp+70h+dwFlags], 80000002h; dwFlags
0x18006a55a  mov     r9d, 4; dumpType
0x18006a560  mov     [rsp+70h+pDumpCustomOptions], 0; pDumpCustomOptions
0x18006a569  mov     rdx, rbx; hProcess
0x18006a56c  mov     rcx, r15; hReportHandle
0x18006a56f  mov     [rsp+70h+lpNumberOfBytesRead], 0; pExceptionParam
0x18006a578  call    WerReportAddDump
0x18006a57d  lea     rcx, [rbp+lpBaseAddress]
0x18006a581  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18006a586  lea     rcx, [rbp+var_20]
0x18006a58a  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18006a58f  test    rdi, rdi
0x18006a592  jnz     loc_18006A495
0x18006a598  xor     eax, eax
0x18006a59a  jmp     short loc_18006A5CF
0x18006a59c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a5a3  lea     rax, WPP_GLOBAL_Control
0x18006a5aa  cmp     rcx, rax
0x18006a5ad  jz      short loc_18006A5CA
0x18006a5af  test    byte ptr [rcx+1Ch], 1
0x18006a5b3  jz      short loc_18006A5CA
0x18006a5b5  mov     rcx, [rcx+10h]
0x18006a5b9  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x18006a5c0  mov     edx, 0A9h
0x18006a5c5  call    WPP_SF_
0x18006a5ca  mov     eax, 80070057h
0x18006a5cf  mov     rcx, [rbp+var_8]
0x18006a5d3  xor     rcx, rsp; StackCookie
0x18006a5d6  call    __security_check_cookie
0x18006a5db  mov     rbx, [rsp+70h+arg_10]
0x18006a5e3  add     rsp, 70h
0x18006a5e7  pop     r15
0x18006a5e9  pop     r14
0x18006a5eb  pop     rdi
0x18006a5ec  pop     rsi
0x18006a5ed  pop     rbp
0x18006a5ee  retn
```
