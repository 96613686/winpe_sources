# WinHvpBuildVpIndexCache

- ea: `0x14001e11c`
- end: `0x14001e23c`
- name: `WinHvpBuildVpIndexCache`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002a678`

## callees

- `0x140006af0`
- `0x140009c50`
- `0x14000b008`
- `0x14001e11c`
- `0x14001e244`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14001e184`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14001e184`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001e1da`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001e1da`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001e214`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001e214`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14001e1b0`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14001e1b0`

## pseudocode

```c
__int64 WinHvpBuildVpIndexCache()
{
  __int64 v0; // rbx
  struct _GROUP_AFFINITY *p_PreviousAffinity; // r14
  ULONG ActiveProcessorCount; // edi
  struct _PROCESSOR_NUMBER ProcNumber; // [rsp+20h] [rbp-30h] BYREF
  struct _GROUP_AFFINITY Affinity; // [rsp+28h] [rbp-28h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+38h] [rbp-18h] BYREF

  Affinity = 0;
  PreviousAffinity = 0;
  WinHvpProcessorToVpIndex = WinHvpAllocatePool(64, 8LL * (unsigned int)WinHvpMaximumProcessorCount, 1433815127);
  if ( WinHvpProcessorToVpIndex )
  {
    p_PreviousAffinity = &PreviousAffinity;
    v0 = 0;
    ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
    if ( ActiveProcessorCount )
    {
      do
      {
        ProcNumber = 0;
        Affinity = 0;
        KeGetProcessorNumberFromIndex(v0, &ProcNumber);
        Affinity.Group = ProcNumber.Group;
        Affinity.Mask = 1LL << ProcNumber.Number;
        KeSetSystemGroupAffinityThread(&Affinity, p_PreviousAffinity);
        p_PreviousAffinity = 0;
        if ( (int)WinHvGetCurrentVpIndex(WinHvpProcessorToVpIndex + 8 * v0) >= 0 )
          *(_BYTE *)(WinHvpProcessorToVpIndex + 8 * v0 + 4) = 1;
        v0 = (unsigned int)(v0 + 1);
      }
      while ( (unsigned int)v0 < ActiveProcessorCount );
      KeRevertToUserGroupAffinityThread(&PreviousAffinity);
      LODWORD(v0) = 0;
    }
  }
  else
  {
    LODWORD(v0) = -1073741670;
    WinHvpTeardownVpIndexCache();
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14001e11c  push    rbp
0x14001e11e  push    rbx
0x14001e11f  push    rsi
0x14001e120  push    rdi
0x14001e121  push    r14
0x14001e123  mov     rbp, rsp
0x14001e126  sub     rsp, 50h
0x14001e12a  mov     rax, cs:__security_cookie
0x14001e131  xor     rax, rsp
0x14001e134  mov     [rbp+var_8], rax
0x14001e138  mov     edx, cs:WinHvpMaximumProcessorCount
0x14001e13e  xorps   xmm0, xmm0
0x14001e141  xorps   xmm1, xmm1
0x14001e144  shl     rdx, 3
0x14001e148  mov     ecx, 40h ; '@'
0x14001e14d  mov     r8d, 55764857h
0x14001e153  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14001e157  movups  xmmword ptr [rbp+PreviousAffinity.Mask], xmm1
0x14001e15b  call    WinHvpAllocatePool
0x14001e160  mov     cs:WinHvpProcessorToVpIndex, rax
0x14001e167  test    rax, rax
0x14001e16a  jnz     short loc_14001E17B
0x14001e16c  mov     ebx, 0C000009Ah
0x14001e171  call    WinHvpTeardownVpIndexCache
0x14001e176  jmp     loc_14001E222
0x14001e17b  mov     ecx, 0FFFFh; GroupNumber
0x14001e180  lea     r14, [rbp+PreviousAffinity]
0x14001e184  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14001e18b  nop     dword ptr [rax+rax+00h]
0x14001e190  xor     ebx, ebx
0x14001e192  mov     edi, eax
0x14001e194  test    eax, eax
0x14001e196  jz      loc_14001E222
0x14001e19c  xorps   xmm0, xmm0
0x14001e19f  mov     dword ptr [rbp+ProcNumber.Group], 0
0x14001e1a6  lea     rdx, [rbp+ProcNumber]; ProcNumber
0x14001e1aa  mov     ecx, ebx; ProcIndex
0x14001e1ac  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14001e1b0  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14001e1b7  nop     dword ptr [rax+rax+00h]
0x14001e1bc  movzx   eax, [rbp+ProcNumber.Group]
0x14001e1c0  mov     rdx, r14; PreviousAffinity
0x14001e1c3  mov     cl, [rbp+ProcNumber.Number]
0x14001e1c6  mov     [rbp+Affinity.Group], ax
0x14001e1ca  mov     eax, 1
0x14001e1cf  shl     rax, cl
0x14001e1d2  lea     rcx, [rbp+Affinity]; Affinity
0x14001e1d6  mov     [rbp+Affinity.Mask], rax
0x14001e1da  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14001e1e1  nop     dword ptr [rax+rax+00h]
0x14001e1e6  mov     rax, cs:WinHvpProcessorToVpIndex
0x14001e1ed  xor     r14d, r14d
0x14001e1f0  lea     rcx, [rax+rbx*8]
0x14001e1f4  call    WinHvGetCurrentVpIndex
0x14001e1f9  test    eax, eax
0x14001e1fb  js      short loc_14001E20A
0x14001e1fd  nop
0x14001e1fe  mov     rax, cs:WinHvpProcessorToVpIndex
0x14001e205  mov     byte ptr [rax+rbx*8+4], 1
0x14001e20a  inc     ebx
0x14001e20c  cmp     ebx, edi
0x14001e20e  jb      short loc_14001E19C
0x14001e210  lea     rcx, [rbp+PreviousAffinity]; PreviousAffinity
0x14001e214  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14001e21b  nop     dword ptr [rax+rax+00h]
0x14001e220  xor     ebx, ebx
0x14001e222  mov     eax, ebx
0x14001e224  mov     rcx, [rbp+var_8]
0x14001e228  xor     rcx, rsp; StackCookie
0x14001e22b  call    __security_check_cookie
0x14001e230  add     rsp, 50h
0x14001e234  pop     r14
0x14001e236  pop     rdi
0x14001e237  pop     rsi
0x14001e238  pop     rbx
0x14001e239  pop     rbp
0x14001e23a  retn
```
