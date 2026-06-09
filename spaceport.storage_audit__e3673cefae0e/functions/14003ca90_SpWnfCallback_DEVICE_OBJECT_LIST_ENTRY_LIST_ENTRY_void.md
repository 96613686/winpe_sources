# SpWnfCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x14003ca90`
- end: `0x14003cbcc`
- name: `?SpWnfCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `316`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140011970`
- `0x14002e364`
- `0x14003ca90`
- `0x140042fc8`
- `0x1400a2180`
- `0x1400b6030`
- `0x1400b6ac0`
- `0x1400b6fc0`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x14003cadd`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14003cb48`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14003cadd`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14003cb48`

## pseudocode

```c
__int64 __fastcall SpWnfCallback(struct _DEVICE_OBJECT *a1, struct _LIST_ENTRY *a2, struct _LIST_ENTRY *a3, void *a4)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // rcx
  int updated; // esi
  volatile __int32 *v8; // r9
  SIO_SPACE *v9; // rax
  unsigned int v10; // ebx
  _BYTE v12[24]; // [rsp+40h] [rbp-18h] BYREF
  signed __int32 v13; // [rsp+78h] [rbp+20h] BYREF

  v4 = 0;
  SP_ITERATOR_SPACE::SP_ITERATOR_SPACE((SP_ITERATOR_SPACE *)v12, 0);
  updated = 0;
  v13 = _InterlockedExchange(v8, 0);
  if ( _bittest(&v13, 1u) )
    ZwUpdateWnfStateData(&WNF_SPAC_SPACEPORT_PROPERTY_CHANGED, v5, 0, 0, v5, v5, v5);
  if ( _bittest(&v13, 0) )
  {
    v9 = SP_ITERATOR_SPACE::First((SP_ITERATOR_SPACE *)v12);
    if ( v9 )
    {
      do
      {
        v10 = v4 + 1;
        if ( !SIO_SPACE::IsSynchronizing(v9) )
          v10 = v4;
        v9 = SP_ITERATOR_SPACE::Next((SP_ITERATOR_SPACE *)v12);
        v4 = v10;
      }
      while ( v9 );
      if ( v10 )
      {
        updated = ZwUpdateWnfStateData(&WNF_DISK_SCRUB_REQUIRED, 0, 0, 0, 0, 0, 0);
        _interlockedbittestandset((volatile signed __int32 *)WPP_MAIN_CB.DeviceExtension + 402, 0);
        SP_WORKITEM::Insert(
          (char *)WPP_MAIN_CB.DeviceExtension + 1400,
          0,
          *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 152),
          0);
      }
    }
  }
  if ( _bittest(&v13, 0) && (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
    McTemplateK0qq_EtwWriteTransfer(v6, ScrubRequired, 0, v4, updated);
  SP_ITERATOR_SPACE::~SP_ITERATOR_SPACE((SP_ITERATOR_SPACE *)v12);
  return 0;
}

```

## disassembly

```asm
0x14003ca90  mov     [rsp+arg_0], rbx
0x14003ca95  mov     [rsp+arg_8], rsi
0x14003ca9a  push    rdi
0x14003ca9b  sub     rsp, 50h
0x14003ca9f  xor     edx, edx; unsigned __int8
0x14003caa1  lea     rcx, [rsp+58h+var_18]; this
0x14003caa6  xor     edi, edi
0x14003caa8  call    ??0SP_ITERATOR_SPACE@@QEAA@E@Z; SP_ITERATOR_SPACE::SP_ITERATOR_SPACE(uchar)
0x14003caad  xor     eax, eax
0x14003caaf  xor     esi, esi
0x14003cab1  xchg    eax, [r9]
0x14003cab4  mov     [rsp+58h+arg_18], eax
0x14003cab8  lea     rax, [rsp+58h+arg_18]
0x14003cabd  bt      dword ptr [rax], 1
0x14003cac1  jnb     short loc_14003CAE9
0x14003cac3  mov     [rsp+58h+var_28], edx
0x14003cac7  lea     rcx, WNF_SPAC_SPACEPORT_PROPERTY_CHANGED
0x14003cace  mov     [rsp+58h+var_30], edx
0x14003cad2  xor     r9d, r9d
0x14003cad5  xor     r8d, r8d
0x14003cad8  mov     [rsp+58h+var_38], rdx
0x14003cadd  call    cs:__imp_ZwUpdateWnfStateData
0x14003cae4  nop     dword ptr [rax+rax+00h]
0x14003cae9  lea     rax, [rsp+58h+arg_18]
0x14003caee  bt      dword ptr [rax], 0
0x14003caf2  jnb     loc_14003CB85
0x14003caf8  lea     rcx, [rsp+58h+var_18]; this
0x14003cafd  call    ?First@SP_ITERATOR_SPACE@@QEAAPEAVSP_SPACE@@XZ; SP_ITERATOR_SPACE::First(void)
0x14003cb02  test    rax, rax
0x14003cb05  jz      short loc_14003CB85
0x14003cb07  mov     rcx, rax; this
0x14003cb0a  call    ?IsSynchronizing@SIO_SPACE@@QEAAEXZ; SIO_SPACE::IsSynchronizing(void)
0x14003cb0f  test    al, al
0x14003cb11  lea     ebx, [rdi+1]
0x14003cb14  lea     rcx, [rsp+58h+var_18]; this
0x14003cb19  cmovz   ebx, edi
0x14003cb1c  call    ?Next@SP_ITERATOR_SPACE@@QEAAPEAVSP_SPACE@@XZ; SP_ITERATOR_SPACE::Next(void)
0x14003cb21  mov     edi, ebx
0x14003cb23  test    rax, rax
0x14003cb26  jnz     short loc_14003CB07
0x14003cb28  test    ebx, ebx
0x14003cb2a  jz      short loc_14003CB85
0x14003cb2c  mov     [rsp+58h+var_28], esi
0x14003cb30  lea     rcx, WNF_DISK_SCRUB_REQUIRED
0x14003cb37  mov     [rsp+58h+var_30], esi
0x14003cb3b  xor     r9d, r9d
0x14003cb3e  xor     r8d, r8d
0x14003cb41  mov     [rsp+58h+var_38], rsi
0x14003cb46  xor     edx, edx
0x14003cb48  call    cs:__imp_ZwUpdateWnfStateData
0x14003cb4f  nop     dword ptr [rax+rax+00h]
0x14003cb54  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003cb5b  xor     r9d, r9d; unsigned __int8
0x14003cb5e  xor     edx, edx; struct _LIST_ENTRY *
0x14003cb60  mov     esi, eax
0x14003cb62  lock bts dword ptr [rcx+648h], 0
0x14003cb6b  mov     r8, cs:WPP_MAIN_CB.DeviceExtension
0x14003cb72  lea     rcx, [r8+578h]; Context
0x14003cb79  mov     r8d, [r8+260h]; unsigned int
0x14003cb80  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x14003cb85  lea     rax, [rsp+58h+arg_18]
0x14003cb8a  bt      dword ptr [rax], 0
0x14003cb8e  jnb     short loc_14003CBAF
0x14003cb90  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x14003cb97  jz      short loc_14003CBAF
0x14003cb99  mov     r9d, edi
0x14003cb9c  mov     dword ptr [rsp+58h+var_38], esi
0x14003cba0  xor     r8d, r8d
0x14003cba3  lea     rdx, ScrubRequired
0x14003cbaa  call    McTemplateK0qq_EtwWriteTransfer
0x14003cbaf  lea     rcx, [rsp+58h+var_18]; this
0x14003cbb4  call    ??1SP_ITERATOR_SPACE@@QEAA@XZ; SP_ITERATOR_SPACE::~SP_ITERATOR_SPACE(void)
0x14003cbb9  mov     rbx, [rsp+58h+arg_0]
0x14003cbbe  xor     eax, eax
0x14003cbc0  mov     rsi, [rsp+58h+arg_8]
0x14003cbc5  add     rsp, 50h
0x14003cbc9  pop     rdi
0x14003cbca  retn
```
