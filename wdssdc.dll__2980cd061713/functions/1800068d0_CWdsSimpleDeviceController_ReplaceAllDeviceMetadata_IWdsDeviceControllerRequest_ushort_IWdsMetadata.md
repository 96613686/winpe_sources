# CWdsSimpleDeviceController::ReplaceAllDeviceMetadata(IWdsDeviceControllerRequest *,ushort *,IWdsMetadata *)

- ea: `0x1800068d0`
- end: `0x180006a57`
- name: `?ReplaceAllDeviceMetadata@CWdsSimpleDeviceController@@UEAAJPEAUIWdsDeviceControllerRequest@@PEAGPEAUIWdsMetadata@@@Z`
- size: `391`
- prototype: `int(CWdsSimpleDeviceController *__hidden this, struct IWdsDeviceControllerRequest *, unsigned __int16 *, struct IWdsMetadata *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180005508`
- `0x180005dac`
- `0x1800068d0`
- `0x180006a60`
- `0x180006cdc`
- `0x180006dd8`
- `0x180008d44`
- `0x180009278`
- `0x180009300`
- `0x180009640`
- `0x18000c4cc`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006901`
- `KERNEL32!EnterCriticalSection` at `0x180006901`

## pseudocode

```c
__int64 __fastcall CWdsSimpleDeviceController::ReplaceAllDeviceMetadata(
        CWdsSimpleDeviceController *this,
        struct IWdsDeviceControllerRequest *a2,
        unsigned __int16 *a3,
        struct IWdsMetadata *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  CWdsSimpleDeviceController *v10; // r15
  __int64 Metadata; // rdi
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  char *v21; // [rsp+20h] [rbp-60h] BYREF
  int v22; // [rsp+28h] [rbp-58h]
  _QWORD v23[3]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v24[3]; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v25[4]; // [rsp+60h] [rbp-20h] BYREF

  v21 = (char *)this + 64;
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v22 = 1;
  v23[0] = 0;
  v23[1] = 0;
  v24[0] = 0;
  v24[1] = 0;
  v25[0] = 0;
  v25[1] = 0;
  if ( a4 || (v7 = -2147024809, (int)ElValidateHr(2147942487LL, v8, v9, 903) >= 0) )
  {
    v10 = (CWdsSimpleDeviceController *)((char *)this - 8);
    Metadata = (unsigned int)CWdsSimpleDeviceController::GetMetadata(
                               (CWdsSimpleDeviceController *)((char *)this - 8),
                               a3,
                               (struct CWdsMetadata *)v23);
    if ( !(unsigned int)ElValidateWin32(Metadata, v12, v13, 910) )
    {
      CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::Clear(v25);
      CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(v23);
      CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(v24);
      LODWORD(Metadata) = CopyFromCom(a4, (struct CWdsMetadata *)v23);
      if ( !(unsigned int)ElValidateWin32((unsigned int)Metadata, v14, v15, 914) )
      {
        if ( (CWdsMetadata::CountInstancesOfTag((CWdsMetadata *)v23, L"WDS.Device.DN")
           || CWdsMetadata::CountInstancesOfTag((CWdsMetadata *)v23, L"WDS.Device.Prestage.MachineOU"))
          && (unsigned int)ElValidateWin32(13, v16, v17, 924) )
        {
          v7 = -2147024883;
          goto LABEL_13;
        }
        LODWORD(Metadata) = CWdsSimpleDeviceController::SetMetadata(v10, a3, (const struct CWdsMetadata *)v23);
        if ( !(unsigned int)ElValidateWin32((unsigned int)Metadata, v18, v19, 928) )
          goto LABEL_13;
      }
    }
    if ( (int)Metadata > 0 )
      v7 = (unsigned __int16)Metadata | 0x80070000;
    else
      v7 = Metadata;
  }
LABEL_13:
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v23);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(&v21);
  return v7;
}

```

## disassembly

```asm
0x1800068d0  mov     [rsp-18h+arg_0], rbx
0x1800068d5  mov     [rsp-18h+arg_8], rsi
0x1800068da  mov     [rsp-18h+arg_10], rdi
0x1800068df  push    rbp
0x1800068e0  push    r14
0x1800068e2  push    r15
0x1800068e4  mov     rbp, rsp
0x1800068e7  sub     rsp, 80h
0x1800068ee  mov     rdi, rcx
0x1800068f1  mov     rsi, r9
0x1800068f4  add     rcx, 40h ; '@'; lpCriticalSection
0x1800068f8  mov     r14, r8
0x1800068fb  mov     [rbp+var_60], rcx
0x1800068ff  xor     ebx, ebx
0x180006901  call    cs:__imp_EnterCriticalSection
0x180006908  nop     dword ptr [rax+rax+00h]
0x18000690d  mov     [rbp+var_58], 1
0x180006914  mov     [rbp+var_50], rbx
0x180006918  mov     [rbp+var_48], rbx
0x18000691c  mov     [rbp+var_38], rbx
0x180006920  mov     [rbp+var_30], rbx
0x180006924  mov     [rbp+var_20], rbx
0x180006928  mov     [rbp+var_18], rbx
0x18000692c  test    rsi, rsi
0x18000692f  jnz     short loc_18000694B
0x180006931  mov     ebx, 80070057h
0x180006936  mov     r9d, 387h
0x18000693c  mov     ecx, ebx
0x18000693e  call    ElValidateHr
0x180006943  test    eax, eax
0x180006945  js      loc_180006A25
0x18000694b  lea     r15, [rdi-8]
0x18000694f  mov     rdx, r14; unsigned __int16 *
0x180006952  mov     rcx, r15; this
0x180006955  lea     r8, [rbp+var_50]; struct CWdsMetadata *
0x180006959  call    ?GetMetadata@CWdsSimpleDeviceController@@QEAAKPEBGPEAVCWdsMetadata@@@Z; CWdsSimpleDeviceController::GetMetadata(ushort const *,CWdsMetadata *)
0x18000695e  mov     r9d, 38Eh
0x180006964  mov     ecx, eax
0x180006966  mov     edi, eax
0x180006968  call    ElValidateWin32
0x18000696d  test    eax, eax
0x18000696f  jnz     loc_180006A14
0x180006975  lea     rcx, [rbp+var_20]
0x180006979  call    ?Clear@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::Clear(void)
0x18000697e  lea     rcx, [rbp+var_50]
0x180006982  call    ?Clear@?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(void)
0x180006987  lea     rcx, [rbp+var_38]
0x18000698b  call    ?Clear@?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(void)
0x180006990  lea     rdx, [rbp+var_50]; struct CWdsMetadata *
0x180006994  mov     rcx, rsi; struct IWdsMetadata *
0x180006997  call    ?CopyFromCom@@YAKPEAUIWdsMetadata@@PEAVCWdsMetadata@@@Z; CopyFromCom(IWdsMetadata *,CWdsMetadata *)
0x18000699c  mov     r9d, 392h
0x1800069a2  mov     ecx, eax
0x1800069a4  mov     edi, eax
0x1800069a6  call    ElValidateWin32
0x1800069ab  test    eax, eax
0x1800069ad  jnz     short loc_180006A14
0x1800069af  lea     rdx, aWdsDeviceDn; "WDS.Device.DN"
0x1800069b6  lea     rcx, [rbp+var_50]; this
0x1800069ba  call    ?CountInstancesOfTag@CWdsMetadata@@QEBAKPEBG@Z; CWdsMetadata::CountInstancesOfTag(ushort const *)
0x1800069bf  test    eax, eax
0x1800069c1  jnz     short loc_1800069D7
0x1800069c3  lea     rdx, aWdsDevicePrest; "WDS.Device.Prestage.MachineOU"
0x1800069ca  lea     rcx, [rbp+var_50]; this
0x1800069ce  call    ?CountInstancesOfTag@CWdsMetadata@@QEBAKPEBG@Z; CWdsMetadata::CountInstancesOfTag(ushort const *)
0x1800069d3  test    eax, eax
0x1800069d5  jz      short loc_1800069F2
0x1800069d7  mov     ecx, 0Dh
0x1800069dc  mov     r9d, 39Ch
0x1800069e2  call    ElValidateWin32
0x1800069e7  test    eax, eax
0x1800069e9  jz      short loc_1800069F2
0x1800069eb  mov     ebx, 8007000Dh
0x1800069f0  jmp     short loc_180006A25
0x1800069f2  lea     r8, [rbp+var_50]; struct CWdsMetadata *
0x1800069f6  mov     rdx, r14; unsigned __int16 *
0x1800069f9  mov     rcx, r15; this
0x1800069fc  call    ?SetMetadata@CWdsSimpleDeviceController@@AEAAKPEBGPEBVCWdsMetadata@@@Z; CWdsSimpleDeviceController::SetMetadata(ushort const *,CWdsMetadata const *)
0x180006a01  mov     r9d, 3A0h
0x180006a07  mov     ecx, eax
0x180006a09  mov     edi, eax
0x180006a0b  call    ElValidateWin32
0x180006a10  test    eax, eax
0x180006a12  jz      short loc_180006A25
0x180006a14  test    edi, edi
0x180006a16  jg      short loc_180006A1C
0x180006a18  mov     ebx, edi
0x180006a1a  jmp     short loc_180006A25
0x180006a1c  movzx   ebx, di
0x180006a1f  or      ebx, 80070000h
0x180006a25  lea     rcx, [rbp+var_50]; this
0x180006a29  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180006a2e  lea     rcx, [rbp+var_60]
0x180006a32  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180006a37  lea     r11, [rsp+80h+var_s0]
0x180006a3f  mov     eax, ebx
0x180006a41  mov     rbx, [r11+20h]
0x180006a45  mov     rsi, [r11+28h]
0x180006a49  mov     rdi, [r11+30h]
0x180006a4d  mov     rsp, r11
0x180006a50  pop     r15
0x180006a52  pop     r14
0x180006a54  pop     rbp
0x180006a55  retn
```
