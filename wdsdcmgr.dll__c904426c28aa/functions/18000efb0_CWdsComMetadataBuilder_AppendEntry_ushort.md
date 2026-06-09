# CWdsComMetadataBuilder::AppendEntry(ushort *)

- ea: `0x18000efb0`
- end: `0x18000f059`
- name: `?AppendEntry@CWdsComMetadataBuilder@@UEAAJPEAG@Z`
- size: `169`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ba74`
- `0x18000e3e4`
- `0x18000efb0`
- `0x180014d58`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000efd6`
- `KERNEL32!EnterCriticalSection` at `0x18000efd6`
- `KERNEL32!LeaveCriticalSection` at `0x18000f03c`
- `KERNEL32!LeaveCriticalSection` at `0x18000f03c`

## string_xrefs

- `0x18000efed`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f017`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::AppendEntry(CWdsComMetadataBuilder *this, unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  unsigned int v5; // ebx
  const char *v6; // rdx
  signed int appended; // edi
  const char *v8; // rdx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( (unsigned int)ValidateNonEmptyBstr(a2)
    || (v5 = -2147024809,
        (int)ElValidateHr(-2147024809, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x2D8u) >= 0) )
  {
    appended = CWdsMetadata::AppendEntry((CWdsComMetadataBuilder *)((char *)this + 64), a2);
    if ( ElValidateWin32(appended, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x2DCu) )
    {
      v5 = (unsigned __int16)appended | 0x80070000;
      if ( appended <= 0 )
        v5 = appended;
    }
  }
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x18000efb0  mov     [rsp+arg_0], rbx
0x18000efb5  mov     [rsp+arg_8], rbp
0x18000efba  mov     [rsp+arg_10], rsi
0x18000efbf  push    rdi
0x18000efc0  sub     rsp, 20h
0x18000efc4  lea     rsi, [rcx+88h]
0x18000efcb  mov     rbp, rcx
0x18000efce  mov     rcx, rsi; lpCriticalSection
0x18000efd1  mov     rdi, rdx
0x18000efd4  xor     ebx, ebx
0x18000efd6  call    cs:__imp_EnterCriticalSection
0x18000efdc  mov     rcx, rdi; pbstr
0x18000efdf  call    ValidateNonEmptyBstr
0x18000efe4  test    eax, eax
0x18000efe6  jnz     short loc_18000F005
0x18000efe8  mov     ebx, 80070057h
0x18000efed  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000eff4  mov     ecx, ebx; int
0x18000eff6  mov     r9d, 2D8h; unsigned int
0x18000effc  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f001  test    eax, eax
0x18000f003  js      short loc_18000F039
0x18000f005  lea     rcx, [rbp+40h]; this
0x18000f009  mov     rdx, rdi; unsigned __int16 *
0x18000f00c  call    ?AppendEntry@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::AppendEntry(ushort const *)
0x18000f011  mov     r9d, 2DCh; unsigned int
0x18000f017  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f01e  mov     ecx, eax; unsigned int
0x18000f020  mov     edi, eax
0x18000f022  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000f027  test    eax, eax
0x18000f029  jz      short loc_18000F039
0x18000f02b  movzx   ebx, di
0x18000f02e  or      ebx, 80070000h
0x18000f034  test    edi, edi
0x18000f036  cmovle  ebx, edi
0x18000f039  mov     rcx, rsi; lpCriticalSection
0x18000f03c  call    cs:__imp_LeaveCriticalSection
0x18000f042  mov     rbp, [rsp+28h+arg_8]
0x18000f047  mov     eax, ebx
0x18000f049  mov     rbx, [rsp+28h+arg_0]
0x18000f04e  mov     rsi, [rsp+28h+arg_10]
0x18000f053  add     rsp, 20h
0x18000f057  pop     rdi
0x18000f058  retn
```
