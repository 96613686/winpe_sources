# RegisterLockStore(ulong,IPubLockStoreInitializer *,IPubLockStore * *)

- ea: `0x1800019f0`
- end: `0x180001a84`
- name: `?RegisterLockStore@@YAJKPEAVIPubLockStoreInitializer@@PEAPEAVIPubLockStore@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(int, struct IPubLockStoreInitializer *, struct IPubLockStore **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001008`
- `0x1800019f0`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180001a30`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001a30`

## pseudocode

```c
__int64 __fastcall RegisterLockStore(int a1, struct IPubLockStoreInitializer *a2, struct IPubLockStore **a3)
{
  char *v5; // rbx

  *a3 = 0;
  if ( a1 != 1 )
    return 2147500033LL;
  v5 = (char *)operator new(0x70u);
  if ( v5 )
  {
    *(_QWORD *)v5 = &MEM_STORE::`vftable';
    STRU::STRU((STRU *)(v5 + 16));
    *((_DWORD *)v5 + 22) = 0;
    *((_QWORD *)v5 + 10) = v5 + 72;
    *((_QWORD *)v5 + 9) = v5 + 72;
    *((_DWORD *)v5 + 23) = 0;
    *((_QWORD *)v5 + 1) = 0;
    *((_DWORD *)v5 + 24) = 1;
    *(_QWORD *)(v5 + 100) = 1000;
  }
  else
  {
    v5 = 0;
  }
  *a3 = (struct IPubLockStore *)v5;
  return v5 == 0 ? 0x80070008 : 0;
}

```

## disassembly

```asm
0x1800019f0  mov     [rsp+arg_0], rbx
0x1800019f5  push    rdi
0x1800019f6  sub     rsp, 20h
0x1800019fa  mov     qword ptr [r8], 0
0x180001a01  mov     rdi, r8
0x180001a04  cmp     ecx, 1
0x180001a07  jz      short loc_180001A10
0x180001a09  mov     eax, 80004001h
0x180001a0e  jmp     short loc_180001A79
0x180001a10  mov     ecx, 70h ; 'p'; Size
0x180001a15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001a1a  mov     rbx, rax
0x180001a1d  test    rax, rax
0x180001a20  jz      short loc_180001A68
0x180001a22  lea     rax, ??_7MEM_STORE@@6B@; const MEM_STORE::`vftable'
0x180001a29  lea     rcx, [rbx+10h]
0x180001a2d  mov     [rbx], rax
0x180001a30  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001a36  lea     rax, [rbx+48h]
0x180001a3a  mov     dword ptr [rbx+58h], 0
0x180001a41  mov     [rax+8], rax
0x180001a45  mov     [rax], rax
0x180001a48  mov     dword ptr [rbx+5Ch], 0
0x180001a4f  mov     qword ptr [rbx+8], 0
0x180001a57  mov     dword ptr [rbx+60h], 1
0x180001a5e  mov     qword ptr [rbx+64h], 3E8h
0x180001a66  jmp     short loc_180001A6A
0x180001a68  xor     ebx, ebx
0x180001a6a  mov     [rdi], rbx
0x180001a6d  neg     rbx
0x180001a70  sbb     eax, eax
0x180001a72  not     eax
0x180001a74  and     eax, 80070008h
0x180001a79  mov     rbx, [rsp+28h+arg_0]
0x180001a7e  add     rsp, 20h
0x180001a82  pop     rdi
0x180001a83  retn
```
