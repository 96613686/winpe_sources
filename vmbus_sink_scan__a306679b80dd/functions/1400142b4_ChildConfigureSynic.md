# ChildConfigureSynic

- ea: `0x1400142b4`
- end: `0x140014481`
- name: `ChildConfigureSynic`
- size: `461`
- prototype: `void()`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140013934`
- `0x14001491c`

## callees

- `0x1400142b4`
- `0x140017000`
- `0x140017540`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400143ac`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400143ac`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140014316`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400143fe`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140014316`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400143fe`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140014378`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140014459`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140014378`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140014459`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400143d7`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400143d7`
- `winhv!WinHvGetSintMessage2` at `0x140014334`
- `winhv!WinHvGetSintMessage2` at `0x140014368`
- `winhv!WinHvGetSintMessage2` at `0x140014334`
- `winhv!WinHvGetSintMessage2` at `0x140014368`
- `winhv!WinHvGetSintEventFlags` at `0x14001440d`
- `winhv!WinHvGetSintEventFlags` at `0x14001440d`
- `winhv!WinHvSetSint2` at `0x14001443e`
- `winhv!WinHvSetSint2` at `0x14001443e`

## pseudocode

```c
void ChildConfigureSynic()
{
  unsigned int v0; // ebx
  unsigned int v1; // edi
  int v2; // eax
  __int64 v3; // rdi
  ULONG ActiveProcessorCount; // esi
  void *SintEventFlags; // rax
  struct _PROCESSOR_NUMBER ProcNumber; // [rsp+20h] [rbp-40h] BYREF
  struct _GROUP_AFFINITY v7; // [rsp+28h] [rbp-38h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+38h] [rbp-28h] BYREF
  struct _GROUP_AFFINITY Affinity; // [rsp+48h] [rbp-18h] BYREF

  ProcNumber = 0;
  v7 = 0;
  PreviousAffinity = 0;
  if ( dword_140020870 == 1 )
  {
    v0 = 4;
    v1 = 1;
  }
  else
  {
    v0 = 0;
    v1 = 0;
  }
  *(_QWORD *)&Affinity.Group = 0;
  Affinity.Mask = 1;
  KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
  WinHvGetSintMessage2(2, v1, &qword_140020810);
  if ( !qword_140020810 && dword_140020870 == 1 )
  {
    v0 = 0;
    dword_140020870 = 2;
    WinHvGetSintMessage2(2, 0, &qword_140020810);
  }
  KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  if ( (dword_14002081C & 1) != 0 )
  {
    v2 = dword_14002081C | 1;
  }
  else
  {
    v0 |= 2u;
    v2 = dword_14002081C & 0xFFFFFFFE;
  }
  dword_14002081C = v2;
  v7 = 0;
  v3 = 0;
  ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
  if ( ActiveProcessorCount )
  {
    do
    {
      if ( *(_BYTE *)(v3 + qword_1400207F8) )
      {
        KeGetProcessorNumberFromIndex(v3, &ProcNumber);
        v7.Group = ProcNumber.Group;
        v7.Mask = 1LL << ProcNumber.Number;
        KeSetSystemGroupAffinityThread(&v7, 0);
        SintEventFlags = (void *)WinHvGetSintEventFlags(2);
        memset(SintEventFlags, 0, 0x100u);
        WinHvSetSint2(2, *(unsigned __int8 *)(v3 + qword_1400207F8), &v7, v0);
      }
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < ActiveProcessorCount );
  }
  KeRevertToUserGroupAffinityThread(&PreviousAffinity);
}

```

## disassembly

```asm
0x1400142b4  push    rbp
0x1400142b6  push    rbx
0x1400142b7  push    rsi
0x1400142b8  push    rdi
0x1400142b9  push    r12
0x1400142bb  push    r13
0x1400142bd  push    r14
0x1400142bf  mov     rbp, rsp
0x1400142c2  sub     rsp, 60h
0x1400142c6  mov     rax, cs:__security_cookie
0x1400142cd  xor     rax, rsp
0x1400142d0  mov     [rbp+var_8], rax
0x1400142d4  mov     r12d, 1
0x1400142da  mov     dword ptr [rbp+ProcNumber.Group], 0
0x1400142e1  cmp     cs:dword_140020870, r12d
0x1400142e8  xorps   xmm0, xmm0
0x1400142eb  xorps   xmm1, xmm1
0x1400142ee  movups  xmmword ptr [rbp+var_38.Mask], xmm0
0x1400142f2  movups  xmmword ptr [rbp+PreviousAffinity.Mask], xmm1
0x1400142f6  jnz     short loc_140014302
0x1400142f8  lea     ebx, [r12+3]
0x1400142fd  mov     edi, r12d
0x140014300  jmp     short loc_140014306
0x140014302  xor     ebx, ebx
0x140014304  xor     edi, edi
0x140014306  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14001430a  lea     rdx, [rbp+PreviousAffinity]; PreviousAffinity
0x14001430e  mov     [rbp+Affinity.Mask], r12
0x140014312  lea     rcx, [rbp+Affinity]; Affinity
0x140014316  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14001431d  nop     dword ptr [rax+rax+00h]
0x140014322  mov     r13d, 2
0x140014328  lea     r8, qword_140020810
0x14001432f  mov     ecx, r13d
0x140014332  mov     edx, edi
0x140014334  call    cs:__imp_WinHvGetSintMessage2
0x14001433b  nop     dword ptr [rax+rax+00h]
0x140014340  cmp     cs:qword_140020810, 0
0x140014348  jnz     short loc_140014374
0x14001434a  cmp     cs:dword_140020870, r12d
0x140014351  jnz     short loc_140014374
0x140014353  xor     ebx, ebx
0x140014355  mov     cs:dword_140020870, r13d
0x14001435c  lea     r8, qword_140020810
0x140014363  xor     edx, edx
0x140014365  mov     ecx, r13d
0x140014368  call    cs:__imp_WinHvGetSintMessage2
0x14001436f  nop     dword ptr [rax+rax+00h]
0x140014374  lea     rcx, [rbp+PreviousAffinity]; PreviousAffinity
0x140014378  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14001437f  nop     dword ptr [rax+rax+00h]
0x140014384  mov     eax, cs:dword_14002081C
0x14001438a  test    r12b, al
0x14001438d  jnz     short loc_140014397
0x14001438f  or      ebx, r13d
0x140014392  and     eax, 0FFFFFFFEh
0x140014395  jmp     short loc_14001439A
0x140014397  or      eax, r12d
0x14001439a  xorps   xmm0, xmm0
0x14001439d  mov     cs:dword_14002081C, eax
0x1400143a3  mov     ecx, 0FFFFh; GroupNumber
0x1400143a8  movups  xmmword ptr [rbp+var_38.Mask], xmm0
0x1400143ac  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1400143b3  nop     dword ptr [rax+rax+00h]
0x1400143b8  xor     edi, edi
0x1400143ba  mov     esi, eax
0x1400143bc  test    eax, eax
0x1400143be  jz      loc_140014455
0x1400143c4  mov     rcx, cs:qword_1400207F8
0x1400143cb  cmp     byte ptr [rdi+rcx], 0
0x1400143cf  jz      short loc_14001444A
0x1400143d1  lea     rdx, [rbp+ProcNumber]; ProcNumber
0x1400143d5  mov     ecx, edi; ProcIndex
0x1400143d7  call    cs:__imp_KeGetProcessorNumberFromIndex
0x1400143de  nop     dword ptr [rax+rax+00h]
0x1400143e3  movzx   eax, [rbp+ProcNumber.Group]
0x1400143e7  xor     edx, edx; PreviousAffinity
0x1400143e9  mov     cl, [rbp+ProcNumber.Number]
0x1400143ec  mov     [rbp+var_38.Group], ax
0x1400143f0  mov     rax, r12
0x1400143f3  shl     rax, cl
0x1400143f6  lea     rcx, [rbp+var_38]; Affinity
0x1400143fa  mov     [rbp+var_38.Mask], rax
0x1400143fe  call    cs:__imp_KeSetSystemGroupAffinityThread
0x140014405  nop     dword ptr [rax+rax+00h]
0x14001440a  mov     ecx, r13d
0x14001440d  call    cs:__imp_WinHvGetSintEventFlags
0x140014414  nop     dword ptr [rax+rax+00h]
0x140014419  xor     edx, edx; Val
0x14001441b  mov     r8d, 100h; Size
0x140014421  mov     rcx, rax; void *
0x140014424  call    memset
0x140014429  mov     rax, cs:qword_1400207F8
0x140014430  lea     r8, [rbp+var_38]
0x140014434  mov     r9d, ebx
0x140014437  mov     ecx, r13d
0x14001443a  movzx   edx, byte ptr [rdi+rax]
0x14001443e  call    cs:__imp_WinHvSetSint2
0x140014445  nop     dword ptr [rax+rax+00h]
0x14001444a  add     edi, r12d
0x14001444d  cmp     edi, esi
0x14001444f  jb      loc_1400143C4
0x140014455  lea     rcx, [rbp+PreviousAffinity]; PreviousAffinity
0x140014459  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140014460  nop     dword ptr [rax+rax+00h]
0x140014465  mov     rcx, [rbp+var_8]
0x140014469  xor     rcx, rsp; StackCookie
0x14001446c  call    __security_check_cookie
0x140014471  add     rsp, 60h
0x140014475  pop     r14
0x140014477  pop     r13
0x140014479  pop     r12
0x14001447b  pop     rdi
0x14001447c  pop     rsi
0x14001447d  pop     rbx
0x14001447e  pop     rbp
0x14001447f  retn
```
