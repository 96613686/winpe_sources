# VidCpuGroupIoctlCreate

- ea: `0x140082818`
- end: `0x14008299a`
- name: `VidCpuGroupIoctlCreate`
- size: `386`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x14003782c`

## callees

- `0x140011518`
- `0x14002f724`
- `0x1400769d8`
- `0x140082818`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400828cf`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400828cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082977`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082977`
- `ntoskrnl!ExAllocatePool2` at `0x140082887`
- `ntoskrnl!ExAllocatePool2` at `0x140082887`
- `winhvr!WinHvCreateCpuGroup` at `0x1400828f4`
- `winhvr!WinHvCreateCpuGroup` at `0x1400828f4`

## string_xrefs

- `0x140082861`: `VidCpuGroupIoctlCreate`
- `0x1400828b3`: `VidCpuGroupIoctlCreate`
- `0x140082916`: `VidCpuGroupIoctlCreate`
- `0x140082936`: `VidCpuGroupIoctlCreate`
- `0x14008295e`: `VidCpuGroupIoctlCreate`

## pseudocode

```c
__int64 __fastcall VidCpuGroupIoctlCreate(void *Src, unsigned int a2, __int64 a3)
{
  __int64 v4; // r14
  void *Pool2; // rdi
  unsigned int v7; // ebx
  int CpuGroup; // eax

  v4 = a2;
  Pool2 = 0;
  if ( a2 - 1 > 0x7FF )
  {
    v7 = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidCpuGroupIoctlCreate",
      "onecore\\vm\\vid\\sys\\driver\\vidcpugroup.c",
      86,
      3221225485LL);
  }
  else if ( (int)VidSidServiceCheck() >= 0 )
  {
    Pool2 = (void *)ExAllocatePool2(65, 4 * v4, 1917084758);
    if ( Pool2 )
    {
      if ( 4 * v4 && ((unsigned __int8)Src & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(Pool2, Src, 4 * v4);
      CpuGroup = WinHvCreateCpuGroup(Pool2, (unsigned int)v4, a3);
      v7 = CpuGroup;
      if ( CpuGroup < 0 )
        VidTraceErrorStatusInternal0(
          "VidCpuGroupIoctlCreate",
          "onecore\\vm\\vid\\sys\\driver\\vidcpugroup.c",
          137,
          (unsigned int)CpuGroup);
    }
    else
    {
      v7 = -1073741670;
      VidTraceErrorStatusInternal0(
        "VidCpuGroupIoctlCreate",
        "onecore\\vm\\vid\\sys\\driver\\vidcpugroup.c",
        109,
        3221225626LL);
    }
  }
  else
  {
    v7 = -1073741727;
    VidTraceErrorStatusInternal0(
      "VidCpuGroupIoctlCreate",
      "onecore\\vm\\vid\\sys\\driver\\vidcpugroup.c",
      94,
      3221225569LL);
  }
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x72446456u);
  return v7;
}

```

## disassembly

```asm
0x140082818  mov     [rsp+arg_0], rbx
0x14008281d  mov     [rsp+arg_8], rsi
0x140082822  push    rdi
0x140082823  push    r14
0x140082825  push    r15
0x140082827  sub     rsp, 20h
0x14008282b  mov     r15, r8
0x14008282e  mov     r14d, edx
0x140082831  mov     rsi, rcx
0x140082834  xor     edi, edi
0x140082836  lea     eax, [r14-1]
0x14008283a  cmp     eax, 7FFh
0x14008283f  ja      loc_140082949
0x140082845  call    VidSidServiceCheck
0x14008284a  test    eax, eax
0x14008284c  jns     short loc_140082872
0x14008284e  mov     ebx, 0C0000061h
0x140082853  mov     r9d, ebx
0x140082856  lea     r8d, [rdi+5Eh]
0x14008285a  lea     rdx, aOnecoreVmVidSy_32; "onecore\\vm\\vid\\sys\\driver\\vidcpugr"...
0x140082861  lea     rcx, aVidcpugroupioc_0; "VidCpuGroupIoctlCreate"
0x140082868  call    VidTraceErrorStatusInternal0
0x14008286d  jmp     loc_14008296A
0x140082872  mov     rbx, r14
0x140082875  shl     rbx, 2
0x140082879  mov     r8d, 72446456h
0x14008287f  mov     rdx, rbx
0x140082882  mov     ecx, 41h ; 'A'
0x140082887  call    cs:__imp_ExAllocatePool2
0x14008288e  nop     dword ptr [rax+rax+00h]
0x140082893  mov     rdi, rax
0x140082896  mov     [rsp+38h+arg_18], rax
0x14008289b  test    rax, rax
0x14008289e  jnz     short loc_1400828C4
0x1400828a0  mov     ebx, 0C000009Ah
0x1400828a5  mov     r9d, ebx
0x1400828a8  lea     r8d, [rax+6Dh]
0x1400828ac  lea     rdx, aOnecoreVmVidSy_32; "onecore\\vm\\vid\\sys\\driver\\vidcpugr"...
0x1400828b3  lea     rcx, aVidcpugroupioc_0; "VidCpuGroupIoctlCreate"
0x1400828ba  call    VidTraceErrorStatusInternal0
0x1400828bf  jmp     loc_14008296A
0x1400828c4  test    rbx, rbx
0x1400828c7  jz      short loc_1400828DC
0x1400828c9  test    sil, 3
0x1400828cd  jz      short loc_1400828DC
0x1400828cf  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400828d6  nop     dword ptr [rax+rax+00h]
0x1400828db  int     3; Trap to Debugger
0x1400828dc  mov     r8, rbx; Size
0x1400828df  mov     rdx, rsi; Src
0x1400828e2  mov     rcx, rdi; void *
0x1400828e5  call    RtlCopyFromUser
0x1400828ea  nop
0x1400828eb  mov     r8, r15
0x1400828ee  mov     edx, r14d
0x1400828f1  mov     rcx, rdi
0x1400828f4  call    cs:__imp_WinHvCreateCpuGroup
0x1400828fb  nop     dword ptr [rax+rax+00h]
0x140082900  mov     ebx, eax
0x140082902  test    eax, eax
0x140082904  jns     short loc_14008296A
0x140082906  mov     r9d, eax
0x140082909  mov     r8d, 89h
0x14008290f  lea     rdx, aOnecoreVmVidSy_32; "onecore\\vm\\vid\\sys\\driver\\vidcpugr"...
0x140082916  lea     rcx, aVidcpugroupioc_0; "VidCpuGroupIoctlCreate"
0x14008291d  call    VidTraceErrorStatusInternal0
0x140082922  jmp     short loc_14008296A
0x140082924  mov     ebx, eax
0x140082926  mov     r9d, eax
0x140082929  mov     r8d, 7Fh
0x14008292f  lea     rdx, aOnecoreVmVidSy_32; "onecore\\vm\\vid\\sys\\driver\\vidcpugr"...
0x140082936  lea     rcx, aVidcpugroupioc_0; "VidCpuGroupIoctlCreate"
0x14008293d  call    VidTraceErrorStatusInternal0
0x140082942  mov     rdi, [rsp+38h+arg_18]
0x140082947  jmp     short loc_14008296A
0x140082949  mov     ebx, 0C000000Dh
0x14008294e  mov     r9d, ebx
0x140082951  mov     r8d, 56h ; 'V'
0x140082957  lea     rdx, aOnecoreVmVidSy_32; "onecore\\vm\\vid\\sys\\driver\\vidcpugr"...
0x14008295e  lea     rcx, aVidcpugroupioc_0; "VidCpuGroupIoctlCreate"
0x140082965  call    VidTraceErrorStatusInternal0
0x14008296a  test    rdi, rdi
0x14008296d  jz      short loc_140082983
0x14008296f  mov     edx, 72446456h; Tag
0x140082974  mov     rcx, rdi; P
0x140082977  call    cs:__imp_ExFreePoolWithTag
0x14008297e  nop     dword ptr [rax+rax+00h]
0x140082983  mov     eax, ebx
0x140082985  mov     rbx, [rsp+38h+arg_0]
0x14008298a  mov     rsi, [rsp+38h+arg_8]
0x14008298f  add     rsp, 20h
0x140082993  pop     r15
0x140082995  pop     r14
0x140082997  pop     rdi
0x140082998  retn
```
