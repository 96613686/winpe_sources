# VhdmpiUnregisterForBootSurface(_VHD_SURFACE *)

- ea: `0x1400bb528`
- end: `0x1400bb69b`
- name: `?VhdmpiUnregisterForBootSurface@@YAJPEAU_VHD_SURFACE@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(struct _VHD_SURFACE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x140035590`

## callees

- `0x140023980`
- `0x14002d104`
- `0x140036284`
- `0x14005e100`
- `0x1400bb0ec`
- `0x1400bb528`

## import_xrefs

- `ntoskrnl!ZwDeleteKey` at `0x1400bb619`
- `ntoskrnl!ZwDeleteKey` at `0x1400bb619`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400bb605`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400bb605`
- `ntoskrnl!ZwClose` at `0x1400bb634`
- `ntoskrnl!ZwClose` at `0x1400bb634`

## pseudocode

```c
__int64 __fastcall VhdmpiUnregisterForBootSurface(struct _VHD_SURFACE *a1)
{
  NTSTATUS v2; // ebx
  unsigned int v3; // edx
  unsigned __int8 v4; // r8
  int v5; // eax
  unsigned __int8 v6; // r8
  unsigned int v7; // r9d
  _QWORD v9[15]; // [rsp+30h] [rbp-78h] BYREF
  HANDLE KeyHandle; // [rsp+B8h] [rbp+10h] BYREF

  KeyHandle = 0;
  memset(v9, 0, 0x70u);
  if ( (unsigned int)Feature_Servicing_VhdRetainBootAttachOnDismount__private_IsEnabledDeviceUsageNoInline()
    && (*((_DWORD *)a1 + 14) & 0x80u) != 0 )
  {
    v2 = 0;
  }
  else
  {
    if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents("VhdmpiUnregisterForBootSurface", 0x1288u, v4, v3, "VhdmpiUnregisterForBootSurface: enter %p...", a1);
    v5 = VhdmpiOpenAutoAttachRegistryKey(&KeyHandle, (__int64)a1, 1);
    if ( v5 >= 0 )
    {
      v9[0] = VhdmpiVhd2SetProjectedEofForNewBackingStoreFile;
      LODWORD(v9[1]) = 72;
      RtlQueryRegistryValuesEx(0x40000000, KeyHandle, v9, 0, 0);
      v2 = ZwDeleteKey(KeyHandle);
    }
    else
    {
      v2 = 0;
      if ( v5 != -1073741772 )
        v2 = v5;
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v2 < 0 && (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
    TraceEvents("VhdmpiUnregisterForBootSurface", 0x12A7u, v6, v7, "Return with status 0x%08X", v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400bb528  mov     rax, rsp
0x1400bb52b  push    rbx
0x1400bb52c  sub     rsp, 0A0h
0x1400bb533  xor     edx, edx; Val
0x1400bb535  mov     qword ptr [rax+10h], 0
0x1400bb53d  mov     rbx, rcx
0x1400bb540  lea     rcx, [rax-78h]; void *
0x1400bb544  lea     r8d, [rdx+70h]; Size
0x1400bb548  call    memset
0x1400bb54d  call    Feature_Servicing_VhdRetainBootAttachOnDismount__private_IsEnabledDeviceUsageNoInline
0x1400bb552  test    eax, eax
0x1400bb554  jz      short loc_1400BB564
0x1400bb556  mov     eax, [rbx+38h]
0x1400bb559  test    al, al
0x1400bb55b  jns     short loc_1400BB564
0x1400bb55d  xor     ebx, ebx
0x1400bb55f  jmp     loc_1400BB627
0x1400bb564  mov     eax, cs:dword_1400876D0
0x1400bb56a  mov     r8d, 5
0x1400bb570  cmp     eax, r8d
0x1400bb573  jbe     short loc_1400BB5B0
0x1400bb575  lea     edx, [r8+0Bh]
0x1400bb579  lea     rcx, dword_1400876D0
0x1400bb580  call    _tlgKeywordOn
0x1400bb585  test    al, al
0x1400bb587  jz      short loc_1400BB5B0
0x1400bb589  mov     ecx, 1288h
0x1400bb58e  mov     qword ptr [rsp+0A8h+var_80], rbx; char
0x1400bb593  mov     r9d, edx; int
0x1400bb596  lea     rax, aVhdmpiunregist_0; "VhdmpiUnregisterForBootSurface: enter %"...
0x1400bb59d  mov     edx, ecx; int
0x1400bb59f  mov     [rsp+0A8h+var_88], rax; char *
0x1400bb5a4  lea     rcx, aVhdmpiunregist_1; "VhdmpiUnregisterForBootSurface"
0x1400bb5ab  call    TraceEvents
0x1400bb5b0  mov     r8b, 1
0x1400bb5b3  lea     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x1400bb5bb  mov     rdx, rbx
0x1400bb5be  call    VhdmpiOpenAutoAttachRegistryKey
0x1400bb5c3  test    eax, eax
0x1400bb5c5  jns     short loc_1400BB5D3
0x1400bb5c7  xor     ebx, ebx
0x1400bb5c9  cmp     eax, 0C0000034h
0x1400bb5ce  cmovnz  ebx, eax
0x1400bb5d1  jmp     short loc_1400BB627
0x1400bb5d3  mov     rdx, [rsp+0A8h+KeyHandle]
0x1400bb5db  lea     rax, ?VhdmpiVhd2SetProjectedEofForNewBackingStoreFile@@YAJPEAU_VHD_BACKING_STORE_HEADER@@@Z; VhdmpiVhd2SetProjectedEofForNewBackingStoreFile(_VHD_BACKING_STORE_HEADER *)
0x1400bb5e2  xor     r9d, r9d
0x1400bb5e5  mov     [rsp+0A8h+var_78], rax
0x1400bb5ea  lea     r8, [rsp+0A8h+var_78]
0x1400bb5ef  mov     [rsp+0A8h+var_70], 48h ; 'H'
0x1400bb5f7  mov     ecx, 40000000h
0x1400bb5fc  mov     [rsp+0A8h+var_88], 0
0x1400bb605  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400bb60c  nop     dword ptr [rax+rax+00h]
0x1400bb611  mov     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x1400bb619  call    cs:__imp_ZwDeleteKey
0x1400bb620  nop     dword ptr [rax+rax+00h]
0x1400bb625  mov     ebx, eax
0x1400bb627  mov     rcx, [rsp+0A8h+KeyHandle]; Handle
0x1400bb62f  test    rcx, rcx
0x1400bb632  jz      short loc_1400BB640
0x1400bb634  call    cs:__imp_ZwClose
0x1400bb63b  nop     dword ptr [rax+rax+00h]
0x1400bb640  test    ebx, ebx
0x1400bb642  jns     short loc_1400BB68F
0x1400bb644  mov     edx, cs:dword_1400876D0
0x1400bb64a  mov     r8d, 2
0x1400bb650  cmp     edx, r8d
0x1400bb653  jbe     short loc_1400BB68F
0x1400bb655  mov     r9d, 80000h
0x1400bb65b  lea     rcx, dword_1400876D0
0x1400bb662  mov     edx, r9d
0x1400bb665  call    _tlgKeywordOn
0x1400bb66a  test    al, al
0x1400bb66c  jz      short loc_1400BB68F
0x1400bb66e  lea     rax, aReturnWithStat_23; "Return with status 0x%08X"
0x1400bb675  mov     dword ptr [rsp+0A8h+var_80], ebx; char
0x1400bb679  mov     edx, 12A7h; int
0x1400bb67e  mov     [rsp+0A8h+var_88], rax; char *
0x1400bb683  lea     rcx, aVhdmpiunregist_1; "VhdmpiUnregisterForBootSurface"
0x1400bb68a  call    TraceEvents
0x1400bb68f  mov     eax, ebx
0x1400bb691  add     rsp, 0A0h
0x1400bb698  pop     rbx
0x1400bb699  retn
```
