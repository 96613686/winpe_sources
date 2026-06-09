# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180005868`
- end: `0x1800058d5`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000246c`
- `0x18000429c`
- `0x180005d78`
- `0x180012b98`

## callees

- `0x180005868`
- `0x1800058dc`
- `0x18000e330`
- `0x180011750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000589d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000589d`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  _QWORD *Local; // rax
  const struct wil::FailureInfo *v3; // rdx
  _BYTE v4[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v4, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v4, v3);
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
0x180005868  push    rbx
0x18000586a  sub     rsp, 0C0h
0x180005871  cmp     dword ptr [rcx+18h], 0
0x180005875  mov     rbx, rcx
0x180005878  jnz     short loc_1800058B8
0x18000587a  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005882  jz      short loc_1800058AF
0x180005884  mov     dl, 1
0x180005886  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000588b  mov     [rbx], rax
0x18000588e  test    rax, rax
0x180005891  jz      short loc_1800058A6
0x180005893  mov     rcx, [rax]
0x180005896  mov     [rbx+10h], rcx
0x18000589a  mov     [rax], rbx
0x18000589d  call    cs:__imp_GetCurrentThreadId
0x1800058a3  mov     [rbx+18h], eax
0x1800058a6  add     rsp, 0C0h
0x1800058ad  pop     rbx
0x1800058ae  retn
0x1800058af  mov     qword ptr [rcx], 0
0x1800058b6  jmp     short loc_1800058A6
0x1800058b8  xor     edx, edx; Val
0x1800058ba  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800058bf  mov     r8d, 98h; Size
0x1800058c5  call    memset_0
0x1800058ca  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800058cf  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
