# PgmCloseConnection

- ea: `0x140005c0c`
- end: `0x140005e35`
- name: `PgmCloseConnection`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140007720`

## callees

- `0x1400052e4`
- `0x140005b30`
- `0x140005c0c`
- `0x14000948c`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140005cc9`
- `ntoskrnl!ExDeleteResourceLite` at `0x140005cc9`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140005d23`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140005d3a`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140005d6c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140005da6`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140005dc6`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140005d23`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140005d3a`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140005d6c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140005da6`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140005dc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ce4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005de4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005e05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005e16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ce4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005de4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005e05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005e16`

## pseudocode

```c
__int64 __fastcall PgmCloseConnection(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  void *v10; // rcx
  void *v11; // rcx

  v3 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids, v3);
  if ( *(_QWORD *)(v3 + 72) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids, v3);
    PgmCleanupSession(v3, 0, 0);
  }
  *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL) = 0;
  if ( *(_BYTE *)(v3 + 161) )
    DestroyFECContext(v3 + 112);
  v4 = *(_QWORD *)(v3 + 40);
  if ( v4 )
  {
    ExDeleteResourceLite((PERESOURCE)(v4 + 736));
    v5 = *(void **)(*(_QWORD *)(v3 + 40) + 24LL);
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
    v6 = *(void **)(*(_QWORD *)(v3 + 40) + 424LL);
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
    v7 = *(_QWORD *)(v3 + 40);
    if ( *(_QWORD *)(v7 + 304) )
    {
      ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v7 + 448));
      ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(v3 + 40) + 576LL));
    }
    v8 = *(void **)(v3 + 40);
LABEL_30:
    ExFreePoolWithTag(v8, 0);
    goto LABEL_31;
  }
  v9 = *(_QWORD *)(v3 + 48);
  if ( v9 )
  {
    if ( (*(_DWORD *)(v3 + 32) & 0x8000) != 0 )
      ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v9 + 320));
    v10 = *(void **)(v3 + 144);
    if ( v10 )
      ExFreePoolWithTag(v10, 0);
    if ( *(_BYTE *)(v3 + 160) )
    {
      ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(v3 + 48) + 448LL));
      if ( *(_BYTE *)(v3 + 161) )
        ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(v3 + 48) + 576LL));
    }
    v11 = *(void **)(*(_QWORD *)(v3 + 48) + 216LL);
    if ( v11 )
    {
      ExFreePoolWithTag(v11, 0);
      *(_QWORD *)(*(_QWORD *)(v3 + 48) + 216LL) = 0;
    }
    v8 = *(void **)(v3 + 48);
    goto LABEL_30;
  }
LABEL_31:
  ExFreePoolWithTag((PVOID)v3, 0);
  return 0;
}

```

## disassembly

```asm
0x140005c0c  mov     [rsp+arg_0], rbx
0x140005c11  mov     [rsp+arg_8], rbp
0x140005c16  push    rdi
0x140005c17  sub     rsp, 20h
0x140005c1b  mov     rax, [rdx+30h]
0x140005c1f  mov     rdi, rdx
0x140005c22  mov     rbx, [rax+18h]
0x140005c26  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c2d  lea     rbp, WPP_GLOBAL_Control
0x140005c34  cmp     rcx, rbp
0x140005c37  jz      short loc_140005C58
0x140005c39  mov     eax, [rcx+2Ch]
0x140005c3c  test    al, 10h
0x140005c3e  jz      short loc_140005C58
0x140005c40  mov     rcx, [rcx+18h]
0x140005c44  lea     r8, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids
0x140005c4b  mov     edx, 12h
0x140005c50  mov     r9, rbx
0x140005c53  call    WPP_SF_q
0x140005c58  cmp     qword ptr [rbx+48h], 0
0x140005c5d  jz      short loc_140005C97
0x140005c5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c66  cmp     rcx, rbp
0x140005c69  jz      short loc_140005C8A
0x140005c6b  mov     eax, [rcx+2Ch]
0x140005c6e  test    al, 4
0x140005c70  jz      short loc_140005C8A
0x140005c72  mov     rcx, [rcx+18h]
0x140005c76  lea     r8, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids
0x140005c7d  mov     edx, 13h
0x140005c82  mov     r9, rbx
0x140005c85  call    WPP_SF_q
0x140005c8a  xor     r8d, r8d
0x140005c8d  xor     edx, edx
0x140005c8f  mov     rcx, rbx
0x140005c92  call    PgmCleanupSession
0x140005c97  mov     rax, [rdi+30h]
0x140005c9b  mov     qword ptr [rax+18h], 0
0x140005ca3  cmp     byte ptr [rbx+0A1h], 0
0x140005caa  jz      short loc_140005CB5
0x140005cac  lea     rcx, [rbx+70h]
0x140005cb0  call    DestroyFECContext
0x140005cb5  mov     rcx, [rbx+28h]
0x140005cb9  test    rcx, rcx
0x140005cbc  jz      loc_140005D4F
0x140005cc2  add     rcx, 2E0h; Resource
0x140005cc9  call    cs:__imp_ExDeleteResourceLite
0x140005cd0  nop     dword ptr [rax+rax+00h]
0x140005cd5  mov     rax, [rbx+28h]
0x140005cd9  mov     rcx, [rax+18h]; P
0x140005cdd  test    rcx, rcx
0x140005ce0  jz      short loc_140005CF0
0x140005ce2  xor     edx, edx; Tag
0x140005ce4  call    cs:__imp_ExFreePoolWithTag
0x140005ceb  nop     dword ptr [rax+rax+00h]
0x140005cf0  mov     rax, [rbx+28h]
0x140005cf4  mov     rcx, [rax+1A8h]; P
0x140005cfb  test    rcx, rcx
0x140005cfe  jz      short loc_140005D0E
0x140005d00  xor     edx, edx; Tag
0x140005d02  call    cs:__imp_ExFreePoolWithTag
0x140005d09  nop     dword ptr [rax+rax+00h]
0x140005d0e  mov     rcx, [rbx+28h]
0x140005d12  cmp     qword ptr [rcx+130h], 0
0x140005d1a  jz      short loc_140005D46
0x140005d1c  add     rcx, 1C0h; Lookaside
0x140005d23  call    cs:__imp_ExDeleteNPagedLookasideList
0x140005d2a  nop     dword ptr [rax+rax+00h]
0x140005d2f  mov     rcx, [rbx+28h]
0x140005d33  add     rcx, 240h; Lookaside
0x140005d3a  call    cs:__imp_ExDeleteNPagedLookasideList
0x140005d41  nop     dword ptr [rax+rax+00h]
0x140005d46  mov     rcx, [rbx+28h]
0x140005d4a  jmp     loc_140005E03
0x140005d4f  mov     rcx, [rbx+30h]
0x140005d53  test    rcx, rcx
0x140005d56  jz      loc_140005E11
0x140005d5c  test    dword ptr [rbx+20h], 8000h
0x140005d63  jz      short loc_140005D78
0x140005d65  add     rcx, 140h; Lookaside
0x140005d6c  call    cs:__imp_ExDeleteNPagedLookasideList
0x140005d73  nop     dword ptr [rax+rax+00h]
0x140005d78  mov     rcx, [rbx+90h]; P
0x140005d7f  test    rcx, rcx
0x140005d82  jz      short loc_140005D92
0x140005d84  xor     edx, edx; Tag
0x140005d86  call    cs:__imp_ExFreePoolWithTag
0x140005d8d  nop     dword ptr [rax+rax+00h]
0x140005d92  cmp     byte ptr [rbx+0A0h], 0
0x140005d99  jz      short loc_140005DD2
0x140005d9b  mov     rcx, [rbx+30h]
0x140005d9f  add     rcx, 1C0h; Lookaside
0x140005da6  call    cs:__imp_ExDeleteNPagedLookasideList
0x140005dad  nop     dword ptr [rax+rax+00h]
0x140005db2  cmp     byte ptr [rbx+0A1h], 0
0x140005db9  jz      short loc_140005DD2
0x140005dbb  mov     rcx, [rbx+30h]
0x140005dbf  add     rcx, 240h; Lookaside
0x140005dc6  call    cs:__imp_ExDeleteNPagedLookasideList
0x140005dcd  nop     dword ptr [rax+rax+00h]
0x140005dd2  mov     rax, [rbx+30h]
0x140005dd6  mov     rcx, [rax+0D8h]; P
0x140005ddd  test    rcx, rcx
0x140005de0  jz      short loc_140005DFF
0x140005de2  xor     edx, edx; Tag
0x140005de4  call    cs:__imp_ExFreePoolWithTag
0x140005deb  nop     dword ptr [rax+rax+00h]
0x140005df0  mov     rax, [rbx+30h]
0x140005df4  mov     qword ptr [rax+0D8h], 0
0x140005dff  mov     rcx, [rbx+30h]; P
0x140005e03  xor     edx, edx; Tag
0x140005e05  call    cs:__imp_ExFreePoolWithTag
0x140005e0c  nop     dword ptr [rax+rax+00h]
0x140005e11  xor     edx, edx; Tag
0x140005e13  mov     rcx, rbx; P
0x140005e16  call    cs:__imp_ExFreePoolWithTag
0x140005e1d  nop     dword ptr [rax+rax+00h]
0x140005e22  mov     rbx, [rsp+28h+arg_0]
0x140005e27  xor     eax, eax
0x140005e29  mov     rbp, [rsp+28h+arg_8]
0x140005e2e  add     rsp, 20h
0x140005e32  pop     rdi
0x140005e33  retn
```
