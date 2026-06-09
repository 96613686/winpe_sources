# CWdsDeviceControllerManager::GetDevice(ATL::CComObject<CWdsDeviceControllerRequest> *,ushort const *,ushort const *,CWdsMetadata *,int *)

- ea: `0x18000600c`
- end: `0x1800062e7`
- name: `?GetDevice@CWdsDeviceControllerManager@@QEAAKPEAV?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@PEBG1PEAVCWdsMetadata@@PEAH@Z`
- size: `731`
- prototype: `__int64 __usercall@<rax>(CWdsDeviceControllerManager *this@<rcx>, struct CWdsMetadata *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180002bd8`

## callees

- `0x1800013d0`
- `0x180004f98`
- `0x18000600c`
- `0x1800068b8`
- `0x180007310`
- `0x18000a5e8`
- `0x18000e504`
- `0x18000e65c`
- `0x1800134f4`
- `0x18001381c`
- `0x180014d58`
- `0x180014ee0`
- `0x180015cc0`

## import_xrefs

- `WDSSRV!WdsPerfCounterAdd` at `0x180006275`
- `WDSSRV!WdsPerfCounterAdd` at `0x180006280`
- `WDSSRV!WdsPerfCounterAdd` at `0x180006275`
- `WDSSRV!WdsPerfCounterAdd` at `0x180006280`
- `OLEAUT32!__imp_SysFreeString` at `0x180006290`
- `OLEAUT32!__imp_SysFreeString` at `0x180006290`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::GetDevice(
        CWdsDeviceControllerManager *this,
        CWdsDeviceControllerRequest *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct CWdsMetadata *a5,
        _DWORD *a6)
{
  struct CWdsComMetadataBuilder *v10; // rsi
  int ManagementEntry; // ebx
  const char *v12; // rdx
  const char *v13; // rdx
  const char *v14; // rdx
  CMRSWLock *v15; // r13
  int v16; // eax
  CWdsDeviceControllerManager *v17; // rcx
  int v18; // edi
  struct _RTL_CRITICAL_SECTION *v19; // r14
  const char *v20; // rdx
  const char *v21; // rdx
  const char *v22; // rdx
  CWdsComMetadataBuilder *v24; // [rsp+48h] [rbp-59h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-51h] BYREF
  CMRSWLock *v26; // [rsp+58h] [rbp-49h] BYREF
  int v27; // [rsp+60h] [rbp-41h]
  CMRSWLock *v28; // [rsp+68h] [rbp-39h] BYREF
  int v29; // [rsp+70h] [rbp-31h]
  _QWORD v30[10]; // [rsp+78h] [rbp-29h] BYREF
  __int16 v31; // [rsp+F8h] [rbp+57h] BYREF
  CWdsDeviceControllerRequest *v32; // [rsp+100h] [rbp+5Fh]

  v32 = a2;
  v28 = (CWdsDeviceControllerManager *)((char *)this + 40);
  v29 = 0;
  CAutoReaderLock::Lock((CAutoReaderLock *)&v28);
  v24 = 0;
  v26 = 0;
  v31 = 0;
  v10 = 0;
  v30[0] = 0;
  v30[1] = 0;
  v30[3] = 0;
  v30[4] = 0;
  v30[6] = 0;
  v30[7] = 0;
  bstrString = 0;
  ManagementEntry = CWdsDeviceControllerManager::GetManagementEntry(this, a3, &v26);
  if ( !ElValidateWin32(
          ManagementEntry,
          v12,
          "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
          0xA41u) )
  {
    ManagementEntry = SysAllocStringHr(a4, &bstrString);
    if ( (int)ElValidateHr(
                ManagementEntry,
                v13,
                "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                0xA44u) >= 0 )
    {
      ManagementEntry = CWdsComMetadataBuilder::CreateInstance((struct CWdsMetadata *)v30, &v24);
      if ( (int)ElValidateHr(
                  ManagementEntry,
                  v14,
                  "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                  0xA48u) >= 0 )
      {
        v15 = v26;
        v27 = 0;
        v26 = (CMRSWLock *)(*((_QWORD *)v26 + 1) + 24LL);
        CAutoReaderLock::Lock((CAutoReaderLock *)&v26);
        v10 = v24;
        v16 = (*(__int64 (__fastcall **)(_QWORD, CWdsDeviceControllerRequest *, BSTR, CWdsComMetadataBuilder *, __int16 *))(**(_QWORD **)v15 + 40LL))(
                *(_QWORD *)v15,
                a2,
                bstrString,
                v24,
                &v31);
        v18 = v27;
        ManagementEntry = v16;
        v19 = (struct _RTL_CRITICAL_SECTION *)v26;
        if ( v27 )
        {
          v18 = v27 - 1;
          if ( v27 == 1 )
            CMRSWLock::ReaderRelease((struct _RTL_CRITICAL_SECTION *)v26);
        }
        CWdsDeviceControllerManager::LogDeviceManagement(
          v17,
          7u,
          *(const unsigned __int16 **)(*((_QWORD *)v15 + 1) + 8LL),
          a4,
          v10,
          0,
          ManagementEntry);
        if ( (int)ElValidateHr(
                    ManagementEntry,
                    v20,
                    "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                    0xA58u) < 0
          || (ManagementEntry = CWdsDeviceControllerRequest::CleanupImpersonation(v32),
              (int)ElValidateHr(
                     ManagementEntry,
                     v21,
                     "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                     0xA5Bu) < 0) )
        {
          if ( ManagementEntry < 0 && (ManagementEntry & 0x1FFF0000) == 0x70000 )
            ManagementEntry = (unsigned __int16)ManagementEntry;
          if ( v18 == 1 )
            CMRSWLock::ReaderRelease(v19);
        }
        else
        {
          if ( v18 == 1 )
            CMRSWLock::ReaderRelease(v19);
          ManagementEntry = CWdsComMetadataBuilder::GetMetadata(v10, a5);
          if ( !ElValidateWin32(
                  ManagementEntry,
                  v22,
                  "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                  0xA5Fu) )
          {
            *a6 = v31 == -1;
            WdsPerfCounterAdd(60);
            WdsPerfCounterAdd(62);
          }
        }
      }
      else
      {
        if ( ManagementEntry < 0 && (ManagementEntry & 0x1FFF0000) == 0x70000 )
          ManagementEntry = (unsigned __int16)ManagementEntry;
        v10 = v24;
      }
    }
    else if ( ManagementEntry < 0 && (ManagementEntry & 0x1FFF0000) == 0x70000 )
    {
      ManagementEntry = (unsigned __int16)ManagementEntry;
    }
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v10 )
      (*(void (__fastcall **)(struct CWdsComMetadataBuilder *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v30);
  if ( v29 == 1 )
    CMRSWLock::ReaderRelease((struct _RTL_CRITICAL_SECTION *)v28);
  return (unsigned int)ManagementEntry;
}

```

## disassembly

```asm
0x18000600c  mov     rax, rsp
0x18000600f  mov     [rax+18h], rbx
0x180006013  mov     [rax+20h], rsi
0x180006017  mov     [rax+10h], rdx
0x18000601b  push    rbp
0x18000601c  push    rdi
0x18000601d  push    r12
0x18000601f  push    r13
0x180006021  push    r14
0x180006023  lea     rbp, [rax-4Fh]
0x180006027  sub     rsp, 0C0h
0x18000602e  lea     rax, [rcx+28h]
0x180006032  mov     rbx, rcx
0x180006035  xor     r13d, r13d
0x180006038  mov     [rbp+47h+var_80], rax
0x18000603c  lea     rcx, [rbp+47h+var_80]; this
0x180006040  mov     [rbp+47h+var_78], r13d
0x180006044  mov     r12, r9
0x180006047  mov     rdi, r8
0x18000604a  mov     r14, rdx
0x18000604d  call    ?Lock@CAutoReaderLock@@QEAAXXZ; CAutoReaderLock::Lock(void)
0x180006052  lea     r8, [rbp+47h+var_90]; struct CWdsDeviceControllerManager::CManagementEntry **
0x180006056  mov     [rbp+47h+var_A0], r13
0x18000605a  mov     rdx, rdi; unsigned __int16 *
0x18000605d  mov     [rbp+47h+var_90], r13
0x180006061  mov     rcx, rbx; this
0x180006064  mov     [rbp+47h+arg_0], r13w
0x180006069  mov     esi, r13d
0x18000606c  mov     [rbp+47h+var_70], r13
0x180006070  mov     [rbp+47h+var_68], r13
0x180006074  mov     [rbp+47h+var_58], r13
0x180006078  mov     [rbp+47h+var_50], r13
0x18000607c  mov     [rbp+47h+var_40], r13
0x180006080  mov     [rbp+47h+var_38], r13
0x180006084  mov     [rbp+47h+bstrString], r13
0x180006088  call    ?GetManagementEntry@CWdsDeviceControllerManager@@AEAAKPEBGPEAPEAUCManagementEntry@1@@Z; CWdsDeviceControllerManager::GetManagementEntry(ushort const *,CWdsDeviceControllerManager::CManagementEntry * *)
0x18000608d  lea     rdi, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180006094  mov     r9d, 0A41h; unsigned int
0x18000609a  mov     r8, rdi; char *
0x18000609d  mov     ecx, eax; unsigned int
0x18000609f  mov     ebx, eax
0x1800060a1  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800060a6  test    eax, eax
0x1800060a8  jnz     loc_1800062AB
0x1800060ae  lea     rdx, [rbp+47h+bstrString]; unsigned __int16 **
0x1800060b2  mov     rcx, r12; unsigned __int16 *
0x1800060b5  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x1800060ba  mov     r9d, 0A44h; unsigned int
0x1800060c0  mov     r8, rdi; char *
0x1800060c3  mov     ecx, eax; int
0x1800060c5  mov     ebx, eax
0x1800060c7  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800060cc  test    eax, eax
0x1800060ce  jns     short loc_1800060F2
0x1800060d0  test    ebx, ebx
0x1800060d2  jns     loc_180006286
0x1800060d8  mov     eax, ebx
0x1800060da  and     eax, 1FFF0000h
0x1800060df  cmp     eax, 70000h
0x1800060e4  jnz     loc_180006286
0x1800060ea  movzx   ebx, bx
0x1800060ed  jmp     loc_180006286
0x1800060f2  lea     rdx, [rbp+47h+var_A0]
0x1800060f6  lea     rcx, [rbp+47h+var_70]; struct CWdsMetadata *
0x1800060fa  call    ?CreateInstance@CWdsComMetadataBuilder@@SAJPEBVCWdsMetadata@@PEAPEAV?$CComObject@VCWdsComMetadataBuilder@@@ATL@@@Z; CWdsComMetadataBuilder::CreateInstance(CWdsMetadata const *,ATL::CComObject<CWdsComMetadataBuilder> * *)
0x1800060ff  mov     r9d, 0A48h; unsigned int
0x180006105  mov     r8, rdi; char *
0x180006108  mov     ecx, eax; int
0x18000610a  mov     ebx, eax
0x18000610c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180006111  test    eax, eax
0x180006113  jns     short loc_180006133
0x180006115  test    ebx, ebx
0x180006117  jns     short loc_18000612A
0x180006119  mov     eax, ebx
0x18000611b  and     eax, 1FFF0000h
0x180006120  cmp     eax, 70000h
0x180006125  jnz     short loc_18000612A
0x180006127  movzx   ebx, bx
0x18000612a  mov     rsi, [rbp+47h+var_A0]
0x18000612e  jmp     loc_180006286
0x180006133  mov     r13, [rbp+47h+var_90]
0x180006137  lea     rcx, [rbp+47h+var_90]; this
0x18000613b  and     [rbp+47h+var_88], esi
0x18000613e  mov     rax, [r13+8]
0x180006142  add     rax, 18h
0x180006146  mov     [rbp+47h+var_90], rax
0x18000614a  call    ?Lock@CAutoReaderLock@@QEAAXXZ; CAutoReaderLock::Lock(void)
0x18000614f  mov     rcx, [r13+0]
0x180006153  lea     rdx, [rbp+47h+arg_0]
0x180006157  mov     rsi, [rbp+47h+var_A0]
0x18000615b  mov     r8, [rbp+47h+bstrString]
0x18000615f  mov     r9, rsi
0x180006162  mov     [rsp+0E0h+var_C0], rdx
0x180006167  mov     rdx, r14
0x18000616a  mov     rax, [rcx]
0x18000616d  mov     rax, [rax+28h]
0x180006171  call    cs:__guard_dispatch_icall_fptr
0x180006177  mov     edi, [rbp+47h+var_88]
0x18000617a  mov     ebx, eax
0x18000617c  mov     r14, [rbp+47h+var_90]
0x180006180  test    edi, edi
0x180006182  jz      short loc_180006191
0x180006184  add     edi, 0FFFFFFFFh
0x180006187  jnz     short loc_180006191
0x180006189  mov     rcx, r14; this
0x18000618c  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180006191  mov     r8, [r13+8]
0x180006195  mov     r9, r12; unsigned __int16 *
0x180006198  xor     r13d, r13d
0x18000619b  mov     [rsp+0E0h+var_B0], ebx; int
0x18000619f  mov     [rsp+0E0h+var_B8], r13d; unsigned int
0x1800061a4  mov     [rsp+0E0h+var_C0], rsi; struct CWdsComMetadataBuilder *
0x1800061a9  mov     r8, [r8+8]; unsigned __int16 *
0x1800061ad  lea     edx, [r13+7]; unsigned int
0x1800061b1  call    ?LogDeviceManagement@CWdsDeviceControllerManager@@AEAAXKPEBG0PEAVCWdsComMetadataBuilder@@KJ@Z; CWdsDeviceControllerManager::LogDeviceManagement(ulong,ushort const *,ushort const *,CWdsComMetadataBuilder *,ulong,long)
0x1800061b6  lea     r12, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800061bd  mov     r9d, 0A58h; unsigned int
0x1800061c3  mov     r8, r12; char *
0x1800061c6  mov     ecx, ebx; int
0x1800061c8  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800061cd  test    eax, eax
0x1800061cf  jns     short loc_180006206
0x1800061d1  test    ebx, ebx
0x1800061d3  jns     short loc_1800061E6
0x1800061d5  mov     eax, ebx
0x1800061d7  and     eax, 1FFF0000h
0x1800061dc  cmp     eax, 70000h
0x1800061e1  jnz     short loc_1800061E6
0x1800061e3  movzx   ebx, bx
0x1800061e6  test    edi, edi
0x1800061e8  jz      loc_180006286
0x1800061ee  lea     eax, [rdi-1]
0x1800061f1  test    eax, eax
0x1800061f3  jnz     loc_180006286
0x1800061f9  mov     rcx, r14; this
0x1800061fc  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180006201  jmp     loc_180006286
0x180006206  mov     rcx, [rbp+47h+arg_8]; this
0x18000620a  call    ?CleanupImpersonation@CWdsDeviceControllerRequest@@QEAAJXZ; CWdsDeviceControllerRequest::CleanupImpersonation(void)
0x18000620f  mov     r9d, 0A5Bh; unsigned int
0x180006215  mov     r8, r12; char *
0x180006218  mov     ecx, eax; int
0x18000621a  mov     ebx, eax
0x18000621c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180006221  test    eax, eax
0x180006223  js      short loc_1800061D1
0x180006225  test    edi, edi
0x180006227  jz      short loc_180006238
0x180006229  lea     eax, [rdi-1]
0x18000622c  test    eax, eax
0x18000622e  jnz     short loc_180006238
0x180006230  mov     rcx, r14; this
0x180006233  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180006238  mov     rdx, [rbp+47h+arg_20]; struct CWdsMetadata *
0x18000623c  mov     rcx, rsi; this
0x18000623f  call    ?GetMetadata@CWdsComMetadataBuilder@@QEAAKPEAVCWdsMetadata@@@Z; CWdsComMetadataBuilder::GetMetadata(CWdsMetadata *)
0x180006244  mov     r9d, 0A5Fh; unsigned int
0x18000624a  mov     r8, r12; char *
0x18000624d  mov     ecx, eax; unsigned int
0x18000624f  mov     ebx, eax
0x180006251  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180006256  test    eax, eax
0x180006258  jnz     short loc_180006286
0x18000625a  cmp     [rbp+47h+arg_0], 0FFFFh
0x18000625f  mov     edx, r13d
0x180006262  mov     rax, [rbp+47h+arg_28]
0x180006266  mov     edi, 1
0x18000626b  setz    dl
0x18000626e  mov     [rax], edx
0x180006270  lea     ecx, [rdi+3Bh]
0x180006273  mov     edx, edi
0x180006275  call    cs:__imp_WdsPerfCounterAdd
0x18000627b  mov     edx, edi
0x18000627d  lea     ecx, [rdi+3Dh]
0x180006280  call    cs:__imp_WdsPerfCounterAdd
0x180006286  cmp     [rbp+47h+bstrString], r13
0x18000628a  jz      short loc_180006296
0x18000628c  mov     rcx, [rbp+47h+bstrString]; bstrString
0x180006290  call    cs:__imp_SysFreeString
0x180006296  test    rsi, rsi
0x180006299  jz      short loc_1800062AB
0x18000629b  mov     rax, [rsi]
0x18000629e  mov     rcx, rsi
0x1800062a1  mov     rax, [rax+10h]
0x1800062a5  call    cs:__guard_dispatch_icall_fptr
0x1800062ab  lea     rcx, [rbp+47h+var_70]; this
0x1800062af  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x1800062b4  mov     eax, [rbp+47h+var_78]
0x1800062b7  test    eax, eax
0x1800062b9  jz      short loc_1800062C9
0x1800062bb  cmp     eax, 1
0x1800062be  jnz     short loc_1800062C9
0x1800062c0  mov     rcx, [rbp+47h+var_80]; this
0x1800062c4  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x1800062c9  lea     r11, [rsp+0E0h+var_20]
0x1800062d1  mov     eax, ebx
0x1800062d3  mov     rbx, [r11+40h]
0x1800062d7  mov     rsi, [r11+48h]
0x1800062db  mov     rsp, r11
0x1800062de  pop     r14
0x1800062e0  pop     r13
0x1800062e2  pop     r12
0x1800062e4  pop     rdi
0x1800062e5  pop     rbp
0x1800062e6  retn
```
