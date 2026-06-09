# WinHvpInitializeHypercallLookasideBuffer

- ea: `0x14001c140`
- end: `0x14001c272`
- name: `WinHvpInitializeHypercallLookasideBuffer`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14002a364`

## callees

- `0x14000b008`
- `0x14001c140`
- `0x14001d65c`
- `0x14001d8c8`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c240`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c240`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001c222`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001c222`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001c20c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001c20c`

## pseudocode

```c
__int64 WinHvpInitializeHypercallLookasideBuffer()
{
  unsigned int v0; // ebx
  unsigned __int8 i; // di
  unsigned __int64 v2; // rsi
  PVOID v3; // rax

  WinHvpNodeInfo = WinHvpAllocatePool(64, 40LL * (unsigned int)WinHvpNodeCount, 1182156887);
  if ( !WinHvpNodeInfo )
    return (unsigned int)-1073741670;
  if ( WinHvpVmManagement )
    WinHvpLoadProximityDomainInfo();
  WinHvpNodeToHypercallLookaside = WinHvpAllocatePool(
                                     66,
                                     (unsigned __int64)(unsigned int)WinHvpNodeCount << 7,
                                     1282820183);
  if ( !WinHvpNodeToHypercallLookaside )
  {
    WinHvpTeardownNodeInfo();
    return (unsigned int)-1073741670;
  }
  v0 = 0;
  for ( i = 0; i < (unsigned int)WinHvpNodeCount; ++i )
  {
    v2 = (unsigned __int64)i << 7;
    ExInitializeNPagedLookasideList(
      (PNPAGED_LOOKASIDE_LIST)(v2 + WinHvpNodeToHypercallLookaside),
      WinHvpAllocateHypercallBuffer,
      WinHvpFreeHypercallBuffer,
      0x200u,
      0x30u,
      i,
      0);
    v3 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v2 + WinHvpNodeToHypercallLookaside));
    if ( v3 )
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v2 + WinHvpNodeToHypercallLookaside), v3);
  }
  return v0;
}

```

## disassembly

```asm
0x14001c140  mov     [rsp+arg_0], rbx
0x14001c145  mov     [rsp+arg_8], rsi
0x14001c14a  push    rdi
0x14001c14b  sub     rsp, 40h
0x14001c14f  mov     eax, cs:WinHvpNodeCount
0x14001c155  mov     ecx, 40h ; '@'
0x14001c15a  mov     r8d, 46764857h
0x14001c160  lea     rdx, [rax+rax*4]
0x14001c164  shl     rdx, 3
0x14001c168  call    WinHvpAllocatePool
0x14001c16d  mov     cs:WinHvpNodeInfo, rax
0x14001c174  test    rax, rax
0x14001c177  jz      short loc_14001C1B2
0x14001c179  cmp     cs:WinHvpVmManagement, 0
0x14001c180  jz      short loc_14001C187
0x14001c182  call    WinHvpLoadProximityDomainInfo
0x14001c187  mov     edx, cs:WinHvpNodeCount
0x14001c18d  mov     ecx, 42h ; 'B'
0x14001c192  shl     rdx, 7
0x14001c196  mov     r8d, 4C764857h
0x14001c19c  call    WinHvpAllocatePool
0x14001c1a1  mov     cs:WinHvpNodeToHypercallLookaside, rax
0x14001c1a8  test    rax, rax
0x14001c1ab  jnz     short loc_14001C1BC
0x14001c1ad  call    WinHvpTeardownNodeInfo
0x14001c1b2  mov     ebx, 0C000009Ah
0x14001c1b7  jmp     loc_14001C25F
0x14001c1bc  xor     ebx, ebx
0x14001c1be  xor     dil, dil
0x14001c1c1  cmp     cs:WinHvpNodeCount, ebx
0x14001c1c7  jbe     loc_14001C25F
0x14001c1cd  mov     rcx, cs:WinHvpNodeToHypercallLookaside
0x14001c1d4  xor     edx, edx
0x14001c1d6  mov     [rsp+48h+Depth], dx; Depth
0x14001c1db  mov     r9d, 200h; Flags
0x14001c1e1  movzx   r8d, dil
0x14001c1e5  lea     rdx, WinHvpAllocateHypercallBuffer; Allocate
0x14001c1ec  mov     [rsp+48h+Tag], r8d; Tag
0x14001c1f1  lea     r8, WinHvpFreeHypercallBuffer; Free
0x14001c1f8  movzx   esi, dil
0x14001c1fc  shl     rsi, 7
0x14001c200  add     rcx, rsi; Lookaside
0x14001c203  mov     [rsp+48h+Size], 30h ; '0'; Size
0x14001c20c  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001c213  nop     dword ptr [rax+rax+00h]
0x14001c218  mov     rcx, cs:WinHvpNodeToHypercallLookaside
0x14001c21f  add     rcx, rsi; Lookaside
0x14001c222  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001c229  nop     dword ptr [rax+rax+00h]
0x14001c22e  test    rax, rax
0x14001c231  jz      short loc_14001C24C
0x14001c233  mov     rcx, cs:WinHvpNodeToHypercallLookaside
0x14001c23a  mov     rdx, rax; Entry
0x14001c23d  add     rcx, rsi; Lookaside
0x14001c240  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001c247  nop     dword ptr [rax+rax+00h]
0x14001c24c  inc     dil
0x14001c24f  movzx   ecx, dil
0x14001c253  cmp     ecx, cs:WinHvpNodeCount
0x14001c259  jb      loc_14001C1CD
0x14001c25f  mov     rsi, [rsp+48h+arg_8]
0x14001c264  mov     eax, ebx
0x14001c266  mov     rbx, [rsp+48h+arg_0]
0x14001c26b  add     rsp, 40h
0x14001c26f  pop     rdi
0x14001c270  retn
```
