# USBVideoPnpRemove

- ea: `0x1400110f0`
- end: `0x1400112b6`
- name: `USBVideoPnpRemove`
- size: `454`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140004bac`
- `0x1400110f0`
- `0x1400112c0`
- `0x14001876c`
- `0x14001ab4c`
- `0x14001b15c`
- `0x140040a70`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140011161`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140011161`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001128d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001128d`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x140011179`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x140011179`
- `ntoskrnl!DbgPrintEx` at `0x140011267`
- `ntoskrnl!DbgPrintEx` at `0x140011267`

## string_xrefs

- `0x14001125a`: `UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n`

## pseudocode

```c
void __fastcall USBVideoPnpRemove(__int64 a1)
{
  __int64 v2; // rdi
  void *v3; // rcx
  NTSTATUS v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rbx
  void (__fastcall *v7)(_QWORD); // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids);
  v2 = *(_QWORD *)(a1 + 16);
  if ( v2 )
  {
    IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 768), RemoveUSBVideoDevice, File, 1u, 0x20u);
    v3 = *(void **)(v2 + 856);
    if ( v3 )
    {
      v4 = PoUnregisterPowerSettingCallback(v3);
      if ( v4 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, v2);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, v2, v4);
      }
      *(_QWORD *)(v2 + 856) = 0;
    }
    v5 = *(_QWORD *)(v2 + 760);
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      *(_QWORD *)(v2 + 760) = 0;
    }
    RemoveUSBVideoDevice(a1, 0);
    CleanupFormatPluginList(v2);
    v6 = *(_QWORD *)(v2 + 872);
    if ( v6 )
    {
      *(_BYTE *)(v6 + 225) = 1;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 220), 0xFFFFFFFF) <= 1 )
      {
        if ( *(_BYTE *)(v6 + 225) )
        {
          v7 = *(void (__fastcall **)(_QWORD))(v6 + 112);
          if ( v7 )
            v7(*(_QWORD *)(v6 + 48));
          ExFreePoolWithTag((PVOID)v6, *(_DWORD *)(v6 + 64));
        }
        else if ( g_EnableDbgPrints )
        {
          DbgPrintEx(
            0x4Du,
            0,
            "UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n",
            (const void *)v6);
        }
      }
      *(_QWORD *)(v2 + 872) = 0;
    }
  }
}

```

## disassembly

```asm
0x1400110f0  mov     [rsp+arg_0], rbx
0x1400110f5  mov     [rsp+arg_8], rdi
0x1400110fa  push    r14
0x1400110fc  sub     rsp, 30h
0x140011100  mov     rbx, rcx
0x140011103  mov     rcx, cs:WPP_GLOBAL_Control
0x14001110a  lea     r14, WPP_GLOBAL_Control
0x140011111  cmp     rcx, r14
0x140011114  jz      short loc_140011131
0x140011116  cmp     byte ptr [rcx+29h], 4
0x14001111a  jb      short loc_140011131
0x14001111c  mov     rcx, [rcx+18h]
0x140011120  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x140011127  mov     edx, 2Fh ; '/'
0x14001112c  call    WPP_SF_
0x140011131  mov     rdi, [rbx+10h]
0x140011135  test    rdi, rdi
0x140011138  jz      loc_1400112A4
0x14001113e  lea     rcx, [rdi+300h]; RemoveLock
0x140011145  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x14001114d  mov     r9d, 1; Line
0x140011153  lea     r8, File; File
0x14001115a  lea     rdx, RemoveUSBVideoDevice; Tag
0x140011161  call    cs:__imp_IoAcquireRemoveLockEx
0x140011168  nop     dword ptr [rax+rax+00h]
0x14001116d  mov     rcx, [rdi+358h]; Handle
0x140011174  test    rcx, rcx
0x140011177  jz      short loc_1400111EE
0x140011179  call    cs:__imp_PoUnregisterPowerSettingCallback
0x140011180  nop     dword ptr [rax+rax+00h]
0x140011185  test    eax, eax
0x140011187  js      short loc_1400111B9
0x140011189  mov     rcx, cs:WPP_GLOBAL_Control
0x140011190  cmp     rcx, r14
0x140011193  jz      short loc_1400111E3
0x140011195  cmp     byte ptr [rcx+29h], 4
0x140011199  jb      short loc_1400111E3
0x14001119b  mov     rcx, [rcx+18h]
0x14001119f  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x1400111a6  mov     edx, 30h ; '0'
0x1400111ab  mov     [rsp+38h+RemlockSize], eax
0x1400111af  mov     r9, rdi
0x1400111b2  call    WPP_SF_qD
0x1400111b7  jmp     short loc_1400111E3
0x1400111b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400111c0  cmp     rcx, r14
0x1400111c3  jz      short loc_1400111E3
0x1400111c5  cmp     byte ptr [rcx+29h], 4
0x1400111c9  jb      short loc_1400111E3
0x1400111cb  mov     rcx, [rcx+18h]
0x1400111cf  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x1400111d6  mov     edx, 31h ; '1'
0x1400111db  mov     r9, rdi
0x1400111de  call    WPP_SF_q
0x1400111e3  mov     qword ptr [rdi+358h], 0
0x1400111ee  mov     rcx, [rdi+2F8h]
0x1400111f5  test    rcx, rcx
0x1400111f8  jz      short loc_140011211
0x1400111fa  mov     rax, [rcx]
0x1400111fd  mov     rax, [rax+10h]
0x140011201  call    _guard_dispatch_icall
0x140011206  mov     qword ptr [rdi+2F8h], 0
0x140011211  xor     edx, edx
0x140011213  mov     rcx, rbx
0x140011216  call    RemoveUSBVideoDevice
0x14001121b  mov     rcx, rdi
0x14001121e  call    CleanupFormatPluginList
0x140011223  mov     rbx, [rdi+368h]
0x14001122a  test    rbx, rbx
0x14001122d  jz      short loc_1400112A4
0x14001122f  mov     byte ptr [rbx+0E1h], 1
0x140011236  or      eax, 0FFFFFFFFh
0x140011239  lock xadd [rbx+0DCh], eax
0x140011241  sub     eax, 1
0x140011244  jg      short loc_140011299
0x140011246  cmp     byte ptr [rbx+0E1h], 0
0x14001124d  jnz     short loc_140011275
0x14001124f  cmp     cs:g_EnableDbgPrints, 0
0x140011256  jz      short loc_140011299
0x140011258  xor     edx, edx; Level
0x14001125a  lea     r8, aUsbdhandleinfo_1; "UsbdHandleInfo->PendingDelete should be"...
0x140011261  mov     r9, rbx
0x140011264  lea     ecx, [rdx+4Dh]; ComponentId
0x140011267  call    cs:__imp_DbgPrintEx
0x14001126e  nop     dword ptr [rax+rax+00h]
0x140011273  jmp     short loc_140011299
0x140011275  mov     rax, [rbx+70h]
0x140011279  test    rax, rax
0x14001127c  jz      short loc_140011287
0x14001127e  mov     rcx, [rbx+30h]
0x140011282  call    _guard_dispatch_icall
0x140011287  mov     edx, [rbx+40h]; Tag
0x14001128a  mov     rcx, rbx; P
0x14001128d  call    cs:__imp_ExFreePoolWithTag
0x140011294  nop     dword ptr [rax+rax+00h]
0x140011299  mov     qword ptr [rdi+368h], 0
0x1400112a4  mov     rbx, [rsp+38h+arg_0]
0x1400112a9  mov     rdi, [rsp+38h+arg_8]
0x1400112ae  add     rsp, 30h
0x1400112b2  pop     r14
0x1400112b4  retn
```
