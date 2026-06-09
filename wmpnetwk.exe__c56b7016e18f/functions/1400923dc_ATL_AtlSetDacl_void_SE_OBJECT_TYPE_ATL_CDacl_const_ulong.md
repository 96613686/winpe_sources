# ATL::AtlSetDacl(void *,_SE_OBJECT_TYPE,ATL::CDacl const &,ulong)

- ea: `0x1400923dc`
- end: `0x14009243f`
- name: `?AtlSetDacl@ATL@@YA_NPEAXW4_SE_OBJECT_TYPE@@AEBVCDacl@1@K@Z`
- size: `99`
- prototype: `bool __fastcall(HANDLE handle, SE_OBJECT_TYPE ObjectType, const struct ATL::CDacl *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140093330`
- `0x140093924`

## callees

- `0x14004ddd0`
- `0x1400923dc`

## import_xrefs

- `ADVAPI32!SetSecurityInfo` at `0x14009241f`
- `ADVAPI32!SetSecurityInfo` at `0x14009241f`
- `KERNEL32!SetLastError` at `0x140092429`
- `KERNEL32!SetLastError` at `0x140092429`

## pseudocode

```c
bool __fastcall ATL::AtlSetDacl(HANDLE handle, SE_OBJECT_TYPE ObjectType, const struct ATL::CDacl *this)
{
  struct _ACL *pDacl; // rax
  DWORD v7; // ebx

  if ( !handle )
    return 0;
  pDacl = (struct _ACL *)ATL::CAcl::GetPACL(this);
  v7 = SetSecurityInfo(handle, ObjectType, 4u, 0, 0, pDacl, 0);
  SetLastError(v7);
  return v7 == 0;
}

```

## disassembly

```asm
0x1400923dc  mov     [rsp+arg_0], rbx
0x1400923e1  push    rdi
0x1400923e2  sub     rsp, 40h
0x1400923e6  mov     edi, edx
0x1400923e8  mov     rbx, rcx
0x1400923eb  test    rcx, rcx
0x1400923ee  jnz     short loc_1400923F4
0x1400923f0  xor     al, al
0x1400923f2  jmp     short loc_140092434
0x1400923f4  mov     rcx, r8; this
0x1400923f7  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x1400923fc  xor     r9d, r9d; psidOwner
0x1400923ff  mov     [rsp+48h+pSacl], 0; pSacl
0x140092408  mov     [rsp+48h+pDacl], rax; pDacl
0x14009240d  mov     edx, edi; ObjectType
0x14009240f  mov     rcx, rbx; handle
0x140092412  mov     [rsp+48h+psidGroup], 0; psidGroup
0x14009241b  lea     r8d, [r9+4]; SecurityInfo
0x14009241f  call    cs:__imp_SetSecurityInfo
0x140092425  mov     ecx, eax; dwErrCode
0x140092427  mov     ebx, eax
0x140092429  call    cs:__imp_SetLastError
0x14009242f  test    ebx, ebx
0x140092431  setz    al
0x140092434  mov     rbx, [rsp+48h+arg_0]
0x140092439  add     rsp, 40h
0x14009243d  pop     rdi
0x14009243e  retn
```
