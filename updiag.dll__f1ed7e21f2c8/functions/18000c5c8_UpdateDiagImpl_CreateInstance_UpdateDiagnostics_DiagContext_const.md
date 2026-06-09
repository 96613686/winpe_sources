# UpdateDiagImpl::CreateInstance(UpdateDiagnostics::DiagContext const *)

- ea: `0x18000c5c8`
- end: `0x18000c6d1`
- name: `?CreateInstance@UpdateDiagImpl@@SAPEAXPEBUDiagContext@UpdateDiagnostics@@@Z`
- size: `265`
- prototype: `void *__fastcall(const struct UpdateDiagnostics::DiagContext *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180008a40`
- `0x18000ef98`

## callees

- `0x180008a2c`
- `0x180009548`
- `0x18000c5c8`
- `0x18000df84`
- `0x18000e050`
- `0x180095af0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c650`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c650`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c658`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c645`

## string_xrefs

- `0x18000c6a7`: `C:\__w\1\s\src\Calliope\libs\api\UpdateDiagImpl.cpp`
- `0x18000c6bf`: `C:\__w\1\s\src\Calliope\libs\api\UpdateDiagImpl.cpp`

## pseudocode

```c
void *__fastcall UpdateDiagImpl::CreateInstance(const struct UpdateDiagnostics::DiagContext *a1)
{
  void *v2; // rdi
  HINSTANCE ThisHandle; // rbp
  HMODULE v4; // rsi
  DWORD LastError; // ebx
  unsigned int v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\api\\UpdateDiagImpl.cpp",
      (const char *)0x80070057LL,
      v10);
  if ( *(_QWORD *)a1 != 24 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\api\\UpdateDiagImpl.cpp",
      (const char *)0x80070057LL,
      v10);
  v2 = operator new(0x18u);
  *(_OWORD *)v2 = 0;
  *((_QWORD *)v2 + 2) = 0;
  *(_QWORD *)v2 = &UpdateDiagImpl::`vftable';
  *((_DWORD *)v2 + 2) = *((_DWORD *)a1 + 2);
  *((_QWORD *)v2 + 2) = 0;
  ThisHandle = DiagUtils::GetThisHandle(0);
  v4 = (HMODULE)*((_QWORD *)v2 + 2);
  if ( v4 )
  {
    LastError = GetLastError();
    FreeLibrary(v4);
    SetLastError(LastError);
  }
  *((_QWORD *)v2 + 2) = ThisHandle;
  if ( *((_DWORD *)v2 + 2) != 1 )
  {
    v7 = wil::verify_hresult<long>(2147500034LL);
    wil::details::in1diag3::Throw_Hr(retaddr, v8, v9, (const char *)v7, v10);
  }
  return v2;
}

```

## disassembly

```asm
0x18000c5c8  mov     [rsp+arg_8], rbx
0x18000c5cd  mov     [rsp+arg_10], rbp
0x18000c5d2  mov     [rsp+arg_18], rsi
0x18000c5d7  push    rdi; int
0x18000c5d8  sub     rsp, 20h
0x18000c5dc  mov     rbx, rcx
0x18000c5df  mov     rcx, [rsp+28h]; this
0x18000c5e4  test    rbx, rbx
0x18000c5e7  jz      loc_18000C6A1
0x18000c5ed  mov     rcx, [rsp+28h]; this
0x18000c5f2  cmp     qword ptr [rbx], 18h
0x18000c5f6  jnz     loc_18000C6B9
0x18000c5fc  mov     ecx, 18h; Size
0x18000c601  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c606  mov     rdi, rax
0x18000c609  mov     [rsp+28h+arg_0], rax
0x18000c60e  xorps   xmm0, xmm0
0x18000c611  xor     eax, eax
0x18000c613  movups  xmmword ptr [rdi], xmm0
0x18000c616  mov     [rdi+10h], rax
0x18000c61a  lea     rax, ??_7UpdateDiagImpl@@6B@; const UpdateDiagImpl::`vftable'
0x18000c621  mov     [rdi], rax
0x18000c624  mov     ecx, [rbx+8]
0x18000c627  mov     [rdi+8], ecx
0x18000c62a  mov     qword ptr [rdi+10h], 0
0x18000c632  xor     ecx, ecx; bool
0x18000c634  call    ?GetThisHandle@DiagUtils@@SAPEAUHINSTANCE__@@_N@Z; DiagUtils::GetThisHandle(bool)
0x18000c639  mov     rbp, rax
0x18000c63c  mov     rsi, [rdi+10h]
0x18000c640  test    rsi, rsi
0x18000c643  jz      short loc_18000C65E
0x18000c645  call    cs:__imp_GetLastError
0x18000c64b  mov     ebx, eax
0x18000c64d  mov     rcx, rsi; hLibModule
0x18000c650  call    cs:__imp_FreeLibrary
0x18000c656  mov     ecx, ebx; dwErrCode
0x18000c658  call    cs:__imp_SetLastError
0x18000c65e  mov     [rdi+10h], rbp
0x18000c662  mov     [rsp+28h+arg_0], 0
0x18000c66b  cmp     dword ptr [rdi+8], 1
0x18000c66f  jnz     short loc_18000C689
0x18000c671  mov     rax, rdi
0x18000c674  mov     rbx, [rsp+28h+arg_8]
0x18000c679  mov     rbp, [rsp+28h+arg_10]
0x18000c67e  mov     rsi, [rsp+28h+arg_18]
0x18000c683  add     rsp, 20h
0x18000c687  pop     rdi
0x18000c688  retn
0x18000c689  mov     ecx, 80004002h
0x18000c68e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000c693  mov     r9d, eax; char *
0x18000c696  mov     rcx, [rsp+28h]; this
0x18000c69b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c6a1  mov     r9d, 80070057h; char *
0x18000c6a7  lea     r8, aCW1SSrcCalliop_18; "C:\\__w\\1\\s\\src\\Calliope\\libs\\api"...
0x18000c6ae  mov     edx, 10h; void *
0x18000c6b3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c6b9  mov     r9d, 80070057h; char *
0x18000c6bf  lea     r8, aCW1SSrcCalliop_18; "C:\\__w\\1\\s\\src\\Calliope\\libs\\api"...
0x18000c6c6  mov     edx, 12h; void *
0x18000c6cb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
