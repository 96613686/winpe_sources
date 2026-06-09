# WimFSFReleaseReadCompletionContext

- ea: `0x14000cfe0`
- end: `0x14000d150`
- name: `WimFSFReleaseReadCompletionContext`
- size: `368`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a9f0`
- `0x140010758`
- `0x14003cd40`

## callees

- `0x14000cfe0`
- `0x14000fb60`
- `0x140010654`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000d0f8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000d0f8`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000d136`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000d136`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000d05a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000d05a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d081`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d0a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d081`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d0a7`

## pseudocode

```c
__int64 __fastcall WimFSFReleaseReadCompletionContext(volatile signed __int32 *Entry)
{
  unsigned __int32 v2; // edi
  void *v3; // rdx
  void *v4; // rbp
  __int64 v5; // r14
  __int64 v6; // rsi
  void *v7; // rcx

  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_dq(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      WPP_b091599abfd73b8a76031cd442416986_Traceguids,
      *((unsigned int *)Entry + 4),
      Entry);
  v2 = _InterlockedDecrement(Entry + 4);
  if ( !v2 )
  {
    v3 = (void *)*((_QWORD *)Entry + 34);
    v4 = (void *)*((_QWORD *)Entry + 31);
    v5 = *((_QWORD *)Entry + 13);
    v6 = *((_QWORD *)Entry + 17);
    if ( v3 )
    {
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(*((_QWORD *)Entry + 6) + 512LL), v3);
      *((_QWORD *)Entry + 34) = 0;
    }
    else
    {
      v7 = (void *)*((_QWORD *)Entry + 35);
      if ( !v7 )
        goto LABEL_10;
      ExFreePoolWithTag(v7, 0);
    }
    *((_QWORD *)Entry + 35) = 0;
LABEL_10:
    if ( !v5 && v4 )
    {
      ExFreePoolWithTag(v4, 0);
      *((_QWORD *)Entry + 31) = 0;
    }
    if ( (Entry[3] & 1) != 0 )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_b091599abfd73b8a76031cd442416986_Traceguids);
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)Entry + 6) + 768LL), (PVOID)Entry);
    }
    if ( v6 )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_b091599abfd73b8a76031cd442416986_Traceguids);
      ExReleaseRundownProtection(*(PEX_RUNDOWN_REF *)(v6 + 96));
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14000cfe0  push    rbx
0x14000cfe2  push    rbp
0x14000cfe3  push    rsi
0x14000cfe4  push    rdi
0x14000cfe5  push    r14
0x14000cfe7  sub     rsp, 30h
0x14000cfeb  mov     rbx, rcx
0x14000cfee  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cff5  mov     eax, [rcx+2Ch]
0x14000cff8  test    al, 20h
0x14000cffa  jz      short loc_14000D020
0x14000cffc  cmp     byte ptr [rcx+29h], 5
0x14000d000  jb      short loc_14000D020
0x14000d002  mov     rcx, [rcx+18h]
0x14000d006  lea     r8, WPP_b091599abfd73b8a76031cd442416986_Traceguids
0x14000d00d  mov     r9d, [rbx+10h]
0x14000d011  mov     edx, 0Fh
0x14000d016  mov     [rsp+58h+var_38], rbx
0x14000d01b  call    WPP_SF_dq
0x14000d020  or      edi, 0FFFFFFFFh
0x14000d023  lock xadd [rbx+10h], edi
0x14000d028  sub     edi, 1
0x14000d02b  jnz     loc_14000D142
0x14000d031  mov     rdx, [rbx+110h]; Entry
0x14000d038  mov     rbp, [rbx+0F8h]
0x14000d03f  mov     r14, [rbx+68h]
0x14000d043  mov     rsi, [rbx+88h]
0x14000d04a  test    rdx, rdx
0x14000d04d  jz      short loc_14000D073
0x14000d04f  mov     rcx, [rbx+30h]
0x14000d053  add     rcx, 200h; Lookaside
0x14000d05a  call    cs:__imp_ExFreeToPagedLookasideList
0x14000d061  nop     dword ptr [rax+rax+00h]
0x14000d066  mov     qword ptr [rbx+110h], 0
0x14000d071  jmp     short loc_14000D08D
0x14000d073  mov     rcx, [rbx+118h]; P
0x14000d07a  test    rcx, rcx
0x14000d07d  jz      short loc_14000D098
0x14000d07f  xor     edx, edx; Tag
0x14000d081  call    cs:__imp_ExFreePoolWithTag
0x14000d088  nop     dword ptr [rax+rax+00h]
0x14000d08d  mov     qword ptr [rbx+118h], 0
0x14000d098  test    r14, r14
0x14000d09b  jnz     short loc_14000D0BA
0x14000d09d  test    rbp, rbp
0x14000d0a0  jz      short loc_14000D0BA
0x14000d0a2  xor     edx, edx; Tag
0x14000d0a4  mov     rcx, rbp; P
0x14000d0a7  call    cs:__imp_ExFreePoolWithTag
0x14000d0ae  nop     dword ptr [rax+rax+00h]
0x14000d0b3  mov     [rbx+0F8h], r14
0x14000d0ba  mov     eax, [rbx+0Ch]
0x14000d0bd  test    al, 1
0x14000d0bf  jz      short loc_14000D104
0x14000d0c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d0c8  mov     eax, [rcx+2Ch]
0x14000d0cb  test    al, 20h
0x14000d0cd  jz      short loc_14000D0EA
0x14000d0cf  cmp     byte ptr [rcx+29h], 5
0x14000d0d3  jb      short loc_14000D0EA
0x14000d0d5  mov     rcx, [rcx+18h]
0x14000d0d9  lea     r8, WPP_b091599abfd73b8a76031cd442416986_Traceguids
0x14000d0e0  mov     edx, 10h
0x14000d0e5  call    WPP_SF_
0x14000d0ea  mov     rcx, [rbx+30h]
0x14000d0ee  mov     rdx, rbx; Entry
0x14000d0f1  add     rcx, 300h; Lookaside
0x14000d0f8  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000d0ff  nop     dword ptr [rax+rax+00h]
0x14000d104  test    rsi, rsi
0x14000d107  jz      short loc_14000D142
0x14000d109  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d110  mov     eax, [rcx+2Ch]
0x14000d113  test    al, 20h
0x14000d115  jz      short loc_14000D132
0x14000d117  cmp     byte ptr [rcx+29h], 5
0x14000d11b  jb      short loc_14000D132
0x14000d11d  mov     rcx, [rcx+18h]
0x14000d121  lea     r8, WPP_b091599abfd73b8a76031cd442416986_Traceguids
0x14000d128  mov     edx, 11h
0x14000d12d  call    WPP_SF_
0x14000d132  mov     rcx, [rsi+60h]; RunRef
0x14000d136  call    cs:__imp_ExReleaseRundownProtection
0x14000d13d  nop     dword ptr [rax+rax+00h]
0x14000d142  mov     eax, edi
0x14000d144  add     rsp, 30h
0x14000d148  pop     r14
0x14000d14a  pop     rdi
0x14000d14b  pop     rsi
0x14000d14c  pop     rbp
0x14000d14d  pop     rbx
0x14000d14e  retn
```
