# CWdsComMetadataBuilder::FilterMatch(IWdsMetadata *,short *)

- ea: `0x18000ee00`
- end: `0x18000ef10`
- name: `?FilterMatch@CWdsComMetadataBuilder@@UEAAJPEAUIWdsMetadata@@PEAF@Z`
- size: `272`
- prototype: `__int64 __fastcall(CWdsComMetadataBuilder *__hidden this, struct IWdsMetadata *, __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000d160`
- `0x18000ee00`
- `0x180014d58`
- `0x180014ee0`
- `0x180015c6d`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000ee27`
- `KERNEL32!EnterCriticalSection` at `0x18000ee27`
- `KERNEL32!LeaveCriticalSection` at `0x18000eef5`
- `KERNEL32!LeaveCriticalSection` at `0x18000eef5`

## string_xrefs

- `0x18000ee40`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000ee86`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000eed2`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::FilterMatch(
        CWdsComMetadataBuilder *this,
        struct IWdsMetadata *a2,
        __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  unsigned int v7; // edi
  const char *v8; // rdx
  const char *v9; // rdx
  __int64 v10; // rbx
  unsigned int v11; // ebx
  const char *v12; // rdx
  const char *v13; // rdx
  int v15; // [rsp+50h] [rbp+8h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v15 = 0;
  if ( a2 && a3
    || (v7 = -2147024809,
        (int)ElValidateHr(-2147024809, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x280u) >= 0) )
  {
    v10 = _RTDynamicCast_0(
            a2,
            0,
            &IWdsMetadata `RTTI Type Descriptor',
            &CWdsComMetadataBuilder `RTTI Type Descriptor',
            0);
    if ( v10
      || (v7 = -2147024809,
          (int)ElValidateHr(-2147024809, v9, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x287u) >= 0) )
    {
      v11 = CWdsMetadata::ComputeMatch(
              (CWdsComMetadataBuilder *)((char *)this + 64),
              (const struct CWdsMetadata *)(v10 + 64),
              1,
              &v15);
      ElValidateWin32(v11, v12, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x1743u);
      if ( !ElValidateWin32(v11, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x28Bu) )
        *a3 = -(v15 != 0);
    }
  }
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x18000ee00  mov     [rsp+arg_8], rbx
0x18000ee05  mov     [rsp+arg_10], rbp
0x18000ee0a  push    rsi
0x18000ee0b  push    rdi
0x18000ee0c  push    r14
0x18000ee0e  sub     rsp, 30h
0x18000ee12  lea     rbp, [rcx+88h]
0x18000ee19  mov     r14, rcx
0x18000ee1c  mov     rcx, rbp; lpCriticalSection
0x18000ee1f  mov     rsi, r8
0x18000ee22  mov     rbx, rdx
0x18000ee25  xor     edi, edi
0x18000ee27  call    cs:__imp_EnterCriticalSection
0x18000ee2d  and     [rsp+48h+arg_0], edi
0x18000ee31  test    rbx, rbx
0x18000ee34  jz      short loc_18000EE3B
0x18000ee36  test    rsi, rsi
0x18000ee39  jnz     short loc_18000EE5C
0x18000ee3b  mov     edi, 80070057h
0x18000ee40  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000ee47  mov     ecx, edi; int
0x18000ee49  mov     r9d, 280h; unsigned int
0x18000ee4f  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000ee54  test    eax, eax
0x18000ee56  js      loc_18000EEF2
0x18000ee5c  and     [rsp+48h+var_28], 0
0x18000ee61  lea     r9, ??_R0?AVCWdsComMetadataBuilder@@@8; CWdsComMetadataBuilder `RTTI Type Descriptor'
0x18000ee68  lea     r8, ??_R0?AUIWdsMetadata@@@8; IWdsMetadata `RTTI Type Descriptor'
0x18000ee6f  xor     edx, edx
0x18000ee71  mov     rcx, rbx
0x18000ee74  call    __RTDynamicCast_0
0x18000ee79  mov     rbx, rax
0x18000ee7c  test    rax, rax
0x18000ee7f  jnz     short loc_18000EE9E
0x18000ee81  mov     edi, 80070057h
0x18000ee86  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000ee8d  mov     ecx, edi; int
0x18000ee8f  mov     r9d, 287h; unsigned int
0x18000ee95  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000ee9a  test    eax, eax
0x18000ee9c  js      short loc_18000EEF2
0x18000ee9e  lea     rdx, [rbx+40h]; struct CWdsMetadata *
0x18000eea2  mov     r8d, 1; int
0x18000eea8  lea     rcx, [r14+40h]; this
0x18000eeac  lea     r9, [rsp+48h+arg_0]; int *
0x18000eeb1  call    ?ComputeMatch@CWdsMetadata@@AEBAKPEBV1@HPEAH@Z; CWdsMetadata::ComputeMatch(CWdsMetadata const *,int,int *)
0x18000eeb6  mov     r9d, 1743h; unsigned int
0x18000eebc  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000eec3  mov     ecx, eax; unsigned int
0x18000eec5  mov     ebx, eax
0x18000eec7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000eecc  mov     r9d, 28Bh; unsigned int
0x18000eed2  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000eed9  mov     ecx, ebx; unsigned int
0x18000eedb  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000eee0  test    eax, eax
0x18000eee2  jnz     short loc_18000EEF2
0x18000eee4  mov     edx, [rsp+48h+arg_0]
0x18000eee8  neg     edx
0x18000eeea  sbb     r8w, r8w
0x18000eeee  mov     [rsi], r8w
0x18000eef2  mov     rcx, rbp; lpCriticalSection
0x18000eef5  call    cs:__imp_LeaveCriticalSection
0x18000eefb  mov     rbx, [rsp+48h+arg_8]
0x18000ef00  mov     eax, edi
0x18000ef02  mov     rbp, [rsp+48h+arg_10]
0x18000ef07  add     rsp, 30h
0x18000ef0b  pop     r14
0x18000ef0d  pop     rdi
0x18000ef0e  pop     rsi
0x18000ef0f  retn
```
