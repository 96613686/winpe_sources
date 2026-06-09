# CWdsComMetadataBuilder::RemoveEntriesByTag(ushort *)

- ea: `0x18000f210`
- end: `0x18000f2b9`
- name: `?RemoveEntriesByTag@CWdsComMetadataBuilder@@UEAAJPEAG@Z`
- size: `169`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000c8c4`
- `0x18000e3e4`
- `0x18000f210`
- `0x180014d58`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f236`
- `KERNEL32!EnterCriticalSection` at `0x18000f236`
- `KERNEL32!LeaveCriticalSection` at `0x18000f29c`
- `KERNEL32!LeaveCriticalSection` at `0x18000f29c`

## string_xrefs

- `0x18000f24d`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f277`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::RemoveEntriesByTag(CWdsComMetadataBuilder *this, unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  unsigned int v5; // ebx
  const char *v6; // rdx
  signed int v7; // edi
  const char *v8; // rdx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( (unsigned int)ValidateNonEmptyBstr(a2)
    || (v5 = -2147024809,
        (int)ElValidateHr(-2147024809, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x354u) >= 0) )
  {
    v7 = CWdsMetadata::RemoveInstancesOfTag((CWdsComMetadataBuilder *)((char *)this + 64), a2);
    if ( ElValidateWin32(v7, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x358u) )
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
0x18000f210  mov     [rsp+arg_0], rbx
0x18000f215  mov     [rsp+arg_8], rbp
0x18000f21a  mov     [rsp+arg_10], rsi
0x18000f21f  push    rdi
0x18000f220  sub     rsp, 20h
0x18000f224  lea     rsi, [rcx+88h]
0x18000f22b  mov     rbp, rcx
0x18000f22e  mov     rcx, rsi; lpCriticalSection
0x18000f231  mov     rdi, rdx
0x18000f234  xor     ebx, ebx
0x18000f236  call    cs:__imp_EnterCriticalSection
0x18000f23c  mov     rcx, rdi; pbstr
0x18000f23f  call    ValidateNonEmptyBstr
0x18000f244  test    eax, eax
0x18000f246  jnz     short loc_18000F265
0x18000f248  mov     ebx, 80070057h
0x18000f24d  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f254  mov     ecx, ebx; int
0x18000f256  mov     r9d, 354h; unsigned int
0x18000f25c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f261  test    eax, eax
0x18000f263  js      short loc_18000F299
0x18000f265  lea     rcx, [rbp+40h]; this
0x18000f269  mov     rdx, rdi; unsigned __int16 *
0x18000f26c  call    ?RemoveInstancesOfTag@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::RemoveInstancesOfTag(ushort const *)
0x18000f271  mov     r9d, 358h; unsigned int
0x18000f277  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f27e  mov     ecx, eax; unsigned int
0x18000f280  mov     edi, eax
0x18000f282  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000f287  test    eax, eax
0x18000f289  jz      short loc_18000F299
0x18000f28b  movzx   ebx, di
0x18000f28e  or      ebx, 80070000h
0x18000f294  test    edi, edi
0x18000f296  cmovle  ebx, edi
0x18000f299  mov     rcx, rsi; lpCriticalSection
0x18000f29c  call    cs:__imp_LeaveCriticalSection
0x18000f2a2  mov     rbp, [rsp+28h+arg_8]
0x18000f2a7  mov     eax, ebx
0x18000f2a9  mov     rbx, [rsp+28h+arg_0]
0x18000f2ae  mov     rsi, [rsp+28h+arg_10]
0x18000f2b3  add     rsp, 20h
0x18000f2b7  pop     rdi
0x18000f2b8  retn
```
