# SocketTransport::ConnectedPeer(void)

- ea: `0x1400601b0`
- end: `0x140060241`
- name: `?ConnectedPeer@SocketTransport@@UEAAAEBVTransportConnectedPeer@@XZ`
- size: `145`
- prototype: `const struct TransportConnectedPeer *(SocketTransport *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400341ac`
- `0x1400601b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400601ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400601ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400601c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400601c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400601cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400601cd`

## string_xrefs

- `0x14006022f`: `onecore\vm\compute\common\transport\sockettransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
RTL_SRWLOCK *__fastcall SocketTransport::ConnectedPeer(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rdi
  RTL_SRWLOCK *result; // rax
  unsigned int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = this + 25;
  AcquireSRWLockExclusive(this + 25);
  LODWORD(v2[1].Ptr) = GetCurrentThreadId();
  if ( HIDWORD(this[28].Ptr) != 6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x4FB,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)0x139F,
      v4);
  LODWORD(v2[1].Ptr) = 0;
  ReleaseSRWLockExclusive(v2);
  if ( LODWORD(this[12].Ptr) == 2 )
    return this + 32;
  result = this + 41;
  if ( LODWORD(this[12].Ptr) == 3 )
    return this + 38;
  return result;
}

```

## disassembly

```asm
0x1400601b0  mov     [rsp+arg_8], rbx
0x1400601b5  push    rdi; unsigned int
0x1400601b6  sub     rsp, 20h
0x1400601ba  mov     rbx, rcx
0x1400601bd  lea     rdi, [rcx+0C8h]
0x1400601c4  mov     rcx, rdi; SRWLock
0x1400601c7  call    cs:__imp_AcquireSRWLockExclusive
0x1400601cd  call    cs:__imp_GetCurrentThreadId
0x1400601d3  mov     [rdi+8], eax
0x1400601d6  mov     [rsp+28h+arg_0], rdi
0x1400601db  cmp     dword ptr [rbx+0E4h], 6
0x1400601e2  jnz     short loc_140060224
0x1400601e4  mov     dword ptr [rdi+8], 0
0x1400601eb  mov     rcx, rdi; SRWLock
0x1400601ee  call    cs:__imp_ReleaseSRWLockExclusive
0x1400601f4  cmp     dword ptr [rbx+60h], 2
0x1400601f8  jnz     short loc_140060203
0x1400601fa  lea     rax, [rbx+100h]
0x140060201  jmp     short loc_140060219
0x140060203  lea     rcx, [rbx+130h]
0x14006020a  lea     rax, [rbx+148h]
0x140060211  cmp     dword ptr [rbx+60h], 3
0x140060215  cmovz   rax, rcx
0x140060219  mov     rbx, [rsp+28h+arg_8]
0x14006021e  add     rsp, 20h
0x140060222  pop     rdi
0x140060223  retn
0x140060224  mov     rcx, [rsp+28h]; this
0x140060229  mov     r9d, 139Fh; char *
0x14006022f  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140060236  mov     edx, 4FBh; void *
0x14006023b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
