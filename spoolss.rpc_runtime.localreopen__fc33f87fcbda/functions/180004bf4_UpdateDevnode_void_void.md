# UpdateDevnode(void *,void *)

- ea: `0x180004bf4`
- end: `0x180004dec`
- name: `?UpdateDevnode@@YAJPEAX0@Z`
- size: `504`
- prototype: `__int64 __fastcall(HANDLE hPrinter, DeviceObject *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180013c20`

## callees

- `0x180001b60`
- `0x180001d00`
- `0x180001e60`
- `0x180004bf4`
- `0x180004df4`
- `0x180012bd0`
- `0x18001374c`
- `0x1800137a4`
- `0x18001389c`
- `0x180013acc`
- `0x180015014`
- `0x180015260`
- `0x180015730`
- `0x1800161e8`

## import_xrefs

- `CFGMGR32!SwDevicePropertySet` at `0x180004d69`
- `CFGMGR32!SwDevicePropertySet` at `0x180004d69`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UpdateDevnode(HANDLE hPrinter, DeviceObject *this)
{
  unsigned __int8 *v4; // r13
  struct _DEVPROPERTY *v5; // r14
  unsigned int v6; // r12d
  int PrinterInfoFromPrinter; // eax
  signed int PrinterInstanceId; // edi
  unsigned __int16 *v9; // rbx
  unsigned int v10; // edi
  NCoreLibrary *v11; // rcx
  HANDLE v12; // rsi
  __int64 v13; // rcx
  NCoreLibrary *v14; // rcx
  NCoreLibrary::TString *v15; // rcx
  struct _PRINTER_INFO_2W *v17; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v18; // [rsp+48h] [rbp-18h] BYREF
  struct _DEVPROPERTY *v19; // [rsp+50h] [rbp-10h] BYREF
  bool v20; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v21; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int8 *v22; // [rsp+B8h] [rbp+58h] BYREF

  v17 = 0;
  v4 = 0;
  v22 = 0;
  v5 = 0;
  v19 = 0;
  v6 = 0;
  v21 = 0;
  PrinterInfoFromPrinter = GetPrinterInfoFromPrinter(hPrinter, &v17);
  PrinterInstanceId = PrinterInfoFromPrinter;
  if ( PrinterInfoFromPrinter > 0 )
    PrinterInstanceId = (unsigned __int16)PrinterInfoFromPrinter | 0x80070000;
  v9 = (unsigned __int16 *)&NCoreLibrary::TString::gszNullState;
  v18 = (unsigned __int16 *)&NCoreLibrary::TString::gszNullState;
  if ( PrinterInstanceId >= 0 )
  {
    PrinterInstanceId = GeneratePrinterInstanceId(v17->pPrinterName, (struct NCoreLibrary::TString *)&v18);
    v20 = 0;
    v9 = v18;
    if ( PrinterInstanceId >= 0 )
    {
      PrinterInstanceId = DeviceObject::DoesDeviceExist(v18, &v20);
      if ( PrinterInstanceId >= 0 )
      {
        if ( !v20 )
        {
          PrinterInstanceId = -2147019873;
          goto LABEL_27;
        }
        v10 = 8;
        if ( GetDriverInfoFromPrinter(hPrinter, &v22, 8u) == 124 )
        {
          v10 = 6;
          if ( GetDriverInfoFromPrinter(hPrinter, &v22, 6u) == 124 )
          {
            v10 = 1;
            GetDriverInfoFromPrinter(hPrinter, &v22, 1u);
          }
        }
        v4 = v22;
        PrinterInstanceId = BuildDevnodeProperties(v17, v22, v10, &v19, &v21, 0, 0);
        v5 = v19;
        v6 = v21;
      }
    }
    if ( PrinterInstanceId >= 0 )
    {
      v12 = RevertToPrinterSelf();
      if ( v12 || (PrinterInstanceId = NCoreLibrary::GetLastErrorAsFailHR(v11), PrinterInstanceId >= 0) )
      {
        if ( v5 )
        {
          PrinterInstanceId = DeviceObject::MarkObjectInUse(this);
          if ( PrinterInstanceId >= 0 )
          {
            v13 = *((_QWORD *)this + 2);
            if ( v13 )
            {
              PrinterInstanceId = SwDevicePropertySet(v13, v6, v5);
              if ( PrinterInstanceId == -2147024846 )
                PrinterInstanceId = -2147024875;
            }
            else
            {
              PrinterInstanceId = -2147019873;
            }
            DeviceObject::UnmarkObjectInUse(this);
          }
        }
        else
        {
          PrinterInstanceId = -2147024809;
        }
        if ( v12 && !ImpersonatePrinterClient(v12) && PrinterInstanceId >= 0 )
          PrinterInstanceId = NCoreLibrary::GetLastErrorAsFailHR(v14);
      }
    }
  }
LABEL_27:
  FreeDevPropertyList(v5, v6);
  DllFreeSplMem(v17);
  DllFreeSplMem(v4);
  NCoreLibrary::TString::vFree(v15, v9);
  return (unsigned int)PrinterInstanceId;
}

```

## disassembly

```asm
0x180004bf4  mov     [rsp-38h+arg_0], rbx
0x180004bf9  push    rbp
0x180004bfa  push    rsi
0x180004bfb  push    rdi
0x180004bfc  push    r12
0x180004bfe  push    r13
0x180004c00  push    r14
0x180004c02  push    r15
0x180004c04  mov     rbp, rsp
0x180004c07  sub     rsp, 60h
0x180004c0b  mov     r15, rdx
0x180004c0e  mov     rsi, rcx
0x180004c11  mov     [rbp+var_20], 0
0x180004c19  xor     r13d, r13d
0x180004c1c  mov     [rbp+arg_18], r13
0x180004c20  xor     r14d, r14d
0x180004c23  mov     [rbp+var_10], r14
0x180004c27  xor     r12d, r12d
0x180004c2a  mov     [rbp+arg_10], r12d
0x180004c2e  lea     rdx, [rbp+var_20]; struct _PRINTER_INFO_2W **
0x180004c32  call    ?GetPrinterInfoFromPrinter@@YAKPEAXPEAPEAU_PRINTER_INFO_2W@@@Z; GetPrinterInfoFromPrinter(void *,_PRINTER_INFO_2W * *)
0x180004c37  mov     edi, eax
0x180004c39  test    eax, eax
0x180004c3b  jle     short loc_180004C46
0x180004c3d  movzx   edi, ax
0x180004c40  or      edi, 80070000h
0x180004c46  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180004c4d  mov     [rbp+var_18], rbx
0x180004c51  test    edi, edi
0x180004c53  js      loc_180004DAC
0x180004c59  lea     rdx, [rbp+var_18]; struct NCoreLibrary::TString *
0x180004c5d  mov     rcx, [rbp+var_20]
0x180004c61  mov     rcx, [rcx+8]; unsigned __int16 *
0x180004c65  call    ?GeneratePrinterInstanceId@@YAJPEBGAEAVTString@NCoreLibrary@@@Z; GeneratePrinterInstanceId(ushort const *,NCoreLibrary::TString &)
0x180004c6a  mov     edi, eax
0x180004c6c  mov     [rbp+arg_8], 0
0x180004c70  mov     rbx, [rbp+var_18]
0x180004c74  test    eax, eax
0x180004c76  js      loc_180004D20
0x180004c7c  lea     rdx, [rbp+arg_8]; bool *
0x180004c80  mov     rcx, rbx; unsigned __int16 *
0x180004c83  call    ?DoesDeviceExist@DeviceObject@@SAJPEBGPEA_N@Z; DeviceObject::DoesDeviceExist(ushort const *,bool *)
0x180004c88  mov     edi, eax
0x180004c8a  test    eax, eax
0x180004c8c  js      loc_180004D20
0x180004c92  cmp     [rbp+arg_8], 0
0x180004c96  jnz     short loc_180004CA2
0x180004c98  mov     edi, 8007139Fh
0x180004c9d  jmp     loc_180004DAC
0x180004ca2  mov     edi, 8
0x180004ca7  mov     r8d, edi; unsigned int
0x180004caa  lea     rdx, [rbp+arg_18]; unsigned __int8 **
0x180004cae  mov     rcx, rsi; hPrinter
0x180004cb1  call    ?GetDriverInfoFromPrinter@@YAKPEAXPEAPEAEK@Z; GetDriverInfoFromPrinter(void *,uchar * *,ulong)
0x180004cb6  cmp     eax, 7Ch ; '|'
0x180004cb9  jnz     short loc_180004CE4
0x180004cbb  lea     edi, [rax-76h]
0x180004cbe  mov     r8d, edi; unsigned int
0x180004cc1  lea     rdx, [rbp+arg_18]; unsigned __int8 **
0x180004cc5  mov     rcx, rsi; hPrinter
0x180004cc8  call    ?GetDriverInfoFromPrinter@@YAKPEAXPEAPEAEK@Z; GetDriverInfoFromPrinter(void *,uchar * *,ulong)
0x180004ccd  cmp     eax, 7Ch ; '|'
0x180004cd0  jnz     short loc_180004CE4
0x180004cd2  lea     edi, [rax-7Bh]
0x180004cd5  mov     r8d, edi; unsigned int
0x180004cd8  lea     rdx, [rbp+arg_18]; unsigned __int8 **
0x180004cdc  mov     rcx, rsi; hPrinter
0x180004cdf  call    ?GetDriverInfoFromPrinter@@YAKPEAXPEAPEAEK@Z; GetDriverInfoFromPrinter(void *,uchar * *,ulong)
0x180004ce4  mov     [rsp+60h+var_30], 0; unsigned int *
0x180004ced  mov     [rsp+60h+var_38], 0; struct _DEVPROPERTY **
0x180004cf6  lea     rax, [rbp+arg_10]
0x180004cfa  mov     [rsp+60h+var_40], rax; unsigned int *
0x180004cff  lea     r9, [rbp+var_10]; struct _DEVPROPERTY **
0x180004d03  mov     r8d, edi; unsigned int
0x180004d06  mov     r13, [rbp+arg_18]
0x180004d0a  mov     rdx, r13; unsigned __int8 *
0x180004d0d  mov     rcx, [rbp+var_20]; struct _PRINTER_INFO_2W *
0x180004d11  call    ?BuildDevnodeProperties@@YAJPEAU_PRINTER_INFO_2W@@PEAEKPEAPEAU_DEVPROPERTY@@PEAK23@Z; BuildDevnodeProperties(_PRINTER_INFO_2W *,uchar *,ulong,_DEVPROPERTY * *,ulong *,_DEVPROPERTY * *,ulong *)
0x180004d16  mov     edi, eax
0x180004d18  mov     r14, [rbp+var_10]
0x180004d1c  mov     r12d, [rbp+arg_10]
0x180004d20  test    edi, edi
0x180004d22  js      loc_180004DAC
0x180004d28  call    RevertToPrinterSelf
0x180004d2d  mov     rsi, rax
0x180004d30  test    rax, rax
0x180004d33  jnz     short loc_180004D40
0x180004d35  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180004d3a  mov     edi, eax
0x180004d3c  test    eax, eax
0x180004d3e  js      short loc_180004DAC
0x180004d40  test    r14, r14
0x180004d43  jnz     short loc_180004D4C
0x180004d45  mov     edi, 80070057h
0x180004d4a  jmp     short loc_180004D90
0x180004d4c  mov     rcx, r15; this
0x180004d4f  call    ?MarkObjectInUse@DeviceObject@@IEAAJXZ; DeviceObject::MarkObjectInUse(void)
0x180004d54  mov     edi, eax
0x180004d56  test    eax, eax
0x180004d58  js      short loc_180004D90
0x180004d5a  mov     rcx, [r15+10h]
0x180004d5e  test    rcx, rcx
0x180004d61  jz      short loc_180004D83
0x180004d63  mov     r8, r14
0x180004d66  mov     edx, r12d
0x180004d69  call    cs:__imp_SwDevicePropertySet
0x180004d70  nop     dword ptr [rax+rax+00h]
0x180004d75  mov     edi, eax
0x180004d77  cmp     eax, 80070032h
0x180004d7c  jnz     short loc_180004D88
0x180004d7e  lea     edi, [rax-1Dh]
0x180004d81  jmp     short loc_180004D88
0x180004d83  mov     edi, 8007139Fh
0x180004d88  mov     rcx, r15; this
0x180004d8b  call    ?UnmarkObjectInUse@DeviceObject@@IEAAXXZ; DeviceObject::UnmarkObjectInUse(void)
0x180004d90  test    rsi, rsi
0x180004d93  jz      short loc_180004DAC
0x180004d95  mov     rcx, rsi; hToken
0x180004d98  call    ImpersonatePrinterClient
0x180004d9d  test    eax, eax
0x180004d9f  jnz     short loc_180004DAC
0x180004da1  test    edi, edi
0x180004da3  js      short loc_180004DAC
0x180004da5  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180004daa  mov     edi, eax
0x180004dac  mov     edx, r12d; unsigned int
0x180004daf  mov     rcx, r14; struct _DEVPROPERTY *
0x180004db2  call    ?FreeDevPropertyList@@YAXPEAU_DEVPROPERTY@@K@Z; FreeDevPropertyList(_DEVPROPERTY *,ulong)
0x180004db7  mov     rcx, [rbp+var_20]
0x180004dbb  call    DllFreeSplMem
0x180004dc0  mov     rcx, r13
0x180004dc3  call    DllFreeSplMem
0x180004dc8  nop
0x180004dc9  mov     rdx, rbx; void *
0x180004dcc  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180004dd1  mov     eax, edi
0x180004dd3  mov     rbx, [rsp+60h+arg_0]
0x180004ddb  add     rsp, 60h
0x180004ddf  pop     r15
0x180004de1  pop     r14
0x180004de3  pop     r13
0x180004de5  pop     r12
0x180004de7  pop     rdi
0x180004de8  pop     rsi
0x180004de9  pop     rbp
0x180004dea  retn
```
