# CGenericUSB::IoCtlUsbdiQueryBusTime(WDFREQUEST__ *)

- ea: `0x1400037d0`
- end: `0x14000392e`
- name: `?IoCtlUsbdiQueryBusTime@CGenericUSB@@AEAAXPEAUWDFREQUEST__@@@Z`
- size: `350`
- prototype: `void __fastcall(CGenericUSB *__hidden this, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140003c10`

## callees

- `0x140001ac0`
- `0x1400037d0`
- `0x140003934`
- `0x140006370`

## pseudocode

```c
void __fastcall CGenericUSB::IoCtlUsbdiQueryBusTime(CGenericUSB *this, struct WDFREQUEST__ *a2)
{
  int v4; // edi
  _DWORD *v5; // [rsp+30h] [rbp-28h] BYREF
  int v6; // [rsp+70h] [rbp+18h] BYREF
  __int64 v7; // [rsp+78h] [rbp+20h] BYREF

  v5 = 0;
  v7 = 0;
  v6 = 0;
  v4 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, _DWORD **, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         4,
         &v5,
         &v7);
  if ( v4 >= 0 )
  {
    if ( v7 == 4 )
    {
      if ( *((_WORD *)this + 45) <= 2u )
      {
        (*((void (__fastcall **)(_QWORD, int *))this + 16))(*((_QWORD *)this + 12), &v6);
        *v5 = v6;
        ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[132].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a2,
          0,
          4);
        return;
      }
      v4 = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, &WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids);
    }
    else
    {
      v4 = -1073741811;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x22u,
      (__int64)&WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
      v4);
  }
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    (unsigned int)v4);
}

```

## disassembly

```asm
0x1400037d0  mov     r11, rsp
0x1400037d3  mov     [r11+8], rbx
0x1400037d7  push    rbp
0x1400037d8  push    rsi
0x1400037d9  push    rdi
0x1400037da  sub     rsp, 40h
0x1400037de  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400037e5  lea     r9, [r11-28h]
0x1400037e9  xor     ebp, ebp
0x1400037eb  mov     rbx, rcx
0x1400037ee  lea     rcx, [r11+20h]
0x1400037f2  mov     [r11-28h], rbp
0x1400037f6  mov     [r11+20h], rbp
0x1400037fa  mov     rsi, rdx
0x1400037fd  mov     [rsp+58h+arg_10], ebp
0x140003801  mov     rax, [rax+870h]
0x140003808  lea     r8d, [rbp+4]
0x14000380c  mov     [r11-38h], rcx
0x140003810  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003817  call    _guard_dispatch_icall
0x14000381c  mov     edi, eax
0x14000381e  test    eax, eax
0x140003820  jns     short loc_14000385E
0x140003822  mov     rcx, cs:WPP_GLOBAL_Control
0x140003829  lea     rax, WPP_GLOBAL_Control
0x140003830  cmp     rcx, rax
0x140003833  jz      loc_140003900
0x140003839  cmp     byte ptr [rcx+29h], 2
0x14000383d  jb      loc_140003900
0x140003843  mov     rcx, [rcx+18h]
0x140003847  lea     edx, [rbp+22h]
0x14000384a  mov     r9d, edi
0x14000384d  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140003854  call    WPP_SF_d
0x140003859  jmp     loc_140003900
0x14000385e  cmp     [rsp+58h+arg_18], 4
0x140003864  jz      short loc_140003870
0x140003866  mov     edi, 0C000000Dh
0x14000386b  jmp     loc_140003900
0x140003870  movzx   eax, word ptr [rbx+5Ah]
0x140003874  cmp     ax, 2
0x140003878  jz      short loc_140003885
0x14000387a  cmp     ax, 1
0x14000387e  jz      short loc_140003885
0x140003880  test    ax, ax
0x140003883  jnz     short loc_1400038CD
0x140003885  mov     rcx, [rbx+60h]
0x140003889  lea     rdx, [rsp+58h+arg_10]
0x14000388e  mov     rax, [rbx+80h]
0x140003895  call    _guard_dispatch_icall
0x14000389a  mov     rcx, [rsp+58h+var_28]
0x14000389f  mov     r9d, 4
0x1400038a5  mov     eax, [rsp+58h+arg_10]
0x1400038a9  xor     r8d, r8d
0x1400038ac  mov     rdx, rsi
0x1400038af  mov     [rcx], eax
0x1400038b1  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400038b8  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400038bf  mov     rax, [rax+848h]
0x1400038c6  call    _guard_dispatch_icall
0x1400038cb  jmp     short loc_140003920
0x1400038cd  mov     edi, 0C0000001h
0x1400038d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400038d9  lea     rax, WPP_GLOBAL_Control
0x1400038e0  cmp     rcx, rax
0x1400038e3  jz      short loc_140003900
0x1400038e5  cmp     byte ptr [rcx+29h], 2
0x1400038e9  jb      short loc_140003900
0x1400038eb  mov     rcx, [rcx+18h]
0x1400038ef  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x1400038f6  mov     edx, 23h ; '#'
0x1400038fb  call    WPP_SF_
0x140003900  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003907  mov     r8d, edi
0x14000390a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003911  mov     rdx, rsi
0x140003914  mov     rax, [rax+838h]
0x14000391b  call    _guard_dispatch_icall
0x140003920  mov     rbx, [rsp+58h+arg_0]
0x140003925  add     rsp, 40h
0x140003929  pop     rdi
0x14000392a  pop     rsi
0x14000392b  pop     rbp
0x14000392c  retn
```
