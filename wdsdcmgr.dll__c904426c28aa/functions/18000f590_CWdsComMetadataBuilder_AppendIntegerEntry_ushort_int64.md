# CWdsComMetadataBuilder::AppendIntegerEntry(ushort *,__int64)

- ea: `0x18000f590`
- end: `0x18000f64a`
- name: `?AppendIntegerEntry@CWdsComMetadataBuilder@@UEAAJPEAG_J@Z`
- size: `186`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000bf44`
- `0x18000e3e4`
- `0x18000f590`
- `0x180014d58`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f5be`
- `KERNEL32!EnterCriticalSection` at `0x18000f5be`
- `KERNEL32!LeaveCriticalSection` at `0x18000f627`
- `KERNEL32!LeaveCriticalSection` at `0x18000f627`

## string_xrefs

- `0x18000f5d5`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f602`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::AppendIntegerEntry(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        union _LARGE_INTEGER a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx
  const char *v8; // rdx
  signed int appended; // edi
  const char *v10; // rdx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( (unsigned int)ValidateNonEmptyBstr(a2)
    || (v7 = -2147024809,
        (int)ElValidateHr(-2147024809, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x408u) >= 0) )
  {
    appended = CWdsMetadata::AppendIntegerEntry((CWdsComMetadataBuilder *)((char *)this + 64), a2, a3);
    if ( ElValidateWin32(appended, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x40Eu) )
    {
      v7 = (unsigned __int16)appended | 0x80070000;
      if ( appended <= 0 )
        v7 = appended;
    }
  }
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x18000f590  mov     rax, rsp
0x18000f593  mov     [rax+8], rbx
0x18000f597  mov     [rax+10h], rbp
0x18000f59b  mov     [rax+18h], rsi
0x18000f59f  mov     [rax+20h], rdi
0x18000f5a3  push    r14
0x18000f5a5  sub     rsp, 20h
0x18000f5a9  lea     rsi, [rcx+88h]
0x18000f5b0  mov     rbp, rcx
0x18000f5b3  mov     rcx, rsi; lpCriticalSection
0x18000f5b6  mov     r14, r8
0x18000f5b9  mov     rdi, rdx
0x18000f5bc  xor     ebx, ebx
0x18000f5be  call    cs:__imp_EnterCriticalSection
0x18000f5c4  mov     rcx, rdi; pbstr
0x18000f5c7  call    ValidateNonEmptyBstr
0x18000f5cc  test    eax, eax
0x18000f5ce  jnz     short loc_18000F5ED
0x18000f5d0  mov     ebx, 80070057h
0x18000f5d5  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f5dc  mov     ecx, ebx; int
0x18000f5de  mov     r9d, 408h; unsigned int
0x18000f5e4  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f5e9  test    eax, eax
0x18000f5eb  js      short loc_18000F624
0x18000f5ed  lea     rcx, [rbp+40h]; this
0x18000f5f1  mov     r8, r14; union _LARGE_INTEGER
0x18000f5f4  mov     rdx, rdi; unsigned __int16 *
0x18000f5f7  call    ?AppendIntegerEntry@CWdsMetadata@@QEAAKPEBGT_LARGE_INTEGER@@@Z; CWdsMetadata::AppendIntegerEntry(ushort const *,_LARGE_INTEGER)
0x18000f5fc  mov     r9d, 40Eh; unsigned int
0x18000f602  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f609  mov     ecx, eax; unsigned int
0x18000f60b  mov     edi, eax
0x18000f60d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000f612  test    eax, eax
0x18000f614  jz      short loc_18000F624
0x18000f616  movzx   ebx, di
0x18000f619  or      ebx, 80070000h
0x18000f61f  test    edi, edi
0x18000f621  cmovle  ebx, edi
0x18000f624  mov     rcx, rsi; lpCriticalSection
0x18000f627  call    cs:__imp_LeaveCriticalSection
0x18000f62d  mov     rbp, [rsp+28h+arg_8]
0x18000f632  mov     eax, ebx
0x18000f634  mov     rbx, [rsp+28h+arg_0]
0x18000f639  mov     rsi, [rsp+28h+arg_10]
0x18000f63e  mov     rdi, [rsp+28h+arg_18]
0x18000f643  add     rsp, 20h
0x18000f647  pop     r14
0x18000f649  retn
```
