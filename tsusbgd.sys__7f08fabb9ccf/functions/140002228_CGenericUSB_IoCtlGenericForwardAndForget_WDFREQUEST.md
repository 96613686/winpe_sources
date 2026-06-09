# CGenericUSB::IoCtlGenericForwardAndForget(WDFREQUEST__ *)

- ea: `0x140002228`
- end: `0x140002311`
- name: `?IoCtlGenericForwardAndForget@CGenericUSB@@AEAAXPEAUWDFREQUEST__@@@Z`
- size: `233`
- prototype: `void __fastcall(CGenericUSB *__hidden this, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140003c10`

## callees

- `0x140001ac0`
- `0x140002228`
- `0x140006330`
- `0x140006370`

## pseudocode

```c
void __fastcall CGenericUSB::IoCtlGenericForwardAndForget(CGenericUSB *this, struct WDFREQUEST__ *a2)
{
  __int64 v2; // r8
  int v4; // ebx
  _DWORD v5[2]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v6; // [rsp+38h] [rbp-20h]

  v2 = *((_QWORD *)this + 4);
  v6 = 0;
  v5[0] = 16;
  v5[1] = 8;
  if ( !((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, _DWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a2,
          v2,
          v5) )
  {
    v4 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[127].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
        (unsigned int)v4);
    if ( v4 < 0 )
      ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        a2,
        (unsigned int)v4);
  }
}

```

## disassembly

```asm
0x140002228  mov     [rsp+arg_10], rbx
0x14000222d  push    rdi
0x14000222e  sub     rsp, 50h
0x140002232  mov     rax, cs:__security_cookie
0x140002239  xor     rax, rsp
0x14000223c  mov     [rsp+58h+var_18], rax
0x140002241  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002248  lea     r9, [rsp+58h+var_28]
0x14000224d  mov     r8, [rcx+20h]
0x140002251  mov     rdi, rdx
0x140002254  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000225b  mov     [rsp+58h+var_20], 0
0x140002264  mov     [rsp+58h+var_28], 10h
0x14000226c  mov     [rsp+58h+var_24], 8
0x140002274  mov     rax, [rax+7E8h]
0x14000227b  call    _guard_dispatch_icall
0x140002280  test    al, al
0x140002282  jnz     short loc_1400022F8
0x140002284  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000228b  mov     rdx, rdi
0x14000228e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002295  mov     rax, [rax+7F0h]
0x14000229c  call    _guard_dispatch_icall
0x1400022a1  mov     ebx, eax
0x1400022a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400022aa  lea     rax, WPP_GLOBAL_Control
0x1400022b1  cmp     rcx, rax
0x1400022b4  jz      short loc_1400022D4
0x1400022b6  cmp     byte ptr [rcx+29h], 5
0x1400022ba  jb      short loc_1400022D4
0x1400022bc  mov     rcx, [rcx+18h]
0x1400022c0  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x1400022c7  mov     edx, 14h
0x1400022cc  mov     r9d, ebx
0x1400022cf  call    WPP_SF_d
0x1400022d4  test    ebx, ebx
0x1400022d6  jns     short loc_1400022F8
0x1400022d8  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400022df  mov     r8d, ebx
0x1400022e2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400022e9  mov     rdx, rdi
0x1400022ec  mov     rax, [rax+838h]
0x1400022f3  call    _guard_dispatch_icall
0x1400022f8  mov     rcx, [rsp+58h+var_18]
0x1400022fd  xor     rcx, rsp; StackCookie
0x140002300  call    __security_check_cookie
0x140002305  mov     rbx, [rsp+58h+arg_10]
0x14000230a  add     rsp, 50h
0x14000230e  pop     rdi
0x14000230f  retn
```
