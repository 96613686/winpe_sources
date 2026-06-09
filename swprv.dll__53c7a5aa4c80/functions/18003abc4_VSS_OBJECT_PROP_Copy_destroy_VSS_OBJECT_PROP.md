# VSS_OBJECT_PROP_Copy::destroy(_VSS_OBJECT_PROP *)

- ea: `0x18003abc4`
- end: `0x18003ad19`
- name: `?destroy@VSS_OBJECT_PROP_Copy@@SAXPEAU_VSS_OBJECT_PROP@@@Z`
- size: `341`
- prototype: `void __fastcall(struct _VSS_OBJECT_PROP *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000dd84`
- `0x1800179f0`
- `0x18003b348`

## callees

- `0x18000212c`
- `0x180033a8c`
- `0x180033c78`
- `0x18003abc4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003acb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003acc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003acd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003acea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003acb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003acc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003acd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003acea`

## string_xrefs

- `0x18003abee`: `PRPCOPYC`
- `0x18003abd2`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18003abe0`: `VSS_OBJECT_PROP_Copy::destroy`

## pseudocode

```c
void __fastcall VSS_OBJECT_PROP_Copy::destroy(struct _VSS_OBJECT_PROP *a1)
{
  LPVOID v2[14]; // [rsp+60h] [rbp-128h] BYREF
  _QWORD v3[3]; // [rsp+D0h] [rbp-B8h] BYREF
  int v4; // [rsp+E8h] [rbp-A0h]
  int v5; // [rsp+ECh] [rbp-9Ch]
  int v6; // [rsp+F0h] [rbp-98h]
  _DWORD v7[36]; // [rsp+F8h] [rbp-90h] BYREF

  v3[0] = L"base\\stor\\vss\\modules\\prop\\copy.cxx";
  v3[1] = L"VSS_OBJECT_PROP_Copy::destroy";
  v3[2] = L"PRPCOPYC";
  v4 = 180;
  v5 = 11;
  v6 = 255;
  v7[30] = 0x1000000;
  memset_0(v7, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)v2, (__int64)v3, 0);
  if ( a1 )
  {
    if ( a1->Type == VSS_OBJECT_SNAPSHOT )
    {
      CoTaskMemFree(a1->Obj.Snap.m_pwszOriginalVolumeName);
      a1->Obj.Snap.m_pwszOriginalVolumeName = 0;
      CoTaskMemFree(a1->Obj.Snap.m_pwszSnapshotDeviceObject);
      a1->Obj.Snap.m_pwszSnapshotDeviceObject = 0;
      CoTaskMemFree(a1->Obj.Snap.m_pwszOriginatingMachine);
      a1->Obj.Snap.m_pwszOriginatingMachine = 0;
      CoTaskMemFree(a1->Obj.Snap.m_pwszServiceMachine);
      a1->Obj.Snap.m_pwszServiceMachine = 0;
      CoTaskMemFree(a1->Obj.Snap.m_pwszExposedName);
      a1->Obj.Snap.m_pwszExposedName = 0;
      CoTaskMemFree(a1->Obj.Snap.m_pwszExposedPath);
      a1->Obj.Snap.m_pwszExposedPath = 0;
    }
    else if ( a1->Type == VSS_OBJECT_PROVIDER )
    {
      CoTaskMemFree(a1->Obj.Prov.m_pwszProviderName);
      a1->Obj.Prov.m_pwszProviderName = 0;
      CoTaskMemFree(a1->Obj.Prov.m_pwszProviderVersion);
      a1->Obj.Prov.m_pwszProviderVersion = 0;
    }
    a1->Type = VSS_OBJECT_UNKNOWN;
  }
  CVssFunctionTracer::~CVssFunctionTracer(v2);
}

```

## disassembly

```asm
0x18003abc4  mov     r11, rsp
0x18003abc7  push    rbx
0x18003abc8  sub     rsp, 180h
0x18003abcf  mov     rbx, rcx
0x18003abd2  lea     rax, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18003abd9  mov     [r11-0B8h], rax
0x18003abe0  lea     rax, aVssObjectPropC; "VSS_OBJECT_PROP_Copy::destroy"
0x18003abe7  mov     [r11-0B0h], rax
0x18003abee  lea     rax, aPrpcopyc; "PRPCOPYC"
0x18003abf5  mov     [r11-0A8h], rax
0x18003abfc  mov     [rsp+188h+var_A0], 0B4h
0x18003ac07  mov     [rsp+188h+var_9C], 0Bh
0x18003ac12  mov     [rsp+188h+var_98], 0FFh
0x18003ac1d  mov     dword ptr [r11-18h], 1000000h
0x18003ac25  xor     edx, edx; Val
0x18003ac27  lea     r8d, [rdx+78h]; Size
0x18003ac2b  lea     rcx, [r11-90h]; void *
0x18003ac32  call    memset_0
0x18003ac37  xor     r8d, r8d
0x18003ac3a  lea     rdx, [rsp+188h+var_B8]
0x18003ac42  lea     rcx, [rsp+188h+var_128]
0x18003ac47  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003ac4c  nop
0x18003ac4d  test    rbx, rbx
0x18003ac50  jz      loc_18003ACFE
0x18003ac56  mov     ecx, [rbx]
0x18003ac58  sub     ecx, 3
0x18003ac5b  jz      short loc_18003AC8C
0x18003ac5d  cmp     ecx, 1
0x18003ac60  jnz     loc_18003ACF8
0x18003ac66  mov     rcx, [rbx+18h]; pv
0x18003ac6a  call    cs:__imp_CoTaskMemFree
0x18003ac70  mov     qword ptr [rbx+18h], 0
0x18003ac78  mov     rcx, [rbx+28h]; pv
0x18003ac7c  call    cs:__imp_CoTaskMemFree
0x18003ac82  mov     qword ptr [rbx+28h], 0
0x18003ac8a  jmp     short loc_18003ACF8
0x18003ac8c  mov     rcx, [rbx+38h]; pv
0x18003ac90  call    cs:__imp_CoTaskMemFree
0x18003ac96  mov     qword ptr [rbx+38h], 0
0x18003ac9e  mov     rcx, [rbx+30h]; pv
0x18003aca2  call    cs:__imp_CoTaskMemFree
0x18003aca8  mov     qword ptr [rbx+30h], 0
0x18003acb0  mov     rcx, [rbx+40h]; pv
0x18003acb4  call    cs:__imp_CoTaskMemFree
0x18003acba  mov     qword ptr [rbx+40h], 0
0x18003acc2  mov     rcx, [rbx+48h]; pv
0x18003acc6  call    cs:__imp_CoTaskMemFree
0x18003accc  mov     qword ptr [rbx+48h], 0
0x18003acd4  mov     rcx, [rbx+50h]; pv
0x18003acd8  call    cs:__imp_CoTaskMemFree
0x18003acde  mov     qword ptr [rbx+50h], 0
0x18003ace6  mov     rcx, [rbx+58h]; pv
0x18003acea  call    cs:__imp_CoTaskMemFree
0x18003acf0  mov     qword ptr [rbx+58h], 0
0x18003acf8  mov     dword ptr [rbx], 0
0x18003acfe  jmp     short loc_18003AD06
0x18003ad00  jmp     short loc_18003AD06
0x18003ad02  jmp     short loc_18003AD06
0x18003ad04  jmp     short $+2
0x18003ad06  lea     rcx, [rsp+188h+var_128]; this
0x18003ad0b  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003ad10  add     rsp, 180h
0x18003ad17  pop     rbx
0x18003ad18  retn
```
