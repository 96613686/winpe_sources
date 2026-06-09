# CWdsComMetadataBuilder::AppendGuidEntry(ushort *,ushort *)

- ea: `0x18000f710`
- end: `0x18000f816`
- name: `?AppendGuidEntry@CWdsComMetadataBuilder@@UEAAJPEAG0@Z`
- size: `262`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000c158`
- `0x18000e3e4`
- `0x18000f710`
- `0x180014010`
- `0x180014d58`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f73e`
- `KERNEL32!EnterCriticalSection` at `0x18000f73e`
- `KERNEL32!LeaveCriticalSection` at `0x18000f7f3`
- `KERNEL32!LeaveCriticalSection` at `0x18000f7f3`

## string_xrefs

- `0x18000f76d`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f798`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f7ce`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::AppendGuidEntry(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx
  const char *v8; // rdx
  signed int appended; // edi
  const char *v10; // rdx
  const char *v11; // rdx
  struct _GUID v13; // [rsp+20h] [rbp-18h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  *(_QWORD *)&v13.Data1 = 0;
  *(_QWORD *)v13.Data4 = 0;
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && (unsigned int)ValidateNonEmptyBstr(a3)
    || (v7 = -2147024809,
        (int)ElValidateHr(-2147024809, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x465u) >= 0) )
  {
    appended = ParseGuid(a3, &v13);
    if ( ElValidateWin32(appended, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x469u)
      || (appended = CWdsMetadata::AppendGuidEntry((CWdsComMetadataBuilder *)((char *)this + 64), a2, &v13),
          ElValidateWin32(appended, v11, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x46Cu)) )
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
0x18000f710  mov     rax, rsp
0x18000f713  mov     [rax+8], rbx
0x18000f717  mov     [rax+10h], rbp
0x18000f71b  mov     [rax+18h], rsi
0x18000f71f  mov     [rax+20h], rdi
0x18000f723  push    r14
0x18000f725  sub     rsp, 30h
0x18000f729  lea     rsi, [rcx+88h]
0x18000f730  mov     r14, rcx
0x18000f733  mov     rcx, rsi; lpCriticalSection
0x18000f736  mov     rdi, r8
0x18000f739  mov     rbp, rdx
0x18000f73c  xor     ebx, ebx
0x18000f73e  call    cs:__imp_EnterCriticalSection
0x18000f744  xor     eax, eax
0x18000f746  mov     rcx, rbp; pbstr
0x18000f749  mov     qword ptr [rsp+38h+var_18.Data1], rax
0x18000f74e  mov     qword ptr [rsp+38h+var_18.Data4], rax
0x18000f753  call    ValidateNonEmptyBstr
0x18000f758  test    eax, eax
0x18000f75a  jz      short loc_18000F768
0x18000f75c  mov     rcx, rdi; pbstr
0x18000f75f  call    ValidateNonEmptyBstr
0x18000f764  test    eax, eax
0x18000f766  jnz     short loc_18000F785
0x18000f768  mov     ebx, 80070057h
0x18000f76d  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f774  mov     ecx, ebx; int
0x18000f776  mov     r9d, 465h; unsigned int
0x18000f77c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f781  test    eax, eax
0x18000f783  js      short loc_18000F7F0
0x18000f785  lea     rdx, [rsp+38h+var_18]; struct _GUID *
0x18000f78a  mov     rcx, rdi; String
0x18000f78d  call    ?ParseGuid@@YAKPEBGPEAU_GUID@@@Z; ParseGuid(ushort const *,_GUID *)
0x18000f792  mov     r9d, 469h; unsigned int
0x18000f798  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f79f  mov     ecx, eax; unsigned int
0x18000f7a1  mov     edi, eax
0x18000f7a3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000f7a8  test    eax, eax
0x18000f7aa  jnz     short loc_18000F7E2
0x18000f7ac  movaps  xmm0, xmmword ptr [rsp+38h+var_18.Data1]
0x18000f7b1  lea     rcx, [r14+40h]; this
0x18000f7b5  lea     r8, [rsp+38h+var_18]; struct _GUID
0x18000f7ba  movdqa  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x18000f7c0  mov     rdx, rbp; unsigned __int16 *
0x18000f7c3  call    ?AppendGuidEntry@CWdsMetadata@@QEAAKPEBGU_GUID@@@Z; CWdsMetadata::AppendGuidEntry(ushort const *,_GUID)
0x18000f7c8  mov     r9d, 46Ch; unsigned int
0x18000f7ce  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f7d5  mov     ecx, eax; unsigned int
0x18000f7d7  mov     edi, eax
0x18000f7d9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000f7de  test    eax, eax
0x18000f7e0  jz      short loc_18000F7F0
0x18000f7e2  movzx   ebx, di
0x18000f7e5  or      ebx, 80070000h
0x18000f7eb  test    edi, edi
0x18000f7ed  cmovle  ebx, edi
0x18000f7f0  mov     rcx, rsi; lpCriticalSection
0x18000f7f3  call    cs:__imp_LeaveCriticalSection
0x18000f7f9  mov     rbp, [rsp+38h+arg_8]
0x18000f7fe  mov     eax, ebx
0x18000f800  mov     rbx, [rsp+38h+arg_0]
0x18000f805  mov     rsi, [rsp+38h+arg_10]
0x18000f80a  mov     rdi, [rsp+38h+arg_18]
0x18000f80f  add     rsp, 30h
0x18000f813  pop     r14
0x18000f815  retn
```
