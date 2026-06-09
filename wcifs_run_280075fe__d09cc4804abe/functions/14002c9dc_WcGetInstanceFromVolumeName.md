# WcGetInstanceFromVolumeName

- ea: `0x14002c9dc`
- end: `0x14002cae1`
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
- `0x14002befc`

## callees

- `0x1400020c4`
- `0x14002c9dc`

## import_xrefs

- `FLTMGR!FltGetVolumeInstanceFromName` at `0x14002ca54`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x14002ca54`
- `FLTMGR!FltGetVolumeFromName` at `0x14002ca08`
- `FLTMGR!FltGetVolumeFromName` at `0x14002ca08`
- `FLTMGR!FltObjectDereference` at `0x14002cac2`
- `FLTMGR!FltObjectDereference` at `0x14002cac2`

## pseudocode

```c
__int64 __fastcall WcGetInstanceFromVolumeName(
        PCUNICODE_STRING VolumeName,
        PCUNICODE_STRING InstanceName,
        PFLT_INSTANCE *RetInstance)
{
  NTSTATUS VolumeFromName; // eax
  unsigned int v6; // ebx
  unsigned __int16 v7; // r9
  NTSTATUS VolumeInstanceFromName; // eax
  int v10; // [rsp+30h] [rbp-18h]
  NTSTATUS v11; // [rsp+38h] [rbp-10h]
  PFLT_VOLUME Volume; // [rsp+68h] [rbp+20h] BYREF

  Volume = 0;
  VolumeFromName = FltGetVolumeFromName(Globals, VolumeName, &Volume);
  v6 = VolumeFromName;
  if ( VolumeFromName < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_8;
    v11 = VolumeFromName;
    v7 = 201;
    v10 = 9044;
    goto LABEL_7;
  }
  VolumeInstanceFromName = FltGetVolumeInstanceFromName(Globals, Volume, InstanceName, RetInstance);
  v6 = VolumeInstanceFromName;
  if ( VolumeInstanceFromName < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v11 = VolumeInstanceFromName;
    v7 = 202;
    v10 = 9051;
LABEL_7:
    WPP_RECORDER_SF_sDd(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      2u,
      0xEu,
      v7,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      "onecore\\base\\fs\\wci\\wcifs\\utils.c",
      v10,
      v11);
  }
LABEL_8:
  if ( Volume )
    FltObjectDereference(Volume);
  return v6;
}

```

## disassembly

```asm
0x14002c9dc  mov     rax, rsp
0x14002c9df  mov     [rax+8], rbx
0x14002c9e3  mov     [rax+10h], rsi
0x14002c9e7  push    rdi
0x14002c9e8  sub     rsp, 40h
0x14002c9ec  mov     rsi, rdx
0x14002c9ef  mov     qword ptr [rax+20h], 0
0x14002c9f7  mov     rdx, rcx; VolumeName
0x14002c9fa  mov     rdi, r8
0x14002c9fd  mov     rcx, cs:Globals; Filter
0x14002ca04  lea     r8, [rax+20h]; RetVolume
0x14002ca08  call    cs:__imp_FltGetVolumeFromName
0x14002ca0f  nop     dword ptr [rax+rax+00h]
0x14002ca14  mov     ebx, eax
0x14002ca16  test    eax, eax
0x14002ca18  jns     short loc_14002CA42
0x14002ca1a  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002ca21  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002ca28  jz      loc_14002CAB8
0x14002ca2e  mov     [rsp+48h+var_10], eax
0x14002ca32  mov     r9d, 0C9h
0x14002ca38  mov     [rsp+48h+var_18], 2354h
0x14002ca40  jmp     short loc_14002CA88
0x14002ca42  mov     rdx, [rsp+48h+Volume]; Volume
0x14002ca47  mov     r9, rdi; RetInstance
0x14002ca4a  mov     rcx, cs:Globals; Filter
0x14002ca51  mov     r8, rsi; InstanceName
0x14002ca54  call    cs:__imp_FltGetVolumeInstanceFromName
0x14002ca5b  nop     dword ptr [rax+rax+00h]
0x14002ca60  mov     ebx, eax
0x14002ca62  test    eax, eax
0x14002ca64  jns     short loc_14002CAB8
0x14002ca66  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002ca6d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002ca74  jz      short loc_14002CAB8
0x14002ca76  mov     [rsp+48h+var_10], eax
0x14002ca7a  mov     r9d, 0CAh
0x14002ca80  mov     [rsp+48h+var_18], 235Bh
0x14002ca88  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ca8f  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002ca96  mov     [rsp+48h+var_20], rax
0x14002ca9b  mov     r8d, 0Eh
0x14002caa1  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002caa8  mov     dl, 2
0x14002caaa  mov     [rsp+48h+var_28], rax
0x14002caaf  mov     rcx, [rcx+40h]
0x14002cab3  call    WPP_RECORDER_SF_sDd
0x14002cab8  mov     rcx, [rsp+48h+Volume]; FltObject
0x14002cabd  test    rcx, rcx
0x14002cac0  jz      short loc_14002CACE
0x14002cac2  call    cs:__imp_FltObjectDereference
0x14002cac9  nop     dword ptr [rax+rax+00h]
0x14002cace  mov     rsi, [rsp+48h+arg_8]
0x14002cad3  mov     eax, ebx
0x14002cad5  mov     rbx, [rsp+48h+arg_0]
0x14002cada  add     rsp, 40h
0x14002cade  pop     rdi
0x14002cadf  retn
```
