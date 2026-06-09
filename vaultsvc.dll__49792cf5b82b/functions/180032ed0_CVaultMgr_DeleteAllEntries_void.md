# CVaultMgr::DeleteAllEntries(void)

- ea: `0x180032ed0`
- end: `0x180032f45`
- name: `?DeleteAllEntries@CVaultMgr@@AEAAXXZ`
- size: `117`
- prototype: `void __fastcall(CVaultMgr *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800029e8`
- `0x18003895c`

## callees

- `0x180012210`
- `0x180032ed0`
- `0x18003af10`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180032f3e`
- `ntdll!RtlAcquireResourceExclusive` at `0x180032ee4`
- `ntdll!RtlAcquireResourceExclusive` at `0x180032ee4`

## pseudocode

```c
void __fastcall CVaultMgr::DeleteAllEntries(struct _RTL_RESOURCE *this)
{
  __int64 i; // rdi
  __int64 v3; // rbp
  __int64 v4; // rbx

  RtlAcquireResourceExclusive(this + 1, 1u);
  for ( i = 0; i != 11; ++i )
  {
    v3 = *((_QWORD *)&this->Lock.DebugInfo + i);
    if ( v3 )
    {
      do
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v3 + 8) + 8LL))(*(_QWORD *)(v3 + 8));
        v4 = *(_QWORD *)(v3 + 16);
        VaultFreeInternal((HLOCAL)v3);
        v3 = v4;
      }
      while ( v4 );
    }
  }
  memset_0(this, 0, 0x58u);
  RtlReleaseResource(this + 1);
}

```

## disassembly

```asm
0x180032ed0  push    rbx
0x180032ed2  push    rbp
0x180032ed3  push    rsi
0x180032ed4  push    rdi
0x180032ed5  push    r14
0x180032ed7  sub     rsp, 20h
0x180032edb  mov     rsi, rcx
0x180032ede  mov     dl, 1; Wait
0x180032ee0  add     rcx, 60h ; '`'; Resource
0x180032ee4  call    cs:__imp_RtlAcquireResourceExclusive
0x180032eea  xor     edi, edi
0x180032eec  mov     rbp, [rsi+rdi*8]
0x180032ef0  test    rbp, rbp
0x180032ef3  jz      short loc_180032F19
0x180032ef5  mov     rcx, [rbp+8]
0x180032ef9  mov     rax, [rcx]
0x180032efc  mov     rax, [rax+8]
0x180032f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f05  mov     rbx, [rbp+10h]
0x180032f09  mov     rcx, rbp; hMem
0x180032f0c  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180032f11  mov     rbp, rbx
0x180032f14  test    rbx, rbx
0x180032f17  jnz     short loc_180032EF5
0x180032f19  inc     rdi
0x180032f1c  cmp     rdi, 0Bh
0x180032f20  jnz     short loc_180032EEC
0x180032f22  xor     edx, edx; Val
0x180032f24  lea     r8d, [rdi+4Dh]; Size
0x180032f28  mov     rcx, rsi; void *
0x180032f2b  call    memset_0
0x180032f30  lea     rcx, [rsi+60h]
0x180032f34  add     rsp, 20h
0x180032f38  pop     r14
0x180032f3a  pop     rdi
0x180032f3b  pop     rsi
0x180032f3c  pop     rbp
0x180032f3d  pop     rbx
0x180032f3e  jmp     cs:__imp_RtlReleaseResource
```
