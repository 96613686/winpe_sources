# ReadManifestAssignedValue

- ea: `0x140043db8`
- end: `0x140043eb4`
- name: `ReadManifestAssignedValue`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140044054`

## callees

- `0x1400024b8`
- `0x140043db8`
- `0x140044698`
- `0x1400448f0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140043ea1`
- `ntoskrnl!ZwClose` at `0x140043ea1`

## string_xrefs

- `0x140043dcc`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\USB`

## pseudocode

```c
int __fastcall ReadManifestAssignedValue(int *a1)
{
  int result; // eax
  int v3; // edx
  int v4; // r9d
  int v5; // [rsp+28h] [rbp-10h]
  int v6; // [rsp+28h] [rbp-10h]
  HANDLE Handle; // [rsp+40h] [rbp+8h] BYREF

  Handle = 0;
  *a1 = 0;
  result = MyRegOpenKeyForRead((__int64)a1, L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\USB", &Handle);
  if ( result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_10;
    v4 = 17;
    goto LABEL_4;
  }
  result = MyRegQueryUlong(Handle);
  if ( result >= 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 4;
      v6 = *a1;
      result = WPP_RECORDER_SF_d(
                 WPP_GLOBAL_Control->DeviceExtension,
                 v3,
                 1,
                 19,
                 (__int64)WPP_5169c4c8089132207a438b4341aed5b6_Traceguids,
                 v6);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v4 = 18;
LABEL_4:
    v5 = result;
    LOBYTE(v3) = 2;
    result = WPP_RECORDER_SF_d(
               WPP_GLOBAL_Control->DeviceExtension,
               v3,
               1,
               v4,
               (__int64)WPP_5169c4c8089132207a438b4341aed5b6_Traceguids,
               v5);
  }
LABEL_10:
  if ( Handle )
    return ZwClose(Handle);
  return result;
}

```

## disassembly

```asm
0x140043db8  push    rbx
0x140043dba  sub     rsp, 30h
0x140043dbe  lea     r8, [rsp+38h+Handle]
0x140043dc3  mov     [rsp+38h+Handle], 0
0x140043dcc  lea     rdx, aRegistryMachin_11; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140043dd3  mov     dword ptr [rcx], 0
0x140043dd9  mov     rbx, rcx
0x140043ddc  call    MyRegOpenKeyForRead
0x140043de1  test    eax, eax
0x140043de3  jns     short loc_140043E29
0x140043de5  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043dec  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140043df3  jz      loc_140043E97
0x140043df9  mov     r9d, 11h
0x140043dff  mov     rcx, cs:WPP_GLOBAL_Control
0x140043e06  mov     r8d, 1
0x140043e0c  mov     [rsp+38h+var_10], eax
0x140043e10  mov     dl, 2
0x140043e12  lea     rax, WPP_5169c4c8089132207a438b4341aed5b6_Traceguids
0x140043e19  mov     [rsp+38h+var_18], rax
0x140043e1e  mov     rcx, [rcx+40h]
0x140043e22  call    WPP_RECORDER_SF_d
0x140043e27  jmp     short loc_140043E97
0x140043e29  mov     rcx, [rsp+38h+Handle]; KeyHandle
0x140043e2e  lea     rdx, aDualrolefeatur_0; "DualRoleFeatures"
0x140043e35  mov     r8, rbx
0x140043e38  call    MyRegQueryUlong
0x140043e3d  test    eax, eax
0x140043e3f  jns     short loc_140043E59
0x140043e41  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043e48  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140043e4f  jz      short loc_140043E97
0x140043e51  mov     r9d, 12h
0x140043e57  jmp     short loc_140043DFF
0x140043e59  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043e60  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140043e67  jz      short loc_140043E97
0x140043e69  mov     eax, [rbx]
0x140043e6b  mov     r9d, 13h
0x140043e71  mov     rcx, cs:WPP_GLOBAL_Control
0x140043e78  mov     dl, 4
0x140043e7a  mov     [rsp+38h+var_10], eax
0x140043e7e  lea     rax, WPP_5169c4c8089132207a438b4341aed5b6_Traceguids
0x140043e85  mov     [rsp+38h+var_18], rax
0x140043e8a  lea     r8d, [r9-12h]
0x140043e8e  mov     rcx, [rcx+40h]
0x140043e92  call    WPP_RECORDER_SF_d
0x140043e97  mov     rcx, [rsp+38h+Handle]; Handle
0x140043e9c  test    rcx, rcx
0x140043e9f  jz      short loc_140043EAD
0x140043ea1  call    cs:__imp_ZwClose
0x140043ea8  nop     dword ptr [rax+rax+00h]
0x140043ead  add     rsp, 30h
0x140043eb1  pop     rbx
0x140043eb2  retn
```
