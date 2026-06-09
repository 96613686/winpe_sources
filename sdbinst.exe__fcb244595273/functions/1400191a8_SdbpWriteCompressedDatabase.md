# SdbpWriteCompressedDatabase

- ea: `0x1400191a8`
- end: `0x140019408`
- name: `SdbpWriteCompressedDatabase`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14001576c`

## callees

- `0x14001008c`
- `0x1400191a8`
- `0x14002e420`
- `0x14002f010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1400192dc`
- `ntdll!RtlAllocateHeap` at `0x1400192dc`
- `ntdll!RtlFreeHeap` at `0x1400193b9`
- `ntdll!RtlFreeHeap` at `0x1400193b9`
- `ntdll!NtWriteFile` at `0x14001928d`
- `ntdll!NtWriteFile` at `0x140019374`
- `ntdll!NtWriteFile` at `0x14001928d`
- `ntdll!NtWriteFile` at `0x140019374`

## string_xrefs

- `0x1400192a8`: `SdbpWriteCompressedDatabase`
- `0x140019328`: `SdbpWriteCompressedDatabase`
- `0x14001938f`: `SdbpWriteCompressedDatabase`
- `0x1400193dd`: `SdbpWriteCompressedDatabase`
- `0x1400191f3`: `Compress callback was not set. Unable to compress SDB.`
- `0x140019297`: `Failed to write the zdb header [%x]`
- `0x14001937e`: `Failed to write the zdb [%x]`
- `0x14001931b`: `Compress callback failed to compress the sdb`

## pseudocode

```c
__int64 __fastcall SdbpWriteCompressedDatabase(__int64 *a1)
{
  unsigned int v1; // esi
  _QWORD *v3; // rdx
  __int64 v4; // rcx
  int v5; // r8d
  void *v6; // rcx
  NTSTATUS v7; // eax
  PVOID Heap; // rax
  void *v9; // rdi
  void *v10; // rcx
  NTSTATUS v11; // eax
  ULONG Length; // [rsp+50h] [rbp-9h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-1h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp+7h] BYREF
  __int128 Buffer; // [rsp+70h] [rbp+17h] BYREF
  int v17; // [rsp+80h] [rbp+27h]

  v1 = 0;
  Length = 0;
  ByteOffset.QuadPart = 0;
  v17 = 0;
  IoStatusBlock = 0;
  Buffer = 0;
  if ( g_CompressCallback )
  {
    v3 = (_QWORD *)a1[1];
    if ( v3 && (v4 = *a1) != 0 )
    {
      v5 = *((_DWORD *)a1 + 5);
      if ( (unsigned int)(v5 - 42) > 0xFFFFFD5 )
      {
        AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 343, "Input DB was either too large or too small.");
      }
      else
      {
        *(_QWORD *)&Buffer = *v3;
        HIDWORD(Buffer) = g_ExpectedAlgorithm;
        DWORD2(Buffer) = 1717724282;
        v17 = v5;
        if ( *(_DWORD *)(v4 + 72) )
          v6 = 0;
        else
          v6 = *(void **)(v4 + 8);
        v7 = NtWriteFile(v6, 0, 0, 0, &IoStatusBlock, &Buffer, 0x14u, &ByteOffset, 0);
        if ( v7 >= 0 )
        {
          ByteOffset.LowPart += 20;
          Length = *((_DWORD *)a1 + 5);
          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
          v9 = Heap;
          if ( Heap )
          {
            if ( (unsigned int)((__int64 (__fastcall *)(PVOID, ULONG *, __int64, _QWORD))g_CompressCallback)(
                                 Heap,
                                 &Length,
                                 a1[1],
                                 *((unsigned int *)a1 + 5)) )
            {
              if ( *(_DWORD *)(*a1 + 72) )
                v10 = 0;
              else
                v10 = *(void **)(*a1 + 8);
              v11 = NtWriteFile(v10, 0, 0, 0, &IoStatusBlock, v9, Length, &ByteOffset, 0);
              if ( v11 >= 0 )
                v1 = 1;
              else
                AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 405, "Failed to write the zdb [%x]", v11);
            }
            else
            {
              AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 386, "Compress callback failed to compress the sdb");
            }
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
          }
          else
          {
            AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 376, "Failed to allocate zdb buffer.");
          }
        }
        else
        {
          AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 367, "Failed to write the zdb header [%x]", v7);
        }
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 337, "Input DB was not in a valid state.");
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 330, "Compress callback was not set. Unable to compress SDB.");
  }
  return v1;
}

```

## disassembly

```asm
0x1400191a8  push    rbp
0x1400191aa  push    rbx
0x1400191ab  push    rsi
0x1400191ac  push    rdi
0x1400191ad  lea     rbp, [rsp-3Fh]
0x1400191b2  sub     rsp, 98h
0x1400191b9  mov     rax, cs:__security_cookie
0x1400191c0  xor     rax, rsp
0x1400191c3  mov     [rbp+57h+var_28], rax
0x1400191c7  xor     esi, esi
0x1400191c9  mov     [rbp+57h+var_60], 0
0x1400191d0  xor     eax, eax
0x1400191d2  mov     qword ptr [rbp+57h+var_58], rsi
0x1400191d6  cmp     cs:g_CompressCallback, rax
0x1400191dd  xorps   xmm0, xmm0
0x1400191e0  xorps   xmm1, xmm1
0x1400191e3  mov     [rbp+57h+var_30], eax
0x1400191e6  mov     rbx, rcx
0x1400191e9  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1400191ed  movups  [rbp+57h+var_40], xmm1
0x1400191f1  jnz     short loc_140019205
0x1400191f3  lea     r9, aCompressCallba; "Compress callback was not set. Unable t"...
0x1400191fa  mov     r8d, 14Ah
0x140019200  jmp     loc_1400193DD
0x140019205  mov     rdx, [rcx+8]
0x140019209  test    rdx, rdx
0x14001920c  jz      loc_1400193D0
0x140019212  mov     rcx, [rcx]
0x140019215  test    rcx, rcx
0x140019218  jz      loc_1400193D0
0x14001921e  mov     r8d, [rbx+14h]
0x140019222  lea     eax, [r8-2Ah]
0x140019226  cmp     eax, 0FFFFFD5h
0x14001922b  ja      loc_1400193C1
0x140019231  mov     eax, [rdx]
0x140019233  mov     dword ptr [rbp+57h+var_40], eax
0x140019236  mov     eax, [rdx+4]
0x140019239  mov     dword ptr [rbp+57h+var_40+4], eax
0x14001923c  mov     eax, cs:g_ExpectedAlgorithm
0x140019242  mov     dword ptr [rbp+57h+var_40+0Ch], eax
0x140019245  mov     dword ptr [rbp+57h+var_40+8], 6662647Ah
0x14001924c  mov     [rbp+57h+var_30], r8d
0x140019250  cmp     [rcx+48h], esi
0x140019253  jz      short loc_140019259
0x140019255  xor     ecx, ecx
0x140019257  jmp     short loc_14001925D
0x140019259  mov     rcx, [rcx+8]; FileHandle
0x14001925d  mov     [rsp+0B0h+Key], rsi; Key
0x140019262  lea     rax, [rbp+57h+var_58]
0x140019266  mov     [rsp+0B0h+ByteOffset], rax; ByteOffset
0x14001926b  xor     r9d, r9d; ApcContext
0x14001926e  lea     rax, [rbp+57h+var_40]
0x140019272  mov     [rsp+0B0h+Length], 14h; Length
0x14001927a  mov     [rsp+0B0h+Buffer], rax; Buffer
0x14001927f  xor     r8d, r8d; ApcRoutine
0x140019282  lea     rax, [rbp+57h+var_50]
0x140019286  xor     edx, edx; Event
0x140019288  mov     [rsp+0B0h+IoStatusBlock], rax; IoStatusBlock
0x14001928d  call    cs:__imp_NtWriteFile
0x140019293  test    eax, eax
0x140019295  jns     short loc_1400192BE
0x140019297  lea     r9, aFailedToWriteT; "Failed to write the zdb header [%x]"
0x14001929e  mov     dword ptr [rsp+0B0h+IoStatusBlock], eax
0x1400192a2  mov     r8d, 16Fh
0x1400192a8  lea     rdx, aSdbpwritecompr; "SdbpWriteCompressedDatabase"
0x1400192af  mov     ecx, 1
0x1400192b4  call    AslLogCallPrintf
0x1400192b9  jmp     loc_1400193EE
0x1400192be  add     dword ptr [rbp+57h+var_58], 14h
0x1400192c2  mov     edx, 8; Flags
0x1400192c7  mov     r8d, [rbx+14h]; Size
0x1400192cb  mov     [rbp+57h+var_60], r8d
0x1400192cf  mov     rcx, gs:60h
0x1400192d8  mov     rcx, [rcx+30h]; HeapHandle
0x1400192dc  call    cs:__imp_RtlAllocateHeap
0x1400192e2  mov     rdi, rax
0x1400192e5  test    rax, rax
0x1400192e8  jnz     short loc_1400192FC
0x1400192ea  lea     r9, aFailedToAlloca_0; "Failed to allocate zdb buffer."
0x1400192f1  mov     r8d, 178h
0x1400192f7  jmp     loc_1400193DD
0x1400192fc  mov     r9d, [rbx+14h]
0x140019300  lea     rdx, [rbp+57h+var_60]
0x140019304  mov     r8, [rbx+8]
0x140019308  mov     rcx, rdi
0x14001930b  mov     rax, cs:g_CompressCallback
0x140019312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019317  test    eax, eax
0x140019319  jnz     short loc_140019339
0x14001931b  lea     r9, aCompressCallba_0; "Compress callback failed to compress th"...
0x140019322  mov     r8d, 182h
0x140019328  lea     rdx, aSdbpwritecompr; "SdbpWriteCompressedDatabase"
0x14001932f  lea     ecx, [rax+1]
0x140019332  call    AslLogCallPrintf
0x140019337  jmp     short loc_1400193A7
0x140019339  mov     rax, [rbx]
0x14001933c  cmp     [rax+48h], esi
0x14001933f  jz      short loc_140019345
0x140019341  xor     ecx, ecx
0x140019343  jmp     short loc_140019349
0x140019345  mov     rcx, [rax+8]; FileHandle
0x140019349  mov     [rsp+0B0h+Key], rsi; Key
0x14001934e  lea     rax, [rbp+57h+var_58]
0x140019352  mov     [rsp+0B0h+ByteOffset], rax; ByteOffset
0x140019357  xor     r9d, r9d; ApcContext
0x14001935a  mov     eax, [rbp+57h+var_60]
0x14001935d  xor     r8d, r8d; ApcRoutine
0x140019360  mov     [rsp+0B0h+Length], eax; Length
0x140019364  xor     edx, edx; Event
0x140019366  lea     rax, [rbp+57h+var_50]
0x14001936a  mov     [rsp+0B0h+Buffer], rdi; Buffer
0x14001936f  mov     [rsp+0B0h+IoStatusBlock], rax; IoStatusBlock
0x140019374  call    cs:__imp_NtWriteFile
0x14001937a  test    eax, eax
0x14001937c  jns     short loc_1400193A2
0x14001937e  lea     r9, aFailedToWriteT_1; "Failed to write the zdb [%x]"
0x140019385  mov     dword ptr [rsp+0B0h+IoStatusBlock], eax
0x140019389  mov     r8d, 195h
0x14001938f  lea     rdx, aSdbpwritecompr; "SdbpWriteCompressedDatabase"
0x140019396  mov     ecx, 1
0x14001939b  call    AslLogCallPrintf
0x1400193a0  jmp     short loc_1400193A7
0x1400193a2  mov     esi, 1
0x1400193a7  mov     rcx, gs:60h
0x1400193b0  mov     r8, rdi; P
0x1400193b3  xor     edx, edx; Flags
0x1400193b5  mov     rcx, [rcx+30h]; HeapHandle
0x1400193b9  call    cs:__imp_RtlFreeHeap
0x1400193bf  jmp     short loc_1400193EE
0x1400193c1  lea     r9, aInputDbWasEith; "Input DB was either too large or too sm"...
0x1400193c8  mov     r8d, 157h
0x1400193ce  jmp     short loc_1400193DD
0x1400193d0  lea     r9, aInputDbWasNotI; "Input DB was not in a valid state."
0x1400193d7  mov     r8d, 151h
0x1400193dd  lea     rdx, aSdbpwritecompr; "SdbpWriteCompressedDatabase"
0x1400193e4  mov     ecx, 1
0x1400193e9  call    AslLogCallPrintf
0x1400193ee  mov     eax, esi
0x1400193f0  mov     rcx, [rbp+57h+var_28]
0x1400193f4  xor     rcx, rsp; StackCookie
0x1400193f7  call    __security_check_cookie
0x1400193fc  add     rsp, 98h
0x140019403  pop     rdi
0x140019404  pop     rsi
0x140019405  pop     rbx
0x140019406  pop     rbp
0x140019407  retn
```
