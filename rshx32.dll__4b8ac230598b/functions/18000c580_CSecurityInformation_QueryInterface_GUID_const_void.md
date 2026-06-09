# CSecurityInformation::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c580`
- end: `0x18000c694`
- name: `?QueryInterface@CSecurityInformation@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: `__int64 __fastcall(CSecurityInformation *this, const struct _GUID *, CSecurityInformation **)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006110`
- `0x180006120`
- `0x180006130`
- `0x180006140`
- `0x180006150`

## callees

- `0x18000c580`

## pseudocode

```c
__int64 __fastcall CSecurityInformation::QueryInterface(
        CSecurityInformation *this,
        const struct _GUID *a2,
        CSecurityInformation **a3)
{
  CSecurityInformation *v4; // rax
  unsigned __int64 v5; // rcx

  if ( *(_OWORD *)a2 == *(_OWORD *)&IID_IUnknown
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISecurityInformation.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISecurityInformation.Data4 )
  {
    v4 = this;
LABEL_25:
    *a3 = v4;
    ++*((_DWORD *)this + 12);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IEffectivePermission.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IEffectivePermission.Data4 )
  {
    v5 = (unsigned __int64)this + 8;
LABEL_24:
    v4 = (CSecurityInformation *)(v5 & -(__int64)(this != 0));
    goto LABEL_25;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISecurityInformation3.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISecurityInformation3.Data4
    && *((_DWORD *)this + 13) == 1 )
  {
    v5 = (unsigned __int64)this + 32;
    goto LABEL_24;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISecurityInformation4.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISecurityInformation4.Data4
    && *((_DWORD *)this + 13) == 1 )
  {
    v5 = (unsigned __int64)this + 40;
    goto LABEL_24;
  }
  if ( *((_DWORD *)this + 13) != 3 )
  {
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISecurityObjectTypeInfo.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISecurityObjectTypeInfo.Data4 )
    {
      v5 = (unsigned __int64)this + 24;
      goto LABEL_24;
    }
    if ( *((_DWORD *)this + 13) == 1
      && *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IEffectivePermission2.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IEffectivePermission2.Data4 )
    {
      v5 = (unsigned __int64)this + 16;
      goto LABEL_24;
    }
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000c580  mov     rax, [rdx]
0x18000c583  mov     r9, rcx
0x18000c586  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000c58d  jnz     short loc_18000C59C
0x18000c58f  mov     rax, [rdx+8]
0x18000c593  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000c59a  jz      short loc_18000C5B5
0x18000c59c  mov     rax, [rdx]
0x18000c59f  cmp     rax, qword ptr cs:IID_ISecurityInformation.Data1
0x18000c5a6  jnz     short loc_18000C5BD
0x18000c5a8  mov     rax, [rdx+8]
0x18000c5ac  cmp     rax, qword ptr cs:IID_ISecurityInformation.Data4
0x18000c5b3  jnz     short loc_18000C5BD
0x18000c5b5  mov     rax, r9
0x18000c5b8  jmp     loc_18000C67D
0x18000c5bd  mov     rax, [rdx]
0x18000c5c0  cmp     rax, qword ptr cs:IID_IEffectivePermission.Data1
0x18000c5c7  jnz     short loc_18000C5DF
0x18000c5c9  mov     rax, [rdx+8]
0x18000c5cd  cmp     rax, qword ptr cs:IID_IEffectivePermission.Data4
0x18000c5d4  jnz     short loc_18000C5DF
0x18000c5d6  add     rcx, 8
0x18000c5da  jmp     loc_18000C671
0x18000c5df  mov     rax, [rdx]
0x18000c5e2  cmp     rax, qword ptr cs:IID_ISecurityInformation3.Data1
0x18000c5e9  jnz     short loc_18000C604
0x18000c5eb  mov     rax, [rdx+8]
0x18000c5ef  cmp     rax, qword ptr cs:IID_ISecurityInformation3.Data4
0x18000c5f6  jnz     short loc_18000C604
0x18000c5f8  cmp     dword ptr [rcx+34h], 1
0x18000c5fc  jnz     short loc_18000C604
0x18000c5fe  add     rcx, 20h ; ' '
0x18000c602  jmp     short loc_18000C671
0x18000c604  mov     rax, [rdx]
0x18000c607  cmp     rax, qword ptr cs:IID_ISecurityInformation4.Data1
0x18000c60e  jnz     short loc_18000C629
0x18000c610  mov     rax, [rdx+8]
0x18000c614  cmp     rax, qword ptr cs:IID_ISecurityInformation4.Data4
0x18000c61b  jnz     short loc_18000C629
0x18000c61d  cmp     dword ptr [rcx+34h], 1
0x18000c621  jnz     short loc_18000C629
0x18000c623  add     rcx, 28h ; '('
0x18000c627  jmp     short loc_18000C671
0x18000c629  cmp     dword ptr [rcx+34h], 3
0x18000c62d  jz      short loc_18000C687
0x18000c62f  mov     rax, [rdx]
0x18000c632  cmp     rax, qword ptr cs:IID_ISecurityObjectTypeInfo.Data1
0x18000c639  jnz     short loc_18000C64E
0x18000c63b  mov     rax, [rdx+8]
0x18000c63f  cmp     rax, qword ptr cs:IID_ISecurityObjectTypeInfo.Data4
0x18000c646  jnz     short loc_18000C64E
0x18000c648  add     rcx, 18h
0x18000c64c  jmp     short loc_18000C671
0x18000c64e  cmp     dword ptr [rcx+34h], 1
0x18000c652  jnz     short loc_18000C687
0x18000c654  mov     rax, [rdx]
0x18000c657  cmp     rax, qword ptr cs:IID_IEffectivePermission2.Data1
0x18000c65e  jnz     short loc_18000C687
0x18000c660  mov     rax, [rdx+8]
0x18000c664  cmp     rax, qword ptr cs:IID_IEffectivePermission2.Data4
0x18000c66b  jnz     short loc_18000C687
0x18000c66d  add     rcx, 10h
0x18000c671  mov     rax, r9
0x18000c674  neg     rax
0x18000c677  sbb     rax, rax
0x18000c67a  and     rax, rcx
0x18000c67d  mov     [r8], rax
0x18000c680  inc     dword ptr [r9+30h]
0x18000c684  xor     eax, eax
0x18000c686  retn
0x18000c687  mov     qword ptr [r8], 0
0x18000c68e  mov     eax, 80004002h
0x18000c693  retn
```
