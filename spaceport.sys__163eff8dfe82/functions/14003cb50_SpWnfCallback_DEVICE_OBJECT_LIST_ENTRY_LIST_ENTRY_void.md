# SpWnfCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x14003cb50`
- end: `0x14003cc8c`
- name: `?SpWnfCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `316`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140011970`
- `0x14002e364`
- `0x14003cb50`
- `0x140043088`
- `0x1400a22b0`
- `0x1400b61d0`
- `0x1400b6c60`
- `0x1400b7160`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x14003cb9d`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14003cc08`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14003cb9d`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14003cc08`

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
0x14003cb50  mov     [rsp+arg_0], rbx
0x14003cb55  mov     [rsp+arg_8], rsi
0x14003cb5a  push    rdi
0x14003cb5b  sub     rsp, 50h
0x14003cb5f  xor     edx, edx; unsigned __int8
0x14003cb61  lea     rcx, [rsp+58h+var_18]; this
0x14003cb66  xor     edi, edi
0x14003cb68  call    ??0SP_ITERATOR_SPACE@@QEAA@E@Z; SP_ITERATOR_SPACE::SP_ITERATOR_SPACE(uchar)
0x14003cb6d  xor     eax, eax
0x14003cb6f  xor     esi, esi
0x14003cb71  xchg    eax, [r9]
0x14003cb74  mov     [rsp+58h+arg_18], eax
0x14003cb78  lea     rax, [rsp+58h+arg_18]
0x14003cb7d  bt      dword ptr [rax], 1
0x14003cb81  jnb     short loc_14003CBA9
0x14003cb83  mov     [rsp+58h+var_28], edx
0x14003cb87  lea     rcx, WNF_SPAC_SPACEPORT_PROPERTY_CHANGED
0x14003cb8e  mov     [rsp+58h+var_30], edx
0x14003cb92  xor     r9d, r9d
0x14003cb95  xor     r8d, r8d
0x14003cb98  mov     [rsp+58h+var_38], rdx
0x14003cb9d  call    cs:__imp_ZwUpdateWnfStateData
0x14003cba4  nop     dword ptr [rax+rax+00h]
0x14003cba9  lea     rax, [rsp+58h+arg_18]
0x14003cbae  bt      dword ptr [rax], 0
0x14003cbb2  jnb     loc_14003CC45
0x14003cbb8  lea     rcx, [rsp+58h+var_18]; this
0x14003cbbd  call    ?First@SP_ITERATOR_SPACE@@QEAAPEAVSP_SPACE@@XZ; SP_ITERATOR_SPACE::First(void)
0x14003cbc2  test    rax, rax
0x14003cbc5  jz      short loc_14003CC45
0x14003cbc7  mov     rcx, rax; this
0x14003cbca  call    ?IsSynchronizing@SIO_SPACE@@QEAAEXZ; SIO_SPACE::IsSynchronizing(void)
0x14003cbcf  test    al, al
0x14003cbd1  lea     ebx, [rdi+1]
0x14003cbd4  lea     rcx, [rsp+58h+var_18]; this
0x14003cbd9  cmovz   ebx, edi
0x14003cbdc  call    ?Next@SP_ITERATOR_SPACE@@QEAAPEAVSP_SPACE@@XZ; SP_ITERATOR_SPACE::Next(void)
0x14003cbe1  mov     edi, ebx
0x14003cbe3  test    rax, rax
0x14003cbe6  jnz     short loc_14003CBC7
0x14003cbe8  test    ebx, ebx
0x14003cbea  jz      short loc_14003CC45
0x14003cbec  mov     [rsp+58h+var_28], esi
0x14003cbf0  lea     rcx, WNF_DISK_SCRUB_REQUIRED
0x14003cbf7  mov     [rsp+58h+var_30], esi
0x14003cbfb  xor     r9d, r9d
0x14003cbfe  xor     r8d, r8d
0x14003cc01  mov     [rsp+58h+var_38], rsi
0x14003cc06  xor     edx, edx
0x14003cc08  call    cs:__imp_ZwUpdateWnfStateData
0x14003cc0f  nop     dword ptr [rax+rax+00h]
0x14003cc14  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003cc1b  xor     r9d, r9d; unsigned __int8
0x14003cc1e  xor     edx, edx; struct _LIST_ENTRY *
0x14003cc20  mov     esi, eax
0x14003cc22  lock bts dword ptr [rcx+648h], 0
0x14003cc2b  mov     r8, cs:WPP_MAIN_CB.DeviceExtension
0x14003cc32  lea     rcx, [r8+578h]; Context
0x14003cc39  mov     r8d, [r8+260h]; unsigned int
0x14003cc40  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x14003cc45  lea     rax, [rsp+58h+arg_18]
0x14003cc4a  bt      dword ptr [rax], 0
0x14003cc4e  jnb     short loc_14003CC6F
0x14003cc50  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x14003cc57  jz      short loc_14003CC6F
0x14003cc59  mov     r9d, edi
0x14003cc5c  mov     dword ptr [rsp+58h+var_38], esi
0x14003cc60  xor     r8d, r8d
0x14003cc63  lea     rdx, ScrubRequired
0x14003cc6a  call    McTemplateK0qq_EtwWriteTransfer
0x14003cc6f  lea     rcx, [rsp+58h+var_18]; this
0x14003cc74  call    ??1SP_ITERATOR_SPACE@@QEAA@XZ; SP_ITERATOR_SPACE::~SP_ITERATOR_SPACE(void)
0x14003cc79  mov     rbx, [rsp+58h+arg_0]
0x14003cc7e  xor     eax, eax
0x14003cc80  mov     rsi, [rsp+58h+arg_8]
0x14003cc85  add     rsp, 50h
0x14003cc89  pop     rdi
0x14003cc8a  retn
```
