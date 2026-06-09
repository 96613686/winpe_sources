# WinHvpCreateVpObject

- ea: `0x1400226bc`
- end: `0x1400227a0`
- name: `WinHvpCreateVpObject`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14001d900`

## callees

- `0x1400042dc`
- `0x140008df4`
- `0x140009c50`
- `0x14000b008`
- `0x14001b084`
- `0x1400226bc`

## import_xrefs

- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140022708`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140022708`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14002277b`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14002277b`

## pseudocode

```c
__int64 __fastcall WinHvpCreateVpObject(__int64 a1, int a2, int a3)
{
  char v3; // si
  unsigned int v4; // r8d
  __int64 Pool; // rax
  __int64 v8; // rdi
  int v9; // ebx
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+20h] [rbp-48h] BYREF

  v3 = 0;
  v4 = a3 & 0x7FFFFFFF;
  PreviousAffinity = 0;
  if ( v4 < WinHvpNodeCount )
  {
    KeSetSystemGroupAffinityThread((PGROUP_AFFINITY)&WinHvpNodeToProcessorMask[2 * v4], &PreviousAffinity);
    v3 = 1;
  }
  Pool = WinHvpAllocatePool(64, 224, 1467369559);
  v8 = Pool;
  if ( Pool )
  {
    *(_QWORD *)Pool = a1;
    *(_DWORD *)(Pool + 8) = a2;
    *(_QWORD *)(Pool + 16) = 1;
    v9 = WinHvpInitializeVpDispatchContext(Pool);
    if ( v9 < 0 || (v9 = WinHvpAddVpToPartition(v8), v9 < 0) )
      WinHvpDereferenceVp(v8);
    else
      v9 = 0;
  }
  else
  {
    v9 = -1073741670;
  }
  if ( v3 )
    KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400226bc  push    rbx
0x1400226be  push    rbp
0x1400226bf  push    rsi
0x1400226c0  push    rdi
0x1400226c1  sub     rsp, 48h
0x1400226c5  mov     rax, cs:__security_cookie
0x1400226cc  xor     rax, rsp
0x1400226cf  mov     [rsp+68h+var_38], rax
0x1400226d4  xor     sil, sil
0x1400226d7  btr     r8d, 1Fh
0x1400226dc  cmp     r8d, cs:WinHvpNodeCount
0x1400226e3  xorps   xmm0, xmm0
0x1400226e6  mov     ebx, edx
0x1400226e8  mov     rbp, rcx
0x1400226eb  movups  xmmword ptr [rsp+68h+PreviousAffinity.Mask], xmm0
0x1400226f0  jnb     short loc_140022717
0x1400226f2  mov     ecx, r8d
0x1400226f5  lea     rax, WinHvpNodeToProcessorMask
0x1400226fc  shl     rcx, 4
0x140022700  lea     rdx, [rsp+68h+PreviousAffinity]; PreviousAffinity
0x140022705  add     rcx, rax; Affinity
0x140022708  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14002270f  nop     dword ptr [rax+rax+00h]
0x140022714  mov     sil, 1
0x140022717  mov     edx, 0E0h
0x14002271c  mov     ecx, 40h ; '@'
0x140022721  mov     r8d, 57764857h
0x140022727  call    WinHvpAllocatePool
0x14002272c  mov     rdi, rax
0x14002272f  test    rax, rax
0x140022732  jnz     short loc_14002273B
0x140022734  mov     ebx, 0C000009Ah
0x140022739  jmp     short loc_140022771
0x14002273b  mov     rcx, rdi
0x14002273e  mov     [rax], rbp
0x140022741  mov     [rax+8], ebx
0x140022744  mov     qword ptr [rax+10h], 1
0x14002274c  call    WinHvpInitializeVpDispatchContext
0x140022751  mov     ebx, eax
0x140022753  test    eax, eax
0x140022755  js      short loc_140022769
0x140022757  mov     rcx, rdi
0x14002275a  call    WinHvpAddVpToPartition
0x14002275f  mov     ebx, eax
0x140022761  test    eax, eax
0x140022763  js      short loc_140022769
0x140022765  xor     ebx, ebx
0x140022767  jmp     short loc_140022771
0x140022769  mov     rcx, rdi
0x14002276c  call    WinHvpDereferenceVp
0x140022771  test    sil, sil
0x140022774  jz      short loc_140022787
0x140022776  lea     rcx, [rsp+68h+PreviousAffinity]; PreviousAffinity
0x14002277b  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140022782  nop     dword ptr [rax+rax+00h]
0x140022787  mov     eax, ebx
0x140022789  mov     rcx, [rsp+68h+var_38]
0x14002278e  xor     rcx, rsp; StackCookie
0x140022791  call    __security_check_cookie
0x140022796  add     rsp, 48h
0x14002279a  pop     rdi
0x14002279b  pop     rsi
0x14002279c  pop     rbp
0x14002279d  pop     rbx
0x14002279e  retn
```
