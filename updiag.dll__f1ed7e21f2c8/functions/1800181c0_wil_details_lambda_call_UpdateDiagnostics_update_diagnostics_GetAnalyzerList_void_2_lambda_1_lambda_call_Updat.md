# wil::details::lambda_call<`UpdateDiagnostics::update_diagnostics::GetAnalyzerList(void)'::`2'::_lambda_1_>::~lambda_call<`UpdateDiagnostics::update_diagnostics::GetAnalyzerList(void)'::`2'::_lambda_1_>(void)

- ea: `0x1800181c0`
- end: `0x180018203`
- name: `??1?$lambda_call@V_lambda_1_@?1??GetAnalyzerList@update_diagnostics@UpdateDiagnostics@@QEAA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ@@details@wil@@QEAA@XZ`
- size: `67`
- prototype: `_DWORD *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18009820d`

## callees

- `0x1800181c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800181e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800181e9`

## pseudocode

```c
_DWORD *__fastcall __1__lambda_call_V_lambda_1___1__GetAnalyzerList_update_diagnostics_UpdateDiagnostics__QEAA_AV__vector_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__V__allocator_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__std__XZ__details_wil__QEAA_XZ(
        __int64 a1)
{
  __int64 v1; // rbx
  _DWORD *result; // rax

  v1 = 0;
  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    result = *(_DWORD **)a1;
    if ( **(_DWORD **)a1 )
    {
      do
      {
        WindowsDeleteString(*(HSTRING *)(**(_QWORD **)(a1 + 8) + 8 * v1));
        result = *(_DWORD **)a1;
        v1 = (unsigned int)(v1 + 1);
      }
      while ( (unsigned int)v1 < **(_DWORD **)a1 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800181c0  mov     [rsp+arg_0], rbx
0x1800181c5  push    rdi
0x1800181c6  sub     rsp, 20h
0x1800181ca  xor     ebx, ebx
0x1800181cc  mov     rdi, rcx
0x1800181cf  cmp     [rcx+10h], bl
0x1800181d2  jz      short loc_1800181F8
0x1800181d4  mov     [rcx+10h], bl
0x1800181d7  mov     rax, [rcx]
0x1800181da  cmp     [rax], ebx
0x1800181dc  jbe     short loc_1800181F8
0x1800181de  mov     rax, [rdi+8]
0x1800181e2  mov     rcx, [rax]
0x1800181e5  mov     rcx, [rcx+rbx*8]; string
0x1800181e9  call    cs:__imp_WindowsDeleteString
0x1800181ef  mov     rax, [rdi]
0x1800181f2  inc     ebx
0x1800181f4  cmp     ebx, [rax]
0x1800181f6  jb      short loc_1800181DE
0x1800181f8  mov     rbx, [rsp+28h+arg_0]
0x1800181fd  add     rsp, 20h
0x180018201  pop     rdi
0x180018202  retn
```
