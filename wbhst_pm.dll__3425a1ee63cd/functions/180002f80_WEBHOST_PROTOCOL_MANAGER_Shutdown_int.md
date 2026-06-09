# WEBHOST_PROTOCOL_MANAGER::Shutdown(int)

- ea: `0x180002f80`
- end: `0x180003016`
- name: `?Shutdown@WEBHOST_PROTOCOL_MANAGER@@UEAAJH@Z`
- size: `150`
- prototype: `__int64 __fastcall(WEBHOST_PROTOCOL_MANAGER *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002ec0`
- `0x180002f80`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002fd7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002fd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ffe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ffe`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::Shutdown(WEBHOST_PROTOCOL_MANAGER *this)
{
  unsigned int v2; // eax
  PMH_SUPPORT_FCNS *v3; // rcx
  unsigned int v4; // esi
  __int64 v5; // rbx
  __int64 v6; // rcx

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 40LL))(*((_QWORD *)this + 9));
  v3 = (PMH_SUPPORT_FCNS *)*((_QWORD *)this + 13);
  v4 = v2;
  if ( v3 )
  {
    PMH_SUPPORT_FCNS::Shutdown(v3);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 16LL))(*((_QWORD *)this + 13));
    *((_QWORD *)this + 13) = 0;
  }
  v5 = *((_QWORD *)this + 12);
  if ( v5 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 32));
    v6 = *(_QWORD *)(v5 + 16);
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
      *(_QWORD *)(v5 + 16) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 32));
  }
  return v4;
}

```

## disassembly

```asm
0x180002f80  mov     [rsp+arg_0], rbx
0x180002f85  mov     [rsp+arg_8], rsi
0x180002f8a  push    rdi
0x180002f8b  sub     rsp, 20h
0x180002f8f  mov     rbx, rcx
0x180002f92  mov     rcx, [rcx+48h]
0x180002f96  mov     rax, [rcx]
0x180002f99  mov     rax, [rax+28h]
0x180002f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa2  mov     rcx, [rbx+68h]; this
0x180002fa6  mov     esi, eax
0x180002fa8  test    rcx, rcx
0x180002fab  jz      short loc_180002FCA
0x180002fad  call    ?Shutdown@PMH_SUPPORT_FCNS@@QEAAXXZ; PMH_SUPPORT_FCNS::Shutdown(void)
0x180002fb2  mov     rcx, [rbx+68h]
0x180002fb6  mov     rdx, [rcx]
0x180002fb9  mov     rax, [rdx+10h]
0x180002fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fc2  mov     qword ptr [rbx+68h], 0
0x180002fca  mov     rbx, [rbx+60h]
0x180002fce  test    rbx, rbx
0x180002fd1  jz      short loc_180003004
0x180002fd3  lea     rcx, [rbx+20h]; lpCriticalSection
0x180002fd7  call    cs:__imp_EnterCriticalSection
0x180002fdd  mov     rcx, [rbx+10h]
0x180002fe1  test    rcx, rcx
0x180002fe4  jz      short loc_180002FFA
0x180002fe6  mov     rax, [rcx]
0x180002fe9  mov     rax, [rax+8]
0x180002fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ff2  mov     qword ptr [rbx+10h], 0
0x180002ffa  lea     rcx, [rbx+20h]; lpCriticalSection
0x180002ffe  call    cs:__imp_LeaveCriticalSection
0x180003004  mov     rbx, [rsp+28h+arg_0]
0x180003009  mov     eax, esi
0x18000300b  mov     rsi, [rsp+28h+arg_8]
0x180003010  add     rsp, 20h
0x180003014  pop     rdi
0x180003015  retn
```
