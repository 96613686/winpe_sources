# CDbAccessor::Shutdown(void)

- ea: `0x1800196b0`
- end: `0x18001975b`
- name: `?Shutdown@CDbAccessor@@QEAAXXZ`
- size: `171`
- prototype: `void __fastcall(CDbAccessor *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003170`
- `0x1800190d0`

## callees

- `0x1800193f0`
- `0x1800196b0`
- `0x180031010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180019719`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001973f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180019719`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001973f`

## pseudocode

```c
void __fastcall CDbAccessor::Shutdown(CDbAccessor *this)
{
  __int64 v1; // rdx
  __int64 v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  v1 = *((_QWORD *)this + 6);
  if ( v1 )
  {
    v3 = *(_QWORD *)this;
    if ( v3 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v3 + 48LL))(v3, v1, 0);
  }
  *((_QWORD *)this + 6) = 0;
  if ( *(_QWORD *)this )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
    *(_QWORD *)this = 0;
  }
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 1) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    operator delete(v5);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 6) = 0;
  CDbAccessor::ReleaseRowBuffer(this);
  v6 = (void *)*((_QWORD *)this + 4);
  if ( v6 )
  {
    operator delete(v6);
    *((_QWORD *)this + 4) = 0;
  }
  *((_DWORD *)this + 10) = 0;
}

```

## disassembly

```asm
0x1800196b0  push    rbx
0x1800196b2  sub     rsp, 20h
0x1800196b6  mov     rdx, [rcx+30h]
0x1800196ba  mov     rbx, rcx
0x1800196bd  test    rdx, rdx
0x1800196c0  jz      short loc_1800196D9
0x1800196c2  mov     rcx, [rcx]
0x1800196c5  test    rcx, rcx
0x1800196c8  jz      short loc_1800196D9
0x1800196ca  mov     rax, [rcx]
0x1800196cd  xor     r8d, r8d
0x1800196d0  mov     rax, [rax+30h]
0x1800196d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196d9  and     qword ptr [rbx+30h], 0
0x1800196de  mov     rcx, [rbx]
0x1800196e1  test    rcx, rcx
0x1800196e4  jz      short loc_1800196F6
0x1800196e6  mov     rax, [rcx]
0x1800196e9  mov     rax, [rax+10h]
0x1800196ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196f2  and     qword ptr [rbx], 0
0x1800196f6  mov     rcx, [rbx+8]
0x1800196fa  test    rcx, rcx
0x1800196fd  jz      short loc_180019710
0x1800196ff  mov     rax, [rcx]
0x180019702  mov     rax, [rax+10h]
0x180019706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001970b  and     qword ptr [rbx+8], 0
0x180019710  mov     rcx, [rbx+10h]
0x180019714  test    rcx, rcx
0x180019717  jz      short loc_18001972A
0x180019719  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180019720  nop     dword ptr [rax+rax+00h]
0x180019725  and     qword ptr [rbx+10h], 0
0x18001972a  and     dword ptr [rbx+18h], 0
0x18001972e  mov     rcx, rbx; this
0x180019731  call    ?ReleaseRowBuffer@CDbAccessor@@QEAAXXZ; CDbAccessor::ReleaseRowBuffer(void)
0x180019736  mov     rcx, [rbx+20h]
0x18001973a  test    rcx, rcx
0x18001973d  jz      short loc_180019750
0x18001973f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180019746  nop     dword ptr [rax+rax+00h]
0x18001974b  and     qword ptr [rbx+20h], 0
0x180019750  and     dword ptr [rbx+28h], 0
0x180019754  add     rsp, 20h
0x180019758  pop     rbx
0x180019759  retn
```
