# CGenericUSB::EvtDeviceFileCreate(WDFREQUEST__ *,WDFFILEOBJECT__ *)

- ea: `0x140001308`
- end: `0x14000145e`
- name: `?EvtDeviceFileCreate@CGenericUSB@@QEAAXPEAUWDFREQUEST__@@PEAUWDFFILEOBJECT__@@@Z`
- size: `342`
- prototype: `void __fastcall(CGenericUSB *__hidden this, struct WDFREQUEST__ *, struct WDFFILEOBJECT__ *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c330`

## callees

- `0x140001308`
- `0x140001b04`
- `0x140006330`
- `0x140006370`
- `0x140006960`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x1400013ef`
- `ntoskrnl!RtlGUIDFromString` at `0x1400013ef`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000133f`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000133f`

## pseudocode

```c
void __fastcall CGenericUSB::EvtDeviceFileCreate(PEPROCESS *this, struct WDFREQUEST__ *a2, struct WDFFILEOBJECT__ *a3)
{
  PEPROCESS CurrentProcess; // rax
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // rax
  NTSTATUS v10; // eax
  UNICODE_STRING GuidString; // [rsp+20h] [rbp-38h] BYREF
  GUID Guid; // [rsp+30h] [rbp-28h] BYREF

  GuidString = 0;
  Guid = 0;
  CurrentProcess = IoGetCurrentProcess();
  if ( CurrentProcess != this[3] )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        2,
        v7,
        CurrentProcess,
        *(_QWORD *)&GuidString.Length,
        GuidString.Buffer,
        *(_QWORD *)&Guid.Data1,
        *(_QWORD *)Guid.Data4);
    goto LABEL_5;
  }
  v9 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFFILEOBJECT__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[68].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a3);
  if ( !v9 || *(_WORD *)v9 < 2u || **(_WORD **)(v9 + 8) != 92 )
  {
LABEL_5:
    v8 = 3221225485LL;
    goto LABEL_11;
  }
  GuidString.Length = *(_WORD *)v9 - 2;
  GuidString.MaximumLength = *(_WORD *)(v9 + 2) - 2;
  GuidString.Buffer = (PWSTR)(*(_QWORD *)(v9 + 8) + 2LL);
  v10 = RtlGUIDFromString(&GuidString, &Guid);
  v8 = (unsigned int)v10;
  if ( v10 >= 0 )
    v8 = memcmp(&Guid, this + 1, 0x10u) != 0 ? 0xC000000D : 0;
LABEL_11:
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    v8);
}

```

## disassembly

```asm
0x140001308  mov     [rsp+arg_0], rbx
0x14000130d  mov     [rsp+arg_18], rsi
0x140001312  push    rdi
0x140001313  sub     rsp, 50h
0x140001317  mov     rax, cs:__security_cookie
0x14000131e  xor     rax, rsp
0x140001321  mov     [rsp+58h+var_18], rax
0x140001326  xorps   xmm0, xmm0
0x140001329  xorps   xmm1, xmm1
0x14000132c  movups  xmmword ptr [rsp+58h+GuidString.Length], xmm0
0x140001331  mov     rdi, r8
0x140001334  mov     rsi, rdx
0x140001337  movups  xmmword ptr [rsp+58h+Guid.Data1], xmm1
0x14000133c  mov     rbx, rcx
0x14000133f  call    cs:__imp_IoGetCurrentProcess
0x140001346  nop     dword ptr [rax+rax+00h]
0x14000134b  cmp     rax, [rbx+18h]
0x14000134f  jz      short loc_140001385
0x140001351  mov     rcx, cs:WPP_GLOBAL_Control
0x140001358  lea     rdx, WPP_GLOBAL_Control
0x14000135f  cmp     rcx, rdx
0x140001362  jz      short loc_14000137A
0x140001364  mov     edx, 2
0x140001369  cmp     [rcx+29h], dl
0x14000136c  jb      short loc_14000137A
0x14000136e  mov     rcx, [rcx+18h]
0x140001372  mov     r9, rax
0x140001375  call    WPP_SF_q
0x14000137a  mov     r8d, 0C000000Dh
0x140001380  jmp     loc_140001423
0x140001385  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000138c  mov     rdx, rdi
0x14000138f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001396  mov     rax, [rax+448h]
0x14000139d  call    _guard_dispatch_icall
0x1400013a2  mov     rcx, rax
0x1400013a5  test    rax, rax
0x1400013a8  jz      short loc_14000137A
0x1400013aa  movzx   r8d, word ptr [rax]
0x1400013ae  mov     edx, 2
0x1400013b3  cmp     r8w, dx
0x1400013b7  jb      short loc_14000137A
0x1400013b9  mov     rax, [rax+8]
0x1400013bd  cmp     word ptr [rax], 5Ch ; '\'
0x1400013c1  jnz     short loc_14000137A
0x1400013c3  sub     r8w, dx
0x1400013c7  mov     [rsp+58h+GuidString.Length], r8w
0x1400013cd  movzx   eax, word ptr [rcx+2]
0x1400013d1  sub     ax, dx
0x1400013d4  mov     [rsp+58h+GuidString.MaximumLength], ax
0x1400013d9  mov     rax, [rcx+8]
0x1400013dd  lea     rcx, [rsp+58h+GuidString]; GuidString
0x1400013e2  add     rax, rdx
0x1400013e5  lea     rdx, [rsp+58h+Guid]; Guid
0x1400013ea  mov     [rsp+58h+GuidString.Buffer], rax
0x1400013ef  call    cs:__imp_RtlGUIDFromString
0x1400013f6  nop     dword ptr [rax+rax+00h]
0x1400013fb  mov     r8d, eax
0x1400013fe  test    eax, eax
0x140001400  js      short loc_140001423
0x140001402  lea     rdx, [rbx+8]; Buf2
0x140001406  mov     r8d, 10h; Size
0x14000140c  lea     rcx, [rsp+58h+Guid]; Buf1
0x140001411  call    memcmp
0x140001416  neg     eax
0x140001418  mov     r8d, 0C000000Dh
0x14000141e  sbb     ecx, ecx
0x140001420  and     r8d, ecx
0x140001423  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000142a  mov     rdx, rsi
0x14000142d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001434  mov     rax, [rax+838h]
0x14000143b  call    _guard_dispatch_icall
0x140001440  mov     rcx, [rsp+58h+var_18]
0x140001445  xor     rcx, rsp; StackCookie
0x140001448  call    __security_check_cookie
0x14000144d  mov     rbx, [rsp+58h+arg_0]
0x140001452  mov     rsi, [rsp+58h+arg_18]
0x140001457  add     rsp, 50h
0x14000145b  pop     rdi
0x14000145c  retn
```
