# CWdsDeviceControllerPacket::GetDeviceQuery(CWdsDeviceQuery *)

- ea: `0x18000dfa0`
- end: `0x18000e151`
- name: `?GetDeviceQuery@CWdsDeviceControllerPacket@@QEAAKPEAUCWdsDeviceQuery@@@Z`
- size: `433`
- prototype: `unsigned int __fastcall(CWdsDeviceControllerPacket *__hidden this, struct CWdsDeviceQuery *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002bd8`

## callees

- `0x18000dde4`
- `0x18000dfa0`
- `0x18000e158`
- `0x1800129e4`
- `0x180012ac8`
- `0x180013dcc`
- `0x180014d58`
- `0x1800150b8`

## string_xrefs

- `0x18000dff0`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x18000e096`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerclient.cpp`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerPacket::GetDeviceQuery(
        CWdsDeviceControllerPacket *this,
        struct CWdsDeviceQuery *a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned __int16 *v4; // rsi
  unsigned int ULONG; // eax
  const char *v8; // rdx
  unsigned int Metadata; // ebx
  const char *v10; // rdx
  const char *v11; // rdx
  const char *v12; // rdx
  const char *v13; // rdx
  void *v14; // rcx
  unsigned int v15; // r9d
  const char *v16; // rdx
  void *Block; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int16 *v19; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  LODWORD(Block) = 0;
  v19 = 0;
  ULONG = CControlPacket::GetULONG(this, L"DeviceQuery.Type", 0, a4, (unsigned int *)&Block);
  Metadata = ULONG;
  if ( ULONG == 2 )
  {
    CWdsDeviceQuery::Shutdown(a2);
    return 0;
  }
  else if ( !ElValidateWin32(ULONG, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x3B3u) )
  {
    if ( (_DWORD)Block )
    {
      if ( (_DWORD)Block == 1 )
      {
        CWdsDeviceQuery::Shutdown(a2);
        Metadata = CWdsDeviceControllerPacket::GetMetadata(
                     this,
                     L"Metadata",
                     (struct CWdsDeviceQuery *)((char *)a2 + 8),
                     v15);
        if ( ElValidateWin32(Metadata, v16, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x3D0u) )
          return Metadata;
        *((_DWORD *)a2 + 20) = 1;
      }
      else
      {
        if ( (_DWORD)Block != 2 )
        {
          Metadata = 13;
          ElValidateWin32(0xDu, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x3D7u);
          return Metadata;
        }
        Metadata = CControlPacket::GetString(this, L"DeviceQuery.NamePattern", 0, 0xFFFFFFFF, &v19);
        if ( ElValidateWin32(Metadata, v11, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x3C4u) )
        {
          v4 = v19;
        }
        else
        {
          Block = 0;
          v4 = v19;
          Metadata = DuplicateStringW(v19, (unsigned __int16 **)&Block);
          if ( ElValidateWin32(
                 Metadata,
                 v12,
                 "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerclient.cpp",
                 0xBAu) )
          {
            v14 = Block;
          }
          else
          {
            CWdsDeviceQuery::Shutdown(a2);
            v14 = 0;
            *(_QWORD *)a2 = Block;
            *((_DWORD *)a2 + 20) = 2;
          }
          if ( v14 )
            operator delete(v14);
          ElValidateWin32(Metadata, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x3C7u);
        }
      }
    }
    else
    {
      CWdsDeviceQuery::Shutdown(a2);
    }
    if ( v4 )
      operator delete(v4);
  }
  return Metadata;
}

```

## disassembly

```asm
0x18000dfa0  mov     rax, rsp
0x18000dfa3  mov     [rax+8], rbx
0x18000dfa7  mov     [rax+10h], rbp
0x18000dfab  push    rsi
0x18000dfac  push    rdi
0x18000dfad  push    r14
0x18000dfaf  sub     rsp, 30h
0x18000dfb3  xor     esi, esi
0x18000dfb5  mov     rdi, rdx
0x18000dfb8  and     [rax+18h], esi
0x18000dfbb  xor     r8d, r8d; unsigned __int16 *
0x18000dfbe  mov     [rax+20h], rsi
0x18000dfc2  lea     rax, [rax+18h]
0x18000dfc6  lea     rdx, aDevicequeryTyp; "DeviceQuery.Type"
0x18000dfcd  mov     [rsp+48h+var_28], rax; unsigned int *
0x18000dfd2  mov     rbp, rcx
0x18000dfd5  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18000dfda  mov     ebx, eax
0x18000dfdc  cmp     eax, 2
0x18000dfdf  jnz     short loc_18000DFF0
0x18000dfe1  mov     rcx, rdi; this
0x18000dfe4  call    ?Shutdown@CWdsDeviceQuery@@QEAAXXZ; CWdsDeviceQuery::Shutdown(void)
0x18000dfe9  xor     ebx, ebx
0x18000dfeb  jmp     loc_18000E13C
0x18000dff0  lea     r14, aBaseEcoWdsLibM_5; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000dff7  mov     r9d, 3B3h; unsigned int
0x18000dffd  mov     r8, r14; char *
0x18000e000  mov     ecx, eax; unsigned int
0x18000e002  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e007  test    eax, eax
0x18000e009  jnz     loc_18000E13C
0x18000e00f  mov     eax, dword ptr [rsp+48h+Block]
0x18000e013  test    eax, eax
0x18000e015  jz      loc_18000E127
0x18000e01b  sub     eax, 1
0x18000e01e  jz      loc_18000E0ED
0x18000e024  cmp     eax, 1
0x18000e027  jz      short loc_18000E043
0x18000e029  mov     ebx, 0Dh
0x18000e02e  mov     r9d, 3D7h; unsigned int
0x18000e034  mov     ecx, ebx; unsigned int
0x18000e036  mov     r8, r14; char *
0x18000e039  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e03e  jmp     loc_18000E13C
0x18000e043  lea     rax, [rsp+48h+arg_18]
0x18000e048  or      r9d, 0FFFFFFFFh; unsigned int
0x18000e04c  xor     r8d, r8d; unsigned __int16 *
0x18000e04f  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x18000e054  lea     rdx, aDevicequeryNam; "DeviceQuery.NamePattern"
0x18000e05b  mov     rcx, rbp; this
0x18000e05e  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x18000e063  mov     r9d, 3C4h; unsigned int
0x18000e069  mov     r8, r14; char *
0x18000e06c  mov     ecx, eax; unsigned int
0x18000e06e  mov     ebx, eax
0x18000e070  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e075  test    eax, eax
0x18000e077  jnz     short loc_18000E0E6
0x18000e079  and     [rsp+48h+Block], rsi
0x18000e07e  lea     rdx, [rsp+48h+Block]; unsigned __int16 **
0x18000e083  mov     rsi, [rsp+48h+arg_18]
0x18000e088  mov     rcx, rsi; unsigned __int16 *
0x18000e08b  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18000e090  mov     r9d, 0BAh; unsigned int
0x18000e096  lea     r8, aBaseEcoWdsLibM_3; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e09d  mov     ecx, eax; unsigned int
0x18000e09f  mov     ebx, eax
0x18000e0a1  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e0a6  test    eax, eax
0x18000e0a8  jnz     short loc_18000E0C5
0x18000e0aa  mov     rcx, rdi; this
0x18000e0ad  call    ?Shutdown@CWdsDeviceQuery@@QEAAXXZ; CWdsDeviceQuery::Shutdown(void)
0x18000e0b2  mov     rax, [rsp+48h+Block]
0x18000e0b7  xor     ecx, ecx
0x18000e0b9  mov     [rdi], rax
0x18000e0bc  mov     dword ptr [rdi+50h], 2
0x18000e0c3  jmp     short loc_18000E0CA
0x18000e0c5  mov     rcx, [rsp+48h+Block]; Block
0x18000e0ca  test    rcx, rcx
0x18000e0cd  jz      short loc_18000E0D4
0x18000e0cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e0d4  mov     r9d, 3C7h; unsigned int
0x18000e0da  mov     r8, r14; char *
0x18000e0dd  mov     ecx, ebx; unsigned int
0x18000e0df  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e0e4  jmp     short loc_18000E12F
0x18000e0e6  mov     rsi, [rsp+48h+arg_18]
0x18000e0eb  jmp     short loc_18000E12F
0x18000e0ed  mov     rcx, rdi; this
0x18000e0f0  call    ?Shutdown@CWdsDeviceQuery@@QEAAXXZ; CWdsDeviceQuery::Shutdown(void)
0x18000e0f5  lea     r8, [rdi+8]; struct CWdsMetadata *
0x18000e0f9  mov     rcx, rbp; this
0x18000e0fc  lea     rdx, aMetadata; "Metadata"
0x18000e103  call    ?GetMetadata@CWdsDeviceControllerPacket@@QEAAKPEBGPEAVCWdsMetadata@@@Z; CWdsDeviceControllerPacket::GetMetadata(ushort const *,CWdsMetadata *)
0x18000e108  mov     r9d, 3D0h; unsigned int
0x18000e10e  mov     r8, r14; char *
0x18000e111  mov     ecx, eax; unsigned int
0x18000e113  mov     ebx, eax
0x18000e115  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e11a  test    eax, eax
0x18000e11c  jnz     short loc_18000E13C
0x18000e11e  mov     dword ptr [rdi+50h], 1
0x18000e125  jmp     short loc_18000E12F
0x18000e127  mov     rcx, rdi; this
0x18000e12a  call    ?Shutdown@CWdsDeviceQuery@@QEAAXXZ; CWdsDeviceQuery::Shutdown(void)
0x18000e12f  test    rsi, rsi
0x18000e132  jz      short loc_18000E13C
0x18000e134  mov     rcx, rsi; Block
0x18000e137  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e13c  mov     rbp, [rsp+48h+arg_8]
0x18000e141  mov     eax, ebx
0x18000e143  mov     rbx, [rsp+48h+arg_0]
0x18000e148  add     rsp, 30h
0x18000e14c  pop     r14
0x18000e14e  pop     rdi
0x18000e14f  pop     rsi
0x18000e150  retn
```
