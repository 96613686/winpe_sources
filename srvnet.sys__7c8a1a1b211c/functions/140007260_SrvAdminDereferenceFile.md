# SrvAdminDereferenceFile

- ea: `0x140007260`
- end: `0x140007351`
- name: `SrvAdminDereferenceFile`
- size: `241`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14000454c`
- `0x1400048a0`
- `0x140022e38`
- `0x140022ff0`
- `0x1400269f0`
- `0x140027b80`
- `0x140027c50`
- `0x140027ce0`

## callees

- `0x140007260`
- `0x140007360`
- `0x140016c84`
- `0x140029b40`
- `0x140029e84`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14002b903`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b916`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b929`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b903`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b916`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b929`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140007334`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140007334`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400072cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b99f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400072cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b99f`

## pseudocode

```c
void __fastcall SrvAdminDereferenceFile(unsigned int *Entry)
{
  __int64 v2; // rdi
  unsigned int v3; // eax
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 2, 0xFFFFFFFF) == 1 )
  {
    v2 = *((_QWORD *)Entry + 16);
    if ( v2 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 24), 0xFFFFFFFF) == 1 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids, v2);
        }
        if ( *(_BYTE *)(v2 + 520) )
        {
          ExDeleteResourceLite((PERESOURCE)(v2 + 96));
          ExDeleteResourceLite((PERESOURCE)(v2 + 200));
          ExDeleteResourceLite((PERESOURCE)(v2 + 304));
          *(_BYTE *)(v2 + 520) = 0;
        }
        v4 = *(void **)(v2 + 64);
        if ( v4 )
        {
          RfsTable64Cleanup(v4);
          *(_QWORD *)(v2 + 64) = 0;
        }
        v5 = *(void **)(v2 + 72);
        if ( v5 )
        {
          RfsTableCleanup(v5);
          *(_QWORD *)(v2 + 72) = 0;
        }
        v6 = *(void **)(v2 + 80);
        if ( v6 )
        {
          RfsTable64Cleanup(v6);
          *(_QWORD *)(v2 + 80) = 0;
        }
        v7 = *(void **)(v2 + 88);
        if ( v7 )
        {
          RfsTable64Cleanup(v7);
          *(_QWORD *)(v2 + 88) = 0;
        }
        SrvNetUpdateMemStatistics(*(unsigned int *)(v2 - 12), *(unsigned int *)(v2 - 16), 0);
        ExFreePoolWithTag((PVOID)(v2 - 16), 0);
      }
      *((_QWORD *)Entry + 16) = 0;
    }
    v3 = Entry[15];
    if ( v3 == 2 )
    {
      ExFreeToPagedLookasideList(&SrvAdminPagedList256, Entry);
      SrvNetUpdateMemStatistics(256, 256, 0);
    }
    else if ( v3 == 1 )
    {
      SrvNetUpdateMemStatistics(*(Entry - 3), *(Entry - 4), 0);
      ExFreePoolWithTag(Entry - 4, 0);
    }
  }
}

```

## disassembly

```asm
0x140007260  push    rbx
0x140007262  sub     rsp, 20h
0x140007266  mov     rbx, rcx
0x140007269  mov     ecx, 0FFFFFFFFh
0x14000726e  mov     eax, ecx
0x140007270  lock xadd [rbx+8], eax
0x140007275  cmp     eax, 1
0x140007278  jnz     short loc_1400072D9
0x14000727a  mov     [rsp+28h+arg_8], rdi
0x14000727f  mov     rdi, [rbx+80h]
0x140007286  test    rdi, rdi
0x140007289  jz      short loc_1400072A7
0x14000728b  mov     [rsp+28h+arg_0], rsi
0x140007290  lock xadd [rdi+18h], ecx
0x140007295  xor     esi, esi
0x140007297  cmp     ecx, eax
0x140007299  jz      short loc_1400072E0
0x14000729b  mov     [rbx+80h], rsi
0x1400072a2  mov     rsi, [rsp+28h+arg_0]
0x1400072a7  mov     eax, [rbx+3Ch]
0x1400072aa  mov     rdi, [rsp+28h+arg_8]
0x1400072af  cmp     eax, 2
0x1400072b2  jz      short loc_14000732A
0x1400072b4  cmp     eax, 1
0x1400072b7  jnz     short loc_1400072D9
0x1400072b9  mov     ecx, [rbx-0Ch]
0x1400072bc  xor     r8d, r8d
0x1400072bf  mov     edx, [rbx-10h]
0x1400072c2  call    SrvNetUpdateMemStatistics
0x1400072c7  xor     edx, edx; Tag
0x1400072c9  lea     rcx, [rbx-10h]; P
0x1400072cd  call    cs:__imp_ExFreePoolWithTag
0x1400072d4  nop     dword ptr [rax+rax+00h]
0x1400072d9  add     rsp, 20h
0x1400072dd  pop     rbx
0x1400072de  retn
0x1400072e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400072e7  lea     rax, WPP_GLOBAL_Control
0x1400072ee  cmp     rcx, rax
0x1400072f1  jz      loc_14002B8F6
0x1400072f7  mov     eax, [rcx+2Ch]
0x1400072fa  test    al, 20h
0x1400072fc  jz      loc_14002B8F6
0x140007302  cmp     byte ptr [rcx+29h], 2
0x140007306  jb      loc_14002B8F6
0x14000730c  mov     rcx, [rcx+18h]
0x140007310  lea     r8, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids
0x140007317  mov     edx, 0Ah
0x14000731c  mov     r9, rdi
0x14000731f  call    WPP_SF_q
0x140007324  nop
0x140007325  jmp     loc_14002B8F6
0x14000732a  mov     rdx, rbx; Entry
0x14000732d  lea     rcx, SrvAdminPagedList256; Lookaside
0x140007334  call    cs:__imp_ExFreeToPagedLookasideList
0x14000733b  nop     dword ptr [rax+rax+00h]
0x140007340  mov     edx, 100h
0x140007345  xor     r8d, r8d
0x140007348  mov     ecx, edx
0x14000734a  call    SrvNetUpdateMemStatistics
0x14000734f  jmp     short loc_1400072D9
0x14002b8f6  cmp     [rdi+208h], sil
0x14002b8fd  jz      short loc_14002B93C
0x14002b8ff  lea     rcx, [rdi+60h]; Resource
0x14002b903  call    cs:__imp_ExDeleteResourceLite
0x14002b90a  nop     dword ptr [rax+rax+00h]
0x14002b90f  lea     rcx, [rdi+0C8h]; Resource
0x14002b916  call    cs:__imp_ExDeleteResourceLite
0x14002b91d  nop     dword ptr [rax+rax+00h]
0x14002b922  lea     rcx, [rdi+130h]; Resource
0x14002b929  call    cs:__imp_ExDeleteResourceLite
0x14002b930  nop     dword ptr [rax+rax+00h]
0x14002b935  mov     [rdi+208h], sil
0x14002b93c  mov     rcx, [rdi+40h]; P
0x14002b940  test    rcx, rcx
0x14002b943  jz      short loc_14002B94E
0x14002b945  call    RfsTable64Cleanup
0x14002b94a  mov     [rdi+40h], rsi
0x14002b94e  mov     rcx, [rdi+48h]; P
0x14002b952  test    rcx, rcx
0x14002b955  jz      short loc_14002B967
0x14002b957  lea     rdx, SrvAdminFreeShare
0x14002b95e  call    RfsTableCleanup
0x14002b963  mov     [rdi+48h], rsi
0x14002b967  mov     rcx, [rdi+50h]; P
0x14002b96b  test    rcx, rcx
0x14002b96e  jz      short loc_14002B979
0x14002b970  call    RfsTable64Cleanup
0x14002b975  mov     [rdi+50h], rsi
0x14002b979  mov     rcx, [rdi+58h]; P
0x14002b97d  test    rcx, rcx
0x14002b980  jz      short loc_14002B98B
0x14002b982  call    RfsTable64Cleanup
0x14002b987  mov     [rdi+58h], rsi
0x14002b98b  mov     ecx, [rdi-0Ch]
0x14002b98e  xor     r8d, r8d
0x14002b991  mov     edx, [rdi-10h]
0x14002b994  call    SrvNetUpdateMemStatistics
0x14002b999  xor     edx, edx; Tag
0x14002b99b  lea     rcx, [rdi-10h]; P
0x14002b99f  call    cs:__imp_ExFreePoolWithTag
0x14002b9a6  nop     dword ptr [rax+rax+00h]
0x14002b9ab  nop
0x14002b9ac  jmp     loc_14000729B
```
