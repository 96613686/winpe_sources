# WinNatUpdateWFPFilters

- ea: `0x1400118d0`
- end: `0x1400119d2`
- name: `WinNatUpdateWFPFilters`
- size: `258`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000f888`
- `0x140011360`
- `0x140011420`

## callees

- `0x14000e4b0`
- `0x14000e9b0`
- `0x14000eb80`
- `0x1400118d0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140011982`
- `ntoskrnl!KeGetCurrentIrql` at `0x140011982`
- `ntoskrnl!ExAllocatePool2` at `0x14001190b`
- `ntoskrnl!ExAllocatePool2` at `0x14001190b`
- `NETIO!NetioInsertWorkQueue` at `0x14001199c`
- `NETIO!NetioInsertWorkQueue` at `0x14001199c`

## pseudocode

```c
__int64 __fastcall WinNatUpdateWFPFilters(__int64 a1, char a2)
{
  __int64 v5; // rdx
  _QWORD *Pool2; // rbx
  __int64 v7; // r8
  __int64 (__fastcall *v8)(PVOID); // rax

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
      v8 = (__int64 (__fastcall *)(PVOID))WinNARemoveWFPFiltersAtPassive;
    Pool2[1] = v8;
    if ( KeGetCurrentIrql() >= 2u )
    {
      NetioInsertWorkQueue(qword_140027B18, Pool2);
      return 0;
    }
    if ( a2 )
      return WinNatAddWFPFiltersAtPassive(Pool2);
    else
      return WinNARemoveWFPFiltersAtPassive(Pool2);
  }
  else
  {
    if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
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
0x1400118d0  mov     [rsp+arg_0], rbx
0x1400118d5  mov     [rsp+arg_8], rsi
0x1400118da  push    rdi
0x1400118db  sub     rsp, 20h
0x1400118df  mov     sil, dl
0x1400118e2  mov     rdi, rcx
0x1400118e5  test    dl, dl
0x1400118e7  jz      short loc_1400118FD
0x1400118e9  mov     rax, [rcx+50h]
0x1400118ed  cmp     byte ptr [rax+362h], 0
0x1400118f4  jnz     short loc_1400118FD
0x1400118f6  xor     eax, eax
0x1400118f8  jmp     loc_1400119C1
0x1400118fd  mov     edx, 18h
0x140011902  mov     r8d, 69774E57h
0x140011908  lea     ecx, [rdx+28h]
0x14001190b  call    cs:__imp_ExAllocatePool2
0x140011912  nop     dword ptr [rax+rax+00h]
0x140011917  mov     rbx, rax
0x14001191a  test    rax, rax
0x14001191d  jnz     short loc_14001194B
0x14001191f  cmp     cs:dword_140027104, 1
0x140011926  jnz     short loc_140011944
0x140011928  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x14001192f  jz      short loc_140011944
0x140011931  lea     r9, aWfpFilterWorki; "WFP filter workitem allocation failed"
0x140011938  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14001193f  call    McTemplateK0z_EtwWriteTransfer
0x140011944  mov     eax, 0C000009Ah
0x140011949  jmp     short loc_1400119C1
0x14001194b  mov     eax, 1
0x140011950  lock xadd [rdi], rax
0x140011955  inc     rax
0x140011958  cmp     rax, 1
0x14001195c  jg      short loc_140011965
0x14001195e  mov     ecx, 0Eh
0x140011963  int     29h; Win8: RtlFailFast(ecx)
0x140011965  lea     rcx, WinNARemoveWFPFiltersAtPassive
0x14001196c  mov     [rbx+10h], rdi
0x140011970  test    sil, sil
0x140011973  lea     rax, WinNatAddWFPFiltersAtPassive
0x14001197a  cmovz   rax, rcx
0x14001197e  mov     [rbx+8], rax
0x140011982  call    cs:__imp_KeGetCurrentIrql
0x140011989  nop     dword ptr [rax+rax+00h]
0x14001198e  cmp     al, 2
0x140011990  jb      short loc_1400119AD
0x140011992  mov     rdx, rbx
0x140011995  lea     rcx, qword_140027B18
0x14001199c  call    cs:__imp_NetioInsertWorkQueue
0x1400119a3  nop     dword ptr [rax+rax+00h]
0x1400119a8  jmp     loc_1400118F6
0x1400119ad  mov     rcx, rbx; P
0x1400119b0  test    sil, sil
0x1400119b3  jz      short loc_1400119BC
0x1400119b5  call    WinNatAddWFPFiltersAtPassive
0x1400119ba  jmp     short loc_1400119C1
0x1400119bc  call    WinNARemoveWFPFiltersAtPassive
0x1400119c1  mov     rbx, [rsp+28h+arg_0]
0x1400119c6  mov     rsi, [rsp+28h+arg_8]
0x1400119cb  add     rsp, 20h
0x1400119cf  pop     rdi
0x1400119d0  retn
```
