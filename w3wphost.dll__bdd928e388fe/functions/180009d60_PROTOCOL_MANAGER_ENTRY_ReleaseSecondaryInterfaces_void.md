# PROTOCOL_MANAGER_ENTRY::ReleaseSecondaryInterfaces(void)

- ea: `0x180009d60`
- end: `0x180009e1e`
- name: `?ReleaseSecondaryInterfaces@PROTOCOL_MANAGER_ENTRY@@QEAAXXZ`
- size: `190`
- prototype: `void __fastcall(PROTOCOL_MANAGER_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006cd8`
- `0x1800094bc`

## callees

- `0x180009d60`
- `0x18000d010`

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
0x180009d60  push    rbx
0x180009d62  sub     rsp, 20h
0x180009d66  mov     rbx, rcx
0x180009d69  mov     rcx, [rcx+108h]
0x180009d70  test    rcx, rcx
0x180009d73  jz      short loc_180009D8C
0x180009d75  mov     rax, [rcx]
0x180009d78  mov     rax, [rax+8]
0x180009d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d81  mov     qword ptr [rbx+108h], 0
0x180009d8c  mov     rcx, [rbx+110h]
0x180009d93  test    rcx, rcx
0x180009d96  jz      short loc_180009DAF
0x180009d98  mov     rax, [rcx]
0x180009d9b  mov     rax, [rax+8]
0x180009d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009da4  mov     qword ptr [rbx+110h], 0
0x180009daf  mov     rcx, [rbx+118h]
0x180009db6  test    rcx, rcx
0x180009db9  jz      short loc_180009DD2
0x180009dbb  mov     rax, [rcx]
0x180009dbe  mov     rax, [rax+8]
0x180009dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dc7  mov     qword ptr [rbx+118h], 0
0x180009dd2  mov     rcx, [rbx+120h]
0x180009dd9  test    rcx, rcx
0x180009ddc  jz      short loc_180009DF5
0x180009dde  mov     rax, [rcx]
0x180009de1  mov     rax, [rax+8]
0x180009de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dea  mov     qword ptr [rbx+120h], 0
0x180009df5  mov     rcx, [rbx+128h]
0x180009dfc  test    rcx, rcx
0x180009dff  jz      short loc_180009E18
0x180009e01  mov     rax, [rcx]
0x180009e04  mov     rax, [rax+8]
0x180009e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e0d  mov     qword ptr [rbx+128h], 0
0x180009e18  add     rsp, 20h
0x180009e1c  pop     rbx
0x180009e1d  retn
```
