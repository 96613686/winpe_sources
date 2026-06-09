# CWdsDeviceControllerManager::LogProviderMetadataQuery(long,CWdsDeviceControllerManager::CQueryEntry *,CWdsComMetadata *,CWdsComMetadataBuilder *,__MIDL___MIDL_itf_wdsmetadata_0000_0000_0001)

- ea: `0x180004dbc`
- end: `0x180004f90`
- name: `?LogProviderMetadataQuery@CWdsDeviceControllerManager@@AEAAXJPEAUCQueryEntry@1@PEAVCWdsComMetadata@@PEAVCWdsComMetadataBuilder@@W4__MIDL___MIDL_itf_wdsmetadata_0000_0000_0001@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006dfc`

## callees

- `0x180004dbc`
- `0x1800071e4`
- `0x18000a5e8`
- `0x18000b228`
- `0x18000e65c`
- `0x180014d58`
- `0x1800150b8`

## pseudocode

```c
void __fastcall CWdsDeviceControllerManager::LogProviderMetadataQuery(
        __int64 a1,
        int a2,
        __int64 a3,
        CWdsComMetadataBuilder *a4,
        CWdsComMetadataBuilder *a5,
        char a6)
{
  unsigned __int16 *v7; // rbx
  unsigned int Metadata; // eax
  const char *v10; // rdx
  unsigned int v11; // eax
  const char *v12; // rdx
  unsigned int v13; // eax
  const char *v14; // rdx
  unsigned int v15; // eax
  const char *v16; // rdx
  unsigned int v17; // ebx
  int v18; // ecx
  __int64 *v19; // rdx
  unsigned __int16 *v20; // [rsp+48h] [rbp-79h] BYREF
  _QWORD v21[10]; // [rsp+58h] [rbp-69h] BYREF
  _QWORD v22[10]; // [rsp+A8h] [rbp-19h] BYREF
  void *Block; // [rsp+118h] [rbp+57h] BYREF

  Block = 0;
  v7 = 0;
  v20 = 0;
  if ( a2 < 0 )
  {
    if ( (byte_18001DD41 & 0x10) == 0 )
      return;
  }
  else if ( (byte_18001DD41 & 0x20) == 0 )
  {
    return;
  }
  v22[0] = 0;
  v22[1] = 0;
  v22[3] = 0;
  v22[4] = 0;
  v22[6] = 0;
  v22[7] = 0;
  v21[0] = 0;
  v21[1] = 0;
  v21[3] = 0;
  v21[4] = 0;
  v21[6] = 0;
  v21[7] = 0;
  Metadata = CWdsComMetadataBuilder::GetMetadata(a4, (struct CWdsMetadata *)v22);
  if ( ElValidateWin32(Metadata, v10, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x73Eu)
    || (v11 = CWdsComMetadataBuilder::GetMetadata(a5, (struct CWdsMetadata *)v21),
        ElValidateWin32(v11, v12, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x741u)) )
  {
    CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v21);
    CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v22);
    return;
  }
  v13 = CWdsMetadata::ToLines((CWdsMetadata *)v22, (unsigned __int16 **)&Block);
  if ( !ElValidateWin32(v13, v14, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x744u) )
  {
    v15 = CWdsMetadata::ToLines((CWdsMetadata *)v21, &v20);
    v17 = ElValidateWin32(v15, v16, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x747u);
    CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v21);
    CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v22);
    if ( !v17 )
    {
      if ( a2 < 0 )
      {
        if ( (byte_18001DD41 & 0x10) != 0 )
        {
          v19 = ProviderMetadataQueryFailed;
          goto LABEL_14;
        }
      }
      else if ( (byte_18001DD41 & 0x20) != 0 )
      {
        v19 = ProviderMetadataQuery;
LABEL_14:
        v7 = v20;
        McTemplateU0zzzqd(v18, (_DWORD)v19, *(_QWORD *)(a3 + 8), (_DWORD)Block, (__int64)v20, a6, a2);
        goto LABEL_18;
      }
    }
    v7 = v20;
    goto LABEL_18;
  }
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v21);
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v22);
LABEL_18:
  if ( Block )
    operator delete(Block);
  if ( v7 )
    operator delete(v7);
}

```

## disassembly

```asm
0x180004dbc  mov     rax, rsp
0x180004dbf  mov     [rax+10h], rbx
0x180004dc3  mov     [rax+18h], rsi
0x180004dc7  mov     [rax+8], rcx
0x180004dcb  push    rbp
0x180004dcc  push    r14
0x180004dce  push    r15
0x180004dd0  lea     rbp, [rax-4Fh]
0x180004dd4  sub     rsp, 0F0h
0x180004ddb  xor     r15d, r15d
0x180004dde  mov     r14, r8
0x180004de1  mov     [rbp+47h+Block], r15
0x180004de5  mov     ebx, r15d
0x180004de8  mov     [rbp+47h+var_C0], rbx
0x180004dec  mov     esi, edx
0x180004dee  test    edx, edx
0x180004df0  js      short loc_180004E00
0x180004df2  test    cs:byte_18001DD41, 20h
0x180004df9  jnz     short loc_180004E0D
0x180004dfb  jmp     loc_180004F77
0x180004e00  test    cs:byte_18001DD41, 10h
0x180004e07  jz      loc_180004F77
0x180004e0d  lea     rdx, [rbp+47h+var_60]; struct CWdsMetadata *
0x180004e11  mov     [rbp+47h+var_60], r15
0x180004e15  mov     rcx, r9; this
0x180004e18  mov     [rbp+47h+var_58], r15
0x180004e1c  mov     [rbp+47h+var_48], r15
0x180004e20  mov     [rbp+47h+var_40], r15
0x180004e24  mov     [rbp+47h+var_30], r15
0x180004e28  mov     [rbp+47h+var_28], r15
0x180004e2c  mov     [rbp+47h+var_B0], r15
0x180004e30  mov     [rbp+47h+var_A8], r15
0x180004e34  mov     [rbp+47h+var_98], r15
0x180004e38  mov     [rbp+47h+var_90], r15
0x180004e3c  mov     [rbp+47h+var_80], r15
0x180004e40  mov     [rbp+47h+var_78], r15
0x180004e44  call    ?GetMetadata@CWdsComMetadataBuilder@@QEAAKPEAVCWdsMetadata@@@Z; CWdsComMetadataBuilder::GetMetadata(CWdsMetadata *)
0x180004e49  mov     r9d, 73Eh; unsigned int
0x180004e4f  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180004e56  mov     ecx, eax; unsigned int
0x180004e58  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004e5d  test    eax, eax
0x180004e5f  jz      short loc_180004E78
0x180004e61  lea     rcx, [rbp+47h+var_B0]; this
0x180004e65  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180004e6a  lea     rcx, [rbp+47h+var_60]; this
0x180004e6e  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180004e73  jmp     loc_180004F77
0x180004e78  mov     rcx, [rbp+47h+arg_20]; this
0x180004e7c  lea     rdx, [rbp+47h+var_B0]; struct CWdsMetadata *
0x180004e80  call    ?GetMetadata@CWdsComMetadataBuilder@@QEAAKPEAVCWdsMetadata@@@Z; CWdsComMetadataBuilder::GetMetadata(CWdsMetadata *)
0x180004e85  mov     r9d, 741h; unsigned int
0x180004e8b  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180004e92  mov     ecx, eax; unsigned int
0x180004e94  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004e99  test    eax, eax
0x180004e9b  jnz     short loc_180004E61
0x180004e9d  lea     rdx, [rbp+47h+Block]; unsigned __int16 **
0x180004ea1  lea     rcx, [rbp+47h+var_60]; this
0x180004ea5  call    ?ToLines@CWdsMetadata@@QEBAKPEAPEAG@Z; CWdsMetadata::ToLines(ushort * *)
0x180004eaa  mov     r9d, 744h; unsigned int
0x180004eb0  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180004eb7  mov     ecx, eax; unsigned int
0x180004eb9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004ebe  lea     rcx, [rbp+47h+var_B0]; this
0x180004ec2  test    eax, eax
0x180004ec4  jz      short loc_180004ED9
0x180004ec6  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180004ecb  lea     rcx, [rbp+47h+var_60]; this
0x180004ecf  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180004ed4  jmp     loc_180004F5B
0x180004ed9  lea     rdx, [rbp+47h+var_C0]; unsigned __int16 **
0x180004edd  call    ?ToLines@CWdsMetadata@@QEBAKPEAPEAG@Z; CWdsMetadata::ToLines(ushort * *)
0x180004ee2  mov     r9d, 747h; unsigned int
0x180004ee8  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180004eef  mov     ecx, eax; unsigned int
0x180004ef1  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004ef6  lea     rcx, [rbp+47h+var_B0]; this
0x180004efa  mov     ebx, eax
0x180004efc  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180004f01  lea     rcx, [rbp+47h+var_60]; this
0x180004f05  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180004f0a  test    ebx, ebx
0x180004f0c  jnz     short loc_180004F57
0x180004f0e  test    esi, esi
0x180004f10  js      short loc_180004F45
0x180004f12  test    cs:byte_18001DD41, 20h
0x180004f19  jz      short loc_180004F57
0x180004f1b  lea     rdx, ProviderMetadataQuery
0x180004f22  mov     eax, [rbp+47h+arg_28]
0x180004f25  mov     rbx, [rbp+47h+var_C0]
0x180004f29  mov     r8, [r14+8]
0x180004f2d  mov     r9, [rbp+47h+Block]
0x180004f31  mov     [rsp+100h+var_D0], esi
0x180004f35  mov     [rsp+100h+var_D8], eax
0x180004f39  mov     qword ptr [rsp+100h+var_E0], rbx
0x180004f3e  call    McTemplateU0zzzqd
0x180004f43  jmp     short loc_180004F5B
0x180004f45  test    cs:byte_18001DD41, 10h
0x180004f4c  jz      short loc_180004F57
0x180004f4e  lea     rdx, ProviderMetadataQueryFailed
0x180004f55  jmp     short loc_180004F22
0x180004f57  mov     rbx, [rbp+47h+var_C0]
0x180004f5b  cmp     [rbp+47h+Block], r15
0x180004f5f  jz      short loc_180004F6A
0x180004f61  mov     rcx, [rbp+47h+Block]; Block
0x180004f65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004f6a  test    rbx, rbx
0x180004f6d  jz      short loc_180004F77
0x180004f6f  mov     rcx, rbx; Block
0x180004f72  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004f77  lea     r11, [rsp+100h+var_10]
0x180004f7f  mov     rbx, [r11+28h]
0x180004f83  mov     rsi, [r11+30h]
0x180004f87  mov     rsp, r11
0x180004f8a  pop     r15
0x180004f8c  pop     r14
0x180004f8e  pop     rbp
0x180004f8f  retn
```
