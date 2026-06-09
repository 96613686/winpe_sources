# VsmmCryptEncryptDecryptData

- ea: `0x1400780cc`
- end: `0x1400786a4`
- name: `VsmmCryptEncryptDecryptData`
- size: `1496`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140035708`

## callees

- `0x1400386a0`
- `0x1400780cc`
- `0x1400ab5e4`
- `0x1400abaa0`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x1400781ac`
- `ntoskrnl!ProbeForWrite` at `0x1400781ac`
- `ntoskrnl!ProbeForRead` at `0x14007818f`
- `ntoskrnl!ProbeForRead` at `0x14007818f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14007816e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14007816e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400782b9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140078417`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400782b9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140078417`
- `ntoskrnl!IoFreeMdl` at `0x140078656`
- `ntoskrnl!IoFreeMdl` at `0x14007866a`
- `ntoskrnl!IoFreeMdl` at `0x140078656`
- `ntoskrnl!IoFreeMdl` at `0x14007866a`
- `ntoskrnl!IoAllocateMdl` at `0x140078238`
- `ntoskrnl!IoAllocateMdl` at `0x140078396`
- `ntoskrnl!IoAllocateMdl` at `0x140078238`
- `ntoskrnl!IoAllocateMdl` at `0x140078396`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007827c`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400783df`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007827c`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400783df`
- `ntoskrnl!MmUnlockPages` at `0x14007862c`
- `ntoskrnl!MmUnlockPages` at `0x140078642`
- `ntoskrnl!MmUnlockPages` at `0x14007862c`
- `ntoskrnl!MmUnlockPages` at `0x140078642`

## pseudocode

```c
__int64 __fastcall VsmmCryptEncryptDecryptData(
        __int64 a1,
        char *a2,
        ULONG *a3,
        char *a4,
        ULONG Length,
        char a6,
        char a7)
{
  struct _MDL *v10; // rdi
  struct _MDL *v11; // rsi
  unsigned int v12; // ebx
  __int64 v13; // rbx
  struct _MDL *Mdl; // rax
  int v15; // edx
  int v16; // r8d
  PVOID MappedSystemVa; // r14
  int v18; // eax
  struct _MDL *v19; // rax
  int v20; // edx
  int v21; // r8d
  PVOID v22; // rax
  int v23; // eax
  int Priority; // [rsp+28h] [rbp-70h]
  int Prioritya; // [rsp+28h] [rbp-70h]
  size_t Size; // [rsp+30h] [rbp-68h]
  char v28; // [rsp+40h] [rbp-58h]
  _DWORD v29[3]; // [rsp+44h] [rbp-54h] BYREF
  struct _MDL *v30; // [rsp+50h] [rbp-48h]
  struct _MDL *v31; // [rsp+58h] [rbp-40h]
  char v33; // [rsp+B8h] [rbp+20h]

  v29[0] = 0;
  v10 = 0;
  v30 = 0;
  v11 = 0;
  v31 = 0;
  v33 = 0;
  v28 = 0;
  if ( !a4 )
  {
    v12 = -1073741811;
    VidTraceErrorInternal0("VsmmCryptEncryptDecryptData", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2191);
    goto LABEL_45;
  }
  if ( Length - 1 > 0x7F00FFF || *a3 > 0x7F01000 )
  {
    v12 = -1073741306;
    VidTraceErrorInternal0("VsmmCryptEncryptDecryptData", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2200);
  }
  else if ( (*(_BYTE *)(a1 + 40) & 1) != 0 && (v13 = *(_QWORD *)(a1 + 10240), v13 == PsGetCurrentProcess()) )
  {
    ProbeForRead(a4, Length, 1u);
    if ( a2 )
    {
      ProbeForWrite(a2, *a3, 1u);
      if ( a4 < a2 )
      {
        if ( &a4[Length - 1] >= a2 )
        {
          v12 = -1073741811;
          VidTraceErrorInternal0("VsmmCryptEncryptDecryptData", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2256);
          goto LABEL_45;
        }
      }
      else if ( &a2[*a3 - 1] >= a4 )
      {
        v12 = -1073741811;
        VidTraceErrorInternal0("VsmmCryptEncryptDecryptData", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2245);
        goto LABEL_45;
      }
    }
    Mdl = IoAllocateMdl(a4, Length, 0, 0, 0);
    v10 = Mdl;
    v30 = Mdl;
    if ( Mdl )
    {
      MmProbeAndLockPages(Mdl, 0, IoReadAccess);
      v33 = 1;
      if ( (v10->MdlFlags & 5) != 0 )
        MappedSystemVa = v10->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v10, 0, MmCached, 0, 0, 0x40000010u);
      if ( MappedSystemVa )
      {
        v29[0] = *a3;
        if ( a6 )
        {
          LODWORD(Size) = Length;
          v18 = VsmmCryptPackWithHeader(a1, v15, v16, 0, (__int64)v29, MappedSystemVa, Size);
        }
        else
        {
          LOBYTE(Priority) = a7;
          v18 = VsmmCryptUnpackWithHeader(a1, 0, v29, MappedSystemVa, Length, Priority);
        }
        v29[1] = v18;
        v12 = v18;
        if ( v18 >= 0 )
        {
          if ( a2 && *a3 >= v29[0] )
          {
            v19 = IoAllocateMdl(a2, *a3, 0, 0, 0);
            v11 = v19;
            v31 = v19;
            if ( v19 )
            {
              MmProbeAndLockPages(v19, 0, IoWriteAccess);
              v28 = 1;
              if ( (v11->MdlFlags & 5) != 0 )
                v22 = v11->MappedSystemVa;
              else
                v22 = MmMapLockedPagesSpecifyCache(v11, 0, MmCached, 0, 0, 0x40000010u);
              if ( v22 )
              {
                if ( a6 )
                {
                  LODWORD(Size) = Length;
                  v23 = VsmmCryptPackWithHeader(a1, v20, v21, (int)v22, (__int64)v29, MappedSystemVa, Size);
                }
                else
                {
                  LOBYTE(Prioritya) = a7;
                  v23 = VsmmCryptUnpackWithHeader(a1, v22, v29, MappedSystemVa, Length, Prioritya);
                }
                v12 = v23;
                if ( v23 >= 0 )
                {
                  if ( v29[0] <= *a3 )
                  {
                    v12 = 0;
                  }
                  else
                  {
                    v12 = -1073741789;
                    VidTraceErrorInternal0(
                      "VsmmCryptEncryptDecryptData",
                      "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c",
                      2408);
                  }
                }
                else
                {
                  VidTraceErrorInternal0(
                    "VsmmCryptEncryptDecryptData",
                    "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c",
                    2397);
                }
              }
              else
              {
                v12 = -1073741670;
                VidTraceErrorInternal0("VsmmCryptEncryptDecryptData", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2367);
              }
            }
            else
            {
              v12 = -1073741670;
              VidTraceErrorInternal0("VsmmCryptEncryptDecryptData", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2346);
            }
          }
          else
          {
            v12 = -1073741789;
            VidTraceErrorInternal0("VsmmCryptEncryptDecryptData", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2338);
          }
        }
        else
        {
          VidTraceErrorInternal0("VsmmCryptEncryptDecryptData", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2320);
        }
      }
      else
      {
        v12 = -1073741670;
        VidTraceErrorInternal0("VsmmCryptEncryptDecryptData", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2286);
      }
    }
    else
    {
      v12 = -1073741670;
      VidTraceErrorInternal0("VsmmCryptEncryptDecryptData", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2265);
    }
  }
  else
  {
    v12 = -1073741790;
    VidTraceErrorInternal0("VsmmCryptEncryptDecryptData", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2208);
  }
LABEL_45:
  if ( v33 )
    MmUnlockPages(v10);
  if ( v28 )
    MmUnlockPages(v11);
  if ( v10 )
    IoFreeMdl(v10);
  if ( v11 )
    IoFreeMdl(v11);
  if ( (int)(v12 + 0x80000000) < 0 || v12 == -1073741789 )
    *a3 = v29[0];
  return v12;
}

```

## disassembly

```asm
0x1400780cc  mov     [rsp+arg_10], r8
0x1400780d1  mov     qword ptr [rsp+arg_0], rcx
0x1400780d6  push    rbx
0x1400780d7  push    rsi
0x1400780d8  push    rdi
0x1400780d9  push    r12
0x1400780db  push    r13
0x1400780dd  push    r14
0x1400780df  push    r15
0x1400780e1  sub     rsp, 60h
0x1400780e5  mov     r14, r9
0x1400780e8  mov     r15, r8
0x1400780eb  mov     r12, rdx
0x1400780ee  mov     [rsp+98h+var_54], 0
0x1400780f6  xor     edi, edi
0x1400780f8  mov     [rsp+98h+var_48], rdi
0x1400780fd  xor     esi, esi
0x1400780ff  mov     [rsp+98h+var_40], rsi
0x140078104  mov     [rsp+98h+arg_18], sil
0x14007810c  mov     [rsp+98h+var_58], sil
0x140078111  test    r9, r9
0x140078114  jnz     short loc_140078139
0x140078116  mov     ebx, 0C000000Dh
0x14007811b  mov     r8d, 88Fh
0x140078121  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140078128  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x14007812f  call    VidTraceErrorInternal0
0x140078134  jmp     loc_14007861F
0x140078139  mov     r13d, dword ptr [rsp+98h+Length]
0x140078141  lea     eax, [r13-1]
0x140078145  cmp     eax, 7F00FFFh
0x14007814a  ja      loc_140078601
0x140078150  cmp     dword ptr [r8], 7F01000h
0x140078157  ja      loc_140078601
0x14007815d  test    byte ptr [rcx+28h], 1
0x140078161  jz      loc_1400785E1
0x140078167  mov     rbx, [rcx+2800h]
0x14007816e  call    cs:__imp_PsGetCurrentProcess
0x140078175  nop     dword ptr [rax+rax+00h]
0x14007817a  cmp     rbx, rax
0x14007817d  jnz     loc_1400785E1
0x140078183  mov     r8d, 1; Alignment
0x140078189  mov     edx, r13d; Length
0x14007818c  mov     rcx, r14; Address
0x14007818f  call    cs:__imp_ProbeForRead
0x140078196  nop     dword ptr [rax+rax+00h]
0x14007819b  test    r12, r12
0x14007819e  jz      short loc_1400781B9
0x1400781a0  mov     edx, [r15]; Length
0x1400781a3  mov     r8d, 1; Alignment
0x1400781a9  mov     rcx, r12; Address
0x1400781ac  call    cs:__imp_ProbeForWrite
0x1400781b3  nop     dword ptr [rax+rax+00h]
0x1400781b8  nop
0x1400781b9  test    r12, r12
0x1400781bc  jz      short loc_140078223
0x1400781be  cmp     r14, r12
0x1400781c1  jb      short loc_1400781F4
0x1400781c3  mov     ecx, [r15]
0x1400781c6  dec     rcx
0x1400781c9  add     rcx, r12
0x1400781cc  cmp     rcx, r14
0x1400781cf  jb      short loc_140078223
0x1400781d1  mov     ebx, 0C000000Dh
0x1400781d6  mov     r8d, 8C5h
0x1400781dc  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400781e3  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x1400781ea  call    VidTraceErrorInternal0
0x1400781ef  jmp     loc_14007861F
0x1400781f4  lea     rax, [r13-1]
0x1400781f8  add     rax, r14
0x1400781fb  cmp     rax, r12
0x1400781fe  jb      short loc_140078223
0x140078200  mov     ebx, 0C000000Dh
0x140078205  mov     r8d, 8D0h
0x14007820b  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140078212  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x140078219  call    VidTraceErrorInternal0
0x14007821e  jmp     loc_14007861F
0x140078223  mov     [rsp+98h+Irp], 0; Irp
0x14007822c  xor     r9d, r9d; ChargeQuota
0x14007822f  xor     r8d, r8d; SecondaryBuffer
0x140078232  mov     edx, r13d; Length
0x140078235  mov     rcx, r14; VirtualAddress
0x140078238  call    cs:__imp_IoAllocateMdl
0x14007823f  nop     dword ptr [rax+rax+00h]
0x140078244  mov     rdi, rax
0x140078247  mov     [rsp+98h+var_48], rax
0x14007824c  test    rax, rax
0x14007824f  jnz     short loc_140078274
0x140078251  mov     ebx, 0C000009Ah
0x140078256  mov     r8d, 8D9h
0x14007825c  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140078263  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x14007826a  call    VidTraceErrorInternal0
0x14007826f  jmp     loc_14007861F
0x140078274  xor     r8d, r8d; Operation
0x140078277  xor     edx, edx; AccessMode
0x140078279  mov     rcx, rdi; MemoryDescriptorList
0x14007827c  call    cs:__imp_MmProbeAndLockPages
0x140078283  nop     dword ptr [rax+rax+00h]
0x140078288  nop
0x140078289  mov     [rsp+98h+arg_18], 1
0x140078291  test    byte ptr [rdi+0Ah], 5
0x140078295  jz      short loc_14007829D
0x140078297  mov     r14, [rdi+18h]
0x14007829b  jmp     short loc_1400782C8
0x14007829d  mov     [rsp+98h+Priority], 40000010h; Priority
0x1400782a5  mov     dword ptr [rsp+98h+Irp], 0; BugCheckOnFailure
0x1400782ad  xor     r9d, r9d; RequestedAddress
0x1400782b0  xor     edx, edx; AccessMode
0x1400782b2  lea     r8d, [r9+1]; CacheType
0x1400782b6  mov     rcx, rdi; MemoryDescriptorList
0x1400782b9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400782c0  nop     dword ptr [rax+rax+00h]
0x1400782c5  mov     r14, rax
0x1400782c8  test    r14, r14
0x1400782cb  jnz     short loc_1400782F0
0x1400782cd  mov     ebx, 0C000009Ah
0x1400782d2  mov     r8d, 8EEh
0x1400782d8  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400782df  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x1400782e6  call    VidTraceErrorInternal0
0x1400782eb  jmp     loc_14007861F
0x1400782f0  mov     eax, [r15]
0x1400782f3  mov     [rsp+98h+var_54], eax
0x1400782f7  mov     rcx, qword ptr [rsp+98h+arg_0]; int
0x1400782ff  cmp     [rsp+98h+arg_28], 0
0x140078307  jz      short loc_140078327
0x140078309  mov     dword ptr [rsp+98h+Size], r13d; Size
0x14007830e  mov     qword ptr [rsp+98h+Priority], r14; Src
0x140078313  lea     rax, [rsp+98h+var_54]
0x140078318  mov     [rsp+98h+Irp], rax; __int64
0x14007831d  xor     r9d, r9d; int
0x140078320  call    VsmmCryptPackWithHeader
0x140078325  jmp     short loc_140078346
0x140078327  mov     al, [rsp+98h+arg_30]
0x14007832e  mov     byte ptr [rsp+98h+Priority], al
0x140078332  mov     dword ptr [rsp+98h+Irp], r13d
0x140078337  mov     r9, r14
0x14007833a  lea     r8, [rsp+98h+var_54]
0x14007833f  xor     edx, edx
0x140078341  call    VsmmCryptUnpackWithHeader
0x140078346  mov     [rsp+98h+var_54+4], eax
0x14007834a  mov     ebx, eax
0x14007834c  test    eax, eax
0x14007834e  jns     short loc_14007836E
0x140078350  mov     r8d, 910h
0x140078356  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x14007835d  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x140078364  call    VidTraceErrorInternal0
0x140078369  jmp     loc_14007861F
0x14007836e  test    r12, r12
0x140078371  jz      loc_14007852C
0x140078377  mov     edx, [r15]; Length
0x14007837a  cmp     edx, [rsp+98h+var_54]
0x14007837e  jb      loc_14007852C
0x140078384  mov     [rsp+98h+Irp], 0; Irp
0x14007838d  xor     r9d, r9d; ChargeQuota
0x140078390  xor     r8d, r8d; SecondaryBuffer
0x140078393  mov     rcx, r12; VirtualAddress
0x140078396  call    cs:__imp_IoAllocateMdl
0x14007839d  nop     dword ptr [rax+rax+00h]
0x1400783a2  mov     rsi, rax
0x1400783a5  mov     [rsp+98h+var_40], rax
0x1400783aa  test    rax, rax
0x1400783ad  jnz     short loc_1400783D2
0x1400783af  mov     ebx, 0C000009Ah
0x1400783b4  mov     r8d, 92Ah
0x1400783ba  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400783c1  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x1400783c8  call    VidTraceErrorInternal0
0x1400783cd  jmp     loc_14007861F
0x1400783d2  mov     ebx, 1
0x1400783d7  mov     r8d, ebx; Operation
0x1400783da  xor     edx, edx; AccessMode
0x1400783dc  mov     rcx, rsi; MemoryDescriptorList
0x1400783df  call    cs:__imp_MmProbeAndLockPages
0x1400783e6  nop     dword ptr [rax+rax+00h]
0x1400783eb  nop
0x1400783ec  mov     [rsp+98h+var_58], bl
0x1400783f0  test    byte ptr [rsi+0Ah], 5
0x1400783f4  jz      short loc_1400783FC
0x1400783f6  mov     rax, [rsi+18h]
0x1400783fa  jmp     short loc_140078423
0x1400783fc  mov     [rsp+98h+Priority], 40000010h; Priority
0x140078404  mov     dword ptr [rsp+98h+Irp], 0; BugCheckOnFailure
0x14007840c  xor     r9d, r9d; RequestedAddress
0x14007840f  mov     r8d, ebx; CacheType
0x140078412  xor     edx, edx; AccessMode
0x140078414  mov     rcx, rsi; MemoryDescriptorList
0x140078417  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007841e  nop     dword ptr [rax+rax+00h]
0x140078423  test    rax, rax
0x140078426  jnz     short loc_14007844B
0x140078428  mov     ebx, 0C000009Ah
0x14007842d  mov     r8d, 93Fh
0x140078433  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x14007843a  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x140078441  call    VidTraceErrorInternal0
0x140078446  jmp     loc_14007861F
0x14007844b  cmp     [rsp+98h+arg_28], 0
0x140078453  jz      short loc_14007847B
0x140078455  mov     dword ptr [rsp+98h+Size], r13d; Size
0x14007845a  mov     qword ptr [rsp+98h+Priority], r14; Src
0x14007845f  lea     rcx, [rsp+98h+var_54]
0x140078464  mov     [rsp+98h+Irp], rcx; __int64
0x140078469  mov     r9, rax; int
0x14007846c  mov     rcx, qword ptr [rsp+98h+arg_0]; int
0x140078474  call    VsmmCryptPackWithHeader
0x140078479  jmp     short loc_1400784A3
0x14007847b  mov     cl, [rsp+98h+arg_30]
0x140078482  mov     byte ptr [rsp+98h+Priority], cl
0x140078486  mov     dword ptr [rsp+98h+Irp], r13d
0x14007848b  mov     r9, r14
0x14007848e  lea     r8, [rsp+98h+var_54]
0x140078493  mov     rdx, rax
0x140078496  mov     rcx, qword ptr [rsp+98h+arg_0]
0x14007849e  call    VsmmCryptUnpackWithHeader
0x1400784a3  mov     ebx, eax
0x1400784a5  test    eax, eax
0x1400784a7  jns     short loc_1400784C7
0x1400784a9  mov     r8d, 95Dh
0x1400784af  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400784b6  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x1400784bd  call    VidTraceErrorInternal0
0x1400784c2  jmp     loc_14007861F
0x1400784c7  mov     eax, [r15]
0x1400784ca  cmp     [rsp+98h+var_54], eax
0x1400784ce  jbe     short loc_1400784F3
0x1400784d0  mov     ebx, 0C0000023h
0x1400784d5  mov     r8d, 968h
0x1400784db  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400784e2  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x1400784e9  call    VidTraceErrorInternal0
0x1400784ee  jmp     loc_14007861F
0x1400784f3  xor     ebx, ebx
0x1400784f5  jmp     loc_14007861F
0x1400784fa  mov     ebx, eax
0x1400784fc  mov     r8d, 935h
0x140078502  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140078509  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x140078510  call    VidTraceErrorInternal0
0x140078515  mov     r15, [rsp+98h+arg_10]
0x14007851d  mov     rdi, [rsp+98h+var_48]
0x140078522  mov     rsi, [rsp+98h+var_40]
0x140078527  jmp     loc_14007861F
0x14007852c  mov     ebx, 0C0000023h
0x140078531  mov     r8d, 922h
0x140078537  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x14007853e  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x140078545  call    VidTraceErrorInternal0
0x14007854a  jmp     loc_14007861F
0x14007854f  mov     ebx, eax
0x140078551  mov     [rsp+98h+var_54+4], eax
0x140078555  mov     r8d, 917h
0x14007855b  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140078562  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x140078569  call    VidTraceErrorInternal0
0x14007856e  mov     r15, [rsp+98h+arg_10]
0x140078576  mov     rdi, [rsp+98h+var_48]
0x14007857b  mov     rsi, [rsp+98h+var_40]
0x140078580  jmp     loc_14007861F
0x140078585  mov     ebx, eax
0x140078587  mov     r8d, 8E4h
0x14007858d  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140078594  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x14007859b  call    VidTraceErrorInternal0
0x1400785a0  mov     r15, [rsp+98h+arg_10]
0x1400785a8  mov     rdi, [rsp+98h+var_48]
0x1400785ad  mov     rsi, [rsp+98h+var_40]
0x1400785b2  jmp     short loc_14007861F
0x1400785b4  mov     ebx, eax
0x1400785b6  mov     r8d, 8B0h
0x1400785bc  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400785c3  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x1400785ca  call    VidTraceErrorInternal0
0x1400785cf  mov     r15, [rsp+98h+arg_10]
0x1400785d7  mov     rdi, [rsp+98h+var_48]
0x1400785dc  mov     rsi, rdi
0x1400785df  jmp     short loc_14007861F
0x1400785e1  mov     ebx, 0C0000022h
0x1400785e6  mov     r8d, 8A0h
0x1400785ec  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400785f3  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x1400785fa  call    VidTraceErrorInternal0
0x1400785ff  jmp     short loc_14007861F
0x140078601  mov     ebx, 0C0000206h
0x140078606  mov     r8d, 898h
0x14007860c  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140078613  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x14007861a  call    VidTraceErrorInternal0
0x14007861f  cmp     [rsp+98h+arg_18], 0
0x140078627  jz      short loc_140078638
0x140078629  mov     rcx, rdi; MemoryDescriptorList
0x14007862c  call    cs:__imp_MmUnlockPages
0x140078633  nop     dword ptr [rax+rax+00h]
0x140078638  cmp     [rsp+98h+var_58], 0
0x14007863d  jz      short loc_14007864E
0x14007863f  mov     rcx, rsi; MemoryDescriptorList
  ... truncated ...
```
