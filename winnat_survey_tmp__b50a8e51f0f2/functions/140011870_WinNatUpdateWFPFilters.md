# WinNatUpdateWFPFilters

- ea: `0x140011870`
- end: `0x140011972`
- name: `WinNatUpdateWFPFilters`
- size: `258`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000f830`
- `0x140011300`
- `0x1400113c0`

## callees

- `0x14000e488`
- `0x14000e980`
- `0x14000eb50`
- `0x140011870`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140011922`
- `ntoskrnl!KeGetCurrentIrql` at `0x140011922`
- `ntoskrnl!ExAllocatePool2` at `0x1400118ab`
- `ntoskrnl!ExAllocatePool2` at `0x1400118ab`
- `NETIO!NetioInsertWorkQueue` at `0x14001193c`
- `NETIO!NetioInsertWorkQueue` at `0x14001193c`

## pseudocode

```c
__int64 __fastcall WinNatUpdateWFPFilters(__int64 a1, char a2)
{
  __int64 v5; // rdx
  _QWORD *Pool2; // rbx
  __int64 v7; // r8
  __int64 (__fastcall *v8)(_QWORD *); // rax

  if ( a2 && !*(_BYTE *)(*(_QWORD *)(a1 + 80) + 866LL) )
    return 0;
  Pool2 = (_QWORD *)ExAllocatePool2(64, 24, 1769426519);
  if ( Pool2 )
  {
    if ( _InterlockedIncrement64((volatile signed __int64 *)a1) <= 1 )
      __fastfail(0xEu);
    Pool2[2] = a1;
    v8 = WinNatAddWFPFiltersAtPassive;
    if ( !a2 )
      v8 = WinNARemoveWFPFiltersAtPassive;
    Pool2[1] = v8;
    if ( KeGetCurrentIrql() >= 2u )
    {
      NetioInsertWorkQueue(qword_140026B18, Pool2);
      return 0;
    }
    if ( a2 )
      return WinNatAddWFPFiltersAtPassive(Pool2);
    else
      return WinNARemoveWFPFiltersAtPassive(Pool2);
  }
  else
  {
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        v5,
        v7,
        L"WFP filter workitem allocation failed");
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140011870  mov     [rsp+arg_0], rbx
0x140011875  mov     [rsp+arg_8], rsi
0x14001187a  push    rdi
0x14001187b  sub     rsp, 20h
0x14001187f  mov     sil, dl
0x140011882  mov     rdi, rcx
0x140011885  test    dl, dl
0x140011887  jz      short loc_14001189D
0x140011889  mov     rax, [rcx+50h]
0x14001188d  cmp     byte ptr [rax+362h], 0
0x140011894  jnz     short loc_14001189D
0x140011896  xor     eax, eax
0x140011898  jmp     loc_140011961
0x14001189d  mov     edx, 18h
0x1400118a2  mov     r8d, 69774E57h
0x1400118a8  lea     ecx, [rdx+28h]
0x1400118ab  call    cs:__imp_ExAllocatePool2
0x1400118b2  nop     dword ptr [rax+rax+00h]
0x1400118b7  mov     rbx, rax
0x1400118ba  test    rax, rax
0x1400118bd  jnz     short loc_1400118EB
0x1400118bf  cmp     cs:dword_140026104, 1
0x1400118c6  jnz     short loc_1400118E4
0x1400118c8  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x1400118cf  jz      short loc_1400118E4
0x1400118d1  lea     r9, aWfpFilterWorki; "WFP filter workitem allocation failed"
0x1400118d8  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400118df  call    McTemplateK0z_EtwWriteTransfer
0x1400118e4  mov     eax, 0C000009Ah
0x1400118e9  jmp     short loc_140011961
0x1400118eb  mov     eax, 1
0x1400118f0  lock xadd [rdi], rax
0x1400118f5  inc     rax
0x1400118f8  cmp     rax, 1
0x1400118fc  jg      short loc_140011905
0x1400118fe  mov     ecx, 0Eh
0x140011903  int     29h; Win8: RtlFailFast(ecx)
0x140011905  lea     rcx, WinNARemoveWFPFiltersAtPassive
0x14001190c  mov     [rbx+10h], rdi
0x140011910  test    sil, sil
0x140011913  lea     rax, WinNatAddWFPFiltersAtPassive
0x14001191a  cmovz   rax, rcx
0x14001191e  mov     [rbx+8], rax
0x140011922  call    cs:__imp_KeGetCurrentIrql
0x140011929  nop     dword ptr [rax+rax+00h]
0x14001192e  cmp     al, 2
0x140011930  jb      short loc_14001194D
0x140011932  mov     rdx, rbx
0x140011935  lea     rcx, qword_140026B18
0x14001193c  call    cs:__imp_NetioInsertWorkQueue
0x140011943  nop     dword ptr [rax+rax+00h]
0x140011948  jmp     loc_140011896
0x14001194d  mov     rcx, rbx; P
0x140011950  test    sil, sil
0x140011953  jz      short loc_14001195C
0x140011955  call    WinNatAddWFPFiltersAtPassive
0x14001195a  jmp     short loc_140011961
0x14001195c  call    WinNARemoveWFPFiltersAtPassive
0x140011961  mov     rbx, [rsp+28h+arg_0]
0x140011966  mov     rsi, [rsp+28h+arg_8]
0x14001196b  add     rsp, 20h
0x14001196f  pop     rdi
0x140011970  retn
```
