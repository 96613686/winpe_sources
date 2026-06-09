# IsCrossArchitectureInstall

- ea: `0x180002630`
- end: `0x180002722`
- name: `IsCrossArchitectureInstall`
- size: `242`
- prototype: `__int64 __fastcall(struct _BLACKBOARD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180002630`
- `0x18000864c`

## import_xrefs

- `WDSCORE!WdsEnumFirstBlackboardItem` at `0x180002688`
- `WDSCORE!WdsEnumFirstBlackboardItem` at `0x180002688`
- `WDSCORE!WdsAbortBlackboardItemEnum` at `0x18000269d`
- `WDSCORE!WdsAbortBlackboardItemEnum` at `0x18000269d`

## pseudocode

```c
__int64 __fastcall IsCrossArchitectureInstall(struct _BLACKBOARD *a1, BOOL *a2)
{
  unsigned int Dword; // esi
  unsigned int v5; // eax
  BOOL v6; // ecx
  __int64 result; // rax
  _OWORD v8[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v9; // [rsp+50h] [rbp-18h]

  if ( !a1 || !a2 )
    return 2147942487LL;
  memset(v8, 0, sizeof(v8));
  v9 = 0;
  if ( !(unsigned int)WdsEnumFirstBlackboardItem(v8, a1, L"ImageInfo\\OSImage", L"SelectedImageArch", 2) )
    return 2147943568LL;
  WdsAbortBlackboardItemEnum(v8);
  Dword = BbGetDword(a1, L"ImageInfo\\OSImage", L"SelectedImageArch", 0xFFFFu);
  if ( Dword == 0xFFFF )
    return 2147942413LL;
  v5 = BbGetDword(a1, L"SetupState\\SetupArchitecture", L"Value", 0xFFFFu);
  if ( v5 == 0xFFFF )
    return 2147942413LL;
  v6 = Dword != v5;
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180002630  mov     r11, rsp
0x180002633  mov     [r11+8], rbx
0x180002637  mov     [r11+10h], rsi
0x18000263b  push    rdi
0x18000263c  sub     rsp, 60h
0x180002640  mov     rdi, rdx
0x180002643  mov     rbx, rcx
0x180002646  test    rcx, rcx
0x180002649  jz      loc_18000270C
0x18000264f  test    rdx, rdx
0x180002652  jz      loc_18000270C
0x180002658  xorps   xmm0, xmm0
0x18000265b  mov     [rsp+68h+var_48], 2
0x180002663  xor     eax, eax
0x180002665  lea     r9, aSelectedimagea; "SelectedImageArch"
0x18000266c  mov     rdx, rcx
0x18000266f  lea     r8, aImageinfoOsima; "ImageInfo\\OSImage"
0x180002676  movups  [rsp+68h+var_38], xmm0
0x18000267b  lea     rcx, [r11-38h]
0x18000267f  movups  [rsp+68h+var_28], xmm0
0x180002684  mov     [r11-18h], rax
0x180002688  call    cs:__imp_WdsEnumFirstBlackboardItem
0x18000268f  nop     dword ptr [rax+rax+00h]
0x180002694  test    eax, eax
0x180002696  jz      short loc_180002705
0x180002698  lea     rcx, [rsp+68h+var_38]
0x18000269d  call    cs:__imp_WdsAbortBlackboardItemEnum
0x1800026a4  nop     dword ptr [rax+rax+00h]
0x1800026a9  mov     r9d, 0FFFFh; unsigned int
0x1800026af  lea     r8, aSelectedimagea; "SelectedImageArch"
0x1800026b6  lea     rdx, aImageinfoOsima; "ImageInfo\\OSImage"
0x1800026bd  mov     rcx, rbx; struct _BLACKBOARD *
0x1800026c0  call    ?BbGetDword@@YAKPEAU_BLACKBOARD@@PEBG1K@Z; BbGetDword(_BLACKBOARD *,ushort const *,ushort const *,ulong)
0x1800026c5  mov     esi, eax
0x1800026c7  cmp     eax, 0FFFFh
0x1800026cc  jz      short loc_1800026FE
0x1800026ce  mov     r9d, 0FFFFh; unsigned int
0x1800026d4  lea     r8, aValue; "Value"
0x1800026db  lea     rdx, aSetupstateSetu; "SetupState\\SetupArchitecture"
0x1800026e2  mov     rcx, rbx; struct _BLACKBOARD *
0x1800026e5  call    ?BbGetDword@@YAKPEAU_BLACKBOARD@@PEBG1K@Z; BbGetDword(_BLACKBOARD *,ushort const *,ushort const *,ulong)
0x1800026ea  cmp     eax, 0FFFFh
0x1800026ef  jz      short loc_1800026FE
0x1800026f1  xor     ecx, ecx
0x1800026f3  cmp     esi, eax
0x1800026f5  setnz   cl
0x1800026f8  xor     eax, eax
0x1800026fa  mov     [rdi], ecx
0x1800026fc  jmp     short loc_180002711
0x1800026fe  mov     eax, 8007000Dh
0x180002703  jmp     short loc_180002711
0x180002705  mov     eax, 80070490h
0x18000270a  jmp     short loc_180002711
0x18000270c  mov     eax, 80070057h
0x180002711  mov     rbx, [rsp+68h+arg_0]
0x180002716  mov     rsi, [rsp+68h+arg_8]
0x18000271b  add     rsp, 60h
0x18000271f  pop     rdi
0x180002720  retn
```
