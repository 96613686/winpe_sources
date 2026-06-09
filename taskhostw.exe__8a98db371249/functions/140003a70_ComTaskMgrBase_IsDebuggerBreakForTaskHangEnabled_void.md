# ComTaskMgrBase::IsDebuggerBreakForTaskHangEnabled(void)

- ea: `0x140003a70`
- end: `0x140003b08`
- name: `?IsDebuggerBreakForTaskHangEnabled@ComTaskMgrBase@@KAHXZ`
- size: `152`
- prototype: `_BOOL8(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140003270`
- `0x140003880`

## callees

- `0x140003a70`
- `0x140009330`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003ab8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003ab8`

## string_xrefs

- `0x140003a88`: `EnableDebuggerBreakForTaskHang`

## pseudocode

```c
_BOOL8 ComTaskMgrBase::IsDebuggerBreakForTaskHangEnabled(void)
{
  unsigned int ValueW; // eax
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF

  pcbData = 4;
  pvData = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule",
             L"EnableDebuggerBreakForTaskHang",
             0x10u,
             0,
             &pvData,
             &pcbData);
  if ( !ValueW )
    return pvData != 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids, ValueW);
  return 0;
}

```

## disassembly

```asm
0x140003a70  push    rbx
0x140003a72  sub     rsp, 40h
0x140003a76  lea     rax, [rsp+48h+arg_8]
0x140003a7b  mov     [rsp+48h+arg_8], 4
0x140003a83  mov     [rsp+48h+pcbData], rax; pcbData
0x140003a88  lea     r8, Value; "EnableDebuggerBreakForTaskHang"
0x140003a8f  lea     rax, [rsp+48h+arg_0]
0x140003a94  xor     ebx, ebx
0x140003a96  mov     [rsp+48h+pvData], rax; pvData
0x140003a9b  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140003aa2  mov     r9d, 10h; dwFlags
0x140003aa8  mov     [rsp+48h+pdwType], rbx; pdwType
0x140003aad  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140003ab4  mov     [rsp+48h+arg_0], ebx
0x140003ab8  call    cs:__imp_RegGetValueW
0x140003abe  test    eax, eax
0x140003ac0  jz      short loc_140003AE3
0x140003ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ac9  lea     rdx, WPP_GLOBAL_Control
0x140003ad0  cmp     rcx, rdx
0x140003ad3  jz      short loc_140003ADB
0x140003ad5  test    byte ptr [rcx+1Ch], 1
0x140003ad9  jnz     short loc_140003AEE
0x140003adb  xor     eax, eax
0x140003add  add     rsp, 40h
0x140003ae1  pop     rbx
0x140003ae2  retn
0x140003ae3  cmp     [rsp+48h+arg_0], ebx
0x140003ae7  mov     eax, ebx
0x140003ae9  setnz   al
0x140003aec  jmp     short loc_140003ADD
0x140003aee  mov     rcx, [rcx+10h]
0x140003af2  lea     r8, WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids
0x140003af9  mov     edx, 0Dh
0x140003afe  mov     r9d, eax
0x140003b01  call    WPP_SF_d
0x140003b06  jmp     short loc_140003ADB
```
