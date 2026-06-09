# CWdsComMetadataBuilder::GetMetadata(CWdsMetadata *)

- ea: `0x18000e65c`
- end: `0x18000e6be`
- name: `?GetMetadata@CWdsComMetadataBuilder@@QEAAKPEAVCWdsMetadata@@@Z`
- size: `98`
- prototype: `unsigned int(CWdsComMetadataBuilder *__hidden this, struct CWdsMetadata *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800042f4`
- `0x180004dbc`
- `0x180004f98`
- `0x180005818`
- `0x18000600c`

## callees

- `0x18000b834`
- `0x180014d58`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e67b`
- `KERNEL32!EnterCriticalSection` at `0x18000e67b`
- `KERNEL32!LeaveCriticalSection` at `0x18000e6a6`
- `KERNEL32!LeaveCriticalSection` at `0x18000e6a6`

## string_xrefs

- `0x18000e693`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::GetMetadata(CWdsComMetadataBuilder *this, struct CWdsMetadata *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  CWdsComMetadataBuilder *v3; // rbx
  const char *v5; // rdx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v3 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  LODWORD(v3) = CWdsMetadata::AppendAll(a2, (CWdsComMetadataBuilder *)((char *)v3 + 64));
  ElValidateWin32((unsigned int)v3, v5, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x106u);
  LeaveCriticalSection(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000e65c  mov     [rsp+arg_0], rbx
0x18000e661  mov     [rsp+arg_8], rsi
0x18000e666  push    rdi
0x18000e667  sub     rsp, 20h
0x18000e66b  lea     rsi, [rcx+88h]
0x18000e672  mov     rbx, rcx
0x18000e675  mov     rcx, rsi; lpCriticalSection
0x18000e678  mov     rdi, rdx
0x18000e67b  call    cs:__imp_EnterCriticalSection
0x18000e681  lea     rdx, [rbx+40h]; struct CWdsMetadata *
0x18000e685  mov     rcx, rdi; this
0x18000e688  call    ?AppendAll@CWdsMetadata@@QEAAKPEBV1@@Z; CWdsMetadata::AppendAll(CWdsMetadata const *)
0x18000e68d  mov     r9d, 106h; unsigned int
0x18000e693  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e69a  mov     ecx, eax; unsigned int
0x18000e69c  mov     ebx, eax
0x18000e69e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e6a3  mov     rcx, rsi; lpCriticalSection
0x18000e6a6  call    cs:__imp_LeaveCriticalSection
0x18000e6ac  mov     rsi, [rsp+28h+arg_8]
0x18000e6b1  mov     eax, ebx
0x18000e6b3  mov     rbx, [rsp+28h+arg_0]
0x18000e6b8  add     rsp, 20h
0x18000e6bc  pop     rdi
0x18000e6bd  retn
```
