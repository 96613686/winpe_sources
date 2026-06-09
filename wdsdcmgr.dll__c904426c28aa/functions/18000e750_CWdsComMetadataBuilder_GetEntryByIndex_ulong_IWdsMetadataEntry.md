# CWdsComMetadataBuilder::GetEntryByIndex(ulong,IWdsMetadataEntry * *)

- ea: `0x18000e750`
- end: `0x18000e840`
- name: `?GetEntryByIndex@CWdsComMetadataBuilder@@UEAAJKPEAPEAUIWdsMetadataEntry@@@Z`
- size: `240`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned int, struct IWdsMetadataEntry **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ad94`
- `0x18000e750`
- `0x180011854`
- `0x180014ee0`
- `0x180015cc0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e77f`
- `KERNEL32!EnterCriticalSection` at `0x18000e77f`
- `KERNEL32!LeaveCriticalSection` at `0x18000e825`
- `KERNEL32!LeaveCriticalSection` at `0x18000e825`

## string_xrefs

- `0x18000e794`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000e7c2`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000e7eb`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::GetEntryByIndex(
        CWdsComMetadataBuilder *this,
        unsigned int a2,
        struct IWdsMetadataEntry **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  const char *v7; // rdx
  unsigned int Instance; // ebx
  const char *v9; // rdx
  const char *v10; // rdx
  struct CWdsMetadataEntry *v12; // [rsp+50h] [rbp+18h] BYREF

  v12 = 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( a3 && a2 < *((_DWORD *)this + 31)
    || (Instance = -2147024809,
        (int)ElValidateHr(-2147024809, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x152u) >= 0) )
  {
    Instance = CWdsMetadata::GetByIndex((CWdsComMetadataBuilder *)((char *)this + 64), a2, &v12);
    if ( (int)ElValidateHr(Instance, v9, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x156u) >= 0 )
    {
      Instance = CWdsComMetadataEntry::CreateInstance(v12);
      if ( (int)ElValidateHr(Instance, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x159u) >= 0 )
        *a3 = 0;
    }
  }
  LeaveCriticalSection(v3);
  return Instance;
}

```

## disassembly

```asm
0x18000e750  mov     rax, rsp
0x18000e753  mov     [rax+10h], rbx
0x18000e757  mov     [rax+20h], rbp
0x18000e75b  push    rsi
0x18000e75c  push    rdi
0x18000e75d  push    r14
0x18000e75f  sub     rsp, 20h
0x18000e763  and     qword ptr [rax+18h], 0
0x18000e768  lea     rsi, [rcx+88h]
0x18000e76f  and     qword ptr [rax+8], 0
0x18000e774  mov     rdi, rcx
0x18000e777  mov     rcx, rsi; lpCriticalSection
0x18000e77a  mov     r14, r8
0x18000e77d  mov     ebp, edx
0x18000e77f  call    cs:__imp_EnterCriticalSection
0x18000e785  test    r14, r14
0x18000e788  jz      short loc_18000E78F
0x18000e78a  cmp     ebp, [rdi+7Ch]
0x18000e78d  jb      short loc_18000E7AC
0x18000e78f  mov     ebx, 80070057h
0x18000e794  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e79b  mov     ecx, ebx; int
0x18000e79d  mov     r9d, 152h; unsigned int
0x18000e7a3  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000e7a8  test    eax, eax
0x18000e7aa  js      short loc_18000E822
0x18000e7ac  lea     rcx, [rdi+40h]; this
0x18000e7b0  mov     edx, ebp; unsigned int
0x18000e7b2  lea     r8, [rsp+38h+arg_10]; struct CWdsMetadataEntry **
0x18000e7b7  call    ?GetByIndex@CWdsMetadata@@QEBAKKPEAPEBVCWdsMetadataEntry@@@Z; CWdsMetadata::GetByIndex(ulong,CWdsMetadataEntry const * *)
0x18000e7bc  mov     r9d, 156h; unsigned int
0x18000e7c2  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e7c9  mov     ecx, eax; int
0x18000e7cb  mov     ebx, eax
0x18000e7cd  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000e7d2  test    eax, eax
0x18000e7d4  js      short loc_18000E822
0x18000e7d6  mov     rcx, [rsp+38h+arg_10]; struct CWdsMetadataEntry *
0x18000e7db  lea     rdx, [rsp+38h+arg_0]
0x18000e7e0  call    ?CreateInstance@CWdsComMetadataEntry@@SAJPEBVCWdsMetadataEntry@@PEAPEAV?$CComObject@VCWdsComMetadataEntry@@@ATL@@@Z; CWdsComMetadataEntry::CreateInstance(CWdsMetadataEntry const *,ATL::CComObject<CWdsComMetadataEntry> * *)
0x18000e7e5  mov     r9d, 159h; unsigned int
0x18000e7eb  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e7f2  mov     ecx, eax; int
0x18000e7f4  mov     ebx, eax
0x18000e7f6  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000e7fb  test    eax, eax
0x18000e7fd  js      short loc_18000E80B
0x18000e7ff  mov     rax, [rsp+38h+arg_0]
0x18000e804  xor     ecx, ecx
0x18000e806  mov     [r14], rax
0x18000e809  jmp     short loc_18000E810
0x18000e80b  mov     rcx, [rsp+38h+arg_0]
0x18000e810  test    rcx, rcx
0x18000e813  jz      short loc_18000E822
0x18000e815  mov     rax, [rcx]
0x18000e818  mov     rax, [rax+10h]
0x18000e81c  call    cs:__guard_dispatch_icall_fptr
0x18000e822  mov     rcx, rsi; lpCriticalSection
0x18000e825  call    cs:__imp_LeaveCriticalSection
0x18000e82b  mov     rbp, [rsp+38h+arg_18]
0x18000e830  mov     eax, ebx
0x18000e832  mov     rbx, [rsp+38h+arg_8]
0x18000e837  add     rsp, 20h
0x18000e83b  pop     r14
0x18000e83d  pop     rdi
0x18000e83e  pop     rsi
0x18000e83f  retn
```
