# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180006010`
- end: `0x180006084`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800046ac`
- `0x180004968`
- `0x18000656c`
- `0x180013c58`

## callees

- `0x180006010`
- `0x18000608c`
- `0x18000efe0`
- `0x1800126a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006045`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006045`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this,
        __int64 a2)
{
  _QWORD *Local; // rax
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v5, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v5, v4);
  }
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(a2) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        this,
                        a2);
    *(_QWORD *)this = Local;
    if ( Local )
    {
      *((_QWORD *)this + 2) = *Local;
      *Local = this;
      *((_DWORD *)this + 6) = GetCurrentThreadId();
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180006010  push    rbx
0x180006012  sub     rsp, 0C0h
0x180006019  cmp     dword ptr [rcx+18h], 0
0x18000601d  mov     rbx, rcx
0x180006020  jnz     short loc_180006067
0x180006022  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000602a  jz      short loc_18000605E
0x18000602c  mov     dl, 1
0x18000602e  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180006033  mov     [rbx], rax
0x180006036  test    rax, rax
0x180006039  jz      short loc_180006054
0x18000603b  mov     rcx, [rax]
0x18000603e  mov     [rbx+10h], rcx
0x180006042  mov     [rax], rbx
0x180006045  call    cs:__imp_GetCurrentThreadId
0x18000604c  nop     dword ptr [rax+rax+00h]
0x180006051  mov     [rbx+18h], eax
0x180006054  add     rsp, 0C0h
0x18000605b  pop     rbx
0x18000605c  retn
0x18000605e  mov     qword ptr [rcx], 0
0x180006065  jmp     short loc_180006054
0x180006067  xor     edx, edx; Val
0x180006069  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000606e  mov     r8d, 98h; Size
0x180006074  call    memset_0
0x180006079  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000607e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
