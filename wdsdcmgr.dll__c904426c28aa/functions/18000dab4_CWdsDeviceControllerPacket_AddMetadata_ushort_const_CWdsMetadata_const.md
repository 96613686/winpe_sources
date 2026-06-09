# CWdsDeviceControllerPacket::AddMetadata(ushort const *,CWdsMetadata const *)

- ea: `0x18000dab4`
- end: `0x18000dbec`
- name: `?AddMetadata@CWdsDeviceControllerPacket@@QEAAKPEBGPEBVCWdsMetadata@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(CWdsDeviceControllerPacket *this, unsigned __int16 *, const struct CWdsMetadata *, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002bd8`
- `0x180003398`

## callees

- `0x18000a3f0`
- `0x18000ad94`
- `0x18000dab4`
- `0x18001284c`
- `0x180012910`
- `0x180014d58`
- `0x1800150b8`

## string_xrefs

- `0x18000daf3`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x18000db2e`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x18000db5b`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x18000db94`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerPacket::AddMetadata(
        CWdsDeviceControllerPacket *this,
        unsigned __int16 *a2,
        const struct CWdsMetadata *a3,
        __int64 a4)
{
  unsigned int v4; // ebp
  void *v6; // rbx
  unsigned int v9; // esi
  const char *v10; // rdx
  unsigned int v11; // edi
  const char *v12; // rdx
  const char *v13; // rdx
  unsigned int v14; // eax
  const char *v15; // rdx
  void *Block; // [rsp+70h] [rbp+18h] BYREF
  struct CWdsMetadataEntry *v18; // [rsp+78h] [rbp+20h] BYREF

  v4 = *((_DWORD *)a3 + 15);
  v6 = 0;
  Block = 0;
  v9 = CControlPacket::AddULONG(this, a2, L"Count", a4, v4);
  if ( !ElValidateWin32(v9, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x72u) )
  {
    v11 = 0;
    if ( v4 )
    {
      do
      {
        v18 = 0;
        v9 = CWdsMetadata::GetByIndex(a3, v11, &v18);
        if ( ElValidateWin32(v9, v12, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x79u) )
          break;
        v9 = CWdsMetadataEntry::ToString(v18, (unsigned __int16 **)&Block);
        v14 = ElValidateWin32(v9, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x7Cu);
        v6 = Block;
        if ( v14 )
          break;
        v9 = CControlPacket::AddString(this, (const char *)a2, L"Entry", v11, (unsigned __int16 *)Block);
        if ( ElValidateWin32(v9, v15, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x82u) )
          break;
        if ( v6 )
        {
          operator delete(v6);
          v6 = 0;
          Block = 0;
        }
        ++v11;
      }
      while ( v11 < v4 );
      if ( v6 )
        operator delete(v6);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18000dab4  mov     rax, rsp
0x18000dab7  mov     [rax+8], rbx
0x18000dabb  mov     [rax+10h], rbp
0x18000dabf  push    rsi
0x18000dac0  push    rdi
0x18000dac1  push    r12
0x18000dac3  push    r14
0x18000dac5  push    r15
0x18000dac7  sub     rsp, 30h
0x18000dacb  mov     ebp, [r8+3Ch]
0x18000dacf  mov     r14, r8
0x18000dad2  xor     ebx, ebx
0x18000dad4  mov     [rax-38h], ebp
0x18000dad7  lea     r8, aCount
0x18000dade  mov     [rax+18h], rbx
0x18000dae2  mov     r15, rdx
0x18000dae5  mov     r12, rcx
0x18000dae8  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z
0x18000daed  lea     r9d, [rbx+72h]; unsigned int
0x18000daf1  mov     ecx, eax; unsigned int
0x18000daf3  lea     r8, aBaseEcoWdsLibM_5
0x18000dafa  mov     esi, eax
0x18000dafc  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000db01  test    eax, eax
0x18000db03  jnz     loc_18000DBD3
0x18000db09  xor     edi, edi
0x18000db0b  test    ebp, ebp
0x18000db0d  jz      loc_18000DBD3
0x18000db13  and     [rsp+58h+arg_18], 0
0x18000db19  lea     r8, [rsp+58h+arg_18]; struct CWdsMetadataEntry **
0x18000db1e  mov     edx, edi; unsigned int
0x18000db20  mov     rcx, r14; this
0x18000db23  call    ?GetByIndex@CWdsMetadata@@QEBAKKPEAPEBVCWdsMetadataEntry@@@Z
0x18000db28  mov     r9d, 79h ; 'y'; unsigned int
0x18000db2e  lea     r8, aBaseEcoWdsLibM_5
0x18000db35  mov     ecx, eax; unsigned int
0x18000db37  mov     esi, eax
0x18000db39  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000db3e  test    eax, eax
0x18000db40  jnz     loc_18000DBC6
0x18000db46  mov     rcx, [rsp+58h+arg_18]; this
0x18000db4b  lea     rdx, [rsp+58h+Block]; unsigned __int16 **
0x18000db50  call    ?ToString@CWdsMetadataEntry@@QEBAKPEAPEAG@Z
0x18000db55  mov     r9d, 7Ch ; '|'; unsigned int
0x18000db5b  lea     r8, aBaseEcoWdsLibM_5
0x18000db62  mov     ecx, eax; unsigned int
0x18000db64  mov     esi, eax
0x18000db66  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000db6b  mov     rbx, [rsp+58h+Block]
0x18000db70  test    eax, eax
0x18000db72  jnz     short loc_18000DBC6
0x18000db74  mov     r9d, edi; unsigned int
0x18000db77  mov     [rsp+58h+var_38], rbx; unsigned __int16 *
0x18000db7c  lea     r8, aEntry
0x18000db83  mov     rdx, r15; unsigned __int16 *
0x18000db86  mov     rcx, r12; this
0x18000db89  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z
0x18000db8e  mov     r9d, 82h; unsigned int
0x18000db94  lea     r8, aBaseEcoWdsLibM_5
0x18000db9b  mov     ecx, eax; unsigned int
0x18000db9d  mov     esi, eax
0x18000db9f  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000dba4  test    eax, eax
0x18000dba6  jnz     short loc_18000DBC6
0x18000dba8  test    rbx, rbx
0x18000dbab  jz      short loc_18000DBBC
0x18000dbad  mov     rcx, rbx; Block
0x18000dbb0  call    ??3@YAXPEAX@Z
0x18000dbb5  xor     ebx, ebx
0x18000dbb7  mov     [rsp+58h+Block], rbx
0x18000dbbc  inc     edi
0x18000dbbe  cmp     edi, ebp
0x18000dbc0  jb      loc_18000DB13
0x18000dbc6  test    rbx, rbx
0x18000dbc9  jz      short loc_18000DBD3
0x18000dbcb  mov     rcx, rbx; Block
0x18000dbce  call    ??3@YAXPEAX@Z
0x18000dbd3  mov     rbx, [rsp+58h+arg_0]
0x18000dbd8  mov     eax, esi
0x18000dbda  mov     rbp, [rsp+58h+arg_8]
0x18000dbdf  add     rsp, 30h
0x18000dbe3  pop     r15
0x18000dbe5  pop     r14
0x18000dbe7  pop     r12
0x18000dbe9  pop     rdi
0x18000dbea  pop     rsi
0x18000dbeb  retn
```
