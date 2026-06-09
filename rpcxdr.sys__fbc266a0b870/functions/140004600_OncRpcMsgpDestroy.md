# OncRpcMsgpDestroy

- ea: `0x140004600`
- end: `0x14000476c`
- name: `OncRpcMsgpDestroy`
- size: `364`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140002b00`
- `0x140002f20`

## callees

- `0x14000127c`
- `0x140002170`
- `0x140002f20`
- `0x140004600`
- `0x1400059a4`
- `0x140008f58`
- `0x14000fa0c`
- `0x14000fabc`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400046fe`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400046fe`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000460d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000460d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004657`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400046a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400046d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004657`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400046a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400046d5`

## pseudocode

```c
void __fastcall OncRpcMsgpDestroy(_QWORD *Entry)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rbx
  int v8; // edi

  if ( KeGetCurrentIrql() >= 2u && (Entry[11] & 2) != 0 )
  {
    OncRpcWiMgrQueueSrvWorkItem(Entry[31], OncRpcMsgDestroy, Entry);
  }
  else
  {
    *((_DWORD *)Entry + 64) |= 8u;
    v2 = (void *)Entry[133];
    if ( v2 )
      ExFreePoolWithTag(v2, 0x766F4752u);
    v3 = (void *)Entry[129];
    if ( v3 )
      OncRpcMsgOutgoingCallDereference(v3);
    v4 = Entry[125];
    if ( v4 )
      NfsStandardHeaderDereferenceNoType(v4);
    if ( Entry[126] )
      OncRpcSeDereferenceOutboundGssCtx();
    v5 = (void *)Entry[127];
    if ( v5 )
      ExFreePoolWithTag(v5, 0x49734752u);
    if ( !*((_DWORD *)Entry + 67) && *((_DWORD *)Entry + 74) == 6 )
    {
      v6 = (void *)Entry[44];
      if ( v6 )
        ExFreePoolWithTag(v6, 0x49734752u);
    }
    OncRpcBufMgrFree(Entry + 4);
    if ( (Entry[32] & 4) != 0 )
    {
      ExFreeToNPagedLookasideList(&stru_14001A700, Entry);
    }
    else
    {
      v7 = Entry[31];
      v8 = NfsStandardHeaderDereferenceNoType(v7);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids, v7, v8);
      if ( !v8 )
        OncRpcWiMgrSrvWorkItemFree(v7);
    }
  }
}

```

## disassembly

```asm
0x140004600  mov     [rsp+arg_0], rbx
0x140004605  push    rdi
0x140004606  sub     rsp, 30h
0x14000460a  mov     rbx, rcx
0x14000460d  call    cs:__imp_KeGetCurrentIrql
0x140004614  nop     dword ptr [rax+rax+00h]
0x140004619  cmp     al, 2
0x14000461b  jb      short loc_14000463F
0x14000461d  mov     eax, [rbx+58h]
0x140004620  test    al, 2
0x140004622  jz      short loc_14000463F
0x140004624  mov     rcx, [rbx+0F8h]
0x14000462b  lea     rdx, OncRpcMsgDestroy
0x140004632  mov     r8, rbx
0x140004635  call    OncRpcWiMgrQueueSrvWorkItem
0x14000463a  jmp     loc_140004760
0x14000463f  or      dword ptr [rbx+100h], 8
0x140004646  mov     rcx, [rbx+428h]; P
0x14000464d  test    rcx, rcx
0x140004650  jz      short loc_140004663
0x140004652  mov     edx, 766F4752h; Tag
0x140004657  call    cs:__imp_ExFreePoolWithTag
0x14000465e  nop     dword ptr [rax+rax+00h]
0x140004663  mov     rcx, [rbx+408h]
0x14000466a  test    rcx, rcx
0x14000466d  jz      short loc_140004674
0x14000466f  call    OncRpcMsgOutgoingCallDereference
0x140004674  mov     rcx, [rbx+3E8h]
0x14000467b  test    rcx, rcx
0x14000467e  jz      short loc_140004685
0x140004680  call    NfsStandardHeaderDereferenceNoType
0x140004685  mov     rcx, [rbx+3F0h]
0x14000468c  test    rcx, rcx
0x14000468f  jz      short loc_140004696
0x140004691  call    OncRpcSeDereferenceOutboundGssCtx
0x140004696  mov     rcx, [rbx+3F8h]; P
0x14000469d  mov     edi, 49734752h
0x1400046a2  test    rcx, rcx
0x1400046a5  jz      short loc_1400046B5
0x1400046a7  mov     edx, edi; Tag
0x1400046a9  call    cs:__imp_ExFreePoolWithTag
0x1400046b0  nop     dword ptr [rax+rax+00h]
0x1400046b5  cmp     dword ptr [rbx+10Ch], 0
0x1400046bc  jnz     short loc_1400046E1
0x1400046be  cmp     dword ptr [rbx+128h], 6
0x1400046c5  jnz     short loc_1400046E1
0x1400046c7  mov     rcx, [rbx+160h]; P
0x1400046ce  test    rcx, rcx
0x1400046d1  jz      short loc_1400046E1
0x1400046d3  mov     edx, edi; Tag
0x1400046d5  call    cs:__imp_ExFreePoolWithTag
0x1400046dc  nop     dword ptr [rax+rax+00h]
0x1400046e1  lea     rcx, [rbx+20h]; Entry
0x1400046e5  call    OncRpcBufMgrFree
0x1400046ea  mov     eax, [rbx+100h]
0x1400046f0  test    al, 4
0x1400046f2  jz      short loc_14000470C
0x1400046f4  mov     rdx, rbx; Entry
0x1400046f7  lea     rcx, stru_14001A700; Lookaside
0x1400046fe  call    cs:__imp_ExFreeToNPagedLookasideList
0x140004705  nop     dword ptr [rax+rax+00h]
0x14000470a  jmp     short loc_140004760
0x14000470c  mov     rbx, [rbx+0F8h]
0x140004713  mov     rcx, rbx
0x140004716  call    NfsStandardHeaderDereferenceNoType
0x14000471b  mov     edi, eax
0x14000471d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004724  lea     rax, WPP_GLOBAL_Control
0x14000472b  cmp     rcx, rax
0x14000472e  jz      short loc_140004754
0x140004730  mov     edx, [rcx+2Ch]
0x140004733  test    dl, 4
0x140004736  jz      short loc_140004754
0x140004738  mov     rcx, [rcx+18h]
0x14000473c  lea     r8, WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids
0x140004743  mov     edx, 1Eh
0x140004748  mov     [rsp+38h+var_18], edi
0x14000474c  mov     r9, rbx
0x14000474f  call    WPP_SF_qd
0x140004754  test    edi, edi
0x140004756  jnz     short loc_140004760
0x140004758  mov     rcx, rbx
0x14000475b  call    OncRpcWiMgrSrvWorkItemFree
0x140004760  mov     rbx, [rsp+38h+arg_0]
0x140004765  add     rsp, 30h
0x140004769  pop     rdi
0x14000476a  retn
```
