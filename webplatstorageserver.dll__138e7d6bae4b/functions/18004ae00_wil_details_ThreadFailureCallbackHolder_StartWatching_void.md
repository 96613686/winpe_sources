# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18004ae00`
- end: `0x18004af22`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `290`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003867c`
- `0x18004addc`
- `0x18006f534`
- `0x18009e098`

## callees

- `0x18004ae00`
- `0x18004aff4`
- `0x180051c14`
- `0x180081b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ae34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ae99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ae34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ae99`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // rdi
  DWORD CurrentThreadId; // esi
  unsigned __int64 v4; // r8
  __int64 v5; // r14
  __int64 i; // rcx
  _QWORD *v7; // rcx
  char *v8; // rax
  signed __int64 v9; // r8
  signed __int64 v10; // rax
  const struct wil::FailureInfo *v11; // rdx
  _BYTE v12[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v12, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v12, v11);
  }
  v2 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
    v5 = 8 * v4;
    for ( i = *(_QWORD *)(8 * v4 + v2); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == CurrentThreadId )
      {
        v7 = (_QWORD *)(i + 16);
        goto LABEL_7;
      }
    }
    v8 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v4);
    v9 = (signed __int64)v8;
    if ( v8 )
    {
      *(_DWORD *)v8 = CurrentThreadId;
      v7 = v8 + 16;
      *((_DWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 2) = 0;
      do
      {
        v10 = *(_QWORD *)(v5 + v2);
        *(_QWORD *)(v9 + 8) = v10;
      }
      while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + v2), v9, v10) );
    }
    else
    {
      v7 = 0;
    }
LABEL_7:
    *(_QWORD *)this = v7;
    if ( v7 )
    {
      *((_QWORD *)this + 2) = *v7;
      *v7 = this;
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
0x18004ae00  mov     rax, rsp
0x18004ae03  push    rbx
0x18004ae04  sub     rsp, 0C0h
0x18004ae0b  cmp     dword ptr [rcx+18h], 0
0x18004ae0f  mov     rbx, rcx
0x18004ae12  jnz     loc_18004AF05
0x18004ae18  mov     [rax+10h], rdi
0x18004ae1c  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18004ae23  test    rdi, rdi
0x18004ae26  jz      loc_18004AEB9
0x18004ae2c  mov     [rax+8], rsi
0x18004ae30  mov     [rax+18h], r14
0x18004ae34  call    cs:__imp_GetCurrentThreadId
0x18004ae3a  mov     r8d, eax
0x18004ae3d  mov     esi, eax
0x18004ae3f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18004ae49  shr     r8, 2
0x18004ae4d  mul     r8
0x18004ae50  shr     rdx, 3
0x18004ae54  lea     rcx, [rdx+rdx*4]
0x18004ae58  add     rcx, rcx
0x18004ae5b  sub     r8, rcx; unsigned __int64
0x18004ae5e  lea     r14, ds:0[r8*8]
0x18004ae66  mov     rcx, [r14+rdi]
0x18004ae6a  test    rcx, rcx
0x18004ae6d  jz      short loc_18004AEC0
0x18004ae6f  cmp     [rcx], esi
0x18004ae71  jnz     short loc_18004AEB3
0x18004ae73  add     rcx, 10h
0x18004ae77  mov     r14, [rsp+0C8h+arg_10]
0x18004ae7f  mov     rsi, [rsp+0C8h+arg_0]
0x18004ae87  mov     [rbx], rcx
0x18004ae8a  test    rcx, rcx
0x18004ae8d  jz      short loc_18004AEA2
0x18004ae8f  mov     rax, [rcx]
0x18004ae92  mov     [rbx+10h], rax
0x18004ae96  mov     [rcx], rbx
0x18004ae99  call    cs:__imp_GetCurrentThreadId
0x18004ae9f  mov     [rbx+18h], eax
0x18004aea2  mov     rdi, [rsp+0C8h+arg_8]
0x18004aeaa  add     rsp, 0C0h
0x18004aeb1  pop     rbx
0x18004aeb2  retn
0x18004aeb3  mov     rcx, [rcx+8]
0x18004aeb7  jmp     short loc_18004AE6A
0x18004aeb9  xor     edx, edx
0x18004aebb  mov     [rcx], rdx
0x18004aebe  jmp     short loc_18004AEA2
0x18004aec0  mov     edx, 18h; dwBytes
0x18004aec5  xor     ecx, ecx; dwFlags
0x18004aec7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18004aecc  mov     r8, rax
0x18004aecf  test    rax, rax
0x18004aed2  jnz     short loc_18004AEDA
0x18004aed4  xor     edx, edx
0x18004aed6  mov     ecx, edx
0x18004aed8  jmp     short loc_18004AE77
0x18004aeda  mov     [rax], esi
0x18004aedc  lea     rcx, [r8+10h]
0x18004aee0  xor     eax, eax
0x18004aee2  xor     edx, edx
0x18004aee4  mov     [r8+4], eax
0x18004aee8  mov     [r8+8], rdx
0x18004aeec  mov     [rcx], rdx
0x18004aeef  nop
0x18004aef0  mov     rax, [r14+rdi]
0x18004aef4  mov     [r8+8], rax
0x18004aef8  lock cmpxchg [r14+rdi], r8
0x18004aefe  jnz     short loc_18004AEF0
0x18004af00  jmp     loc_18004AE77
0x18004af05  xor     edx, edx; Val
0x18004af07  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18004af0c  mov     r8d, 98h; Size
0x18004af12  call    memset_0
0x18004af17  lea     rcx, [rsp+0C8h+var_A8]; this
0x18004af1c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
