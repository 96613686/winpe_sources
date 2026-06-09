# CWdsComMetadataBuilder::Match(IWdsMetadata *,short *)

- ea: `0x18000ec90`
- end: `0x18000edf2`
- name: `?Match@CWdsComMetadataBuilder@@UEAAJPEAUIWdsMetadata@@PEAF@Z`
- size: `354`
- prototype: `__int64 __fastcall(CWdsComMetadataBuilder *__hidden this, struct IWdsMetadata *, __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000d160`
- `0x18000ec90`
- `0x180014d58`
- `0x180014ee0`
- `0x180015c6d`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000ecbb`
- `KERNEL32!EnterCriticalSection` at `0x18000ecbb`
- `KERNEL32!LeaveCriticalSection` at `0x18000edd3`
- `KERNEL32!LeaveCriticalSection` at `0x18000edd3`

## string_xrefs

- `0x18000ecd9`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000ed1d`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000edb6`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::Match(CWdsComMetadataBuilder *this, struct IWdsMetadata *a2, __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r14
  unsigned int v7; // edi
  const char *v8; // rdx
  int v9; // ebx
  const char *v10; // rdx
  __int64 v11; // rbp
  CWdsMetadata *v12; // r12
  unsigned int v13; // ebp
  const char *v14; // rdx
  const char *v15; // rdx
  const char *v16; // rdx
  int v18; // [rsp+60h] [rbp+8h] BYREF
  int v19; // [rsp+68h] [rbp+10h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v9 = 0;
  if ( a2 && a3
    || (v7 = -2147024809,
        (int)ElValidateHr(-2147024809, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x249u) >= 0) )
  {
    v11 = _RTDynamicCast_0(
            a2,
            0,
            &IWdsMetadata `RTTI Type Descriptor',
            &CWdsComMetadataBuilder `RTTI Type Descriptor',
            0);
    if ( v11
      || (v7 = -2147024809,
          (int)ElValidateHr(-2147024809, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x250u) >= 0) )
    {
      v18 = 0;
      v12 = (CWdsMetadata *)(v11 + 64);
      v19 = 0;
      v13 = CWdsMetadata::ComputeMatch(
              (CWdsComMetadataBuilder *)((char *)this + 64),
              (const struct CWdsMetadata *)(v11 + 64),
              0,
              &v18);
      if ( !ElValidateWin32(v13, v14, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x1717u) )
      {
        v13 = CWdsMetadata::ComputeMatch(v12, (CWdsComMetadataBuilder *)((char *)this + 64), 0, &v19);
        if ( !ElValidateWin32(v13, v16, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x171Au) && (v18 || v19) )
          v9 = 1;
      }
      if ( !ElValidateWin32(v13, v15, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x254u) )
        *a3 = -(v9 != 0);
    }
  }
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x18000ec90  mov     [rsp+arg_10], rbx
0x18000ec95  mov     [rsp+arg_18], rbp
0x18000ec9a  push    rsi
0x18000ec9b  push    rdi
0x18000ec9c  push    r12
0x18000ec9e  push    r14
0x18000eca0  push    r15
0x18000eca2  sub     rsp, 30h
0x18000eca6  lea     r14, [rcx+88h]
0x18000ecad  mov     r15, rcx
0x18000ecb0  mov     rcx, r14; lpCriticalSection
0x18000ecb3  mov     rsi, r8
0x18000ecb6  mov     rbp, rdx
0x18000ecb9  xor     edi, edi
0x18000ecbb  call    cs:__imp_EnterCriticalSection
0x18000ecc1  xor     ebx, ebx
0x18000ecc3  mov     r12d, 80070057h
0x18000ecc9  test    rbp, rbp
0x18000eccc  jz      short loc_18000ECD3
0x18000ecce  test    rsi, rsi
0x18000ecd1  jnz     short loc_18000ECF3
0x18000ecd3  mov     r9d, 249h; unsigned int
0x18000ecd9  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000ece0  mov     ecx, r12d; int
0x18000ece3  mov     edi, r12d
0x18000ece6  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000eceb  test    eax, eax
0x18000eced  js      loc_18000EDD0
0x18000ecf3  and     [rsp+58h+var_38], ebx
0x18000ecf7  lea     r9, ??_R0?AVCWdsComMetadataBuilder@@@8; CWdsComMetadataBuilder `RTTI Type Descriptor'
0x18000ecfe  lea     r8, ??_R0?AUIWdsMetadata@@@8; IWdsMetadata `RTTI Type Descriptor'
0x18000ed05  xor     edx, edx
0x18000ed07  mov     rcx, rbp
0x18000ed0a  call    __RTDynamicCast_0
0x18000ed0f  mov     rbp, rax
0x18000ed12  test    rax, rax
0x18000ed15  jnz     short loc_18000ED37
0x18000ed17  mov     r9d, 250h; unsigned int
0x18000ed1d  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000ed24  mov     ecx, r12d; int
0x18000ed27  mov     edi, r12d
0x18000ed2a  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000ed2f  test    eax, eax
0x18000ed31  js      loc_18000EDD0
0x18000ed37  and     [rsp+58h+arg_0], ebx
0x18000ed3b  lea     r12, [rbp+40h]
0x18000ed3f  and     [rsp+58h+arg_8], ebx
0x18000ed43  lea     r9, [rsp+58h+arg_0]; int *
0x18000ed48  mov     rdx, r12; struct CWdsMetadata *
0x18000ed4b  lea     rcx, [r15+40h]; this
0x18000ed4f  xor     r8d, r8d; int
0x18000ed52  call    ?ComputeMatch@CWdsMetadata@@AEBAKPEBV1@HPEAH@Z; CWdsMetadata::ComputeMatch(CWdsMetadata const *,int,int *)
0x18000ed57  mov     r9d, 1717h; unsigned int
0x18000ed5d  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000ed64  mov     ecx, eax; unsigned int
0x18000ed66  mov     ebp, eax
0x18000ed68  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ed6d  test    eax, eax
0x18000ed6f  jnz     short loc_18000EDB0
0x18000ed71  lea     r9, [rsp+58h+arg_8]; int *
0x18000ed76  xor     r8d, r8d; int
0x18000ed79  lea     rdx, [r15+40h]; struct CWdsMetadata *
0x18000ed7d  mov     rcx, r12; this
0x18000ed80  call    ?ComputeMatch@CWdsMetadata@@AEBAKPEBV1@HPEAH@Z; CWdsMetadata::ComputeMatch(CWdsMetadata const *,int,int *)
0x18000ed85  mov     r9d, 171Ah; unsigned int
0x18000ed8b  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000ed92  mov     ecx, eax; unsigned int
0x18000ed94  mov     ebp, eax
0x18000ed96  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ed9b  test    eax, eax
0x18000ed9d  jnz     short loc_18000EDB0
0x18000ed9f  cmp     [rsp+58h+arg_0], ebx
0x18000eda3  jnz     short loc_18000EDAB
0x18000eda5  cmp     [rsp+58h+arg_8], ebx
0x18000eda9  jz      short loc_18000EDB0
0x18000edab  mov     ebx, 1
0x18000edb0  mov     r9d, 254h; unsigned int
0x18000edb6  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000edbd  mov     ecx, ebp; unsigned int
0x18000edbf  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000edc4  test    eax, eax
0x18000edc6  jnz     short loc_18000EDD0
0x18000edc8  neg     ebx
0x18000edca  sbb     dx, dx
0x18000edcd  mov     [rsi], dx
0x18000edd0  mov     rcx, r14; lpCriticalSection
0x18000edd3  call    cs:__imp_LeaveCriticalSection
0x18000edd9  mov     rbx, [rsp+58h+arg_10]
0x18000edde  mov     eax, edi
0x18000ede0  mov     rbp, [rsp+58h+arg_18]
0x18000ede5  add     rsp, 30h
0x18000ede9  pop     r15
0x18000edeb  pop     r14
0x18000eded  pop     r12
0x18000edef  pop     rdi
0x18000edf0  pop     rsi
0x18000edf1  retn
```
