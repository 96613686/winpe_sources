# PFPreCreate

- ea: `0x140009f60`
- end: `0x14000a0c7`
- name: `PFPreCreate`
- size: `359`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation`

## callees

- `0x140003000`
- `0x140009f60`
- `0x14000b950`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000a098`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000a098`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140009fec`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140009fec`
- `FLTMGR!FltGetRequestorProcessId` at `0x140009f92`
- `FLTMGR!FltGetRequestorProcessId` at `0x140009f92`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x14000a082`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x14000a082`
- `FLTMGR!FltReleaseResource` at `0x140009fd0`
- `FLTMGR!FltReleaseResource` at `0x140009fd0`
- `FLTMGR!FltAddOpenReparseEntry` at `0x14000a043`
- `FLTMGR!FltAddOpenReparseEntry` at `0x14000a043`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000a05c`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000a05c`
- `FLTMGR!FltAcquireResourceShared` at `0x140009fa9`
- `FLTMGR!FltAcquireResourceShared` at `0x140009fa9`

## pseudocode

```c
__int64 __fastcall PFPreCreate(PFLT_CALLBACK_DATA Data, __int64 a2, _QWORD *a3)
{
  unsigned int v3; // ebp
  __int64 Entry; // rbx
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  NTSTATUS v10; // r14d
  ULONG RequestorProcessId; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0;
  if ( (Data->Iopb->Parameters.Create.Options & 0x200000) != 0 )
  {
    RequestorProcessId = FltGetRequestorProcessId(Data);
    FltAcquireResourceShared(&stru_1400061E0);
    Entry = PriGetEntry(MatchByProcessId, &RequestorProcessId);
    FltReleaseResource(&stru_1400061E0);
    if ( !Entry )
    {
      v8 = ExAllocateFromPagedLookasideList(&Lookaside);
      v9 = v8;
      if ( !v8 )
      {
        v10 = -1073741670;
LABEL_11:
        Data->IoStatus.Status = v10;
        return 4;
      }
      memset(v8, 0, 0x40u);
      v9[2] = v9 + 1;
      v9[1] = v9 + 1;
      *((_DWORD *)v9 + 6) = -2147483640;
      *((_DWORD *)v9 + 7) = -2147483522;
      *((_DWORD *)v9 + 12) = 48;
      v10 = FltAddOpenReparseEntry(*(_QWORD *)(a2 + 8), Data, v9 + 1);
      if ( v10 < 0 )
      {
        if ( *v9 && *(_QWORD *)*v9 != *v9 )
          FltRemoveOpenReparseEntry(*(_QWORD *)(a2 + 8), Data);
        ExFreeToPagedLookasideList(&Lookaside, v9);
        goto LABEL_11;
      }
      *v9 = v9 + 1;
      FltSetCallbackDataDirty(Data);
      *a3 = v9;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140009f60  mov     [rsp+arg_8], rbx
0x140009f65  mov     [rsp+arg_10], rbp
0x140009f6a  push    rsi
0x140009f6b  push    rdi
0x140009f6c  push    r12
0x140009f6e  push    r14
0x140009f70  push    r15
0x140009f72  sub     rsp, 20h
0x140009f76  mov     rax, [rcx+10h]
0x140009f7a  xor     ebp, ebp
0x140009f7c  mov     r12, r8
0x140009f7f  mov     r15, rdx
0x140009f82  mov     rdi, rcx
0x140009f85  test    dword ptr [rax+20h], 200000h
0x140009f8c  jz      loc_14000A0AD
0x140009f92  call    cs:__imp_FltGetRequestorProcessId
0x140009f99  nop     dword ptr [rax+rax+00h]
0x140009f9e  lea     rcx, stru_1400061E0; Resource
0x140009fa5  mov     [rsp+48h+arg_0], eax
0x140009fa9  call    cs:__imp_FltAcquireResourceShared
0x140009fb0  nop     dword ptr [rax+rax+00h]
0x140009fb5  lea     rdx, [rsp+48h+arg_0]
0x140009fba  lea     rcx, MatchByProcessId
0x140009fc1  call    PriGetEntry
0x140009fc6  lea     rcx, stru_1400061E0; Resource
0x140009fcd  mov     rbx, rax
0x140009fd0  call    cs:__imp_FltReleaseResource
0x140009fd7  nop     dword ptr [rax+rax+00h]
0x140009fdc  test    rbx, rbx
0x140009fdf  jnz     loc_14000A0AD
0x140009fe5  lea     rcx, Lookaside; Lookaside
0x140009fec  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140009ff3  nop     dword ptr [rax+rax+00h]
0x140009ff8  mov     rbx, rax
0x140009ffb  test    rax, rax
0x140009ffe  jnz     short loc_14000A00B
0x14000a000  mov     r14d, 0C000009Ah
0x14000a006  jmp     loc_14000A0A4
0x14000a00b  xor     edx, edx; Val
0x14000a00d  mov     rcx, rbx; void *
0x14000a010  lea     r8d, [rdx+40h]; Size
0x14000a014  call    memset
0x14000a019  lea     rsi, [rbx+8]
0x14000a01d  mov     rdx, rdi
0x14000a020  mov     [rsi+8], rsi
0x14000a024  mov     r8, rsi
0x14000a027  mov     [rsi], rsi
0x14000a02a  mov     dword ptr [rsi+10h], 80000008h
0x14000a031  mov     dword ptr [rsi+14h], 8000007Eh
0x14000a038  mov     dword ptr [rsi+28h], 30h ; '0'
0x14000a03f  mov     rcx, [r15+8]
0x14000a043  call    cs:__imp_FltAddOpenReparseEntry
0x14000a04a  nop     dword ptr [rax+rax+00h]
0x14000a04f  mov     r14d, eax
0x14000a052  test    eax, eax
0x14000a054  js      short loc_14000A06E
0x14000a056  mov     rcx, rdi; Data
0x14000a059  mov     [rbx], rsi
0x14000a05c  call    cs:__imp_FltSetCallbackDataDirty
0x14000a063  nop     dword ptr [rax+rax+00h]
0x14000a068  mov     [r12], rbx
0x14000a06c  jmp     short loc_14000A0AD
0x14000a06e  mov     r8, [rbx]
0x14000a071  test    r8, r8
0x14000a074  jz      short loc_14000A08E
0x14000a076  cmp     [r8], r8
0x14000a079  jz      short loc_14000A08E
0x14000a07b  mov     rcx, [r15+8]
0x14000a07f  mov     rdx, rdi
0x14000a082  call    cs:__imp_FltRemoveOpenReparseEntry
0x14000a089  nop     dword ptr [rax+rax+00h]
0x14000a08e  mov     rdx, rbx; Entry
0x14000a091  lea     rcx, Lookaside; Lookaside
0x14000a098  call    cs:__imp_ExFreeToPagedLookasideList
0x14000a09f  nop     dword ptr [rax+rax+00h]
0x14000a0a4  mov     [rdi+18h], r14d
0x14000a0a8  mov     ebp, 4
0x14000a0ad  mov     rbx, [rsp+48h+arg_8]
0x14000a0b2  mov     eax, ebp
0x14000a0b4  mov     rbp, [rsp+48h+arg_10]
0x14000a0b9  add     rsp, 20h
0x14000a0bd  pop     r15
0x14000a0bf  pop     r14
0x14000a0c1  pop     r12
0x14000a0c3  pop     rdi
0x14000a0c4  pop     rsi
0x14000a0c5  retn
```
