# SrvNetDeviceControl

- ea: `0x1400507c0`
- end: `0x140050935`
- name: `SrvNetDeviceControl`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140050640`

## callees

- `0x140015790`
- `0x1400507c0`
- `0x140050940`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14005082b`
- `ntoskrnl!ProbeForRead` at `0x140050843`
- `ntoskrnl!ProbeForRead` at `0x14005082b`
- `ntoskrnl!ProbeForRead` at `0x140050843`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400508ec`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400508ec`

## pseudocode

```c
__int64 __fastcall SrvNetDeviceControl(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v3; // rbx
  int v4; // esi
  unsigned int v5; // r15d
  unsigned int v6; // r14d
  void *v7; // r13
  PVOID v8; // r12
  __int64 v10; // rcx

  v2 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_6feed98b03653c48bfec8caf18231585_Traceguids);
  }
  v3 = *(_QWORD *)(v2 + 184);
  v4 = *(_DWORD *)(v3 + 24);
  v5 = *(_DWORD *)(v3 + 16);
  v6 = *(_DWORD *)(v3 + 8);
  if ( (v4 & 3) == 3 )
  {
    v7 = *(void **)(v3 + 32);
    v8 = *(PVOID *)(v2 + 112);
    if ( *(_BYTE *)(v2 + 64) == 1 )
    {
      ProbeForRead(*(volatile void **)(v3 + 32), v5, 1u);
      ProbeForRead(v8, v6, 1u);
    }
  }
  else if ( (v4 & 3) != 0 )
  {
    if ( (v4 & 3u) - 1 < 2 )
    {
      v7 = *(void **)(v2 + 24);
      if ( v6 )
      {
        v10 = *(_QWORD *)(v2 + 8);
        if ( (*(_BYTE *)(v10 + 10) & 5) != 0 )
          v8 = *(PVOID *)(v10 + 24);
        else
          v8 = MmMapLockedPagesSpecifyCache((PMDL)v10, 0, MmCached, 0, 0, 0x40000010u);
      }
      else
      {
        v8 = 0;
      }
    }
    else
    {
      v8 = 0;
      v7 = 0;
    }
  }
  else
  {
    v7 = *(void **)(v2 + 24);
    v8 = v7;
  }
  LOBYTE(a2) = 1;
  return SrvNetProcessFsctl(
           *(_QWORD *)(v3 + 48),
           a2,
           v7,
           v5,
           v8,
           v6,
           v4,
           v2 + 48,
           *(_QWORD *)(v3 + 40),
           *(_BYTE *)(v2 + 64),
           v2);
}

```

## disassembly

```asm
0x1400507c0  push    rbx
0x1400507c2  push    rsi
0x1400507c3  push    rdi
0x1400507c4  push    r12
0x1400507c6  push    r13
0x1400507c8  push    r14
0x1400507ca  push    r15
0x1400507cc  sub     rsp, 60h
0x1400507d0  mov     rdi, rdx
0x1400507d3  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x1400507da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400507e1  cmp     rcx, rax
0x1400507e4  jz      short loc_1400507F1
0x1400507e6  mov     eax, [rcx+2Ch]
0x1400507e9  test    al, 2
0x1400507eb  jnz     loc_140050900
0x1400507f1  mov     rbx, [rdi+0B8h]
0x1400507f8  mov     esi, [rbx+18h]
0x1400507fb  mov     r15d, [rbx+10h]
0x1400507ff  mov     r14d, [rbx+8]
0x140050803  mov     eax, esi
0x140050805  and     eax, 3
0x140050808  cmp     eax, 3
0x14005080b  jnz     loc_1400508A2
0x140050811  mov     r13, [rbx+20h]
0x140050815  mov     r12, [rdi+70h]
0x140050819  cmp     byte ptr [rdi+40h], 1
0x14005081d  jnz     short loc_140050853
0x14005081f  mov     edx, r15d; Length
0x140050822  mov     r8d, 1; Alignment
0x140050828  mov     rcx, r13; Address
0x14005082b  call    cs:__imp_ProbeForRead
0x140050832  nop     dword ptr [rax+rax+00h]
0x140050837  mov     edx, r14d; Length
0x14005083a  mov     r8d, 1; Alignment
0x140050840  mov     rcx, r12; Address
0x140050843  call    cs:__imp_ProbeForRead
0x14005084a  nop     dword ptr [rax+rax+00h]
0x14005084f  jmp     short loc_140050853
0x140050851  jmp     short loc_140050891
0x140050853  lea     rcx, [rdi+30h]
0x140050857  mov     [rsp+98h+var_48], rdi
0x14005085c  movzx   eax, byte ptr [rdi+40h]
0x140050860  mov     [rsp+98h+var_50], al
0x140050864  mov     rax, [rbx+28h]
0x140050868  mov     [rsp+98h+var_58], rax
0x14005086d  mov     [rsp+98h+var_60], rcx
0x140050872  mov     [rsp+98h+var_68], esi
0x140050876  mov     [rsp+98h+Priority], r14d
0x14005087b  mov     qword ptr [rsp+98h+BugCheckOnFailure], r12
0x140050880  mov     r9d, r15d
0x140050883  mov     r8, r13
0x140050886  mov     dl, 1
0x140050888  mov     rcx, [rbx+30h]
0x14005088c  call    SrvNetProcessFsctl
0x140050891  add     rsp, 60h
0x140050895  pop     r15
0x140050897  pop     r14
0x140050899  pop     r13
0x14005089b  pop     r12
0x14005089d  pop     rdi
0x14005089e  pop     rsi
0x14005089f  pop     rbx
0x1400508a0  retn
0x1400508a2  test    eax, eax
0x1400508a4  jz      short loc_1400508B8
0x1400508a6  sub     eax, 1
0x1400508a9  jz      short loc_140050924
0x1400508ab  cmp     eax, 1
0x1400508ae  jz      short loc_140050924
0x1400508b0  xor     r12d, r12d
0x1400508b3  mov     r13d, r12d
0x1400508b6  jmp     short loc_140050853
0x1400508b8  mov     r13, [rdi+18h]
0x1400508bc  mov     r12, r13
0x1400508bf  jmp     short loc_140050853
0x1400508c1  mov     rcx, [rdi+8]; MemoryDescriptorList
0x1400508c5  test    byte ptr [rcx+0Ah], 5
0x1400508c9  jz      short loc_1400508D1
0x1400508cb  mov     r12, [rcx+18h]
0x1400508cf  jmp     short loc_140050853
0x1400508d1  mov     [rsp+98h+Priority], 40000010h; Priority
0x1400508d9  xor     r12d, r12d
0x1400508dc  mov     [rsp+98h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x1400508e1  xor     r9d, r9d; RequestedAddress
0x1400508e4  xor     edx, edx; AccessMode
0x1400508e6  mov     r8d, 1; CacheType
0x1400508ec  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400508f3  nop     dword ptr [rax+rax+00h]
0x1400508f8  mov     r12, rax
0x1400508fb  jmp     loc_140050853
0x140050900  cmp     byte ptr [rcx+29h], 2
0x140050904  jb      loc_1400507F1
0x14005090a  mov     edx, 0Fh
0x14005090f  lea     r8, WPP_6feed98b03653c48bfec8caf18231585_Traceguids
0x140050916  mov     rcx, [rcx+18h]
0x14005091a  call    WPP_SF_
0x14005091f  jmp     loc_1400507F1
0x140050924  mov     r13, [rdi+18h]
0x140050928  test    r14d, r14d
0x14005092b  jnz     short loc_1400508C1
0x14005092d  xor     r12d, r12d
0x140050930  jmp     loc_140050853
```
