# SdbpOpenCompressedDatabase

- ea: `0x140019018`
- end: `0x1400191a0`
- name: `SdbpOpenCompressedDatabase`
- size: `392`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140016198`

## callees

- `0x14001008c`
- `0x140015934`
- `0x140017730`
- `0x140019018`
- `0x14002f010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1400190cd`
- `ntdll!RtlAllocateHeap` at `0x1400190cd`
- `ntdll!RtlFreeHeap` at `0x140019143`
- `ntdll!RtlFreeHeap` at `0x140019143`

## string_xrefs

- `0x14001904d`: `SdbpOpenCompressedDatabase`
- `0x140019122`: `SdbpOpenCompressedDatabase`
- `0x1400190a2`: `SDB compression algorithm does not match callback algorithm.`
- `0x140019088`: `SDB is not compressed`
- `0x1400190db`: `SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory`

## pseudocode

```c
__int64 __fastcall SdbpOpenCompressedDatabase(_QWORD **a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // edi
  _QWORD *v4; // rbx
  _DWORD *v7; // rbp
  _DWORD *v8; // rcx
  PVOID Heap; // r14
  __int64 result; // rax
  _QWORD *v11; // rax
  unsigned int v12; // [rsp+78h] [rbp+10h] BYREF
  int v13; // [rsp+7Ch] [rbp+14h]

  v13 = HIDWORD(a2);
  v3 = 0;
  v4 = 0;
  v12 = 0;
  if ( !g_ExpandCallback )
  {
    AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 175, "No expand callback method set. Cannot expand ZDB file.");
    goto LABEL_16;
  }
  v7 = *a1;
  if ( *((_DWORD *)*a1 + 5) >= 0x14u )
  {
    v8 = (_DWORD *)*((_QWORD *)v7 + 1);
    if ( v8[2] == 1717724282 )
    {
      if ( v8[3] == g_ExpectedAlgorithm )
      {
        v12 = v8[4];
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v12);
        if ( Heap )
        {
          if ( (unsigned int)((__int64 (__fastcall *)(PVOID, unsigned int *, __int64, _QWORD))g_ExpandCallback)(
                               Heap,
                               &v12,
                               *((_QWORD *)v7 + 1) + 20LL,
                               (unsigned int)(v7[5] - 20)) )
          {
            v11 = SdbpOpenDatabaseInMemory((__int64)Heap, v12, a3);
            v4 = v11;
            if ( v11 )
            {
              *((_DWORD *)v11 + 6) |= 0xCu;
              v3 = 1;
              v12 = 0;
              goto LABEL_16;
            }
          }
          else
          {
            AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 221, "Expand callback failed to expand SDB");
          }
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
          v12 = 0;
          if ( v4 )
          {
            SdbCloseDatabaseRead(v4);
            v4 = 0;
          }
        }
        else
        {
          AslLogCallPrintf(
            1,
            "SdbpOpenCompressedDatabase",
            211,
            "SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory");
        }
      }
      else
      {
        AslLogCallPrintf(
          1,
          "SdbpOpenCompressedDatabase",
          192,
          "SDB compression algorithm does not match callback algorithm.");
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 187, "SDB is not compressed");
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 180, "SDB file too small to be valid");
  }
LABEL_16:
  SdbCloseDatabaseRead(*a1);
  result = v3;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x140019018  mov     [rsp+arg_8], rdx
0x14001901d  push    rbx
0x14001901e  push    rbp
0x14001901f  push    rsi
0x140019020  push    rdi
0x140019021  push    r14
0x140019023  push    r15
0x140019025  sub     rsp, 38h
0x140019029  xor     edi, edi
0x14001902b  xor     ebx, ebx
0x14001902d  cmp     cs:g_ExpandCallback, rbx
0x140019034  mov     r15d, r8d
0x140019037  mov     rsi, rcx
0x14001903a  mov     dword ptr [rsp+68h+arg_8], edi
0x14001903e  jnz     short loc_140019063
0x140019040  lea     r9, aNoExpandCallba; "No expand callback method set. Cannot e"...
0x140019047  mov     r8d, 0AFh
0x14001904d  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x140019054  mov     ecx, 1
0x140019059  call    AslLogCallPrintf
0x14001905e  jmp     loc_14001915C
0x140019063  mov     rbp, [rcx]
0x140019066  cmp     dword ptr [rbp+14h], 14h
0x14001906a  jnb     short loc_14001907B
0x14001906c  lea     r9, aSdbFileTooSmal; "SDB file too small to be valid"
0x140019073  mov     r8d, 0B4h
0x140019079  jmp     short loc_14001904D
0x14001907b  mov     rcx, [rbp+8]
0x14001907f  cmp     dword ptr [rcx+8], 6662647Ah
0x140019086  jz      short loc_140019097
0x140019088  lea     r9, aSdbIsNotCompre; "SDB is not compressed"
0x14001908f  mov     r8d, 0BBh
0x140019095  jmp     short loc_14001904D
0x140019097  mov     eax, cs:g_ExpectedAlgorithm
0x14001909d  cmp     [rcx+0Ch], eax
0x1400190a0  jz      short loc_1400190B1
0x1400190a2  lea     r9, aSdbCompression; "SDB compression algorithm does not matc"...
0x1400190a9  mov     r8d, 0C0h
0x1400190af  jmp     short loc_14001904D
0x1400190b1  mov     eax, [rcx+10h]
0x1400190b4  mov     edx, 8; Flags
0x1400190b9  mov     dword ptr [rsp+68h+arg_8], eax
0x1400190bd  mov     r8d, eax; Size
0x1400190c0  mov     rcx, gs:60h
0x1400190c9  mov     rcx, [rcx+30h]; HeapHandle
0x1400190cd  call    cs:__imp_RtlAllocateHeap
0x1400190d3  mov     r14, rax
0x1400190d6  test    rax, rax
0x1400190d9  jnz     short loc_1400190ED
0x1400190db  lea     r9, aSdbpopencompre_1; "SdbpOpenCompressedDatabase failed to al"...
0x1400190e2  mov     r8d, 0D3h
0x1400190e8  jmp     loc_14001904D
0x1400190ed  mov     r9d, [rbp+14h]
0x1400190f1  lea     rdx, [rsp+68h+arg_8]
0x1400190f6  mov     r8, [rbp+8]
0x1400190fa  sub     r9d, 14h
0x1400190fe  mov     rax, cs:g_ExpandCallback
0x140019105  add     r8, 14h
0x140019109  mov     rcx, r14
0x14001910c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019111  test    eax, eax
0x140019113  jnz     short loc_140019176
0x140019115  lea     r9, aExpandCallback; "Expand callback failed to expand SDB"
0x14001911c  mov     r8d, 0DDh
0x140019122  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x140019129  lea     ecx, [rax+1]
0x14001912c  call    AslLogCallPrintf
0x140019131  mov     rcx, gs:60h
0x14001913a  mov     r8, r14; P
0x14001913d  xor     edx, edx; Flags
0x14001913f  mov     rcx, [rcx+30h]; HeapHandle
0x140019143  call    cs:__imp_RtlFreeHeap
0x140019149  mov     dword ptr [rsp+68h+arg_8], edi
0x14001914d  test    rbx, rbx
0x140019150  jz      short loc_14001915C
0x140019152  mov     rcx, rbx
0x140019155  call    SdbCloseDatabaseRead
0x14001915a  xor     ebx, ebx
0x14001915c  mov     rcx, [rsi]
0x14001915f  call    SdbCloseDatabaseRead
0x140019164  mov     eax, edi
0x140019166  mov     [rsi], rbx
0x140019169  add     rsp, 38h
0x14001916d  pop     r15
0x14001916f  pop     r14
0x140019171  pop     rdi
0x140019172  pop     rsi
0x140019173  pop     rbp
0x140019174  pop     rbx
0x140019175  retn
0x140019176  mov     edx, dword ptr [rsp+68h+arg_8]
0x14001917a  mov     r8d, r15d
0x14001917d  mov     rcx, r14
0x140019180  call    SdbpOpenDatabaseInMemory
0x140019185  mov     rbx, rax
0x140019188  test    rax, rax
0x14001918b  jz      short loc_140019131
0x14001918d  or      dword ptr [rax+18h], 0Ch
0x140019191  mov     edi, 1
0x140019196  mov     dword ptr [rsp+68h+arg_8], 0
0x14001919e  jmp     short loc_14001915C
```
