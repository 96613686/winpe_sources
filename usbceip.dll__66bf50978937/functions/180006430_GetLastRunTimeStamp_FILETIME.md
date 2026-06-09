# GetLastRunTimeStamp(_FILETIME *)

- ea: `0x180006430`
- end: `0x1800064a7`
- name: `?GetLastRunTimeStamp@@YAXPEAU_FILETIME@@@Z`
- size: `119`
- prototype: `void __fastcall(struct _FILETIME *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180005da0`
- `0x180006320`
- `0x1800065f8`

## callees

- `0x180006430`
- `0x18000bc7c`
- `0x18000bd24`
- `0x18000c114`

## string_xrefs

- `0x18000646c`: `UsbCeipTaskLastRunTimestamp`

## pseudocode

```c
void __fastcall GetLastRunTimeStamp(struct _FILETIME *a1)
{
  HKEY phkResult[5]; // [rsp+20h] [rbp-28h] BYREF
  struct _FILETIME v3; // [rsp+58h] [rbp+10h] BYREF

  CRegistryKey::CRegistryKey(phkResult, HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Usb\\Ceip");
  v3 = 0;
  if ( CRegistryKey::QueryFixedLengthValue(
         (CRegistryKey *)phkResult,
         L"UsbCeipTaskLastRunTimestamp",
         8u,
         (unsigned __int8 *)&v3) )
  {
    *a1 = v3;
  }
  else
  {
    *a1 = 0;
  }
  CRegistryKey::~CRegistryKey((CRegistryKey *)phkResult);
}

```

## disassembly

```asm
0x180006430  push    rbx
0x180006432  sub     rsp, 40h
0x180006436  mov     rbx, rcx
0x180006439  mov     r9d, 1; unsigned int
0x18000643f  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Usb"...
0x180006446  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18000644d  lea     rcx, [rsp+48h+phkResult]; phkResult
0x180006452  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)
0x180006457  nop
0x180006458  mov     [rsp+48h+arg_8], 0
0x180006461  lea     r9, [rsp+48h+arg_8]; unsigned __int8 *
0x180006466  mov     r8d, 8; unsigned int
0x18000646c  lea     rdx, aUsbceiptasklas; "UsbCeipTaskLastRunTimestamp"
0x180006473  lea     rcx, [rsp+48h+phkResult]; this
0x180006478  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x18000647d  test    al, al
0x18000647f  jz      short loc_180006490
0x180006481  mov     eax, dword ptr [rsp+48h+arg_8]
0x180006485  mov     [rbx], eax
0x180006487  mov     eax, dword ptr [rsp+48h+arg_8+4]
0x18000648b  mov     [rbx+4], eax
0x18000648e  jmp     short loc_180006497
0x180006490  mov     qword ptr [rbx], 0
0x180006497  lea     rcx, [rsp+48h+phkResult]; this
0x18000649c  call    ??1CRegistryKey@@QEAA@XZ; CRegistryKey::~CRegistryKey(void)
0x1800064a1  add     rsp, 40h
0x1800064a5  pop     rbx
0x1800064a6  retn
```
