# CWdsDeviceControllerManager::ManagementRequest(ATL::CComObject<CWdsDeviceControllerRequest> *,CWdsDeviceControllerPacket *,CWdsDeviceControllerPacket *)

- ea: `0x180002bd8`
- end: `0x180003391`
- name: `?ManagementRequest@CWdsDeviceControllerManager@@AEAAKPEAV?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@PEAVCWdsDeviceControllerPacket@@1@Z`
- size: `1977`
- prototype: `__int64 __fastcall(CWdsDeviceControllerManager *this, CWdsDeviceControllerRequest *, CWdsDeviceControllerPacket *, CWdsDeviceControllerPacket *)`
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800026ac`
- `0x180003508`

## callees

- `0x180001370`
- `0x180002bd8`
- `0x1800051e8`
- `0x180005430`
- `0x18000563c`
- `0x180005818`
- `0x18000600c`
- `0x1800063b4`
- `0x1800068b8`
- `0x180006b84`
- `0x180007310`
- `0x18000a5e8`
- `0x18000dab4`
- `0x18000dbf4`
- `0x18000dcec`
- `0x18000dd30`
- `0x18000dde4`
- `0x18000defc`
- `0x18000df40`
- `0x18000dfa0`
- `0x18000e158`
- `0x18001284c`
- `0x180012910`
- `0x1800129e4`
- `0x180012ac8`
- `0x1800134f4`
- `0x180014d58`
- `0x1800150b8`

## string_xrefs

- `0x180002c82`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x180002d8f`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x180002eb3`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x180002eee`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x180003045`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x1800030cc`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x1800030fe`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::ManagementRequest(
        CWdsDeviceControllerManager *this,
        CWdsDeviceControllerRequest *a2,
        CWdsDeviceControllerPacket *a3,
        CWdsDeviceControllerPacket *a4)
{
  CWdsDeviceControllerRequest *v7; // r13
  unsigned int AvailableManagementControllers; // edi
  unsigned __int16 *v9; // r12
  int v10; // esi
  int v11; // eax
  unsigned int String; // eax
  const char *v13; // rdx
  void *v14; // rcx
  int v15; // esi
  const char *v16; // rdx
  unsigned int v17; // r9d
  CWdsMetadata *v18; // rcx
  const char *v19; // rdx
  const char *v20; // rdx
  const char *v21; // rdx
  const char *v22; // rdx
  const char *v23; // rdx
  const char *v24; // rdx
  unsigned int v25; // r15d
  unsigned int v26; // ebx
  const unsigned __int16 *v27; // r13
  const char *v28; // rdx
  const char *v29; // rdx
  const char *v30; // rdx
  const char *v31; // rdx
  unsigned int v32; // ebx
  CWdsMetadata *v33; // rcx
  const char *v34; // rdx
  const char *v35; // rdx
  const char *v36; // rdx
  unsigned int v37; // r9d
  const char *v38; // rdx
  const char *v39; // rdx
  unsigned int v40; // r9d
  unsigned int v41; // ecx
  const char *v42; // rdx
  unsigned int v43; // r9d
  const char *v44; // rdx
  const char *v45; // rdx
  const char *v46; // rdx
  const char *v47; // rdx
  unsigned int v48; // ebx
  const char *v50; // rdx
  const char *v51; // rdx
  bool v52; // zf
  const char *v53; // rdx
  const char *v54; // rdx
  const char *v55; // rdx
  const char *v56; // rdx
  unsigned __int16 *v57; // [rsp+40h] [rbp-79h] BYREF
  __int64 v58; // [rsp+48h] [rbp-71h] BYREF
  unsigned int v59[2]; // [rsp+50h] [rbp-69h]
  __int64 v60; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v61[2]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v62; // [rsp+78h] [rbp-41h]
  __int64 v63; // [rsp+80h] [rbp-39h]
  __int64 v64; // [rsp+88h] [rbp-31h]
  __int64 v65; // [rsp+90h] [rbp-29h]
  __int64 v66; // [rsp+98h] [rbp-21h]
  __int64 v67; // [rsp+A0h] [rbp-19h]
  int v68; // [rsp+B0h] [rbp-9h]
  CMRSWLock *v69; // [rsp+C0h] [rbp+7h] BYREF
  int v70; // [rsp+C8h] [rbp+Fh]
  struct CWdsDeviceControllerManager::CManagementEntry *v71; // [rsp+D0h] [rbp+17h] BYREF
  void *Block; // [rsp+120h] [rbp+67h] BYREF
  CWdsDeviceControllerRequest *v73; // [rsp+128h] [rbp+6Fh]
  unsigned int v74; // [rsp+130h] [rbp+77h] BYREF

  v73 = a2;
  v7 = a2;
  v70 = 0;
  AvailableManagementControllers = 0;
  v57 = 0;
  v9 = 0;
  v69 = (CWdsDeviceControllerManager *)((char *)this + 40);
  v10 = 2;
  v11 = *((_DWORD *)a3 + 6);
  if ( v11 != 3 )
  {
    if ( (unsigned int)(v11 - 4) <= 4 )
    {
      Block = 0;
      String = CControlPacket::GetString(a3, L"Controller", 0, 0xFFFFFFFF, (unsigned __int16 **)&Block);
      AvailableManagementControllers = String;
      if ( String == 2
        || ElValidateWin32(String, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x294u) )
      {
        v14 = Block;
      }
      else
      {
        v9 = (unsigned __int16 *)Block;
        v14 = 0;
      }
      if ( v14 )
        operator delete(v14);
      if ( AvailableManagementControllers == 2 )
      {
        v9 = 0;
        AvailableManagementControllers = 0;
      }
    }
    else
    {
      AvailableManagementControllers = 87;
      if ( ElValidateWin32(
             0x57u,
             (const char *)a2,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x2FDu) )
      {
        return AvailableManagementControllers;
      }
    }
  }
  CAutoReaderLock::Lock((CAutoReaderLock *)&v69);
  switch ( *((_DWORD *)a3 + 6) )
  {
    case 3:
      v58 = 0;
      *(_QWORD *)v59 = 0;
      AvailableManagementControllers = CWdsDeviceControllerManager::GetAvailableManagementControllers(this, &v58);
      if ( ElValidateWin32(
             AvailableManagementControllers,
             v55,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x318u) )
      {
        CDynArray<unsigned short *,CDeallocateString>::Clear(&v58);
        goto LABEL_63;
      }
      AvailableManagementControllers = CWdsDeviceControllerPacket::AddManagementControllerList(a4);
      v48 = ElValidateWin32(
              AvailableManagementControllers,
              v56,
              "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
              0x31Bu);
      CDynArray<unsigned short *,CDeallocateString>::Clear(&v58);
      goto LABEL_58;
    case 4:
      v60 = 0;
      v61[0] = 0;
      v62 = 0;
      v63 = 0;
      v65 = 0;
      v66 = 0;
      AvailableManagementControllers = CWdsDeviceControllerPacket::GetMetadata(
                                         a3,
                                         L"Metadata",
                                         (struct CWdsMetadata *)&v60);
      if ( !ElValidateWin32(
              AvailableManagementControllers,
              v53,
              "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
              0x325u) )
      {
        AvailableManagementControllers = CWdsDeviceControllerManager::AddDevice(
                                           this,
                                           v7,
                                           v9,
                                           (struct CWdsMetadata *)&v60,
                                           &v57);
        if ( !ElValidateWin32(
                AvailableManagementControllers,
                v54,
                "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                0x32Bu) )
        {
          AvailableManagementControllers = CWdsDeviceControllerPacket::AddDevice(a4, v57);
          v40 = 814;
          v41 = AvailableManagementControllers;
          goto LABEL_75;
        }
      }
LABEL_43:
      v18 = (CWdsMetadata *)&v60;
      goto LABEL_21;
    case 5:
      AvailableManagementControllers = CWdsDeviceControllerPacket::GetDevice(a3, &v57);
      if ( ElValidateWin32(
             AvailableManagementControllers,
             v50,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x336u) )
      {
        goto LABEL_63;
      }
      AvailableManagementControllers = CWdsDeviceControllerManager::DeleteDevice(this, v7, v9, v57);
      v52 = ElValidateWin32(
              AvailableManagementControllers,
              v51,
              "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
              0x33Bu) == 0;
      goto LABEL_77;
    case 6:
      v60 = 0;
      v61[0] = 0;
      v62 = 0;
      v63 = 0;
      v65 = 0;
      v66 = 0;
      AvailableManagementControllers = CWdsDeviceControllerPacket::GetDevice(a3, &v57);
      if ( ElValidateWin32(
             AvailableManagementControllers,
             v42,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x345u) )
      {
        goto LABEL_43;
      }
      LODWORD(Block) = 0;
      AvailableManagementControllers = CControlPacket::GetULONG(
                                         a3,
                                         L"DeviceModificationType",
                                         0,
                                         v43,
                                         (unsigned int *)&Block);
      if ( !ElValidateWin32(
              AvailableManagementControllers,
              v44,
              "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp",
              0x2DEu) )
      {
        if ( (_DWORD)Block == 1 )
        {
          v10 = 1;
        }
        else if ( (_DWORD)Block != 2 )
        {
          if ( (_DWORD)Block == 3 )
          {
            v10 = 3;
          }
          else
          {
            AvailableManagementControllers = 13;
            ElValidateWin32(0xDu, v45, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x2EDu);
          }
        }
      }
      if ( ElValidateWin32(
             AvailableManagementControllers,
             v45,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x348u) )
      {
        goto LABEL_43;
      }
      AvailableManagementControllers = CWdsDeviceControllerPacket::GetMetadata(
                                         a3,
                                         L"Metadata",
                                         (struct CWdsMetadata *)&v60);
      if ( ElValidateWin32(
             AvailableManagementControllers,
             v46,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x34Cu) )
      {
        goto LABEL_43;
      }
      AvailableManagementControllers = CWdsDeviceControllerManager::ModifyDevice(
                                         this,
                                         v7,
                                         v9,
                                         v57,
                                         v10,
                                         (struct CWdsMetadata *)&v60);
      v48 = ElValidateWin32(
              AvailableManagementControllers,
              v47,
              "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
              0x353u);
      CWdsMetadata::~CWdsMetadata((CWdsMetadata *)&v60);
LABEL_58:
      if ( v48 )
        goto LABEL_63;
LABEL_59:
      if ( v70 )
      {
        if ( !--v70 )
          CMRSWLock::ReaderRelease(v69);
      }
      CWdsDeviceControllerRequest::Shutdown(v7);
      goto LABEL_63;
    case 7:
      v60 = 0;
      v61[0] = 0;
      v62 = 0;
      v63 = 0;
      v65 = 0;
      v66 = 0;
      LODWORD(Block) = 0;
      AvailableManagementControllers = CWdsDeviceControllerPacket::GetDevice(a3, &v57);
      if ( !ElValidateWin32(
              AvailableManagementControllers,
              v34,
              "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
              0x35Du) )
      {
        AvailableManagementControllers = CWdsDeviceControllerManager::GetDevice(
                                           this,
                                           (struct CWdsMetadata *)&v60,
                                           (__int64)&Block);
        if ( !ElValidateWin32(
                AvailableManagementControllers,
                v35,
                "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                0x364u) )
        {
          AvailableManagementControllers = CWdsDeviceControllerPacket::AddMetadata(
                                             a4,
                                             L"Metadata",
                                             (const struct CWdsMetadata *)&v60);
          if ( !ElValidateWin32(
                  AvailableManagementControllers,
                  v36,
                  "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                  0x367u) )
          {
            AvailableManagementControllers = CControlPacket::AddULONG(a4, L"DeviceExists", 0, v37, (_DWORD)Block != 0);
            ElValidateWin32(
              AvailableManagementControllers,
              v38,
              "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp",
              0x1C7u);
            v40 = 874;
            v41 = AvailableManagementControllers;
LABEL_75:
            v32 = ElValidateWin32(
                    v41,
                    v39,
                    "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                    v40);
            v33 = (CWdsMetadata *)&v60;
LABEL_76:
            CWdsMetadata::~CWdsMetadata(v33);
            v52 = v32 == 0;
LABEL_77:
            if ( !v52 )
              goto LABEL_63;
            goto LABEL_59;
          }
        }
      }
      goto LABEL_43;
  }
  if ( *((_DWORD *)a3 + 6) != 8 )
    goto LABEL_59;
  v15 = 0;
  v74 = 0;
  v61[0] = 0;
  v61[1] = 0;
  v63 = 0;
  v64 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v60 = 0;
  v58 = 0;
  *(_QWORD *)v59 = 0;
  v71 = 0;
  AvailableManagementControllers = CWdsDeviceControllerPacket::GetDeviceListCount(a3, &v74);
  if ( !ElValidateWin32(
          AvailableManagementControllers,
          v16,
          "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
          0x377u) )
  {
    LODWORD(Block) = 0;
    AvailableManagementControllers = CControlPacket::GetULONG(a3, L"DeviceList.Offset", 0, v17, (unsigned int *)&Block);
    if ( !ElValidateWin32(
            AvailableManagementControllers,
            v19,
            "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp",
            0x35Eu) )
      v15 = (int)Block;
    if ( !ElValidateWin32(
            AvailableManagementControllers,
            v20,
            "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
            0x37Au) )
    {
      AvailableManagementControllers = CWdsDeviceControllerPacket::GetDeviceQuery(a3, (struct CWdsDeviceQuery *)&v60);
      if ( !ElValidateWin32(
              AvailableManagementControllers,
              v21,
              "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
              0x37Du) )
      {
        AvailableManagementControllers = CWdsDeviceControllerManager::GetManagementEntry(this, v9, &v71);
        if ( !ElValidateWin32(
                AvailableManagementControllers,
                v22,
                "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                0x381u) )
        {
          AvailableManagementControllers = CWdsDeviceControllerManager::QueryDevices(
                                             this,
                                             v7,
                                             v9,
                                             (__int64)&v58,
                                             v74,
                                             v15);
          if ( !ElValidateWin32(
                  AvailableManagementControllers,
                  v23,
                  "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                  0x389u) )
          {
            v25 = v59[1];
            v26 = 0;
            if ( v59[1] )
            {
              while ( 1 )
              {
                v27 = 0;
                AvailableManagementControllers = 0;
                if ( v26 < v25 )
                  v27 = *(const unsigned __int16 **)(v58 + 8LL * v26);
                else
                  AvailableManagementControllers = 1413;
                if ( ElValidateWin32(
                       AvailableManagementControllers,
                       v24,
                       "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                       0x392u) )
                {
                  goto LABEL_20;
                }
                if ( !*((_DWORD *)a4 + 10)
                  || *((_DWORD *)a4 + 8) < *((_DWORD *)a4 + 9)
                  || (AvailableManagementControllers = 5023,
                      !ElValidateWin32(
                         0x139Fu,
                         v28,
                         "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp",
                         0x140u)) )
                {
                  AvailableManagementControllers = CControlPacket::AddString(
                                                     a4,
                                                     L"DeviceList.Identifier",
                                                     0,
                                                     *((_DWORD *)a4 + 8),
                                                     v27);
                  if ( !ElValidateWin32(
                          AvailableManagementControllers,
                          v30,
                          "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp",
                          0x147u) )
                    ++*((_DWORD *)a4 + 8);
                }
                if ( ElValidateWin32(
                       AvailableManagementControllers,
                       v29,
                       "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                       0x395u) )
                {
                  goto LABEL_20;
                }
                if ( ++v26 >= v25 )
                {
                  v7 = v73;
                  break;
                }
              }
            }
            AvailableManagementControllers = CWdsDeviceControllerPacket::AddDeviceListCount(a4, v25);
            v32 = ElValidateWin32(
                    AvailableManagementControllers,
                    v31,
                    "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                    0x399u);
            CDynArray<unsigned short *,CDeallocateString>::Clear(&v58);
            CWdsDeviceQuery::Shutdown((CWdsDeviceQuery *)&v60);
            v33 = (CWdsMetadata *)v61;
            goto LABEL_76;
          }
        }
      }
    }
  }
LABEL_20:
  CDynArray<unsigned short *,CDeallocateString>::Clear(&v58);
  CWdsDeviceQuery::Shutdown((CWdsDeviceQuery *)&v60);
  v18 = (CWdsMetadata *)v61;
LABEL_21:
  CWdsMetadata::~CWdsMetadata(v18);
LABEL_63:
  if ( v9 )
    operator delete(v9);
  if ( v57 )
    operator delete(v57);
  if ( v70 == 1 )
    CMRSWLock::ReaderRelease(v69);
  return AvailableManagementControllers;
}

```

## disassembly

```asm
0x180002bd8  mov     [rsp-8+arg_18], rbx
0x180002bdd  mov     [rsp-8+arg_8], rdx
0x180002be2  push    rbp
0x180002be3  push    rsi
0x180002be4  push    rdi
0x180002be5  push    r12
0x180002be7  push    r13
0x180002be9  push    r14
0x180002beb  push    r15
0x180002bed  lea     rbp, [rsp-27h]
0x180002bf2  sub     rsp, 0E0h
0x180002bf9  mov     r15, rcx
0x180002bfc  mov     r14, r9
0x180002bff  xor     ecx, ecx
0x180002c01  mov     rbx, r8
0x180002c04  mov     r13, rdx
0x180002c07  mov     [rbp+57h+var_48], ecx
0x180002c0a  mov     edi, ecx
0x180002c0c  mov     [rbp+57h+var_D0], rcx
0x180002c10  lea     rax, [r15+28h]
0x180002c14  mov     r12d, ecx
0x180002c17  mov     [rbp+57h+var_50], rax
0x180002c1b  lea     esi, [rcx+2]
0x180002c1e  mov     eax, [r8+18h]
0x180002c22  cmp     eax, 3
0x180002c25  jz      loc_180002CB3
0x180002c2b  add     eax, 0FFFFFFFCh
0x180002c2e  cmp     eax, 4
0x180002c31  jbe     short loc_180002C53
0x180002c33  lea     edi, [rcx+57h]
0x180002c36  mov     r9d, 2FDh; unsigned int
0x180002c3c  mov     ecx, edi; unsigned int
0x180002c3e  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180002c45  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002c4a  test    eax, eax
0x180002c4c  jz      short loc_180002CB3
0x180002c4e  jmp     loc_1800031F6
0x180002c53  mov     [rbp+57h+Block], rcx
0x180002c57  lea     rax, [rbp+57h+Block]
0x180002c5b  mov     rcx, rbx; this
0x180002c5e  mov     [rsp+110h+var_F0], rax; unsigned __int16 **
0x180002c63  or      r9d, 0FFFFFFFFh; unsigned int
0x180002c67  lea     rdx, aController; "Controller"
0x180002c6e  xor     r8d, r8d; unsigned __int16 *
0x180002c71  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x180002c76  mov     edi, eax
0x180002c78  cmp     eax, esi
0x180002c7a  jz      short loc_180002C9C
0x180002c7c  mov     r9d, 294h; unsigned int
0x180002c82  lea     r8, aBaseEcoWdsLibM_5; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180002c89  mov     ecx, eax; unsigned int
0x180002c8b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002c90  test    eax, eax
0x180002c92  jnz     short loc_180002C9C
0x180002c94  mov     r12, [rbp+57h+Block]
0x180002c98  xor     ecx, ecx
0x180002c9a  jmp     short loc_180002CA0
0x180002c9c  mov     rcx, [rbp+57h+Block]; Block
0x180002ca0  test    rcx, rcx
0x180002ca3  jz      short loc_180002CAA
0x180002ca5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002caa  cmp     edi, esi
0x180002cac  jnz     short loc_180002CB3
0x180002cae  xor     r12d, r12d
0x180002cb1  xor     edi, edi
0x180002cb3  lea     rcx, [rbp+57h+var_50]; this
0x180002cb7  call    ?Lock@CAutoReaderLock@@QEAAXXZ; CAutoReaderLock::Lock(void)
0x180002cbc  mov     ecx, [rbx+18h]
0x180002cbf  sub     ecx, 3
0x180002cc2  jz      loc_180003321
0x180002cc8  sub     ecx, 1
0x180002ccb  jz      loc_180003268
0x180002cd1  sub     ecx, 1
0x180002cd4  jz      loc_180003213
0x180002cda  sub     ecx, 1
0x180002cdd  jz      loc_180003062
0x180002ce3  sub     ecx, 1
0x180002ce6  jz      loc_180002F6F
0x180002cec  cmp     ecx, 1
0x180002cef  jnz     loc_1800031A9
0x180002cf5  xor     esi, esi
0x180002cf7  lea     rdx, [rbp+57h+arg_10]; unsigned int *
0x180002cfb  mov     rcx, rbx; this
0x180002cfe  mov     [rbp+57h+arg_10], esi
0x180002d01  mov     [rbp+57h+var_A8], rsi
0x180002d05  mov     [rbp+57h+var_A0], rsi
0x180002d09  mov     [rbp+57h+var_90], rsi
0x180002d0d  mov     [rbp+57h+var_88], rsi
0x180002d11  mov     [rbp+57h+var_78], rsi
0x180002d15  mov     [rbp+57h+var_70], rsi
0x180002d19  mov     [rbp+57h+var_60], esi
0x180002d1c  mov     [rbp+57h+var_B0], rsi
0x180002d20  mov     [rbp+57h+var_C8], rsi
0x180002d24  mov     qword ptr [rbp+57h+var_C0], rsi
0x180002d28  mov     [rbp+57h+var_40], rsi
0x180002d2c  call    ?GetDeviceListCount@CWdsDeviceControllerPacket@@QEAAKPEAK@Z; CWdsDeviceControllerPacket::GetDeviceListCount(ulong *)
0x180002d31  mov     r9d, 377h; unsigned int
0x180002d37  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180002d3e  mov     ecx, eax; unsigned int
0x180002d40  mov     edi, eax
0x180002d42  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002d47  test    eax, eax
0x180002d49  jz      short loc_180002D6B
0x180002d4b  lea     rcx, [rbp+57h+var_C8]
0x180002d4f  call    ?Clear@?$CDynArray@PEAGVCDeallocateString@@@@QEAAXXZ; CDynArray<ushort *,CDeallocateString>::Clear(void)
0x180002d54  lea     rcx, [rbp+57h+var_B0]; this
0x180002d58  call    ?Shutdown@CWdsDeviceQuery@@QEAAXXZ; CWdsDeviceQuery::Shutdown(void)
0x180002d5d  lea     rcx, [rbp+57h+var_A8]; this
0x180002d61  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180002d66  jmp     loc_1800031C6
0x180002d6b  lea     rax, [rbp+57h+Block]
0x180002d6f  mov     dword ptr [rbp+57h+Block], esi
0x180002d72  xor     r8d, r8d; unsigned __int16 *
0x180002d75  mov     [rsp+110h+var_F0], rax; unsigned int *
0x180002d7a  lea     rdx, aDevicelistOffs; "DeviceList.Offset"
0x180002d81  mov     rcx, rbx; this
0x180002d84  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x180002d89  mov     r9d, 35Eh; unsigned int
0x180002d8f  lea     r8, aBaseEcoWdsLibM_5; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180002d96  mov     ecx, eax; unsigned int
0x180002d98  mov     edi, eax
0x180002d9a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002d9f  test    eax, eax
0x180002da1  cmovz   esi, dword ptr [rbp+57h+Block]
0x180002da5  mov     r9d, 37Ah; unsigned int
0x180002dab  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180002db2  mov     ecx, edi; unsigned int
0x180002db4  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002db9  test    eax, eax
0x180002dbb  jnz     short loc_180002D4B
0x180002dbd  lea     rdx, [rbp+57h+var_B0]; struct CWdsDeviceQuery *
0x180002dc1  mov     rcx, rbx; this
0x180002dc4  call    ?GetDeviceQuery@CWdsDeviceControllerPacket@@QEAAKPEAUCWdsDeviceQuery@@@Z; CWdsDeviceControllerPacket::GetDeviceQuery(CWdsDeviceQuery *)
0x180002dc9  lea     rbx, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180002dd0  mov     r9d, 37Dh; unsigned int
0x180002dd6  mov     r8, rbx; char *
0x180002dd9  mov     ecx, eax; unsigned int
0x180002ddb  mov     edi, eax
0x180002ddd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002de2  test    eax, eax
0x180002de4  jnz     loc_180002D4B
0x180002dea  lea     r8, [rbp+57h+var_40]; struct CWdsDeviceControllerManager::CManagementEntry **
0x180002dee  mov     rdx, r12; unsigned __int16 *
0x180002df1  mov     rcx, r15; this
0x180002df4  call    ?GetManagementEntry@CWdsDeviceControllerManager@@AEAAKPEBGPEAPEAUCManagementEntry@1@@Z; CWdsDeviceControllerManager::GetManagementEntry(ushort const *,CWdsDeviceControllerManager::CManagementEntry * *)
0x180002df9  mov     r9d, 381h; unsigned int
0x180002dff  mov     r8, rbx; char *
0x180002e02  mov     ecx, eax; unsigned int
0x180002e04  mov     edi, eax
0x180002e06  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002e0b  test    eax, eax
0x180002e0d  jnz     loc_180002D4B
0x180002e13  mov     eax, [rbp+57h+arg_10]
0x180002e16  lea     r9, [rbp+57h+var_B0]
0x180002e1a  mov     [rsp+110h+var_E0], esi; int
0x180002e1e  mov     r8, r12; unsigned __int16 *
0x180002e21  mov     dword ptr [rsp+110h+var_E8], eax; int
0x180002e25  mov     rdx, r13; CWdsDeviceControllerRequest *
0x180002e28  lea     rax, [rbp+57h+var_C8]
0x180002e2c  mov     rcx, r15; this
0x180002e2f  mov     [rsp+110h+var_F0], rax; __int64
0x180002e34  call    ?QueryDevices@CWdsDeviceControllerManager@@QEAAKPEAV?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@PEBGPEAUCWdsDeviceQuery@@PEAV?$CDynArray@PEAGVCDeallocateString@@@@KK@Z; CWdsDeviceControllerManager::QueryDevices(ATL::CComObject<CWdsDeviceControllerRequest> *,ushort const *,CWdsDeviceQuery *,CDynArray<ushort *,CDeallocateString> *,ulong,ulong)
0x180002e39  mov     r9d, 389h; unsigned int
0x180002e3f  mov     r8, rbx; char *
0x180002e42  mov     ecx, eax; unsigned int
0x180002e44  mov     edi, eax
0x180002e46  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002e4b  xor     esi, esi
0x180002e4d  test    eax, eax
0x180002e4f  jnz     loc_180002D4B
0x180002e55  mov     r15d, [rbp+57h+var_C0+4]
0x180002e59  mov     ebx, esi
0x180002e5b  test    r15d, r15d
0x180002e5e  jz      loc_180002F31
0x180002e64  lea     esi, [rax+1]
0x180002e67  xor     r13d, r13d
0x180002e6a  xor     edi, edi
0x180002e6c  cmp     ebx, r15d
0x180002e6f  jb      short loc_180002E78
0x180002e71  mov     edi, 585h
0x180002e76  jmp     short loc_180002E82
0x180002e78  mov     rcx, [rbp+57h+var_C8]
0x180002e7c  mov     eax, ebx
0x180002e7e  mov     r13, [rcx+rax*8]
0x180002e82  mov     r9d, 392h; unsigned int
0x180002e88  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180002e8f  mov     ecx, edi; unsigned int
0x180002e91  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002e96  test    eax, eax
0x180002e98  jnz     loc_180002D4B
0x180002e9e  cmp     [r14+28h], eax
0x180002ea2  jz      short loc_180002ECD
0x180002ea4  mov     eax, [r14+24h]
0x180002ea8  cmp     [r14+20h], eax
0x180002eac  jb      short loc_180002ECD
0x180002eae  mov     eax, 139Fh
0x180002eb3  lea     r8, aBaseEcoWdsLibM_5; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180002eba  mov     ecx, eax; unsigned int
0x180002ebc  mov     r9d, 140h; unsigned int
0x180002ec2  mov     edi, eax
0x180002ec4  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002ec9  test    eax, eax
0x180002ecb  jnz     short loc_180002F06
0x180002ecd  mov     r9d, [r14+20h]; unsigned int
0x180002ed1  lea     rdx, aDevicelistIden; "DeviceList.Identifier"
0x180002ed8  xor     r8d, r8d; unsigned __int16 *
0x180002edb  mov     [rsp+110h+var_F0], r13; unsigned __int16 *
0x180002ee0  mov     rcx, r14; this
0x180002ee3  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x180002ee8  mov     r9d, 147h; unsigned int
0x180002eee  lea     r8, aBaseEcoWdsLibM_5; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180002ef5  mov     ecx, eax; unsigned int
0x180002ef7  mov     edi, eax
0x180002ef9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002efe  test    eax, eax
0x180002f00  jnz     short loc_180002F06
0x180002f02  add     [r14+20h], esi
0x180002f06  mov     r9d, 395h; unsigned int
0x180002f0c  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180002f13  mov     ecx, edi; unsigned int
0x180002f15  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002f1a  test    eax, eax
0x180002f1c  jnz     loc_180002D4B
0x180002f22  add     ebx, esi
0x180002f24  cmp     ebx, r15d
0x180002f27  jb      loc_180002E67
0x180002f2d  mov     r13, [rbp+57h+arg_8]
0x180002f31  mov     edx, r15d; unsigned int
0x180002f34  mov     rcx, r14; this
0x180002f37  call    ?AddDeviceListCount@CWdsDeviceControllerPacket@@QEAAKK@Z; CWdsDeviceControllerPacket::AddDeviceListCount(ulong)
0x180002f3c  mov     r9d, 399h; unsigned int
0x180002f42  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180002f49  mov     ecx, eax; unsigned int
0x180002f4b  mov     edi, eax
0x180002f4d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002f52  lea     rcx, [rbp+57h+var_C8]
0x180002f56  mov     ebx, eax
0x180002f58  call    ?Clear@?$CDynArray@PEAGVCDeallocateString@@@@QEAAXXZ; CDynArray<ushort *,CDeallocateString>::Clear(void)
0x180002f5d  lea     rcx, [rbp+57h+var_B0]; this
0x180002f61  call    ?Shutdown@CWdsDeviceQuery@@QEAAXXZ; CWdsDeviceQuery::Shutdown(void)
0x180002f66  lea     rcx, [rbp+57h+var_A8]
0x180002f6a  jmp     loc_18000330F
0x180002f6f  xor     esi, esi
0x180002f71  lea     rdx, [rbp+57h+var_D0]; unsigned __int16 **
0x180002f75  mov     rcx, rbx; this
0x180002f78  mov     [rbp+57h+var_B0], rsi
0x180002f7c  mov     [rbp+57h+var_A8], rsi
0x180002f80  mov     [rbp+57h+var_98], rsi
0x180002f84  mov     [rbp+57h+var_90], rsi
0x180002f88  mov     [rbp+57h+var_80], rsi
0x180002f8c  mov     [rbp+57h+var_78], rsi
0x180002f90  mov     dword ptr [rbp+57h+Block], esi
0x180002f93  call    ?GetDevice@CWdsDeviceControllerPacket@@QEAAKPEAPEAG@Z; CWdsDeviceControllerPacket::GetDevice(ushort * *)
0x180002f98  lea     rbx, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180002f9f  mov     r9d, 35Dh; unsigned int
0x180002fa5  mov     r8, rbx; char *
0x180002fa8  mov     ecx, eax; unsigned int
0x180002faa  mov     edi, eax
0x180002fac  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002fb1  test    eax, eax
0x180002fb3  jz      short loc_180002FBE
0x180002fb5  lea     rcx, [rbp+57h+var_B0]
0x180002fb9  jmp     loc_180002D61
0x180002fbe  mov     r9, [rbp+57h+var_D0]
0x180002fc2  lea     rax, [rbp+57h+Block]
0x180002fc6  mov     [rsp+110h+var_E8], rax; __int64
0x180002fcb  mov     r8, r12
0x180002fce  lea     rax, [rbp+57h+var_B0]
0x180002fd2  mov     rdx, r13
0x180002fd5  mov     rcx, r15; this
0x180002fd8  mov     [rsp+110h+var_F0], rax; struct CWdsMetadata *
0x180002fdd  call    ?GetDevice@CWdsDeviceControllerManager@@QEAAKPEAV?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@PEBG1PEAVCWdsMetadata@@PEAH@Z; CWdsDeviceControllerManager::GetDevice(ATL::CComObject<CWdsDeviceControllerRequest> *,ushort const *,ushort const *,CWdsMetadata *,int *)
0x180002fe2  mov     r9d, 364h; unsigned int
0x180002fe8  mov     r8, rbx; char *
0x180002feb  mov     ecx, eax; unsigned int
0x180002fed  mov     edi, eax
0x180002fef  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002ff4  test    eax, eax
0x180002ff6  jnz     short loc_180002FB5
0x180002ff8  lea     r8, [rbp+57h+var_B0]; struct CWdsMetadata *
0x180002ffc  mov     rcx, r14; this
0x180002fff  lea     rdx, aMetadata; "Metadata"
0x180003006  call    ?AddMetadata@CWdsDeviceControllerPacket@@QEAAKPEBGPEBVCWdsMetadata@@@Z; CWdsDeviceControllerPacket::AddMetadata(ushort const *,CWdsMetadata const *)
0x18000300b  mov     r9d, 367h; unsigned int
0x180003011  mov     r8, rbx; char *
0x180003014  mov     ecx, eax; unsigned int
0x180003016  mov     edi, eax
0x180003018  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000301d  test    eax, eax
0x18000301f  jnz     short loc_180002FB5
0x180003021  cmp     dword ptr [rbp+57h+Block], esi
0x180003024  lea     rdx, aDeviceexists; "DeviceExists"
0x18000302b  mov     eax, esi
0x18000302d  mov     rcx, r14; this
0x180003030  setnz   al
0x180003033  xor     r8d, r8d; unsigned __int16 *
0x180003036  mov     dword ptr [rsp+110h+var_F0], eax; unsigned int
0x18000303a  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x18000303f  mov     r9d, 1C7h; unsigned int
0x180003045  lea     r8, aBaseEcoWdsLibM_5; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
  ... truncated ...
```
