# CWdsComMetadataBuilder::AppendAllEntries(IWdsMetadata *)

- ea: `0x18000f8e0`
- end: `0x18000f9c5`
- name: `?AppendAllEntries@CWdsComMetadataBuilder@@UEAAJPEAUIWdsMetadata@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(CWdsComMetadataBuilder *__hidden this, struct IWdsMetadata *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000b834`
- `0x18000f8e0`
- `0x180014d58`
- `0x180014ee0`
- `0x180015c6d`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f906`
- `KERNEL32!EnterCriticalSection` at `0x18000f906`
- `KERNEL32!LeaveCriticalSection` at `0x18000f9a8`
- `KERNEL32!LeaveCriticalSection` at `0x18000f9a8`

## string_xrefs

- `0x18000f916`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f958`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f983`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::AppendAllEntries(CWdsComMetadataBuilder *this, struct IWdsMetadata *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  unsigned int v5; // ebx
  const char *v6; // rdx
  const char *v7; // rdx
  __int64 v8; // rdi
  signed int appended; // edi
  const char *v10; // rdx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( a2
    || (v5 = -2147024809,
        (int)ElValidateHr(-2147024809, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x4C1u) >= 0) )
  {
    v8 = _RTDynamicCast_0(
           a2,
           0,
           &IWdsMetadata `RTTI Type Descriptor',
           &CWdsComMetadataBuilder `RTTI Type Descriptor',
           0);
    if ( v8
      || (v5 = -2147024809,
          (int)ElValidateHr(-2147024809, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x4C8u) >= 0) )
    {
      appended = CWdsMetadata::AppendAll(
                   (CWdsComMetadataBuilder *)((char *)this + 64),
                   (const struct CWdsMetadata *)(v8 + 64));
      if ( ElValidateWin32(appended, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x4CCu) )
      {
        v5 = (unsigned __int16)appended | 0x80070000;
        if ( appended <= 0 )
          v5 = appended;
      }
    }
  }
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x18000f8e0  mov     [rsp+arg_0], rbx
0x18000f8e5  mov     [rsp+arg_8], rbp
0x18000f8ea  mov     [rsp+arg_10], rsi
0x18000f8ef  push    rdi
0x18000f8f0  sub     rsp, 30h
0x18000f8f4  lea     rsi, [rcx+88h]
0x18000f8fb  mov     rbp, rcx
0x18000f8fe  mov     rcx, rsi; lpCriticalSection
0x18000f901  mov     rdi, rdx
0x18000f904  xor     ebx, ebx
0x18000f906  call    cs:__imp_EnterCriticalSection
0x18000f90c  test    rdi, rdi
0x18000f90f  jnz     short loc_18000F92E
0x18000f911  mov     ebx, 80070057h
0x18000f916  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f91d  mov     ecx, ebx; int
0x18000f91f  mov     r9d, 4C1h; unsigned int
0x18000f925  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f92a  test    eax, eax
0x18000f92c  js      short loc_18000F9A5
0x18000f92e  and     [rsp+38h+var_18], 0
0x18000f933  lea     r9, ??_R0?AVCWdsComMetadataBuilder@@@8; CWdsComMetadataBuilder `RTTI Type Descriptor'
0x18000f93a  lea     r8, ??_R0?AUIWdsMetadata@@@8; IWdsMetadata `RTTI Type Descriptor'
0x18000f941  xor     edx, edx
0x18000f943  mov     rcx, rdi
0x18000f946  call    __RTDynamicCast_0
0x18000f94b  mov     rdi, rax
0x18000f94e  test    rax, rax
0x18000f951  jnz     short loc_18000F970
0x18000f953  mov     ebx, 80070057h
0x18000f958  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f95f  mov     ecx, ebx; int
0x18000f961  mov     r9d, 4C8h; unsigned int
0x18000f967  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f96c  test    eax, eax
0x18000f96e  js      short loc_18000F9A5
0x18000f970  lea     rdx, [rdi+40h]; struct CWdsMetadata *
0x18000f974  lea     rcx, [rbp+40h]; this
0x18000f978  call    ?AppendAll@CWdsMetadata@@QEAAKPEBV1@@Z; CWdsMetadata::AppendAll(CWdsMetadata const *)
0x18000f97d  mov     r9d, 4CCh; unsigned int
0x18000f983  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f98a  mov     ecx, eax; unsigned int
0x18000f98c  mov     edi, eax
0x18000f98e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000f993  test    eax, eax
0x18000f995  jz      short loc_18000F9A5
0x18000f997  movzx   ebx, di
0x18000f99a  or      ebx, 80070000h
0x18000f9a0  test    edi, edi
0x18000f9a2  cmovle  ebx, edi
0x18000f9a5  mov     rcx, rsi; lpCriticalSection
0x18000f9a8  call    cs:__imp_LeaveCriticalSection
0x18000f9ae  mov     rbp, [rsp+38h+arg_8]
0x18000f9b3  mov     eax, ebx
0x18000f9b5  mov     rbx, [rsp+38h+arg_0]
0x18000f9ba  mov     rsi, [rsp+38h+arg_10]
0x18000f9bf  add     rsp, 30h
0x18000f9c3  pop     rdi
0x18000f9c4  retn
```
