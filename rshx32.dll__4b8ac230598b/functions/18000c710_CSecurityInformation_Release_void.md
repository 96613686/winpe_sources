# CSecurityInformation::Release(void)

- ea: `0x18000c710`
- end: `0x18000c735`
- name: `?Release@CSecurityInformation@@UEAAKXZ`
- size: `37`
- prototype: `__int64 __fastcall(CSecurityInformation *this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006160`
- `0x180006170`
- `0x180006180`
- `0x180006190`
- `0x1800061a0`

## callees

- `0x18000c710`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CSecurityInformation::Release(CSecurityInformation *this)
{
  bool v1; // zf
  __int64 result; // rax

  v1 = (*((_DWORD *)this + 12))-- == 1;
  result = *((unsigned int *)this + 12);
  if ( v1 )
  {
    (*(void (__fastcall **)(CSecurityInformation *, __int64))(*(_QWORD *)this + 80LL))(this, 1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c710  sub     rsp, 28h
0x18000c714  add     dword ptr [rcx+30h], 0FFFFFFFFh
0x18000c718  mov     eax, [rcx+30h]
0x18000c71b  jnz     short loc_18000C730
0x18000c71d  mov     rax, [rcx]
0x18000c720  mov     edx, 1
0x18000c725  mov     rax, [rax+50h]
0x18000c729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c72e  xor     eax, eax
0x18000c730  add     rsp, 28h
0x18000c734  retn
```
