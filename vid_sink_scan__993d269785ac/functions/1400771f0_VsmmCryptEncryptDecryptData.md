# VsmmCryptEncryptDecryptData

- ea: `0x1400771f0`
- end: `0x1400777c8`
- name: `VsmmCryptEncryptDecryptData`
- size: `1496`
- prototype: `__int64 __fastcall(__int64, char *, ULONG *, char *, ULONG Length, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140035698`

## callees

- `0x140038630`
- `0x1400771f0`
- `0x1400a9864`
- `0x1400a9d20`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x1400772d0`
- `ntoskrnl!ProbeForWrite` at `0x1400772d0`
- `ntoskrnl!ProbeForRead` at `0x1400772b3`
- `ntoskrnl!ProbeForRead` at `0x1400772b3`
- `ntoskrnl!PsGetCurrentProcess` at `0x140077292`
- `ntoskrnl!PsGetCurrentProcess` at `0x140077292`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400773dd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007753b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400773dd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007753b`
- `ntoskrnl!IoFreeMdl` at `0x14007777a`
- `ntoskrnl!IoFreeMdl` at `0x14007778e`
- `ntoskrnl!IoFreeMdl` at `0x14007777a`
- `ntoskrnl!IoFreeMdl` at `0x14007778e`
- `ntoskrnl!IoAllocateMdl` at `0x14007735c`
- `ntoskrnl!IoAllocateMdl` at `0x1400774ba`
- `ntoskrnl!IoAllocateMdl` at `0x14007735c`
- `ntoskrnl!IoAllocateMdl` at `0x1400774ba`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400773a0`
- `ntoskrnl!MmProbeAndLockPages` at `0x140077503`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400773a0`
- `ntoskrnl!MmProbeAndLockPages` at `0x140077503`
- `ntoskrnl!MmUnlockPages` at `0x140077750`
- `ntoskrnl!MmUnlockPages` at `0x140077766`
- `ntoskrnl!MmUnlockPages` at `0x140077750`
- `ntoskrnl!MmUnlockPages` at `0x140077766`

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
  __int64 v15; // rdx
  __int64 v16; // r8
  PVOID MappedSystemVa; // r14
  int v18; // eax
  struct _MDL *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  PVOID v22; // rax
  int v23; // eax
  size_t Size; // [rsp+30h] [rbp-68h]
  char v26; // [rsp+40h] [rbp-58h]
  unsigned int v27[3]; // [rsp+44h] [rbp-54h] BYREF
  struct _MDL *v28; // [rsp+50h] [rbp-48h]
  struct _MDL *v29; // [rsp+58h] [rbp-40h]
  char v31; // [rsp+B8h] [rbp+20h]

  v27[0] = 0;
  v10 = 0;
  v28 = 0;
  v11 = 0;
  v29 = 0;
  v31 = 0;
  v26 = 0;
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
    v28 = Mdl;
    if ( Mdl )
    {
      MmProbeAndLockPages(Mdl, 0, IoReadAccess);
      v31 = 1;
      if ( (v10->MdlFlags & 5) != 0 )
        MappedSystemVa = v10->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v10, 0, MmCached, 0, 0, 0x40000010u);
      if ( MappedSystemVa )
      {
        v27[0] = *a3;
        if ( a6 )
        {
          LODWORD(Size) = Length;
          v18 = VsmmCryptPackWithHeader(a1, v15, v16, 0, v27, MappedSystemVa, Size);
        }
        else
        {
          v18 = VsmmCryptUnpackWithHeader(a1, 0, v27, (__int64)MappedSystemVa, Length, a7);
        }
        v27[1] = v18;
        v12 = v18;
        if ( v18 >= 0 )
        {
          if ( a2 && *a3 >= v27[0] )
          {
            v19 = IoAllocateMdl(a2, *a3, 0, 0, 0);
            v11 = v19;
            v29 = v19;
            if ( v19 )
            {
              MmProbeAndLockPages(v19, 0, IoWriteAccess);
              v26 = 1;
              if ( (v11->MdlFlags & 5) != 0 )
                v22 = v11->MappedSystemVa;
              else
                v22 = MmMapLockedPagesSpecifyCache(v11, 0, MmCached, 0, 0, 0x40000010u);
              if ( v22 )
              {
                if ( a6 )
                {
                  LODWORD(Size) = Length;
                  v23 = VsmmCryptPackWithHeader(a1, v20, v21, (__int64)v22, v27, MappedSystemVa, Size);
                }
                else
                {
                  v23 = VsmmCryptUnpackWithHeader(a1, v22, v27, (__int64)MappedSystemVa, Length, a7);
                }
                v12 = v23;
                if ( v23 >= 0 )
                {
                  if ( v27[0] <= *a3 )
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
  if ( v31 )
    MmUnlockPages(v10);
  if ( v26 )
    MmUnlockPages(v11);
  if ( v10 )
    IoFreeMdl(v10);
  if ( v11 )
    IoFreeMdl(v11);
  if ( (int)(v12 + 0x80000000) < 0 || v12 == -1073741789 )
    *a3 = v27[0];
  return v12;
}

```

## disassembly

```asm
0x1400771f0  mov     [rsp+arg_10], r8
0x1400771f5  mov     qword ptr [rsp+arg_0], rcx
0x1400771fa  push    rbx
0x1400771fb  push    rsi
0x1400771fc  push    rdi
0x1400771fd  push    r12
0x1400771ff  push    r13
0x140077201  push    r14
0x140077203  push    r15
0x140077205  sub     rsp, 60h
0x140077209  mov     r14, r9
0x14007720c  mov     r15, r8
0x14007720f  mov     r12, rdx
0x140077212  mov     [rsp+98h+var_54], 0
0x14007721a  xor     edi, edi
0x14007721c  mov     [rsp+98h+var_48], rdi
0x140077221  xor     esi, esi
0x140077223  mov     [rsp+98h+var_40], rsi
0x140077228  mov     [rsp+98h+arg_18], sil
0x140077230  mov     [rsp+98h+var_58], sil
0x140077235  test    r9, r9
0x140077238  jnz     short loc_14007725D
0x14007723a  mov     ebx, 0C000000Dh
0x14007723f  mov     r8d, 88Fh
0x140077245  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x14007724c  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x140077253  call    VidTraceErrorInternal0
0x140077258  jmp     loc_140077743
0x14007725d  mov     r13d, dword ptr [rsp+98h+Length]
0x140077265  lea     eax, [r13-1]
0x140077269  cmp     eax, 7F00FFFh
0x14007726e  ja      loc_140077725
0x140077274  cmp     dword ptr [r8], 7F01000h
0x14007727b  ja      loc_140077725
0x140077281  test    byte ptr [rcx+28h], 1
0x140077285  jz      loc_140077705
0x14007728b  mov     rbx, [rcx+2800h]
0x140077292  call    cs:__imp_PsGetCurrentProcess
0x140077299  nop     dword ptr [rax+rax+00h]
0x14007729e  cmp     rbx, rax
0x1400772a1  jnz     loc_140077705
0x1400772a7  mov     r8d, 1; Alignment
0x1400772ad  mov     edx, r13d; Length
0x1400772b0  mov     rcx, r14; Address
0x1400772b3  call    cs:__imp_ProbeForRead
0x1400772ba  nop     dword ptr [rax+rax+00h]
0x1400772bf  test    r12, r12
0x1400772c2  jz      short loc_1400772DD
0x1400772c4  mov     edx, [r15]; Length
0x1400772c7  mov     r8d, 1; Alignment
0x1400772cd  mov     rcx, r12; Address
0x1400772d0  call    cs:__imp_ProbeForWrite
0x1400772d7  nop     dword ptr [rax+rax+00h]
0x1400772dc  nop
0x1400772dd  test    r12, r12
0x1400772e0  jz      short loc_140077347
0x1400772e2  cmp     r14, r12
0x1400772e5  jb      short loc_140077318
0x1400772e7  mov     ecx, [r15]
0x1400772ea  dec     rcx
0x1400772ed  add     rcx, r12
0x1400772f0  cmp     rcx, r14
0x1400772f3  jb      short loc_140077347
0x1400772f5  mov     ebx, 0C000000Dh
0x1400772fa  mov     r8d, 8C5h
0x140077300  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077307  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x14007730e  call    VidTraceErrorInternal0
0x140077313  jmp     loc_140077743
0x140077318  lea     rax, [r13-1]
0x14007731c  add     rax, r14
0x14007731f  cmp     rax, r12
0x140077322  jb      short loc_140077347
0x140077324  mov     ebx, 0C000000Dh
0x140077329  mov     r8d, 8D0h
0x14007732f  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077336  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x14007733d  call    VidTraceErrorInternal0
0x140077342  jmp     loc_140077743
0x140077347  mov     [rsp+98h+Irp], 0; Irp
0x140077350  xor     r9d, r9d; ChargeQuota
0x140077353  xor     r8d, r8d; SecondaryBuffer
0x140077356  mov     edx, r13d; Length
0x140077359  mov     rcx, r14; VirtualAddress
0x14007735c  call    cs:__imp_IoAllocateMdl
0x140077363  nop     dword ptr [rax+rax+00h]
0x140077368  mov     rdi, rax
0x14007736b  mov     [rsp+98h+var_48], rax
0x140077370  test    rax, rax
0x140077373  jnz     short loc_140077398
0x140077375  mov     ebx, 0C000009Ah
0x14007737a  mov     r8d, 8D9h
0x140077380  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077387  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x14007738e  call    VidTraceErrorInternal0
0x140077393  jmp     loc_140077743
0x140077398  xor     r8d, r8d; Operation
0x14007739b  xor     edx, edx; AccessMode
0x14007739d  mov     rcx, rdi; MemoryDescriptorList
0x1400773a0  call    cs:__imp_MmProbeAndLockPages
0x1400773a7  nop     dword ptr [rax+rax+00h]
0x1400773ac  nop
0x1400773ad  mov     [rsp+98h+arg_18], 1
0x1400773b5  test    byte ptr [rdi+0Ah], 5
0x1400773b9  jz      short loc_1400773C1
0x1400773bb  mov     r14, [rdi+18h]
0x1400773bf  jmp     short loc_1400773EC
0x1400773c1  mov     [rsp+98h+Priority], 40000010h; Priority
0x1400773c9  mov     dword ptr [rsp+98h+Irp], 0; BugCheckOnFailure
0x1400773d1  xor     r9d, r9d; RequestedAddress
0x1400773d4  xor     edx, edx; AccessMode
0x1400773d6  lea     r8d, [r9+1]; CacheType
0x1400773da  mov     rcx, rdi; MemoryDescriptorList
0x1400773dd  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400773e4  nop     dword ptr [rax+rax+00h]
0x1400773e9  mov     r14, rax
0x1400773ec  test    r14, r14
0x1400773ef  jnz     short loc_140077414
0x1400773f1  mov     ebx, 0C000009Ah
0x1400773f6  mov     r8d, 8EEh
0x1400773fc  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077403  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x14007740a  call    VidTraceErrorInternal0
0x14007740f  jmp     loc_140077743
0x140077414  mov     eax, [r15]
0x140077417  mov     [rsp+98h+var_54], eax
0x14007741b  mov     rcx, qword ptr [rsp+98h+arg_0]; int
0x140077423  cmp     [rsp+98h+arg_28], 0
0x14007742b  jz      short loc_14007744B
0x14007742d  mov     dword ptr [rsp+98h+Size], r13d; Size
0x140077432  mov     qword ptr [rsp+98h+Priority], r14; Src
0x140077437  lea     rax, [rsp+98h+var_54]
0x14007743c  mov     [rsp+98h+Irp], rax; __int64
0x140077441  xor     r9d, r9d; int
0x140077444  call    VsmmCryptPackWithHeader
0x140077449  jmp     short loc_14007746A
0x14007744b  mov     al, [rsp+98h+arg_30]
0x140077452  mov     byte ptr [rsp+98h+Priority], al
0x140077456  mov     dword ptr [rsp+98h+Irp], r13d
0x14007745b  mov     r9, r14
0x14007745e  lea     r8, [rsp+98h+var_54]
0x140077463  xor     edx, edx
0x140077465  call    VsmmCryptUnpackWithHeader
0x14007746a  mov     [rsp+98h+var_54+4], eax
0x14007746e  mov     ebx, eax
0x140077470  test    eax, eax
0x140077472  jns     short loc_140077492
0x140077474  mov     r8d, 910h
0x14007747a  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077481  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x140077488  call    VidTraceErrorInternal0
0x14007748d  jmp     loc_140077743
0x140077492  test    r12, r12
0x140077495  jz      loc_140077650
0x14007749b  mov     edx, [r15]; Length
0x14007749e  cmp     edx, [rsp+98h+var_54]
0x1400774a2  jb      loc_140077650
0x1400774a8  mov     [rsp+98h+Irp], 0; Irp
0x1400774b1  xor     r9d, r9d; ChargeQuota
0x1400774b4  xor     r8d, r8d; SecondaryBuffer
0x1400774b7  mov     rcx, r12; VirtualAddress
0x1400774ba  call    cs:__imp_IoAllocateMdl
0x1400774c1  nop     dword ptr [rax+rax+00h]
0x1400774c6  mov     rsi, rax
0x1400774c9  mov     [rsp+98h+var_40], rax
0x1400774ce  test    rax, rax
0x1400774d1  jnz     short loc_1400774F6
0x1400774d3  mov     ebx, 0C000009Ah
0x1400774d8  mov     r8d, 92Ah
0x1400774de  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400774e5  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x1400774ec  call    VidTraceErrorInternal0
0x1400774f1  jmp     loc_140077743
0x1400774f6  mov     ebx, 1
0x1400774fb  mov     r8d, ebx; Operation
0x1400774fe  xor     edx, edx; AccessMode
0x140077500  mov     rcx, rsi; MemoryDescriptorList
0x140077503  call    cs:__imp_MmProbeAndLockPages
0x14007750a  nop     dword ptr [rax+rax+00h]
0x14007750f  nop
0x140077510  mov     [rsp+98h+var_58], bl
0x140077514  test    byte ptr [rsi+0Ah], 5
0x140077518  jz      short loc_140077520
0x14007751a  mov     rax, [rsi+18h]
0x14007751e  jmp     short loc_140077547
0x140077520  mov     [rsp+98h+Priority], 40000010h; Priority
0x140077528  mov     dword ptr [rsp+98h+Irp], 0; BugCheckOnFailure
0x140077530  xor     r9d, r9d; RequestedAddress
0x140077533  mov     r8d, ebx; CacheType
0x140077536  xor     edx, edx; AccessMode
0x140077538  mov     rcx, rsi; MemoryDescriptorList
0x14007753b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140077542  nop     dword ptr [rax+rax+00h]
0x140077547  test    rax, rax
0x14007754a  jnz     short loc_14007756F
0x14007754c  mov     ebx, 0C000009Ah
0x140077551  mov     r8d, 93Fh
0x140077557  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x14007755e  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x140077565  call    VidTraceErrorInternal0
0x14007756a  jmp     loc_140077743
0x14007756f  cmp     [rsp+98h+arg_28], 0
0x140077577  jz      short loc_14007759F
0x140077579  mov     dword ptr [rsp+98h+Size], r13d; Size
0x14007757e  mov     qword ptr [rsp+98h+Priority], r14; Src
0x140077583  lea     rcx, [rsp+98h+var_54]
0x140077588  mov     [rsp+98h+Irp], rcx; __int64
0x14007758d  mov     r9, rax; int
0x140077590  mov     rcx, qword ptr [rsp+98h+arg_0]; int
0x140077598  call    VsmmCryptPackWithHeader
0x14007759d  jmp     short loc_1400775C7
0x14007759f  mov     cl, [rsp+98h+arg_30]
0x1400775a6  mov     byte ptr [rsp+98h+Priority], cl
0x1400775aa  mov     dword ptr [rsp+98h+Irp], r13d
0x1400775af  mov     r9, r14
0x1400775b2  lea     r8, [rsp+98h+var_54]
0x1400775b7  mov     rdx, rax
0x1400775ba  mov     rcx, qword ptr [rsp+98h+arg_0]
0x1400775c2  call    VsmmCryptUnpackWithHeader
0x1400775c7  mov     ebx, eax
0x1400775c9  test    eax, eax
0x1400775cb  jns     short loc_1400775EB
0x1400775cd  mov     r8d, 95Dh
0x1400775d3  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400775da  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x1400775e1  call    VidTraceErrorInternal0
0x1400775e6  jmp     loc_140077743
0x1400775eb  mov     eax, [r15]
0x1400775ee  cmp     [rsp+98h+var_54], eax
0x1400775f2  jbe     short loc_140077617
0x1400775f4  mov     ebx, 0C0000023h
0x1400775f9  mov     r8d, 968h
0x1400775ff  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077606  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x14007760d  call    VidTraceErrorInternal0
0x140077612  jmp     loc_140077743
0x140077617  xor     ebx, ebx
0x140077619  jmp     loc_140077743
0x14007761e  mov     ebx, eax
0x140077620  mov     r8d, 935h
0x140077626  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x14007762d  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x140077634  call    VidTraceErrorInternal0
0x140077639  mov     r15, [rsp+98h+arg_10]
0x140077641  mov     rdi, [rsp+98h+var_48]
0x140077646  mov     rsi, [rsp+98h+var_40]
0x14007764b  jmp     loc_140077743
0x140077650  mov     ebx, 0C0000023h
0x140077655  mov     r8d, 922h
0x14007765b  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077662  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x140077669  call    VidTraceErrorInternal0
0x14007766e  jmp     loc_140077743
0x140077673  mov     ebx, eax
0x140077675  mov     [rsp+98h+var_54+4], eax
0x140077679  mov     r8d, 917h
0x14007767f  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077686  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x14007768d  call    VidTraceErrorInternal0
0x140077692  mov     r15, [rsp+98h+arg_10]
0x14007769a  mov     rdi, [rsp+98h+var_48]
0x14007769f  mov     rsi, [rsp+98h+var_40]
0x1400776a4  jmp     loc_140077743
0x1400776a9  mov     ebx, eax
0x1400776ab  mov     r8d, 8E4h
0x1400776b1  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400776b8  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x1400776bf  call    VidTraceErrorInternal0
0x1400776c4  mov     r15, [rsp+98h+arg_10]
0x1400776cc  mov     rdi, [rsp+98h+var_48]
0x1400776d1  mov     rsi, [rsp+98h+var_40]
0x1400776d6  jmp     short loc_140077743
0x1400776d8  mov     ebx, eax
0x1400776da  mov     r8d, 8B0h
0x1400776e0  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400776e7  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x1400776ee  call    VidTraceErrorInternal0
0x1400776f3  mov     r15, [rsp+98h+arg_10]
0x1400776fb  mov     rdi, [rsp+98h+var_48]
0x140077700  mov     rsi, rdi
0x140077703  jmp     short loc_140077743
0x140077705  mov     ebx, 0C0000022h
0x14007770a  mov     r8d, 8A0h
0x140077710  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077717  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x14007771e  call    VidTraceErrorInternal0
0x140077723  jmp     short loc_140077743
0x140077725  mov     ebx, 0C0000206h
0x14007772a  mov     r8d, 898h
0x140077730  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077737  lea     rcx, aVsmmcryptencry; "VsmmCryptEncryptDecryptData"
0x14007773e  call    VidTraceErrorInternal0
0x140077743  cmp     [rsp+98h+arg_18], 0
0x14007774b  jz      short loc_14007775C
0x14007774d  mov     rcx, rdi; MemoryDescriptorList
0x140077750  call    cs:__imp_MmUnlockPages
0x140077757  nop     dword ptr [rax+rax+00h]
0x14007775c  cmp     [rsp+98h+var_58], 0
0x140077761  jz      short loc_140077772
0x140077763  mov     rcx, rsi; MemoryDescriptorList
  ... truncated ...
```
