# SrvAdminDereferenceInstance

- ea: `0x1400054f0`
- end: `0x14000555e`
- name: `SrvAdminDereferenceInstance`
- size: `110`
- prototype: ``
- caller_count: `17`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000454c`
- `0x1400048a0`
- `0x140004bc0`
- `0x140005100`
- `0x140005190`
- `0x1400051f0`
- `0x140007160`
- `0x1400141ec`
- `0x140014284`
- `0x140022530`
- `0x140022ff0`
- `0x140023260`
- `0x140023370`
- `0x140024bb8`
- `0x1400251a0`
- `0x14004c350`
- `0x14004c430`

## callees

- `0x1400054f0`
- `0x140007360`
- `0x140016c84`
- `0x140029b40`
- `0x140029e84`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14002b0f3`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b106`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b119`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b0f3`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b106`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b119`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b191`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b191`

## pseudocode

```c
void __fastcall SrvAdminDereferenceInstance(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 24), 0xFFFFFFFF) == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids, a1);
    }
    if ( *(_BYTE *)(a1 + 520) )
    {
      ExDeleteResourceLite((PERESOURCE)(a1 + 96));
      ExDeleteResourceLite((PERESOURCE)(a1 + 200));
      ExDeleteResourceLite((PERESOURCE)(a1 + 304));
      *(_BYTE *)(a1 + 520) = 0;
    }
    v2 = *(void **)(a1 + 64);
    if ( v2 )
    {
      RfsTable64Cleanup(v2);
      *(_QWORD *)(a1 + 64) = 0;
    }
    v3 = *(void **)(a1 + 72);
    if ( v3 )
    {
      RfsTableCleanup(v3);
      *(_QWORD *)(a1 + 72) = 0;
    }
    v4 = *(void **)(a1 + 80);
    if ( v4 )
    {
      RfsTable64Cleanup(v4);
      *(_QWORD *)(a1 + 80) = 0;
    }
    v5 = *(void **)(a1 + 88);
    if ( v5 )
    {
      RfsTable64Cleanup(v5);
      *(_QWORD *)(a1 + 88) = 0;
    }
    SrvNetUpdateMemStatistics(*(unsigned int *)(a1 - 12), *(unsigned int *)(a1 - 16), 0);
    ExFreePoolWithTag((PVOID)(a1 - 16), 0);
  }
}

```

## disassembly

```asm
0x1400054f0  push    rbx
0x1400054f2  sub     rsp, 20h
0x1400054f6  mov     rbx, rcx
0x1400054f9  mov     eax, 0FFFFFFFFh
0x1400054fe  lock xadd [rcx+18h], eax
0x140005503  cmp     eax, 1
0x140005506  jz      short loc_14000550F
0x140005508  add     rsp, 20h
0x14000550c  pop     rbx
0x14000550d  retn
0x14000550f  mov     [rsp+28h+arg_0], rdi
0x140005514  mov     rcx, cs:WPP_GLOBAL_Control
0x14000551b  lea     rax, WPP_GLOBAL_Control
0x140005522  cmp     rcx, rax
0x140005525  jz      loc_14002B0E6
0x14000552b  mov     eax, [rcx+2Ch]
0x14000552e  test    al, 20h
0x140005530  jz      loc_14002B0E6
0x140005536  cmp     byte ptr [rcx+29h], 2
0x14000553a  jb      loc_14002B0E6
0x140005540  mov     rcx, [rcx+18h]
0x140005544  lea     r8, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids
0x14000554b  mov     edx, 0Ah
0x140005550  mov     r9, rbx
0x140005553  call    WPP_SF_q
0x140005558  nop
0x140005559  jmp     loc_14002B0E6
0x14002b0e6  cmp     byte ptr [rbx+208h], 0
0x14002b0ed  jz      short loc_14002B12C
0x14002b0ef  lea     rcx, [rbx+60h]; Resource
0x14002b0f3  call    cs:__imp_ExDeleteResourceLite
0x14002b0fa  nop     dword ptr [rax+rax+00h]
0x14002b0ff  lea     rcx, [rbx+0C8h]; Resource
0x14002b106  call    cs:__imp_ExDeleteResourceLite
0x14002b10d  nop     dword ptr [rax+rax+00h]
0x14002b112  lea     rcx, [rbx+130h]; Resource
0x14002b119  call    cs:__imp_ExDeleteResourceLite
0x14002b120  nop     dword ptr [rax+rax+00h]
0x14002b125  mov     byte ptr [rbx+208h], 0
0x14002b12c  mov     rcx, [rbx+40h]; P
0x14002b130  xor     edi, edi
0x14002b132  test    rcx, rcx
0x14002b135  jz      short loc_14002B140
0x14002b137  call    RfsTable64Cleanup
0x14002b13c  mov     [rbx+40h], rdi
0x14002b140  mov     rcx, [rbx+48h]; P
0x14002b144  test    rcx, rcx
0x14002b147  jz      short loc_14002B159
0x14002b149  lea     rdx, SrvAdminFreeShare
0x14002b150  call    RfsTableCleanup
0x14002b155  mov     [rbx+48h], rdi
0x14002b159  mov     rcx, [rbx+50h]; P
0x14002b15d  test    rcx, rcx
0x14002b160  jz      short loc_14002B16B
0x14002b162  call    RfsTable64Cleanup
0x14002b167  mov     [rbx+50h], rdi
0x14002b16b  mov     rcx, [rbx+58h]; P
0x14002b16f  test    rcx, rcx
0x14002b172  jz      short loc_14002B17D
0x14002b174  call    RfsTable64Cleanup
0x14002b179  mov     [rbx+58h], rdi
0x14002b17d  mov     ecx, [rbx-0Ch]
0x14002b180  xor     r8d, r8d
0x14002b183  mov     edx, [rbx-10h]
0x14002b186  call    SrvNetUpdateMemStatistics
0x14002b18b  xor     edx, edx; Tag
0x14002b18d  lea     rcx, [rbx-10h]; P
0x14002b191  call    cs:__imp_ExFreePoolWithTag
0x14002b198  nop     dword ptr [rax+rax+00h]
0x14002b19d  mov     rdi, [rsp+28h+arg_0]
0x14002b1a2  jmp     loc_140005508
```
