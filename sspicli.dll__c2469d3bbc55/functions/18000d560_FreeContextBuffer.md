# FreeContextBuffer

- ea: `0x18000d560`
- end: `0x18000d6e5`
- name: `FreeContextBuffer`
- size: `389`
- prototype: `SECURITY_STATUS __stdcall(PVOID pvContextBuffer)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004290`
- `0x1800157e0`
- `0x18001fc00`
- `0x1800207f0`

## callees

- `0x180007c90`
- `0x18000d560`
- `0x18001b500`
- `0x180022053`
- `0x180023010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000d5e1`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d63d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d5e1`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d63d`
- `ntdll!RtlEnterCriticalSection` at `0x18000d579`
- `ntdll!RtlEnterCriticalSection` at `0x18000d579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d617`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d617`

## pseudocode

```c
SECURITY_STATUS __stdcall FreeContextBuffer(PVOID pvContextBuffer)
{
  unsigned int v2; // ecx
  unsigned int v3; // esi
  PVOID *v4; // r9
  char v5; // bl
  void (__fastcall **v6)(PVOID); // rdx

  RtlEnterCriticalSection(&SecVMListLock);
  v2 = 0;
  v3 = SecVMListElements;
  while ( 1 )
  {
    if ( v2 >= SecVMListElements )
    {
      RtlLeaveCriticalSection(&SecVMListLock);
LABEL_9:
      LocalFree(pvContextBuffer);
      return 0;
    }
    v4 = (PVOID *)((char *)SecVMList + 16 * v2);
    if ( pvContextBuffer == *v4 )
      break;
    ++v2;
  }
  v5 = *((_BYTE *)v4 + 8);
  memmove_0((char *)SecVMList + 16 * v2, (char *)SecVMList + 16 * v2 + 16, 16LL * (SecVMListElements - v2 - 1));
  ++SecVMListAvailable;
  SecVMListElements = v3 - 1;
  RtlLeaveCriticalSection(&SecVMListLock);
  if ( v5 )
  {
    v6 = (void (__fastcall **)(PVOID))SecpLsaInprocDispatch;
    if ( !SecpLsaInprocDispatch )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_32bb870c29d9333430a8ba27024d5086_Traceguids,
          pvContextBuffer);
      goto LABEL_9;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_32bb870c29d9333430a8ba27024d5086_Traceguids,
        pvContextBuffer);
      v6 = (void (__fastcall **)(PVOID))SecpLsaInprocDispatch;
    }
    (*v6)(pvContextBuffer);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_32bb870c29d9333430a8ba27024d5086_Traceguids,
        pvContextBuffer);
    LsaFreeReturnBuffer(pvContextBuffer);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d560  mov     [rsp+arg_0], rbx
0x18000d565  mov     [rsp+arg_8], rsi
0x18000d56a  push    rdi
0x18000d56b  sub     rsp, 20h
0x18000d56f  mov     rdi, rcx
0x18000d572  lea     rcx, ?SecVMListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000d579  call    cs:__imp_RtlEnterCriticalSection
0x18000d57f  mov     r10, cs:?SecVMList@@3PEAU_VM_LIST_ENTRY@@EA; _VM_LIST_ENTRY * SecVMList
0x18000d586  xor     ecx, ecx
0x18000d588  mov     esi, cs:?SecVMListElements@@3KA; ulong SecVMListElements
0x18000d58e  cmp     ecx, esi
0x18000d590  jnb     loc_18000D636
0x18000d596  mov     r9d, ecx
0x18000d599  lea     edx, [rcx+1]
0x18000d59c  shl     r9, 4
0x18000d5a0  add     r9, r10
0x18000d5a3  cmp     rdi, [r9]
0x18000d5a6  jnz     loc_18000D62F
0x18000d5ac  mov     bl, [r9+8]
0x18000d5b0  mov     r8d, esi
0x18000d5b3  sub     r8d, ecx
0x18000d5b6  shl     rdx, 4
0x18000d5ba  dec     r8d
0x18000d5bd  add     rdx, r10; Src
0x18000d5c0  shl     r8, 4; Size
0x18000d5c4  mov     rcx, r9; void *
0x18000d5c7  call    memmove_0
0x18000d5cc  inc     cs:?SecVMListAvailable@@3KA; ulong SecVMListAvailable
0x18000d5d2  lea     rcx, ?SecVMListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000d5d9  dec     esi
0x18000d5db  mov     cs:?SecVMListElements@@3KA, esi; ulong SecVMListElements
0x18000d5e1  call    cs:__imp_RtlLeaveCriticalSection
0x18000d5e7  test    bl, bl
0x18000d5e9  jz      loc_18000D6A7
0x18000d5ef  mov     rdx, cs:SecpLsaInprocDispatch
0x18000d5f6  test    rdx, rdx
0x18000d5f9  jnz     short loc_18000D645
0x18000d5fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d602  lea     rax, WPP_GLOBAL_Control
0x18000d609  cmp     rcx, rax
0x18000d60c  jz      short loc_18000D614
0x18000d60e  test    byte ptr [rcx+1Ch], 4
0x18000d612  jnz     short loc_18000D68A
0x18000d614  mov     rcx, rdi; hMem
0x18000d617  call    cs:__imp_LocalFree
0x18000d61d  mov     rbx, [rsp+28h+arg_0]
0x18000d622  xor     eax, eax
0x18000d624  mov     rsi, [rsp+28h+arg_8]
0x18000d629  add     rsp, 20h
0x18000d62d  pop     rdi
0x18000d62e  retn
0x18000d62f  mov     ecx, edx
0x18000d631  jmp     loc_18000D58E
0x18000d636  lea     rcx, ?SecVMListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000d63d  call    cs:__imp_RtlLeaveCriticalSection
0x18000d643  jmp     short loc_18000D614
0x18000d645  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d64c  lea     rax, WPP_GLOBAL_Control
0x18000d653  cmp     rcx, rax
0x18000d656  jz      short loc_18000D67D
0x18000d658  test    byte ptr [rcx+1Ch], 4
0x18000d65c  jz      short loc_18000D67D
0x18000d65e  mov     rcx, [rcx+10h]
0x18000d662  lea     r8, WPP_32bb870c29d9333430a8ba27024d5086_Traceguids
0x18000d669  mov     edx, 0Ah
0x18000d66e  mov     r9, rdi
0x18000d671  call    WPP_SF_q
0x18000d676  mov     rdx, cs:SecpLsaInprocDispatch
0x18000d67d  mov     rax, [rdx]
0x18000d680  mov     rcx, rdi
0x18000d683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d688  jmp     short loc_18000D61D
0x18000d68a  mov     rcx, [rcx+10h]
0x18000d68e  lea     r8, WPP_32bb870c29d9333430a8ba27024d5086_Traceguids
0x18000d695  mov     edx, 0Bh
0x18000d69a  mov     r9, rdi
0x18000d69d  call    WPP_SF_q
0x18000d6a2  jmp     loc_18000D614
0x18000d6a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6ae  lea     rax, WPP_GLOBAL_Control
0x18000d6b5  cmp     rcx, rax
0x18000d6b8  jz      short loc_18000D6D8
0x18000d6ba  test    byte ptr [rcx+1Ch], 4
0x18000d6be  jz      short loc_18000D6D8
0x18000d6c0  mov     rcx, [rcx+10h]
0x18000d6c4  lea     r8, WPP_32bb870c29d9333430a8ba27024d5086_Traceguids
0x18000d6cb  mov     edx, 0Ch
0x18000d6d0  mov     r9, rdi
0x18000d6d3  call    WPP_SF_q
0x18000d6d8  mov     rcx, rdi; Buffer
0x18000d6db  call    LsaFreeReturnBuffer
0x18000d6e0  jmp     loc_18000D61D
```
