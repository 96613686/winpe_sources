# CWdsComMetadataBuilder::RemoveEntry(IWdsMetadataEntry *)

- ea: `0x1800112f0`
- end: `0x1800113a9`
- name: `?RemoveEntry@CWdsComMetadataBuilder@@UEAAJPEAUIWdsMetadataEntry@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(CWdsComMetadataBuilder *__hidden this, struct IWdsMetadataEntry *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800112f0`
- `0x180014ee0`
- `0x180015cc0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001130f`
- `KERNEL32!EnterCriticalSection` at `0x18001130f`
- `KERNEL32!LeaveCriticalSection` at `0x180011391`
- `KERNEL32!LeaveCriticalSection` at `0x180011391`
- `OLEAUT32!__imp_SysFreeString` at `0x180011382`
- `OLEAUT32!__imp_SysFreeString` at `0x180011382`

## string_xrefs

- `0x180011336`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180011368`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::RemoveEntry(CWdsComMetadataBuilder *this, struct IWdsMetadataEntry *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v5; // rax
  unsigned int v6; // ebx
  const char *v7; // rdx
  const char *v8; // rdx
  BSTR bstrString; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v5 = *(_QWORD *)a2;
  bstrString = 0;
  v6 = (*(__int64 (__fastcall **)(struct IWdsMetadataEntry *, BSTR *))(v5 + 120))(a2, &bstrString);
  if ( (int)ElValidateHr(v6, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x964u) >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(CWdsComMetadataBuilder *, BSTR))(*(_QWORD *)this + 320LL))(this, bstrString);
    ElValidateHr(v6, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x967u);
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  LeaveCriticalSection(v2);
  return v6;
}

```

## disassembly

```asm
0x1800112f0  mov     [rsp+arg_8], rbx
0x1800112f5  mov     [rsp+arg_10], rsi
0x1800112fa  push    rdi
0x1800112fb  sub     rsp, 20h
0x1800112ff  lea     rsi, [rcx+88h]
0x180011306  mov     rdi, rcx
0x180011309  mov     rcx, rsi; lpCriticalSection
0x18001130c  mov     rbx, rdx
0x18001130f  call    cs:__imp_EnterCriticalSection
0x180011315  mov     rax, [rbx]
0x180011318  lea     rdx, [rsp+28h+bstrString]
0x18001131d  and     [rsp+28h+bstrString], 0
0x180011323  mov     rcx, rbx
0x180011326  mov     rax, [rax+78h]
0x18001132a  call    cs:__guard_dispatch_icall_fptr
0x180011330  mov     r9d, 964h; unsigned int
0x180011336  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001133d  mov     ecx, eax; int
0x18001133f  mov     ebx, eax
0x180011341  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011346  test    eax, eax
0x180011348  js      short loc_180011378
0x18001134a  mov     rax, [rdi]
0x18001134d  mov     rcx, rdi
0x180011350  mov     rdx, [rsp+28h+bstrString]
0x180011355  mov     rax, [rax+140h]
0x18001135c  call    cs:__guard_dispatch_icall_fptr
0x180011362  mov     r9d, 967h; unsigned int
0x180011368  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001136f  mov     ecx, eax; int
0x180011371  mov     ebx, eax
0x180011373  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011378  mov     rcx, [rsp+28h+bstrString]; bstrString
0x18001137d  test    rcx, rcx
0x180011380  jz      short loc_18001138E
0x180011382  call    cs:__imp_SysFreeString
0x180011388  and     [rsp+28h+bstrString], 0
0x18001138e  mov     rcx, rsi; lpCriticalSection
0x180011391  call    cs:__imp_LeaveCriticalSection
0x180011397  mov     rsi, [rsp+28h+arg_10]
0x18001139c  mov     eax, ebx
0x18001139e  mov     rbx, [rsp+28h+arg_8]
0x1800113a3  add     rsp, 20h
0x1800113a7  pop     rdi
0x1800113a8  retn
```
