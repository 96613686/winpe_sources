# VmpReleaseInterfaces

- ea: `0x1400033a0`
- end: `0x140003906`
- name: `VmpReleaseInterfaces`
- size: `1382`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000443c`
- `0x14000e888`
- `0x14000eba0`

## callees

- `0x1400033a0`

## import_xrefs

- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400033cc`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000358d`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000374e`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400033cc`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000358d`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000374e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140003567`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140003728`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400038e9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140003567`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140003728`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400038e9`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14000340e`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003443`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14000347b`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400034b9`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400034ee`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003523`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003558`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400035cf`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003604`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14000363c`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14000367a`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400036af`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400036e4`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003719`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003790`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400037c5`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400037fd`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14000383b`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003870`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400038a5`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400038da`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14000340e`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003443`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14000347b`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400034b9`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400034ee`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003523`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003558`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400035cf`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003604`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14000363c`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14000367a`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400036af`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400036e4`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003719`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003790`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400037c5`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400037fd`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14000383b`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140003870`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400038a5`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400038da`

## pseudocode

```c
void __fastcall VmpReleaseInterfaces(__int64 a1)
{
  struct _UNICODE_STRING *v2; // rsi
  __int64 v3; // rcx
  __int64 v4; // rcx

  if ( *(_QWORD *)(a1 + 176) )
  {
    v2 = (struct _UNICODE_STRING *)(a1 + 168);
    IoSetDeviceInterfaceState((PUNICODE_STRING)(a1 + 168), 0);
    if ( !*(_BYTE *)(a1 + 426) )
    {
      IoSetDeviceInterfacePropertyData(v2, &DEVPKEY_Storage_Disk_Number, 0, 0, 0, 0, 0);
      IoSetDeviceInterfacePropertyData(v2, &DEVPKEY_Storage_Partition_Number, 0, 0, 0, 0, 0);
      if ( *(_BYTE *)(a1 + 424) )
      {
        IoSetDeviceInterfacePropertyData(v2, &DEVPKEY_Storage_Gpt_Type, 0, 0, 0, 0, 0);
        IoSetDeviceInterfacePropertyData(v2, &DEVPKEY_Storage_Gpt_Name, 0, 0, 0, 0, 0);
      }
      else
      {
        IoSetDeviceInterfacePropertyData(v2, &DEVPKEY_Storage_Mbr_Type, 0, 0, 0, 0, 0);
      }
    }
    IoSetDeviceInterfacePropertyData(v2, &DEVPKEY_Storage_Portable, 0, 0, 0, 0, 0);
    IoSetDeviceInterfacePropertyData(v2, &DEVPKEY_Storage_Removable_Media, 0, 0, 0, 0, 0);
    IoSetDeviceInterfacePropertyData(v2, &DEVPKEY_Storage_System_Critical, 0, 0, 0, 0, 0);
    RtlFreeUnicodeString(v2);
  }
  if ( *(_QWORD *)(a1 + 192) )
  {
    IoSetDeviceInterfaceState((PUNICODE_STRING)(a1 + 184), 0);
    if ( !*(_BYTE *)(a1 + 426) )
    {
      IoSetDeviceInterfacePropertyData(a1 + 184, &DEVPKEY_Storage_Disk_Number, 0, 0, 0, 0, 0);
      IoSetDeviceInterfacePropertyData(a1 + 184, &DEVPKEY_Storage_Partition_Number, 0, 0, 0, 0, 0);
      v3 = a1 + 184;
      if ( *(_BYTE *)(a1 + 424) )
      {
        IoSetDeviceInterfacePropertyData(v3, &DEVPKEY_Storage_Gpt_Type, 0, 0, 0, 0, 0);
        IoSetDeviceInterfacePropertyData(a1 + 184, &DEVPKEY_Storage_Gpt_Name, 0, 0, 0, 0, 0);
      }
      else
      {
        IoSetDeviceInterfacePropertyData(v3, &DEVPKEY_Storage_Mbr_Type, 0, 0, 0, 0, 0);
      }
    }
    IoSetDeviceInterfacePropertyData(a1 + 184, &DEVPKEY_Storage_Portable, 0, 0, 0, 0, 0);
    IoSetDeviceInterfacePropertyData(a1 + 184, &DEVPKEY_Storage_Removable_Media, 0, 0, 0, 0, 0);
    IoSetDeviceInterfacePropertyData(a1 + 184, &DEVPKEY_Storage_System_Critical, 0, 0, 0, 0, 0);
    RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 184));
  }
  if ( *(_QWORD *)(a1 + 208) )
  {
    IoSetDeviceInterfaceState((PUNICODE_STRING)(a1 + 200), 0);
    if ( !*(_BYTE *)(a1 + 426) )
    {
      IoSetDeviceInterfacePropertyData(a1 + 200, &DEVPKEY_Storage_Disk_Number, 0, 0, 0, 0, 0);
      IoSetDeviceInterfacePropertyData(a1 + 200, &DEVPKEY_Storage_Partition_Number, 0, 0, 0, 0, 0);
      v4 = a1 + 200;
      if ( *(_BYTE *)(a1 + 424) )
      {
        IoSetDeviceInterfacePropertyData(v4, &DEVPKEY_Storage_Gpt_Type, 0, 0, 0, 0, 0);
        IoSetDeviceInterfacePropertyData(a1 + 200, &DEVPKEY_Storage_Gpt_Name, 0, 0, 0, 0, 0);
      }
      else
      {
        IoSetDeviceInterfacePropertyData(v4, &DEVPKEY_Storage_Mbr_Type, 0, 0, 0, 0, 0);
      }
    }
    IoSetDeviceInterfacePropertyData(a1 + 200, &DEVPKEY_Storage_Portable, 0, 0, 0, 0, 0);
    IoSetDeviceInterfacePropertyData(a1 + 200, &DEVPKEY_Storage_Removable_Media, 0, 0, 0, 0, 0);
    IoSetDeviceInterfacePropertyData(a1 + 200, &DEVPKEY_Storage_System_Critical, 0, 0, 0, 0, 0);
    RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 200));
  }
}

```

## disassembly

```asm
0x1400033a0  mov     [rsp+arg_0], rbx
0x1400033a5  mov     [rsp+arg_8], rsi
0x1400033aa  push    rdi
0x1400033ab  sub     rsp, 40h
0x1400033af  cmp     qword ptr [rcx+0B0h], 0
0x1400033b7  mov     rbx, rcx
0x1400033ba  jz      loc_140003573
0x1400033c0  lea     rsi, [rcx+0A8h]
0x1400033c7  xor     edx, edx; Enable
0x1400033c9  mov     rcx, rsi; SymbolicLinkName
0x1400033cc  call    cs:__imp_IoSetDeviceInterfaceState
0x1400033d3  nop     dword ptr [rax+rax+00h]
0x1400033d8  cmp     byte ptr [rbx+1AAh], 0
0x1400033df  jnz     loc_1400034C5
0x1400033e5  mov     [rsp+48h+var_18], 0
0x1400033ee  lea     rdx, DEVPKEY_Storage_Disk_Number
0x1400033f5  mov     [rsp+48h+var_20], 0
0x1400033fd  xor     r9d, r9d
0x140003400  xor     r8d, r8d
0x140003403  mov     [rsp+48h+var_28], 0
0x14000340b  mov     rcx, rsi
0x14000340e  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x140003415  nop     dword ptr [rax+rax+00h]
0x14000341a  mov     [rsp+48h+var_18], 0
0x140003423  lea     rdx, DEVPKEY_Storage_Partition_Number
0x14000342a  mov     [rsp+48h+var_20], 0
0x140003432  xor     r9d, r9d
0x140003435  xor     r8d, r8d
0x140003438  mov     [rsp+48h+var_28], 0
0x140003440  mov     rcx, rsi
0x140003443  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14000344a  nop     dword ptr [rax+rax+00h]
0x14000344f  xor     r8d, r8d
0x140003452  mov     [rsp+48h+var_18], 0
0x14000345b  xor     r9d, r9d
0x14000345e  mov     [rsp+48h+var_20], r8d
0x140003463  mov     rcx, rsi
0x140003466  mov     [rsp+48h+var_28], r8d
0x14000346b  cmp     [rbx+1A8h], r8b
0x140003472  jz      short loc_1400034B2
0x140003474  lea     rdx, DEVPKEY_Storage_Gpt_Type
0x14000347b  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x140003482  nop     dword ptr [rax+rax+00h]
0x140003487  mov     [rsp+48h+var_18], 0
0x140003490  lea     rdx, DEVPKEY_Storage_Gpt_Name
0x140003497  xor     r9d, r9d
0x14000349a  mov     [rsp+48h+var_20], 0
0x1400034a2  xor     r8d, r8d
0x1400034a5  mov     [rsp+48h+var_28], 0
0x1400034ad  mov     rcx, rsi
0x1400034b0  jmp     short loc_1400034B9
0x1400034b2  lea     rdx, DEVPKEY_Storage_Mbr_Type
0x1400034b9  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x1400034c0  nop     dword ptr [rax+rax+00h]
0x1400034c5  mov     [rsp+48h+var_18], 0
0x1400034ce  lea     rdx, DEVPKEY_Storage_Portable
0x1400034d5  mov     [rsp+48h+var_20], 0
0x1400034dd  xor     r9d, r9d
0x1400034e0  xor     r8d, r8d
0x1400034e3  mov     [rsp+48h+var_28], 0
0x1400034eb  mov     rcx, rsi
0x1400034ee  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x1400034f5  nop     dword ptr [rax+rax+00h]
0x1400034fa  mov     [rsp+48h+var_18], 0
0x140003503  lea     rdx, DEVPKEY_Storage_Removable_Media
0x14000350a  mov     [rsp+48h+var_20], 0
0x140003512  xor     r9d, r9d
0x140003515  xor     r8d, r8d
0x140003518  mov     [rsp+48h+var_28], 0
0x140003520  mov     rcx, rsi
0x140003523  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14000352a  nop     dword ptr [rax+rax+00h]
0x14000352f  mov     [rsp+48h+var_18], 0
0x140003538  lea     rdx, DEVPKEY_Storage_System_Critical
0x14000353f  mov     [rsp+48h+var_20], 0
0x140003547  xor     r9d, r9d
0x14000354a  xor     r8d, r8d
0x14000354d  mov     [rsp+48h+var_28], 0
0x140003555  mov     rcx, rsi
0x140003558  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14000355f  nop     dword ptr [rax+rax+00h]
0x140003564  mov     rcx, rsi; UnicodeString
0x140003567  call    cs:__imp_RtlFreeUnicodeString
0x14000356e  nop     dword ptr [rax+rax+00h]
0x140003573  cmp     qword ptr [rbx+0C0h], 0
0x14000357b  jz      loc_140003734
0x140003581  lea     rsi, [rbx+0B8h]
0x140003588  xor     edx, edx; Enable
0x14000358a  mov     rcx, rsi; SymbolicLinkName
0x14000358d  call    cs:__imp_IoSetDeviceInterfaceState
0x140003594  nop     dword ptr [rax+rax+00h]
0x140003599  cmp     byte ptr [rbx+1AAh], 0
0x1400035a0  jnz     loc_140003686
0x1400035a6  mov     [rsp+48h+var_18], 0
0x1400035af  lea     rdx, DEVPKEY_Storage_Disk_Number
0x1400035b6  mov     [rsp+48h+var_20], 0
0x1400035be  xor     r9d, r9d
0x1400035c1  xor     r8d, r8d
0x1400035c4  mov     [rsp+48h+var_28], 0
0x1400035cc  mov     rcx, rsi
0x1400035cf  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x1400035d6  nop     dword ptr [rax+rax+00h]
0x1400035db  mov     [rsp+48h+var_18], 0
0x1400035e4  lea     rdx, DEVPKEY_Storage_Partition_Number
0x1400035eb  mov     [rsp+48h+var_20], 0
0x1400035f3  xor     r9d, r9d
0x1400035f6  xor     r8d, r8d
0x1400035f9  mov     [rsp+48h+var_28], 0
0x140003601  mov     rcx, rsi
0x140003604  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14000360b  nop     dword ptr [rax+rax+00h]
0x140003610  xor     r8d, r8d
0x140003613  mov     [rsp+48h+var_18], 0
0x14000361c  xor     r9d, r9d
0x14000361f  mov     [rsp+48h+var_20], r8d
0x140003624  mov     rcx, rsi
0x140003627  mov     [rsp+48h+var_28], r8d
0x14000362c  cmp     [rbx+1A8h], r8b
0x140003633  jz      short loc_140003673
0x140003635  lea     rdx, DEVPKEY_Storage_Gpt_Type
0x14000363c  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x140003643  nop     dword ptr [rax+rax+00h]
0x140003648  mov     [rsp+48h+var_18], 0
0x140003651  lea     rdx, DEVPKEY_Storage_Gpt_Name
0x140003658  xor     r9d, r9d
0x14000365b  mov     [rsp+48h+var_20], 0
0x140003663  xor     r8d, r8d
0x140003666  mov     [rsp+48h+var_28], 0
0x14000366e  mov     rcx, rsi
0x140003671  jmp     short loc_14000367A
0x140003673  lea     rdx, DEVPKEY_Storage_Mbr_Type
0x14000367a  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x140003681  nop     dword ptr [rax+rax+00h]
0x140003686  mov     [rsp+48h+var_18], 0
0x14000368f  lea     rdx, DEVPKEY_Storage_Portable
0x140003696  mov     [rsp+48h+var_20], 0
0x14000369e  xor     r9d, r9d
0x1400036a1  xor     r8d, r8d
0x1400036a4  mov     [rsp+48h+var_28], 0
0x1400036ac  mov     rcx, rsi
0x1400036af  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x1400036b6  nop     dword ptr [rax+rax+00h]
0x1400036bb  mov     [rsp+48h+var_18], 0
0x1400036c4  lea     rdx, DEVPKEY_Storage_Removable_Media
0x1400036cb  mov     [rsp+48h+var_20], 0
0x1400036d3  xor     r9d, r9d
0x1400036d6  xor     r8d, r8d
0x1400036d9  mov     [rsp+48h+var_28], 0
0x1400036e1  mov     rcx, rsi
0x1400036e4  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x1400036eb  nop     dword ptr [rax+rax+00h]
0x1400036f0  mov     [rsp+48h+var_18], 0
0x1400036f9  lea     rdx, DEVPKEY_Storage_System_Critical
0x140003700  mov     [rsp+48h+var_20], 0
0x140003708  xor     r9d, r9d
0x14000370b  xor     r8d, r8d
0x14000370e  mov     [rsp+48h+var_28], 0
0x140003716  mov     rcx, rsi
0x140003719  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x140003720  nop     dword ptr [rax+rax+00h]
0x140003725  mov     rcx, rsi; UnicodeString
0x140003728  call    cs:__imp_RtlFreeUnicodeString
0x14000372f  nop     dword ptr [rax+rax+00h]
0x140003734  cmp     qword ptr [rbx+0D0h], 0
0x14000373c  jz      loc_1400038F5
0x140003742  lea     rsi, [rbx+0C8h]
0x140003749  xor     edx, edx; Enable
0x14000374b  mov     rcx, rsi; SymbolicLinkName
0x14000374e  call    cs:__imp_IoSetDeviceInterfaceState
0x140003755  nop     dword ptr [rax+rax+00h]
0x14000375a  cmp     byte ptr [rbx+1AAh], 0
0x140003761  jnz     loc_140003847
0x140003767  mov     [rsp+48h+var_18], 0
0x140003770  lea     rdx, DEVPKEY_Storage_Disk_Number
0x140003777  mov     [rsp+48h+var_20], 0
0x14000377f  xor     r9d, r9d
0x140003782  xor     r8d, r8d
0x140003785  mov     [rsp+48h+var_28], 0
0x14000378d  mov     rcx, rsi
0x140003790  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x140003797  nop     dword ptr [rax+rax+00h]
0x14000379c  mov     [rsp+48h+var_18], 0
0x1400037a5  lea     rdx, DEVPKEY_Storage_Partition_Number
0x1400037ac  mov     [rsp+48h+var_20], 0
0x1400037b4  xor     r9d, r9d
0x1400037b7  xor     r8d, r8d
0x1400037ba  mov     [rsp+48h+var_28], 0
0x1400037c2  mov     rcx, rsi
0x1400037c5  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x1400037cc  nop     dword ptr [rax+rax+00h]
0x1400037d1  xor     r8d, r8d
0x1400037d4  mov     [rsp+48h+var_18], 0
0x1400037dd  xor     r9d, r9d
0x1400037e0  mov     [rsp+48h+var_20], r8d
0x1400037e5  mov     rcx, rsi
0x1400037e8  mov     [rsp+48h+var_28], r8d
0x1400037ed  cmp     [rbx+1A8h], r8b
0x1400037f4  jz      short loc_140003834
0x1400037f6  lea     rdx, DEVPKEY_Storage_Gpt_Type
0x1400037fd  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x140003804  nop     dword ptr [rax+rax+00h]
0x140003809  mov     [rsp+48h+var_18], 0
0x140003812  lea     rdx, DEVPKEY_Storage_Gpt_Name
0x140003819  xor     r9d, r9d
0x14000381c  mov     [rsp+48h+var_20], 0
0x140003824  xor     r8d, r8d
0x140003827  mov     [rsp+48h+var_28], 0
0x14000382f  mov     rcx, rsi
0x140003832  jmp     short loc_14000383B
0x140003834  lea     rdx, DEVPKEY_Storage_Mbr_Type
0x14000383b  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x140003842  nop     dword ptr [rax+rax+00h]
0x140003847  mov     [rsp+48h+var_18], 0
0x140003850  lea     rdx, DEVPKEY_Storage_Portable
0x140003857  mov     [rsp+48h+var_20], 0
0x14000385f  xor     r9d, r9d
0x140003862  xor     r8d, r8d
0x140003865  mov     [rsp+48h+var_28], 0
0x14000386d  mov     rcx, rsi
0x140003870  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x140003877  nop     dword ptr [rax+rax+00h]
0x14000387c  mov     [rsp+48h+var_18], 0
0x140003885  lea     rdx, DEVPKEY_Storage_Removable_Media
0x14000388c  mov     [rsp+48h+var_20], 0
0x140003894  xor     r9d, r9d
0x140003897  xor     r8d, r8d
0x14000389a  mov     [rsp+48h+var_28], 0
0x1400038a2  mov     rcx, rsi
0x1400038a5  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x1400038ac  nop     dword ptr [rax+rax+00h]
0x1400038b1  mov     [rsp+48h+var_18], 0
0x1400038ba  lea     rdx, DEVPKEY_Storage_System_Critical
0x1400038c1  mov     [rsp+48h+var_20], 0
0x1400038c9  xor     r9d, r9d
0x1400038cc  xor     r8d, r8d
0x1400038cf  mov     [rsp+48h+var_28], 0
0x1400038d7  mov     rcx, rsi
0x1400038da  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x1400038e1  nop     dword ptr [rax+rax+00h]
0x1400038e6  mov     rcx, rsi; UnicodeString
0x1400038e9  call    cs:__imp_RtlFreeUnicodeString
0x1400038f0  nop     dword ptr [rax+rax+00h]
0x1400038f5  mov     rbx, [rsp+48h+arg_0]
0x1400038fa  mov     rsi, [rsp+48h+arg_8]
0x1400038ff  add     rsp, 40h
0x140003903  pop     rdi
0x140003904  retn
```
