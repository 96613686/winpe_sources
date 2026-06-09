# CWdsComMetadataBuilder::RemoveAllEntries(void)

- ea: `0x1800113b0`
- end: `0x180011420`
- name: `?RemoveAllEntries@CWdsComMetadataBuilder@@UEAAJXZ`
- size: `112`
- prototype: `__int64 __fastcall(CWdsComMetadataBuilder *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000ad40`
- `0x1800113b0`
- `0x180014d58`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800113ce`
- `KERNEL32!EnterCriticalSection` at `0x1800113ce`
- `KERNEL32!LeaveCriticalSection` at `0x180011408`
- `KERNEL32!LeaveCriticalSection` at `0x180011408`

## string_xrefs

- `0x1800113e3`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::RemoveAllEntries(CWdsComMetadataBuilder *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  unsigned int v3; // edi
  signed int v4; // ebx
  const char *v5; // rdx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v4 = CWdsMetadata::Clear((CWdsComMetadataBuilder *)((char *)this + 64));
  if ( ElValidateWin32(v4, v5, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x989u) )
  {
    v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 <= 0 )
      v3 = v4;
  }
  LeaveCriticalSection(v1);
  return v3;
}

```

## disassembly

```asm
0x1800113b0  mov     [rsp+arg_0], rbx
0x1800113b5  mov     [rsp+arg_8], rsi
0x1800113ba  push    rdi
0x1800113bb  sub     rsp, 20h
0x1800113bf  lea     rsi, [rcx+88h]
0x1800113c6  mov     rbx, rcx
0x1800113c9  mov     rcx, rsi; lpCriticalSection
0x1800113cc  xor     edi, edi
0x1800113ce  call    cs:__imp_EnterCriticalSection
0x1800113d4  lea     rcx, [rbx+40h]; this
0x1800113d8  call    ?Clear@CWdsMetadata@@QEAAKXZ; CWdsMetadata::Clear(void)
0x1800113dd  mov     r9d, 989h; unsigned int
0x1800113e3  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800113ea  mov     ecx, eax; unsigned int
0x1800113ec  mov     ebx, eax
0x1800113ee  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800113f3  test    eax, eax
0x1800113f5  jz      short loc_180011405
0x1800113f7  movzx   edi, bx
0x1800113fa  or      edi, 80070000h
0x180011400  test    ebx, ebx
0x180011402  cmovle  edi, ebx
0x180011405  mov     rcx, rsi; lpCriticalSection
0x180011408  call    cs:__imp_LeaveCriticalSection
0x18001140e  mov     rbx, [rsp+28h+arg_0]
0x180011413  mov     eax, edi
0x180011415  mov     rsi, [rsp+28h+arg_8]
0x18001141a  add     rsp, 20h
0x18001141e  pop     rdi
0x18001141f  retn
```
