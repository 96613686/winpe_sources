# VidInformationIoctlGetSystemInformation

- ea: `0x14009a35c`
- end: `0x14009a61a`
- name: `VidInformationIoctlGetSystemInformation`
- size: `702`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400377bc`
- `0x14009a324`

## callees

- `0x140008fd8`
- `0x1400161ec`
- `0x140021626`
- `0x140021650`
- `0x14009a35c`
- `0x14009a65c`
- `0x14009a70c`

## import_xrefs

- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14009a58f`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14009a58f`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14009a5a8`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14009a5a8`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14009a55b`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14009a55b`
- `winhvr!WinHvGetSystemInformation` at `0x14009a5f0`
- `winhvr!WinHvGetSystemInformation` at `0x14009a5f0`

## pseudocode

```c
NTSTATUS __fastcall VidInformationIoctlGetSystemInformation(
        int a1,
        ULONG *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        _DWORD *a6)
{
  unsigned int v9; // ebx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  NTSTATUS result; // eax
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  bool v20; // r15
  _PROCESSOR_NUMBER ProcNumber; // [rsp+30h] [rbp-78h] BYREF
  NTSTATUS v27; // [rsp+34h] [rbp-74h]
  char Str1[16]; // [rsp+38h] [rbp-70h] BYREF
  struct _GROUP_AFFINITY Affinity; // [rsp+48h] [rbp-60h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+58h] [rbp-50h] BYREF

  *a6 = 0;
  v9 = 6;
  if ( a1 <= 6 )
  {
    if ( a1 != 6 )
    {
      if ( a1 )
      {
        v10 = a1 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( v12 )
            {
              v13 = v12 - 1;
              if ( v13 )
              {
                if ( v13 == 1 )
                  return WinHvGetSystemInformation(v9, a2, a3, a4, a5, a6);
                return -1073741821;
              }
              v9 = 5;
            }
            else
            {
              v9 = 4;
            }
          }
          else
          {
            v9 = 2;
          }
        }
        else
        {
          v9 = 1;
        }
      }
      else
      {
        v9 = 0;
      }
      return WinHvGetSystemInformation(v9, a2, a3, a4, a5, a6);
    }
    if ( a5 >= 2 )
    {
      result = VidCppcQuerySupport(a4);
      v27 = result;
      if ( result >= 0 )
      {
        result = VidCppcQueryResourcePrioritiesSupport(a4 + 1);
        v27 = result;
        *a6 = 2;
      }
      return result;
    }
    return -1073741789;
  }
  v15 = a1 - 7;
  if ( !v15 )
  {
    v9 = 11;
    return WinHvGetSystemInformation(v9, a2, a3, a4, a5, a6);
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    v9 = 12;
    return WinHvGetSystemInformation(v9, a2, a3, a4, a5, a6);
  }
  v17 = v16 - 1;
  if ( v17 )
  {
    v18 = v17 - 1;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        if ( v19 != 1 )
          return -1073741821;
        v9 = 9;
      }
      else
      {
        v9 = 14;
      }
    }
    else
    {
      v9 = 3;
    }
    return WinHvGetSystemInformation(v9, a2, a3, a4, a5, a6);
  }
  *(_OWORD *)Str1 = 0;
  HviGetHypervisorFeatures(Str1);
  v20 = 0;
  if ( (*(_QWORD *)Str1 & 0x100000000LL) != 0 )
  {
    *(_OWORD *)Str1 = 0;
    HviGetHypervisorFeatures(Str1);
    if ( (*(_QWORD *)Str1 & 0x100000000000LL) == 0 )
      v20 = 1;
  }
  *(_DWORD *)&Str1[12] = 0;
  ProcNumber = 0;
  Affinity = 0;
  PreviousAffinity = 0;
  _RAX = 0;
  __asm { cpuid }
  *(_DWORD *)Str1 = _RBX;
  *(_DWORD *)&Str1[4] = _RDX;
  *(_DWORD *)&Str1[8] = _RCX;
  if ( strncmp_0(Str1, "AuthenticAMD", 0xCu) || !v20 )
  {
    v9 = 13;
    return WinHvGetSystemInformation(v9, a2, a3, a4, a5, a6);
  }
  if ( a3 != 4 || a5 != 256 )
    return -1073741789;
  result = KeGetProcessorNumberFromIndex(*a2, &ProcNumber);
  if ( result >= 0 )
  {
    Affinity.Group = ProcNumber.Group;
    Affinity.Mask = 1LL << ProcNumber.Number;
    KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
    VidBuildSystemTopology(a4);
    KeRevertToUserGroupAffinityThread(&PreviousAffinity);
    *a6 = 256;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14009a35c  push    rbx
0x14009a35e  push    rsi
0x14009a35f  push    rdi
0x14009a360  push    r12
0x14009a362  push    r13
0x14009a364  push    r14
0x14009a366  push    r15
0x14009a368  sub     rsp, 70h
0x14009a36c  mov     rax, cs:__security_cookie
0x14009a373  xor     rax, rsp
0x14009a376  mov     [rsp+0A8h+var_40], rax
0x14009a37b  mov     rsi, r9
0x14009a37e  mov     r12d, r8d
0x14009a381  mov     r13, rdx
0x14009a384  mov     r14, [rsp+0A8h+arg_28]
0x14009a38c  mov     dword ptr [r14], 0
0x14009a393  mov     ebx, 6
0x14009a398  cmp     ecx, ebx
0x14009a39a  jg      loc_14009A43B
0x14009a3a0  jz      short loc_14009A3F7
0x14009a3a2  test    ecx, ecx
0x14009a3a4  jz      short loc_14009A3F0
0x14009a3a6  sub     ecx, 1
0x14009a3a9  jz      short loc_14009A3E6
0x14009a3ab  sub     ecx, 1
0x14009a3ae  jz      short loc_14009A3DC
0x14009a3b0  sub     ecx, 1
0x14009a3b3  jz      short loc_14009A3D2
0x14009a3b5  sub     ecx, 1
0x14009a3b8  jz      short loc_14009A3C8
0x14009a3ba  cmp     ecx, 1
0x14009a3bd  jnz     loc_14009A461
0x14009a3c3  jmp     loc_14009A5D5
0x14009a3c8  mov     ebx, 5
0x14009a3cd  jmp     loc_14009A5D5
0x14009a3d2  mov     ebx, 4
0x14009a3d7  jmp     loc_14009A5D5
0x14009a3dc  mov     ebx, 2
0x14009a3e1  jmp     loc_14009A5D5
0x14009a3e6  mov     ebx, 1
0x14009a3eb  jmp     loc_14009A5D5
0x14009a3f0  xor     ebx, ebx
0x14009a3f2  jmp     loc_14009A5D5
0x14009a3f7  mov     ebx, 2
0x14009a3fc  cmp     [rsp+0A8h+arg_20], ebx
0x14009a403  jb      loc_14009A5BB
0x14009a409  mov     rcx, rsi
0x14009a40c  call    VidCppcQuerySupport
0x14009a411  mov     [rsp+0A8h+var_74], eax
0x14009a415  test    eax, eax
0x14009a417  js      loc_14009A5FC
0x14009a41d  lea     rcx, [rsi+1]
0x14009a421  call    VidCppcQueryResourcePrioritiesSupport
0x14009a426  mov     [rsp+0A8h+var_74], eax
0x14009a42a  mov     [r14], ebx
0x14009a42d  jmp     loc_14009A5FC
0x14009a432  mov     [rsp+0A8h+var_74], eax
0x14009a436  jmp     loc_14009A5FC
0x14009a43b  sub     ecx, 7
0x14009a43e  jz      loc_14009A5D0
0x14009a444  sub     ecx, 1
0x14009a447  jz      loc_14009A5C9
0x14009a44d  sub     ecx, 1
0x14009a450  jz      short loc_14009A489
0x14009a452  sub     ecx, 1
0x14009a455  jz      short loc_14009A47F
0x14009a457  sub     ecx, 1
0x14009a45a  jz      short loc_14009A475
0x14009a45c  cmp     ecx, 1
0x14009a45f  jz      short loc_14009A46B
0x14009a461  mov     eax, 0C0000003h
0x14009a466  jmp     loc_14009A5FC
0x14009a46b  mov     ebx, 9
0x14009a470  jmp     loc_14009A5D5
0x14009a475  mov     ebx, 0Eh
0x14009a47a  jmp     loc_14009A5D5
0x14009a47f  mov     ebx, 3
0x14009a484  jmp     loc_14009A5D5
0x14009a489  xorps   xmm0, xmm0
0x14009a48c  movups  xmmword ptr [rsp+0A8h+Str1], xmm0
0x14009a491  lea     rcx, [rsp+0A8h+Str1]
0x14009a496  call    HviGetHypervisorFeatures
0x14009a49b  mov     rax, 100000000h
0x14009a4a5  test    qword ptr [rsp+0A8h+Str1], rax
0x14009a4aa  jz      short loc_14009A4D9
0x14009a4ac  xorps   xmm0, xmm0
0x14009a4af  movups  xmmword ptr [rsp+0A8h+Str1], xmm0
0x14009a4b4  lea     rcx, [rsp+0A8h+Str1]
0x14009a4b9  call    HviGetHypervisorFeatures
0x14009a4be  mov     rax, 100000000000h
0x14009a4c8  test    qword ptr [rsp+0A8h+Str1], rax
0x14009a4cd  jnz     short loc_14009A4D9
0x14009a4cf  mov     edi, 1
0x14009a4d4  mov     r15b, dil
0x14009a4d7  jmp     short loc_14009A4E1
0x14009a4d9  xor     r15b, r15b
0x14009a4dc  mov     edi, 1
0x14009a4e1  xorps   xmm0, xmm0
0x14009a4e4  movups  xmmword ptr [rsp+0A8h+Str1], xmm0
0x14009a4e9  mov     dword ptr [rsp+0A8h+ProcNumber.Group], 0
0x14009a4f1  xorps   xmm1, xmm1
0x14009a4f4  movups  xmmword ptr [rsp+0A8h+Affinity.Mask], xmm1
0x14009a4f9  movups  xmmword ptr [rsp+0A8h+PreviousAffinity.Mask], xmm0
0x14009a4fe  xor     eax, eax
0x14009a500  xor     ecx, ecx
0x14009a502  cpuid
0x14009a504  mov     dword ptr [rsp+0A8h+Str1], eax
0x14009a508  mov     dword ptr [rsp+0A8h+Str1], ebx
0x14009a50c  mov     dword ptr [rsp+0A8h+Str1+4], edx
0x14009a510  mov     dword ptr [rsp+0A8h+Str1+8], ecx
0x14009a514  mov     r8d, 0Ch; MaxCount
0x14009a51a  lea     rdx, Str2; "AuthenticAMD"
0x14009a521  lea     rcx, [rsp+0A8h+Str1]; Str1
0x14009a526  call    strncmp_0
0x14009a52b  test    eax, eax
0x14009a52d  jnz     loc_14009A5C2
0x14009a533  test    r15b, r15b
0x14009a536  jz      loc_14009A5C2
0x14009a53c  lea     ebx, [rax+4]
0x14009a53f  cmp     r12d, ebx
0x14009a542  jnz     short loc_14009A5BB
0x14009a544  mov     ebx, 100h
0x14009a549  cmp     [rsp+0A8h+arg_20], ebx
0x14009a550  jnz     short loc_14009A5BB
0x14009a552  lea     rdx, [rsp+0A8h+ProcNumber]; ProcNumber
0x14009a557  mov     ecx, [r13+0]; ProcIndex
0x14009a55b  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14009a562  nop     dword ptr [rax+rax+00h]
0x14009a567  test    eax, eax
0x14009a569  js      loc_14009A5FC
0x14009a56f  movzx   eax, [rsp+0A8h+ProcNumber.Group]
0x14009a574  mov     [rsp+0A8h+Affinity.Group], ax
0x14009a579  mov     cl, [rsp+0A8h+ProcNumber.Number]
0x14009a57d  shl     rdi, cl
0x14009a580  mov     [rsp+0A8h+Affinity.Mask], rdi
0x14009a585  lea     rdx, [rsp+0A8h+PreviousAffinity]; PreviousAffinity
0x14009a58a  lea     rcx, [rsp+0A8h+Affinity]; Affinity
0x14009a58f  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14009a596  nop     dword ptr [rax+rax+00h]
0x14009a59b  mov     rcx, rsi
0x14009a59e  call    VidBuildSystemTopology
0x14009a5a3  lea     rcx, [rsp+0A8h+PreviousAffinity]; PreviousAffinity
0x14009a5a8  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14009a5af  nop     dword ptr [rax+rax+00h]
0x14009a5b4  mov     [r14], ebx
0x14009a5b7  xor     eax, eax
0x14009a5b9  jmp     short loc_14009A5FC
0x14009a5bb  mov     eax, 0C0000023h
0x14009a5c0  jmp     short loc_14009A5FC
0x14009a5c2  mov     ebx, 0Dh
0x14009a5c7  jmp     short loc_14009A5D5
0x14009a5c9  mov     ebx, 0Ch
0x14009a5ce  jmp     short loc_14009A5D5
0x14009a5d0  mov     ebx, 0Bh
0x14009a5d5  mov     [rsp+0A8h+var_80], r14
0x14009a5da  mov     eax, [rsp+0A8h+arg_20]
0x14009a5e1  mov     [rsp+0A8h+var_88], eax
0x14009a5e5  mov     r9, rsi
0x14009a5e8  mov     r8d, r12d
0x14009a5eb  mov     rdx, r13
0x14009a5ee  mov     ecx, ebx
0x14009a5f0  call    cs:__imp_WinHvGetSystemInformation
0x14009a5f7  nop     dword ptr [rax+rax+00h]
0x14009a5fc  mov     rcx, [rsp+0A8h+var_40]
0x14009a601  xor     rcx, rsp; StackCookie
0x14009a604  call    __security_check_cookie
0x14009a609  add     rsp, 70h
0x14009a60d  pop     r15
0x14009a60f  pop     r14
0x14009a611  pop     r13
0x14009a613  pop     r12
0x14009a615  pop     rdi
0x14009a616  pop     rsi
0x14009a617  pop     rbx
0x14009a618  retn
```
