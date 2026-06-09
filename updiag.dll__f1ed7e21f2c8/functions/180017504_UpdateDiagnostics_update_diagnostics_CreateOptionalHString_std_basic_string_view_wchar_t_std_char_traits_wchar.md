# UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x180017504`
- end: `0x180017596`
- name: `?_CreateOptionalHString@update_diagnostics@UpdateDiagnostics@@CAPEAUHSTRING__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180016e7c`
- `0x18001759c`

## callees

- `0x180009548`
- `0x180017504`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017544`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017544`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017531`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001755a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001755a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001753c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001753c`

## pseudocode

```c
HSTRING __fastcall UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(__int64 a1, HSTRING *a2)
{
  HSTRING v5; // rbp
  DWORD LastError; // ebx
  UINT32 v7; // edx
  const WCHAR *v8; // rcx
  HRESULT String; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !*(_QWORD *)(a1 + 8) )
    return 0;
  v5 = *a2;
  if ( *a2 )
  {
    LastError = GetLastError();
    WindowsDeleteString(v5);
    SetLastError(LastError);
  }
  v7 = *(_DWORD *)(a1 + 8);
  v8 = *(const WCHAR **)a1;
  *a2 = 0;
  String = WindowsCreateString(v8, v7, a2);
  if ( String < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
      (const char *)(unsigned int)String,
      v10);
  return *a2;
}

```

## disassembly

```asm
0x180017504  mov     [rsp+arg_0], rbx
0x180017509  mov     [rsp+arg_8], rbp
0x18001750e  mov     [rsp+arg_10], rsi
0x180017513  push    rdi; int
0x180017514  sub     rsp, 20h
0x180017518  cmp     qword ptr [rcx+8], 0
0x18001751d  mov     rdi, rdx
0x180017520  mov     rsi, rcx
0x180017523  jnz     short loc_180017529
0x180017525  xor     eax, eax
0x180017527  jmp     short loc_180017567
0x180017529  mov     rbp, [rdx]
0x18001752c  test    rbp, rbp
0x18001752f  jz      short loc_18001754A
0x180017531  call    cs:__imp_GetLastError
0x180017537  mov     rcx, rbp; string
0x18001753a  mov     ebx, eax
0x18001753c  call    cs:__imp_WindowsDeleteString
0x180017542  mov     ecx, ebx; dwErrCode
0x180017544  call    cs:__imp_SetLastError
0x18001754a  mov     edx, [rsi+8]; length
0x18001754d  mov     r8, rdi; string
0x180017550  mov     rcx, [rsi]; sourceString
0x180017553  mov     qword ptr [rdi], 0
0x18001755a  call    cs:__imp_WindowsCreateString
0x180017560  test    eax, eax
0x180017562  js      short loc_18001757C
0x180017564  mov     rax, [rdi]
0x180017567  mov     rbx, [rsp+28h+arg_0]
0x18001756c  mov     rbp, [rsp+28h+arg_8]
0x180017571  mov     rsi, [rsp+28h+arg_10]
0x180017576  add     rsp, 20h
0x18001757a  pop     rdi
0x18001757b  retn
0x18001757c  mov     rcx, [rsp+28h]; this
0x180017581  lea     r8, aCW1SSrcCalliop_0; "C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDi"...
0x180017588  mov     r9d, eax; char *
0x18001758b  mov     edx, 1BBh; void *
0x180017590  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
