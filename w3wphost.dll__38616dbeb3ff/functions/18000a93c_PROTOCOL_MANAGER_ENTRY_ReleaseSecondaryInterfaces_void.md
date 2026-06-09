# PROTOCOL_MANAGER_ENTRY::ReleaseSecondaryInterfaces(void)

- ea: `0x18000a93c`
- end: `0x18000a9fb`
- name: `?ReleaseSecondaryInterfaces@PROTOCOL_MANAGER_ENTRY@@QEAAXXZ`
- size: `191`
- prototype: `void __fastcall(PROTOCOL_MANAGER_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007398`
- `0x180009f54`

## callees

- `0x18000a93c`
- `0x18000e010`

## pseudocode

```c
void __fastcall PROTOCOL_MANAGER_ENTRY::ReleaseSecondaryInterfaces(PROTOCOL_MANAGER_ENTRY *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *((_QWORD *)this + 33);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    *((_QWORD *)this + 33) = 0;
  }
  v3 = *((_QWORD *)this + 34);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
    *((_QWORD *)this + 34) = 0;
  }
  v4 = *((_QWORD *)this + 35);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    *((_QWORD *)this + 35) = 0;
  }
  v5 = *((_QWORD *)this + 36);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    *((_QWORD *)this + 36) = 0;
  }
  v6 = *((_QWORD *)this + 37);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    *((_QWORD *)this + 37) = 0;
  }
}

```

## disassembly

```asm
0x18000a93c  push    rbx
0x18000a93e  sub     rsp, 20h
0x18000a942  mov     rbx, rcx
0x18000a945  mov     rcx, [rcx+108h]
0x18000a94c  test    rcx, rcx
0x18000a94f  jz      short loc_18000A968
0x18000a951  mov     rax, [rcx]
0x18000a954  mov     rax, [rax+8]
0x18000a958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a95d  mov     qword ptr [rbx+108h], 0
0x18000a968  mov     rcx, [rbx+110h]
0x18000a96f  test    rcx, rcx
0x18000a972  jz      short loc_18000A98B
0x18000a974  mov     rax, [rcx]
0x18000a977  mov     rax, [rax+8]
0x18000a97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a980  mov     qword ptr [rbx+110h], 0
0x18000a98b  mov     rcx, [rbx+118h]
0x18000a992  test    rcx, rcx
0x18000a995  jz      short loc_18000A9AE
0x18000a997  mov     rax, [rcx]
0x18000a99a  mov     rax, [rax+8]
0x18000a99e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9a3  mov     qword ptr [rbx+118h], 0
0x18000a9ae  mov     rcx, [rbx+120h]
0x18000a9b5  test    rcx, rcx
0x18000a9b8  jz      short loc_18000A9D1
0x18000a9ba  mov     rax, [rcx]
0x18000a9bd  mov     rax, [rax+8]
0x18000a9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9c6  mov     qword ptr [rbx+120h], 0
0x18000a9d1  mov     rcx, [rbx+128h]
0x18000a9d8  test    rcx, rcx
0x18000a9db  jz      short loc_18000A9F4
0x18000a9dd  mov     rax, [rcx]
0x18000a9e0  mov     rax, [rax+8]
0x18000a9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9e9  mov     qword ptr [rbx+128h], 0
0x18000a9f4  add     rsp, 20h
0x18000a9f8  pop     rbx
0x18000a9f9  retn
```
