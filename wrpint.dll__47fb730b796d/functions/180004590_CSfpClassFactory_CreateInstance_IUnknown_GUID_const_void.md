# CSfpClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004590`
- end: `0x18000461f`
- name: `?CreateInstance@CSfpClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `143`
- prototype: `__int64 __fastcall(CSfpClassFactory *this, struct IUnknown *, const struct _GUID *, CSFPIntegrityCheckAndRepair **)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001300`
- `0x180002500`
- `0x180004590`

## pseudocode

```c
__int64 __fastcall CSfpClassFactory::CreateInstance(
        CSfpClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        CSFPIntegrityCheckAndRepair **a4)
{
  CSFPIntegrityCheckAndRepair *v6; // rax
  CSFPIntegrityCheckAndRepair *v7; // rax

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  if ( (*(_QWORD *)&a3->Data1 != *(_QWORD *)&IID_IUnknown.Data1 || *(_QWORD *)a3->Data4 != *(_QWORD *)IID_IUnknown.Data4)
    && (*(_QWORD *)&a3->Data1 != *(_QWORD *)&GUID_90ed9faa_a6e5_4671_8e50_1c060f8b9c47.Data1
     || *(_QWORD *)a3->Data4 != *(_QWORD *)GUID_90ed9faa_a6e5_4671_8e50_1c060f8b9c47.Data4) )
  {
    return 2147500034LL;
  }
  v6 = (CSFPIntegrityCheckAndRepair *)operator new(0xD0u);
  if ( !v6 )
    return 2147942414LL;
  v7 = CSFPIntegrityCheckAndRepair::CSFPIntegrityCheckAndRepair(v6);
  if ( !v7 )
    return 2147942414LL;
  *a4 = v7;
  return 0;
}

```

## disassembly

```asm
0x180004590  push    rbx
0x180004592  sub     rsp, 20h
0x180004596  mov     rbx, r9
0x180004599  test    r9, r9
0x18000459c  jnz     short loc_1800045A5
0x18000459e  mov     eax, 80070057h
0x1800045a3  jmp     short loc_180004619
0x1800045a5  mov     qword ptr [r9], 0
0x1800045ac  test    rdx, rdx
0x1800045af  jz      short loc_1800045B8
0x1800045b1  mov     eax, 80040110h
0x1800045b6  jmp     short loc_180004619
0x1800045b8  mov     rax, [r8]
0x1800045bb  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800045c2  jnz     short loc_1800045D1
0x1800045c4  mov     rax, [r8+8]
0x1800045c8  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800045cf  jz      short loc_1800045EA
0x1800045d1  mov     rax, [r8]
0x1800045d4  cmp     rax, qword ptr cs:_GUID_90ed9faa_a6e5_4671_8e50_1c060f8b9c47.Data1
0x1800045db  jnz     short loc_180004614
0x1800045dd  mov     rax, [r8+8]
0x1800045e1  cmp     rax, qword ptr cs:_GUID_90ed9faa_a6e5_4671_8e50_1c060f8b9c47.Data4
0x1800045e8  jnz     short loc_180004614
0x1800045ea  mov     ecx, 0D0h; Size
0x1800045ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045f4  test    rax, rax
0x1800045f7  jz      short loc_18000460D
0x1800045f9  mov     rcx, rax; this
0x1800045fc  call    ??0CSFPIntegrityCheckAndRepair@@QEAA@XZ; CSFPIntegrityCheckAndRepair::CSFPIntegrityCheckAndRepair(void)
0x180004601  test    rax, rax
0x180004604  jz      short loc_18000460D
0x180004606  mov     [rbx], rax
0x180004609  xor     eax, eax
0x18000460b  jmp     short loc_180004619
0x18000460d  mov     eax, 8007000Eh
0x180004612  jmp     short loc_180004619
0x180004614  mov     eax, 80004002h
0x180004619  add     rsp, 20h
0x18000461d  pop     rbx
0x18000461e  retn
```
