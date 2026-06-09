# PgmCreateConnection

- ea: `0x140036008`
- end: `0x140036194`
- name: `PgmCreateConnection`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400078e0`

## callees

- `0x140005068`
- `0x1400050ac`
- `0x1400054d0`
- `0x140036008`

## import_xrefs

- `ntoskrnl!ExInterlockedInsertTailList` at `0x140036161`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140036161`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400360f3`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400360f3`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400360dd`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400360dd`
- `ntoskrnl!ExAllocatePool2` at `0x14003607e`
- `ntoskrnl!ExAllocatePool2` at `0x14003607e`

## pseudocode

```c
__int64 __fastcall PgmCreateConnection(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *Pool2; // rax
  _QWORD *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9

  if ( *(_WORD *)(a4 + 6) >= 8u )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 424, 812476240);
    v8 = Pool2;
    if ( Pool2 )
    {
      Pool2[1] = Pool2;
      *Pool2 = Pool2;
      KeInitializeSpinLock(Pool2 + 45);
      ++*((_DWORD *)v8 + 5);
      *((_DWORD *)v8 + 4) = 810763603;
      v8[9] = PsGetCurrentProcess(v10, v9, v11, v12);
      v8[10] = *(_QWORD *)(*(unsigned __int8 *)(a4 + 5) + a4 + 9);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids,
          v8,
          *(_QWORD *)(*(unsigned __int8 *)(a4 + 5) + a4 + 9));
      ExInterlockedInsertTailList((PLIST_ENTRY)&WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc, (PLIST_ENTRY)v8, &SpinLock);
      *(_QWORD *)(*(_QWORD *)(a3 + 48) + 24LL) = v8;
      *(_QWORD *)(*(_QWORD *)(a3 + 48) + 32LL) = 2;
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids, 424);
      return 3221225626LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids,
        *(unsigned __int16 *)(a4 + 6),
        8);
    return 3221225991LL;
  }
}

```

## disassembly

```asm
0x140036008  mov     [rsp+arg_0], rbx
0x14003600d  mov     [rsp+arg_8], rsi
0x140036012  push    rdi
0x140036013  sub     rsp, 30h
0x140036017  movzx   edx, word ptr [r9+6]
0x14003601c  mov     rsi, r8
0x14003601f  mov     r8d, 8
0x140036025  mov     rdi, r9
0x140036028  cmp     dx, r8w
0x14003602c  jnb     short loc_14003606E
0x14003602e  mov     rcx, cs:WPP_GLOBAL_Control
0x140036035  lea     rax, WPP_GLOBAL_Control
0x14003603c  cmp     rcx, rax
0x14003603f  jz      short loc_140036064
0x140036041  mov     eax, [rcx+2Ch]
0x140036044  test    al, 2
0x140036046  jz      short loc_140036064
0x140036048  mov     rcx, [rcx+18h]
0x14003604c  mov     r9d, edx
0x14003604f  lea     edx, [r8+2]
0x140036053  mov     dword ptr [rsp+38h+var_18], r8d
0x140036058  lea     r8, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids
0x14003605f  call    WPP_SF_Dd
0x140036064  mov     eax, 0C0000207h
0x140036069  jmp     loc_140036183
0x14003606e  mov     edx, 1A8h
0x140036073  mov     ecx, 40h ; '@'
0x140036078  mov     r8d, 306D6750h
0x14003607e  call    cs:__imp_ExAllocatePool2
0x140036085  nop     dword ptr [rax+rax+00h]
0x14003608a  mov     rbx, rax
0x14003608d  test    rax, rax
0x140036090  jnz     short loc_1400360CF
0x140036092  mov     rcx, cs:WPP_GLOBAL_Control
0x140036099  lea     rax, WPP_GLOBAL_Control
0x1400360a0  cmp     rcx, rax
0x1400360a3  jz      short loc_1400360C5
0x1400360a5  mov     eax, [rcx+2Ch]
0x1400360a8  test    al, 2
0x1400360aa  jz      short loc_1400360C5
0x1400360ac  mov     rcx, [rcx+18h]
0x1400360b0  lea     edx, [rbx+0Bh]
0x1400360b3  mov     r9d, 1A8h
0x1400360b9  lea     r8, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids
0x1400360c0  call    WPP_SF_d
0x1400360c5  mov     eax, 0C000009Ah
0x1400360ca  jmp     loc_140036183
0x1400360cf  lea     rcx, [rax+168h]; SpinLock
0x1400360d6  mov     [rax+8], rbx
0x1400360da  mov     [rax], rbx
0x1400360dd  call    cs:__imp_KeInitializeSpinLock
0x1400360e4  nop     dword ptr [rax+rax+00h]
0x1400360e9  inc     dword ptr [rbx+14h]
0x1400360ec  mov     dword ptr [rbx+10h], 30534553h
0x1400360f3  call    cs:__imp_PsGetCurrentProcess
0x1400360fa  nop     dword ptr [rax+rax+00h]
0x1400360ff  mov     [rbx+48h], rax
0x140036103  movzx   eax, byte ptr [rdi+5]
0x140036107  mov     rcx, [rax+rdi+9]
0x14003610c  mov     [rbx+50h], rcx
0x140036110  mov     rcx, cs:WPP_GLOBAL_Control
0x140036117  lea     rax, WPP_GLOBAL_Control
0x14003611e  cmp     rcx, rax
0x140036121  jz      short loc_140036150
0x140036123  mov     eax, [rcx+2Ch]
0x140036126  test    al, 4
0x140036128  jz      short loc_140036150
0x14003612a  movzx   eax, byte ptr [rdi+5]
0x14003612e  lea     r8, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids
0x140036135  mov     rcx, [rcx+18h]
0x140036139  mov     edx, 0Ch
0x14003613e  mov     r9, rbx
0x140036141  mov     rax, [rax+rdi+9]
0x140036146  mov     [rsp+38h+var_18], rax
0x14003614b  call    WPP_SF_qq
0x140036150  lea     r8, SpinLock; Lock
0x140036157  mov     rdx, rbx; ListEntry
0x14003615a  lea     rcx, WPP_MAIN_CB.Queue+40h; ListHead
0x140036161  call    cs:__imp_ExInterlockedInsertTailList
0x140036168  nop     dword ptr [rax+rax+00h]
0x14003616d  mov     rax, [rsi+30h]
0x140036171  mov     [rax+18h], rbx
0x140036175  mov     rax, [rsi+30h]
0x140036179  mov     qword ptr [rax+20h], 2
0x140036181  xor     eax, eax
0x140036183  mov     rbx, [rsp+38h+arg_0]
0x140036188  mov     rsi, [rsp+38h+arg_8]
0x14003618d  add     rsp, 30h
0x140036191  pop     rdi
0x140036192  retn
```
