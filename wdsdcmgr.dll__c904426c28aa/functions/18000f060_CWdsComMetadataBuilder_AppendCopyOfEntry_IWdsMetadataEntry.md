# CWdsComMetadataBuilder::AppendCopyOfEntry(IWdsMetadataEntry *)

- ea: `0x18000f060`
- end: `0x18000f14c`
- name: `?AppendCopyOfEntry@CWdsComMetadataBuilder@@UEAAJPEAUIWdsMetadataEntry@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(CWdsComMetadataBuilder *__hidden this, struct IWdsMetadataEntry *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ba74`
- `0x18000f060`
- `0x180014d58`
- `0x180014ee0`
- `0x180015cc0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f089`
- `KERNEL32!EnterCriticalSection` at `0x18000f089`
- `KERNEL32!LeaveCriticalSection` at `0x18000f12f`
- `KERNEL32!LeaveCriticalSection` at `0x18000f12f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f120`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f120`

## string_xrefs

- `0x18000f099`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f0cc`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f0f4`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::AppendCopyOfEntry(
        CWdsComMetadataBuilder *this,
        struct IWdsMetadataEntry *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  const char *v5; // rdx
  unsigned int v6; // ebx
  const char *v7; // rdx
  signed int appended; // edi
  const char *v9; // rdx
  BSTR bstrString; // [rsp+30h] [rbp+8h] BYREF

  bstrString = 0;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( a2
    || (v6 = -2147024809,
        (int)ElValidateHr(-2147024809, v5, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x303u) >= 0) )
  {
    v6 = (*(__int64 (__fastcall **)(struct IWdsMetadataEntry *, BSTR *))(*(_QWORD *)a2 + 120LL))(a2, &bstrString);
    if ( (int)ElValidateHr(v6, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x307u) >= 0 )
    {
      appended = CWdsMetadata::AppendEntry((CWdsComMetadataBuilder *)((char *)this + 64), bstrString);
      if ( ElValidateWin32(appended, v9, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x30Au) )
      {
        v6 = (unsigned __int16)appended | 0x80070000;
        if ( appended <= 0 )
          v6 = appended;
      }
    }
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
0x18000f060  mov     rax, rsp
0x18000f063  mov     [rax+10h], rbx
0x18000f067  mov     [rax+18h], rbp
0x18000f06b  mov     [rax+20h], rsi
0x18000f06f  push    rdi
0x18000f070  sub     rsp, 20h
0x18000f074  and     qword ptr [rax+8], 0
0x18000f079  lea     rsi, [rcx+88h]
0x18000f080  mov     rbp, rcx
0x18000f083  mov     rdi, rdx
0x18000f086  mov     rcx, rsi; lpCriticalSection
0x18000f089  call    cs:__imp_EnterCriticalSection
0x18000f08f  test    rdi, rdi
0x18000f092  jnz     short loc_18000F0B1
0x18000f094  mov     ebx, 80070057h
0x18000f099  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f0a0  mov     ecx, ebx; int
0x18000f0a2  mov     r9d, 303h; unsigned int
0x18000f0a8  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f0ad  test    eax, eax
0x18000f0af  js      short loc_18000F116
0x18000f0b1  mov     rax, [rdi]
0x18000f0b4  lea     rdx, [rsp+28h+bstrString]
0x18000f0b9  mov     rcx, rdi
0x18000f0bc  mov     rax, [rax+78h]
0x18000f0c0  call    cs:__guard_dispatch_icall_fptr
0x18000f0c6  mov     r9d, 307h; unsigned int
0x18000f0cc  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f0d3  mov     ecx, eax; int
0x18000f0d5  mov     ebx, eax
0x18000f0d7  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f0dc  test    eax, eax
0x18000f0de  js      short loc_18000F116
0x18000f0e0  mov     rdx, [rsp+28h+bstrString]; unsigned __int16 *
0x18000f0e5  lea     rcx, [rbp+40h]; this
0x18000f0e9  call    ?AppendEntry@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::AppendEntry(ushort const *)
0x18000f0ee  mov     r9d, 30Ah; unsigned int
0x18000f0f4  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f0fb  mov     ecx, eax; unsigned int
0x18000f0fd  mov     edi, eax
0x18000f0ff  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000f104  test    eax, eax
0x18000f106  jz      short loc_18000F116
0x18000f108  movzx   ebx, di
0x18000f10b  or      ebx, 80070000h
0x18000f111  test    edi, edi
0x18000f113  cmovle  ebx, edi
0x18000f116  mov     rcx, [rsp+28h+bstrString]; bstrString
0x18000f11b  test    rcx, rcx
0x18000f11e  jz      short loc_18000F12C
0x18000f120  call    cs:__imp_SysFreeString
0x18000f126  and     [rsp+28h+bstrString], 0
0x18000f12c  mov     rcx, rsi; lpCriticalSection
0x18000f12f  call    cs:__imp_LeaveCriticalSection
0x18000f135  mov     rbp, [rsp+28h+arg_10]
0x18000f13a  mov     eax, ebx
0x18000f13c  mov     rbx, [rsp+28h+arg_8]
0x18000f141  mov     rsi, [rsp+28h+arg_18]
0x18000f146  add     rsp, 20h
0x18000f14a  pop     rdi
0x18000f14b  retn
```
