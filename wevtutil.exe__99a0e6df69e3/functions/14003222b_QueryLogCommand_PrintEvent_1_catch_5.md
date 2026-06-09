# _QueryLogCommand::PrintEvent_::_1_::catch$5

- ea: `0x14003222b`
- end: `0x140032306`
- name: `_QueryLogCommand::PrintEvent_::_1_::catch$5`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14000cabc`
- `0x14000cc04`
- `0x14000d144`
- `0x14000d7e4`
- `0x14000d868`
- `0x14000d8c4`
- `0x14003222b`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140032246`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140032246`

## pseudocode

```c
__int64 __fastcall QueryLogCommand::PrintEvent_::_1_::catch_5(__int64 a1, _QWORD *a2)
{
  unsigned int v3; // ebx
  HANDLE StdHandle; // rdi
  void *v5; // rax

  v3 = *(_DWORD *)(a2[6] + 24LL);
  StdHandle = GetStdHandle(0xFFFFFFF4);
  a2[4] = L"Failed to render events.";
  a2[5] = 24;
  FilePuts(StdHandle, a2 + 4);
  std::wstring::wstring(a2 + 7, L" Error=");
  std::to_wstring(a2 + 11, v3);
  v5 = (void *)std::wstring::_Append<wchar_t>(a2 + 7);
  std::wstring::_Append<wchar_t>(v5);
  std::wstring::_Tidy_deallocate(a2 + 11);
  *((_OWORD *)a2 + 2) = *(_OWORD *)std::wstring::operator std::wstring_view(a2 + 7, a2 + 11);
  FilePuts(StdHandle, a2 + 4);
  std::wstring::_Tidy_deallocate(a2 + 7);
  return 0;
}

```

## disassembly

```asm
0x14003222b  mov     [rsp+arg_8], rdx
0x140032230  push    rbx
0x140032231  push    rbp
0x140032232  push    rdi
0x140032233  sub     rsp, 20h
0x140032237  mov     rbp, rdx
0x14003223a  mov     rax, [rbp+30h]
0x14003223e  mov     ebx, [rax+18h]
0x140032241  mov     ecx, 0FFFFFFF4h; nStdHandle
0x140032246  call    cs:__imp_GetStdHandle
0x14003224c  mov     rdi, rax
0x14003224f  lea     rax, aFailedToRender; "Failed to render events."
0x140032256  mov     [rbp+20h], rax
0x14003225a  mov     qword ptr [rbp+28h], 18h
0x140032262  lea     rdx, [rbp+20h]
0x140032266  mov     rcx, rdi; hFile
0x140032269  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x14003226e  nop
0x14003226f  lea     rdx, aError; " Error="
0x140032276  lea     rcx, [rbp+38h]
0x14003227a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14003227f  nop
0x140032280  mov     edx, ebx
0x140032282  lea     rcx, [rbp+58h]
0x140032286  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@I@Z; std::to_wstring(uint)
0x14003228b  nop
0x14003228c  mov     r8, [rax+10h]
0x140032290  cmp     qword ptr [rax+18h], 7
0x140032295  jbe     short loc_14003229A
0x140032297  mov     rax, [rax]
0x14003229a  mov     rdx, rax
0x14003229d  lea     rcx, [rbp+38h]; Src
0x1400322a1  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1400322a6  mov     r8d, 4
0x1400322ac  lea     rdx, asc_140037960; "\r\n\r\n"
0x1400322b3  mov     rcx, rax; Src
0x1400322b6  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1400322bb  nop
0x1400322bc  lea     rcx, [rbp+58h]
0x1400322c0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400322c5  lea     rdx, [rbp+58h]
0x1400322c9  lea     rcx, [rbp+38h]
0x1400322cd  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1400322d2  movups  xmm0, xmmword ptr [rax]
0x1400322d5  movdqu  xmmword ptr [rbp+20h], xmm0
0x1400322da  lea     rdx, [rbp+20h]
0x1400322de  mov     rcx, rdi; hFile
0x1400322e1  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x1400322e6  nop
0x1400322e7  lea     rcx, [rbp+38h]
0x1400322eb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400322f0  nop
0x1400322f1  jmp     short $+2
0x1400322f3  mov     rax, 0
0x1400322fd  add     rsp, 20h
0x140032301  pop     rdi
0x140032302  pop     rbp
0x140032303  pop     rbx
0x140032304  retn
```
