# InstallExtPropDesc

- ea: `0x1400242a4`
- end: `0x140024846`
- name: `InstallExtPropDesc`
- size: `1442`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140010650`

## callees

- `0x1400083c8`
- `0x1400088b4`
- `0x14000a6cc`
- `0x14000b4bc`
- `0x14000ecc8`
- `0x140011f4c`
- `0x140013a6c`
- `0x140013b88`
- `0x140022240`
- `0x1400242a4`
- `0x14002b99c`
- `0x14002d9c4`
- `0x14002e100`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140024812`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024828`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024812`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024828`
- `ntoskrnl!RtlCompareMemory` at `0x140024733`
- `ntoskrnl!RtlCompareMemory` at `0x140024733`
- `ntoskrnl!ExAllocatePool2` at `0x1400245b7`
- `ntoskrnl!ExAllocatePool2` at `0x1400246a8`
- `ntoskrnl!ExAllocatePool2` at `0x1400245b7`
- `ntoskrnl!ExAllocatePool2` at `0x1400246a8`

## pseudocode

```c
void __fastcall InstallExtPropDesc(__int64 a1)
{
  struct _DEVICE_OBJECT *v1; // r14
  int PdoRegistryParameter; // edx
  int v4; // eax
  int v5; // edx
  int v6; // edx
  int v7; // r9d
  int v8; // r8d
  __int64 v9; // rcx
  __int64 Pool2; // rax
  int v11; // r8d
  unsigned int *v12; // rsi
  unsigned int *v13; // rdi
  int MsOsFeatureDescriptor; // eax
  int v15; // edx
  int v16; // r9d
  __int64 v17; // rax
  int v18; // r8d
  int v19; // r9d
  unsigned int v20; // r15d
  int v21; // eax
  char v22; // [rsp+28h] [rbp-30h]
  __int64 v23; // [rsp+28h] [rbp-30h]
  __int64 v24; // [rsp+28h] [rbp-30h]
  int v25; // [rsp+30h] [rbp-28h]
  int v26; // [rsp+30h] [rbp-28h]
  char v27; // [rsp+30h] [rbp-28h]
  _DWORD v28[6]; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int16 v29; // [rsp+A0h] [rbp+48h] BYREF
  int v30; // [rsp+A8h] [rbp+50h] BYREF
  int v31; // [rsp+B0h] [rbp+58h] BYREF
  int v32; // [rsp+B8h] [rbp+60h]

  v1 = *(struct _DEVICE_OBJECT **)(a1 + 224);
  v32 = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  v28[0] = 0;
  PdoRegistryParameter = GetPdoRegistryParameter(v1, aRevisionid, &v31, 4, 0, 0, 0);
  if ( (int)(PdoRegistryParameter + 0x80000000) >= 0
    && PdoRegistryParameter != -1073741772
    && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v22 = PdoRegistryParameter;
    LOBYTE(PdoRegistryParameter) = 5;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(a1 + 392),
      PdoRegistryParameter,
      1,
      46,
      (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
      v22);
  }
  LOBYTE(v25) = 0;
  v4 = GetPdoRegistryParameter(v1, aVendorrevision, &v30, 4, 0, 0, v25);
  if ( (int)(v4 + 0x80000000) >= 0
    && v4 != -1073741772
    && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 392), 5, 1, 47, (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids, v4);
  }
  if ( !(unsigned __int8)GetFunctionMsOs20VendorRevision(a1, &v29)
    && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 392), v5, 1, 48, (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids);
  }
  if ( (unsigned int)Feature_WinUsb_Print__private_IsEnabledDeviceUsageNoInline() && *(_BYTE *)(a1 + 408) )
    SetPdoRegistryParameter(v1, 1u);
  LOBYTE(v26) = 0;
  if ( (int)GetPdoRegistryParameter(v1, aExtpropdescsem, 0, 0, 0, 0, v26) >= 0
    && v31 == *(unsigned __int16 *)(*(_QWORD *)(a1 + 232) + 108LL)
    && v30 == v29 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      v7 = 49;
      v8 = 1;
      LOBYTE(v6) = 5;
LABEL_24:
      WPP_RECORDER_SF_q(
        *(_QWORD *)(a1 + 392),
        v6,
        v8,
        v7,
        (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
        *(_QWORD *)(a1 + 224));
      return;
    }
    return;
  }
  v9 = *(_QWORD *)(a1 + 232);
  v31 = *(unsigned __int16 *)(v9 + 108);
  v30 = v29;
  if ( *(_QWORD *)(v9 + 1128) )
  {
    if ( (int)InstallMsOs20RegistryValues(a1) >= 0 )
    {
      SetPdoRegistryParameter(v1, 4u);
      SetPdoRegistryParameter(v1, 4u);
      v32 = 1;
      SetPdoRegistryParameter(v1, 4u);
    }
    return;
  }
  SetPdoRegistryParameter(v1, 4u);
  SetPdoRegistryParameter(v1, 4u);
  v32 = 1;
  SetPdoRegistryParameter(v1, 4u);
  Pool2 = ExAllocatePool2(64, 10, 1130525525);
  v12 = (unsigned int *)Pool2;
  if ( Pool2 )
  {
    LOBYTE(v11) = *(_BYTE *)(a1 + 8);
    LOBYTE(v6) = 1;
    v13 = 0;
    MsOsFeatureDescriptor = GetMsOsFeatureDescriptor(*(_QWORD *)(a1 + 232), v6, v11, 5, Pool2, 10, (__int64)v28);
    if ( MsOsFeatureDescriptor < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_62;
      v16 = 51;
      goto LABEL_34;
    }
    if ( v28[0] != 10
      || *v12 < 0xA
      || (v15 = 256, *((_WORD *)v12 + 2) != 256)
      || *((_WORD *)v12 + 3) != 5
      || !*((_WORD *)v12 + 4) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_62;
      v19 = 52;
      goto LABEL_60;
    }
    v17 = ExAllocatePool2(64, *v12, 1130525525);
    v13 = (unsigned int *)v17;
    if ( !v17 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_62;
      v19 = 53;
LABEL_60:
      v24 = *(_QWORD *)(a1 + 224);
LABEL_61:
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_q(
        *(_QWORD *)(a1 + 392),
        v15,
        8,
        v19,
        (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
        v24);
      goto LABEL_62;
    }
    LOBYTE(v18) = *(_BYTE *)(a1 + 8);
    LOBYTE(v15) = 1;
    MsOsFeatureDescriptor = GetMsOsFeatureDescriptor(*(_QWORD *)(a1 + 232), v15, v18, 5, v17, *v12, (__int64)v28);
    if ( MsOsFeatureDescriptor < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v16 = 54;
LABEL_34:
        v27 = MsOsFeatureDescriptor;
        v23 = *(_QWORD *)(a1 + 224);
LABEL_35:
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_qD(
          *(_QWORD *)(a1 + 392),
          v15,
          8,
          v16,
          (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
          v23,
          v27);
      }
LABEL_62:
      ExFreePoolWithTag(v12, 0x43627355u);
      if ( v13 )
        ExFreePoolWithTag(v13, 0x43627355u);
      return;
    }
    v20 = v28[0];
    if ( v28[0] != *v12 || RtlCompareMemory(v12, v13, 0xAu) != 10 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_62;
      v19 = 55;
      v24 = *(_QWORD *)(a1 + 224);
      goto LABEL_61;
    }
    v21 = USBD_ValidateExtendedPropertyDescriptor(v13, v20);
    if ( v21 >= 0 )
    {
      v21 = USBD_InstallExtPropDescSections(v1, v13, *v13);
      if ( v21 >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_62;
      v16 = 57;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_62;
      v16 = 56;
    }
    v27 = v21;
    v23 = *(_QWORD *)(a1 + 224);
    goto LABEL_35;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v7 = 50;
    LOBYTE(v6) = 2;
    v8 = 8;
    goto LABEL_24;
  }
}

```

## disassembly

```asm
0x1400242a4  push    rbp
0x1400242a6  push    rbx
0x1400242a7  push    rsi
0x1400242a8  push    rdi
0x1400242a9  push    r12
0x1400242ab  push    r13
0x1400242ad  push    r14
0x1400242af  push    r15
0x1400242b1  mov     rbp, rsp
0x1400242b4  sub     rsp, 58h
0x1400242b8  mov     r14, [rcx+0E0h]
0x1400242bf  lea     r8, [rbp+arg_10]
0x1400242c3  xor     r12d, r12d
0x1400242c6  lea     rdx, aRevisionid; "RevisionId"
0x1400242cd  mov     rbx, rcx
0x1400242d0  mov     [rsp+58h+var_28], r12b
0x1400242d5  mov     [rsp+58h+var_30], r12
0x1400242da  mov     rcx, r14
0x1400242dd  mov     [rbp+arg_18], r12d
0x1400242e1  lea     edi, [r12+4]
0x1400242e6  mov     [rbp+arg_10], r12d
0x1400242ea  mov     r9d, edi
0x1400242ed  mov     [rbp+arg_8], r12d
0x1400242f1  mov     [rbp+arg_0], r12w
0x1400242f6  mov     [rbp+var_18], r12d
0x1400242fa  mov     qword ptr [rsp+58h+Type], r12
0x1400242ff  call    GetPdoRegistryParameter
0x140024304  mov     edx, eax
0x140024306  lea     r15, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x14002430d  mov     eax, 80000000h
0x140024312  lea     esi, [rdi-3]
0x140024315  lea     r13, WPP_RECORDER_INITIALIZED
0x14002431c  lea     ecx, [rdx+rax]
0x14002431f  test    eax, ecx
0x140024321  jnz     short loc_140024361
0x140024323  cmp     edx, 0C0000034h
0x140024329  jz      short loc_140024361
0x14002432b  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140024332  jz      short loc_140024361
0x140024334  mov     rax, cs:WPP_GLOBAL_Control
0x14002433b  cmp     [rax+48h], r12w
0x140024340  jz      short loc_140024361
0x140024342  mov     rcx, [rbx+188h]
0x140024349  lea     r9d, [r12+2Eh]
0x14002434e  mov     dword ptr [rsp+58h+var_30], edx
0x140024352  mov     r8d, esi
0x140024355  mov     dl, 5
0x140024357  mov     qword ptr [rsp+58h+Type], r15
0x14002435c  call    WPP_RECORDER_SF_d
0x140024361  mov     [rsp+58h+var_28], r12b
0x140024366  lea     r8, [rbp+arg_8]
0x14002436a  mov     [rsp+58h+var_30], r12
0x14002436f  lea     rdx, aVendorrevision; "VendorRevision"
0x140024376  mov     r9d, edi
0x140024379  mov     qword ptr [rsp+58h+Type], r12
0x14002437e  mov     rcx, r14
0x140024381  call    GetPdoRegistryParameter
0x140024386  mov     edx, 80000000h
0x14002438b  lea     ecx, [rax+rdx]
0x14002438e  test    edx, ecx
0x140024390  jnz     short loc_1400243D2
0x140024392  cmp     eax, 0C0000034h
0x140024397  jz      short loc_1400243D2
0x140024399  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400243a0  jz      short loc_1400243D2
0x1400243a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400243a9  cmp     [rcx+48h], r12w
0x1400243ae  jz      short loc_1400243D2
0x1400243b0  mov     rcx, [rbx+188h]
0x1400243b7  mov     r9d, 2Fh ; '/'
0x1400243bd  mov     dword ptr [rsp+58h+var_30], eax
0x1400243c1  mov     r8d, esi
0x1400243c4  mov     qword ptr [rsp+58h+Type], r15
0x1400243c9  lea     edx, [r9-2Ah]
0x1400243cd  call    WPP_RECORDER_SF_d
0x1400243d2  lea     rdx, [rbp+arg_0]
0x1400243d6  mov     rcx, rbx
0x1400243d9  call    GetFunctionMsOs20VendorRevision
0x1400243de  test    al, al
0x1400243e0  jnz     short loc_140024415
0x1400243e2  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400243e9  jz      short loc_140024415
0x1400243eb  mov     rax, cs:WPP_GLOBAL_Control
0x1400243f2  cmp     [rax+48h], r12w
0x1400243f7  jz      short loc_140024415
0x1400243f9  mov     rcx, [rbx+188h]
0x140024400  mov     r9d, 30h ; '0'
0x140024406  mov     r8d, esi
0x140024409  mov     qword ptr [rsp+58h+Type], r15
0x14002440e  mov     dl, 5
0x140024410  call    WPP_RECORDER_SF_
0x140024415  call    Feature_WinUsb_Print__private_IsEnabledDeviceUsageNoInline
0x14002441a  test    eax, eax
0x14002441c  jz      short loc_140024447
0x14002441e  cmp     [rbx+198h], r12b
0x140024425  jz      short loc_140024447
0x140024427  mov     r9d, 4Eh ; 'N'
0x14002442d  mov     [rsp+58h+Type], esi; Type
0x140024431  lea     r8, a6aa3bdac3c994b; "{6AA3BDAC-3C99-4BA3-B2CA-A751DB8B808D}"
0x140024438  mov     rcx, r14; DeviceObject
0x14002443b  lea     rdx, aDeviceinterfac; "DeviceInterfaceGuid"
0x140024442  call    SetPdoRegistryParameter
0x140024447  mov     [rsp+58h+var_28], r12b
0x14002444c  lea     rdx, aExtpropdescsem; "ExtPropDescSemaphore"
0x140024453  mov     [rsp+58h+var_30], r12
0x140024458  xor     r9d, r9d
0x14002445b  xor     r8d, r8d
0x14002445e  mov     qword ptr [rsp+58h+Type], r12
0x140024463  mov     rcx, r14
0x140024466  call    GetPdoRegistryParameter
0x14002446b  test    eax, eax
0x14002446d  js      short loc_1400244D4
0x14002446f  mov     rax, [rbx+0E8h]
0x140024476  movzx   ecx, word ptr [rax+6Ch]
0x14002447a  cmp     [rbp+arg_10], ecx
0x14002447d  jnz     short loc_1400244D4
0x14002447f  movzx   eax, [rbp+arg_0]
0x140024483  cmp     [rbp+arg_8], eax
0x140024486  jnz     short loc_1400244D4
0x140024488  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14002448f  jz      loc_140024834
0x140024495  mov     rax, cs:WPP_GLOBAL_Control
0x14002449c  cmp     [rax+48h], r12w
0x1400244a1  jz      loc_140024834
0x1400244a7  mov     r9d, 31h ; '1'
0x1400244ad  mov     r8d, esi
0x1400244b0  mov     dl, 5
0x1400244b2  mov     rax, [rbx+0E0h]
0x1400244b9  mov     rcx, [rbx+188h]
0x1400244c0  mov     [rsp+58h+var_30], rax
0x1400244c5  mov     qword ptr [rsp+58h+Type], r15
0x1400244ca  call    WPP_RECORDER_SF_q
0x1400244cf  jmp     loc_140024834
0x1400244d4  mov     rcx, [rbx+0E8h]
0x1400244db  movzx   eax, word ptr [rcx+6Ch]
0x1400244df  mov     [rbp+arg_10], eax
0x1400244e2  movzx   eax, [rbp+arg_0]
0x1400244e6  mov     [rbp+arg_8], eax
0x1400244e9  cmp     [rcx+468h], r12
0x1400244f0  jz      short loc_140024558
0x1400244f2  mov     rcx, rbx
0x1400244f5  call    InstallMsOs20RegistryValues
0x1400244fa  test    eax, eax
0x1400244fc  js      loc_140024834
0x140024502  mov     r9d, edi
0x140024505  mov     [rsp+58h+Type], edi; Type
0x140024509  lea     r8, [rbp+arg_8]
0x14002450d  mov     rcx, r14; DeviceObject
0x140024510  lea     rdx, aVendorrevision; "VendorRevision"
0x140024517  call    SetPdoRegistryParameter
0x14002451c  mov     r9d, edi
0x14002451f  mov     [rsp+58h+Type], edi; Type
0x140024523  lea     r8, [rbp+arg_10]
0x140024527  mov     rcx, r14; DeviceObject
0x14002452a  lea     rdx, aRevisionid; "RevisionId"
0x140024531  call    SetPdoRegistryParameter
0x140024536  mov     r9d, edi
0x140024539  mov     [rbp+arg_18], esi
0x14002453c  lea     r8, [rbp+arg_18]
0x140024540  mov     [rsp+58h+Type], edi; Type
0x140024544  lea     rdx, aExtpropdescsem; "ExtPropDescSemaphore"
0x14002454b  mov     rcx, r14; DeviceObject
0x14002454e  call    SetPdoRegistryParameter
0x140024553  jmp     loc_140024834
0x140024558  mov     r9d, edi
0x14002455b  mov     [rsp+58h+Type], edi; Type
0x14002455f  lea     r8, [rbp+arg_8]
0x140024563  mov     rcx, r14; DeviceObject
0x140024566  lea     rdx, aVendorrevision; "VendorRevision"
0x14002456d  call    SetPdoRegistryParameter
0x140024572  mov     r9d, edi
0x140024575  mov     [rsp+58h+Type], edi; Type
0x140024579  lea     r8, [rbp+arg_10]
0x14002457d  mov     rcx, r14; DeviceObject
0x140024580  lea     rdx, aRevisionid; "RevisionId"
0x140024587  call    SetPdoRegistryParameter
0x14002458c  mov     r9d, edi
0x14002458f  mov     [rbp+arg_18], esi
0x140024592  lea     r8, [rbp+arg_18]
0x140024596  mov     [rsp+58h+Type], edi; Type
0x14002459a  lea     rdx, aExtpropdescsem; "ExtPropDescSemaphore"
0x1400245a1  mov     rcx, r14; DeviceObject
0x1400245a4  call    SetPdoRegistryParameter
0x1400245a9  mov     edx, 0Ah
0x1400245ae  mov     r8d, 43627355h
0x1400245b4  lea     ecx, [rdx+36h]
0x1400245b7  call    cs:__imp_ExAllocatePool2
0x1400245be  nop     dword ptr [rax+rax+00h]
0x1400245c3  mov     rsi, rax
0x1400245c6  test    rax, rax
0x1400245c9  jnz     short loc_1400245E7
0x1400245cb  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400245d2  jz      loc_140024834
0x1400245d8  lea     r9d, [rax+32h]
0x1400245dc  mov     dl, 2
0x1400245de  lea     r8d, [rax+8]
0x1400245e2  jmp     loc_1400244B2
0x1400245e7  mov     r8b, [rbx+8]
0x1400245eb  lea     rax, [rbp+var_18]
0x1400245ef  mov     rcx, [rbx+0E8h]
0x1400245f6  mov     r9d, 5
0x1400245fc  mov     qword ptr [rsp+58h+var_28], rax
0x140024601  mov     dl, 1
0x140024603  mov     dword ptr [rsp+58h+var_30], 0Ah
0x14002460b  mov     rdi, r12
0x14002460e  mov     qword ptr [rsp+58h+Type], rsi
0x140024613  call    GetMsOsFeatureDescriptor
0x140024618  test    eax, eax
0x14002461a  jns     short loc_14002465D
0x14002461c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140024623  jz      loc_140024808
0x140024629  mov     r9d, 33h ; '3'
0x14002462f  mov     dword ptr [rsp+58h+var_28], eax
0x140024633  mov     rax, [rbx+0E0h]
0x14002463a  mov     [rsp+58h+var_30], rax
0x14002463f  mov     qword ptr [rsp+58h+Type], r15
0x140024644  mov     rcx, [rbx+188h]
0x14002464b  mov     r8d, 8
0x140024651  mov     dl, 2
0x140024653  call    WPP_RECORDER_SF_qD
0x140024658  jmp     loc_140024808
0x14002465d  cmp     [rbp+var_18], 0Ah
0x140024661  jnz     loc_1400247D4
0x140024667  mov     eax, [rsi]
0x140024669  cmp     eax, 0Ah
0x14002466c  jb      loc_1400247D4
0x140024672  mov     edx, 100h
0x140024677  cmp     [rsi+4], dx
0x14002467b  jnz     loc_1400247D4
0x140024681  mov     ecx, 5
0x140024686  cmp     [rsi+6], cx
0x14002468a  jnz     loc_1400247D4
0x140024690  cmp     [rsi+8], r12w
0x140024695  jz      loc_1400247D4
0x14002469b  mov     edx, eax
0x14002469d  mov     ecx, 40h ; '@'
0x1400246a2  mov     r8d, 43627355h
0x1400246a8  call    cs:__imp_ExAllocatePool2
0x1400246af  nop     dword ptr [rax+rax+00h]
0x1400246b4  mov     rdi, rax
0x1400246b7  test    rax, rax
0x1400246ba  jnz     short loc_1400246D2
0x1400246bc  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400246c3  jz      loc_140024808
0x1400246c9  lea     r9d, [rax+35h]
0x1400246cd  jmp     loc_1400247E3
0x1400246d2  mov     r8b, [rbx+8]
0x1400246d6  lea     rax, [rbp+var_18]
0x1400246da  mov     rcx, [rbx+0E8h]
0x1400246e1  mov     r9d, 5
0x1400246e7  mov     qword ptr [rsp+58h+var_28], rax
0x1400246ec  mov     dl, 1
0x1400246ee  mov     eax, [rsi]
0x1400246f0  mov     dword ptr [rsp+58h+var_30], eax
0x1400246f4  mov     qword ptr [rsp+58h+Type], rdi
0x1400246f9  call    GetMsOsFeatureDescriptor
0x1400246fe  test    eax, eax
0x140024700  jns     short loc_14002471A
0x140024702  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140024709  jz      loc_140024808
0x14002470f  mov     r9d, 36h ; '6'
0x140024715  jmp     loc_14002462F
0x14002471a  mov     r15d, [rbp+var_18]
0x14002471e  cmp     r15d, [rsi]
0x140024721  jnz     loc_1400247AB
0x140024727  mov     r8d, 0Ah; Length
0x14002472d  mov     rdx, rdi; Source2
0x140024730  mov     rcx, rsi; Source1
0x140024733  call    cs:__imp_RtlCompareMemory
0x14002473a  nop     dword ptr [rax+rax+00h]
0x14002473f  cmp     rax, 0Ah
0x140024743  jnz     short loc_1400247AB
0x140024745  mov     edx, r15d
0x140024748  mov     rcx, rdi
0x14002474b  call    USBD_ValidateExtendedPropertyDescriptor
0x140024750  test    eax, eax
0x140024752  jns     short loc_140024788
0x140024754  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14002475b  jz      loc_140024808
0x140024761  mov     r9d, 38h ; '8'
0x140024767  mov     dword ptr [rsp+58h+var_28], eax
0x14002476b  mov     rax, [rbx+0E0h]
0x140024772  mov     [rsp+58h+var_30], rax
0x140024777  lea     rax, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x14002477e  mov     qword ptr [rsp+58h+Type], rax
0x140024783  jmp     loc_140024644
0x140024788  mov     r8d, [rdi]
0x14002478b  mov     rdx, rdi
0x14002478e  mov     rcx, r14
0x140024791  call    USBD_InstallExtPropDescSections
0x140024796  test    eax, eax
0x140024798  jns     short loc_140024808
0x14002479a  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400247a1  jz      short loc_140024808
0x1400247a3  mov     r9d, 39h ; '9'
0x1400247a9  jmp     short loc_140024767
0x1400247ab  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400247b2  jz      short loc_140024808
0x1400247b4  mov     rax, [rbx+0E0h]
0x1400247bb  mov     r9d, 37h ; '7'
  ... truncated ...
```
