# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000d818`
- end: `0x18000d885`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d6dc`

## callees

- `0x1800033b4`
- `0x180006b2c`
- `0x180009348`
- `0x18000d818`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d86a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d86a`

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
0x18000d818  push    rbx
0x18000d81a  sub     rsp, 0C0h
0x18000d821  cmp     dword ptr [rcx+18h], 0
0x18000d825  mov     rbx, rcx
0x18000d828  jz      short loc_18000D847
0x18000d82a  xor     edx, edx; Val
0x18000d82c  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000d831  mov     r8d, 98h; Size
0x18000d837  call    memset_0
0x18000d83c  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000d841  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d847  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d84f  jz      short loc_18000D875
0x18000d851  mov     dl, 1
0x18000d853  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000d858  mov     [rbx], rax
0x18000d85b  test    rax, rax
0x18000d85e  jz      short loc_18000D87C
0x18000d860  mov     rcx, [rax]
0x18000d863  mov     [rbx+10h], rcx
0x18000d867  mov     [rax], rbx
0x18000d86a  call    cs:__imp_GetCurrentThreadId
0x18000d870  mov     [rbx+18h], eax
0x18000d873  jmp     short loc_18000D87C
0x18000d875  mov     qword ptr [rcx], 0
0x18000d87c  add     rsp, 0C0h
0x18000d883  pop     rbx
0x18000d884  retn
```
