# GetMarkOfTheWebFromFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180023220`
- end: `0x180023432`
- name: `?GetMarkOfTheWebFromFile@@YA?AUMarkOfTheWeb@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `530`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180021b00`
- `0x180021e84`
- `0x180023dbc`

## callees

- `0x180006bd4`
- `0x180021600`
- `0x180021868`
- `0x180023220`
- `0x180023890`
- `0x180024574`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180023343`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180023343`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800233a9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800233a9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023300`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023300`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetMarkOfTheWebFromFile(__int64 a1, const WCHAR *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rbx
  HANDLE FileW; // rbx
  const char *v7; // r9
  __int64 result; // rax
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-48h] BYREF
  LPVOID lpBuffer[8]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+10h] BYREF
  int v15; // [rsp+A0h] [rbp+18h]
  HANDLE v16; // [rsp+A8h] [rbp+20h] BYREF

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v4 = a1 + 32;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 7;
  *(_WORD *)(a1 + 32) = 0;
  *(_OWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 7;
  *(_WORD *)(a1 + 64) = 0;
  v5 = a1 + 96;
  *(_OWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 7;
  *(_WORD *)(a1 + 96) = 0;
  v15 = 1;
  std::wstring::_Assign<unsigned short>(a1, L"3", 1);
  std::wstring::_Assign<unsigned short>(v4, &Class, 0);
  std::wstring::_Assign<unsigned short>(v5, &Class, 0);
  try
  {
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const WCHAR **)a2;
    FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v16 = FileW;
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      FileSize.QuadPart = 0;
      if ( GetFileSizeEx(FileW, &FileSize) && FileSize.QuadPart <= 4096 )
      {
        std::vector<char>::vector<char>(lpBuffer);
        NumberOfBytesRead = 0;
        if ( ReadFile(FileW, lpBuffer[0], FileSize.LowPart, &NumberOfBytesRead, 0)
          && NumberOfBytesRead == FileSize.QuadPart )
        {
          ParseMotwData(lpBuffer, a1);
          std::vector<unsigned char>::_Tidy(lpBuffer);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
          result = a1;
        }
        else
        {
          std::vector<unsigned char>::_Tidy(lpBuffer);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
          result = a1;
        }
      }
      else
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
        result = a1;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
      result = a1;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xCE,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      v7);
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x180023220  mov     r11, rsp
0x180023223  mov     [r11+8], rcx
0x180023227  push    rbx
0x180023228  push    rsi
0x180023229  push    rdi
0x18002322a  push    r12
0x18002322c  push    r14
0x18002322e  sub     rsp, 60h
0x180023232  mov     r14, rdx
0x180023235  mov     rsi, rcx
0x180023238  mov     dword ptr [r11+18h], 1
0x180023240  xorps   xmm0, xmm0
0x180023243  movups  xmmword ptr [rcx], xmm0
0x180023246  mov     qword ptr [rcx+10h], 0
0x18002324e  mov     r12d, 7
0x180023254  mov     [rcx+18h], r12
0x180023258  xor     eax, eax
0x18002325a  mov     [rcx], ax
0x18002325d  lea     rdi, [rcx+20h]
0x180023261  movups  xmmword ptr [rdi], xmm0
0x180023264  mov     [rdi+10h], rax
0x180023268  mov     [rdi+18h], r12
0x18002326c  mov     [rdi], ax
0x18002326f  movups  xmmword ptr [rcx+40h], xmm0
0x180023273  mov     [rcx+50h], rax
0x180023277  mov     [rcx+58h], r12
0x18002327b  mov     [rcx+40h], ax
0x18002327f  lea     rbx, [rcx+60h]
0x180023283  movups  xmmword ptr [rbx], xmm0
0x180023286  mov     [rbx+10h], rax
0x18002328a  mov     [rbx+18h], r12
0x18002328e  mov     [rbx], ax
0x180023291  mov     dword ptr [r11+18h], 1
0x180023299  lea     r8d, [r12-6]
0x18002329e  lea     rdx, a3; "3"
0x1800232a5  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800232aa  xor     r8d, r8d
0x1800232ad  lea     rdx, Class
0x1800232b4  mov     rcx, rdi
0x1800232b7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800232bc  xor     r8d, r8d
0x1800232bf  lea     rdx, Class
0x1800232c6  mov     rcx, rbx
0x1800232c9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800232ce  nop
0x1800232cf  cmp     [r14+18h], r12
0x1800232d3  jbe     short loc_1800232D8
0x1800232d5  mov     r14, [r14]
0x1800232d8  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x1800232e1  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800232e9  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x1800232f1  xor     r9d, r9d; lpSecurityAttributes
0x1800232f4  mov     edx, 80000000h; dwDesiredAccess
0x1800232f9  lea     r8d, [r9+1]; dwShareMode
0x1800232fd  mov     rcx, r14; lpFileName
0x180023300  call    cs:__imp_CreateFileW
0x180023306  mov     rbx, rax
0x180023309  mov     [rsp+88h+arg_18], rax
0x180023311  inc     rax
0x180023314  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002331a  jnz     short loc_180023332
0x18002331c  lea     rcx, [rsp+88h+arg_18]
0x180023324  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180023329  nop
0x18002332a  mov     rax, rsi
0x18002332d  jmp     loc_180023426
0x180023332  mov     qword ptr [rsp+88h+FileSize], 0
0x18002333b  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x180023340  mov     rcx, rbx; hFile
0x180023343  call    cs:__imp_GetFileSizeEx
0x180023349  test    eax, eax
0x18002334b  jnz     short loc_180023363
0x18002334d  lea     rcx, [rsp+88h+arg_18]
0x180023355  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002335a  nop
0x18002335b  mov     rax, rsi
0x18002335e  jmp     loc_180023426
0x180023363  mov     rdx, qword ptr [rsp+88h+FileSize]
0x180023368  cmp     rdx, 1000h
0x18002336f  jg      loc_18002340B
0x180023375  lea     rcx, [rsp+88h+lpBuffer]
0x18002337a  call    ??0?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,std::allocator<char> const &)
0x18002337f  nop
0x180023380  mov     [rsp+88h+NumberOfBytesRead], 0
0x18002338b  mov     qword ptr [rsp+88h+dwCreationDisposition], 0; lpOverlapped
0x180023394  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002339c  mov     r8d, dword ptr [rsp+88h+FileSize]; nNumberOfBytesToRead
0x1800233a1  mov     rdx, [rsp+88h+lpBuffer]; lpBuffer
0x1800233a6  mov     rcx, rbx; hFile
0x1800233a9  call    cs:__imp_ReadFile
0x1800233af  test    eax, eax
0x1800233b1  jz      short loc_1800233ED
0x1800233b3  mov     eax, [rsp+88h+NumberOfBytesRead]
0x1800233ba  cmp     rax, qword ptr [rsp+88h+FileSize]
0x1800233bf  jnz     short loc_1800233ED
0x1800233c1  mov     rdx, rsi
0x1800233c4  lea     rcx, [rsp+88h+lpBuffer]
0x1800233c9  call    ?ParseMotwData@@YAXAEBV?$vector@DV?$allocator@D@std@@@std@@AEAUMarkOfTheWeb@@@Z; ParseMotwData(std::vector<char> const &,MarkOfTheWeb &)
0x1800233ce  nop
0x1800233cf  lea     rcx, [rsp+88h+lpBuffer]
0x1800233d4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800233d9  nop
0x1800233da  lea     rcx, [rsp+88h+arg_18]
0x1800233e2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800233e7  nop
0x1800233e8  mov     rax, rsi
0x1800233eb  jmp     short loc_180023426
0x1800233ed  lea     rcx, [rsp+88h+lpBuffer]
0x1800233f2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800233f7  nop
0x1800233f8  lea     rcx, [rsp+88h+arg_18]
0x180023400  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180023405  nop
0x180023406  mov     rax, rsi
0x180023409  jmp     short loc_180023426
0x18002340b  lea     rcx, [rsp+88h+arg_18]
0x180023413  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180023418  nop
0x180023419  mov     rax, rsi
0x18002341c  jmp     short loc_180023426
0x18002341e  mov     rax, [rsp+88h+arg_0]
0x180023426  add     rsp, 60h
0x18002342a  pop     r14
0x18002342c  pop     r12
0x18002342e  pop     rdi
0x18002342f  pop     rsi
0x180023430  pop     rbx
0x180023431  retn
```
