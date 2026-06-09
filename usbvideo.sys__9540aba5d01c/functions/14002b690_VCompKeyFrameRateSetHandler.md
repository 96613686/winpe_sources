# VCompKeyFrameRateSetHandler

- ea: `0x14002b690`
- end: `0x14002b7de`
- name: `VCompKeyFrameRateSetHandler`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a468`
- `0x14000a4b4`
- `0x14002af70`
- `0x14002b690`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14002b7ac`
- `ntoskrnl!KeReleaseSemaphore` at `0x14002b7ac`
- `ks!KsReleaseControl` at `0x14002b7bb`
- `ks!KsReleaseControl` at `0x14002b7bb`
- `ks!KsAcquireControl` at `0x14002b6e1`
- `ks!KsAcquireControl` at `0x14002b6e1`
- `ks!KsGetFilterFromIrp` at `0x14002b6c6`
- `ks!KsGetFilterFromIrp` at `0x14002b6c6`
- `ks!KsGetDevice` at `0x14002b6f0`
- `ks!KsGetDevice` at `0x14002b6f0`

## pseudocode

```c
__int64 __fastcall VCompKeyFrameRateSetHandler(IRP *a1, __int64 a2)
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
          v15[4] = *(_WORD *)(a2 + 28);
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
0x14002b690  mov     [rsp-28h+arg_8], rbx
0x14002b695  push    rbp
0x14002b696  push    rsi
0x14002b697  push    rdi
0x14002b698  push    r14
0x14002b69a  push    r15
0x14002b69c  mov     rbp, rsp
0x14002b69f  sub     rsp, 40h
0x14002b6a3  mov     r14, rdx
0x14002b6a6  mov     [rbp+arg_18], 0
0x14002b6ae  mov     rdi, rcx
0x14002b6b1  mov     [rbp+var_8], 0
0x14002b6b9  mov     ebx, 0C0000001h
0x14002b6be  mov     [rbp+var_10], 0
0x14002b6c6  call    cs:__imp_KsGetFilterFromIrp
0x14002b6cd  nop     dword ptr [rax+rax+00h]
0x14002b6d2  mov     rsi, rax
0x14002b6d5  test    rax, rax
0x14002b6d8  jz      loc_14002B7C7
0x14002b6de  mov     rcx, rax; Object
0x14002b6e1  call    cs:__imp_KsAcquireControl
0x14002b6e8  nop     dword ptr [rax+rax+00h]
0x14002b6ed  mov     rcx, rsi; Object
0x14002b6f0  call    cs:__imp_KsGetDevice
0x14002b6f7  nop     dword ptr [rax+rax+00h]
0x14002b6fc  mov     [rbp+arg_0], rax
0x14002b700  test    rax, rax
0x14002b703  jz      loc_14002B7B8
0x14002b709  mov     rcx, [rax+10h]
0x14002b70d  call    AcquireProbeCommitLock
0x14002b712  mov     ebx, eax
0x14002b714  test    eax, eax
0x14002b716  js      loc_14002B7B8
0x14002b71c  mov     edx, [r14+18h]
0x14002b720  lea     rax, [rbp+var_10]
0x14002b724  mov     [rsp+40h+var_18], rax
0x14002b729  lea     r9, [rbp+var_8]
0x14002b72d  lea     rax, [rbp+arg_0]
0x14002b731  mov     rcx, rdi
0x14002b734  lea     r8, [rbp+arg_18]
0x14002b738  mov     qword ptr [rsp+40h+var_20], rax
0x14002b73d  call    InitializeProbeCommitControl
0x14002b742  mov     r15, [rbp+arg_0]
0x14002b746  mov     ebx, eax
0x14002b748  test    eax, eax
0x14002b74a  js      short loc_14002B798
0x14002b74c  movzx   eax, word ptr [r14+1Ch]
0x14002b751  mov     rcx, [rbp+arg_18]
0x14002b755  mov     [rcx+8], ax
0x14002b759  mov     rax, [rdi+0B8h]
0x14002b760  cmp     dword ptr [rax+10h], 28h ; '('
0x14002b764  jb      short loc_14002B778
0x14002b766  mov     eax, [r14+20h]
0x14002b76a  mov     edx, 0FFh
0x14002b76f  shr     eax, 8
0x14002b772  and     ax, dx
0x14002b775  mov     [rcx], ax
0x14002b778  mov     rdx, [rbp+var_10]
0x14002b77c  mov     rcx, r15; int
0x14002b77f  mov     r8, [rbp+var_8]
0x14002b783  cmp     dword ptr [rdx+68h], 0
0x14002b787  setnz   al
0x14002b78a  xor     r9d, r9d
0x14002b78d  mov     [rsp+40h+var_20], al; char
0x14002b791  call    ProbeCommitSetHandler
0x14002b796  mov     ebx, eax
0x14002b798  mov     rcx, [r15+10h]
0x14002b79c  xor     r9d, r9d; Wait
0x14002b79f  xor     edx, edx; Increment
0x14002b7a1  mov     rcx, [rcx+1A8h]; Semaphore
0x14002b7a8  lea     r8d, [r9+1]; Adjustment
0x14002b7ac  call    cs:__imp_KeReleaseSemaphore
0x14002b7b3  nop     dword ptr [rax+rax+00h]
0x14002b7b8  mov     rcx, rsi; Object
0x14002b7bb  call    cs:__imp_KsReleaseControl
0x14002b7c2  nop     dword ptr [rax+rax+00h]
0x14002b7c7  mov     [rdi+30h], ebx
0x14002b7ca  mov     eax, ebx
0x14002b7cc  mov     rbx, [rsp+40h+arg_8]
0x14002b7d1  add     rsp, 40h
0x14002b7d5  pop     r15
0x14002b7d7  pop     r14
0x14002b7d9  pop     rdi
0x14002b7da  pop     rsi
0x14002b7db  pop     rbp
0x14002b7dc  retn
```
