# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x14000f650`
- end: `0x14000f6c4`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000c354`

## callees

- `0x140002fa0`
- `0x140005cd4`
- `0x1400093f0`
- `0x14000f650`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000f6a2`
- `KERNEL32!GetCurrentThreadId` at `0x14000f6a2`

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
0x14000f650  push    rbx
0x14000f652  sub     rsp, 0C0h
0x14000f659  cmp     dword ptr [rcx+18h], 0
0x14000f65d  mov     rbx, rcx
0x14000f660  jz      short loc_14000F67F
0x14000f662  xor     edx, edx; Val
0x14000f664  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000f669  mov     r8d, 98h; Size
0x14000f66f  call    memset_0
0x14000f674  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000f679  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000f67f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000f687  jz      short loc_14000F6B3
0x14000f689  mov     dl, 1
0x14000f68b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14000f690  mov     [rbx], rax
0x14000f693  test    rax, rax
0x14000f696  jz      short loc_14000F6BA
0x14000f698  mov     rcx, [rax]
0x14000f69b  mov     [rbx+10h], rcx
0x14000f69f  mov     [rax], rbx
0x14000f6a2  call    cs:__imp_GetCurrentThreadId
0x14000f6a9  nop     dword ptr [rax+rax+00h]
0x14000f6ae  mov     [rbx+18h], eax
0x14000f6b1  jmp     short loc_14000F6BA
0x14000f6b3  mov     qword ptr [rcx], 0
0x14000f6ba  add     rsp, 0C0h
0x14000f6c1  pop     rbx
0x14000f6c2  retn
```
