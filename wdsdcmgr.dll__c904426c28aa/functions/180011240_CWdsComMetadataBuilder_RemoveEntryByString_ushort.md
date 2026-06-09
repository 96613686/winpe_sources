# CWdsComMetadataBuilder::RemoveEntryByString(ushort *)

- ea: `0x180011240`
- end: `0x1800112e9`
- name: `?RemoveEntryByString@CWdsComMetadataBuilder@@UEAAJPEAG@Z`
- size: `169`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000c4e0`
- `0x18000e3e4`
- `0x180011240`
- `0x180014d58`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180011266`
- `KERNEL32!EnterCriticalSection` at `0x180011266`
- `KERNEL32!LeaveCriticalSection` at `0x1800112cc`
- `KERNEL32!LeaveCriticalSection` at `0x1800112cc`

## string_xrefs

- `0x18001127d`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x1800112a7`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::RemoveEntryByString(CWdsComMetadataBuilder *this, unsigned __int16 *a2)
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
        (int)ElValidateHr(-2147024809, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x93Du) >= 0) )
  {
    v7 = CWdsMetadata::RemoveEntryByString((CWdsComMetadataBuilder *)((char *)this + 64), a2);
    if ( ElValidateWin32(v7, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x941u) )
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
0x180011240  mov     [rsp+arg_0], rbx
0x180011245  mov     [rsp+arg_8], rbp
0x18001124a  mov     [rsp+arg_10], rsi
0x18001124f  push    rdi
0x180011250  sub     rsp, 20h
0x180011254  lea     rsi, [rcx+88h]
0x18001125b  mov     rbp, rcx
0x18001125e  mov     rcx, rsi; lpCriticalSection
0x180011261  mov     rdi, rdx
0x180011264  xor     ebx, ebx
0x180011266  call    cs:__imp_EnterCriticalSection
0x18001126c  mov     rcx, rdi; pbstr
0x18001126f  call    ValidateNonEmptyBstr
0x180011274  test    eax, eax
0x180011276  jnz     short loc_180011295
0x180011278  mov     ebx, 80070057h
0x18001127d  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011284  mov     ecx, ebx; int
0x180011286  mov     r9d, 93Dh; unsigned int
0x18001128c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011291  test    eax, eax
0x180011293  js      short loc_1800112C9
0x180011295  lea     rcx, [rbp+40h]; this
0x180011299  mov     rdx, rdi; unsigned __int16 *
0x18001129c  call    ?RemoveEntryByString@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::RemoveEntryByString(ushort const *)
0x1800112a1  mov     r9d, 941h; unsigned int
0x1800112a7  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800112ae  mov     ecx, eax; unsigned int
0x1800112b0  mov     edi, eax
0x1800112b2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800112b7  test    eax, eax
0x1800112b9  jz      short loc_1800112C9
0x1800112bb  movzx   ebx, di
0x1800112be  or      ebx, 80070000h
0x1800112c4  test    edi, edi
0x1800112c6  cmovle  ebx, edi
0x1800112c9  mov     rcx, rsi; lpCriticalSection
0x1800112cc  call    cs:__imp_LeaveCriticalSection
0x1800112d2  mov     rbp, [rsp+28h+arg_8]
0x1800112d7  mov     eax, ebx
0x1800112d9  mov     rbx, [rsp+28h+arg_0]
0x1800112de  mov     rsi, [rsp+28h+arg_10]
0x1800112e3  add     rsp, 20h
0x1800112e7  pop     rdi
0x1800112e8  retn
```
