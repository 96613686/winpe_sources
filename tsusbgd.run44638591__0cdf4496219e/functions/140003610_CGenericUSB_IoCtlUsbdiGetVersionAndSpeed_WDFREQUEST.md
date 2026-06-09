# CGenericUSB::IoCtlUsbdiGetVersionAndSpeed(WDFREQUEST__ *)

- ea: `0x140003610`
- end: `0x1400037c9`
- name: `?IoCtlUsbdiGetVersionAndSpeed@CGenericUSB@@AEAAXPEAUWDFREQUEST__@@@Z`
- size: `441`
- prototype: `void __fastcall(CGenericUSB *__hidden this, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140003c10`

## callees

- `0x140001ac0`
- `0x140003610`
- `0x140003934`
- `0x140006370`

## pseudocode

```c
void __fastcall CGenericUSB::IoCtlUsbdiGetVersionAndSpeed(CGenericUSB *this, struct WDFREQUEST__ *a2)
{
  int v4; // edi
  __int16 v5; // ax
  char v6; // dl
  __int64 v7; // [rsp+30h] [rbp-10h] BYREF
  __int64 v8; // [rsp+38h] [rbp-8h] BYREF
  int v9; // [rsp+70h] [rbp+30h] BYREF
  __int64 v10; // [rsp+78h] [rbp+38h] BYREF

  v8 = 0;
  v7 = 0;
  v10 = 0;
  v9 = 0;
  v4 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, __int64 *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         20,
         &v7,
         &v8);
  if ( v4 >= 0 )
  {
    if ( v8 == 20 )
    {
      v5 = *((_WORD *)this + 45);
      if ( v5 == 2 || v5 == 1 )
      {
        (*((void (__fastcall **)(_QWORD, __int64 *, int *))this + 15))(*((_QWORD *)this + 12), &v10, &v9);
        v6 = (*((__int64 (__fastcall **)(_QWORD))this + 19))(*((_QWORD *)this + 12));
      }
      else
      {
        if ( v5 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids);
          v4 = -1073741823;
          goto LABEL_17;
        }
        (*((void (__fastcall **)(_QWORD, __int64 *, int *))this + 15))(*((_QWORD *)this + 12), &v10, &v9);
        v6 = 0;
      }
      *(_DWORD *)v7 = *((unsigned __int16 *)this + 45);
      *(_QWORD *)(v7 + 4) = v10;
      *(_DWORD *)(v7 + 12) = v9;
      *(_BYTE *)(v7 + 16) = v6;
      ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[132].Blink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        a2,
        0,
        20);
      return;
    }
    v4 = -1073741811;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x20u,
      (__int64)WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
      v4);
  }
LABEL_17:
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    (unsigned int)v4);
}

```

## disassembly

```asm
0x140003610  mov     [rsp-18h+arg_0], rbx
0x140003615  mov     [rsp-18h+arg_8], rsi
0x14000361a  push    rbp
0x14000361b  push    rdi
0x14000361c  push    r14
0x14000361e  mov     rbp, rsp
0x140003621  sub     rsp, 40h
0x140003625  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000362c  lea     r9, [rbp+var_10]
0x140003630  xor     r14d, r14d
0x140003633  mov     rbx, rcx
0x140003636  lea     rcx, [rbp+var_8]
0x14000363a  mov     [rbp+var_8], r14
0x14000363e  mov     [rbp+var_10], r14
0x140003642  mov     rsi, rdx
0x140003645  mov     [rbp+arg_18], r14
0x140003649  mov     [rbp+arg_10], r14d
0x14000364d  lea     r8d, [r14+14h]
0x140003651  mov     rax, [rax+870h]
0x140003658  mov     [rsp+40h+var_20], rcx
0x14000365d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003664  call    _guard_dispatch_icall
0x140003669  mov     edi, eax
0x14000366b  test    eax, eax
0x14000366d  jns     short loc_1400036AC
0x14000366f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003676  lea     rax, WPP_GLOBAL_Control
0x14000367d  cmp     rcx, rax
0x140003680  jz      loc_140003795
0x140003686  cmp     byte ptr [rcx+29h], 2
0x14000368a  jb      loc_140003795
0x140003690  mov     rcx, [rcx+18h]
0x140003694  lea     edx, [r14+20h]
0x140003698  mov     r9d, edi
0x14000369b  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x1400036a2  call    WPP_SF_d
0x1400036a7  jmp     loc_140003795
0x1400036ac  cmp     [rbp+var_8], 14h
0x1400036b1  jz      short loc_1400036BD
0x1400036b3  mov     edi, 0C000000Dh
0x1400036b8  jmp     loc_140003795
0x1400036bd  movzx   eax, word ptr [rbx+5Ah]
0x1400036c1  cmp     ax, 2
0x1400036c5  jnz     short loc_1400036F0
0x1400036c7  mov     rax, [rbx+78h]
0x1400036cb  lea     r8, [rbp+arg_10]
0x1400036cf  mov     rcx, [rbx+60h]
0x1400036d3  lea     rdx, [rbp+arg_18]
0x1400036d7  call    _guard_dispatch_icall
0x1400036dc  mov     rax, [rbx+98h]
0x1400036e3  mov     rcx, [rbx+60h]
0x1400036e7  call    _guard_dispatch_icall
0x1400036ec  mov     dl, al
0x1400036ee  jmp     short loc_140003713
0x1400036f0  cmp     ax, 1
0x1400036f4  jz      short loc_1400036C7
0x1400036f6  test    ax, ax
0x1400036f9  jnz     short loc_140003762
0x1400036fb  mov     rax, [rbx+78h]
0x1400036ff  lea     r8, [rbp+arg_10]
0x140003703  mov     rcx, [rbx+60h]
0x140003707  lea     rdx, [rbp+arg_18]
0x14000370b  call    _guard_dispatch_icall
0x140003710  mov     dl, r14b
0x140003713  mov     rax, [rbp+var_10]
0x140003717  mov     r9d, 14h
0x14000371d  movzx   ecx, word ptr [rbx+5Ah]
0x140003721  xor     r8d, r8d
0x140003724  mov     [rax], ecx
0x140003726  mov     rax, [rbp+arg_18]
0x14000372a  mov     rcx, [rbp+var_10]
0x14000372e  mov     [rcx+4], rax
0x140003732  mov     rcx, [rbp+var_10]
0x140003736  mov     eax, [rbp+arg_10]
0x140003739  mov     [rcx+0Ch], eax
0x14000373c  mov     rax, [rbp+var_10]
0x140003740  mov     [rax+10h], dl
0x140003743  mov     rdx, rsi
0x140003746  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000374d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003754  mov     rax, [rax+848h]
0x14000375b  call    _guard_dispatch_icall
0x140003760  jmp     short loc_1400037B5
0x140003762  mov     rcx, cs:WPP_GLOBAL_Control
0x140003769  lea     rax, WPP_GLOBAL_Control
0x140003770  cmp     rcx, rax
0x140003773  jz      short loc_140003790
0x140003775  cmp     byte ptr [rcx+29h], 2
0x140003779  jb      short loc_140003790
0x14000377b  mov     rcx, [rcx+18h]
0x14000377f  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140003786  mov     edx, 21h ; '!'
0x14000378b  call    WPP_SF_
0x140003790  mov     edi, 0C0000001h
0x140003795  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000379c  mov     r8d, edi
0x14000379f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400037a6  mov     rdx, rsi
0x1400037a9  mov     rax, [rax+838h]
0x1400037b0  call    _guard_dispatch_icall
0x1400037b5  mov     rbx, [rsp+40h+arg_0]
0x1400037ba  mov     rsi, [rsp+40h+arg_8]
0x1400037bf  add     rsp, 40h
0x1400037c3  pop     r14
0x1400037c5  pop     rdi
0x1400037c6  pop     rbp
0x1400037c7  retn
```
