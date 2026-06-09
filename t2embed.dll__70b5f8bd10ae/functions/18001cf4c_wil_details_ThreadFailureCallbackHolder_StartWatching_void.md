# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18001cf4c`
- end: `0x18001cfb9`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001cf28`

## callees

- `0x18001bcdc`
- `0x18001cf4c`
- `0x180026e60`
- `0x18002a566`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001cf9e`
- `KERNEL32!GetCurrentThreadId` at `0x18001cf9e`

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
0x18001cf4c  push    rbx
0x18001cf4e  sub     rsp, 0C0h
0x18001cf55  cmp     dword ptr [rcx+18h], 0
0x18001cf59  mov     rbx, rcx
0x18001cf5c  jz      short loc_18001CF7B
0x18001cf5e  xor     edx, edx; Val
0x18001cf60  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18001cf65  mov     r8d, 98h; Size
0x18001cf6b  call    memset_0
0x18001cf70  lea     rcx, [rsp+0C8h+var_A8]; this
0x18001cf75  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001cf7b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001cf83  jz      short loc_18001CFA9
0x18001cf85  mov     dl, 1
0x18001cf87  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001cf8c  mov     [rbx], rax
0x18001cf8f  test    rax, rax
0x18001cf92  jz      short loc_18001CFB0
0x18001cf94  mov     rcx, [rax]
0x18001cf97  mov     [rbx+10h], rcx
0x18001cf9b  mov     [rax], rbx
0x18001cf9e  call    cs:__imp_GetCurrentThreadId
0x18001cfa4  mov     [rbx+18h], eax
0x18001cfa7  jmp     short loc_18001CFB0
0x18001cfa9  mov     qword ptr [rcx], 0
0x18001cfb0  add     rsp, 0C0h
0x18001cfb7  pop     rbx
0x18001cfb8  retn
```
