# CWshEnvRegistry::iQueryInterface(_GUID const &,void * *)

- ea: `0x18000c5e0`
- end: `0x18000c66a`
- name: `?iQueryInterface@CWshEnvRegistry@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `138`
- prototype: `__int64 __fastcall(CWshEnvRegistry *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x180001be0`
- `0x18000c5e0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CWshEnvRegistry::iQueryInterface(CWshEnvRegistry *this, const struct _GUID *a2, void **a3)
{
  __int64 v5; // rax
  char *v6; // rax
  char *v7; // rcx
  __int64 v8; // rax

  if ( !a3 )
    return 2147500035LL;
  v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IWshEnvironment.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWshEnvironment.Data1 )
    v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IWshEnvironment.Data4;
  if ( !v5 )
  {
    v6 = (char *)this - 16;
    v7 = (char *)this - 16;
LABEL_11:
    *a3 = v6;
    (*(void (__fastcall **)(char *, const struct _GUID *, void **, CWshEnvRegistry *))(*(_QWORD *)v7 + 8LL))(
      v7,
      a2,
      a3,
      this);
    return 0;
  }
  v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IProvideClassInfo.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IProvideClassInfo.Data1 )
    v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IProvideClassInfo.Data4;
  if ( !v8 )
  {
    v7 = (char *)this - 16;
    a2 = (const struct _GUID *)((char *)this - 8);
    v6 = (char *)(((unsigned __int64)this - 8) & -(__int64)(v7 != 0));
    goto LABEL_11;
  }
  return CDispatch::iQueryInterface(this, a2, a3);
}

```

## disassembly

```asm
0x18000c5e0  sub     rsp, 28h
0x18000c5e4  mov     r9, rcx
0x18000c5e7  test    r8, r8
0x18000c5ea  jnz     short loc_18000C5F6
0x18000c5ec  mov     eax, 80004003h
0x18000c5f1  add     rsp, 28h
0x18000c5f5  retn
0x18000c5f6  mov     rax, [rdx]
0x18000c5f9  sub     rax, qword ptr cs:IID_IWshEnvironment.Data1
0x18000c600  jnz     short loc_18000C60D
0x18000c602  mov     rax, [rdx+8]
0x18000c606  sub     rax, qword ptr cs:IID_IWshEnvironment.Data4
0x18000c60d  test    rax, rax
0x18000c610  jnz     short loc_18000C61B
0x18000c612  lea     rax, [rcx-10h]
0x18000c616  mov     rcx, rax
0x18000c619  jmp     short loc_18000C64B
0x18000c61b  mov     rax, [rdx]
0x18000c61e  sub     rax, qword ptr cs:IID_IProvideClassInfo.Data1
0x18000c625  jnz     short loc_18000C632
0x18000c627  mov     rax, [rdx+8]
0x18000c62b  sub     rax, qword ptr cs:IID_IProvideClassInfo.Data4
0x18000c632  test    rax, rax
0x18000c635  jnz     short loc_18000C661
0x18000c637  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c63b  lea     rdx, [r9-8]
0x18000c63f  mov     rax, rcx
0x18000c642  neg     rax
0x18000c645  sbb     rax, rax
0x18000c648  and     rax, rdx
0x18000c64b  mov     [r8], rax
0x18000c64e  mov     rax, [rcx]
0x18000c651  mov     rax, [rax+8]
0x18000c655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c65a  xor     eax, eax
0x18000c65c  add     rsp, 28h
0x18000c660  retn
0x18000c661  add     rsp, 28h
0x18000c665  jmp     ?iQueryInterface@CDispatch@@MEAAJAEBU_GUID@@PEAPEAX@Z; CDispatch::iQueryInterface(_GUID const &,void * *)
```
