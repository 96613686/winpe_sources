# VCompPFramesPerKeyFrameSetHandler

- ea: `0x14002b8e0`
- end: `0x14002ba2a`
- name: `VCompPFramesPerKeyFrameSetHandler`
- size: `330`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a468`
- `0x14000a4b4`
- `0x14002af70`
- `0x14002b8e0`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14002b9f8`
- `ntoskrnl!KeReleaseSemaphore` at `0x14002b9f8`
- `ks!KsReleaseControl` at `0x14002ba07`
- `ks!KsReleaseControl` at `0x14002ba07`
- `ks!KsAcquireControl` at `0x14002b931`
- `ks!KsAcquireControl` at `0x14002b931`
- `ks!KsGetFilterFromIrp` at `0x14002b916`
- `ks!KsGetFilterFromIrp` at `0x14002b916`
- `ks!KsGetDevice` at `0x14002b940`
- `ks!KsGetDevice` at `0x14002b940`

## pseudocode

```c
__int64 __fastcall VCompPFramesPerKeyFrameSetHandler(IRP *a1, __int64 a2)
{
  int v4; // ebx
  PKSFILTER FilterFromIrp; // rax
  PKSFILTER v6; // rsi
  PKSDEVICE Device; // rax
  __int64 Context; // r15
  _WORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  int v12[2]; // [rsp+38h] [rbp-8h] BYREF
  _WORD *v13; // [rsp+70h] [rbp+30h] BYREF
  __int64 v14; // [rsp+88h] [rbp+48h] BYREF

  v13 = 0;
  v11 = 0;
  v4 = -1073741823;
  v14 = 0;
  FilterFromIrp = KsGetFilterFromIrp(a1);
  v6 = FilterFromIrp;
  if ( FilterFromIrp )
  {
    KsAcquireControl(FilterFromIrp);
    Device = KsGetDevice(v6);
    *(_QWORD *)v12 = Device;
    if ( Device )
    {
      Context = (__int64)Device->Context;
      v4 = AcquireProbeCommitLock(Context);
      if ( v4 >= 0 )
      {
        v4 = InitializeProbeCommitControl(a1, *(_DWORD *)(a2 + 24), &v13, &v11, (PKSDEVICE *)v12, &v14);
        if ( v4 >= 0 )
        {
          v9 = v13;
          v13[5] = *(_WORD *)(a2 + 28);
          if ( a1->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options >= 0x28 )
            *v9 = (unsigned __int8)BYTE1(*(_DWORD *)(a2 + 32));
          v4 = ProbeCommitSetHandler(v12[0], v14, v11, 0, *(_DWORD *)(v14 + 104) != 0);
        }
        KeReleaseSemaphore(*(PRKSEMAPHORE *)(Context + 424), 0, 1, 0);
      }
    }
    KsReleaseControl(v6);
  }
  a1->IoStatus.Status = v4;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14002b8e0  mov     [rsp-28h+arg_8], rbx
0x14002b8e5  push    rbp
0x14002b8e6  push    rsi
0x14002b8e7  push    rdi
0x14002b8e8  push    r14
0x14002b8ea  push    r15
0x14002b8ec  mov     rbp, rsp
0x14002b8ef  sub     rsp, 40h
0x14002b8f3  mov     r14, rdx
0x14002b8f6  mov     [rbp+arg_0], 0
0x14002b8fe  mov     rdi, rcx
0x14002b901  mov     [rbp+var_10], 0
0x14002b909  mov     ebx, 0C0000001h
0x14002b90e  mov     [rbp+arg_18], 0
0x14002b916  call    cs:__imp_KsGetFilterFromIrp
0x14002b91d  nop     dword ptr [rax+rax+00h]
0x14002b922  mov     rsi, rax
0x14002b925  test    rax, rax
0x14002b928  jz      loc_14002BA13
0x14002b92e  mov     rcx, rax; Object
0x14002b931  call    cs:__imp_KsAcquireControl
0x14002b938  nop     dword ptr [rax+rax+00h]
0x14002b93d  mov     rcx, rsi; Object
0x14002b940  call    cs:__imp_KsGetDevice
0x14002b947  nop     dword ptr [rax+rax+00h]
0x14002b94c  mov     qword ptr [rbp+var_8], rax
0x14002b950  test    rax, rax
0x14002b953  jz      loc_14002BA04
0x14002b959  mov     r15, [rax+10h]
0x14002b95d  mov     rcx, r15
0x14002b960  call    AcquireProbeCommitLock
0x14002b965  mov     ebx, eax
0x14002b967  test    eax, eax
0x14002b969  js      loc_14002BA04
0x14002b96f  mov     edx, [r14+18h]
0x14002b973  lea     rax, [rbp+arg_18]
0x14002b977  mov     [rsp+40h+var_18], rax
0x14002b97c  lea     r9, [rbp+var_10]
0x14002b980  lea     rax, [rbp+var_8]
0x14002b984  mov     rcx, rdi
0x14002b987  lea     r8, [rbp+arg_0]
0x14002b98b  mov     qword ptr [rsp+40h+var_20], rax
0x14002b990  call    InitializeProbeCommitControl
0x14002b995  mov     ebx, eax
0x14002b997  test    eax, eax
0x14002b999  js      short loc_14002B9E8
0x14002b99b  movzx   eax, word ptr [r14+1Ch]
0x14002b9a0  mov     rcx, [rbp+arg_0]
0x14002b9a4  mov     [rcx+0Ah], ax
0x14002b9a8  mov     rax, [rdi+0B8h]
0x14002b9af  cmp     dword ptr [rax+10h], 28h ; '('
0x14002b9b3  jb      short loc_14002B9C7
0x14002b9b5  mov     eax, [r14+20h]
0x14002b9b9  mov     edx, 0FFh
0x14002b9be  shr     eax, 8
0x14002b9c1  and     ax, dx
0x14002b9c4  mov     [rcx], ax
0x14002b9c7  mov     rdx, [rbp+arg_18]
0x14002b9cb  mov     r8, [rbp+var_10]
0x14002b9cf  mov     rcx, qword ptr [rbp+var_8]; int
0x14002b9d3  cmp     dword ptr [rdx+68h], 0
0x14002b9d7  setnz   al
0x14002b9da  xor     r9d, r9d
0x14002b9dd  mov     [rsp+40h+var_20], al; char
0x14002b9e1  call    ProbeCommitSetHandler
0x14002b9e6  mov     ebx, eax
0x14002b9e8  mov     rcx, [r15+1A8h]; Semaphore
0x14002b9ef  xor     r9d, r9d; Wait
0x14002b9f2  xor     edx, edx; Increment
0x14002b9f4  lea     r8d, [r9+1]; Adjustment
0x14002b9f8  call    cs:__imp_KeReleaseSemaphore
0x14002b9ff  nop     dword ptr [rax+rax+00h]
0x14002ba04  mov     rcx, rsi; Object
0x14002ba07  call    cs:__imp_KsReleaseControl
0x14002ba0e  nop     dword ptr [rax+rax+00h]
0x14002ba13  mov     [rdi+30h], ebx
0x14002ba16  mov     eax, ebx
0x14002ba18  mov     rbx, [rsp+40h+arg_8]
0x14002ba1d  add     rsp, 40h
0x14002ba21  pop     r15
0x14002ba23  pop     r14
0x14002ba25  pop     rdi
0x14002ba26  pop     rsi
0x14002ba27  pop     rbp
0x14002ba28  retn
```
