# CWdsComMetadataBuilder::RemoveEntryByIndex(ulong)

- ea: `0x18000f160`
- end: `0x18000f200`
- name: `?RemoveEntryByIndex@CWdsComMetadataBuilder@@UEAAJK@Z`
- size: `160`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ac50`
- `0x18000f160`
- `0x180014d58`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f185`
- `KERNEL32!EnterCriticalSection` at `0x18000f185`
- `KERNEL32!LeaveCriticalSection` at `0x18000f1e3`
- `KERNEL32!LeaveCriticalSection` at `0x18000f1e3`

## string_xrefs

- `0x18000f195`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f1be`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::RemoveEntryByIndex(CWdsComMetadataBuilder *this, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  unsigned int v5; // ebx
  const char *v6; // rdx
  signed int v7; // edi
  const char *v8; // rdx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( a2 < *((_DWORD *)this + 31)
    || (v5 = -2147024809,
        (int)ElValidateHr(-2147024809, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x32Eu) >= 0) )
  {
    v7 = CWdsMetadata::RemoveEntry((CWdsComMetadataBuilder *)((char *)this + 64), a2);
    if ( ElValidateWin32(v7, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x332u) )
    {
      v5 = (unsigned __int16)v7 | 0x80070000;
      if ( v7 <= 0 )
        v5 = v7;
    }
  }
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x18000f160  mov     [rsp+arg_0], rbx
0x18000f165  mov     [rsp+arg_8], rbp
0x18000f16a  mov     [rsp+arg_10], rsi
0x18000f16f  push    rdi
0x18000f170  sub     rsp, 20h
0x18000f174  lea     rsi, [rcx+88h]
0x18000f17b  mov     rdi, rcx
0x18000f17e  mov     rcx, rsi; lpCriticalSection
0x18000f181  mov     ebp, edx
0x18000f183  xor     ebx, ebx
0x18000f185  call    cs:__imp_EnterCriticalSection
0x18000f18b  cmp     ebp, [rdi+7Ch]
0x18000f18e  jb      short loc_18000F1AD
0x18000f190  mov     ebx, 80070057h
0x18000f195  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f19c  mov     ecx, ebx; int
0x18000f19e  mov     r9d, 32Eh; unsigned int
0x18000f1a4  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f1a9  test    eax, eax
0x18000f1ab  js      short loc_18000F1E0
0x18000f1ad  lea     rcx, [rdi+40h]; this
0x18000f1b1  mov     edx, ebp; unsigned int
0x18000f1b3  call    ?RemoveEntry@CWdsMetadata@@QEAAKK@Z; CWdsMetadata::RemoveEntry(ulong)
0x18000f1b8  mov     r9d, 332h; unsigned int
0x18000f1be  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f1c5  mov     ecx, eax; unsigned int
0x18000f1c7  mov     edi, eax
0x18000f1c9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000f1ce  test    eax, eax
0x18000f1d0  jz      short loc_18000F1E0
0x18000f1d2  movzx   ebx, di
0x18000f1d5  or      ebx, 80070000h
0x18000f1db  test    edi, edi
0x18000f1dd  cmovle  ebx, edi
0x18000f1e0  mov     rcx, rsi; lpCriticalSection
0x18000f1e3  call    cs:__imp_LeaveCriticalSection
0x18000f1e9  mov     rbp, [rsp+28h+arg_8]
0x18000f1ee  mov     eax, ebx
0x18000f1f0  mov     rbx, [rsp+28h+arg_0]
0x18000f1f5  mov     rsi, [rsp+28h+arg_10]
0x18000f1fa  add     rsp, 20h
0x18000f1fe  pop     rdi
0x18000f1ff  retn
```
