# KeyMgrIntfUpdateGroupKey(MSMSEC_INTF_CONTEXT *)

- ea: `0x1800428e0`
- end: `0x180042b40`
- name: `?KeyMgrIntfUpdateGroupKey@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z`
- size: `608`
- prototype: `unsigned int __fastcall(struct MSMSEC_INTF_CONTEXT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180065fb0`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180011030`
- `0x1800169c0`
- `0x18002bb08`
- `0x180036990`
- `0x1800428e0`
- `0x180042b48`
- `0x180059d64`
- `0x180064edc`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800429d3`
- `MobileNetworking!ReleaseWriteLock` at `0x180042aa1`
- `MobileNetworking!ReleaseWriteLock` at `0x180042b2b`
- `MobileNetworking!ReleaseWriteLock` at `0x1800429d3`
- `MobileNetworking!ReleaseWriteLock` at `0x180042aa1`
- `MobileNetworking!ReleaseWriteLock` at `0x180042b2b`
- `MobileNetworking!AcquireWriteLock` at `0x180042af2`
- `MobileNetworking!AcquireWriteLock` at `0x180042af2`

## string_xrefs

- `0x1800429c9`: `KeyMgrIntfUpdateGroupKey`
- `0x180042a97`: `KeyMgrIntfUpdateGroupKey`
- `0x180042ae8`: `KeyMgrIntfUpdateGroupKey`
- `0x180042b1e`: `KeyMgrIntfUpdateGroupKey`

## pseudocode

```c
__int64 __fastcall KeyMgrIntfUpdateGroupKey(struct MSMSEC_INTF_CONTEXT *a1)
{
  unsigned int PortPtrList; // eax
  unsigned int v3; // r14d
  int v4; // r15d
  PVOID *v5; // rcx
  __int64 v6; // rdx
  struct _LIST_ENTRY *Flink; // r12
  struct _LIST_ENTRY *v9; // rdi
  struct _LIST_ENTRY v10; // [rsp+20h] [rbp-18h] BYREF

  v10 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 272, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids);
  v10.Blink = &v10;
  v10.Flink = &v10;
  PortPtrList = SecMgrLockAndCheckAdapterDeleted(a1);
  v3 = PortPtrList;
  if ( PortPtrList )
  {
    v4 = 0;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v6 = 273;
LABEL_8:
      WPP_SF_d(v5[7], v6, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, PortPtrList);
LABEL_9:
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v4 = 1;
    if ( !GetNumActivePorts(a1) )
      goto LABEL_9;
    PortPtrList = SecMgrRefPortsAndGetPortPtrList(
                    *((struct _LIST_ENTRY **)a1 + 334),
                    (struct _LIST_ENTRY *)a1 + 167,
                    &v10);
    v3 = PortPtrList;
    if ( !PortPtrList )
    {
      TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Unlocking <<<");
      ReleaseWriteLock(a1, (char *)a1 + 2512, "KeyMgrIntfUpdateGroupKey", 3479);
      Flink = v10.Flink;
      v4 = 0;
      while ( Flink != &v10 )
      {
        v9 = Flink[1].Flink;
        TracePortId((unsigned int)v9[19].Blink, ">>> Locking >>>");
        AcquireWriteLock(v9, &v9[20], "KeyMgrIntfUpdateGroupKey", 3493);
        KeyMgrAuthUpdateGroupKey((struct MSMSEC_PORT_CONTEXT *)v9);
        TracePortId((unsigned int)v9[19].Blink, "<<< Unlocking <<<");
        ReleaseWriteLock(v9, &v9[20], "KeyMgrIntfUpdateGroupKey", 3495);
        Flink = Flink->Flink;
      }
      goto LABEL_9;
    }
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v6 = 274;
      goto LABEL_8;
    }
  }
  if ( v10.Flink != &v10 )
  {
    DerefPortsAndFreePortPtrListHelper(&v10, 1);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(a1, (char *)a1 + 2512, "KeyMgrIntfUpdateGroupKey", 3511);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x100) != 0 )
    WPP_SF_d(v5[7], 275, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800428e0  push    rbp
0x1800428e2  push    rbx
0x1800428e3  push    rsi
0x1800428e4  push    rdi
0x1800428e5  push    r12
0x1800428e7  push    r13
0x1800428e9  push    r14
0x1800428eb  push    r15
0x1800428ed  mov     rbp, rsp
0x1800428f0  sub     rsp, 38h
0x1800428f4  xorps   xmm0, xmm0
0x1800428f7  mov     rsi, rcx
0x1800428fa  movups  xmmword ptr [rbp+var_18.Flink], xmm0
0x1800428fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180042905  lea     r13, WPP_GLOBAL_Control
0x18004290c  cmp     rcx, r13
0x18004290f  jz      short loc_18004292F
0x180042911  test    dword ptr [rcx+44h], 100h
0x180042918  jz      short loc_18004292F
0x18004291a  mov     rcx, [rcx+38h]
0x18004291e  lea     r8, WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids
0x180042925  mov     edx, 110h
0x18004292a  call    WPP_SF_
0x18004292f  lea     rax, [rbp+var_18]
0x180042933  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x180042936  mov     [rbp+var_18.Blink], rax
0x18004293a  lea     rax, [rbp+var_18]
0x18004293e  mov     [rbp+var_18.Flink], rax
0x180042942  call    ?SecMgrLockAndCheckAdapterDeleted@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrLockAndCheckAdapterDeleted(MSMSEC_INTF_CONTEXT *)
0x180042947  mov     r14d, eax
0x18004294a  test    eax, eax
0x18004294c  jz      loc_180042A21
0x180042952  xor     r15d, r15d
0x180042955  mov     rcx, cs:WPP_GLOBAL_Control
0x18004295c  cmp     rcx, r13
0x18004295f  jz      short loc_180042986
0x180042961  test    byte ptr [rcx+44h], 1
0x180042965  jz      short loc_180042986
0x180042967  mov     edx, 111h
0x18004296c  mov     rcx, [rcx+38h]
0x180042970  lea     r8, WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids
0x180042977  mov     r9d, eax
0x18004297a  call    WPP_SF_d
0x18004297f  mov     rcx, cs:WPP_GLOBAL_Control
0x180042986  lea     rax, [rbp+var_18]
0x18004298a  cmp     [rbp+var_18.Flink], rax
0x18004298e  jz      short loc_1800429A5
0x180042990  mov     edx, 1; int
0x180042995  lea     rcx, [rbp+var_18]; struct _LIST_ENTRY *
0x180042999  call    ?DerefPortsAndFreePortPtrListHelper@@YAXPEAU_LIST_ENTRY@@H@Z; DerefPortsAndFreePortPtrListHelper(_LIST_ENTRY *,int)
0x18004299e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800429a5  test    r15d, r15d
0x1800429a8  jz      short loc_1800429E6
0x1800429aa  mov     ecx, [rsi+9C0h]; unsigned int
0x1800429b0  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800429b7  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800429bc  lea     rdx, [rsi+9D0h]
0x1800429c3  mov     r9d, 0DB7h
0x1800429c9  lea     r8, aKeymgrintfupda; "KeyMgrIntfUpdateGroupKey"
0x1800429d0  mov     rcx, rsi
0x1800429d3  call    cs:__imp_ReleaseWriteLock
0x1800429da  nop     dword ptr [rax+rax+00h]
0x1800429df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800429e6  cmp     rcx, r13
0x1800429e9  jz      short loc_180042A0C
0x1800429eb  test    dword ptr [rcx+44h], 100h
0x1800429f2  jz      short loc_180042A0C
0x1800429f4  mov     rcx, [rcx+38h]
0x1800429f8  lea     r8, WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids
0x1800429ff  mov     edx, 113h
0x180042a04  mov     r9d, r14d
0x180042a07  call    WPP_SF_d
0x180042a0c  mov     eax, r14d
0x180042a0f  add     rsp, 38h
0x180042a13  pop     r15
0x180042a15  pop     r14
0x180042a17  pop     r13
0x180042a19  pop     r12
0x180042a1b  pop     rdi
0x180042a1c  pop     rsi
0x180042a1d  pop     rbx
0x180042a1e  pop     rbp
0x180042a1f  retn
0x180042a21  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x180042a24  mov     r15d, 1
0x180042a2a  call    ?GetNumActivePorts@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; GetNumActivePorts(MSMSEC_INTF_CONTEXT *)
0x180042a2f  test    eax, eax
0x180042a31  jz      loc_18004297F
0x180042a37  lea     rcx, [rsi+0A70h]
0x180042a3e  mov     rdx, rcx; struct _LIST_ENTRY *
0x180042a41  lea     r8, [rbp+var_18]; struct _LIST_ENTRY *
0x180042a45  mov     rcx, [rcx]; struct _LIST_ENTRY *
0x180042a48  call    ?SecMgrRefPortsAndGetPortPtrList@@YAKPEAU_LIST_ENTRY@@00@Z; SecMgrRefPortsAndGetPortPtrList(_LIST_ENTRY *,_LIST_ENTRY *,_LIST_ENTRY *)
0x180042a4d  mov     r14d, eax
0x180042a50  test    eax, eax
0x180042a52  jz      short loc_180042A78
0x180042a54  mov     rcx, cs:WPP_GLOBAL_Control
0x180042a5b  cmp     rcx, r13
0x180042a5e  jz      loc_180042986
0x180042a64  test    [rcx+44h], r15b
0x180042a68  jz      loc_180042986
0x180042a6e  mov     edx, 112h
0x180042a73  jmp     loc_18004296C
0x180042a78  mov     ecx, [rsi+9C0h]; unsigned int
0x180042a7e  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180042a85  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180042a8a  lea     rdx, [rsi+9D0h]
0x180042a91  mov     r9d, 0D97h
0x180042a97  lea     r8, aKeymgrintfupda; "KeyMgrIntfUpdateGroupKey"
0x180042a9e  mov     rcx, rsi
0x180042aa1  call    cs:__imp_ReleaseWriteLock
0x180042aa8  nop     dword ptr [rax+rax+00h]
0x180042aad  mov     r12, [rbp+var_18.Flink]
0x180042ab1  xor     r15d, r15d
0x180042ab4  lea     rax, [rbp+var_18]
0x180042ab8  cmp     r12, rax
0x180042abb  jz      loc_18004297F
0x180042ac1  mov     rdi, [r12+10h]
0x180042ac6  lea     rdx, aLocking; ">>> Locking >>>"
0x180042acd  mov     ecx, [rdi+138h]; unsigned int
0x180042ad3  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180042ad8  lea     rbx, [rdi+140h]
0x180042adf  mov     r9d, 0DA5h
0x180042ae5  mov     rdx, rbx
0x180042ae8  lea     r8, aKeymgrintfupda; "KeyMgrIntfUpdateGroupKey"
0x180042aef  mov     rcx, rdi
0x180042af2  call    cs:__imp_AcquireWriteLock
0x180042af9  nop     dword ptr [rax+rax+00h]
0x180042afe  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180042b01  call    ?KeyMgrAuthUpdateGroupKey@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; KeyMgrAuthUpdateGroupKey(MSMSEC_PORT_CONTEXT *)
0x180042b06  mov     ecx, [rdi+138h]; unsigned int
0x180042b0c  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180042b13  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180042b18  mov     r9d, 0DA7h
0x180042b1e  lea     r8, aKeymgrintfupda; "KeyMgrIntfUpdateGroupKey"
0x180042b25  mov     rdx, rbx
0x180042b28  mov     rcx, rdi
0x180042b2b  call    cs:__imp_ReleaseWriteLock
0x180042b32  nop     dword ptr [rax+rax+00h]
0x180042b37  mov     r12, [r12]
0x180042b3b  jmp     loc_180042AB4
```
