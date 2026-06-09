# CWdsDeviceControllerManager::QueryRequest(ATL::CComObject<CWdsDeviceControllerRequest> *,CWdsDeviceControllerPacket *,CWdsDeviceControllerPacket *)

- ea: `0x180003398`
- end: `0x180003502`
- name: `?QueryRequest@CWdsDeviceControllerManager@@AEAAKPEAV?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@PEAVCWdsDeviceControllerPacket@@1@Z`
- size: `362`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, CWdsDeviceControllerRequest *this, CWdsDeviceControllerPacket *, CWdsDeviceControllerPacket *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000294c`
- `0x180003508`

## callees

- `0x180001370`
- `0x180003398`
- `0x1800042f4`
- `0x18000a5e8`
- `0x18000dab4`
- `0x18000dde4`
- `0x180014d58`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::QueryRequest(
        LPCRITICAL_SECTION lpCriticalSection,
        CWdsDeviceControllerRequest *this,
        CWdsDeviceControllerPacket *a3,
        CWdsDeviceControllerPacket *a4)
{
  bool v4; // zf
  unsigned int Metadata; // ebx
  const char *v10; // rdx
  const char *v11; // rdx
  const char *v12; // rdx
  const char *v13; // rdx
  _QWORD v15[10]; // [rsp+28h] [rbp-69h] BYREF
  _QWORD v16[10]; // [rsp+78h] [rbp-19h] BYREF

  v4 = *((_DWORD *)a3 + 6) == 2;
  v16[0] = 0;
  v16[1] = 0;
  v16[3] = 0;
  v16[4] = 0;
  v16[6] = 0;
  v16[7] = 0;
  v15[0] = 0;
  v15[1] = 0;
  v15[3] = 0;
  v15[4] = 0;
  v15[6] = 0;
  v15[7] = 0;
  if ( v4
    || (Metadata = 87,
        !ElValidateWin32(
           0x57u,
           (const char *)this,
           "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
           0x3D0u)) )
  {
    Metadata = CWdsDeviceControllerPacket::GetMetadata(a3, L"Metadata", (struct CWdsMetadata *)v16);
    if ( !ElValidateWin32(
            Metadata,
            v10,
            "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
            0x3D4u) )
    {
      Metadata = CWdsDeviceControllerPacket::GetMetadata(a3, L"MetadataRS", (struct CWdsMetadata *)v15);
      if ( !ElValidateWin32(
              Metadata,
              v11,
              "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
              0x3D8u) )
      {
        Metadata = CWdsDeviceControllerManager::QueryMetadata(lpCriticalSection);
        if ( !ElValidateWin32(
                Metadata,
                v12,
                "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                0x3DBu) )
        {
          CWdsDeviceControllerRequest::Shutdown(this);
          Metadata = CWdsDeviceControllerPacket::AddMetadata(a4, L"Metadata", (const struct CWdsMetadata *)v15);
          ElValidateWin32(
            Metadata,
            v13,
            "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
            0x3E0u);
        }
      }
    }
  }
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v15);
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v16);
  return Metadata;
}

```

## disassembly

```asm
0x180003398  mov     rax, rsp
0x18000339b  mov     [rax+8], rbx
0x18000339f  mov     [rax+10h], rsi
0x1800033a3  mov     [rax+18h], rdi
0x1800033a7  push    rbp
0x1800033a8  push    r12
0x1800033aa  push    r13
0x1800033ac  push    r14
0x1800033ae  push    r15
0x1800033b0  lea     rbp, [rax-5Fh]
0x1800033b4  sub     rsp, 0C0h
0x1800033bb  xor     r12d, r12d
0x1800033be  lea     r13, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800033c5  cmp     dword ptr [r8+18h], 2
0x1800033ca  mov     r14, r9
0x1800033cd  mov     rdi, r8
0x1800033d0  mov     [rbp+57h+var_70], r12
0x1800033d4  mov     rsi, rdx
0x1800033d7  mov     [rbp+57h+var_68], r12
0x1800033db  mov     r15, rcx
0x1800033de  mov     [rbp+57h+var_58], r12
0x1800033e2  mov     [rbp+57h+var_50], r12
0x1800033e6  mov     [rbp+57h+var_40], r12
0x1800033ea  mov     [rbp+57h+var_38], r12
0x1800033ee  mov     [rbp+57h+var_C0], r12
0x1800033f2  mov     [rbp+57h+var_B8], r12
0x1800033f6  mov     [rbp+57h+var_A8], r12
0x1800033fa  mov     [rbp+57h+var_A0], r12
0x1800033fe  mov     [rbp+57h+var_90], r12
0x180003402  mov     [rbp+57h+var_88], r12
0x180003406  jz      short loc_180003425
0x180003408  lea     ebx, [r12+57h]
0x18000340d  mov     r9d, 3D0h; unsigned int
0x180003413  mov     ecx, ebx; unsigned int
0x180003415  mov     r8, r13; char *
0x180003418  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000341d  test    eax, eax
0x18000341f  jnz     loc_1800034CD
0x180003425  lea     r8, [rbp+57h+var_70]; struct CWdsMetadata *
0x180003429  mov     rcx, rdi; this
0x18000342c  lea     rdx, aMetadata; "Metadata"
0x180003433  call    ?GetMetadata@CWdsDeviceControllerPacket@@QEAAKPEBGPEAVCWdsMetadata@@@Z; CWdsDeviceControllerPacket::GetMetadata(ushort const *,CWdsMetadata *)
0x180003438  mov     r9d, 3D4h; unsigned int
0x18000343e  mov     r8, r13; char *
0x180003441  mov     ecx, eax; unsigned int
0x180003443  mov     ebx, eax
0x180003445  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000344a  test    eax, eax
0x18000344c  jnz     short loc_1800034CD
0x18000344e  lea     r8, [rbp+57h+var_C0]; struct CWdsMetadata *
0x180003452  mov     rcx, rdi; this
0x180003455  lea     rdx, aMetadatars; "MetadataRS"
0x18000345c  call    ?GetMetadata@CWdsDeviceControllerPacket@@QEAAKPEBGPEAVCWdsMetadata@@@Z; CWdsDeviceControllerPacket::GetMetadata(ushort const *,CWdsMetadata *)
0x180003461  mov     r9d, 3D8h; unsigned int
0x180003467  mov     r8, r13; char *
0x18000346a  mov     ecx, eax; unsigned int
0x18000346c  mov     ebx, eax
0x18000346e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180003473  test    eax, eax
0x180003475  jnz     short loc_1800034CD
0x180003477  lea     r9, [rbp+57h+var_C0]
0x18000347b  mov     rdx, rsi
0x18000347e  lea     r8, [rbp+57h+var_70]
0x180003482  mov     rcx, r15; lpCriticalSection
0x180003485  call    ?QueryMetadata@CWdsDeviceControllerManager@@QEAAKPEAV?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@PEBVCWdsMetadata@@PEAV4@@Z; CWdsDeviceControllerManager::QueryMetadata(ATL::CComObject<CWdsDeviceControllerRequest> *,CWdsMetadata const *,CWdsMetadata *)
0x18000348a  mov     r9d, 3DBh; unsigned int
0x180003490  mov     r8, r13; char *
0x180003493  mov     ecx, eax; unsigned int
0x180003495  mov     ebx, eax
0x180003497  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000349c  test    eax, eax
0x18000349e  jnz     short loc_1800034CD
0x1800034a0  mov     rcx, rsi; this
0x1800034a3  call    ?Shutdown@CWdsDeviceControllerRequest@@QEAAXXZ; CWdsDeviceControllerRequest::Shutdown(void)
0x1800034a8  lea     r8, [rbp+57h+var_C0]; struct CWdsMetadata *
0x1800034ac  mov     rcx, r14; this
0x1800034af  lea     rdx, aMetadata; "Metadata"
0x1800034b6  call    ?AddMetadata@CWdsDeviceControllerPacket@@QEAAKPEBGPEBVCWdsMetadata@@@Z; CWdsDeviceControllerPacket::AddMetadata(ushort const *,CWdsMetadata const *)
0x1800034bb  mov     r9d, 3E0h; unsigned int
0x1800034c1  mov     r8, r13; char *
0x1800034c4  mov     ecx, eax; unsigned int
0x1800034c6  mov     ebx, eax
0x1800034c8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800034cd  lea     rcx, [rbp+57h+var_C0]; this
0x1800034d1  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x1800034d6  lea     rcx, [rbp+57h+var_70]; this
0x1800034da  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x1800034df  lea     r11, [rsp+0E0h+var_20]
0x1800034e7  mov     eax, ebx
0x1800034e9  mov     rbx, [r11+30h]
0x1800034ed  mov     rsi, [r11+38h]
0x1800034f1  mov     rdi, [r11+40h]
0x1800034f5  mov     rsp, r11
0x1800034f8  pop     r15
0x1800034fa  pop     r14
0x1800034fc  pop     r13
0x1800034fe  pop     r12
0x180003500  pop     rbp
0x180003501  retn
```
