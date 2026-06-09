# CWdsComMetadataBuilder::Merge(IWdsMetadata *)

- ea: `0x180011150`
- end: `0x180011235`
- name: `?Merge@CWdsComMetadataBuilder@@UEAAJPEAUIWdsMetadata@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(CWdsComMetadataBuilder *__hidden this, struct IWdsMetadata *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000b47c`
- `0x180011150`
- `0x180014d58`
- `0x180014ee0`
- `0x180015c6d`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180011176`
- `KERNEL32!EnterCriticalSection` at `0x180011176`
- `KERNEL32!LeaveCriticalSection` at `0x180011218`
- `KERNEL32!LeaveCriticalSection` at `0x180011218`

## string_xrefs

- `0x180011186`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x1800111c8`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x1800111f3`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::Merge(CWdsComMetadataBuilder *this, struct IWdsMetadata *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  unsigned int v5; // ebx
  const char *v6; // rdx
  const char *v7; // rdx
  __int64 v8; // rdi
  signed int v9; // edi
  const char *v10; // rdx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( a2
    || (v5 = -2147024809,
        (int)ElValidateHr(-2147024809, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x90Au) >= 0) )
  {
    v8 = _RTDynamicCast_0(
           a2,
           0,
           &IWdsMetadata `RTTI Type Descriptor',
           &CWdsComMetadataBuilder `RTTI Type Descriptor',
           0);
    if ( v8
      || (v5 = -2147024809,
          (int)ElValidateHr(-2147024809, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x911u) >= 0) )
    {
      v9 = CWdsMetadata::Merge((CWdsComMetadataBuilder *)((char *)this + 64), (const struct CWdsMetadata *)(v8 + 64));
      if ( ElValidateWin32(v9, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x915u) )
      {
        v5 = (unsigned __int16)v9 | 0x80070000;
        if ( v9 <= 0 )
          v5 = v9;
      }
    }
  }
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x180011150  mov     [rsp+arg_0], rbx
0x180011155  mov     [rsp+arg_8], rbp
0x18001115a  mov     [rsp+arg_10], rsi
0x18001115f  push    rdi
0x180011160  sub     rsp, 30h
0x180011164  lea     rsi, [rcx+88h]
0x18001116b  mov     rbp, rcx
0x18001116e  mov     rcx, rsi; lpCriticalSection
0x180011171  mov     rdi, rdx
0x180011174  xor     ebx, ebx
0x180011176  call    cs:__imp_EnterCriticalSection
0x18001117c  test    rdi, rdi
0x18001117f  jnz     short loc_18001119E
0x180011181  mov     ebx, 80070057h
0x180011186  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001118d  mov     ecx, ebx; int
0x18001118f  mov     r9d, 90Ah; unsigned int
0x180011195  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18001119a  test    eax, eax
0x18001119c  js      short loc_180011215
0x18001119e  and     [rsp+38h+var_18], 0
0x1800111a3  lea     r9, ??_R0?AVCWdsComMetadataBuilder@@@8; CWdsComMetadataBuilder `RTTI Type Descriptor'
0x1800111aa  lea     r8, ??_R0?AUIWdsMetadata@@@8; IWdsMetadata `RTTI Type Descriptor'
0x1800111b1  xor     edx, edx
0x1800111b3  mov     rcx, rdi
0x1800111b6  call    __RTDynamicCast_0
0x1800111bb  mov     rdi, rax
0x1800111be  test    rax, rax
0x1800111c1  jnz     short loc_1800111E0
0x1800111c3  mov     ebx, 80070057h
0x1800111c8  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800111cf  mov     ecx, ebx; int
0x1800111d1  mov     r9d, 911h; unsigned int
0x1800111d7  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800111dc  test    eax, eax
0x1800111de  js      short loc_180011215
0x1800111e0  lea     rdx, [rdi+40h]; struct CWdsMetadata *
0x1800111e4  lea     rcx, [rbp+40h]; this
0x1800111e8  call    ?Merge@CWdsMetadata@@QEAAKPEBV1@@Z; CWdsMetadata::Merge(CWdsMetadata const *)
0x1800111ed  mov     r9d, 915h; unsigned int
0x1800111f3  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800111fa  mov     ecx, eax; unsigned int
0x1800111fc  mov     edi, eax
0x1800111fe  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011203  test    eax, eax
0x180011205  jz      short loc_180011215
0x180011207  movzx   ebx, di
0x18001120a  or      ebx, 80070000h
0x180011210  test    edi, edi
0x180011212  cmovle  ebx, edi
0x180011215  mov     rcx, rsi; lpCriticalSection
0x180011218  call    cs:__imp_LeaveCriticalSection
0x18001121e  mov     rbp, [rsp+38h+arg_8]
0x180011223  mov     eax, ebx
0x180011225  mov     rbx, [rsp+38h+arg_0]
0x18001122a  mov     rsi, [rsp+38h+arg_10]
0x18001122f  add     rsp, 30h
0x180011233  pop     rdi
0x180011234  retn
```
