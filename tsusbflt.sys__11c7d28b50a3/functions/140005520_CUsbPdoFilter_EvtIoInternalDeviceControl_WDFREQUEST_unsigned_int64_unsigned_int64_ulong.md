# CUsbPdoFilter::EvtIoInternalDeviceControl(WDFREQUEST__ *,unsigned __int64,unsigned __int64,ulong)

- ea: `0x140005520`
- end: `0x14000574d`
- name: `?EvtIoInternalDeviceControl@CUsbPdoFilter@@QEAAXPEAUWDFREQUEST__@@_K1K@Z`
- size: `557`
- prototype: `void __fastcall(CUsbPdoFilter *this, struct WDFREQUEST__ *, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140009a70`

## callees

- `0x140004f48`
- `0x140005520`
- `0x140006128`
- `0x14000a9f0`
- `0x14000aa30`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByPointer` at `0x140005654`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x140005654`
- `ntoskrnl!PsProcessType` at `0x140005641`

## pseudocode

```c
void __fastcall CUsbPdoFilter::EvtIoInternalDeviceControl(
        CUsbPdoFilter *this,
        struct WDFREQUEST__ *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  __int64 v5; // r14
  __int64 v8; // r8
  NTSTATUS v9; // ebx
  _OWORD *v10; // [rsp+30h] [rbp-30h] BYREF
  __int64 v11; // [rsp+38h] [rbp-28h] BYREF
  __int128 v12; // [rsp+40h] [rbp-20h] BYREF

  v5 = 0;
  v12 = 0;
  if ( a5 == 2245635 )
  {
    v10 = 0;
    v11 = 0;
    v9 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, _OWORD **, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a2,
           16,
           &v10,
           &v11);
    if ( v9 < 0 )
      goto LABEL_18;
    v5 = 16;
    *v10 = *((_OWORD *)this + 1);
LABEL_17:
    v9 = 0;
    goto LABEL_18;
  }
  if ( a5 == 2245639 )
  {
    v10 = 0;
    v11 = 0;
    v9 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, _OWORD **, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a2,
           8,
           &v10,
           &v11);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          23,
          WPP_be851031edc93d18f2bbe38844c4b0c7_Traceguids,
          (unsigned int)v9);
      goto LABEL_18;
    }
    v9 = ObReferenceObjectByPointer(*((PVOID *)this + 4), 0, (POBJECT_TYPE)PsProcessType, 0);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_qd(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          WPP_be851031edc93d18f2bbe38844c4b0c7_Traceguids,
          *((_QWORD *)this + 4),
          v9);
      goto LABEL_18;
    }
    v5 = 8;
    *(_QWORD *)v10 = *((_QWORD *)this + 4);
    goto LABEL_17;
  }
  v8 = *((_QWORD *)this + 6);
  *(_QWORD *)&v12 = 0x800000010LL;
  if ( ((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         v8,
         &v12) )
  {
    return;
  }
  v9 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[127].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2);
  if ( v9 >= 0 )
    v9 = -1073741823;
LABEL_18:
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[132].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    (unsigned int)v9,
    v5);
}

```

## disassembly

```asm
0x140005520  mov     [rsp-18h+arg_10], rbx
0x140005525  mov     [rsp-18h+arg_18], rsi
0x14000552a  push    rbp
0x14000552b  push    rdi
0x14000552c  push    r14
0x14000552e  mov     rbp, rsp
0x140005531  sub     rsp, 60h
0x140005535  mov     rax, cs:__security_cookie
0x14000553c  xor     rax, rsp
0x14000553f  mov     [rbp+var_10], rax
0x140005543  mov     eax, [rbp+arg_20]
0x140005546  xor     r14d, r14d
0x140005549  xorps   xmm0, xmm0
0x14000554c  mov     rsi, rdx
0x14000554f  mov     rdi, rcx
0x140005552  movups  [rbp+var_20], xmm0
0x140005556  sub     eax, 224403h
0x14000555b  jz      loc_1400056B9
0x140005561  cmp     eax, 4
0x140005564  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000556b  jz      short loc_1400055CF
0x14000556d  mov     r8, [rcx+30h]
0x140005571  lea     r9, [rbp+var_20]
0x140005575  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000557c  mov     dword ptr [rbp+var_20], 10h
0x140005583  mov     dword ptr [rbp+var_20+4], 8
0x14000558a  mov     rax, [rax+7E8h]
0x140005591  call    _guard_dispatch_icall
0x140005596  test    al, al
0x140005598  jnz     loc_14000572B
0x14000559e  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400055a5  mov     rdx, rsi
0x1400055a8  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400055af  mov     rax, [rax+7F0h]
0x1400055b6  call    _guard_dispatch_icall
0x1400055bb  mov     ebx, eax
0x1400055bd  test    eax, eax
0x1400055bf  js      loc_140005708
0x1400055c5  mov     ebx, 0C0000001h
0x1400055ca  jmp     loc_140005708
0x1400055cf  lea     rcx, [rbp+var_28]
0x1400055d3  mov     [rbp+var_30], r14
0x1400055d7  mov     [rsp+60h+var_40], rcx
0x1400055dc  lea     r9, [rbp+var_30]
0x1400055e0  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400055e7  mov     r8d, 8
0x1400055ed  mov     [rbp+var_28], r14
0x1400055f1  mov     rax, [rax+870h]
0x1400055f8  call    _guard_dispatch_icall
0x1400055fd  mov     ebx, eax
0x1400055ff  test    eax, eax
0x140005601  jns     short loc_140005641
0x140005603  mov     rcx, cs:WPP_GLOBAL_Control
0x14000560a  lea     rax, WPP_GLOBAL_Control
0x140005611  cmp     rcx, rax
0x140005614  jz      loc_140005708
0x14000561a  cmp     byte ptr [rcx+29h], 2
0x14000561e  jb      loc_140005708
0x140005624  mov     rcx, [rcx+18h]
0x140005628  lea     r8, WPP_be851031edc93d18f2bbe38844c4b0c7_Traceguids
0x14000562f  mov     edx, 17h
0x140005634  mov     r9d, ebx
0x140005637  call    WPP_SF_d
0x14000563c  jmp     loc_140005708
0x140005641  mov     r8, cs:__imp_PsProcessType
0x140005648  xor     r9d, r9d; AccessMode
0x14000564b  mov     rcx, [rdi+20h]; Object
0x14000564f  xor     edx, edx; DesiredAccess
0x140005651  mov     r8, [r8]; ObjectType
0x140005654  call    cs:__imp_ObReferenceObjectByPointer
0x14000565b  nop     dword ptr [rax+rax+00h]
0x140005660  mov     ebx, eax
0x140005662  test    eax, eax
0x140005664  jns     short loc_1400056A6
0x140005666  mov     rcx, cs:WPP_GLOBAL_Control
0x14000566d  lea     rax, WPP_GLOBAL_Control
0x140005674  cmp     rcx, rax
0x140005677  jz      loc_140005708
0x14000567d  cmp     byte ptr [rcx+29h], 2
0x140005681  jb      loc_140005708
0x140005687  mov     r9, [rdi+20h]
0x14000568b  lea     r8, WPP_be851031edc93d18f2bbe38844c4b0c7_Traceguids
0x140005692  mov     rcx, [rcx+18h]
0x140005696  mov     edx, 18h
0x14000569b  mov     dword ptr [rsp+60h+var_40], ebx
0x14000569f  call    WPP_SF_qd
0x1400056a4  jmp     short loc_140005708
0x1400056a6  mov     rax, [rbp+var_30]
0x1400056aa  mov     r14d, 8
0x1400056b0  mov     rcx, [rdi+20h]
0x1400056b4  mov     [rax], rcx
0x1400056b7  jmp     short loc_140005706
0x1400056b9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400056c0  lea     rcx, [rbp+var_28]
0x1400056c4  mov     [rbp+var_30], r14
0x1400056c8  lea     r9, [rbp+var_30]
0x1400056cc  mov     [rbp+var_28], r14
0x1400056d0  mov     r8d, 10h
0x1400056d6  mov     [rsp+60h+var_40], rcx
0x1400056db  mov     rax, [rax+870h]
0x1400056e2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400056e9  call    _guard_dispatch_icall
0x1400056ee  mov     ebx, eax
0x1400056f0  test    eax, eax
0x1400056f2  js      short loc_140005708
0x1400056f4  mov     rax, [rbp+var_30]
0x1400056f8  mov     r14d, 10h
0x1400056fe  movups  xmm0, xmmword ptr [rdi+10h]
0x140005702  movdqu  xmmword ptr [rax], xmm0
0x140005706  xor     ebx, ebx
0x140005708  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000570f  mov     r9, r14
0x140005712  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140005719  mov     r8d, ebx
0x14000571c  mov     rdx, rsi
0x14000571f  mov     rax, [rax+848h]
0x140005726  call    _guard_dispatch_icall
0x14000572b  mov     rcx, [rbp+var_10]
0x14000572f  xor     rcx, rsp; StackCookie
0x140005732  call    __security_check_cookie
0x140005737  lea     r11, [rsp+60h+var_s0]
0x14000573c  mov     rbx, [r11+30h]
0x140005740  mov     rsi, [r11+38h]
0x140005744  mov     rsp, r11
0x140005747  pop     r14
0x140005749  pop     rdi
0x14000574a  pop     rbp
0x14000574b  retn
```
