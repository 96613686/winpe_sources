# WerpAddRegisteredDumpsToReport

- ea: `0x180067330`
- end: `0x1800674dd`
- name: `WerpAddRegisteredDumpsToReport`
- size: `429`
- prototype: `__int64 __fastcall(HREPORT hReportHandle, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002e4b8`

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x180007e34`
- `0x180050db0`
- `0x180060740`
- `0x180067330`
- `0x1800a3b98`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18006742a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18006742a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800673fe`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800673fe`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800673cd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800673cd`

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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, &WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180067330  mov     [rsp-28h+arg_10], rbx
0x180067335  push    rbp
0x180067336  push    rsi
0x180067337  push    rdi
0x180067338  push    r14
0x18006733a  push    r15
0x18006733c  mov     rbp, rsp
0x18006733f  sub     rsp, 70h
0x180067343  mov     rax, cs:__security_cookie
0x18006734a  xor     rax, rsp
0x18006734d  mov     [rbp+var_8], rax
0x180067351  mov     [rbp+lpBaseAddress], 0
0x180067359  mov     rsi, rdx
0x18006735c  mov     r15, rcx
0x18006735f  test    rcx, rcx
0x180067362  jz      loc_18006748A
0x180067368  test    rdx, rdx
0x18006736b  jz      loc_18006748A
0x180067371  lea     rdx, [rbp+lpBaseAddress]; struct _WER_DUMP_COLLECTION **
0x180067375  mov     rcx, rsi; void *
0x180067378  call    ?WerpGetDumpCollectionListStart@@YAJPEAXPEAPEAU_WER_DUMP_COLLECTION@@@Z; WerpGetDumpCollectionListStart(void *,_WER_DUMP_COLLECTION * *)
0x18006737d  test    eax, eax
0x18006737f  js      loc_1800674BD
0x180067385  mov     rdi, [rbp+lpBaseAddress]
0x180067389  test    rdi, rdi
0x18006738c  jz      loc_1800674BD
0x180067392  xor     r14d, r14d
0x180067395  cmp     r14d, 200h
0x18006739c  jnb     loc_180067486
0x1800673a2  xorps   xmm0, xmm0
0x1800673a5  mov     [rbp+NumberOfBytesRead], 0
0x1800673ad  lea     rax, [rbp+NumberOfBytesRead]
0x1800673b1  mov     r9d, 10h; nSize
0x1800673b7  lea     r8, [rbp+Buffer]; lpBuffer
0x1800673bb  mov     [rsp+70h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1800673c0  mov     rdx, rdi; lpBaseAddress
0x1800673c3  mov     rcx, rsi; hProcess
0x1800673c6  movups  [rbp+Buffer], xmm0
0x1800673ca  inc     r14d
0x1800673cd  call    cs:__imp_ReadProcessMemory
0x1800673d3  test    eax, eax
0x1800673d5  jz      loc_18006747D
0x1800673db  cmp     [rbp+NumberOfBytesRead], 10h
0x1800673e0  jnz     loc_18006747D
0x1800673e6  mov     r8d, dword ptr [rbp+Buffer+8]; dwProcessId
0x1800673ea  mov     rdi, qword ptr [rbp+Buffer]
0x1800673ee  test    r8d, r8d
0x1800673f1  jz      loc_18006747D
0x1800673f7  xor     edx, edx; bInheritHandle
0x1800673f9  mov     ecx, 100450h; dwDesiredAccess
0x1800673fe  call    cs:__imp_OpenProcess
0x180067404  mov     rbx, rax
0x180067407  mov     [rbp+var_20], rax
0x18006740b  inc     rax
0x18006740e  cmp     rax, 1
0x180067412  jbe     short loc_180067474
0x180067414  mov     eax, dword ptr [rbp+Buffer+0Ch]
0x180067417  xor     r8d, r8d
0x18006741a  mov     [rbp+lpBaseAddress], r8
0x18006741e  test    eax, eax
0x180067420  jz      short loc_180067440
0x180067422  xor     edx, edx; bInheritHandle
0x180067424  mov     r8d, eax; dwThreadId
0x180067427  lea     ecx, [rdx+48h]; dwDesiredAccess
0x18006742a  call    cs:__imp_OpenThread
0x180067430  mov     rdx, rax
0x180067433  lea     rcx, [rbp+lpBaseAddress]
0x180067437  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18006743c  mov     r8, [rbp+lpBaseAddress]; hThread
0x180067440  mov     [rsp+70h+dwFlags], 80000002h; dwFlags
0x180067448  mov     r9d, 4; dumpType
0x18006744e  mov     [rsp+70h+pDumpCustomOptions], 0; pDumpCustomOptions
0x180067457  mov     rdx, rbx; hProcess
0x18006745a  mov     rcx, r15; hReportHandle
0x18006745d  mov     [rsp+70h+lpNumberOfBytesRead], 0; pExceptionParam
0x180067466  call    WerReportAddDump
0x18006746b  lea     rcx, [rbp+lpBaseAddress]
0x18006746f  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180067474  lea     rcx, [rbp+var_20]
0x180067478  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18006747d  test    rdi, rdi
0x180067480  jnz     loc_180067395
0x180067486  xor     eax, eax
0x180067488  jmp     short loc_1800674BD
0x18006748a  mov     rcx, cs:WPP_GLOBAL_Control
0x180067491  lea     rax, WPP_GLOBAL_Control
0x180067498  cmp     rcx, rax
0x18006749b  jz      short loc_1800674B8
0x18006749d  test    byte ptr [rcx+1Ch], 1
0x1800674a1  jz      short loc_1800674B8
0x1800674a3  mov     rcx, [rcx+10h]
0x1800674a7  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x1800674ae  mov     edx, 0A9h
0x1800674b3  call    WPP_SF_
0x1800674b8  mov     eax, 80070057h
0x1800674bd  mov     rcx, [rbp+var_8]
0x1800674c1  xor     rcx, rsp; StackCookie
0x1800674c4  call    __security_check_cookie
0x1800674c9  mov     rbx, [rsp+70h+arg_10]
0x1800674d1  add     rsp, 70h
0x1800674d5  pop     r15
0x1800674d7  pop     r14
0x1800674d9  pop     rdi
0x1800674da  pop     rsi
0x1800674db  pop     rbp
0x1800674dc  retn
```
