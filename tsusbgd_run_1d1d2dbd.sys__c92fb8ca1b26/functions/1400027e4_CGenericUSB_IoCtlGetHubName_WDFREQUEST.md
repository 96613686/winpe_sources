# CGenericUSB::IoCtlGetHubName(WDFREQUEST__ *)

- ea: `0x1400027e4`
- end: `0x14000296f`
- name: `?IoCtlGetHubName@CGenericUSB@@AEAAXPEAUWDFREQUEST__@@@Z`
- size: `395`
- prototype: `void __fastcall(CGenericUSB *__hidden this, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140003c10`

## callees

- `0x140001ac0`
- `0x1400027e4`
- `0x140006330`
- `0x140006370`
- `0x140006440`

## pseudocode

```c
void __fastcall CGenericUSB::IoCtlGetHubName(CGenericUSB *this, struct WDFREQUEST__ *a2)
{
  __int64 v4; // r8
  int v5; // ebx
  __int128 v6; // [rsp+30h] [rbp-39h] BYREF
  __int128 v7; // [rsp+40h] [rbp-29h] BYREF
  __int128 v8; // [rsp+50h] [rbp-19h]
  __int64 v9; // [rsp+60h] [rbp-9h]
  _DWORD v10[18]; // [rsp+68h] [rbp-1h] BYREF

  memset(v10, 0, sizeof(v10));
  v9 = 0;
  v7 = 0;
  LOWORD(v7) = 40;
  v6 = 0;
  v8 = 0;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[133].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    &v7);
  v10[4] = v8;
  v10[2] = DWORD2(v7);
  LOWORD(v10[0]) = 15;
  v10[6] = 2228256;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _DWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    v10);
  v4 = *((_QWORD *)this + 4);
  v6 = 0x800000010uLL;
  if ( !((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a2,
          v4,
          &v6) )
  {
    v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[127].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x1Du,
        (__int64)&WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
        v5);
    if ( v5 < 0 )
      ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        a2,
        (unsigned int)v5);
  }
}

```

## disassembly

```asm
0x1400027e4  mov     [rsp-8+arg_10], rbx
0x1400027e9  mov     [rsp-8+arg_18], rdi
0x1400027ee  push    rbp
0x1400027ef  lea     rbp, [rsp-57h]
0x1400027f4  sub     rsp, 0C0h
0x1400027fb  mov     rax, cs:__security_cookie
0x140002802  xor     rax, rsp
0x140002805  mov     [rbp+57h+var_10], rax
0x140002809  mov     rdi, rdx
0x14000280c  mov     rbx, rcx
0x14000280f  xor     edx, edx; Val
0x140002811  lea     rcx, [rbp+57h+var_58]; void *
0x140002815  lea     r8d, [rdx+48h]; Size
0x140002819  call    memset
0x14000281e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002825  lea     r8, [rbp+57h+var_80]
0x140002829  xor     eax, eax
0x14000282b  xorps   xmm1, xmm1
0x14000282e  mov     [rbp+57h+var_60], rax
0x140002832  xorps   xmm0, xmm0
0x140002835  movups  [rbp+57h+var_80], xmm1
0x140002839  mov     eax, 28h ; '('
0x14000283e  mov     rdx, rdi
0x140002841  mov     word ptr [rbp+57h+var_80], ax
0x140002845  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000284c  movups  [rbp+57h+var_90], xmm0
0x140002850  movups  [rbp+57h+var_70], xmm1
0x140002854  mov     rax, [rax+850h]
0x14000285b  call    _guard_dispatch_icall
0x140002860  mov     eax, dword ptr [rbp+57h+var_70]
0x140002863  lea     r8, [rbp+57h+var_58]
0x140002867  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000286e  mov     rdx, rdi
0x140002871  mov     [rbp+57h+var_48], eax
0x140002874  mov     eax, dword ptr [rbp+57h+var_80+8]
0x140002877  mov     [rbp+57h+var_50], eax
0x14000287a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002881  mov     [rbp+57h+var_58], 0Fh
0x140002887  mov     [rbp+57h+var_40], 220020h
0x14000288e  mov     rax, [rax+7E0h]
0x140002895  call    _guard_dispatch_icall
0x14000289a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400028a1  lea     r9, [rbp+57h+var_90]
0x1400028a5  mov     r8, [rbx+20h]
0x1400028a9  mov     rdx, rdi
0x1400028ac  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400028b3  mov     qword ptr [rbp+57h+var_90+8], 0
0x1400028bb  mov     dword ptr [rbp+57h+var_90], 10h
0x1400028c2  mov     dword ptr [rbp+57h+var_90+4], 8
0x1400028c9  mov     rax, [rax+7E8h]
0x1400028d0  call    _guard_dispatch_icall
0x1400028d5  test    al, al
0x1400028d7  jnz     short loc_14000294D
0x1400028d9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400028e0  mov     rdx, rdi
0x1400028e3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400028ea  mov     rax, [rax+7F0h]
0x1400028f1  call    _guard_dispatch_icall
0x1400028f6  mov     ebx, eax
0x1400028f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400028ff  lea     rax, WPP_GLOBAL_Control
0x140002906  cmp     rcx, rax
0x140002909  jz      short loc_140002929
0x14000290b  cmp     byte ptr [rcx+29h], 5
0x14000290f  jb      short loc_140002929
0x140002911  mov     rcx, [rcx+18h]
0x140002915  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x14000291c  mov     edx, 1Dh
0x140002921  mov     r9d, ebx
0x140002924  call    WPP_SF_d
0x140002929  test    ebx, ebx
0x14000292b  jns     short loc_14000294D
0x14000292d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002934  mov     r8d, ebx
0x140002937  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000293e  mov     rdx, rdi
0x140002941  mov     rax, [rax+838h]
0x140002948  call    _guard_dispatch_icall
0x14000294d  mov     rcx, [rbp+57h+var_10]
0x140002951  xor     rcx, rsp; StackCookie
0x140002954  call    __security_check_cookie
0x140002959  lea     r11, [rsp+0C0h+var_s0]
0x140002961  mov     rbx, [r11+20h]
0x140002965  mov     rdi, [r11+28h]
0x140002969  mov     rsp, r11
0x14000296c  pop     rbp
0x14000296d  retn
```
