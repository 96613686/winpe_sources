# SocketTransport::SetCallbacks(TransportCallbacks *)

- ea: `0x140062300`
- end: `0x14006239c`
- name: `?SetCallbacks@SocketTransport@@UEAAXPEAVTransportCallbacks@@@Z`
- size: `156`
- prototype: `void(SocketTransport *__hidden this, struct TransportCallbacks *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400341ac`
- `0x140062300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140062362`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140062362`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14006231f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14006231f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140062325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140062325`

## string_xrefs

- `0x14006238a`: `onecore\vm\compute\common\transport\sockettransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SocketTransport::SetCallbacks(RTL_SRWLOCK *this, struct TransportCallbacks *a2)
{
  RTL_SRWLOCK *v4; // rdi
  int Ptr_high; // ecx
  int v6; // eax
  unsigned int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = this + 25;
  AcquireSRWLockExclusive(this + 25);
  LODWORD(v4[1].Ptr) = GetCurrentThreadId();
  Ptr_high = HIDWORD(this[28].Ptr);
  if ( Ptr_high )
  {
    if ( Ptr_high != 1 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        (const char *)0x139F,
        v7);
    LOBYTE(this[29].Ptr) = 1;
    v6 = 3;
  }
  else
  {
    v6 = 2;
  }
  HIDWORD(this[28].Ptr) = v6;
  LODWORD(v4[1].Ptr) = 0;
  ReleaseSRWLockExclusive(v4);
  this[18].Ptr = a2;
}

```

## disassembly

```asm
0x140062300  mov     [rsp+arg_8], rbx
0x140062305  mov     [rsp+arg_10], rsi
0x14006230a  push    rdi; unsigned int
0x14006230b  sub     rsp, 20h
0x14006230f  mov     rsi, rdx
0x140062312  mov     rbx, rcx
0x140062315  lea     rdi, [rcx+0C8h]
0x14006231c  mov     rcx, rdi; SRWLock
0x14006231f  call    cs:__imp_AcquireSRWLockExclusive
0x140062325  call    cs:__imp_GetCurrentThreadId
0x14006232b  mov     [rdi+8], eax
0x14006232e  mov     [rsp+28h+arg_0], rdi
0x140062333  mov     ecx, [rbx+0E4h]
0x140062339  test    ecx, ecx
0x14006233b  jz      short loc_14006234D
0x14006233d  cmp     ecx, 1
0x140062340  jnz     short loc_14006237F
0x140062342  mov     [rbx+0E8h], cl
0x140062348  lea     eax, [rcx+2]
0x14006234b  jmp     short loc_140062352
0x14006234d  mov     eax, 2
0x140062352  mov     [rbx+0E4h], eax
0x140062358  mov     dword ptr [rdi+8], 0
0x14006235f  mov     rcx, rdi; SRWLock
0x140062362  call    cs:__imp_ReleaseSRWLockExclusive
0x140062368  mov     [rbx+90h], rsi
0x14006236f  mov     rbx, [rsp+28h+arg_8]
0x140062374  mov     rsi, [rsp+28h+arg_10]
0x140062379  add     rsp, 20h
0x14006237d  pop     rdi
0x14006237e  retn
0x14006237f  mov     rcx, [rsp+28h]; this
0x140062384  mov     r9d, 139Fh; char *
0x14006238a  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140062391  mov     edx, 162h; void *
0x140062396  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
