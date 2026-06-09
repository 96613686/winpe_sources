# CSvcQueryProxy::FreeCursorAsync(ulong)

- ea: `0x1800fd7b8`
- end: `0x1800fd892`
- name: `?FreeCursorAsync@CSvcQueryProxy@@AEAAXK@Z`
- size: `218`
- prototype: `void __fastcall(CSvcQueryProxy *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800fd7a0`
- `0x180107244`
- `0x1801c2e58`

## callees

- `0x1800fd7b8`
- `0x18017791c`
- `0x180188dc0`
- `0x180189280`
- `0x1801b5f70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800fd827`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800fd827`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800fd83a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800fd83a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fd809`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fd809`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fd843`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fd843`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
void __fastcall CSvcQueryProxy::FreeCursorAsync(CSvcQueryProxy *this, int a2)
{
  HMODULE *v4; // rbx
  struct _TP_WORK *ThreadpoolWork; // r14
  int LastScode; // esi

  v4 = (HMODULE *)operator new(0x18u);
  *(_OWORD *)v4 = 0;
  v4[2] = 0;
  *v4 = (HMODULE)this;
  *((_DWORD *)v4 + 2) = a2;
  ThreadpoolWork = CreateThreadpoolWork(CSvcQueryProxy::FreeCursorAsyncCallback, v4, 0);
  if ( ThreadpoolWork )
  {
    if ( GetModuleHandleExW(4u, (LPCWSTR)CSvcQueryProxy::FreeCursorAsyncCallback, v4 + 2) )
    {
      LastScode = 0;
      _InterlockedIncrement((volatile signed __int32 *)this + 4);
      SubmitThreadpoolWork(ThreadpoolWork);
    }
    else
    {
      LastScode = GetLastScode();
    }
    CloseThreadpoolWork(ThreadpoolWork);
  }
  else
  {
    LastScode = GetLastScode();
  }
  if ( LastScode < 0 )
  {
    operator delete(v4);
    CRequestClient::TerminateRudelyNoThrow(**((CRequestClient ***)this + 1));
  }
}

```

## disassembly

```asm
0x1800fd7b8  mov     [rsp+arg_8], rbx
0x1800fd7bd  mov     [rsp+arg_0], rcx
0x1800fd7c2  push    rsi
0x1800fd7c3  push    rdi
0x1800fd7c4  push    r14
0x1800fd7c6  sub     rsp, 20h
0x1800fd7ca  mov     esi, edx
0x1800fd7cc  mov     rdi, rcx
0x1800fd7cf  mov     [rsp+38h+arg_10], 0
0x1800fd7d8  mov     ecx, 18h; Size
0x1800fd7dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fd7e2  mov     rbx, rax
0x1800fd7e5  xorps   xmm0, xmm0
0x1800fd7e8  xor     eax, eax
0x1800fd7ea  movups  xmmword ptr [rbx], xmm0
0x1800fd7ed  mov     [rbx+10h], rax
0x1800fd7f1  mov     [rsp+38h+arg_10], rbx
0x1800fd7f6  mov     [rbx], rdi
0x1800fd7f9  mov     [rbx+8], esi
0x1800fd7fc  xor     r8d, r8d; pcbe
0x1800fd7ff  mov     rdx, rbx; pv
0x1800fd802  lea     rcx, ?FreeCursorAsyncCallback@CSvcQueryProxy@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800fd809  call    cs:__imp_CreateThreadpoolWork
0x1800fd80f  mov     r14, rax
0x1800fd812  test    rax, rax
0x1800fd815  jz      short loc_1800FD85B
0x1800fd817  lea     r8, [rbx+10h]; phModule
0x1800fd81b  lea     rdx, ?FreeCursorAsyncCallback@CSvcQueryProxy@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; lpModuleName
0x1800fd822  mov     ecx, 4; dwFlags
0x1800fd827  call    cs:__imp_GetModuleHandleExW
0x1800fd82d  test    eax, eax
0x1800fd82f  jz      short loc_1800FD864
0x1800fd831  xor     esi, esi
0x1800fd833  lock inc dword ptr [rdi+10h]
0x1800fd837  mov     rcx, r14; pwk
0x1800fd83a  call    cs:__imp_SubmitThreadpoolWork
0x1800fd840  mov     rcx, r14; pwk
0x1800fd843  call    cs:__imp_CloseThreadpoolWork
0x1800fd849  test    esi, esi
0x1800fd84b  js      short loc_1800FD877
0x1800fd84d  mov     rbx, [rsp+38h+arg_8]
0x1800fd852  add     rsp, 20h
0x1800fd856  pop     r14
0x1800fd858  pop     rdi
0x1800fd859  pop     rsi
0x1800fd85a  retn
0x1800fd85b  call    ?GetLastScode@@YAJXZ; GetLastScode(void)
0x1800fd860  mov     esi, eax
0x1800fd862  jmp     short loc_1800FD849
0x1800fd864  call    ?GetLastScode@@YAJXZ; GetLastScode(void)
0x1800fd869  mov     esi, eax
0x1800fd86b  jmp     short loc_1800FD840
0x1800fd86d  mov     rdi, [rsp+38h+arg_0]
0x1800fd872  mov     rbx, [rsp+38h+arg_10]
0x1800fd877  mov     edx, 18h
0x1800fd87c  mov     rcx, rbx; Block
0x1800fd87f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fd884  mov     rcx, [rdi+8]
0x1800fd888  mov     rcx, [rcx]; this
0x1800fd88b  call    ?TerminateRudelyNoThrow@CRequestClient@@QEAAXXZ; CRequestClient::TerminateRudelyNoThrow(void)
0x1800fd890  jmp     short loc_1800FD84D
```
