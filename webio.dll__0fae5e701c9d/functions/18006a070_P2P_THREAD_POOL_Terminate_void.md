# P2P_THREAD_POOL::Terminate(void)

- ea: `0x18006a070`
- end: `0x18006a0ea`
- name: `?Terminate@P2P_THREAD_POOL@@QEAAXXZ`
- size: `122`
- prototype: `void __fastcall(P2P_THREAD_POOL *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800438c0`
- `0x18005bdd4`

## callees

- `0x18006a070`
- `0x18006a1ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18006a0c7`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18006a0c7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006a0dc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006a0dc`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18006a09a`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18006a09a`

## pseudocode

```c
void __fastcall P2P_THREAD_POOL::Terminate(P2P_THREAD_POOL *this)
{
  int v2; // edi

  if ( *((_QWORD *)this + 1) )
  {
    v2 = 1;
    do
    {
      if ( PostQueuedCompletionStatus(*(HANDLE *)this, 0, 0, (LPOVERLAPPED)((char *)this + 16)) )
      {
        --v2;
      }
      else if ( !SwitchToThread() )
      {
        Sleep(0x3E8u);
      }
    }
    while ( v2 );
  }
  P2P_THREAD_POOL::Dereference(this);
}

```

## disassembly

```asm
0x18006a070  mov     [rsp+arg_0], rbx
0x18006a075  mov     [rsp+arg_8], rsi
0x18006a07a  push    rdi
0x18006a07b  sub     rsp, 20h
0x18006a07f  cmp     qword ptr [rcx+8], 0
0x18006a084  mov     rbx, rcx
0x18006a087  jz      short loc_18006A0B0
0x18006a089  mov     edi, 1
0x18006a08e  mov     rcx, [rbx]; CompletionPort
0x18006a091  lea     r9, [rbx+10h]; lpOverlapped
0x18006a095  xor     r8d, r8d; dwCompletionKey
0x18006a098  xor     edx, edx; dwNumberOfBytesTransferred
0x18006a09a  call    cs:__imp_PostQueuedCompletionStatus
0x18006a0a1  nop     dword ptr [rax+rax+00h]
0x18006a0a6  test    eax, eax
0x18006a0a8  jz      short loc_18006A0C7
0x18006a0aa  dec     edi
0x18006a0ac  test    edi, edi
0x18006a0ae  jnz     short loc_18006A08E
0x18006a0b0  mov     rcx, rbx; this
0x18006a0b3  mov     rbx, [rsp+28h+arg_0]
0x18006a0b8  mov     rsi, [rsp+28h+arg_8]
0x18006a0bd  add     rsp, 20h
0x18006a0c1  pop     rdi
0x18006a0c2  jmp     ?Dereference@P2P_THREAD_POOL@@AEAAXXZ; P2P_THREAD_POOL::Dereference(void)
0x18006a0c7  call    cs:__imp_SwitchToThread
0x18006a0ce  nop     dword ptr [rax+rax+00h]
0x18006a0d3  test    eax, eax
0x18006a0d5  jnz     short loc_18006A0AC
0x18006a0d7  mov     ecx, 3E8h; dwMilliseconds
0x18006a0dc  call    cs:__imp_Sleep
0x18006a0e3  nop     dword ptr [rax+rax+00h]
0x18006a0e8  jmp     short loc_18006A0AC
```
