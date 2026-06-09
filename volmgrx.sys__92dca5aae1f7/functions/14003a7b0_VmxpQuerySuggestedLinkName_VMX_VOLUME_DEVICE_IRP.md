# VmxpQuerySuggestedLinkName(VMX_VOLUME_DEVICE *,_IRP *)

- ea: `0x14003a7b0`
- end: `0x14003aa34`
- name: `?VmxpQuerySuggestedLinkName@@YAJPEAVVMX_VOLUME_DEVICE@@PEAU_IRP@@@Z`
- size: `644`
- prototype: `__int64 __fastcall(struct VMX_VOLUME_DEVICE *, struct _IRP *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14005bc90`

## callees

- `0x14000982c`
- `0x1400099d8`
- `0x14001b960`
- `0x14001bb80`
- `0x14003a7b0`
- `0x14003f51c`
- `0x14004053c`
- `0x14005d40c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14003a94a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003a94a`

## pseudocode

```c
__int64 __fastcall VmxpQuerySuggestedLinkName(struct VMX_VOLUME_DEVICE *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  VMX_NOTIFICATION_QUEUE *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  struct VMX_PACK *PackById; // rax
  struct VMX_RECORD *VolumeById; // rax
  VMX_NOTIFICATION_QUEUE *v11; // rcx
  __int64 v12; // rdx
  struct VMX_VOLUME_DEVICE **v13; // rcx
  unsigned __int8 DriveLetter; // al
  struct _IRP *MasterIrp; // rdx
  __int64 Length; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-68h] BYREF
  wchar_t pszDest[32]; // [rsp+30h] [rbp-58h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  DestinationString = 0;
  if ( CurrentStackLocation->Parameters.Read.Length < 6 )
  {
    v5 = WPP_GLOBAL_Control;
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v6;
    }
    v7 = 360;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v5 + 3), v7, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v6);
    return v6;
  }
  PackById = VmxpFindPackById((struct _GUID *)((char *)a1 + 44));
  if ( !PackById || !*((_BYTE *)PackById + 56) )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3221225486LL;
    }
    v12 = 361;
    goto LABEL_35;
  }
  VolumeById = VMX_CONFIG::FindVolumeById(*((VMX_CONFIG **)PackById + 2), (struct _GUID *)((char *)a1 + 60));
  if ( !VolumeById )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3221225486LL;
    }
    v12 = 362;
LABEL_35:
    WPP_SF_d(*((_QWORD *)v11 + 3), v12, WPP_2f8af752156e3401cd435973c831895d_Traceguids, 3221225486LL);
    return 3221225486LL;
  }
  v13 = (struct VMX_VOLUME_DEVICE **)*((_QWORD *)VolumeById + (*((_WORD *)VolumeById + 32) & 1) + 5);
  if ( v13[31] != a1 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3221225486LL;
    }
    v12 = 363;
    goto LABEL_35;
  }
  DriveLetter = VMX_VOLUME_INFO::QueryDriveLetter((VMX_VOLUME_INFO *)v13);
  if ( !DriveLetter )
  {
    v5 = WPP_GLOBAL_Control;
    v6 = -1073741275;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v6;
    }
    v7 = 364;
    goto LABEL_6;
  }
  RtlStringCbPrintfW(pszDest, 0x3Cu, L"\\DosDevices\\%c:", DriveLetter);
  RtlInitUnicodeString(&DestinationString, pszDest);
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  LOBYTE(MasterIrp->Type) = 1;
  Length = DestinationString.Length;
  MasterIrp->Size = DestinationString.Length;
  a2->IoStatus.Information = Length + 4;
  if ( CurrentStackLocation->Parameters.Read.Length < (unsigned __int64)(Length + 4) )
  {
    a2->IoStatus.Information = 4;
    v5 = WPP_GLOBAL_Control;
    v6 = -2147483643;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      return v6;
    }
    v7 = 365;
    goto LABEL_6;
  }
  memmove(&MasterIrp->Size + 1, DestinationString.Buffer, MasterIrp->Size);
  return 0;
}

```

## disassembly

```asm
0x14003a7b0  mov     [rsp+arg_10], rbx
0x14003a7b5  mov     [rsp+arg_18], rsi
0x14003a7ba  push    rdi
0x14003a7bb  sub     rsp, 80h
0x14003a7c2  mov     rax, cs:__security_cookie
0x14003a7c9  xor     rax, rsp
0x14003a7cc  mov     [rsp+88h+var_18], rax
0x14003a7d1  mov     rsi, [rdx+0B8h]
0x14003a7d8  xorps   xmm0, xmm0
0x14003a7db  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x14003a7e0  mov     rdi, rdx
0x14003a7e3  mov     rbx, rcx
0x14003a7e6  cmp     dword ptr [rsi+8], 6
0x14003a7ea  jnb     short loc_14003A830
0x14003a7ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a7f3  lea     rax, WPP_GLOBAL_Control
0x14003a7fa  mov     ebx, 0C000000Dh
0x14003a7ff  cmp     rcx, rax
0x14003a802  jz      short loc_14003A829
0x14003a804  mov     eax, [rcx+2Ch]
0x14003a807  test    al, 4
0x14003a809  jz      short loc_14003A829
0x14003a80b  cmp     byte ptr [rcx+29h], 2
0x14003a80f  jb      short loc_14003A829
0x14003a811  mov     edx, 168h
0x14003a816  mov     rcx, [rcx+18h]
0x14003a81a  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14003a821  mov     r9d, ebx
0x14003a824  call    WPP_SF_d
0x14003a829  mov     eax, ebx
0x14003a82b  jmp     loc_14003AA11
0x14003a830  add     rcx, 2Ch ; ','; struct _GUID *
0x14003a834  call    ?VmxpFindPackById@@YAPEAVVMX_PACK@@PEAU_GUID@@@Z; VmxpFindPackById(_GUID *)
0x14003a839  test    rax, rax
0x14003a83c  jz      loc_14003A9D1
0x14003a842  cmp     byte ptr [rax+38h], 0
0x14003a846  jz      loc_14003A9D1
0x14003a84c  mov     rcx, [rax+10h]; this
0x14003a850  lea     rdx, [rbx+3Ch]; struct _GUID *
0x14003a854  call    ?FindVolumeById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindVolumeById(_GUID *)
0x14003a859  mov     rcx, rax
0x14003a85c  test    rax, rax
0x14003a85f  jnz     short loc_14003A897
0x14003a861  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a868  lea     rax, WPP_GLOBAL_Control
0x14003a86f  cmp     rcx, rax
0x14003a872  jz      loc_14003AA0C
0x14003a878  mov     eax, [rcx+2Ch]
0x14003a87b  test    al, 4
0x14003a87d  jz      loc_14003AA0C
0x14003a883  cmp     byte ptr [rcx+29h], 2
0x14003a887  jb      loc_14003AA0C
0x14003a88d  mov     edx, 16Ah
0x14003a892  jmp     loc_14003A9F6
0x14003a897  movzx   eax, word ptr [rax+40h]
0x14003a89b  and     eax, 1
0x14003a89e  mov     rcx, [rcx+rax*8+28h]; this
0x14003a8a3  cmp     [rcx+0F8h], rbx
0x14003a8aa  jz      short loc_14003A8E2
0x14003a8ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a8b3  lea     rax, WPP_GLOBAL_Control
0x14003a8ba  cmp     rcx, rax
0x14003a8bd  jz      loc_14003AA0C
0x14003a8c3  mov     eax, [rcx+2Ch]
0x14003a8c6  test    al, 4
0x14003a8c8  jz      loc_14003AA0C
0x14003a8ce  cmp     byte ptr [rcx+29h], 2
0x14003a8d2  jb      loc_14003AA0C
0x14003a8d8  mov     edx, 16Bh
0x14003a8dd  jmp     loc_14003A9F6
0x14003a8e2  call    ?QueryDriveLetter@VMX_VOLUME_INFO@@QEAAEXZ; VMX_VOLUME_INFO::QueryDriveLetter(void)
0x14003a8e7  test    al, al
0x14003a8e9  jnz     short loc_14003A926
0x14003a8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a8f2  lea     rax, WPP_GLOBAL_Control
0x14003a8f9  mov     ebx, 0C0000225h
0x14003a8fe  cmp     rcx, rax
0x14003a901  jz      loc_14003A829
0x14003a907  mov     eax, [rcx+2Ch]
0x14003a90a  test    al, 4
0x14003a90c  jz      loc_14003A829
0x14003a912  cmp     byte ptr [rcx+29h], 2
0x14003a916  jb      loc_14003A829
0x14003a91c  mov     edx, 16Ch
0x14003a921  jmp     loc_14003A816
0x14003a926  movzx   r9d, al
0x14003a92a  lea     r8, aDosdevicesC; "\\DosDevices\\%c:"
0x14003a931  mov     edx, 3Ch ; '<'; cbDest
0x14003a936  lea     rcx, [rsp+88h+pszDest]; pszDest
0x14003a93b  call    RtlStringCbPrintfW
0x14003a940  lea     rdx, [rsp+88h+pszDest]; SourceString
0x14003a945  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14003a94a  call    cs:__imp_RtlInitUnicodeString
0x14003a951  nop     dword ptr [rax+rax+00h]
0x14003a956  mov     rdx, [rdi+18h]
0x14003a95a  mov     byte ptr [rdx], 1
0x14003a95d  movzx   eax, [rsp+88h+DestinationString.Length]
0x14003a962  mov     [rdx+2], ax
0x14003a966  lea     rcx, [rax+4]
0x14003a96a  mov     [rdi+38h], rcx
0x14003a96e  mov     eax, [rsi+8]
0x14003a971  cmp     rax, rcx
0x14003a974  jnb     short loc_14003A9BA
0x14003a976  mov     qword ptr [rdi+38h], 4
0x14003a97e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a985  lea     rax, WPP_GLOBAL_Control
0x14003a98c  mov     ebx, 80000005h
0x14003a991  cmp     rcx, rax
0x14003a994  jz      loc_14003A829
0x14003a99a  mov     edx, [rcx+2Ch]
0x14003a99d  test    dl, 4
0x14003a9a0  jz      loc_14003A829
0x14003a9a6  cmp     byte ptr [rcx+29h], 3
0x14003a9aa  jb      loc_14003A829
0x14003a9b0  mov     edx, 16Dh
0x14003a9b5  jmp     loc_14003A816
0x14003a9ba  movzx   r8d, word ptr [rdx+2]; Size
0x14003a9bf  lea     rcx, [rdx+4]; void *
0x14003a9c3  mov     rdx, [rsp+88h+DestinationString.Buffer]; Src
0x14003a9c8  call    memmove
0x14003a9cd  xor     eax, eax
0x14003a9cf  jmp     short loc_14003AA11
0x14003a9d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a9d8  lea     rax, WPP_GLOBAL_Control
0x14003a9df  cmp     rcx, rax
0x14003a9e2  jz      short loc_14003AA0C
0x14003a9e4  mov     eax, [rcx+2Ch]
0x14003a9e7  test    al, 4
0x14003a9e9  jz      short loc_14003AA0C
0x14003a9eb  cmp     byte ptr [rcx+29h], 2
0x14003a9ef  jb      short loc_14003AA0C
0x14003a9f1  mov     edx, 169h
0x14003a9f6  mov     rcx, [rcx+18h]
0x14003a9fa  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14003aa01  mov     r9d, 0C000000Eh
0x14003aa07  call    WPP_SF_d
0x14003aa0c  mov     eax, 0C000000Eh
0x14003aa11  mov     rcx, [rsp+88h+var_18]
0x14003aa16  xor     rcx, rsp; StackCookie
0x14003aa19  call    __security_check_cookie
0x14003aa1e  lea     r11, [rsp+88h+var_8]
0x14003aa26  mov     rbx, [r11+20h]
0x14003aa2a  mov     rsi, [r11+28h]
0x14003aa2e  mov     rsp, r11
0x14003aa31  pop     rdi
0x14003aa32  retn
```
