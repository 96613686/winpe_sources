# CWdsComMetadataBuilder::Clone(IWdsMetadataBuilder * *)

- ea: `0x18000ef20`
- end: `0x18000efaa`
- name: `?Clone@CWdsComMetadataBuilder@@UEAAJPEAPEAUIWdsMetadataBuilder@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(CWdsComMetadataBuilder *__hidden this, struct IWdsMetadataBuilder **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e504`
- `0x18000ef20`
- `0x180014ee0`
- `0x180015cc0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000ef3f`
- `KERNEL32!EnterCriticalSection` at `0x18000ef3f`
- `KERNEL32!LeaveCriticalSection` at `0x18000ef92`
- `KERNEL32!LeaveCriticalSection` at `0x18000ef92`

## string_xrefs

- `0x18000ef5f`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::Clone(CWdsComMetadataBuilder *this, struct IWdsMetadataBuilder **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  unsigned int v5; // ebx
  const char *v6; // rdx
  int v7; // eax
  CWdsComMetadataBuilder *v8; // rcx
  CWdsComMetadataBuilder *v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v10 = 0;
  v5 = CWdsComMetadataBuilder::CreateInstance((CWdsComMetadataBuilder *)((char *)this + 64), &v10);
  v7 = ElValidateHr(v5, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x2AFu);
  v8 = v10;
  if ( v7 >= 0 )
  {
    *a2 = v10;
    v8 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(CWdsComMetadataBuilder *))(*(_QWORD *)v8 + 16LL))(v8);
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x18000ef20  mov     [rsp+arg_8], rbx
0x18000ef25  mov     [rsp+arg_10], rsi
0x18000ef2a  push    rdi
0x18000ef2b  sub     rsp, 20h
0x18000ef2f  lea     rdi, [rcx+88h]
0x18000ef36  mov     rbx, rcx
0x18000ef39  mov     rcx, rdi; lpCriticalSection
0x18000ef3c  mov     rsi, rdx
0x18000ef3f  call    cs:__imp_EnterCriticalSection
0x18000ef45  and     [rsp+28h+arg_0], 0
0x18000ef4b  lea     rcx, [rbx+40h]; struct CWdsMetadata *
0x18000ef4f  lea     rdx, [rsp+28h+arg_0]
0x18000ef54  call    ?CreateInstance@CWdsComMetadataBuilder@@SAJPEBVCWdsMetadata@@PEAPEAV?$CComObject@VCWdsComMetadataBuilder@@@ATL@@@Z; CWdsComMetadataBuilder::CreateInstance(CWdsMetadata const *,ATL::CComObject<CWdsComMetadataBuilder> * *)
0x18000ef59  mov     r9d, 2AFh; unsigned int
0x18000ef5f  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000ef66  mov     ecx, eax; int
0x18000ef68  mov     ebx, eax
0x18000ef6a  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000ef6f  mov     rcx, [rsp+28h+arg_0]
0x18000ef74  test    eax, eax
0x18000ef76  js      short loc_18000EF7D
0x18000ef78  mov     [rsi], rcx
0x18000ef7b  xor     ecx, ecx
0x18000ef7d  test    rcx, rcx
0x18000ef80  jz      short loc_18000EF8F
0x18000ef82  mov     rax, [rcx]
0x18000ef85  mov     rax, [rax+10h]
0x18000ef89  call    cs:__guard_dispatch_icall_fptr
0x18000ef8f  mov     rcx, rdi; lpCriticalSection
0x18000ef92  call    cs:__imp_LeaveCriticalSection
0x18000ef98  mov     rsi, [rsp+28h+arg_10]
0x18000ef9d  mov     eax, ebx
0x18000ef9f  mov     rbx, [rsp+28h+arg_8]
0x18000efa4  add     rsp, 20h
0x18000efa8  pop     rdi
0x18000efa9  retn
```
