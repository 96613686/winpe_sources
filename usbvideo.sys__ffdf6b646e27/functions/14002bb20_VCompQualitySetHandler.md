# VCompQualitySetHandler

- ea: `0x14002bb20`
- end: `0x14002bc6e`
- name: `VCompQualitySetHandler`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a468`
- `0x14000a4b4`
- `0x14002af70`
- `0x14002bb20`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14002bc3c`
- `ntoskrnl!KeReleaseSemaphore` at `0x14002bc3c`
- `ks!KsReleaseControl` at `0x14002bc4b`
- `ks!KsReleaseControl` at `0x14002bc4b`
- `ks!KsAcquireControl` at `0x14002bb71`
- `ks!KsAcquireControl` at `0x14002bb71`
- `ks!KsGetFilterFromIrp` at `0x14002bb56`
- `ks!KsGetFilterFromIrp` at `0x14002bb56`
- `ks!KsGetDevice` at `0x14002bb80`
- `ks!KsGetDevice` at `0x14002bb80`

## pseudocode

```c
__int64 __fastcall VCompQualitySetHandler(IRP *a1, __int64 a2)
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
          v15[6] = *(_WORD *)(a2 + 28);
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
0x14002bb20  mov     [rsp-28h+arg_8], rbx
0x14002bb25  push    rbp
0x14002bb26  push    rsi
0x14002bb27  push    rdi
0x14002bb28  push    r14
0x14002bb2a  push    r15
0x14002bb2c  mov     rbp, rsp
0x14002bb2f  sub     rsp, 40h
0x14002bb33  mov     r14, rdx
0x14002bb36  mov     [rbp+arg_18], 0
0x14002bb3e  mov     rdi, rcx
0x14002bb41  mov     [rbp+var_8], 0
0x14002bb49  mov     ebx, 0C0000001h
0x14002bb4e  mov     [rbp+var_10], 0
0x14002bb56  call    cs:__imp_KsGetFilterFromIrp
0x14002bb5d  nop     dword ptr [rax+rax+00h]
0x14002bb62  mov     rsi, rax
0x14002bb65  test    rax, rax
0x14002bb68  jz      loc_14002BC57
0x14002bb6e  mov     rcx, rax; Object
0x14002bb71  call    cs:__imp_KsAcquireControl
0x14002bb78  nop     dword ptr [rax+rax+00h]
0x14002bb7d  mov     rcx, rsi; Object
0x14002bb80  call    cs:__imp_KsGetDevice
0x14002bb87  nop     dword ptr [rax+rax+00h]
0x14002bb8c  mov     [rbp+arg_0], rax
0x14002bb90  test    rax, rax
0x14002bb93  jz      loc_14002BC48
0x14002bb99  mov     rcx, [rax+10h]
0x14002bb9d  call    AcquireProbeCommitLock
0x14002bba2  mov     ebx, eax
0x14002bba4  test    eax, eax
0x14002bba6  js      loc_14002BC48
0x14002bbac  mov     edx, [r14+18h]
0x14002bbb0  lea     rax, [rbp+var_10]
0x14002bbb4  mov     [rsp+40h+var_18], rax
0x14002bbb9  lea     r9, [rbp+var_8]
0x14002bbbd  lea     rax, [rbp+arg_0]
0x14002bbc1  mov     rcx, rdi
0x14002bbc4  lea     r8, [rbp+arg_18]
0x14002bbc8  mov     qword ptr [rsp+40h+var_20], rax
0x14002bbcd  call    InitializeProbeCommitControl
0x14002bbd2  mov     r15, [rbp+arg_0]
0x14002bbd6  mov     ebx, eax
0x14002bbd8  test    eax, eax
0x14002bbda  js      short loc_14002BC28
0x14002bbdc  movzx   eax, word ptr [r14+1Ch]
0x14002bbe1  mov     rcx, [rbp+arg_18]
0x14002bbe5  mov     [rcx+0Ch], ax
0x14002bbe9  mov     rax, [rdi+0B8h]
0x14002bbf0  cmp     dword ptr [rax+10h], 28h ; '('
0x14002bbf4  jb      short loc_14002BC08
0x14002bbf6  mov     eax, [r14+20h]
0x14002bbfa  mov     edx, 0FFh
0x14002bbff  shr     eax, 8
0x14002bc02  and     ax, dx
0x14002bc05  mov     [rcx], ax
0x14002bc08  mov     rdx, [rbp+var_10]
0x14002bc0c  mov     rcx, r15; int
0x14002bc0f  mov     r8, [rbp+var_8]
0x14002bc13  cmp     dword ptr [rdx+68h], 0
0x14002bc17  setnz   al
0x14002bc1a  xor     r9d, r9d
0x14002bc1d  mov     [rsp+40h+var_20], al; char
0x14002bc21  call    ProbeCommitSetHandler
0x14002bc26  mov     ebx, eax
0x14002bc28  mov     rcx, [r15+10h]
0x14002bc2c  xor     r9d, r9d; Wait
0x14002bc2f  xor     edx, edx; Increment
0x14002bc31  mov     rcx, [rcx+1A8h]; Semaphore
0x14002bc38  lea     r8d, [r9+1]; Adjustment
0x14002bc3c  call    cs:__imp_KeReleaseSemaphore
0x14002bc43  nop     dword ptr [rax+rax+00h]
0x14002bc48  mov     rcx, rsi; Object
0x14002bc4b  call    cs:__imp_KsReleaseControl
0x14002bc52  nop     dword ptr [rax+rax+00h]
0x14002bc57  mov     [rdi+30h], ebx
0x14002bc5a  mov     eax, ebx
0x14002bc5c  mov     rbx, [rsp+40h+arg_8]
0x14002bc61  add     rsp, 40h
0x14002bc65  pop     r15
0x14002bc67  pop     r14
0x14002bc69  pop     rdi
0x14002bc6a  pop     rsi
0x14002bc6b  pop     rbp
0x14002bc6c  retn
```
