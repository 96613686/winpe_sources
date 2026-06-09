# CWdsComMetadataBuilder::AppendEntriesByTag(ushort *,IWdsMetadata *)

- ea: `0x18000f9d0`
- end: `0x18000fad2`
- name: `?AppendEntriesByTag@CWdsComMetadataBuilder@@UEAAJPEAGPEAUIWdsMetadata@@@Z`
- size: `258`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, struct IWdsMetadata *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000b92c`
- `0x18000e3e4`
- `0x18000f9d0`
- `0x180014d58`
- `0x180014ee0`
- `0x180015c6d`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f9fe`
- `KERNEL32!EnterCriticalSection` at `0x18000f9fe`
- `KERNEL32!LeaveCriticalSection` at `0x18000faaf`
- `KERNEL32!LeaveCriticalSection` at `0x18000faaf`

## string_xrefs

- `0x18000fa1a`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000fa5c`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000fa8a`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::AppendEntriesByTag(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        struct IWdsMetadata *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx
  const char *v8; // rdx
  const char *v9; // rdx
  __int64 v10; // rdi
  signed int appended; // edi
  const char *v12; // rdx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( a3 && (unsigned int)ValidateNonEmptyBstr(a2)
    || (v7 = -2147024809,
        (int)ElValidateHr(-2147024809, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x4F5u) >= 0) )
  {
    v10 = _RTDynamicCast_0(
            a3,
            0,
            &IWdsMetadata `RTTI Type Descriptor',
            &CWdsComMetadataBuilder `RTTI Type Descriptor',
            0);
    if ( v10
      || (v7 = -2147024809,
          (int)ElValidateHr(-2147024809, v9, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x4FCu) >= 0) )
    {
      appended = CWdsMetadata::AppendEntriesOfTag(
                   (CWdsComMetadataBuilder *)((char *)this + 64),
                   a2,
                   (const struct CWdsMetadata *)(v10 + 64));
      if ( ElValidateWin32(appended, v12, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x500u) )
      {
        v7 = (unsigned __int16)appended | 0x80070000;
        if ( appended <= 0 )
          v7 = appended;
      }
    }
  }
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x18000f9d0  mov     rax, rsp
0x18000f9d3  mov     [rax+8], rbx
0x18000f9d7  mov     [rax+10h], rbp
0x18000f9db  mov     [rax+18h], rsi
0x18000f9df  mov     [rax+20h], rdi
0x18000f9e3  push    r14
0x18000f9e5  sub     rsp, 30h
0x18000f9e9  lea     rsi, [rcx+88h]
0x18000f9f0  mov     r14, rcx
0x18000f9f3  mov     rcx, rsi; lpCriticalSection
0x18000f9f6  mov     rdi, r8
0x18000f9f9  mov     rbp, rdx
0x18000f9fc  xor     ebx, ebx
0x18000f9fe  call    cs:__imp_EnterCriticalSection
0x18000fa04  test    rdi, rdi
0x18000fa07  jz      short loc_18000FA15
0x18000fa09  mov     rcx, rbp; pbstr
0x18000fa0c  call    ValidateNonEmptyBstr
0x18000fa11  test    eax, eax
0x18000fa13  jnz     short loc_18000FA32
0x18000fa15  mov     ebx, 80070057h
0x18000fa1a  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000fa21  mov     ecx, ebx; int
0x18000fa23  mov     r9d, 4F5h; unsigned int
0x18000fa29  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000fa2e  test    eax, eax
0x18000fa30  js      short loc_18000FAAC
0x18000fa32  and     [rsp+38h+var_18], 0
0x18000fa37  lea     r9, ??_R0?AVCWdsComMetadataBuilder@@@8; CWdsComMetadataBuilder `RTTI Type Descriptor'
0x18000fa3e  lea     r8, ??_R0?AUIWdsMetadata@@@8; IWdsMetadata `RTTI Type Descriptor'
0x18000fa45  xor     edx, edx
0x18000fa47  mov     rcx, rdi
0x18000fa4a  call    __RTDynamicCast_0
0x18000fa4f  mov     rdi, rax
0x18000fa52  test    rax, rax
0x18000fa55  jnz     short loc_18000FA74
0x18000fa57  mov     ebx, 80070057h
0x18000fa5c  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000fa63  mov     ecx, ebx; int
0x18000fa65  mov     r9d, 4FCh; unsigned int
0x18000fa6b  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000fa70  test    eax, eax
0x18000fa72  js      short loc_18000FAAC
0x18000fa74  lea     r8, [rdi+40h]; struct CWdsMetadata *
0x18000fa78  mov     rdx, rbp; unsigned __int16 *
0x18000fa7b  lea     rcx, [r14+40h]; this
0x18000fa7f  call    ?AppendEntriesOfTag@CWdsMetadata@@QEAAKPEBGPEBV1@@Z; CWdsMetadata::AppendEntriesOfTag(ushort const *,CWdsMetadata const *)
0x18000fa84  mov     r9d, 500h; unsigned int
0x18000fa8a  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000fa91  mov     ecx, eax; unsigned int
0x18000fa93  mov     edi, eax
0x18000fa95  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000fa9a  test    eax, eax
0x18000fa9c  jz      short loc_18000FAAC
0x18000fa9e  movzx   ebx, di
0x18000faa1  or      ebx, 80070000h
0x18000faa7  test    edi, edi
0x18000faa9  cmovle  ebx, edi
0x18000faac  mov     rcx, rsi; lpCriticalSection
0x18000faaf  call    cs:__imp_LeaveCriticalSection
0x18000fab5  mov     rbp, [rsp+38h+arg_8]
0x18000faba  mov     eax, ebx
0x18000fabc  mov     rbx, [rsp+38h+arg_0]
0x18000fac1  mov     rsi, [rsp+38h+arg_10]
0x18000fac6  mov     rdi, [rsp+38h+arg_18]
0x18000facb  add     rsp, 30h
0x18000facf  pop     r14
0x18000fad1  retn
```
