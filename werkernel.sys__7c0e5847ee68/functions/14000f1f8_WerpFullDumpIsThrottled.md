# WerpFullDumpIsThrottled

- ea: `0x14000f1f8`
- end: `0x14000f3d8`
- name: `WerpFullDumpIsThrottled`
- size: `480`
- prototype: `char __fastcall(PCWSTR SourceString, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000d438`

## callees

- `0x14000d2a8`
- `0x14000efa4`
- `0x14000f144`
- `0x14000f1f8`
- `0x14000fba0`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000f292`
- `ntoskrnl!DbgPrintEx` at `0x14000f2be`
- `ntoskrnl!DbgPrintEx` at `0x14000f2e5`
- `ntoskrnl!DbgPrintEx` at `0x14000f292`
- `ntoskrnl!DbgPrintEx` at `0x14000f2be`
- `ntoskrnl!DbgPrintEx` at `0x14000f2e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f275`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f275`
- `ntoskrnl!_wcsicmp` at `0x14000f300`
- `ntoskrnl!_wcsicmp` at `0x14000f300`
- `ntoskrnl!MmIsVerifierEnabled` at `0x14000f319`
- `ntoskrnl!MmIsVerifierEnabled` at `0x14000f319`
- `ntoskrnl!MmGetPhysicalMemoryRanges` at `0x14000f22d`
- `ntoskrnl!MmGetPhysicalMemoryRanges` at `0x14000f22d`

## pseudocode

```c
char __fastcall WerpFullDumpIsThrottled(PCWSTR SourceString, _DWORD *a2)
{
  unsigned __int64 v4; // rsi
  signed __int64 v5; // rbx
  PPHYSICAL_MEMORY_RANGE PhysicalMemoryRanges; // rax
  PPHYSICAL_MEMORY_RANGE v7; // rcx
  unsigned int v8; // r8d
  __int64 v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rdx
  char v13; // [rsp+60h] [rbp+18h] BYREF
  ULONG VerifierFlags; // [rsp+68h] [rbp+20h] BYREF

  WerpRefreshThrottlePolicy();
  v4 = -1;
  v5 = MEMORY[0xFFFFF78000000014];
  if ( qword_1400093D0 != -1 )
  {
    PhysicalMemoryRanges = MmGetPhysicalMemoryRanges();
    v7 = PhysicalMemoryRanges;
    if ( PhysicalMemoryRanges )
    {
      v8 = 0;
      v9 = 0;
      if ( PhysicalMemoryRanges->NumberOfBytes.QuadPart )
      {
        do
        {
          v10 = v8++;
          v9 += (unsigned __int64)v7[v10].NumberOfBytes.QuadPart >> 12;
        }
        while ( v7[v8].NumberOfBytes.QuadPart );
      }
      v4 = v9 << 12;
      ExFreePoolWithTag(v7, 0);
    }
    else
    {
      DbgPrintEx(5u, 1u, "WERKERNELHOST: Failed to get the number of pages. System Memory Policy will be disabled.\n");
    }
    if ( v4 > qword_1400093D0 )
    {
      DbgPrintEx(
        5u,
        1u,
        "WERKERNELHOST: System memory threshold is not met. Memory Threshold %I64u bytes, SystemMemory %I64u bytes\n",
        qword_1400093D0,
        v4);
      if ( a2 )
        *a2 = 16;
      return 1;
    }
    DbgPrintEx(
      5u,
      1u,
      "WERKERNELHOST: System memory threshold is met. Memory Threshold %I64u bytes, SystemMemory %I64u bytes\n",
      qword_1400093D0,
      v4);
  }
  v13 = 0;
  if ( !_wcsicmp(L"VerifierExt", SourceString) )
  {
    VerifierFlags = 0;
    if ( MmIsVerifierEnabled(&VerifierFlags) >= 0 && (VerifierFlags & 0x400000) != 0 )
    {
      if ( !WerpExceedsPerComponentThreshold(SourceString, v5, *((unsigned __int64 *)&xmmword_1400093B8 + 1), &v13) )
      {
        if ( v13 )
          goto LABEL_26;
        v11 = xmmword_1400093B8;
        goto LABEL_22;
      }
LABEL_18:
      if ( a2 )
        *a2 = (v13 != 0) + 17;
      return 1;
    }
  }
  if ( WerpExceedsPerComponentThreshold(SourceString, v5, *((unsigned __int64 *)&xmmword_1400093A8 + 1), &v13) )
    goto LABEL_18;
  if ( v13 )
    goto LABEL_26;
  v11 = xmmword_1400093A8;
LABEL_22:
  if ( (unsigned __int8)WerpExceedsSystemThreshold(v5, v11) )
  {
    if ( a2 )
      *a2 = 19;
    return 1;
  }
LABEL_26:
  if ( !WerpCheckDiskSpace() )
  {
    *a2 = 20;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14000f1f8  mov     [rsp+arg_0], rbx
0x14000f1fd  push    rbp
0x14000f1fe  push    rsi
0x14000f1ff  push    rdi
0x14000f200  sub     rsp, 30h
0x14000f204  mov     rdi, rdx
0x14000f207  mov     rbp, rcx
0x14000f20a  call    WerpRefreshThrottlePolicy
0x14000f20f  mov     rbx, 0FFFFF78000000014h
0x14000f219  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000f21d  mov     rbx, [rbx]
0x14000f220  cmp     cs:qword_1400093D0, rsi
0x14000f227  jz      loc_14000F2F1
0x14000f22d  call    cs:__imp_MmGetPhysicalMemoryRanges
0x14000f234  nop     dword ptr [rax+rax+00h]
0x14000f239  mov     rcx, rax; P
0x14000f23c  test    rax, rax
0x14000f23f  jz      short loc_14000F283
0x14000f241  xor     r8d, r8d
0x14000f244  xor     esi, esi
0x14000f246  cmp     [rax+8], rsi
0x14000f24a  jz      short loc_14000F26F
0x14000f24c  mov     eax, r8d
0x14000f24f  inc     r8d
0x14000f252  add     rax, rax
0x14000f255  mov     rdx, [rcx+rax*8+8]
0x14000f25a  shr     rdx, 0Ch
0x14000f25e  mov     eax, r8d
0x14000f261  add     rsi, rdx
0x14000f264  add     rax, rax
0x14000f267  cmp     qword ptr [rcx+rax*8+8], 0
0x14000f26d  jnz     short loc_14000F24C
0x14000f26f  shl     rsi, 0Ch
0x14000f273  xor     edx, edx; Tag
0x14000f275  call    cs:__imp_ExFreePoolWithTag
0x14000f27c  nop     dword ptr [rax+rax+00h]
0x14000f281  jmp     short loc_14000F29E
0x14000f283  mov     edx, 1; Level
0x14000f288  lea     r8, aWerkernelhostF_9; "WERKERNELHOST: Failed to get the number"...
0x14000f28f  lea     ecx, [rdx+4]; ComponentId
0x14000f292  call    cs:__imp_DbgPrintEx
0x14000f299  nop     dword ptr [rax+rax+00h]
0x14000f29e  mov     r9, cs:qword_1400093D0
0x14000f2a5  mov     edx, 1; Level
0x14000f2aa  mov     [rsp+48h+var_28], rsi
0x14000f2af  lea     ecx, [rdx+4]; ComponentId
0x14000f2b2  cmp     rsi, r9
0x14000f2b5  jbe     short loc_14000F2DE
0x14000f2b7  lea     r8, aWerkernelhostS_0; "WERKERNELHOST: System memory threshold "...
0x14000f2be  call    cs:__imp_DbgPrintEx
0x14000f2c5  nop     dword ptr [rax+rax+00h]
0x14000f2ca  test    rdi, rdi
0x14000f2cd  jz      loc_14000F3B3
0x14000f2d3  mov     dword ptr [rdi], 10h
0x14000f2d9  jmp     loc_14000F3B3
0x14000f2de  lea     r8, aWerkernelhostS_5; "WERKERNELHOST: System memory threshold "...
0x14000f2e5  call    cs:__imp_DbgPrintEx
0x14000f2ec  nop     dword ptr [rax+rax+00h]
0x14000f2f1  mov     rdx, rbp; Str2
0x14000f2f4  mov     [rsp+48h+arg_10], 0
0x14000f2f9  lea     rcx, aVerifierext; "VerifierExt"
0x14000f300  call    cs:__imp__wcsicmp
0x14000f307  nop     dword ptr [rax+rax+00h]
0x14000f30c  test    eax, eax
0x14000f30e  jnz     short loc_14000F35D
0x14000f310  lea     rcx, [rsp+48h+VerifierFlags]; VerifierFlags
0x14000f315  mov     [rsp+48h+VerifierFlags], eax
0x14000f319  call    cs:__imp_MmIsVerifierEnabled
0x14000f320  nop     dword ptr [rax+rax+00h]
0x14000f325  test    eax, eax
0x14000f327  js      short loc_14000F35D
0x14000f329  test    [rsp+48h+VerifierFlags], 400000h
0x14000f331  jz      short loc_14000F35D
0x14000f333  mov     r8, qword ptr cs:xmmword_1400093B8+8
0x14000f33a  lea     r9, [rsp+48h+arg_10]
0x14000f33f  mov     rdx, rbx
0x14000f342  mov     rcx, rbp; SourceString
0x14000f345  call    WerpExceedsPerComponentThreshold
0x14000f34a  test    al, al
0x14000f34c  jnz     short loc_14000F378
0x14000f34e  cmp     [rsp+48h+arg_10], al
0x14000f352  jnz     short loc_14000F3B7
0x14000f354  mov     rdx, qword ptr cs:xmmword_1400093B8
0x14000f35b  jmp     short loc_14000F39C
0x14000f35d  mov     r8, qword ptr cs:xmmword_1400093A8+8
0x14000f364  lea     r9, [rsp+48h+arg_10]
0x14000f369  mov     rdx, rbx
0x14000f36c  mov     rcx, rbp; SourceString
0x14000f36f  call    WerpExceedsPerComponentThreshold
0x14000f374  test    al, al
0x14000f376  jz      short loc_14000F38E
0x14000f378  test    rdi, rdi
0x14000f37b  jz      short loc_14000F3B3
0x14000f37d  mov     al, [rsp+48h+arg_10]
0x14000f381  neg     al
0x14000f383  sbb     ecx, ecx
0x14000f385  neg     ecx
0x14000f387  add     ecx, 11h
0x14000f38a  mov     [rdi], ecx
0x14000f38c  jmp     short loc_14000F3B3
0x14000f38e  cmp     [rsp+48h+arg_10], 0
0x14000f393  jnz     short loc_14000F3B7
0x14000f395  mov     rdx, qword ptr cs:xmmword_1400093A8
0x14000f39c  mov     rcx, rbx
0x14000f39f  call    WerpExceedsSystemThreshold
0x14000f3a4  test    al, al
0x14000f3a6  jz      short loc_14000F3B7
0x14000f3a8  test    rdi, rdi
0x14000f3ab  jz      short loc_14000F3B3
0x14000f3ad  mov     dword ptr [rdi], 13h
0x14000f3b3  mov     al, 1
0x14000f3b5  jmp     short loc_14000F3CA
0x14000f3b7  call    WerpCheckDiskSpace
0x14000f3bc  test    al, al
0x14000f3be  jnz     short loc_14000F3C8
0x14000f3c0  mov     dword ptr [rdi], 14h
0x14000f3c6  jmp     short loc_14000F3B3
0x14000f3c8  xor     al, al
0x14000f3ca  mov     rbx, [rsp+48h+arg_0]
0x14000f3cf  add     rsp, 30h
0x14000f3d3  pop     rdi
0x14000f3d4  pop     rsi
0x14000f3d5  pop     rbp
0x14000f3d6  retn
```
