# SclReleasePrivileges

- ea: `0x180001970`
- end: `0x180001a12`
- name: `SclReleasePrivileges`
- size: `162`
- prototype: `__int64 __fastcall(_DWORD *P)`
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180001010`
- `0x180001de0`
- `0x180002640`
- `0x180002a60`
- `0x180005a90`
- `0x1800061b0`
- `0x1800065f8`

## callees

- `0x180001970`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x1800019b9`
- `ntdll!RtlAdjustPrivilege` at `0x1800019c3`
- `ntdll!RtlAdjustPrivilege` at `0x1800019b9`
- `ntdll!RtlAdjustPrivilege` at `0x1800019c3`
- `ntdll!RtlFreeHeap` at `0x1800019e2`
- `ntdll!RtlFreeHeap` at `0x1800019fa`
- `ntdll!RtlFreeHeap` at `0x1800019e2`
- `ntdll!RtlFreeHeap` at `0x1800019fa`

## pseudocode

```c
__int64 __fastcall SclReleasePrivileges(_DWORD *P)
{
  NTSTATUS v3; // esi
  __int64 i; // rdi
  __int64 v5; // rcx
  ULONG v6; // ecx
  unsigned __int8 OldValue; // [rsp+30h] [rbp+8h] BYREF

  if ( !P )
    return 0;
  v3 = 0;
  if ( *(_QWORD *)P )
  {
    for ( i = 0; (unsigned int)i < P[2]; i = (unsigned int)(i + 1) )
    {
      v5 = *(_QWORD *)P;
      if ( *(_DWORD *)(*(_QWORD *)P + 8 * i + 4) )
      {
        OldValue = 0;
        v6 = *(_DWORD *)(v5 + 8 * i);
        if ( v3 < 0 )
          RtlAdjustPrivilege(v6, 0, 0, &OldValue);
        else
          v3 = RtlAdjustPrivilege(v6, 0, 0, &OldValue);
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)P);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180001970  mov     [rsp+arg_8], rbx
0x180001975  mov     [rsp+arg_10], rsi
0x18000197a  push    rdi
0x18000197b  sub     rsp, 20h
0x18000197f  mov     rbx, rcx
0x180001982  test    rcx, rcx
0x180001985  jnz     short loc_18000198B
0x180001987  xor     eax, eax
0x180001989  jmp     short loc_180001A02
0x18000198b  xor     esi, esi
0x18000198d  cmp     [rcx], rsi
0x180001990  jz      short loc_1800019E8
0x180001992  xor     edi, edi
0x180001994  cmp     [rcx+8], esi
0x180001997  jbe     short loc_1800019D0
0x180001999  mov     rcx, [rbx]
0x18000199c  cmp     dword ptr [rcx+rdi*8+4], 0
0x1800019a1  jz      short loc_1800019C9
0x1800019a3  xor     r8d, r8d; ForThread
0x1800019a6  mov     [rsp+28h+OldValue], 0
0x1800019ab  mov     ecx, [rcx+rdi*8]; Privilege
0x1800019ae  lea     r9, [rsp+28h+OldValue]; OldValue
0x1800019b3  xor     edx, edx; NewValue
0x1800019b5  test    esi, esi
0x1800019b7  js      short loc_1800019C3
0x1800019b9  call    cs:__imp_RtlAdjustPrivilege
0x1800019bf  mov     esi, eax
0x1800019c1  jmp     short loc_1800019C9
0x1800019c3  call    cs:__imp_RtlAdjustPrivilege
0x1800019c9  inc     edi
0x1800019cb  cmp     edi, [rbx+8]
0x1800019ce  jb      short loc_180001999
0x1800019d0  mov     rcx, gs:60h
0x1800019d9  xor     edx, edx; Flags
0x1800019db  mov     r8, [rbx]; P
0x1800019de  mov     rcx, [rcx+30h]; HeapHandle
0x1800019e2  call    cs:__imp_RtlFreeHeap
0x1800019e8  mov     rcx, gs:60h
0x1800019f1  mov     r8, rbx; P
0x1800019f4  xor     edx, edx; Flags
0x1800019f6  mov     rcx, [rcx+30h]; HeapHandle
0x1800019fa  call    cs:__imp_RtlFreeHeap
0x180001a00  mov     eax, esi
0x180001a02  mov     rbx, [rsp+28h+arg_8]
0x180001a07  mov     rsi, [rsp+28h+arg_10]
0x180001a0c  add     rsp, 20h
0x180001a10  pop     rdi
0x180001a11  retn
```
