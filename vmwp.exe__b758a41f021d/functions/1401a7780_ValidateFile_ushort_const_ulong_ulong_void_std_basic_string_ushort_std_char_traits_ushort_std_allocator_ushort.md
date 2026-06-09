# ValidateFile(ushort const *,ulong,ulong,void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1401a7780`
- end: `0x1401a79b0`
- name: `?ValidateFile@@YAHPEBGKKPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1401a8d10`

## callees

- `0x14003c680`
- `0x14003d828`
- `0x14011ea40`
- `0x1401a5bd8`
- `0x1401a7780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1401a797f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1401a797f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401a7832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401a78af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401a78e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401a7832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401a78af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401a78e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401a794a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401a794a`
- `ntdll!RtlAllocateHeap` at `0x1401a785a`
- `ntdll!RtlAllocateHeap` at `0x1401a785a`
- `ntdll!RtlFreeHeap` at `0x1401a796d`
- `ntdll!RtlFreeHeap` at `0x1401a796d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1401a7891`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1401a7891`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1401a7818`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1401a7818`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1401a78d5`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1401a78d5`

## pseudocode

```c
__int64 __fastcall ValidateFile(const WCHAR *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v5; // r14d
  HANDLE FileW; // rsi
  DWORD LastError; // ebx
  WCHAR *Heap; // rdi
  int v9; // ebx
  DWORD FinalPathNameByHandleW; // eax
  __int64 v11; // r15
  __int64 v12; // rax
  DWORD dwFlags[8]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+78h] [rbp-90h]
  __int64 v16; // [rsp+88h] [rbp-80h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+90h] [rbp-78h] BYREF

  v5 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  v15 = 0;
  v16 = 0;
  dwFlags[0] = 0;
  dwFlags[1] = 1;
  dwFlags[2] = 8;
  dwFlags[3] = 9;
  dwFlags[4] = 10;
  FileW = CreateFileW(a1, 0x80u, 7u, 0, 3u, 0x100080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
  }
  else
  {
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xFFFEu);
    if ( Heap )
    {
      v9 = 0;
      while ( 1 )
      {
        FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, Heap, 0x7FFFu, dwFlags[v9]);
        v11 = FinalPathNameByHandleW;
        if ( FinalPathNameByHandleW )
          break;
        if ( (unsigned int)++v9 >= 5 )
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 2;
          goto LABEL_14;
        }
      }
      if ( GetFileInformationByHandle(FileW, &FileInformation) )
      {
        if ( (FileInformation.dwFileAttributes & 0x10) != 0 )
        {
          LastError = 267;
        }
        else
        {
          try
          {
            v12 = std::wstring::wstring(dwFlags, Heap, v11);
            std::wstring::operator=(a5, v12);
            std::wstring::_Tidy_deallocate(dwFlags);
            LastError = 0;
            v5 = 1;
          }
          catch ( std::bad_alloc )
          {
            LastError = 14;
            v5 = 0;
          }
        }
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = 14;
    }
LABEL_14:
    CloseHandle(FileW);
    if ( Heap )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
  if ( LastError )
    SetLastError(LastError);
  return v5;
}

```

## disassembly

```asm
0x1401a7780  mov     r11, rsp
0x1401a7783  push    rbx
0x1401a7784  push    rsi
0x1401a7785  push    rdi
0x1401a7786  push    r12
0x1401a7788  push    r14
0x1401a778a  push    r15
0x1401a778c  sub     rsp, 0D8h
0x1401a7793  mov     rax, cs:__security_cookie
0x1401a779a  xor     rax, rsp
0x1401a779d  mov     [rsp+108h+var_40], rax
0x1401a77a5  mov     r12, [rsp+108h+arg_20]
0x1401a77ad  xor     r14d, r14d
0x1401a77b0  mov     [rsp+108h+var_C4], r14d
0x1401a77b5  xorps   xmm0, xmm0
0x1401a77b8  xor     eax, eax
0x1401a77ba  movups  xmmword ptr [r11-78h], xmm0
0x1401a77bf  movups  xmmword ptr [r11-68h], xmm0
0x1401a77c4  movups  xmmword ptr [r11-58h], xmm0
0x1401a77c9  mov     [r11-48h], eax
0x1401a77cd  movups  [rsp+108h+var_90], xmm0
0x1401a77d2  mov     [r11-80h], rax
0x1401a77d6  mov     [rsp+108h+dwFlags], eax
0x1401a77da  mov     [rsp+108h+var_AC], 1
0x1401a77e2  lea     ebx, [rax+8]
0x1401a77e5  mov     [rsp+108h+var_A8], ebx
0x1401a77e9  mov     [rsp+108h+var_A4], 9
0x1401a77f1  mov     [rsp+108h+var_A0], 0Ah
0x1401a77f9  mov     [rsp+108h+hTemplateFile], rax; hTemplateFile
0x1401a77fe  mov     [rsp+108h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1401a7806  mov     [rsp+108h+dwCreationDisposition], 3; dwCreationDisposition
0x1401a780e  xor     r9d, r9d; lpSecurityAttributes
0x1401a7811  lea     edx, [rbx+78h]; dwDesiredAccess
0x1401a7814  lea     r8d, [r14+7]; dwShareMode
0x1401a7818  call    cs:__imp_CreateFileW
0x1401a781f  nop     dword ptr [rax+rax+00h]
0x1401a7824  mov     rsi, rax
0x1401a7827  mov     [rsp+108h+var_C0], rax
0x1401a782c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401a7830  jnz     short loc_1401A7845
0x1401a7832  call    cs:__imp_GetLastError
0x1401a7839  nop     dword ptr [rax+rax+00h]
0x1401a783e  mov     ebx, eax
0x1401a7840  jmp     loc_1401A7979
0x1401a7845  mov     rcx, gs:60h
0x1401a784e  mov     r8d, 0FFFEh; Size
0x1401a7854  mov     edx, ebx; Flags
0x1401a7856  mov     rcx, [rcx+30h]; HeapHandle
0x1401a785a  call    cs:__imp_RtlAllocateHeap
0x1401a7861  nop     dword ptr [rax+rax+00h]
0x1401a7866  mov     rdi, rax
0x1401a7869  mov     [rsp+108h+var_B8], rax
0x1401a786e  test    rax, rax
0x1401a7871  jnz     short loc_1401A787B
0x1401a7873  lea     ebx, [rax+0Eh]
0x1401a7876  jmp     loc_1401A7947
0x1401a787b  xor     ebx, ebx
0x1401a787d  movsxd  r9, ebx
0x1401a7880  mov     r9d, [rsp+r9*4+108h+dwFlags]; dwFlags
0x1401a7885  mov     r8d, 7FFFh; cchFilePath
0x1401a788b  mov     rdx, rdi; lpszFilePath
0x1401a788e  mov     rcx, rsi; hFile
0x1401a7891  call    cs:__imp_GetFinalPathNameByHandleW
0x1401a7898  nop     dword ptr [rax+rax+00h]
0x1401a789d  mov     r15d, eax
0x1401a78a0  test    eax, eax
0x1401a78a2  jnz     short loc_1401A78CA
0x1401a78a4  inc     ebx
0x1401a78a6  cmp     ebx, 5
0x1401a78a9  jb      short loc_1401A787D
0x1401a78ab  test    eax, eax
0x1401a78ad  jnz     short loc_1401A78CA
0x1401a78af  call    cs:__imp_GetLastError
0x1401a78b6  nop     dword ptr [rax+rax+00h]
0x1401a78bb  mov     ebx, eax
0x1401a78bd  test    eax, eax
0x1401a78bf  jnz     loc_1401A7947
0x1401a78c5  lea     ebx, [rax+2]
0x1401a78c8  jmp     short loc_1401A7947
0x1401a78ca  lea     rdx, [rsp+108h+FileInformation]; lpFileInformation
0x1401a78d2  mov     rcx, rsi; hFile
0x1401a78d5  call    cs:__imp_GetFileInformationByHandle
0x1401a78dc  nop     dword ptr [rax+rax+00h]
0x1401a78e1  test    eax, eax
0x1401a78e3  jnz     short loc_1401A78F5
0x1401a78e5  call    cs:__imp_GetLastError
0x1401a78ec  nop     dword ptr [rax+rax+00h]
0x1401a78f1  mov     ebx, eax
0x1401a78f3  jmp     short loc_1401A7947
0x1401a78f5  test    byte ptr [rsp+108h+FileInformation.dwFileAttributes], 10h
0x1401a78fd  jz      short loc_1401A7906
0x1401a78ff  mov     ebx, 10Bh
0x1401a7904  jmp     short loc_1401A7947
0x1401a7906  mov     r8, r15
0x1401a7909  mov     rdx, rdi
0x1401a790c  lea     rcx, [rsp+108h+dwFlags]
0x1401a7911  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1401a7916  mov     rdx, rax
0x1401a7919  mov     rcx, r12
0x1401a791c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1401a7921  lea     rcx, [rsp+108h+dwFlags]
0x1401a7926  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1401a792b  nop
0x1401a792c  xor     ebx, ebx
0x1401a792e  lea     r14d, [rbx+1]
0x1401a7932  jmp     short loc_1401A7947
0x1401a7934  mov     ebx, [rsp+108h+var_C8]
0x1401a7938  mov     r14d, [rsp+108h+var_C4]
0x1401a793d  mov     rsi, [rsp+108h+var_C0]
0x1401a7942  mov     rdi, [rsp+108h+var_B8]
0x1401a7947  mov     rcx, rsi; hObject
0x1401a794a  call    cs:__imp_CloseHandle
0x1401a7951  nop     dword ptr [rax+rax+00h]
0x1401a7956  test    rdi, rdi
0x1401a7959  jz      short loc_1401A7979
0x1401a795b  mov     rcx, gs:60h
0x1401a7964  mov     r8, rdi; P
0x1401a7967  xor     edx, edx; Flags
0x1401a7969  mov     rcx, [rcx+30h]; HeapHandle
0x1401a796d  call    cs:__imp_RtlFreeHeap
0x1401a7974  nop     dword ptr [rax+rax+00h]
0x1401a7979  test    ebx, ebx
0x1401a797b  jz      short loc_1401A798B
0x1401a797d  mov     ecx, ebx; dwErrCode
0x1401a797f  call    cs:__imp_SetLastError
0x1401a7986  nop     dword ptr [rax+rax+00h]
0x1401a798b  mov     eax, r14d
0x1401a798e  mov     rcx, [rsp+108h+var_40]
0x1401a7996  xor     rcx, rsp; StackCookie
0x1401a7999  call    __security_check_cookie
0x1401a799e  add     rsp, 0D8h
0x1401a79a5  pop     r15
0x1401a79a7  pop     r14
0x1401a79a9  pop     r12
0x1401a79ab  pop     rdi
0x1401a79ac  pop     rsi
0x1401a79ad  pop     rbx
0x1401a79ae  retn
```
