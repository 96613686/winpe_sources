# CShareWithList::UpdateDevice(ushort *)

- ea: `0x18000df2c`
- end: `0x18000e105`
- name: `?UpdateDevice@CShareWithList@@QEAAJPEAG@Z`
- size: `473`
- prototype: `__int64 __fastcall(CShareWithList *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000822c`
- `0x180009900`

## callees

- `0x180003860`
- `0x180003888`
- `0x1800090ec`
- `0x18000a130`
- `0x18000c284`
- `0x18000df2c`
- `0x18000e1f4`
- `0x180012cb0`
- `0x180012dd8`
- `0x180016460`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000e03f`
- `KERNEL32!LeaveCriticalSection` at `0x18000e091`
- `KERNEL32!LeaveCriticalSection` at `0x18000e03f`
- `KERNEL32!LeaveCriticalSection` at `0x18000e091`
- `KERNEL32!EnterCriticalSection` at `0x18000e018`
- `KERNEL32!EnterCriticalSection` at `0x18000e018`

## pseudocode

```c
__int64 __fastcall CShareWithList::UpdateDevice(CShareWithList *this, unsigned __int16 *a2)
{
  CShareWithList *v3; // r14
  _QWORD *v4; // r10
  unsigned __int16 *v5; // rax
  __int64 v6; // r8
  unsigned int Item; // ebx
  struct CShareWithListItemBase *Ptr; // rax
  CShareWithListItemBase *v9; // rsi
  int v11; // [rsp+58h] [rbp+10h] BYREF

  v3 = this;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
  {
    McTemplateU0zq_EventWriteTransfer(this, ShareMediaCPL_UpdateDevice_Start, a2, 0);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
    goto LABEL_22;
  v5 = a2;
  v6 = 0x7FFFFFFF;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  this = (CShareWithList *)((0x7FFFFFFF - (_DWORD)v6) & (unsigned int)-(v6 != 0));
  if ( (v6 != 0 ? 0x7FFFFFFF - (_DWORD)v6 : 0) != 0 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_S(v4[2], 148, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, a2);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 72));
    v11 = -1;
    Item = CShareWithList::FindItem(v3, a2, &v11);
    if ( Item )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 72));
    }
    else
    {
      Ptr = (struct CShareWithListItemBase *)DPA_GetPtr(*((HDPA *)v3 + 3), v11);
      v9 = Ptr;
      if ( Ptr )
      {
        Item = CShareWithList::RefreshDeviceSettings(v3, Ptr, a2);
        if ( (Item & 0x80000000) == 0 )
          Item = CShareWithListItemBase::UpdateUI(v9, 1);
      }
      else
      {
        Item = -2147467259;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 72));
      CShareWithList::ApplyNetworkFilterToDeviceList(v3);
    }
    v4 = WPP_GLOBAL_Control;
  }
  else
  {
LABEL_22:
    Item = -2147467261;
  }
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
  {
    McTemplateU0zq_EventWriteTransfer(this, ShareMediaCPL_UpdateDevice_Stop, a2, Item);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d(v4[2], 149, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, Item);
  return Item;
}

```

## disassembly

```asm
0x18000df2c  mov     [rsp+arg_0], rbx
0x18000df31  mov     [rsp+arg_10], rbp
0x18000df36  push    rsi
0x18000df37  push    rdi
0x18000df38  push    r12
0x18000df3a  push    r14
0x18000df3c  push    r15
0x18000df3e  sub     rsp, 20h
0x18000df42  mov     rdi, rdx
0x18000df45  mov     r14, rcx
0x18000df48  mov     r10, cs:WPP_GLOBAL_Control
0x18000df4f  lea     r12, WPP_GLOBAL_Control
0x18000df56  cmp     r10, r12
0x18000df59  jz      short loc_18000DF7E
0x18000df5b  test    byte ptr [r10+1Ch], 20h
0x18000df60  jz      short loc_18000DF7E
0x18000df62  mov     rcx, [r10+10h]
0x18000df66  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000df6d  mov     edx, 93h
0x18000df72  call    WPP_SF_
0x18000df77  mov     r10, cs:WPP_GLOBAL_Control
0x18000df7e  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x18000df85  jz      short loc_18000DFA0
0x18000df87  xor     r9d, r9d
0x18000df8a  lea     rdx, ShareMediaCPL_UpdateDevice_Start
0x18000df91  mov     r8, rdi
0x18000df94  call    McTemplateU0zq_EventWriteTransfer
0x18000df99  mov     r10, cs:WPP_GLOBAL_Control
0x18000dfa0  xor     r15d, r15d
0x18000dfa3  test    rdi, rdi
0x18000dfa6  jz      loc_18000E0A1
0x18000dfac  mov     r9d, 7FFFFFFFh
0x18000dfb2  mov     rax, rdi
0x18000dfb5  mov     r8d, r9d
0x18000dfb8  cmp     [rax], r15w
0x18000dfbc  jz      short loc_18000DFC8
0x18000dfbe  add     rax, 2
0x18000dfc2  sub     r8, 1
0x18000dfc6  jnz     short loc_18000DFB8
0x18000dfc8  sub     r9d, r8d
0x18000dfcb  mov     rax, r8
0x18000dfce  neg     rax
0x18000dfd1  mov     rdx, r8
0x18000dfd4  sbb     ecx, ecx
0x18000dfd6  and     ecx, r9d
0x18000dfd9  neg     rdx
0x18000dfdc  sbb     edx, edx
0x18000dfde  and     edx, ecx
0x18000dfe0  neg     r8
0x18000dfe3  sbb     eax, eax
0x18000dfe5  test    edx, eax
0x18000dfe7  jbe     loc_18000E0A1
0x18000dfed  cmp     r10, r12
0x18000dff0  jz      short loc_18000E011
0x18000dff2  test    byte ptr [r10+1Ch], 8
0x18000dff7  jz      short loc_18000E011
0x18000dff9  mov     rcx, [r10+10h]
0x18000dffd  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000e004  mov     edx, 94h
0x18000e009  mov     r9, rdi
0x18000e00c  call    WPP_SF_S
0x18000e011  lea     rbp, [r14+48h]
0x18000e015  mov     rcx, rbp; lpCriticalSection
0x18000e018  call    cs:__imp_EnterCriticalSection
0x18000e01e  lea     r8, [rsp+48h+arg_8]; int *
0x18000e023  mov     [rsp+48h+arg_8], 0FFFFFFFFh
0x18000e02b  mov     rdx, rdi; unsigned __int16 *
0x18000e02e  mov     rcx, r14; this
0x18000e031  call    ?FindItem@CShareWithList@@QEAAJPEAGPEAH@Z; CShareWithList::FindItem(ushort *,int *)
0x18000e036  mov     ebx, eax
0x18000e038  test    eax, eax
0x18000e03a  jz      short loc_18000E04E
0x18000e03c  mov     rcx, rbp; lpCriticalSection
0x18000e03f  call    cs:__imp_LeaveCriticalSection
0x18000e045  mov     r10, cs:WPP_GLOBAL_Control
0x18000e04c  jmp     short loc_18000E0A6
0x18000e04e  movsxd  rdx, [rsp+48h+arg_8]; i
0x18000e053  mov     rcx, [r14+18h]; hdpa
0x18000e057  call    DPA_GetPtr
0x18000e05c  mov     rsi, rax
0x18000e05f  test    rax, rax
0x18000e062  jz      short loc_18000E089
0x18000e064  mov     r8, rdi; unsigned __int16 *
0x18000e067  mov     rdx, rax; struct CShareWithListItemBase *
0x18000e06a  mov     rcx, r14; this
0x18000e06d  call    ?RefreshDeviceSettings@CShareWithList@@QEAAJPEAVCShareWithListItemBase@@PEAG@Z; CShareWithList::RefreshDeviceSettings(CShareWithListItemBase *,ushort *)
0x18000e072  mov     ebx, eax
0x18000e074  test    eax, eax
0x18000e076  js      short loc_18000E08E
0x18000e078  mov     edx, 1; int
0x18000e07d  mov     rcx, rsi; this
0x18000e080  call    ?UpdateUI@CShareWithListItemBase@@QEAAJH@Z; CShareWithListItemBase::UpdateUI(int)
0x18000e085  mov     ebx, eax
0x18000e087  jmp     short loc_18000E08E
0x18000e089  mov     ebx, 80004005h
0x18000e08e  mov     rcx, rbp; lpCriticalSection
0x18000e091  call    cs:__imp_LeaveCriticalSection
0x18000e097  mov     rcx, r14; this
0x18000e09a  call    ?ApplyNetworkFilterToDeviceList@CShareWithList@@QEAAJXZ; CShareWithList::ApplyNetworkFilterToDeviceList(void)
0x18000e09f  jmp     short loc_18000E045
0x18000e0a1  mov     ebx, 80004003h
0x18000e0a6  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x18000e0ad  jz      short loc_18000E0C8
0x18000e0af  mov     r9d, ebx
0x18000e0b2  lea     rdx, ShareMediaCPL_UpdateDevice_Stop
0x18000e0b9  mov     r8, rdi
0x18000e0bc  call    McTemplateU0zq_EventWriteTransfer
0x18000e0c1  mov     r10, cs:WPP_GLOBAL_Control
0x18000e0c8  cmp     r10, r12
0x18000e0cb  jz      short loc_18000E0EC
0x18000e0cd  test    byte ptr [r10+1Ch], 20h
0x18000e0d2  jz      short loc_18000E0EC
0x18000e0d4  mov     rcx, [r10+10h]
0x18000e0d8  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000e0df  mov     edx, 95h
0x18000e0e4  mov     r9d, ebx
0x18000e0e7  call    WPP_SF_d
0x18000e0ec  mov     rbp, [rsp+48h+arg_10]
0x18000e0f1  mov     eax, ebx
0x18000e0f3  mov     rbx, [rsp+48h+arg_0]
0x18000e0f8  add     rsp, 20h
0x18000e0fc  pop     r15
0x18000e0fe  pop     r14
0x18000e100  pop     r12
0x18000e102  pop     rdi
0x18000e103  pop     rsi
0x18000e104  retn
```
