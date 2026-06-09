# MpDeleteInstanceContext

- ea: `0x14006cb90`
- end: `0x14006ce32`
- name: `MpDeleteInstanceContext`
- size: `674`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000ae58`
- `0x14006cb90`
- `0x14006ce34`
- `0x140077580`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14006ccd7`
- `ntoskrnl!ExDeleteResourceLite` at `0x14006ccd7`
- `ntoskrnl!KeBugCheckEx` at `0x14006cd3a`
- `ntoskrnl!KeBugCheckEx` at `0x14006cd5d`
- `ntoskrnl!KeBugCheckEx` at `0x14006cdd0`
- `ntoskrnl!KeBugCheckEx` at `0x14006cd3a`
- `ntoskrnl!KeBugCheckEx` at `0x14006cd5d`
- `ntoskrnl!KeBugCheckEx` at `0x14006cdd0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006cc89`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006cc89`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006cc7d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006cc7d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006cc42`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006cc42`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006cc2d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006cc2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cd07`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ce0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ce21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cd07`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ce0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ce21`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14006ccb7`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14006ccb7`

## pseudocode

```c
void __fastcall MpDeleteInstanceContext(__int64 a1, unsigned __int16 a2)
{
  ULONG_PTR v3; // rdx
  ULONG_PTR v4; // rdx
  __int64 *v5; // rsi
  ULONG_PTR v6; // rbx
  __int64 *v7; // rcx
  __int64 **v8; // rax
  struct _FLT_GENERIC_WORKITEM *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx

  if ( a2 != 2 )
    KeBugCheckEx(0x108u, a2, 2u, 0, 0);
  v3 = *(_QWORD *)(a1 + 128);
  if ( v3 != a1 + 128 )
    KeBugCheckEx(0x108u, v3, *(_QWORD *)(a1 + 136), 0, 0);
  v4 = *(_QWORD *)(a1 + 392);
  if ( v4 != a1 + 392 )
    KeBugCheckEx(0x108u, v4, *(_QWORD *)(a1 + 400), 0, 0);
  if ( (*(_DWORD *)(a1 + 80) & 0x10) != 0 )
    _InterlockedDecrement((volatile signed __int32 *)(MpData + 4060));
  if ( dword_140026A00 == 1 )
    MpFreeFileStateGenericTable(a1, 27);
  if ( dword_140026A04 == 1 )
    MpFreeFileStateGenericTable(a1, 28);
  if ( dword_140026A08 == 1 )
    MpFreeFileStateGenericTable(a1, 2);
  v5 = (__int64 *)(a1 + 8);
  if ( (__int64 *)*v5 != v5 )
  {
    v6 = MpData;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v6 + 752), 1u);
    v7 = (__int64 *)*v5;
    if ( *(__int64 **)(*v5 + 8) != v5 || (v8 = *(__int64 ***)(a1 + 16), *v8 != v5) )
      __fastfail(3u);
    *v8 = v7;
    v7[1] = (__int64)v8;
    ExReleaseResourceLite((PERESOURCE)(MpData + 752));
    KeLeaveCriticalRegion();
  }
  if ( (*(_DWORD *)(a1 + 84) & 0x800) != 0 )
    _InterlockedDecrement((volatile signed __int32 *)MpDlpData + 9);
  v9 = *(struct _FLT_GENERIC_WORKITEM **)(a1 + 408);
  if ( v9 )
    FltFreeGenericWorkItem(v9);
  if ( *(_QWORD *)(a1 + 440) )
  {
    MpRemoveAllKnownBadEntries(a1);
    ExFreePoolWithTag(*(PVOID *)(a1 + 440), 0x6862504Du);
  }
  ExDeleteResourceLite((PERESOURCE)(a1 + 288));
  if ( *(_WORD *)(a1 + 24)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      42,
      (unsigned int)WPP_49dcc05efb723005c5388b24d04d6cac_Traceguids,
      (unsigned int)KeGetCurrentThread(),
      a1 + 24);
  }
  v10 = *(void **)(a1 + 48);
  if ( v10 )
    ExFreePoolWithTag(v10, 0x6E67504Du);
  v11 = *(void **)(a1 + 32);
  if ( v11 )
    ExFreePoolWithTag(v11, 0x6E76504Du);
}

```

## disassembly

```asm
0x14006cb90  mov     [rsp+arg_0], rbx
0x14006cb95  mov     [rsp+arg_8], rsi
0x14006cb9a  push    rdi
0x14006cb9b  sub     rsp, 30h
0x14006cb9f  mov     esi, 2
0x14006cba4  mov     rdi, rcx
0x14006cba7  cmp     dx, si
0x14006cbaa  jnz     loc_14006CDBB
0x14006cbb0  lea     rax, [rcx+80h]
0x14006cbb7  mov     rdx, [rax]; BugCheckParameter1
0x14006cbba  cmp     rdx, rax
0x14006cbbd  jnz     loc_14006CD24
0x14006cbc3  lea     rax, [rcx+188h]
0x14006cbca  mov     rdx, [rax]; BugCheckParameter1
0x14006cbcd  cmp     rdx, rax
0x14006cbd0  jnz     loc_14006CD47
0x14006cbd6  mov     eax, [rcx+50h]
0x14006cbd9  test    al, 10h
0x14006cbdb  jnz     loc_14006CDDD
0x14006cbe1  cmp     cs:dword_140026A00, 1
0x14006cbe8  jnz     short loc_14006CBF4
0x14006cbea  mov     edx, 1Bh
0x14006cbef  call    MpFreeFileStateGenericTable
0x14006cbf4  cmp     cs:dword_140026A04, 1
0x14006cbfb  jnz     short loc_14006CC0A
0x14006cbfd  mov     edx, 1Ch
0x14006cc02  mov     rcx, rdi
0x14006cc05  call    MpFreeFileStateGenericTable
0x14006cc0a  cmp     cs:dword_140026A08, 1
0x14006cc11  jnz     short loc_14006CC1D
0x14006cc13  mov     edx, esi
0x14006cc15  mov     rcx, rdi
0x14006cc18  call    MpFreeFileStateGenericTable
0x14006cc1d  lea     rsi, [rdi+8]
0x14006cc21  cmp     [rsi], rsi
0x14006cc24  jz      short loc_14006CC95
0x14006cc26  mov     rbx, cs:MpData
0x14006cc2d  call    cs:__imp_KeEnterCriticalRegion
0x14006cc34  nop     dword ptr [rax+rax+00h]
0x14006cc39  mov     dl, 1; Wait
0x14006cc3b  lea     rcx, [rbx+2F0h]; Resource
0x14006cc42  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14006cc49  nop     dword ptr [rax+rax+00h]
0x14006cc4e  mov     rcx, [rsi]
0x14006cc51  cmp     [rcx+8], rsi
0x14006cc55  jnz     loc_14006CDF0
0x14006cc5b  mov     rax, [rsi+8]
0x14006cc5f  cmp     [rax], rsi
0x14006cc62  jnz     loc_14006CDF0
0x14006cc68  mov     [rax], rcx
0x14006cc6b  mov     [rcx+8], rax
0x14006cc6f  mov     rcx, cs:MpData
0x14006cc76  add     rcx, 2F0h; Resource
0x14006cc7d  call    cs:__imp_ExReleaseResourceLite
0x14006cc84  nop     dword ptr [rax+rax+00h]
0x14006cc89  call    cs:__imp_KeLeaveCriticalRegion
0x14006cc90  nop     dword ptr [rax+rax+00h]
0x14006cc95  test    dword ptr [rdi+54h], 800h
0x14006cc9c  jz      short loc_14006CCA9
0x14006cc9e  mov     rax, cs:MpDlpData
0x14006cca5  lock dec dword ptr [rax+24h]
0x14006cca9  mov     rcx, [rdi+198h]; FltWorkItem
0x14006ccb0  xor     ebx, ebx
0x14006ccb2  test    rcx, rcx
0x14006ccb5  jz      short loc_14006CCC3
0x14006ccb7  call    cs:__imp_FltFreeGenericWorkItem
0x14006ccbe  nop     dword ptr [rax+rax+00h]
0x14006ccc3  cmp     [rdi+1B8h], rbx
0x14006ccca  jnz     loc_14006CDF7
0x14006ccd0  lea     rcx, [rdi+120h]; Resource
0x14006ccd7  call    cs:__imp_ExDeleteResourceLite
0x14006ccde  nop     dword ptr [rax+rax+00h]
0x14006cce3  lea     rcx, [rdi+18h]
0x14006cce7  cmp     [rcx], bx
0x14006ccea  jnz     short loc_14006CD6A
0x14006ccec  mov     rcx, [rdi+30h]; P
0x14006ccf0  test    rcx, rcx
0x14006ccf3  jnz     loc_14006CE1C
0x14006ccf9  mov     rcx, [rdi+20h]; P
0x14006ccfd  test    rcx, rcx
0x14006cd00  jz      short loc_14006CD13
0x14006cd02  mov     edx, 6E76504Dh; Tag
0x14006cd07  call    cs:__imp_ExFreePoolWithTag
0x14006cd0e  nop     dword ptr [rax+rax+00h]
0x14006cd13  mov     rbx, [rsp+38h+arg_0]
0x14006cd18  mov     rsi, [rsp+38h+arg_8]
0x14006cd1d  add     rsp, 30h
0x14006cd21  pop     rdi
0x14006cd22  retn
0x14006cd24  mov     r8, [rcx+88h]; BugCheckParameter2
0x14006cd2b  xor     ebx, ebx
0x14006cd2d  mov     ecx, 108h; BugCheckCode
0x14006cd32  mov     [rsp+38h+BugCheckParameter4], rbx; BugCheckParameter4
0x14006cd37  xor     r9d, r9d; BugCheckParameter3
0x14006cd3a  call    cs:__imp_KeBugCheckEx
0x14006cd47  mov     r8, [rcx+190h]; BugCheckParameter2
0x14006cd4e  xor     ebx, ebx
0x14006cd50  mov     ecx, 108h; BugCheckCode
0x14006cd55  mov     [rsp+38h+BugCheckParameter4], rbx; BugCheckParameter4
0x14006cd5a  xor     r9d, r9d; BugCheckParameter3
0x14006cd5d  call    cs:__imp_KeBugCheckEx
0x14006cd6a  mov     rax, cs:WPP_GLOBAL_Control
0x14006cd71  lea     rdx, WPP_GLOBAL_Control
0x14006cd78  cmp     rax, rdx
0x14006cd7b  jz      loc_14006CCEC
0x14006cd81  mov     eax, [rax+2Ch]
0x14006cd84  test    al, 4
0x14006cd86  jz      loc_14006CCEC
0x14006cd8c  mov     r9, gs:188h
0x14006cd95  lea     r8, WPP_49dcc05efb723005c5388b24d04d6cac_Traceguids
0x14006cd9c  mov     [rsp+38h+BugCheckParameter4], rcx
0x14006cda1  mov     edx, 2Ah ; '*'
0x14006cda6  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cdad  mov     rcx, [rcx+18h]
0x14006cdb1  call    WPP_SF_qZ
0x14006cdb6  jmp     loc_14006CCEC
0x14006cdbb  xor     ebx, ebx
0x14006cdbd  movzx   edx, dx; BugCheckParameter1
0x14006cdc0  xor     r9d, r9d; BugCheckParameter3
0x14006cdc3  mov     [rsp+38h+BugCheckParameter4], rbx; BugCheckParameter4
0x14006cdc8  mov     r8, rsi; BugCheckParameter2
0x14006cdcb  mov     ecx, 108h; BugCheckCode
0x14006cdd0  call    cs:__imp_KeBugCheckEx
0x14006cddd  mov     rax, cs:MpData
0x14006cde4  lock dec dword ptr [rax+0FDCh]
0x14006cdeb  jmp     loc_14006CBE1
0x14006cdf0  mov     ecx, 3
0x14006cdf5  int     29h; Win8: RtlFailFast(ecx)
0x14006cdf7  mov     rcx, rdi
0x14006cdfa  call    MpRemoveAllKnownBadEntries
0x14006cdff  mov     rcx, [rdi+1B8h]; P
0x14006ce06  mov     edx, 6862504Dh; Tag
0x14006ce0b  call    cs:__imp_ExFreePoolWithTag
0x14006ce12  nop     dword ptr [rax+rax+00h]
0x14006ce17  jmp     loc_14006CCD0
0x14006ce1c  mov     edx, 6E67504Dh; Tag
0x14006ce21  call    cs:__imp_ExFreePoolWithTag
0x14006ce28  nop     dword ptr [rax+rax+00h]
0x14006ce2d  jmp     loc_14006CCF9
```
