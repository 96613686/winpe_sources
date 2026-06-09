# VhdmpiUnregisterForBootSurface(_VHD_SURFACE *)

- ea: `0x1400bb538`
- end: `0x1400bb6ab`
- name: `?VhdmpiUnregisterForBootSurface@@YAJPEAU_VHD_SURFACE@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(struct _VHD_SURFACE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1400351a0`

## callees

- `0x140023560`
- `0x14002cbe4`
- `0x140035e94`
- `0x14005dd00`
- `0x1400bb0fc`
- `0x1400bb538`

## import_xrefs

- `ntoskrnl!ZwDeleteKey` at `0x1400bb629`
- `ntoskrnl!ZwDeleteKey` at `0x1400bb629`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400bb615`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400bb615`
- `ntoskrnl!ZwClose` at `0x1400bb644`
- `ntoskrnl!ZwClose` at `0x1400bb644`

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
    if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
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
  if ( v2 < 0 && (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
    TraceEvents("VhdmpiUnregisterForBootSurface", 0x12A7u, v6, v7, "Return with status 0x%08X", v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400bb538  mov     rax, rsp
0x1400bb53b  push    rbx
0x1400bb53c  sub     rsp, 0A0h
0x1400bb543  xor     edx, edx; Val
0x1400bb545  mov     qword ptr [rax+10h], 0
0x1400bb54d  mov     rbx, rcx
0x1400bb550  lea     rcx, [rax-78h]; void *
0x1400bb554  lea     r8d, [rdx+70h]; Size
0x1400bb558  call    memset
0x1400bb55d  call    Feature_Servicing_VhdRetainBootAttachOnDismount__private_IsEnabledDeviceUsageNoInline
0x1400bb562  test    eax, eax
0x1400bb564  jz      short loc_1400BB574
0x1400bb566  mov     eax, [rbx+38h]
0x1400bb569  test    al, al
0x1400bb56b  jns     short loc_1400BB574
0x1400bb56d  xor     ebx, ebx
0x1400bb56f  jmp     loc_1400BB637
0x1400bb574  mov     eax, cs:dword_140087708
0x1400bb57a  mov     r8d, 5
0x1400bb580  cmp     eax, r8d
0x1400bb583  jbe     short loc_1400BB5C0
0x1400bb585  lea     edx, [r8+0Bh]
0x1400bb589  lea     rcx, dword_140087708
0x1400bb590  call    _tlgKeywordOn
0x1400bb595  test    al, al
0x1400bb597  jz      short loc_1400BB5C0
0x1400bb599  mov     ecx, 1288h
0x1400bb59e  mov     qword ptr [rsp+0A8h+var_80], rbx; char
0x1400bb5a3  mov     r9d, edx; int
0x1400bb5a6  lea     rax, aVhdmpiunregist_0; "VhdmpiUnregisterForBootSurface: enter %"...
0x1400bb5ad  mov     edx, ecx; int
0x1400bb5af  mov     [rsp+0A8h+var_88], rax; char *
0x1400bb5b4  lea     rcx, aVhdmpiunregist_1; "VhdmpiUnregisterForBootSurface"
0x1400bb5bb  call    TraceEvents
0x1400bb5c0  mov     r8b, 1
0x1400bb5c3  lea     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x1400bb5cb  mov     rdx, rbx
0x1400bb5ce  call    VhdmpiOpenAutoAttachRegistryKey
0x1400bb5d3  test    eax, eax
0x1400bb5d5  jns     short loc_1400BB5E3
0x1400bb5d7  xor     ebx, ebx
0x1400bb5d9  cmp     eax, 0C0000034h
0x1400bb5de  cmovnz  ebx, eax
0x1400bb5e1  jmp     short loc_1400BB637
0x1400bb5e3  mov     rdx, [rsp+0A8h+KeyHandle]
0x1400bb5eb  lea     rax, ?VhdmpiVhd2SetProjectedEofForNewBackingStoreFile@@YAJPEAU_VHD_BACKING_STORE_HEADER@@@Z; VhdmpiVhd2SetProjectedEofForNewBackingStoreFile(_VHD_BACKING_STORE_HEADER *)
0x1400bb5f2  xor     r9d, r9d
0x1400bb5f5  mov     [rsp+0A8h+var_78], rax
0x1400bb5fa  lea     r8, [rsp+0A8h+var_78]
0x1400bb5ff  mov     [rsp+0A8h+var_70], 48h ; 'H'
0x1400bb607  mov     ecx, 40000000h
0x1400bb60c  mov     [rsp+0A8h+var_88], 0
0x1400bb615  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400bb61c  nop     dword ptr [rax+rax+00h]
0x1400bb621  mov     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x1400bb629  call    cs:__imp_ZwDeleteKey
0x1400bb630  nop     dword ptr [rax+rax+00h]
0x1400bb635  mov     ebx, eax
0x1400bb637  mov     rcx, [rsp+0A8h+KeyHandle]; Handle
0x1400bb63f  test    rcx, rcx
0x1400bb642  jz      short loc_1400BB650
0x1400bb644  call    cs:__imp_ZwClose
0x1400bb64b  nop     dword ptr [rax+rax+00h]
0x1400bb650  test    ebx, ebx
0x1400bb652  jns     short loc_1400BB69F
0x1400bb654  mov     edx, cs:dword_140087708
0x1400bb65a  mov     r8d, 2
0x1400bb660  cmp     edx, r8d
0x1400bb663  jbe     short loc_1400BB69F
0x1400bb665  mov     r9d, 80000h
0x1400bb66b  lea     rcx, dword_140087708
0x1400bb672  mov     edx, r9d
0x1400bb675  call    _tlgKeywordOn
0x1400bb67a  test    al, al
0x1400bb67c  jz      short loc_1400BB69F
0x1400bb67e  lea     rax, aReturnWithStat_23; "Return with status 0x%08X"
0x1400bb685  mov     dword ptr [rsp+0A8h+var_80], ebx; char
0x1400bb689  mov     edx, 12A7h; int
0x1400bb68e  mov     [rsp+0A8h+var_88], rax; char *
0x1400bb693  lea     rcx, aVhdmpiunregist_1; "VhdmpiUnregisterForBootSurface"
0x1400bb69a  call    TraceEvents
0x1400bb69f  mov     eax, ebx
0x1400bb6a1  add     rsp, 0A0h
0x1400bb6a8  pop     rbx
0x1400bb6a9  retn
```
