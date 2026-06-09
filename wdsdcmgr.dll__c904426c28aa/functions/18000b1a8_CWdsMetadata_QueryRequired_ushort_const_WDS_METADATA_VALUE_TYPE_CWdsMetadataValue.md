# CWdsMetadata::QueryRequired(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *)

- ea: `0x18000b1a8`
- end: `0x18000b221`
- name: `?QueryRequired@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x1800042f4`
- `0x180010790`
- `0x1800108e0`
- `0x180010a00`
- `0x180010b60`
- `0x180010c80`
- `0x180010da0`
- `0x180011000`

## callees

- `0x180009838`
- `0x18000af78`
- `0x18000b1a8`
- `0x180014d58`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::QueryRequired(
        CWdsMetadata *a1,
        const unsigned __int16 *a2,
        int a3,
        CWdsMetadataValue *a4)
{
  unsigned int Optional; // ebx
  const char *v6; // rdx
  const char *v7; // rdx
  int v9; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+38h] [rbp-20h]
  __int64 v11; // [rsp+40h] [rbp-18h]

  v9 = 0;
  v10 = 0;
  v11 = 0;
  Optional = CWdsMetadata::QueryOptional(a1, a2, a3, a4, (struct CWdsMetadataValue *)&v9);
  if ( !(unsigned int)ElValidateWin32(Optional, v6, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xF42u)
    && !*(_DWORD *)a4 )
  {
    Optional = 1168;
    ElValidateWin32(0x490u, v7, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xF48u);
  }
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v9);
  return Optional;
}

```

## disassembly

```asm
0x18000b1a8  mov     r11, rsp
0x18000b1ab  mov     [r11+8], rbx
0x18000b1af  push    rdi
0x18000b1b0  sub     rsp, 50h
0x18000b1b4  and     [rsp+58h+var_28], 0
0x18000b1b9  xor     eax, eax
0x18000b1bb  mov     [r11-20h], rax
0x18000b1bf  mov     rdi, r9
0x18000b1c2  mov     [r11-18h], rax
0x18000b1c6  lea     rax, [r11-28h]
0x18000b1ca  mov     [r11-38h], rax
0x18000b1ce  call    ?QueryOptional@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@PEBV3@@Z; CWdsMetadata::QueryOptional(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *,CWdsMetadataValue const *)
0x18000b1d3  mov     r9d, 0F42h; unsigned int
0x18000b1d9  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000b1e0  mov     ecx, eax; unsigned int
0x18000b1e2  mov     ebx, eax
0x18000b1e4  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000b1e9  test    eax, eax
0x18000b1eb  jnz     short loc_18000B20A
0x18000b1ed  cmp     [rdi], eax
0x18000b1ef  jnz     short loc_18000B20A
0x18000b1f1  mov     ebx, 490h
0x18000b1f6  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000b1fd  mov     ecx, ebx; unsigned int
0x18000b1ff  mov     r9d, 0F48h; unsigned int
0x18000b205  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000b20a  lea     rcx, [rsp+58h+var_28]; this
0x18000b20f  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18000b214  mov     eax, ebx
0x18000b216  mov     rbx, [rsp+58h+arg_0]
0x18000b21b  add     rsp, 50h
0x18000b21f  pop     rdi
0x18000b220  retn
```
