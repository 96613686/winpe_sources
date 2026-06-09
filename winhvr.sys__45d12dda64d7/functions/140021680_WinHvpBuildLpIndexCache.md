# WinHvpBuildLpIndexCache

- ea: `0x140021680`
- end: `0x14002185d`
- name: `WinHvpBuildLpIndexCache`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x14002a678`

## callees

- `0x140002240`
- `0x140003610`
- `0x1400045b0`
- `0x140009c50`
- `0x140009c90`
- `0x14000a040`
- `0x14000b008`
- `0x140021680`
- `0x140021864`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14002172c`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14002172c`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140021795`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140021795`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140021821`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140021821`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14002176b`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14002176b`

## pseudocode

```c
__int64 WinHvpBuildLpIndexCache()
{
  char v0; // r15
  unsigned int v1; // ebx
  int v2; // edi
  struct _GROUP_AFFINITY *p_PreviousAffinity; // r14
  ULONG ActiveProcessorCount; // eax
  __int64 v5; // r13
  __int64 v6; // rbx
  unsigned int v7; // r12d
  __int64 v8; // rsi
  struct _PROCESSOR_NUMBER ProcNumber[2]; // [rsp+20h] [rbp-69h] BYREF
  _DWORD *v11; // [rsp+28h] [rbp-61h] BYREF
  _QWORD v12[8]; // [rsp+30h] [rbp-59h] BYREF
  struct _GROUP_AFFINITY Affinity; // [rsp+70h] [rbp-19h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+80h] [rbp-9h] BYREF

  memset(v12, 0, sizeof(v12));
  v11 = 0;
  *(_QWORD *)&ProcNumber[0].Group = 0;
  v0 = 0;
  v1 = 8 * WinHvpMaximumProcessorCount;
  Affinity = 0;
  PreviousAffinity = 0;
  WinHvpSetupHypercall(&v11, ProcNumber, v12);
  WinHvpProcessorToLpIndex = WinHvpAllocatePool(64, v1, 1433815127);
  if ( WinHvpProcessorToLpIndex )
  {
    p_PreviousAffinity = &PreviousAffinity;
    ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
    v5 = *(_QWORD *)&ProcNumber[0].Group;
    v6 = 0;
    v7 = ActiveProcessorCount;
    while ( (unsigned int)v6 < v7 )
    {
      if ( WinHvpCpuManagement )
      {
        ProcNumber[0] = 0;
        Affinity = 0;
        KeGetProcessorNumberFromIndex(v6, ProcNumber);
        Affinity.Group = ProcNumber[0].Group;
        Affinity.Mask = 1LL << ProcNumber[0].Number;
        KeSetSystemGroupAffinityThread(&Affinity, p_PreviousAffinity);
        v0 = 1;
        *v11 = -2;
        v2 = WinHvpSimplePoolHypercall_CallViaMacro(v12[0], 138);
        if ( v2 < 0 )
          goto LABEL_3;
        v8 = 8 * v6;
        p_PreviousAffinity = 0;
        *(_DWORD *)(8 * v6 + WinHvpProcessorToLpIndex) = *(unsigned __int16 *)(v5 + 4);
      }
      else
      {
        v8 = 8 * v6;
        v2 = WinHvNtProcessorToVpIndex((unsigned int)v6, 8 * v6 + WinHvpProcessorToLpIndex);
        if ( v2 < 0 )
          goto LABEL_3;
      }
      v6 = (unsigned int)(v6 + 1);
      *(_BYTE *)(v8 + WinHvpProcessorToLpIndex + 4) = 1;
    }
    v2 = 0;
  }
  else
  {
    v2 = -1073741670;
LABEL_3:
    WinHvpTeardownLpIndexCache();
  }
  if ( v0 )
    KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  ((void (__fastcall *)(_QWORD))v12[7])(v12[0]);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140021680  push    rbp
0x140021682  push    rbx
0x140021683  push    rsi
0x140021684  push    rdi
0x140021685  push    r12
0x140021687  push    r13
0x140021689  push    r14
0x14002168b  push    r15
0x14002168d  lea     rbp, [rsp-1Fh]
0x140021692  sub     rsp, 0A8h
0x140021699  mov     rax, cs:__security_cookie
0x1400216a0  xor     rax, rsp
0x1400216a3  mov     [rbp+57h+var_50], rax
0x1400216a7  mov     edi, 40h ; '@'
0x1400216ac  lea     rcx, [rbp+57h+var_B0]; void *
0x1400216b0  mov     r8d, edi; Size
0x1400216b3  xor     edx, edx; Val
0x1400216b5  call    memset
0x1400216ba  mov     eax, cs:WinHvpMaximumProcessorCount
0x1400216c0  lea     r8, [rbp+57h+var_B0]
0x1400216c4  xorps   xmm0, xmm0
0x1400216c7  mov     [rbp+57h+var_B8], 0
0x1400216cf  xorps   xmm1, xmm1
0x1400216d2  mov     qword ptr [rbp+57h+ProcNumber.Group], 0
0x1400216da  lea     rdx, [rbp+57h+ProcNumber]
0x1400216de  xor     r15b, r15b
0x1400216e1  lea     rcx, [rbp+57h+var_B8]
0x1400216e5  lea     ebx, ds:0[rax*8]
0x1400216ec  movups  xmmword ptr [rbp+57h+Affinity.Mask], xmm0
0x1400216f0  movups  xmmword ptr [rbp+57h+PreviousAffinity.Mask], xmm1
0x1400216f4  call    WinHvpSetupHypercall
0x1400216f9  mov     edx, ebx
0x1400216fb  mov     r8d, 55764857h
0x140021701  mov     ecx, edi
0x140021703  call    WinHvpAllocatePool
0x140021708  mov     cs:WinHvpProcessorToLpIndex, rax
0x14002170f  test    rax, rax
0x140021712  jnz     short loc_140021723
0x140021714  mov     edi, 0C000009Ah
0x140021719  call    WinHvpTeardownLpIndexCache
0x14002171e  jmp     loc_140021818
0x140021723  mov     ecx, 0FFFFh; GroupNumber
0x140021728  lea     r14, [rbp+57h+PreviousAffinity]
0x14002172c  call    cs:__imp_KeQueryActiveProcessorCountEx
0x140021733  nop     dword ptr [rax+rax+00h]
0x140021738  mov     r13, qword ptr [rbp+57h+ProcNumber.Group]
0x14002173c  xor     ebx, ebx
0x14002173e  mov     r12d, eax
0x140021741  cmp     ebx, r12d
0x140021744  jnb     loc_140021816
0x14002174a  cmp     cs:WinHvpCpuManagement, 0
0x140021751  mov     ecx, ebx; ProcIndex
0x140021753  jz      loc_1400217E2
0x140021759  xorps   xmm0, xmm0
0x14002175c  mov     dword ptr [rbp+57h+ProcNumber.Group], 0
0x140021763  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x140021767  movups  xmmword ptr [rbp+57h+Affinity.Mask], xmm0
0x14002176b  call    cs:__imp_KeGetProcessorNumberFromIndex
0x140021772  nop     dword ptr [rax+rax+00h]
0x140021777  movzx   eax, [rbp+57h+ProcNumber.Group]
0x14002177b  mov     rdx, r14; PreviousAffinity
0x14002177e  mov     cl, [rbp+57h+ProcNumber.Number]
0x140021781  mov     [rbp+57h+Affinity.Group], ax
0x140021785  mov     eax, 1
0x14002178a  shl     rax, cl
0x14002178d  lea     rcx, [rbp+57h+Affinity]; Affinity
0x140021791  mov     [rbp+57h+Affinity.Mask], rax
0x140021795  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14002179c  nop     dword ptr [rax+rax+00h]
0x1400217a1  mov     rax, [rbp+57h+var_B8]
0x1400217a5  mov     edx, 8Ah
0x1400217aa  mov     r15b, 1
0x1400217ad  mov     dword ptr [rax], 0FFFFFFFEh
0x1400217b3  mov     rcx, [rbp+57h+var_B0]
0x1400217b7  call    WinHvpSimplePoolHypercall_CallViaMacro
0x1400217bc  mov     edi, eax
0x1400217be  test    eax, eax
0x1400217c0  js      loc_140021719
0x1400217c6  mov     rax, cs:WinHvpProcessorToLpIndex
0x1400217cd  lea     rsi, ds:0[rbx*8]
0x1400217d5  movzx   ecx, word ptr [r13+4]
0x1400217da  xor     r14d, r14d
0x1400217dd  mov     [rsi+rax], ecx
0x1400217e0  jmp     short loc_140021803
0x1400217e2  mov     rdx, cs:WinHvpProcessorToLpIndex
0x1400217e9  lea     rsi, ds:0[rbx*8]
0x1400217f1  add     rdx, rsi
0x1400217f4  call    WinHvNtProcessorToVpIndex
0x1400217f9  mov     edi, eax
0x1400217fb  test    eax, eax
0x1400217fd  js      loc_140021719
0x140021803  mov     rax, cs:WinHvpProcessorToLpIndex
0x14002180a  inc     ebx
0x14002180c  mov     byte ptr [rsi+rax+4], 1
0x140021811  jmp     loc_140021741
0x140021816  xor     edi, edi
0x140021818  test    r15b, r15b
0x14002181b  jz      short loc_14002182D
0x14002181d  lea     rcx, [rbp+57h+PreviousAffinity]; PreviousAffinity
0x140021821  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140021828  nop     dword ptr [rax+rax+00h]
0x14002182d  mov     rcx, [rbp+57h+var_B0]
0x140021831  mov     rax, [rbp+57h+var_78]
0x140021835  call    _guard_dispatch_icall
0x14002183a  mov     eax, edi
0x14002183c  mov     rcx, [rbp+57h+var_50]
0x140021840  xor     rcx, rsp; StackCookie
0x140021843  call    __security_check_cookie
0x140021848  add     rsp, 0A8h
0x14002184f  pop     r15
0x140021851  pop     r14
0x140021853  pop     r13
0x140021855  pop     r12
0x140021857  pop     rdi
0x140021858  pop     rsi
0x140021859  pop     rbx
0x14002185a  pop     rbp
0x14002185b  retn
```
