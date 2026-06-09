# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180029a38`
- end: `0x180029aa5`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180029958`

## callees

- `0x180005c94`
- `0x180011fc0`
- `0x1800161d8`
- `0x180029a38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029a8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029a8a`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  const struct wil::FailureInfo *v2; // rdx
  _QWORD *Local; // rax
  _BYTE v4[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v4, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v4, v2);
  }
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        (__int64)this,
                        1);
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
0x180029a38  push    rbx
0x180029a3a  sub     rsp, 0C0h
0x180029a41  cmp     dword ptr [rcx+18h], 0
0x180029a45  mov     rbx, rcx
0x180029a48  jz      short loc_180029A67
0x180029a4a  xor     edx, edx; Val
0x180029a4c  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180029a51  mov     r8d, 98h; Size
0x180029a57  call    memset_0
0x180029a5c  lea     rcx, [rsp+0C8h+var_A8]; this
0x180029a61  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180029a67  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180029a6f  jz      short loc_180029A95
0x180029a71  mov     dl, 1
0x180029a73  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180029a78  mov     [rbx], rax
0x180029a7b  test    rax, rax
0x180029a7e  jz      short loc_180029A9C
0x180029a80  mov     rcx, [rax]
0x180029a83  mov     [rbx+10h], rcx
0x180029a87  mov     [rax], rbx
0x180029a8a  call    cs:__imp_GetCurrentThreadId
0x180029a90  mov     [rbx+18h], eax
0x180029a93  jmp     short loc_180029A9C
0x180029a95  mov     qword ptr [rcx], 0
0x180029a9c  add     rsp, 0C0h
0x180029aa3  pop     rbx
0x180029aa4  retn
```
