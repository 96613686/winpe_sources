# FilterDispatch

- ea: `0x14000c5b0`
- end: `0x14000c7aa`
- name: `FilterDispatch`
- size: `506`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000443c`
- `0x14000448c`
- `0x140006960`
- `0x140009270`
- `0x14000a730`
- `0x14000c5b0`
- `0x14000d8ec`
- `0x14000d91c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000c759`
- `ntoskrnl!IofCompleteRequest` at `0x14000c759`

## pseudocode

```c
__int64 __fastcall FilterDispatch(__int64 a1, IRP *a2)
{
  IRP *v2; // rsi
  unsigned int v3; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _DEVICE_OBJECT **v5; // rdi
  struct _DEVICE_OBJECT *v6; // rbp
  struct _DEVICE_OBJECT **v7; // rcx

  v2 = a2;
  v3 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->MajorFunction )
  {
    if ( CurrentStackLocation->MajorFunction == 18 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
      AcquireSpinLock(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, "FilterDispatch", 490, 0);
      v5 = (struct _DEVICE_OBJECT **)WPP_MAIN_CB.DeviceQueue.1;
      if ( (BOOLEAN *)WPP_MAIN_CB.DeviceQueue.32 != &WPP_MAIN_CB.DeviceQueue.Busy )
      {
        do
        {
          v6 = *v5;
          FilterAddRef(v5);
          ReleaseSpinLock(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, "FilterDispatch", 502, 0);
          v3 = FilterRemoveAllVirtualAdapters(v5);
          if ( v3
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
          }
          AcquireSpinLock(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, "FilterDispatch", 509, 0);
          v7 = v5;
          if ( v6 != *v5 )
            v6 = (struct _DEVICE_OBJECT *)WPP_MAIN_CB.DeviceQueue.1;
          v5 = (struct _DEVICE_OBJECT **)v6;
          FilterDeRef(v7);
        }
        while ( v6 != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy );
        v2 = a2;
      }
      ReleaseSpinLock(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, "FilterDispatch", 527, 0);
    }
  }
  else if ( CurrentStackLocation->FileObject->FileName.Length )
  {
    v3 = -1073741790;
  }
  v2->IoStatus.Status = v3;
  IofCompleteRequest(v2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x14000c5b0  mov     [rsp+arg_0], rbx
0x14000c5b5  mov     [rsp+arg_10], rbp
0x14000c5ba  mov     [rsp+arg_8], rdx
0x14000c5bf  push    rsi
0x14000c5c0  push    rdi
0x14000c5c1  push    r12
0x14000c5c3  push    r14
0x14000c5c5  push    r15
0x14000c5c7  sub     rsp, 20h
0x14000c5cb  xor     r12d, r12d
0x14000c5ce  mov     rsi, rdx
0x14000c5d1  mov     ebx, r12d
0x14000c5d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c5db  lea     r15, WPP_GLOBAL_Control
0x14000c5e2  cmp     rcx, r15
0x14000c5e5  jz      short loc_14000C603
0x14000c5e7  mov     eax, [rcx+2Ch]
0x14000c5ea  test    al, 20h
0x14000c5ec  jz      short loc_14000C603
0x14000c5ee  mov     rcx, [rcx+18h]
0x14000c5f2  lea     edx, [r12+2Ah]
0x14000c5f7  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x14000c5fe  call    WPP_SF_
0x14000c603  mov     rcx, [rsi+0B8h]
0x14000c60a  mov     al, [rcx]
0x14000c60c  test    al, al
0x14000c60e  jz      loc_14000C740
0x14000c614  cmp     al, 12h
0x14000c616  jnz     loc_14000C751
0x14000c61c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c623  cmp     rcx, r15
0x14000c626  jz      short loc_14000C644
0x14000c628  mov     eax, [rcx+2Ch]
0x14000c62b  test    al, 20h
0x14000c62d  jz      short loc_14000C644
0x14000c62f  mov     rcx, [rcx+18h]
0x14000c633  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x14000c63a  mov     edx, 2Bh ; '+'
0x14000c63f  call    WPP_SF_
0x14000c644  xor     r9d, r9d
0x14000c647  lea     rdx, aFilterdispatch; "FilterDispatch"
0x14000c64e  mov     r8d, 1EAh
0x14000c654  lea     rcx, WPP_MAIN_CB.Queue+10h
0x14000c65b  call    AcquireSpinLock
0x14000c660  mov     rdi, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x14000c667  lea     rax, WPP_MAIN_CB.DeviceQueue.20h
0x14000c66e  cmp     rdi, rax
0x14000c671  jz      loc_14000C722
0x14000c677  lea     rsi, WPP_MAIN_CB.DeviceQueue.20h
0x14000c67e  mov     rbp, [rdi]
0x14000c681  mov     rcx, rdi
0x14000c684  mov     r14, rdi
0x14000c687  call    FilterAddRef
0x14000c68c  xor     r9d, r9d
0x14000c68f  lea     rdx, aFilterdispatch; "FilterDispatch"
0x14000c696  mov     r8d, 1F6h
0x14000c69c  lea     rcx, WPP_MAIN_CB.Queue+10h
0x14000c6a3  call    ReleaseSpinLock
0x14000c6a8  mov     rcx, rdi
0x14000c6ab  call    FilterRemoveAllVirtualAdapters
0x14000c6b0  mov     ebx, eax
0x14000c6b2  test    eax, eax
0x14000c6b4  jz      short loc_14000C6E2
0x14000c6b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c6bd  cmp     rcx, r15
0x14000c6c0  jz      short loc_14000C6E2
0x14000c6c2  mov     edx, [rcx+2Ch]
0x14000c6c5  test    dl, 1
0x14000c6c8  jz      short loc_14000C6E2
0x14000c6ca  mov     rcx, [rcx+18h]
0x14000c6ce  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x14000c6d5  mov     edx, 2Ch ; ','
0x14000c6da  mov     r9d, eax
0x14000c6dd  call    WPP_SF_d
0x14000c6e2  xor     r9d, r9d
0x14000c6e5  lea     rdx, aFilterdispatch; "FilterDispatch"
0x14000c6ec  mov     r8d, 1FDh
0x14000c6f2  lea     rcx, WPP_MAIN_CB.Queue+10h
0x14000c6f9  call    AcquireSpinLock
0x14000c6fe  cmp     rbp, [rdi]
0x14000c701  mov     rcx, r14; VirtualAddress
0x14000c704  cmovnz  rbp, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x14000c70c  mov     rdi, rbp
0x14000c70f  call    FilterDeRef
0x14000c714  cmp     rbp, rsi
0x14000c717  jnz     loc_14000C67E
0x14000c71d  mov     rsi, [rsp+48h+arg_8]
0x14000c722  xor     r9d, r9d
0x14000c725  lea     rdx, aFilterdispatch; "FilterDispatch"
0x14000c72c  mov     r8d, 20Fh
0x14000c732  lea     rcx, WPP_MAIN_CB.Queue+10h
0x14000c739  call    ReleaseSpinLock
0x14000c73e  jmp     short loc_14000C751
0x14000c740  mov     rax, [rcx+30h]
0x14000c744  mov     ecx, 0C0000022h
0x14000c749  cmp     [rax+58h], r12w
0x14000c74e  cmovnz  ebx, ecx
0x14000c751  xor     edx, edx; PriorityBoost
0x14000c753  mov     [rsi+30h], ebx
0x14000c756  mov     rcx, rsi; Irp
0x14000c759  call    cs:__imp_IofCompleteRequest
0x14000c760  nop     dword ptr [rax+rax+00h]
0x14000c765  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c76c  cmp     rcx, r15
0x14000c76f  jz      short loc_14000C790
0x14000c771  mov     eax, [rcx+2Ch]
0x14000c774  test    al, 20h
0x14000c776  jz      short loc_14000C790
0x14000c778  mov     rcx, [rcx+18h]
0x14000c77c  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x14000c783  mov     edx, 2Dh ; '-'
0x14000c788  mov     r9d, ebx
0x14000c78b  call    WPP_SF_d
0x14000c790  mov     rbp, [rsp+48h+arg_10]
0x14000c795  mov     eax, ebx
0x14000c797  mov     rbx, [rsp+48h+arg_0]
0x14000c79c  add     rsp, 20h
0x14000c7a0  pop     r15
0x14000c7a2  pop     r14
0x14000c7a4  pop     r12
0x14000c7a6  pop     rdi
0x14000c7a7  pop     rsi
0x14000c7a8  retn
```
