# CWamAdmin::QueryInterface(_GUID const &,void * *)

- ea: `0x1800039f0`
- end: `0x180003aa8`
- name: `?QueryInterface@CWamAdmin@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `184`
- prototype: `__int64 __fastcall(CWamAdmin *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ab0`
- `0x180003ac0`

## callees

- `0x1800039f0`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall CWamAdmin::QueryInterface(CWamAdmin *this, const struct _GUID *a2, void **a3)
{
  unsigned __int64 v3; // rax

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWamAdmin.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IWamAdmin.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWamAdmin2.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IWamAdmin2.Data4 )
  {
    goto LABEL_14;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMSAdminReplication.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IMSAdminReplication.Data4 )
  {
    v3 = (unsigned __int64)this + 8;
LABEL_13:
    this = (CWamAdmin *)(v3 & -(__int64)(this != 0));
LABEL_14:
    *a3 = this;
    (*(void (__fastcall **)(CWamAdmin *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IIISApplicationAdmin.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IIISApplicationAdmin.Data4 )
  {
    v3 = (unsigned __int64)this + 16;
    goto LABEL_13;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x1800039f0  sub     rsp, 28h
0x1800039f4  mov     rax, [rdx]
0x1800039f7  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800039fe  jnz     short loc_180003A0D
0x180003a00  mov     rax, [rdx+8]
0x180003a04  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180003a0b  jz      short loc_180003A84
0x180003a0d  mov     rax, [rdx]
0x180003a10  cmp     rax, qword ptr cs:IID_IWamAdmin.Data1
0x180003a17  jnz     short loc_180003A26
0x180003a19  mov     rax, [rdx+8]
0x180003a1d  cmp     rax, qword ptr cs:IID_IWamAdmin.Data4
0x180003a24  jz      short loc_180003A84
0x180003a26  mov     rax, [rdx]
0x180003a29  cmp     rax, qword ptr cs:IID_IWamAdmin2.Data1
0x180003a30  jnz     short loc_180003A3F
0x180003a32  mov     rax, [rdx+8]
0x180003a36  cmp     rax, qword ptr cs:IID_IWamAdmin2.Data4
0x180003a3d  jz      short loc_180003A84
0x180003a3f  mov     rax, [rdx]
0x180003a42  cmp     rax, qword ptr cs:IID_IMSAdminReplication.Data1
0x180003a49  jnz     short loc_180003A5E
0x180003a4b  mov     rax, [rdx+8]
0x180003a4f  cmp     rax, qword ptr cs:IID_IMSAdminReplication.Data4
0x180003a56  jnz     short loc_180003A5E
0x180003a58  lea     rax, [rcx+8]
0x180003a5c  jmp     short loc_180003A7B
0x180003a5e  mov     rax, [rdx]
0x180003a61  cmp     rax, qword ptr cs:IID_IIISApplicationAdmin.Data1
0x180003a68  jnz     short loc_180003A97
0x180003a6a  mov     rax, [rdx+8]
0x180003a6e  cmp     rax, qword ptr cs:IID_IIISApplicationAdmin.Data4
0x180003a75  jnz     short loc_180003A97
0x180003a77  lea     rax, [rcx+10h]
0x180003a7b  neg     rcx
0x180003a7e  sbb     rcx, rcx
0x180003a81  and     rcx, rax
0x180003a84  mov     [r8], rcx
0x180003a87  mov     rax, [rcx]
0x180003a8a  mov     rax, [rax+8]
0x180003a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a93  xor     eax, eax
0x180003a95  jmp     short loc_180003AA3
0x180003a97  mov     qword ptr [r8], 0
0x180003a9e  mov     eax, 80004002h
0x180003aa3  add     rsp, 28h
0x180003aa7  retn
```
