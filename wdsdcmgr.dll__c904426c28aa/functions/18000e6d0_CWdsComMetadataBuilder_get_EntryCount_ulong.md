# CWdsComMetadataBuilder::get_EntryCount(ulong *)

- ea: `0x18000e6d0`
- end: `0x18000e743`
- name: `?get_EntryCount@CWdsComMetadataBuilder@@UEAAJPEAK@Z`
- size: `115`
- prototype: `__int64 __fastcall(CWdsComMetadataBuilder *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e6d0`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e6f6`
- `KERNEL32!EnterCriticalSection` at `0x18000e6f6`
- `KERNEL32!LeaveCriticalSection` at `0x18000e726`
- `KERNEL32!LeaveCriticalSection` at `0x18000e726`

## string_xrefs

- `0x18000e706`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::get_EntryCount(CWdsComMetadataBuilder *this, unsigned int *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  unsigned int v5; // ebx
  const char *v6; // rdx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( a2
    || (v5 = -2147024809,
        (int)ElValidateHr(-2147024809, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x129u) >= 0) )
  {
    *a2 = *((_DWORD *)this + 31);
  }
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x18000e6d0  mov     [rsp+arg_0], rbx
0x18000e6d5  mov     [rsp+arg_8], rbp
0x18000e6da  mov     [rsp+arg_10], rsi
0x18000e6df  push    rdi
0x18000e6e0  sub     rsp, 20h
0x18000e6e4  lea     rdi, [rcx+88h]
0x18000e6eb  mov     rbp, rcx
0x18000e6ee  mov     rcx, rdi; lpCriticalSection
0x18000e6f1  mov     rsi, rdx
0x18000e6f4  xor     ebx, ebx
0x18000e6f6  call    cs:__imp_EnterCriticalSection
0x18000e6fc  test    rsi, rsi
0x18000e6ff  jnz     short loc_18000E71E
0x18000e701  mov     ebx, 80070057h
0x18000e706  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e70d  mov     ecx, ebx; int
0x18000e70f  mov     r9d, 129h; unsigned int
0x18000e715  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000e71a  test    eax, eax
0x18000e71c  js      short loc_18000E723
0x18000e71e  mov     edx, [rbp+7Ch]
0x18000e721  mov     [rsi], edx
0x18000e723  mov     rcx, rdi; lpCriticalSection
0x18000e726  call    cs:__imp_LeaveCriticalSection
0x18000e72c  mov     rbp, [rsp+28h+arg_8]
0x18000e731  mov     eax, ebx
0x18000e733  mov     rbx, [rsp+28h+arg_0]
0x18000e738  mov     rsi, [rsp+28h+arg_10]
0x18000e73d  add     rsp, 20h
0x18000e741  pop     rdi
0x18000e742  retn
```
