# CheckUSBFnIncludeDefaultCfg

- ea: `0x140043a24`
- end: `0x140043bf8`
- name: `CheckUSBFnIncludeDefaultCfg`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140044054`

## callees

- `0x1400024b8`
- `0x140043a24`
- `0x140044698`
- `0x1400448f0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140043b32`
- `ntoskrnl!ZwClose` at `0x140043bd4`
- `ntoskrnl!ZwClose` at `0x140043b32`
- `ntoskrnl!ZwClose` at `0x140043bd4`

## string_xrefs

- `0x140043a42`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\USBFN\Default`
- `0x140043b4a`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\USBFN`

## pseudocode

```c
char __fastcall CheckUSBFnIncludeDefaultCfg(__int64 a1)
{
  NTSTATUS v1; // eax
  int v2; // edx
  int v3; // r9d
  int Ulong; // eax
  int v5; // edx
  __int64 v6; // rcx
  HANDLE Handle; // [rsp+48h] [rbp+18h] BYREF

  Handle = 0;
  v1 = MyRegOpenKeyForRead(a1, L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\USBFN\\Default", &Handle);
  if ( v1 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_18;
    v3 = 20;
    goto LABEL_4;
  }
  Ulong = MyRegQueryUlong(Handle);
  if ( Ulong >= 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        1,
        22,
        (__int64)WPP_5169c4c8089132207a438b4341aed5b6_Traceguids,
        0);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      1,
      21,
      (__int64)WPP_5169c4c8089132207a438b4341aed5b6_Traceguids,
      Ulong);
  }
  ZwClose(Handle);
  Handle = 0;
  v1 = MyRegOpenKeyForRead(v6, L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\USBFN", &Handle);
  if ( v1 >= 0 )
  {
    v1 = MyRegQueryUlong(Handle);
    if ( v1 >= 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v2) = 4;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v2,
          1,
          25,
          (__int64)WPP_5169c4c8089132207a438b4341aed5b6_Traceguids,
          0);
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v3 = 24;
      goto LABEL_4;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v3 = 23;
LABEL_4:
    LOBYTE(v2) = 4;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v2,
      1,
      v3,
      (__int64)WPP_5169c4c8089132207a438b4341aed5b6_Traceguids,
      v1);
  }
LABEL_18:
  if ( Handle )
    ZwClose(Handle);
  return 0;
}

```

## disassembly

```asm
0x140043a24  mov     [rsp-8+arg_10], rbx
0x140043a29  mov     [rsp-8+arg_18], rsi
0x140043a2e  push    rbp
0x140043a2f  mov     rbp, rsp
0x140043a32  sub     rsp, 30h
0x140043a36  lea     r8, [rbp+Handle]
0x140043a3a  mov     [rbp+Handle], 0
0x140043a42  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140043a49  mov     [rbp+arg_0], 0
0x140043a50  call    MyRegOpenKeyForRead
0x140043a55  test    eax, eax
0x140043a57  jns     short loc_140043AA0
0x140043a59  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043a60  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140043a67  jz      loc_140043BCB
0x140043a6d  mov     r9d, 14h
0x140043a73  lea     rsi, WPP_5169c4c8089132207a438b4341aed5b6_Traceguids
0x140043a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140043a81  mov     r8d, 1
0x140043a87  mov     [rsp+30h+var_8], eax
0x140043a8b  mov     dl, 4
0x140043a8d  mov     [rsp+30h+var_10], rsi
0x140043a92  mov     rcx, [rcx+40h]
0x140043a96  call    WPP_RECORDER_SF_d
0x140043a9b  jmp     loc_140043BCB
0x140043aa0  mov     rcx, [rbp+Handle]; KeyHandle
0x140043aa4  lea     r8, [rbp+arg_0]
0x140043aa8  lea     rdx, aIncludedefault; "IncludeDefaultCfg"
0x140043aaf  call    MyRegQueryUlong
0x140043ab4  lea     rsi, WPP_5169c4c8089132207a438b4341aed5b6_Traceguids
0x140043abb  test    eax, eax
0x140043abd  jns     short loc_140043AF6
0x140043abf  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043ac6  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140043acd  jz      short loc_140043B2E
0x140043acf  mov     rcx, cs:WPP_GLOBAL_Control
0x140043ad6  mov     r9d, 15h
0x140043adc  mov     [rsp+30h+var_8], eax
0x140043ae0  mov     dl, 4
0x140043ae2  mov     [rsp+30h+var_10], rsi
0x140043ae7  mov     rcx, [rcx+40h]
0x140043aeb  lea     r8d, [r9-14h]
0x140043aef  call    WPP_RECORDER_SF_d
0x140043af4  jmp     short loc_140043B2E
0x140043af6  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043afd  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140043b04  jz      short loc_140043B2E
0x140043b06  mov     rcx, cs:WPP_GLOBAL_Control
0x140043b0d  mov     r9d, 16h
0x140043b13  mov     eax, [rbp+arg_0]
0x140043b16  mov     dl, 4
0x140043b18  mov     [rsp+30h+var_8], eax
0x140043b1c  mov     [rsp+30h+var_10], rsi
0x140043b21  mov     rcx, [rcx+40h]
0x140043b25  lea     r8d, [r9-15h]
0x140043b29  call    WPP_RECORDER_SF_d
0x140043b2e  mov     rcx, [rbp+Handle]; Handle
0x140043b32  call    cs:__imp_ZwClose
0x140043b39  nop     dword ptr [rax+rax+00h]
0x140043b3e  lea     r8, [rbp+Handle]
0x140043b42  mov     [rbp+Handle], 0
0x140043b4a  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140043b51  call    MyRegOpenKeyForRead
0x140043b56  test    eax, eax
0x140043b58  jns     short loc_140043B6E
0x140043b5a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x140043b61  jz      short loc_140043BCB
0x140043b63  mov     r9d, 17h
0x140043b69  jmp     loc_140043A7A
0x140043b6e  mov     rcx, [rbp+Handle]; KeyHandle
0x140043b72  lea     r8, [rbp+arg_0]
0x140043b76  lea     rdx, aIncludedefault; "IncludeDefaultCfg"
0x140043b7d  call    MyRegQueryUlong
0x140043b82  test    eax, eax
0x140043b84  jns     short loc_140043B9A
0x140043b86  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x140043b8d  jz      short loc_140043BCB
0x140043b8f  mov     r9d, 18h
0x140043b95  jmp     loc_140043A7A
0x140043b9a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x140043ba1  jz      short loc_140043BCB
0x140043ba3  mov     rcx, cs:WPP_GLOBAL_Control
0x140043baa  mov     r9d, 19h
0x140043bb0  mov     eax, [rbp+arg_0]
0x140043bb3  mov     dl, 4
0x140043bb5  mov     [rsp+30h+var_8], eax
0x140043bb9  mov     [rsp+30h+var_10], rsi
0x140043bbe  mov     rcx, [rcx+40h]
0x140043bc2  lea     r8d, [r9-18h]
0x140043bc6  call    WPP_RECORDER_SF_d
0x140043bcb  mov     rcx, [rbp+Handle]; Handle
0x140043bcf  test    rcx, rcx
0x140043bd2  jz      short loc_140043BE0
0x140043bd4  call    cs:__imp_ZwClose
0x140043bdb  nop     dword ptr [rax+rax+00h]
0x140043be0  cmp     [rbp+arg_0], 0
0x140043be4  mov     rbx, [rsp+30h+arg_10]
0x140043be9  mov     rsi, [rsp+30h+arg_18]
0x140043bee  setnz   al
0x140043bf1  add     rsp, 30h
0x140043bf5  pop     rbp
0x140043bf6  retn
```
