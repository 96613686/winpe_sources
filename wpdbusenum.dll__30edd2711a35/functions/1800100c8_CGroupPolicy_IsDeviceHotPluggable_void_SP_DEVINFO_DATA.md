# CGroupPolicy::IsDeviceHotPluggable(void *,_SP_DEVINFO_DATA *)

- ea: `0x1800100c8`
- end: `0x1800101c4`
- name: `?IsDeviceHotPluggable@CGroupPolicy@@IEAAHPEAXPEAU_SP_DEVINFO_DATA@@@Z`
- size: `252`
- prototype: `_BOOL8 __fastcall(CGroupPolicy *this, void *, struct _SP_DEVINFO_DATA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18000f390`

## callees

- `0x180002fa0`
- `0x1800100c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001018d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001018d`
- `SETUPAPI!CM_Get_DevNode_Status_Ex` at `0x180010183`
- `SETUPAPI!CM_Get_DevNode_Status_Ex` at `0x180010183`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180010117`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180010117`

## pseudocode

```c
_BOOL8 __fastcall CGroupPolicy::IsDeviceHotPluggable(CGroupPolicy *this, void *a2, struct _SP_DEVINFO_DATA *a3)
{
  DWORD LastError; // eax
  DWORD DevInst; // r8d
  DWORD v7; // eax
  ULONG pulProblemNumber[6]; // [rsp+40h] [rbp-18h] BYREF
  int v9; // [rsp+60h] [rbp+8h] BYREF
  int v10; // [rsp+64h] [rbp+Ch]
  ULONG pulStatus; // [rsp+78h] [rbp+20h] BYREF

  v10 = HIDWORD(this);
  pulStatus = 0;
  pulProblemNumber[0] = 0;
  v9 = 0;
  if ( !SetupDiGetDeviceRegistryPropertyW(a2, a3, 0xFu, 0, (PBYTE)&v9, 4u, 0) )
  {
    LastError = GetLastError();
    GPDebugPrintX(2, "Failed to retrieve capabilities. Error %d\n", LastError);
    return 0;
  }
  GPDebugPrintX(8, "Capabilities value: 0x%08x\n", v9);
  DevInst = a3->DevInst;
  pulStatus = 0;
  pulProblemNumber[0] = 0;
  if ( CM_Get_DevNode_Status_Ex(&pulStatus, pulProblemNumber, DevInst, 0, 0) )
  {
    v7 = GetLastError();
    GPDebugPrintX(2, "Failed to retrieve device status. Error %d\n", v7);
    return 0;
  }
  return (v9 & 0x8C) == 4 && ((pulStatus & 8) != 0 || (v9 & 2) != 0);
}

```

## disassembly

```asm
0x1800100c8  mov     r11, rsp
0x1800100cb  mov     [r11+8], rcx
0x1800100cf  push    rbx
0x1800100d0  sub     rsp, 50h
0x1800100d4  mov     qword ptr [r11-28h], 0
0x1800100dc  lea     rcx, [r11+8]
0x1800100e0  mov     rbx, r8
0x1800100e3  mov     [rsp+58h+PropertyBufferSize], 4; PropertyBufferSize
0x1800100eb  mov     rax, rdx
0x1800100ee  mov     [r11-38h], rcx
0x1800100f2  xor     r9d, r9d; PropertyRegDataType
0x1800100f5  mov     [rsp+58h+pulStatus], 0
0x1800100fd  mov     rdx, rbx; DeviceInfoData
0x180010100  mov     [rsp+58h+pulProblemNumber], 0
0x180010108  mov     rcx, rax; DeviceInfoSet
0x18001010b  mov     [rsp+58h+arg_0], 0
0x180010113  lea     r8d, [r9+0Fh]; Property
0x180010117  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x18001011d  test    eax, eax
0x18001011f  jnz     short loc_180010143
0x180010121  call    cs:__imp_GetLastError
0x180010127  lea     rdx, aFailedToRetrie; "Failed to retrieve capabilities. Error "...
0x18001012e  mov     r8d, eax
0x180010131  mov     ecx, 2; unsigned int
0x180010136  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18001013b  xor     eax, eax
0x18001013d  add     rsp, 50h
0x180010141  pop     rbx
0x180010142  retn
0x180010143  mov     r8d, [rsp+58h+arg_0]
0x180010148  lea     rdx, aCapabilitiesVa; "Capabilities value: 0x%08x\n"
0x18001014f  mov     ecx, 8; unsigned int
0x180010154  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010159  mov     r8d, [rbx+14h]; dnDevInst
0x18001015d  lea     rdx, [rsp+58h+pulProblemNumber]; pulProblemNumber
0x180010162  xor     r9d, r9d; ulFlags
0x180010165  mov     [rsp+58h+pulStatus], 0
0x18001016d  lea     rcx, [rsp+58h+pulStatus]; pulStatus
0x180010172  mov     [rsp+58h+pulProblemNumber], 0
0x18001017a  mov     [rsp+58h+hMachine], 0; hMachine
0x180010183  call    cs:__imp_CM_Get_DevNode_Status_Ex
0x180010189  test    eax, eax
0x18001018b  jz      short loc_18001019C
0x18001018d  call    cs:__imp_GetLastError
0x180010193  lea     rdx, aFailedToRetrie_0; "Failed to retrieve device status. Error"...
0x18001019a  jmp     short loc_18001012E
0x18001019c  mov     eax, [rsp+58h+arg_0]
0x1800101a0  and     al, 8Ch
0x1800101a2  cmp     al, 4
0x1800101a4  jnz     short loc_18001013B
0x1800101a6  test    byte ptr [rsp+58h+pulStatus], 8
0x1800101ab  setz    cl
0x1800101ae  test    byte ptr [rsp+58h+arg_0], 2
0x1800101b3  setz    al
0x1800101b6  test    al, cl
0x1800101b8  jnz     short loc_18001013B
0x1800101ba  mov     eax, 1
0x1800101bf  jmp     loc_18001013D
```
