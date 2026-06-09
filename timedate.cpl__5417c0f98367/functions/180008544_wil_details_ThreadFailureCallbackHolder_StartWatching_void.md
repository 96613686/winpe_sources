# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180008544`
- end: `0x1800085b1`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005b94`

## callees

- `0x18000616c`
- `0x180008544`
- `0x180008ff8`
- `0x180028f2e`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008596`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008596`

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
0x180008544  push    rbx
0x180008546  sub     rsp, 0C0h
0x18000854d  cmp     dword ptr [rcx+18h], 0
0x180008551  mov     rbx, rcx
0x180008554  jz      short loc_180008573
0x180008556  xor     edx, edx; Val
0x180008558  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000855d  mov     r8d, 98h; Size
0x180008563  call    memset_0
0x180008568  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000856d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008573  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000857b  jz      short loc_1800085A1
0x18000857d  mov     dl, 1
0x18000857f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180008584  mov     [rbx], rax
0x180008587  test    rax, rax
0x18000858a  jz      short loc_1800085A8
0x18000858c  mov     rcx, [rax]
0x18000858f  mov     [rbx+10h], rcx
0x180008593  mov     [rax], rbx
0x180008596  call    cs:__imp_GetCurrentThreadId
0x18000859c  mov     [rbx+18h], eax
0x18000859f  jmp     short loc_1800085A8
0x1800085a1  mov     qword ptr [rcx], 0
0x1800085a8  add     rsp, 0C0h
0x1800085af  pop     rbx
0x1800085b0  retn
```
