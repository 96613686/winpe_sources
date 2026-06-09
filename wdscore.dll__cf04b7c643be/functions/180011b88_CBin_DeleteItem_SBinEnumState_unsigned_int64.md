# CBin::DeleteItem(SBinEnumState *,unsigned __int64)

- ea: `0x180011b88`
- end: `0x180011c46`
- name: `?DeleteItem@CBin@@QEAAHPEAUSBinEnumState@@_K@Z`
- size: `190`
- prototype: `__int64 __fastcall(CBin *__hidden this, struct SBinEnumState *, unsigned __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180013b28`
- `0x1800142c8`

## callees

- `0x180011b88`
- `0x1800132f8`
- `0x1800134ec`
- `0x180016694`
- `0x180018638`

## pseudocode

```c
__int64 __fastcall CBin::DeleteItem(CBin *this, struct SBinEnumState *a2, void *a3)
{
  __int64 v4; // rdi
  bool v5; // zf
  struct SMainPageHeader *v7; // rax
  _QWORD v8[3]; // [rsp+40h] [rbp-18h] BYREF
  void *v9; // [rsp+68h] [rbp+10h] BYREF
  void *v10; // [rsp+70h] [rbp+18h] BYREF

  v10 = a3;
  v9 = a2;
  if ( !*((_DWORD *)this + 74) )
    return 0;
  v4 = *((_QWORD *)this + 27);
  v5 = *((_DWORD *)this + 58) == 0;
  v8[0] = v4;
  if ( v5 )
  {
    v10 = 0;
    v7 = CBin::MapPageHeader(this, &v10);
    if ( !v7 )
      return 0;
    *((_QWORD *)v7 + 4) = v4;
    CBin::UnmapPageHeader(this, v10);
  }
  else
  {
    CBin::EnumRestoreState(this, (CBin *)((char *)this + 232));
    v9 = 0;
    v10 = 0;
    if ( !(unsigned int)CBin::EnumReadWrite(this, 0, (unsigned __int64)v8, 8u, &v9, (unsigned __int64 *)&v10, 8u) )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180011b88  mov     rax, rsp
0x180011b8b  mov     [rax+8], rbx
0x180011b8f  mov     [rax+18h], r8
0x180011b93  mov     [rax+10h], rdx
0x180011b97  push    rdi
0x180011b98  sub     rsp, 50h
0x180011b9c  cmp     dword ptr [rcx+128h], 0
0x180011ba3  mov     rbx, rcx
0x180011ba6  jz      short loc_180011C08
0x180011ba8  mov     rdi, [rcx+0D8h]
0x180011baf  lea     rdx, [rcx+0E8h]; struct SBinEnumState *
0x180011bb6  cmp     dword ptr [rdx], 0
0x180011bb9  mov     [rax-18h], rdi
0x180011bbd  jz      short loc_180011C16
0x180011bbf  call    ?EnumRestoreState@CBin@@QEAAHAEAUSBinEnumState@@@Z; CBin::EnumRestoreState(SBinEnumState &)
0x180011bc4  mov     r9d, 8; unsigned __int64
0x180011bca  mov     [rsp+58h+arg_8], 0
0x180011bd3  mov     [rsp+58h+var_28], r9; unsigned __int64
0x180011bd8  lea     rax, [rsp+58h+arg_10]
0x180011bdd  mov     [rsp+58h+var_30], rax; unsigned __int64 *
0x180011be2  lea     r8, [rsp+58h+var_18]; void *
0x180011be7  lea     rax, [rsp+58h+arg_8]
0x180011bec  mov     [rsp+58h+arg_10], 0
0x180011bf5  xor     edx, edx; int
0x180011bf7  mov     [rsp+58h+var_38], rax; void **
0x180011bfc  mov     rcx, rbx; this
0x180011bff  call    ?EnumReadWrite@CBin@@QEAAHHPEAX_KAEAPEAXAEA_K1@Z; CBin::EnumReadWrite(int,void *,unsigned __int64,void * &,unsigned __int64 &,unsigned __int64)
0x180011c04  test    eax, eax
0x180011c06  jnz     short loc_180011C3F
0x180011c08  xor     eax, eax
0x180011c0a  mov     rbx, [rsp+58h+arg_0]
0x180011c0f  add     rsp, 50h
0x180011c13  pop     rdi
0x180011c14  retn
0x180011c16  lea     rdx, [rsp+58h+arg_10]; void **
0x180011c1b  mov     [rsp+58h+arg_10], 0
0x180011c24  call    ?MapPageHeader@CBin@@AEAAPEAUSMainPageHeader@@PEAPEAX@Z; CBin::MapPageHeader(void * *)
0x180011c29  test    rax, rax
0x180011c2c  jz      short loc_180011C08
0x180011c2e  mov     [rax+20h], rdi
0x180011c32  mov     rcx, rbx; this
0x180011c35  mov     rdx, [rsp+58h+arg_10]; void *
0x180011c3a  call    ?UnmapPageHeader@CBin@@AEAAHPEAX@Z; CBin::UnmapPageHeader(void *)
0x180011c3f  mov     eax, 1
0x180011c44  jmp     short loc_180011C0A
```
