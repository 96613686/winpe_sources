# CWdsMetadata::AppendEntry(ushort const *)

- ea: `0x18000d57c`
- end: `0x18000d632`
- name: `?AppendEntry@CWdsMetadata@@QEAAKPEBG@Z`
- size: `182`
- prototype: `unsigned int __fastcall(CWdsMetadata *__hidden this, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `6`
- tags: ``

## callers

- `0x1800096e8`
- `0x18000d2ac`
- `0x18000d39c`
- `0x18000d638`
- `0x18000d754`
- `0x18000d8c4`
- `0x18000d980`
- `0x18000db14`
- `0x180010c74`
- `0x180013b90`
- `0x1800152b4`

## callees

- `0x1800015d8`
- `0x18000d188`
- `0x18000d57c`
- `0x18000e110`
- `0x18000e5f8`
- `0x18000fd28`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::AppendEntry(CWdsMetadata *this, const unsigned __int16 *a2)
{
  CWdsMetadataEntry *v4; // rax
  CWdsMetadataEntry *v5; // rbx
  unsigned int inserted; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // edx
  __int64 v10; // rdx
  __int64 v11; // r8

  v4 = (CWdsMetadataEntry *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    *((_DWORD *)v4 + 10) = 0;
    *((_OWORD *)v4 + 3) = 0;
    *(_QWORD *)v4 = 0;
    *((_QWORD *)v4 + 1) = 0;
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 3) = 0;
    *((_DWORD *)v4 + 8) = 0;
    *((_DWORD *)v4 + 9) = 0;
    inserted = CWdsMetadataEntry::Initialize(v4, a2);
    if ( (unsigned int)ElValidateWin32_2(inserted, v7, v8, 0x1077u)
      || (inserted = CWdsMetadata::InsertEntryAtIndex(this, v5, *((_DWORD *)this + 15)),
          (unsigned int)ElValidateWin32_2(inserted, v10, v11, 0x107Au)) )
    {
      CWdsMetadataEntry::`scalar deleting destructor'(v5, v9);
    }
  }
  else
  {
    return 8;
  }
  return inserted;
}

```

## disassembly

```asm
0x18000d57c  mov     [rsp+arg_0], rbx
0x18000d581  mov     [rsp+arg_8], rsi
0x18000d586  push    rdi
0x18000d587  sub     rsp, 20h
0x18000d58b  mov     rdi, rdx
0x18000d58e  mov     rsi, rcx
0x18000d591  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d598  mov     ecx, 40h ; '@'; unsigned __int64
0x18000d59d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d5a2  mov     rbx, rax
0x18000d5a5  test    rax, rax
0x18000d5a8  jz      short loc_18000D61A
0x18000d5aa  and     dword ptr [rax+28h], 0
0x18000d5ae  xorps   xmm0, xmm0
0x18000d5b1  movups  xmmword ptr [rax+30h], xmm0
0x18000d5b5  and     qword ptr [rax], 0
0x18000d5b9  mov     rdx, rdi; unsigned __int16 *
0x18000d5bc  and     qword ptr [rax+8], 0
0x18000d5c1  mov     rcx, rax; this
0x18000d5c4  and     qword ptr [rax+10h], 0
0x18000d5c9  and     qword ptr [rax+18h], 0
0x18000d5ce  and     dword ptr [rax+20h], 0
0x18000d5d2  and     dword ptr [rax+24h], 0
0x18000d5d6  call    ?Initialize@CWdsMetadataEntry@@QEAAKPEBG@Z; CWdsMetadataEntry::Initialize(ushort const *)
0x18000d5db  mov     r9d, 1077h
0x18000d5e1  mov     ecx, eax
0x18000d5e3  mov     edi, eax
0x18000d5e5  call    ElValidateWin32_2
0x18000d5ea  test    eax, eax
0x18000d5ec  jnz     short loc_18000D610
0x18000d5ee  mov     r8d, [rsi+3Ch]; unsigned int
0x18000d5f2  mov     rdx, rbx; struct CWdsMetadataEntry *
0x18000d5f5  mov     rcx, rsi; this
0x18000d5f8  call    ?InsertEntryAtIndex@CWdsMetadata@@AEAAKPEAVCWdsMetadataEntry@@K@Z; CWdsMetadata::InsertEntryAtIndex(CWdsMetadataEntry *,ulong)
0x18000d5fd  mov     r9d, 107Ah
0x18000d603  mov     ecx, eax
0x18000d605  mov     edi, eax
0x18000d607  call    ElValidateWin32_2
0x18000d60c  test    eax, eax
0x18000d60e  jz      short loc_18000D61F
0x18000d610  mov     rcx, rbx; this
0x18000d613  call    ??_GCWdsMetadataEntry@@QEAAPEAXI@Z; CWdsMetadataEntry::`scalar deleting destructor'(uint)
0x18000d618  jmp     short loc_18000D61F
0x18000d61a  mov     edi, 8
0x18000d61f  mov     rbx, [rsp+28h+arg_0]
0x18000d624  mov     eax, edi
0x18000d626  mov     rsi, [rsp+28h+arg_8]
0x18000d62b  add     rsp, 20h
0x18000d62f  pop     rdi
0x18000d630  retn
```
