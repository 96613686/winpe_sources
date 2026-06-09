# TurnOffEmd

- ea: `0x140012984`
- end: `0x140012a86`
- name: `TurnOffEmd`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14000e630`

## callees

- `0x140012984`
- `0x14003ec14`
- `0x1400530a8`
- `0x14008be98`
- `0x14008bf28`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400129fd`
- `KERNEL32!GetLastError` at `0x1400129fd`
- `ntdll!RtlNtStatusToDosError` at `0x1400129d1`
- `ntdll!RtlNtStatusToDosError` at `0x1400129d1`

## string_xrefs

- `0x1400129e9`: `ERROR: Could not disable cache hits: %x\n`
- `0x1400129b4`: `ERROR: Could not open control handle: %x\n`
- `0x140012a32`: `> Unable to Query and/or configure EMD device: %s`
- `0x140012a4e`: `> EMD service will be restored on exit.`

## pseudocode

```c
void __fastcall TurnOffEmd(__int64 a1)
{
  __int64 v1; // rcx
  NTSTATUS ControlDeviceHandle; // ebx
  ULONG v3; // eax
  char Buffer[512]; // [rsp+20h] [rbp-228h] BYREF
  DWORD LastError; // [rsp+220h] [rbp-28h]
  char v6; // [rsp+224h] [rbp-24h]
  __int64 v7; // [rsp+228h] [rbp-20h]

  if ( *(_BYTE *)(a1 + 17) )
  {
    ControlDeviceHandle = SmuGetControlDeviceHandle();
    if ( ControlDeviceHandle >= 0 )
    {
      ControlDeviceHandle = SmuCacheHitsControl(v1, 1);
      if ( ControlDeviceHandle >= 0 )
      {
        v3 = 0;
LABEL_8:
        if ( v3 )
        {
          v6 = 1;
          LastError = GetLastError();
          v7 = 0;
          mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
          Log_Text_F(
            (__int64)"base\\winsat\\exe\\main.cpp",
            2492,
            "> Unable to Query and/or configure EMD device: %s",
            Buffer);
          byte_1401C1258 = 0;
        }
        else
        {
          byte_1401C1258 = 1;
          Log_Text_F((__int64)"base\\winsat\\exe\\main.cpp", 2496, "> EMD service will be restored on exit.");
        }
        return;
      }
      Log_Text_F(
        (__int64)"base\\winsat\\exe\\main.cpp",
        2473,
        "ERROR: Could not disable cache hits: %x\n",
        (unsigned int)ControlDeviceHandle);
    }
    else
    {
      Log_Text_F(
        (__int64)"base\\winsat\\exe\\main.cpp",
        2466,
        "ERROR: Could not open control handle: %x\n",
        (unsigned int)ControlDeviceHandle);
    }
    v3 = RtlNtStatusToDosError(ControlDeviceHandle);
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x140012984  push    rbx
0x140012986  sub     rsp, 240h
0x14001298d  mov     rax, cs:__security_cookie
0x140012994  xor     rax, rsp
0x140012997  mov     [rsp+248h+var_18], rax
0x14001299f  cmp     byte ptr [rcx+11h], 0
0x1400129a3  jz      loc_140012A6D
0x1400129a9  call    SmuGetControlDeviceHandle
0x1400129ae  mov     ebx, eax
0x1400129b0  test    eax, eax
0x1400129b2  jns     short loc_1400129D9
0x1400129b4  lea     r8, aErrorCouldNotO; "ERROR: Could not open control handle: %"...
0x1400129bb  mov     edx, 9A2h
0x1400129c0  mov     r9d, ebx
0x1400129c3  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x1400129ca  call    Log_Text_F
0x1400129cf  mov     ecx, ebx; Status
0x1400129d1  call    cs:__imp_RtlNtStatusToDosError
0x1400129d7  jmp     short loc_1400129F9
0x1400129d9  mov     edx, 1
0x1400129de  call    SmuCacheHitsControl
0x1400129e3  mov     ebx, eax
0x1400129e5  test    eax, eax
0x1400129e7  jns     short loc_1400129F7
0x1400129e9  lea     r8, aErrorCouldNotD; "ERROR: Could not disable cache hits: %x"...
0x1400129f0  mov     edx, 9A9h
0x1400129f5  jmp     short loc_1400129C0
0x1400129f7  xor     eax, eax
0x1400129f9  test    eax, eax
0x1400129fb  jz      short loc_140012A4E
0x1400129fd  call    cs:__imp_GetLastError
0x140012a03  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x140012a08  mov     [rsp+248h+var_24], 1
0x140012a10  mov     [rsp+248h+var_28], eax
0x140012a17  mov     [rsp+248h+var_20], 0
0x140012a23  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140012a28  lea     r9, [rsp+248h+Buffer]
0x140012a2d  mov     edx, 9BCh
0x140012a32  lea     r8, aUnableToQueryA; "> Unable to Query and/or configure EMD "...
0x140012a39  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x140012a40  call    Log_Text_F
0x140012a45  mov     cs:byte_1401C1258, 0
0x140012a4c  jmp     short loc_140012A6D
0x140012a4e  lea     r8, aEmdServiceWill; "> EMD service will be restored on exit."
0x140012a55  mov     cs:byte_1401C1258, 1
0x140012a5c  mov     edx, 9C0h
0x140012a61  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x140012a68  call    Log_Text_F
0x140012a6d  mov     rcx, [rsp+248h+var_18]
0x140012a75  xor     rcx, rsp; StackCookie
0x140012a78  call    __security_check_cookie
0x140012a7d  add     rsp, 240h
0x140012a84  pop     rbx
0x140012a85  retn
```
