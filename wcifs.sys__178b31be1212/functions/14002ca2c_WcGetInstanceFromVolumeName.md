# WcGetInstanceFromVolumeName

- ea: `0x14002ca2c`
- end: `0x14002cb31`
- name: `WcGetInstanceFromVolumeName`
- size: `261`
- prototype: `__int64 __fastcall(PCUNICODE_STRING VolumeName, PCUNICODE_STRING InstanceName, PFLT_INSTANCE *RetInstance)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002520`
- `0x14001a62c`
- `0x14001fe40`
- `0x140020e60`
- `0x14002bf4c`

## callees

- `0x1400020c4`
- `0x14002ca2c`

## import_xrefs

- `FLTMGR!FltGetVolumeInstanceFromName` at `0x14002caa4`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x14002caa4`
- `FLTMGR!FltGetVolumeFromName` at `0x14002ca58`
- `FLTMGR!FltGetVolumeFromName` at `0x14002ca58`
- `FLTMGR!FltObjectDereference` at `0x14002cb12`
- `FLTMGR!FltObjectDereference` at `0x14002cb12`

## pseudocode

```c
__int64 __fastcall WcGetInstanceFromVolumeName(
        PCUNICODE_STRING VolumeName,
        PCUNICODE_STRING InstanceName,
        PFLT_INSTANCE *RetInstance)
{
  NTSTATUS VolumeFromName; // eax
  int v6; // edx
  unsigned int v7; // ebx
  int v8; // r9d
  NTSTATUS VolumeInstanceFromName; // eax
  char v11; // [rsp+30h] [rbp-18h]
  char v12; // [rsp+38h] [rbp-10h]
  PFLT_VOLUME Volume; // [rsp+68h] [rbp+20h] BYREF

  Volume = 0;
  VolumeFromName = FltGetVolumeFromName(Globals, VolumeName, &Volume);
  v7 = VolumeFromName;
  if ( VolumeFromName < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_8;
    v12 = VolumeFromName;
    v8 = 201;
    v11 = 84;
    goto LABEL_7;
  }
  VolumeInstanceFromName = FltGetVolumeInstanceFromName(Globals, Volume, InstanceName, RetInstance);
  v7 = VolumeInstanceFromName;
  if ( VolumeInstanceFromName < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v12 = VolumeInstanceFromName;
    v8 = 202;
    v11 = 91;
LABEL_7:
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_sDd(
      wil_details_featureDescriptors_a->DeviceExtension,
      v6,
      14,
      v8,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      v11,
      v12);
  }
LABEL_8:
  if ( Volume )
    FltObjectDereference(Volume);
  return v7;
}

```

## disassembly

```asm
0x14002ca2c  mov     rax, rsp
0x14002ca2f  mov     [rax+8], rbx
0x14002ca33  mov     [rax+10h], rsi
0x14002ca37  push    rdi
0x14002ca38  sub     rsp, 40h
0x14002ca3c  mov     rsi, rdx
0x14002ca3f  mov     qword ptr [rax+20h], 0
0x14002ca47  mov     rdx, rcx; VolumeName
0x14002ca4a  mov     rdi, r8
0x14002ca4d  mov     rcx, cs:Globals; Filter
0x14002ca54  lea     r8, [rax+20h]; RetVolume
0x14002ca58  call    cs:__imp_FltGetVolumeFromName
0x14002ca5f  nop     dword ptr [rax+rax+00h]
0x14002ca64  mov     ebx, eax
0x14002ca66  test    eax, eax
0x14002ca68  jns     short loc_14002CA92
0x14002ca6a  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002ca71  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002ca78  jz      loc_14002CB08
0x14002ca7e  mov     dword ptr [rsp+48h+var_10], eax
0x14002ca82  mov     r9d, 0C9h
0x14002ca88  mov     dword ptr [rsp+48h+var_18], 2354h
0x14002ca90  jmp     short loc_14002CAD8
0x14002ca92  mov     rdx, [rsp+48h+Volume]; Volume
0x14002ca97  mov     r9, rdi; RetInstance
0x14002ca9a  mov     rcx, cs:Globals; Filter
0x14002caa1  mov     r8, rsi; InstanceName
0x14002caa4  call    cs:__imp_FltGetVolumeInstanceFromName
0x14002caab  nop     dword ptr [rax+rax+00h]
0x14002cab0  mov     ebx, eax
0x14002cab2  test    eax, eax
0x14002cab4  jns     short loc_14002CB08
0x14002cab6  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002cabd  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002cac4  jz      short loc_14002CB08
0x14002cac6  mov     dword ptr [rsp+48h+var_10], eax
0x14002caca  mov     r9d, 0CAh
0x14002cad0  mov     dword ptr [rsp+48h+var_18], 235Bh
0x14002cad8  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002cadf  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002cae6  mov     [rsp+48h+var_20], rax
0x14002caeb  mov     r8d, 0Eh
0x14002caf1  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002caf8  mov     dl, 2
0x14002cafa  mov     [rsp+48h+var_28], rax
0x14002caff  mov     rcx, [rcx+40h]
0x14002cb03  call    WPP_RECORDER_SF_sDd
0x14002cb08  mov     rcx, [rsp+48h+Volume]; FltObject
0x14002cb0d  test    rcx, rcx
0x14002cb10  jz      short loc_14002CB1E
0x14002cb12  call    cs:__imp_FltObjectDereference
0x14002cb19  nop     dword ptr [rax+rax+00h]
0x14002cb1e  mov     rsi, [rsp+48h+arg_8]
0x14002cb23  mov     eax, ebx
0x14002cb25  mov     rbx, [rsp+48h+arg_0]
0x14002cb2a  add     rsp, 40h
0x14002cb2e  pop     rdi
0x14002cb2f  retn
```
