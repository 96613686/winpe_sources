# UpdateDevnode(void *,void *)

- ea: `0x1800048b4`
- end: `0x180004aa1`
- name: `?UpdateDevnode@@YAJPEAX0@Z`
- size: `493`
- prototype: `__int64 __fastcall(HANDLE hPrinter, DeviceObject *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180012500`

## callees

- `0x180001b50`
- `0x180001cd0`
- `0x180001e00`
- `0x1800048b4`
- `0x180004aa8`
- `0x1800114cc`
- `0x180011fec`
- `0x180012044`
- `0x180012130`
- `0x180012344`
- `0x1800138bc`
- `0x180013acc`
- `0x180013e70`
- `0x180014854`

## import_xrefs

- `CFGMGR32!SwDevicePropertySet` at `0x180004a25`
- `CFGMGR32!SwDevicePropertySet` at `0x180004a25`

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
0x1800048b4  mov     [rsp-38h+arg_0], rbx
0x1800048b9  push    rbp
0x1800048ba  push    rsi
0x1800048bb  push    rdi
0x1800048bc  push    r12
0x1800048be  push    r13
0x1800048c0  push    r14
0x1800048c2  push    r15
0x1800048c4  mov     rbp, rsp
0x1800048c7  sub     rsp, 60h
0x1800048cb  mov     r15, rdx
0x1800048ce  mov     rsi, rcx
0x1800048d1  mov     [rbp+var_20], 0
0x1800048d9  xor     r13d, r13d
0x1800048dc  mov     [rbp+arg_18], r13
0x1800048e0  xor     r14d, r14d
0x1800048e3  mov     [rbp+var_10], r14
0x1800048e7  xor     r12d, r12d
0x1800048ea  mov     [rbp+arg_10], r12d
0x1800048ee  lea     rdx, [rbp+var_20]; struct _PRINTER_INFO_2W **
0x1800048f2  call    ?GetPrinterInfoFromPrinter@@YAKPEAXPEAPEAU_PRINTER_INFO_2W@@@Z; GetPrinterInfoFromPrinter(void *,_PRINTER_INFO_2W * *)
0x1800048f7  mov     edi, eax
0x1800048f9  test    eax, eax
0x1800048fb  jle     short loc_180004906
0x1800048fd  movzx   edi, ax
0x180004900  or      edi, 80070000h
0x180004906  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x18000490d  mov     [rbp+var_18], rbx
0x180004911  test    edi, edi
0x180004913  js      loc_180004A62
0x180004919  lea     rdx, [rbp+var_18]; struct NCoreLibrary::TString *
0x18000491d  mov     rcx, [rbp+var_20]
0x180004921  mov     rcx, [rcx+8]; unsigned __int16 *
0x180004925  call    ?GeneratePrinterInstanceId@@YAJPEBGAEAVTString@NCoreLibrary@@@Z; GeneratePrinterInstanceId(ushort const *,NCoreLibrary::TString &)
0x18000492a  mov     edi, eax
0x18000492c  mov     [rbp+arg_8], 0
0x180004930  mov     rbx, [rbp+var_18]
0x180004934  test    eax, eax
0x180004936  js      loc_1800049E0
0x18000493c  lea     rdx, [rbp+arg_8]; bool *
0x180004940  mov     rcx, rbx; unsigned __int16 *
0x180004943  call    ?DoesDeviceExist@DeviceObject@@SAJPEBGPEA_N@Z; DeviceObject::DoesDeviceExist(ushort const *,bool *)
0x180004948  mov     edi, eax
0x18000494a  test    eax, eax
0x18000494c  js      loc_1800049E0
0x180004952  cmp     [rbp+arg_8], 0
0x180004956  jnz     short loc_180004962
0x180004958  mov     edi, 8007139Fh
0x18000495d  jmp     loc_180004A62
0x180004962  mov     edi, 8
0x180004967  mov     r8d, edi; unsigned int
0x18000496a  lea     rdx, [rbp+arg_18]; unsigned __int8 **
0x18000496e  mov     rcx, rsi; hPrinter
0x180004971  call    ?GetDriverInfoFromPrinter@@YAKPEAXPEAPEAEK@Z; GetDriverInfoFromPrinter(void *,uchar * *,ulong)
0x180004976  cmp     eax, 7Ch ; '|'
0x180004979  jnz     short loc_1800049A4
0x18000497b  lea     edi, [rax-76h]
0x18000497e  mov     r8d, edi; unsigned int
0x180004981  lea     rdx, [rbp+arg_18]; unsigned __int8 **
0x180004985  mov     rcx, rsi; hPrinter
0x180004988  call    ?GetDriverInfoFromPrinter@@YAKPEAXPEAPEAEK@Z; GetDriverInfoFromPrinter(void *,uchar * *,ulong)
0x18000498d  cmp     eax, 7Ch ; '|'
0x180004990  jnz     short loc_1800049A4
0x180004992  lea     edi, [rax-7Bh]
0x180004995  mov     r8d, edi; unsigned int
0x180004998  lea     rdx, [rbp+arg_18]; unsigned __int8 **
0x18000499c  mov     rcx, rsi; hPrinter
0x18000499f  call    ?GetDriverInfoFromPrinter@@YAKPEAXPEAPEAEK@Z; GetDriverInfoFromPrinter(void *,uchar * *,ulong)
0x1800049a4  mov     [rsp+60h+var_30], 0; unsigned int *
0x1800049ad  mov     [rsp+60h+var_38], 0; struct _DEVPROPERTY **
0x1800049b6  lea     rax, [rbp+arg_10]
0x1800049ba  mov     [rsp+60h+var_40], rax; unsigned int *
0x1800049bf  lea     r9, [rbp+var_10]; struct _DEVPROPERTY **
0x1800049c3  mov     r8d, edi; unsigned int
0x1800049c6  mov     r13, [rbp+arg_18]
0x1800049ca  mov     rdx, r13; unsigned __int8 *
0x1800049cd  mov     rcx, [rbp+var_20]; struct _PRINTER_INFO_2W *
0x1800049d1  call    ?BuildDevnodeProperties@@YAJPEAU_PRINTER_INFO_2W@@PEAEKPEAPEAU_DEVPROPERTY@@PEAK23@Z; BuildDevnodeProperties(_PRINTER_INFO_2W *,uchar *,ulong,_DEVPROPERTY * *,ulong *,_DEVPROPERTY * *,ulong *)
0x1800049d6  mov     edi, eax
0x1800049d8  mov     r14, [rbp+var_10]
0x1800049dc  mov     r12d, [rbp+arg_10]
0x1800049e0  test    edi, edi
0x1800049e2  js      short loc_180004A62
0x1800049e4  call    RevertToPrinterSelf
0x1800049e9  mov     rsi, rax
0x1800049ec  test    rax, rax
0x1800049ef  jnz     short loc_1800049FC
0x1800049f1  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800049f6  mov     edi, eax
0x1800049f8  test    eax, eax
0x1800049fa  js      short loc_180004A62
0x1800049fc  test    r14, r14
0x1800049ff  jnz     short loc_180004A08
0x180004a01  mov     edi, 80070057h
0x180004a06  jmp     short loc_180004A46
0x180004a08  mov     rcx, r15; this
0x180004a0b  call    ?MarkObjectInUse@DeviceObject@@IEAAJXZ; DeviceObject::MarkObjectInUse(void)
0x180004a10  mov     edi, eax
0x180004a12  test    eax, eax
0x180004a14  js      short loc_180004A46
0x180004a16  mov     rcx, [r15+10h]
0x180004a1a  test    rcx, rcx
0x180004a1d  jz      short loc_180004A39
0x180004a1f  mov     r8, r14
0x180004a22  mov     edx, r12d
0x180004a25  call    cs:__imp_SwDevicePropertySet
0x180004a2b  mov     edi, eax
0x180004a2d  cmp     eax, 80070032h
0x180004a32  jnz     short loc_180004A3E
0x180004a34  lea     edi, [rax-1Dh]
0x180004a37  jmp     short loc_180004A3E
0x180004a39  mov     edi, 8007139Fh
0x180004a3e  mov     rcx, r15; this
0x180004a41  call    ?UnmarkObjectInUse@DeviceObject@@IEAAXXZ; DeviceObject::UnmarkObjectInUse(void)
0x180004a46  test    rsi, rsi
0x180004a49  jz      short loc_180004A62
0x180004a4b  mov     rcx, rsi; hToken
0x180004a4e  call    ImpersonatePrinterClient
0x180004a53  test    eax, eax
0x180004a55  jnz     short loc_180004A62
0x180004a57  test    edi, edi
0x180004a59  js      short loc_180004A62
0x180004a5b  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180004a60  mov     edi, eax
0x180004a62  mov     edx, r12d; unsigned int
0x180004a65  mov     rcx, r14; struct _DEVPROPERTY *
0x180004a68  call    ?FreeDevPropertyList@@YAXPEAU_DEVPROPERTY@@K@Z; FreeDevPropertyList(_DEVPROPERTY *,ulong)
0x180004a6d  mov     rcx, [rbp+var_20]
0x180004a71  call    DllFreeSplMem
0x180004a76  mov     rcx, r13
0x180004a79  call    DllFreeSplMem
0x180004a7e  nop
0x180004a7f  mov     rdx, rbx; void *
0x180004a82  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180004a87  mov     eax, edi
0x180004a89  mov     rbx, [rsp+60h+arg_0]
0x180004a91  add     rsp, 60h
0x180004a95  pop     r15
0x180004a97  pop     r14
0x180004a99  pop     r13
0x180004a9b  pop     r12
0x180004a9d  pop     rdi
0x180004a9e  pop     rsi
0x180004a9f  pop     rbp
0x180004aa0  retn
```
