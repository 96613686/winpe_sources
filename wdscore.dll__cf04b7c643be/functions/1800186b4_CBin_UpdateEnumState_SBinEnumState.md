# CBin::UpdateEnumState(SBinEnumState &)

- ea: `0x1800186b4`
- end: `0x180018750`
- name: `?UpdateEnumState@CBin@@QEAAHAEAUSBinEnumState@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(CBin *__hidden this, struct SBinEnumState *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180011264`
- `0x1800134ec`

## callees

- `0x1800186b4`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall CBin::UpdateEnumState(CBin *this, struct SBinEnumState *a2)
{
  int v2; // eax
  __int64 v5; // rdx
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 18);
  v8 = 0;
  if ( *((_DWORD *)a2 + 1) != v2 )
  {
    if ( *(_DWORD *)a2 )
    {
      v5 = *((_QWORD *)a2 + 2);
      if ( v5 )
      {
        *((_DWORD *)a2 + 1) = v2;
        result = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64 *))(**((_QWORD **)this + 13) + 16LL))(
                   *((_QWORD *)this + 13),
                   (v5 + 1) << 8,
                   256,
                   &v8);
        if ( !result )
          return result;
        *((_QWORD *)a2 + 4) = (*((_QWORD *)a2 + 2) + 1LL + *(_QWORD *)result) << 8;
        v7 = v8;
        *((_QWORD *)a2 + 1) = *(_QWORD *)(result + 8);
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13), v7);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800186b4  mov     [rsp+arg_8], rbx
0x1800186b9  push    rdi
0x1800186ba  sub     rsp, 30h
0x1800186be  mov     eax, [rcx+48h]
0x1800186c1  mov     rbx, rdx
0x1800186c4  mov     rdi, rcx
0x1800186c7  mov     [rsp+38h+arg_0], 0
0x1800186d0  cmp     [rdx+4], eax
0x1800186d3  jz      short loc_18001873F
0x1800186d5  cmp     dword ptr [rdx], 0
0x1800186d8  jz      short loc_18001873F
0x1800186da  mov     rdx, [rdx+10h]
0x1800186de  test    rdx, rdx
0x1800186e1  jz      short loc_18001873F
0x1800186e3  mov     [rbx+4], eax
0x1800186e6  lea     r9, [rsp+38h+arg_0]
0x1800186eb  mov     rcx, [rcx+68h]
0x1800186ef  inc     rdx
0x1800186f2  shl     rdx, 8
0x1800186f6  mov     r8d, 100h
0x1800186fc  mov     rax, [rcx]
0x1800186ff  mov     rax, [rax+10h]
0x180018703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018708  test    rax, rax
0x18001870b  jz      short loc_180018744
0x18001870d  mov     rdx, [rax]
0x180018710  mov     rcx, [rbx+10h]
0x180018714  inc     rcx
0x180018717  add     rdx, rcx
0x18001871a  shl     rdx, 8
0x18001871e  mov     [rbx+20h], rdx
0x180018722  mov     rax, [rax+8]
0x180018726  mov     rdx, [rsp+38h+arg_0]
0x18001872b  mov     [rbx+8], rax
0x18001872f  mov     rcx, [rdi+68h]
0x180018733  mov     rax, [rcx]
0x180018736  mov     rax, [rax+18h]
0x18001873a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001873f  mov     eax, 1
0x180018744  mov     rbx, [rsp+38h+arg_8]
0x180018749  add     rsp, 30h
0x18001874d  pop     rdi
0x18001874e  retn
```
