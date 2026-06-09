# DbgTraceFrmt

- ea: `0x1400011b0`
- end: `0x140001291`
- name: `DbgTraceFrmt`
- size: `225`
- prototype: ``
- caller_count: `21`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400015c0`
- `0x1400016ac`
- `0x14000a120`
- `0x14000a284`
- `0x14000a3c4`
- `0x14000a55c`
- `0x14000a660`
- `0x14000ac48`
- `0x14000aca0`
- `0x14000aec4`
- `0x14000b03c`
- `0x14000b160`
- `0x14000b418`
- `0x14000b614`
- `0x14000b76c`
- `0x14000b854`
- `0x14000b908`
- `0x14000c078`
- `0x14000c1bc`
- `0x14000c4a4`
- `0x14000c55c`

## callees

- `0x1400011b0`
- `0x140001544`
- `0x140001a30`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140001246`
- `ntoskrnl!DbgPrintEx` at `0x140001246`
- `ntoskrnl!_vsnprintf` at `0x1400011fe`
- `ntoskrnl!_vsnprintf` at `0x1400011fe`

## pseudocode

```c
void DbgTraceFrmt(unsigned int a1, const char *a2, ...)
{
  unsigned int v2; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  char Dest[511]; // [rsp+30h] [rbp-218h] BYREF
  char v6; // [rsp+22Fh] [rbp-19h]
  __int64 v7; // [rsp+260h] [rbp+18h] BYREF
  va_list va; // [rsp+260h] [rbp+18h]
  va_list va1; // [rsp+268h] [rbp+20h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  v7 = va_arg(va1, _QWORD);
  if ( a1 <= g_DebugLevel )
  {
    v2 = _vsnprintf(Dest, 0x1FFu, a2, va);
    if ( v2 >= 0x200 )
    {
      v6 = 0;
      if ( (Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits & 4) != 0 )
        McTemplateK0s_EtwWriteTransfer(
          v3,
          (const EVENT_DESCRIPTOR *)Trace_Error,
          v4,
          "StringCchPrintfA() in DbgTraceFrmt() failed: Insufficient buffer");
    }
    else
    {
      if ( v2 == 511 )
        v6 = 0;
      if ( (Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits & 0x20) != 0 )
        McTemplateK0s_EtwWriteTransfer(v3, (const EVENT_DESCRIPTOR *)Trace_Verbose, v4, Dest);
      DbgPrintEx(0x4Du, 2u, Dest);
    }
  }
}

```

## disassembly

```asm
0x1400011b0  mov     r11, rsp
0x1400011b3  mov     [r11+10h], rdx
0x1400011b7  mov     [r11+18h], r8
0x1400011bb  mov     [r11+20h], r9
0x1400011bf  sub     rsp, 248h
0x1400011c6  mov     rax, cs:__security_cookie
0x1400011cd  xor     rax, rsp
0x1400011d0  mov     [rsp+248h+var_18], rax
0x1400011d8  cmp     ecx, cs:g_DebugLevel
0x1400011de  mov     [rsp+248h+var_228], 0
0x1400011e7  ja      loc_140001278
0x1400011ed  mov     r8, rdx; Format
0x1400011f0  lea     r9, [r11+18h]; Args
0x1400011f4  mov     edx, 1FFh; Count
0x1400011f9  lea     rcx, [rsp+248h+Dest]; Dest
0x1400011fe  call    cs:__imp__vsnprintf
0x140001205  nop     dword ptr [rax+rax+00h]
0x14000120a  test    eax, eax
0x14000120c  js      short loc_140001254
0x14000120e  cmp     eax, 1FFh
0x140001213  ja      short loc_140001254
0x140001215  jnz     short loc_14000121F
0x140001217  mov     [rsp+248h+var_19], 0
0x14000121f  test    cs:Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits, 20h
0x140001226  jz      short loc_140001239
0x140001228  lea     r9, [rsp+248h+Dest]
0x14000122d  lea     rdx, Trace_Verbose
0x140001234  call    McTemplateK0s_EtwWriteTransfer
0x140001239  mov     edx, 2; Level
0x14000123e  lea     r8, [rsp+248h+Dest]; Format
0x140001243  lea     ecx, [rdx+4Bh]; ComponentId
0x140001246  call    cs:__imp_DbgPrintEx
0x14000124d  nop     dword ptr [rax+rax+00h]
0x140001252  jmp     short loc_140001278
0x140001254  test    cs:Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits, 4
0x14000125b  mov     [rsp+248h+var_19], 0
0x140001263  jz      short loc_140001278
0x140001265  lea     r9, aStringcchprint_0; "StringCchPrintfA() in DbgTraceFrmt() fa"...
0x14000126c  lea     rdx, Trace_Error
0x140001273  call    McTemplateK0s_EtwWriteTransfer
0x140001278  mov     rcx, [rsp+248h+var_18]
0x140001280  xor     rcx, rsp; StackCookie
0x140001283  call    __security_check_cookie
0x140001288  add     rsp, 248h
0x14000128f  retn
```
