# VCompWindowSizeSetHandler

- ea: `0x14002bd60`
- end: `0x14002beae`
- name: `VCompWindowSizeSetHandler`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a468`
- `0x14000a4b4`
- `0x14002af70`
- `0x14002bd60`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14002be7c`
- `ntoskrnl!KeReleaseSemaphore` at `0x14002be7c`
- `ks!KsReleaseControl` at `0x14002be8b`
- `ks!KsReleaseControl` at `0x14002be8b`
- `ks!KsAcquireControl` at `0x14002bdb1`
- `ks!KsAcquireControl` at `0x14002bdb1`
- `ks!KsGetFilterFromIrp` at `0x14002bd96`
- `ks!KsGetFilterFromIrp` at `0x14002bd96`
- `ks!KsGetDevice` at `0x14002bdc0`
- `ks!KsGetDevice` at `0x14002bdc0`

## pseudocode

```c
__int64 __fastcall VCompWindowSizeSetHandler(IRP *a1, __int64 a2)
{
  int v4; // ebx
  PKSFILTER FilterFromIrp; // rax
  PKSFILTER v6; // rsi
  PKSDEVICE Device; // rax
  int v8; // eax
  PKSDEVICE v9; // r15
  _WORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-10h] BYREF
  __int64 v13; // [rsp+38h] [rbp-8h] BYREF
  PKSDEVICE v14; // [rsp+70h] [rbp+30h] BYREF
  _WORD *v15; // [rsp+88h] [rbp+48h] BYREF

  v15 = 0;
  v13 = 0;
  v4 = -1073741823;
  v12 = 0;
  FilterFromIrp = KsGetFilterFromIrp(a1);
  v6 = FilterFromIrp;
  if ( FilterFromIrp )
  {
    KsAcquireControl(FilterFromIrp);
    Device = KsGetDevice(v6);
    v14 = Device;
    if ( Device )
    {
      v4 = AcquireProbeCommitLock((__int64)Device->Context);
      if ( v4 >= 0 )
      {
        v8 = InitializeProbeCommitControl(a1, *(_DWORD *)(a2 + 24), &v15, &v13, &v14, &v12);
        v9 = v14;
        v4 = v8;
        if ( v8 >= 0 )
        {
          v10 = v15;
          v15[7] = *(_WORD *)(a2 + 28);
          if ( a1->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options >= 0x28 )
            *v10 = (unsigned __int8)BYTE1(*(_DWORD *)(a2 + 32));
          v4 = ProbeCommitSetHandler((int)v9, v12, v13, 0, *(_DWORD *)(v12 + 104) != 0);
        }
        KeReleaseSemaphore(*((PRKSEMAPHORE *)v9->Context + 53), 0, 1, 0);
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
0x14002bd60  mov     [rsp-28h+arg_8], rbx
0x14002bd65  push    rbp
0x14002bd66  push    rsi
0x14002bd67  push    rdi
0x14002bd68  push    r14
0x14002bd6a  push    r15
0x14002bd6c  mov     rbp, rsp
0x14002bd6f  sub     rsp, 40h
0x14002bd73  mov     r14, rdx
0x14002bd76  mov     [rbp+arg_18], 0
0x14002bd7e  mov     rdi, rcx
0x14002bd81  mov     [rbp+var_8], 0
0x14002bd89  mov     ebx, 0C0000001h
0x14002bd8e  mov     [rbp+var_10], 0
0x14002bd96  call    cs:__imp_KsGetFilterFromIrp
0x14002bd9d  nop     dword ptr [rax+rax+00h]
0x14002bda2  mov     rsi, rax
0x14002bda5  test    rax, rax
0x14002bda8  jz      loc_14002BE97
0x14002bdae  mov     rcx, rax; Object
0x14002bdb1  call    cs:__imp_KsAcquireControl
0x14002bdb8  nop     dword ptr [rax+rax+00h]
0x14002bdbd  mov     rcx, rsi; Object
0x14002bdc0  call    cs:__imp_KsGetDevice
0x14002bdc7  nop     dword ptr [rax+rax+00h]
0x14002bdcc  mov     [rbp+arg_0], rax
0x14002bdd0  test    rax, rax
0x14002bdd3  jz      loc_14002BE88
0x14002bdd9  mov     rcx, [rax+10h]
0x14002bddd  call    AcquireProbeCommitLock
0x14002bde2  mov     ebx, eax
0x14002bde4  test    eax, eax
0x14002bde6  js      loc_14002BE88
0x14002bdec  mov     edx, [r14+18h]
0x14002bdf0  lea     rax, [rbp+var_10]
0x14002bdf4  mov     [rsp+40h+var_18], rax
0x14002bdf9  lea     r9, [rbp+var_8]
0x14002bdfd  lea     rax, [rbp+arg_0]
0x14002be01  mov     rcx, rdi
0x14002be04  lea     r8, [rbp+arg_18]
0x14002be08  mov     qword ptr [rsp+40h+var_20], rax
0x14002be0d  call    InitializeProbeCommitControl
0x14002be12  mov     r15, [rbp+arg_0]
0x14002be16  mov     ebx, eax
0x14002be18  test    eax, eax
0x14002be1a  js      short loc_14002BE68
0x14002be1c  movzx   eax, word ptr [r14+1Ch]
0x14002be21  mov     rcx, [rbp+arg_18]
0x14002be25  mov     [rcx+0Eh], ax
0x14002be29  mov     rax, [rdi+0B8h]
0x14002be30  cmp     dword ptr [rax+10h], 28h ; '('
0x14002be34  jb      short loc_14002BE48
0x14002be36  mov     eax, [r14+20h]
0x14002be3a  mov     edx, 0FFh
0x14002be3f  shr     eax, 8
0x14002be42  and     ax, dx
0x14002be45  mov     [rcx], ax
0x14002be48  mov     rdx, [rbp+var_10]
0x14002be4c  mov     rcx, r15; int
0x14002be4f  mov     r8, [rbp+var_8]
0x14002be53  cmp     dword ptr [rdx+68h], 0
0x14002be57  setnz   al
0x14002be5a  xor     r9d, r9d
0x14002be5d  mov     [rsp+40h+var_20], al; char
0x14002be61  call    ProbeCommitSetHandler
0x14002be66  mov     ebx, eax
0x14002be68  mov     rcx, [r15+10h]
0x14002be6c  xor     r9d, r9d; Wait
0x14002be6f  xor     edx, edx; Increment
0x14002be71  mov     rcx, [rcx+1A8h]; Semaphore
0x14002be78  lea     r8d, [r9+1]; Adjustment
0x14002be7c  call    cs:__imp_KeReleaseSemaphore
0x14002be83  nop     dword ptr [rax+rax+00h]
0x14002be88  mov     rcx, rsi; Object
0x14002be8b  call    cs:__imp_KsReleaseControl
0x14002be92  nop     dword ptr [rax+rax+00h]
0x14002be97  mov     [rdi+30h], ebx
0x14002be9a  mov     eax, ebx
0x14002be9c  mov     rbx, [rsp+40h+arg_8]
0x14002bea1  add     rsp, 40h
0x14002bea5  pop     r15
0x14002bea7  pop     r14
0x14002bea9  pop     rdi
0x14002beaa  pop     rsi
0x14002beab  pop     rbp
0x14002beac  retn
```
