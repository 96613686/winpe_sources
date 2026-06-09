# SclAcquireRequiredPrivileges

- ea: `0x180001010`
- end: `0x180001196`
- name: `SclAcquireRequiredPrivileges`
- size: `390`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180001de0`
- `0x180002640`
- `0x180002a60`
- `0x180005a90`
- `0x1800061b0`
- `0x1800065f8`

## callees

- `0x180001010`
- `0x180001970`
- `0x18000a524`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180001078`
- `ntdll!RtlAllocateHeap` at `0x1800010a8`
- `ntdll!RtlAllocateHeap` at `0x180001078`
- `ntdll!RtlAllocateHeap` at `0x1800010a8`
- `ntdll!RtlAdjustPrivilege` at `0x1800010f9`
- `ntdll!RtlAdjustPrivilege` at `0x1800010f9`

## string_xrefs

- `0x180001139`: `(%lx): Unable to enable privilege [%u]!`
- `0x18000114c`: `SclAcquireRequiredPrivileges`

## pseudocode

```c
__int64 __fastcall SclAcquireRequiredPrivileges(_QWORD *a1)
{
  _DWORD *Heap; // rsi
  NTSTATUS v4; // edi
  PVOID v5; // rax
  __int64 v6; // rbp
  ULONG v7; // r14d
  ULONG Privilege[8]; // [rsp+40h] [rbp-38h]
  unsigned __int8 OldValue; // [rsp+80h] [rbp+8h] BYREF

  Privilege[0] = 17;
  Privilege[1] = 18;
  Privilege[2] = 8;
  Privilege[3] = 9;
  Privilege[4] = 28;
  if ( !a1 )
    return 3221225485LL;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
  if ( Heap && (v5 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x28u), (*(_QWORD *)Heap = v5) != 0) )
  {
    v4 = 0;
    v6 = 0;
    Heap[2] = 5;
    while ( (unsigned int)v6 < 5 )
    {
      v7 = Privilege[v6];
      OldValue = 0;
      v4 = RtlAdjustPrivilege(v7, 1u, 0, &OldValue);
      if ( v4 < 0 )
      {
        SclLogGenericMessage(0, 3, (unsigned int)SclEvent_Generic_Error, 531, (__int64)"SclAcquireRequiredPrivileges");
        goto LABEL_12;
      }
      *(_DWORD *)(*(_QWORD *)Heap + 8 * v6) = v7;
      *(_DWORD *)(*(_QWORD *)Heap + 8 * v6 + 4) = OldValue == 0;
      v6 = (unsigned int)(v6 + 1);
    }
    *a1 = Heap;
    Heap = 0;
  }
  else
  {
    v4 = -1073741801;
  }
LABEL_12:
  SclReleasePrivileges(Heap);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001010  push    rbx
0x180001012  sub     rsp, 70h
0x180001016  mov     [rsp+78h+Privilege], 11h
0x18000101e  mov     rbx, rcx
0x180001021  mov     [rsp+78h+var_34], 12h
0x180001029  mov     [rsp+78h+var_30], 8
0x180001031  mov     [rsp+78h+var_2C], 9
0x180001039  mov     [rsp+78h+var_28], 1Ch
0x180001041  test    rcx, rcx
0x180001044  jnz     short loc_180001050
0x180001046  mov     eax, 0C000000Dh
0x18000104b  jmp     loc_180001190
0x180001050  mov     rcx, gs:60h
0x180001059  mov     edx, 8; Flags
0x18000105e  mov     [rsp+78h+arg_10], rsi
0x180001066  mov     r8d, 50h ; 'P'; Size
0x18000106c  mov     [rsp+78h+arg_18], rdi
0x180001074  mov     rcx, [rcx+30h]; HeapHandle
0x180001078  call    cs:__imp_RtlAllocateHeap
0x18000107e  mov     rsi, rax
0x180001081  test    rax, rax
0x180001084  jnz     short loc_180001090
0x180001086  mov     edi, 0C0000017h
0x18000108b  jmp     loc_180001176
0x180001090  mov     rcx, gs:60h
0x180001099  mov     edx, 8; Flags
0x18000109e  mov     r8d, 28h ; '('; Size
0x1800010a4  mov     rcx, [rcx+30h]; HeapHandle
0x1800010a8  call    cs:__imp_RtlAllocateHeap
0x1800010ae  mov     [rsi], rax
0x1800010b1  test    rax, rax
0x1800010b4  jz      short loc_180001086
0x1800010b6  mov     [rsp+78h+arg_8], rbp
0x1800010be  xor     edi, edi
0x1800010c0  mov     [rsp+78h+var_10], r14
0x1800010c5  xor     ebp, ebp
0x1800010c7  mov     [rsp+78h+var_18], r15
0x1800010cc  mov     dword ptr [rsi+8], 5
0x1800010d3  cmp     ebp, 5
0x1800010d6  jnb     loc_18000115F
0x1800010dc  mov     r14d, [rsp+rbp*4+78h+Privilege]
0x1800010e1  lea     r9, [rsp+78h+OldValue]; OldValue
0x1800010e9  mov     ecx, r14d; Privilege
0x1800010ec  mov     [rsp+78h+OldValue], 0
0x1800010f4  xor     r8d, r8d; ForThread
0x1800010f7  mov     dl, 1; NewValue
0x1800010f9  call    cs:__imp_RtlAdjustPrivilege
0x1800010ff  mov     edi, eax
0x180001101  test    eax, eax
0x180001103  js      short loc_180001123
0x180001105  mov     rcx, [rsi]
0x180001108  xor     edx, edx
0x18000110a  mov     [rcx+rbp*8], r14d
0x18000110e  cmp     [rsp+78h+OldValue], dl
0x180001115  mov     rcx, [rsi]
0x180001118  setz    dl
0x18000111b  mov     [rcx+rbp*8+4], edx
0x18000111f  inc     ebp
0x180001121  jmp     short loc_1800010D3
0x180001123  mov     [rsp+78h+var_40], r14d
0x180001128  lea     r8, SclEvent_Generic_Error
0x18000112f  mov     [rsp+78h+var_48], eax
0x180001133  mov     r9d, 213h
0x180001139  lea     rax, aLxUnableToEnab; "(%lx): Unable to enable privilege [%u]!"
0x180001140  mov     edx, 3
0x180001145  mov     [rsp+78h+var_50], rax
0x18000114a  xor     ecx, ecx
0x18000114c  lea     rax, aSclacquirerequ_0; "SclAcquireRequiredPrivileges"
0x180001153  mov     [rsp+78h+var_58], rax
0x180001158  call    SclLogGenericMessage
0x18000115d  jmp     short loc_180001164
0x18000115f  mov     [rbx], rsi
0x180001162  xor     esi, esi
0x180001164  mov     r14, [rsp+78h+var_10]
0x180001169  mov     r15, [rsp+78h+var_18]
0x18000116e  mov     rbp, [rsp+78h+arg_8]
0x180001176  mov     rcx, rsi; P
0x180001179  call    SclReleasePrivileges
0x18000117e  mov     rsi, [rsp+78h+arg_10]
0x180001186  mov     eax, edi
0x180001188  mov     rdi, [rsp+78h+arg_18]
0x180001190  add     rsp, 70h
0x180001194  pop     rbx
0x180001195  retn
```
