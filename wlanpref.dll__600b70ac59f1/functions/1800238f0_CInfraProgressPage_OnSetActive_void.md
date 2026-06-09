# CInfraProgressPage::OnSetActive(void)

- ea: `0x1800238f0`
- end: `0x1800239c1`
- name: `?OnSetActive@CInfraProgressPage@@QEAA_JXZ`
- size: `209`
- prototype: `__int64 __fastcall(CInfraProgressPage *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008b8c`

## callees

- `0x180023308`
- `0x1800238f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002398c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002398c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002397a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002397a`
- `USER32!PostMessageW` at `0x180023923`
- `USER32!PostMessageW` at `0x18002393b`
- `USER32!PostMessageW` at `0x180023923`
- `USER32!PostMessageW` at `0x18002393b`
- `USER32!GetParent` at `0x180023909`
- `USER32!GetParent` at `0x180023909`

## pseudocode

```c
GUID *__fastcall CInfraProgressPage::OnSetActive(HWND *this)
{
  HWND Parent; // rbx
  HWND v3; // rax
  signed int LastError; // eax
  unsigned int v5; // ecx
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  ThreadId = 0;
  Parent = GetParent(this[13]);
  PostMessageW(Parent, 0x470u, 0, 16);
  PostMessageW(Parent, 0x48Au, 0x11u, 22);
  SetFormattedText((WPARAM)this[13]);
  v3 = (HWND)CreateThread(0, 0, CInfraProgressPage::CreateProfileProc, this, 0, &ThreadId);
  this[34] = v3;
  if ( v3 )
    return 0;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  *((_DWORD *)this[35] + 15) = v5;
  return &CLSID_InfraErrorPage;
}

```

## disassembly

```asm
0x1800238f0  mov     [rsp+arg_8], rbx
0x1800238f5  push    rdi
0x1800238f6  sub     rsp, 30h
0x1800238fa  mov     rdi, rcx
0x1800238fd  mov     [rsp+38h+ThreadId], 0
0x180023905  mov     rcx, [rcx+68h]; hWnd
0x180023909  call    cs:__imp_GetParent
0x18002390f  mov     r9d, 10h; lParam
0x180023915  xor     r8d, r8d; wParam
0x180023918  mov     rcx, rax; hWnd
0x18002391b  mov     edx, 470h; Msg
0x180023920  mov     rbx, rax
0x180023923  call    cs:__imp_PostMessageW
0x180023929  mov     r9d, 16h; lParam
0x18002392f  mov     edx, 48Ah; Msg
0x180023934  mov     rcx, rbx; hWnd
0x180023937  lea     r8d, [r9-5]; wParam
0x18002393b  call    cs:__imp_PostMessageW
0x180023941  mov     r8, [rdi+118h]
0x180023948  mov     edx, 2AB7h
0x18002394d  mov     rcx, [rdi+68h]; wParam
0x180023951  mov     r8, [r8+10h]
0x180023955  call    SetFormattedText
0x18002395a  lea     rax, [rsp+38h+ThreadId]
0x18002395f  mov     r9, rdi; lpParameter
0x180023962  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180023967  lea     r8, ?CreateProfileProc@CInfraProgressPage@@SAKPEAX@Z; lpStartAddress
0x18002396e  xor     edx, edx; dwStackSize
0x180023970  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180023978  xor     ecx, ecx; lpThreadAttributes
0x18002397a  call    cs:__imp_CreateThread
0x180023980  mov     [rdi+110h], rax
0x180023987  test    rax, rax
0x18002398a  jnz     short loc_1800239B4
0x18002398c  call    cs:__imp_GetLastError
0x180023992  mov     ecx, eax
0x180023994  test    eax, eax
0x180023996  jle     short loc_1800239A1
0x180023998  movzx   ecx, ax
0x18002399b  or      ecx, 80070000h
0x1800239a1  mov     rax, [rdi+118h]
0x1800239a8  mov     [rax+3Ch], ecx
0x1800239ab  lea     rax, CLSID_InfraErrorPage
0x1800239b2  jmp     short loc_1800239B6
0x1800239b4  xor     eax, eax
0x1800239b6  mov     rbx, [rsp+38h+arg_8]
0x1800239bb  add     rsp, 30h
0x1800239bf  pop     rdi
0x1800239c0  retn
```
