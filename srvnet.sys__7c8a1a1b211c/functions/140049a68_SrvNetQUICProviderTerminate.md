# SrvNetQUICProviderTerminate

- ea: `0x140049a68`
- end: `0x140049b83`
- name: `SrvNetQUICProviderTerminate`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140056be0`

## callees

- `0x14002a4c0`
- `0x140049a68`

## import_xrefs

- `ntoskrnl!RtlRunOnceBeginInitialize` at `0x140049a80`
- `ntoskrnl!RtlRunOnceBeginInitialize` at `0x140049a80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049b60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049b60`
- `NETIO!NmrDeregisterClient` at `0x140049b2f`
- `NETIO!NmrDeregisterClient` at `0x140049b2f`
- `NETIO!NmrClientDetachProviderComplete` at `0x140049b1b`
- `NETIO!NmrClientDetachProviderComplete` at `0x140049b1b`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140049b45`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140049b45`

## pseudocode

```c
void SrvNetQUICProviderTerminate()
{
  PVOID v0; // rdi
  HANDLE *v1; // rbx

  if ( !RtlRunOnceBeginInitialize(&SrvNetQUICInitOnce, 1u, 0) )
  {
    if ( SMBQuicRegistration )
    {
      (*(void (**)(void))(MsQuic + 48))();
      SMBQuicRegistration = 0;
    }
    if ( MsQuic )
    {
      (*(void (**)(void))(*((_QWORD *)QuicNmrHandle + 17) + 16LL))();
      v0 = QuicNmrHandle;
      MsQuic = 0;
      v1 = (HANDLE *)((char *)QuicNmrHandle + 80);
      _m_prefetchw((char *)QuicNmrHandle + 144);
      if ( _InterlockedOr8((volatile signed __int8 *)QuicNmrHandle + 144, 1u) )
        NmrClientDetachProviderComplete(*v1);
      if ( *v1 )
      {
        if ( NmrDeregisterClient(*v1) == 259 )
          NmrWaitForClientDeregisterComplete(*v1);
        *v1 = 0;
      }
      ExFreePoolWithTag(v0, 0x634E514Du);
      QuicNmrHandle = 0;
    }
  }
}

```

## disassembly

```asm
0x140049a68  mov     [rsp+arg_0], rbx
0x140049a6d  push    rdi
0x140049a6e  sub     rsp, 20h
0x140049a72  xor     r8d, r8d; Context
0x140049a75  lea     rcx, SrvNetQUICInitOnce; RunOnce
0x140049a7c  lea     edx, [r8+1]; Flags
0x140049a80  call    cs:__imp_RtlRunOnceBeginInitialize
0x140049a87  nop     dword ptr [rax+rax+00h]
0x140049a8c  test    eax, eax
0x140049a8e  jnz     loc_140049B77
0x140049a94  mov     rcx, cs:SMBQuicRegistration
0x140049a9b  test    rcx, rcx
0x140049a9e  jz      short loc_140049ABB
0x140049aa0  mov     rax, cs:MsQuic
0x140049aa7  mov     rax, [rax+30h]
0x140049aab  call    _guard_dispatch_icall
0x140049ab0  mov     cs:SMBQuicRegistration, 0
0x140049abb  mov     rcx, cs:MsQuic
0x140049ac2  test    rcx, rcx
0x140049ac5  jz      loc_140049B77
0x140049acb  mov     rax, cs:QuicNmrHandle
0x140049ad2  mov     rdx, [rax+88h]
0x140049ad9  mov     rax, [rdx+10h]
0x140049add  call    _guard_dispatch_icall
0x140049ae2  mov     rdi, cs:QuicNmrHandle
0x140049ae9  mov     cs:MsQuic, 0
0x140049af4  lea     rbx, [rdi+50h]
0x140049af8  prefetchw byte ptr [rdi+90h]
0x140049aff  mov     al, [rdi+90h]
0x140049b05  mov     cl, al
0x140049b07  or      cl, 1
0x140049b0a  lock cmpxchg [rdi+90h], cl
0x140049b12  jnz     short loc_140049B05
0x140049b14  test    al, al
0x140049b16  jz      short loc_140049B27
0x140049b18  mov     rcx, [rbx]; NmrBindingHandle
0x140049b1b  call    cs:__imp_NmrClientDetachProviderComplete
0x140049b22  nop     dword ptr [rax+rax+00h]
0x140049b27  mov     rcx, [rbx]; NmrClientHandle
0x140049b2a  test    rcx, rcx
0x140049b2d  jz      short loc_140049B58
0x140049b2f  call    cs:__imp_NmrDeregisterClient
0x140049b36  nop     dword ptr [rax+rax+00h]
0x140049b3b  cmp     eax, 103h
0x140049b40  jnz     short loc_140049B51
0x140049b42  mov     rcx, [rbx]; NmrClientHandle
0x140049b45  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x140049b4c  nop     dword ptr [rax+rax+00h]
0x140049b51  mov     qword ptr [rbx], 0
0x140049b58  mov     edx, 634E514Dh; Tag
0x140049b5d  mov     rcx, rdi; P
0x140049b60  call    cs:__imp_ExFreePoolWithTag
0x140049b67  nop     dword ptr [rax+rax+00h]
0x140049b6c  mov     cs:QuicNmrHandle, 0
0x140049b77  mov     rbx, [rsp+28h+arg_0]
0x140049b7c  add     rsp, 20h
0x140049b80  pop     rdi
0x140049b81  retn
```
