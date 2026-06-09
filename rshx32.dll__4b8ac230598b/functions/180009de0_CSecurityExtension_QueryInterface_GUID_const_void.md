# CSecurityExtension::QueryInterface(_GUID const &,void * *)

- ea: `0x180009de0`
- end: `0x180009e7f`
- name: `?QueryInterface@CSecurityExtension@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `159`
- prototype: `__int64 __fastcall(CSecurityExtension *this, const struct _GUID *, CSecurityExtension **)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009e90`
- `0x180009ea0`

## callees

- `0x180009de0`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::QueryInterface(
        CSecurityExtension *this,
        const struct _GUID *a2,
        CSecurityExtension **a3)
{
  CSecurityExtension *v4; // rax
  unsigned __int64 v5; // rcx

  if ( *(_OWORD *)a2 == *(_OWORD *)&IID_IUnknown
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IShellExtInit.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IShellExtInit.Data4 )
  {
    v4 = this;
LABEL_13:
    *a3 = v4;
    ++*((_DWORD *)this + 6);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IShellPropSheetExt.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IShellPropSheetExt.Data4 )
  {
    v5 = (unsigned __int64)this + 8;
LABEL_12:
    v4 = (CSecurityExtension *)(v5 & -(__int64)(this != 0));
    goto LABEL_13;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IElevatedNtfsSecurity.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IElevatedNtfsSecurity.Data4
    && *((_DWORD *)this + 7) == 1 )
  {
    v5 = (unsigned __int64)this + 16;
    goto LABEL_12;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x180009de0  mov     rax, [rdx]
0x180009de3  mov     r9, rcx
0x180009de6  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180009ded  jnz     short loc_180009DFC
0x180009def  mov     rax, [rdx+8]
0x180009df3  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180009dfa  jz      short loc_180009E15
0x180009dfc  mov     rax, [rdx]
0x180009dff  cmp     rax, qword ptr cs:IID_IShellExtInit.Data1
0x180009e06  jnz     short loc_180009E1A
0x180009e08  mov     rax, [rdx+8]
0x180009e0c  cmp     rax, qword ptr cs:IID_IShellExtInit.Data4
0x180009e13  jnz     short loc_180009E1A
0x180009e15  mov     rax, r9
0x180009e18  jmp     short loc_180009E68
0x180009e1a  mov     rax, [rdx]
0x180009e1d  cmp     rax, qword ptr cs:IID_IShellPropSheetExt.Data1
0x180009e24  jnz     short loc_180009E39
0x180009e26  mov     rax, [rdx+8]
0x180009e2a  cmp     rax, qword ptr cs:IID_IShellPropSheetExt.Data4
0x180009e31  jnz     short loc_180009E39
0x180009e33  add     rcx, 8
0x180009e37  jmp     short loc_180009E5C
0x180009e39  mov     rax, [rdx]
0x180009e3c  cmp     rax, qword ptr cs:IID_IElevatedNtfsSecurity.Data1
0x180009e43  jnz     short loc_180009E72
0x180009e45  mov     rax, [rdx+8]
0x180009e49  cmp     rax, qword ptr cs:IID_IElevatedNtfsSecurity.Data4
0x180009e50  jnz     short loc_180009E72
0x180009e52  cmp     dword ptr [rcx+1Ch], 1
0x180009e56  jnz     short loc_180009E72
0x180009e58  add     rcx, 10h
0x180009e5c  mov     rax, r9
0x180009e5f  neg     rax
0x180009e62  sbb     rax, rax
0x180009e65  and     rax, rcx
0x180009e68  mov     [r8], rax
0x180009e6b  inc     dword ptr [r9+18h]
0x180009e6f  xor     eax, eax
0x180009e71  retn
0x180009e72  mov     qword ptr [r8], 0
0x180009e79  mov     eax, 80004002h
0x180009e7e  retn
```
