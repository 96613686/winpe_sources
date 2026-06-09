# ValidateFile(ushort const *,ulong,ulong,void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1401b86a0`
- end: `0x1401b88d0`
- name: `?ValidateFile@@YAHPEBGKKPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1401b9c30`

## callees

- `0x140030120`
- `0x140031ca8`
- `0x140132960`
- `0x1401b6af8`
- `0x1401b86a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1401b889f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1401b889f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b8752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b87cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b8805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b8752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b87cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b8805`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b886a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b886a`
- `ntdll!RtlAllocateHeap` at `0x1401b877a`
- `ntdll!RtlAllocateHeap` at `0x1401b877a`
- `ntdll!RtlFreeHeap` at `0x1401b888d`
- `ntdll!RtlFreeHeap` at `0x1401b888d`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1401b87f5`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1401b87f5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1401b87b1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1401b87b1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1401b8738`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1401b8738`

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
0x1401b86a0  mov     r11, rsp
0x1401b86a3  push    rbx
0x1401b86a4  push    rsi
0x1401b86a5  push    rdi
0x1401b86a6  push    r12
0x1401b86a8  push    r14
0x1401b86aa  push    r15
0x1401b86ac  sub     rsp, 0D8h
0x1401b86b3  mov     rax, cs:__security_cookie
0x1401b86ba  xor     rax, rsp
0x1401b86bd  mov     [rsp+108h+var_40], rax
0x1401b86c5  mov     r12, [rsp+108h+arg_20]
0x1401b86cd  xor     r14d, r14d
0x1401b86d0  mov     [rsp+108h+var_C4], r14d
0x1401b86d5  xorps   xmm0, xmm0
0x1401b86d8  xor     eax, eax
0x1401b86da  movups  xmmword ptr [r11-78h], xmm0
0x1401b86df  movups  xmmword ptr [r11-68h], xmm0
0x1401b86e4  movups  xmmword ptr [r11-58h], xmm0
0x1401b86e9  mov     [r11-48h], eax
0x1401b86ed  movups  [rsp+108h+var_90], xmm0
0x1401b86f2  mov     [r11-80h], rax
0x1401b86f6  mov     [rsp+108h+dwFlags], eax
0x1401b86fa  mov     [rsp+108h+var_AC], 1
0x1401b8702  lea     ebx, [rax+8]
0x1401b8705  mov     [rsp+108h+var_A8], ebx
0x1401b8709  mov     [rsp+108h+var_A4], 9
0x1401b8711  mov     [rsp+108h+var_A0], 0Ah
0x1401b8719  mov     [rsp+108h+hTemplateFile], rax; hTemplateFile
0x1401b871e  mov     [rsp+108h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1401b8726  mov     [rsp+108h+dwCreationDisposition], 3; dwCreationDisposition
0x1401b872e  xor     r9d, r9d; lpSecurityAttributes
0x1401b8731  lea     edx, [rbx+78h]; dwDesiredAccess
0x1401b8734  lea     r8d, [r14+7]; dwShareMode
0x1401b8738  call    cs:__imp_CreateFileW
0x1401b873f  nop     dword ptr [rax+rax+00h]
0x1401b8744  mov     rsi, rax
0x1401b8747  mov     [rsp+108h+var_C0], rax
0x1401b874c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401b8750  jnz     short loc_1401B8765
0x1401b8752  call    cs:__imp_GetLastError
0x1401b8759  nop     dword ptr [rax+rax+00h]
0x1401b875e  mov     ebx, eax
0x1401b8760  jmp     loc_1401B8899
0x1401b8765  mov     rcx, gs:60h
0x1401b876e  mov     r8d, 0FFFEh; Size
0x1401b8774  mov     edx, ebx; Flags
0x1401b8776  mov     rcx, [rcx+30h]; HeapHandle
0x1401b877a  call    cs:__imp_RtlAllocateHeap
0x1401b8781  nop     dword ptr [rax+rax+00h]
0x1401b8786  mov     rdi, rax
0x1401b8789  mov     [rsp+108h+var_B8], rax
0x1401b878e  test    rax, rax
0x1401b8791  jnz     short loc_1401B879B
0x1401b8793  lea     ebx, [rax+0Eh]
0x1401b8796  jmp     loc_1401B8867
0x1401b879b  xor     ebx, ebx
0x1401b879d  movsxd  r9, ebx
0x1401b87a0  mov     r9d, [rsp+r9*4+108h+dwFlags]; dwFlags
0x1401b87a5  mov     r8d, 7FFFh; cchFilePath
0x1401b87ab  mov     rdx, rdi; lpszFilePath
0x1401b87ae  mov     rcx, rsi; hFile
0x1401b87b1  call    cs:__imp_GetFinalPathNameByHandleW
0x1401b87b8  nop     dword ptr [rax+rax+00h]
0x1401b87bd  mov     r15d, eax
0x1401b87c0  test    eax, eax
0x1401b87c2  jnz     short loc_1401B87EA
0x1401b87c4  inc     ebx
0x1401b87c6  cmp     ebx, 5
0x1401b87c9  jb      short loc_1401B879D
0x1401b87cb  test    eax, eax
0x1401b87cd  jnz     short loc_1401B87EA
0x1401b87cf  call    cs:__imp_GetLastError
0x1401b87d6  nop     dword ptr [rax+rax+00h]
0x1401b87db  mov     ebx, eax
0x1401b87dd  test    eax, eax
0x1401b87df  jnz     loc_1401B8867
0x1401b87e5  lea     ebx, [rax+2]
0x1401b87e8  jmp     short loc_1401B8867
0x1401b87ea  lea     rdx, [rsp+108h+FileInformation]; lpFileInformation
0x1401b87f2  mov     rcx, rsi; hFile
0x1401b87f5  call    cs:__imp_GetFileInformationByHandle
0x1401b87fc  nop     dword ptr [rax+rax+00h]
0x1401b8801  test    eax, eax
0x1401b8803  jnz     short loc_1401B8815
0x1401b8805  call    cs:__imp_GetLastError
0x1401b880c  nop     dword ptr [rax+rax+00h]
0x1401b8811  mov     ebx, eax
0x1401b8813  jmp     short loc_1401B8867
0x1401b8815  test    byte ptr [rsp+108h+FileInformation.dwFileAttributes], 10h
0x1401b881d  jz      short loc_1401B8826
0x1401b881f  mov     ebx, 10Bh
0x1401b8824  jmp     short loc_1401B8867
0x1401b8826  mov     r8, r15
0x1401b8829  mov     rdx, rdi
0x1401b882c  lea     rcx, [rsp+108h+dwFlags]
0x1401b8831  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1401b8836  mov     rdx, rax
0x1401b8839  mov     rcx, r12
0x1401b883c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1401b8841  lea     rcx, [rsp+108h+dwFlags]
0x1401b8846  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1401b884b  nop
0x1401b884c  xor     ebx, ebx
0x1401b884e  lea     r14d, [rbx+1]
0x1401b8852  jmp     short loc_1401B8867
0x1401b8854  mov     ebx, [rsp+108h+var_C8]
0x1401b8858  mov     r14d, [rsp+108h+var_C4]
0x1401b885d  mov     rsi, [rsp+108h+var_C0]
0x1401b8862  mov     rdi, [rsp+108h+var_B8]
0x1401b8867  mov     rcx, rsi; hObject
0x1401b886a  call    cs:__imp_CloseHandle
0x1401b8871  nop     dword ptr [rax+rax+00h]
0x1401b8876  test    rdi, rdi
0x1401b8879  jz      short loc_1401B8899
0x1401b887b  mov     rcx, gs:60h
0x1401b8884  mov     r8, rdi; P
0x1401b8887  xor     edx, edx; Flags
0x1401b8889  mov     rcx, [rcx+30h]; HeapHandle
0x1401b888d  call    cs:__imp_RtlFreeHeap
0x1401b8894  nop     dword ptr [rax+rax+00h]
0x1401b8899  test    ebx, ebx
0x1401b889b  jz      short loc_1401B88AB
0x1401b889d  mov     ecx, ebx; dwErrCode
0x1401b889f  call    cs:__imp_SetLastError
0x1401b88a6  nop     dword ptr [rax+rax+00h]
0x1401b88ab  mov     eax, r14d
0x1401b88ae  mov     rcx, [rsp+108h+var_40]
0x1401b88b6  xor     rcx, rsp; StackCookie
0x1401b88b9  call    __security_check_cookie
0x1401b88be  add     rsp, 0D8h
0x1401b88c5  pop     r15
0x1401b88c7  pop     r14
0x1401b88c9  pop     r12
0x1401b88cb  pop     rdi
0x1401b88cc  pop     rsi
0x1401b88cd  pop     rbx
0x1401b88ce  retn
```
