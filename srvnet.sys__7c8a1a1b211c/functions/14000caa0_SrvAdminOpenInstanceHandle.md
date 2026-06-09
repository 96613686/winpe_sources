# SrvAdminOpenInstanceHandle

- ea: `0x14000caa0`
- end: `0x14000cc82`
- name: `SrvAdminOpenInstanceHandle`
- size: `482`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140050640`
- `0x1400525b0`

## callees

- `0x14000caa0`
- `0x14001389c`
- `0x140015790`
- `0x1400163d8`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14000cb3b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000cb3b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cba6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cba6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000cae4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000caf9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000cae4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000caf9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cacf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cacf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cb87`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cb9a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cb87`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cb9a`

## pseudocode

```c
__int64 __fastcall SrvAdminOpenInstanceHandle(struct _DEVICE_OBJECT *a1, __int64 a2)
{
  const UNICODE_STRING *v3; // rsi
  __int64 i; // rbx
  unsigned int v5; // esi

  if ( a1 != SrvAdminDeviceObject )
    return 0;
  v3 = (const UNICODE_STRING *)qword_140036198;
  if ( *(_WORD *)(a2 + 88) )
    v3 = (const UNICODE_STRING *)(a2 + 88);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&SrvAdminInstanceStartStopLock, 1u);
  ExAcquireResourceExclusiveLite(&SrvAdminInstanceListLock, 1u);
  if ( *(_QWORD *)(a2 + 24) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids);
    }
    v5 = -1073741595;
  }
  else
  {
    for ( i = SrvAdminInstanceList; (__int64 *)i != &SrvAdminInstanceList; i = *(_QWORD *)i )
    {
      if ( RtlEqualUnicodeString((PCUNICODE_STRING)(i + 32), v3, 1u) )
      {
        v5 = 0;
        *(_QWORD *)(a2 + 24) = i;
        _InterlockedIncrement((volatile signed __int32 *)(i + 24));
        ++*(_DWORD *)(i + 28);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids,
            *(unsigned __int8 *)(i + 16));
        }
        goto LABEL_10;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids, v3);
    }
    v5 = -1073741772;
  }
LABEL_10:
  ExReleaseResourceLite(&SrvAdminInstanceStartStopLock);
  ExReleaseResourceLite(&SrvAdminInstanceListLock);
  KeLeaveCriticalRegion();
  return v5;
}

```

## disassembly

```asm
0x14000caa0  push    rdi
0x14000caa2  sub     rsp, 20h
0x14000caa6  cmp     rcx, cs:SrvAdminDeviceObject
0x14000caad  mov     rdi, rdx
0x14000cab0  jnz     loc_14000CBE2
0x14000cab6  cmp     word ptr [rdx+58h], 0
0x14000cabb  lea     rax, [rdx+58h]
0x14000cabf  mov     [rsp+28h+arg_10], rsi
0x14000cac4  lea     rsi, qword_140036198
0x14000cacb  cmovnz  rsi, rax
0x14000cacf  call    cs:__imp_KeEnterCriticalRegion
0x14000cad6  nop     dword ptr [rax+rax+00h]
0x14000cadb  mov     dl, 1; Wait
0x14000cadd  lea     rcx, SrvAdminInstanceStartStopLock; Resource
0x14000cae4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000caeb  nop     dword ptr [rax+rax+00h]
0x14000caf0  mov     dl, 1; Wait
0x14000caf2  lea     rcx, SrvAdminInstanceListLock; Resource
0x14000caf9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000cb00  nop     dword ptr [rax+rax+00h]
0x14000cb05  cmp     qword ptr [rdi+18h], 0
0x14000cb0a  jnz     loc_14000CBC8
0x14000cb10  mov     [rsp+28h+arg_0], rbx
0x14000cb15  mov     rbx, cs:SrvAdminInstanceList
0x14000cb1c  mov     [rsp+28h+arg_8], rbp
0x14000cb21  lea     rbp, SrvAdminInstanceList
0x14000cb28  cmp     rbx, rbp
0x14000cb2b  jz      loc_14000CC38
0x14000cb31  lea     rcx, [rbx+20h]; String1
0x14000cb35  mov     r8b, 1; CaseInSensitive
0x14000cb38  mov     rdx, rsi; String2
0x14000cb3b  call    cs:__imp_RtlEqualUnicodeString
0x14000cb42  nop     dword ptr [rax+rax+00h]
0x14000cb47  test    al, al
0x14000cb49  jz      short loc_14000CBC0
0x14000cb4b  xor     esi, esi
0x14000cb4d  mov     [rdi+18h], rbx
0x14000cb51  lock inc dword ptr [rbx+18h]
0x14000cb55  inc     dword ptr [rbx+1Ch]
0x14000cb58  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb5f  lea     rax, WPP_GLOBAL_Control
0x14000cb66  cmp     rcx, rax
0x14000cb69  jz      short loc_14000CB76
0x14000cb6b  mov     eax, [rcx+2Ch]
0x14000cb6e  test    al, 20h
0x14000cb70  jnz     loc_14000CC0F
0x14000cb76  mov     rbx, [rsp+28h+arg_0]
0x14000cb7b  mov     rbp, [rsp+28h+arg_8]
0x14000cb80  lea     rcx, SrvAdminInstanceStartStopLock; Resource
0x14000cb87  call    cs:__imp_ExReleaseResourceLite
0x14000cb8e  nop     dword ptr [rax+rax+00h]
0x14000cb93  lea     rcx, SrvAdminInstanceListLock; Resource
0x14000cb9a  call    cs:__imp_ExReleaseResourceLite
0x14000cba1  nop     dword ptr [rax+rax+00h]
0x14000cba6  call    cs:__imp_KeLeaveCriticalRegion
0x14000cbad  nop     dword ptr [rax+rax+00h]
0x14000cbb2  mov     eax, esi
0x14000cbb4  mov     rsi, [rsp+28h+arg_10]
0x14000cbb9  add     rsp, 20h
0x14000cbbd  pop     rdi
0x14000cbbe  retn
0x14000cbc0  mov     rbx, [rbx]
0x14000cbc3  jmp     loc_14000CB28
0x14000cbc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cbcf  lea     rax, WPP_GLOBAL_Control
0x14000cbd6  cmp     rcx, rax
0x14000cbd9  jnz     short loc_14000CBEB
0x14000cbdb  mov     esi, 0C00000E5h
0x14000cbe0  jmp     short loc_14000CB80
0x14000cbe2  xor     eax, eax
0x14000cbe4  add     rsp, 20h
0x14000cbe8  pop     rdi
0x14000cbe9  retn
0x14000cbeb  mov     eax, [rcx+2Ch]
0x14000cbee  test    al, 20h
0x14000cbf0  jz      short loc_14000CBDB
0x14000cbf2  cmp     byte ptr [rcx+29h], 1
0x14000cbf6  jb      short loc_14000CBDB
0x14000cbf8  mov     rcx, [rcx+18h]
0x14000cbfc  lea     r8, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids
0x14000cc03  mov     edx, 16h
0x14000cc08  call    WPP_SF_
0x14000cc0d  jmp     short loc_14000CBDB
0x14000cc0f  cmp     byte ptr [rcx+29h], 2
0x14000cc13  jb      loc_14000CB76
0x14000cc19  movzx   r9d, byte ptr [rbx+10h]
0x14000cc1e  lea     r8, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids
0x14000cc25  mov     rcx, [rcx+18h]
0x14000cc29  mov     edx, 17h
0x14000cc2e  call    WPP_SF_d
0x14000cc33  jmp     loc_14000CB76
0x14000cc38  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc3f  lea     rax, WPP_GLOBAL_Control
0x14000cc46  cmp     rcx, rax
0x14000cc49  jz      loc_14002C2B4
0x14000cc4f  mov     eax, [rcx+2Ch]
0x14000cc52  test    al, 20h
0x14000cc54  jz      loc_14002C2B4
0x14000cc5a  cmp     byte ptr [rcx+29h], 2
0x14000cc5e  jb      loc_14002C2B4
0x14000cc64  mov     rcx, [rcx+18h]
0x14000cc68  lea     r8, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids
0x14000cc6f  mov     edx, 18h
0x14000cc74  mov     r9, rsi
0x14000cc77  call    WPP_SF_Z
0x14000cc7c  nop
0x14000cc7d  jmp     loc_14002C2B4
0x14002c2b4  mov     esi, 0C0000034h
0x14002c2b9  jmp     loc_14000CB76
```
