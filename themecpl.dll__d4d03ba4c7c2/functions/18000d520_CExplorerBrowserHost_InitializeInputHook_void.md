# CExplorerBrowserHost::_InitializeInputHook(void)

- ea: `0x18000d520`
- end: `0x18000d5d5`
- name: `?_InitializeInputHook@CExplorerBrowserHost@@AEAAXXZ`
- size: `181`
- prototype: `void __fastcall(CExplorerBrowserHost *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bae0`

## callees

- `0x18000d520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d551`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d551`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d567`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d59d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d567`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d59d`
- `USER32!SetWindowsHookExW` at `0x18000d584`
- `USER32!SetWindowsHookExW` at `0x18000d5ba`
- `USER32!SetWindowsHookExW` at `0x18000d584`
- `USER32!SetWindowsHookExW` at `0x18000d5ba`

## pseudocode

```c
void __fastcall CExplorerBrowserHost::_InitializeInputHook(CExplorerBrowserHost *this)
{
  HHOOK *v1; // rbx
  DWORD CurrentThreadId; // eax
  DWORD v4; // eax

  v1 = (HHOOK *)((char *)this + 336);
  if ( !*((_QWORD *)this + 41) || !*v1 )
  {
    TlsSetValue(g_tlsCurrentExplorerBrowserHost, this);
    if ( !*((_QWORD *)this + 41) )
    {
      CurrentThreadId = GetCurrentThreadId();
      *((_QWORD *)this + 41) = SetWindowsHookExW(3, CExplorerBrowserHost::s_MessageHookProc, 0, CurrentThreadId);
    }
    if ( !*v1 )
    {
      v4 = GetCurrentThreadId();
      *v1 = SetWindowsHookExW(4, CExplorerBrowserHost::s_FocusHookProc, 0, v4);
    }
  }
}

```

## disassembly

```asm
0x18000d520  mov     [rsp+arg_0], rbx
0x18000d525  push    rdi
0x18000d526  sub     rsp, 20h
0x18000d52a  cmp     qword ptr [rcx+148h], 0
0x18000d532  lea     rbx, [rcx+150h]
0x18000d539  mov     rdi, rcx
0x18000d53c  jz      short loc_18000D548
0x18000d53e  cmp     qword ptr [rbx], 0
0x18000d542  jnz     loc_18000D5C9
0x18000d548  mov     ecx, cs:?g_tlsCurrentExplorerBrowserHost@@3KA; dwTlsIndex
0x18000d54e  mov     rdx, rdi; lpTlsValue
0x18000d551  call    cs:__imp_TlsSetValue
0x18000d558  nop     dword ptr [rax+rax+00h]
0x18000d55d  cmp     qword ptr [rdi+148h], 0
0x18000d565  jnz     short loc_18000D597
0x18000d567  call    cs:__imp_GetCurrentThreadId
0x18000d56e  nop     dword ptr [rax+rax+00h]
0x18000d573  xor     r8d, r8d; hmod
0x18000d576  lea     rdx, ?s_MessageHookProc@CExplorerBrowserHost@@CA_JH_K_J@Z; lpfn
0x18000d57d  mov     r9d, eax; dwThreadId
0x18000d580  lea     ecx, [r8+3]; idHook
0x18000d584  call    cs:__imp_SetWindowsHookExW
0x18000d58b  nop     dword ptr [rax+rax+00h]
0x18000d590  mov     [rdi+148h], rax
0x18000d597  cmp     qword ptr [rbx], 0
0x18000d59b  jnz     short loc_18000D5C9
0x18000d59d  call    cs:__imp_GetCurrentThreadId
0x18000d5a4  nop     dword ptr [rax+rax+00h]
0x18000d5a9  xor     r8d, r8d; hmod
0x18000d5ac  lea     rdx, ?s_FocusHookProc@CExplorerBrowserHost@@CA_JH_K_J@Z; lpfn
0x18000d5b3  mov     r9d, eax; dwThreadId
0x18000d5b6  lea     ecx, [r8+4]; idHook
0x18000d5ba  call    cs:__imp_SetWindowsHookExW
0x18000d5c1  nop     dword ptr [rax+rax+00h]
0x18000d5c6  mov     [rbx], rax
0x18000d5c9  mov     rbx, [rsp+28h+arg_0]
0x18000d5ce  add     rsp, 20h
0x18000d5d2  pop     rdi
0x18000d5d3  retn
```
