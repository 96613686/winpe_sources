# IumCreateSecureSection

- ea: `0x14005bd70`
- end: `0x14005c1d9`
- name: `IumCreateSecureSection`
- size: `1129`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x140002ef0`
- `0x140003780`
- `0x140009940`
- `0x14000c8d0`
- `0x140027540`
- `0x14002b534`
- `0x14003492c`
- `0x14005bd70`
- `0x14005e988`
- `0x140081290`
- `0x14008793c`
- `0x140087b9c`
- `0x1400a0c00`
- `0x1400a0df8`
- `0x1400f2fc0`
- `0x1400f9a80`
- `0x1400fc664`
- `0x1400fc7c0`

## pseudocode

```c
__int64 __fastcall IumCreateSecureSection(_QWORD *a1, int a2, __int64 a3, int a4, unsigned int a5, int a6)
{
  int v8; // r10d
  char v10; // dl
  _QWORD *StackBase; // rax
  __int64 v12; // rax
  __int64 result; // rax
  bool v14; // r12
  __int64 ULong64FromUser; // rax
  _QWORD *v16; // rax
  __int64 v17; // rdx
  int v18; // r14d
  __int64 v19; // rsi
  __int16 ProtectionMask; // ax
  __int64 v21; // rdx
  unsigned int v22; // r9d
  int v23; // r8d
  __int64 v24; // r15
  __int64 v25; // r12
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned __int64 v29; // rbx
  __int64 HyperspacePte; // r12
  __int64 PteTrace; // rax
  PVOID *v32; // r13
  PVOID v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  _QWORD *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rdx
  int v39; // ecx
  __int64 v40; // rcx
  char v41; // [rsp+30h] [rbp-58h]
  bool v42; // [rsp+34h] [rbp-54h]
  int v43; // [rsp+38h] [rbp-50h]
  ULONG BackTraceHash; // [rsp+3Ch] [rbp-4Ch] BYREF
  _DWORD *v45; // [rsp+40h] [rbp-48h] BYREF
  __int64 v46; // [rsp+48h] [rbp-40h] BYREF
  __int64 v47; // [rsp+50h] [rbp-38h]
  __int64 CurrentIrql; // [rsp+58h] [rbp-30h]
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+0h]

  v8 = a2;
  v10 = *((_BYTE *)KeGetPcr()->NtTib.StackBase + 96);
  v41 = v10;
  if ( v10 )
  {
    StackBase = KeGetPcr()->NtTib.StackBase;
    v12 = StackBase ? StackBase[10] : 0LL;
    if ( (*(_BYTE *)(v12 + 400) & 1) == 0 )
      return 3221225506LL;
  }
  v14 = 0;
  v42 = 0;
  v46 = 0;
  v45 = 0;
  if ( v10 )
  {
    ULong64FromUser = RtlReadULong64FromUser(a1);
    RtlWriteULong64ToUser(a1, ULong64FromUser);
    v8 = a2;
  }
  else
  {
    v16 = KeGetPcr()->NtTib.StackBase;
    if ( v16 )
      v17 = v16[10];
    else
      v17 = 0;
    v14 = v17 == PsIumSystemProcess;
    v42 = v17 == PsIumSystemProcess;
  }
  if ( !a3 )
    return 3221225713LL;
  if ( ((a4 - 1) & 0xFFFFFFFC) != 0 || a4 == 3 || ((a5 - 1) & 0xFFFFFFFC) != 0 || a5 == 3 )
    return 3221225541LL;
  if ( (a6 & 0xFFFFFFF9) != 0 || (a6 & 4) != 0 && (a6 & 2) == 0 )
    return 3221225716LL;
  result = SkmmCreateSecureSection(v8, 0, a3, a4, (__int64)&v45);
  v18 = result;
  if ( (int)result >= 0 )
  {
    v43 = 0;
    v19 = (__int64)v45;
    if ( (a6 & 2) != 0 )
    {
      *v45 |= 0x20000u;
      v43 = 6;
    }
    if ( (a6 & 4) != 0 )
      *(_DWORD *)v19 |= 0x10000u;
    *(_DWORD *)v19 &= ~0x8000u;
    ProtectionMask = SkmiMakeProtectionMask(a5);
    *(_DWORD *)v19 = v23 ^ ((unsigned __int16)v23 ^ (unsigned __int16)(ProtectionMask << 9)) & 0x1E00;
    if ( !v22 )
      goto LABEL_52;
    LODWORD(v24) = 0;
    if ( *(_DWORD *)(v19 + 4) )
    {
      do
      {
        v25 = *(_QWORD *)(*(_QWORD *)(v19 + 8) + 8LL * (unsigned int)v24) >> 12;
        v18 = SkmiClaimTrustedPage(v25 & 0xFFFFFFFFFFLL, 0, v22);
        if ( v18 < 0 )
          break;
        if ( (*(_DWORD *)v19 & 0x10000) != 0 )
        {
          v29 = (v25 << 12)
              ^ ((v25 << 12)
               ^ ((v25 & 0xFFFFFFFFFFLL) << 12))
              & 0xFFF0000000000FFFuLL
              ^ 0x800000000000007BuLL
              | 0x18;
          CurrentIrql = KeGetCurrentIrql();
          __writecr8(2u);
          HyperspacePte = SkmiGetHyperspacePte(v26, v21, v27, v28);
          PteTrace = SkmiGetPteTrace(0, HyperspacePte, 0, v29, *(_QWORD *)HyperspacePte);
          v47 = PteTrace;
          if ( PteTrace )
          {
            v32 = (PVOID *)(PteTrace + 32);
            memset_0((void *)(PteTrace + 32), 0, 0x40u);
            if ( (SkmiFlags & 0x400000) != 0 )
            {
              v33 = KeGetPcr()->NtTib.StackBase;
              if ( v33 )
              {
                if ( !RtlCaptureStackBackTrace((ULONG)v33, 8u, v32, &BackTraceHash) )
                {
                  v35 = v47;
                  *(_QWORD *)(v47 + 40) = retaddr;
                  *v32 = (PVOID)SkmiGetInstructionPointer(v35, v34);
                }
              }
            }
          }
          if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
            && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
          {
            v36 = KeGetPcr()->NtTib.StackBase;
            v37 = v36 ? v36[10] : 0LL;
            v38 = *(_QWORD *)(v37 + 232);
            if ( v38 )
            {
              v39 = SkiKvaShadowMode;
              *(_QWORD *)(v38 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v29;
              if ( v39 != 2 && (v29 & 1) != 0 )
                v29 |= 0x8000000000000000uLL;
            }
          }
          *(_QWORD *)HyperspacePte = v29;
          SkeCacheInvalidatePage(HyperspacePte << 25 >> 16);
          SkmiReleaseHyperspacePte(HyperspacePte);
          LOBYTE(v40) = CurrentIrql;
          SkeLowerIrql(v40);
        }
        LODWORD(v24) = v24 + 1;
        v22 = v43;
      }
      while ( (unsigned int)v24 < *(_DWORD *)(v19 + 4) );
      v14 = v42;
    }
    if ( v18 < 0 )
    {
      while ( (_DWORD)v24 )
      {
        v24 = (unsigned int)(v24 - 1);
        SkmiReleaseTrustedPage((*(_QWORD *)(*(_QWORD *)(v19 + 8) + 8 * v24) >> 12) & 0xFFFFFFFFFFLL);
      }
      *(_DWORD *)v19 &= ~0x20000u;
    }
    else
    {
LABEL_52:
      LOBYTE(v21) = v14;
      v18 = SkobCreateHandle(v19, v21, 0, &v46);
      if ( v18 >= 0 )
      {
        if ( v41 )
          RtlWriteULong64ToUser(a1, v46);
        else
          *a1 = v46;
        v46 = 0;
      }
    }
    if ( v46 )
      SkobCloseHandleEx(v46, 0, 0, 0, 0);
    SkobDereferenceObject(v19);
    return (unsigned int)v18;
  }
  return result;
}

```

## disassembly

```asm
0x14005bd70  mov     rax, rsp
0x14005bd73  mov     [rax+18h], rbx
0x14005bd77  mov     [rax+20h], rsi
0x14005bd7b  mov     [rax+10h], rdx
0x14005bd7f  mov     [rax+8], rcx
0x14005bd83  push    rdi
0x14005bd84  push    r12
0x14005bd86  push    r13
0x14005bd88  push    r14
0x14005bd8a  push    r15
0x14005bd8c  sub     rsp, 60h
0x14005bd90  mov     esi, r9d
0x14005bd93  mov     r14, r8
0x14005bd96  mov     r10, rdx
0x14005bd99  mov     rbx, rcx
0x14005bd9c  mov     rax, gs:8
0x14005bda5  mov     dl, [rax+60h]
0x14005bda8  mov     [rsp+88h+var_58], dl
0x14005bdac  xor     edi, edi
0x14005bdae  test    dl, dl
0x14005bdb0  jz      short loc_14005BDE0
0x14005bdb2  mov     rax, gs:8
0x14005bdbb  test    rax, rax
0x14005bdbe  jz      short loc_14005BDC6
0x14005bdc0  mov     rax, [rax+50h]
0x14005bdc4  jmp     short loc_14005BDC9
0x14005bdc6  mov     rax, rdi
0x14005bdc9  mov     ecx, 1
0x14005bdce  test    [rax+190h], cl
0x14005bdd4  jnz     short loc_14005BDE5
0x14005bdd6  mov     eax, 0C0000022h
0x14005bddb  jmp     loc_14005C1BE
0x14005bde0  mov     ecx, 1
0x14005bde5  mov     r12b, dil
0x14005bde8  mov     [rsp+88h+var_54], r12d
0x14005bded  mov     [rsp+88h+var_40], rdi
0x14005bdf2  mov     [rsp+88h+var_48], rdi
0x14005bdf7  test    dl, dl
0x14005bdf9  jz      short loc_14005BE1D
0x14005bdfb  mov     rcx, rbx
0x14005bdfe  call    RtlReadULong64FromUser
0x14005be03  mov     rdx, rax
0x14005be06  mov     rcx, rbx
0x14005be09  call    RtlWriteULong64ToUser
0x14005be0e  mov     r10, [rsp+88h+arg_8]
0x14005be16  jmp     short loc_14005BE48
0x14005be18  jmp     loc_14005C1BE
0x14005be1d  mov     rax, gs:8
0x14005be26  test    rax, rax
0x14005be29  jz      short loc_14005BE31
0x14005be2b  mov     rdx, [rax+50h]
0x14005be2f  jmp     short loc_14005BE34
0x14005be31  mov     rdx, rdi
0x14005be34  movzx   r12d, r12b
0x14005be38  cmp     rdx, cs:PsIumSystemProcess
0x14005be3f  cmovz   r12d, ecx
0x14005be43  mov     [rsp+88h+var_54], r12d
0x14005be48  test    r14, r14
0x14005be4b  jnz     short loc_14005BE57
0x14005be4d  mov     eax, 0C00000F1h
0x14005be52  jmp     loc_14005C1BE
0x14005be57  lea     eax, [rsi-1]
0x14005be5a  mov     ecx, 0FFFFFFFCh
0x14005be5f  test    ecx, eax
0x14005be61  jnz     loc_14005C1B9
0x14005be67  cmp     esi, 3
0x14005be6a  jz      loc_14005C1B9
0x14005be70  mov     r13d, [rsp+88h+arg_20]
0x14005be78  lea     eax, [r13-1]
0x14005be7c  test    ecx, eax
0x14005be7e  jnz     loc_14005C1B9
0x14005be84  cmp     r13d, 3
0x14005be88  jz      loc_14005C1B9
0x14005be8e  mov     ebx, [rsp+88h+arg_28]
0x14005be95  test    ebx, 0FFFFFFF9h
0x14005be9b  jnz     loc_14005C1B2
0x14005bea1  mov     r15d, ebx
0x14005bea4  and     ebx, 2
0x14005bea7  and     r15d, 4
0x14005beab  jz      short loc_14005BEB5
0x14005bead  test    ebx, ebx
0x14005beaf  jz      loc_14005C1B2
0x14005beb5  lea     rax, [rsp+88h+var_48]
0x14005beba  mov     [rsp+88h+var_68], rax
0x14005bebf  mov     r9d, esi
0x14005bec2  mov     r8, r14
0x14005bec5  xor     edx, edx
0x14005bec7  mov     rcx, r10
0x14005beca  call    SkmmCreateSecureSection
0x14005becf  mov     r14d, eax
0x14005bed2  test    eax, eax
0x14005bed4  js      loc_14005C1BE
0x14005beda  mov     r9d, edi
0x14005bedd  mov     [rsp+88h+var_50], edi
0x14005bee1  mov     rsi, [rsp+88h+var_48]
0x14005bee6  test    ebx, ebx
0x14005bee8  jz      short loc_14005BEF9
0x14005beea  bts     dword ptr [rsi], 11h
0x14005beee  mov     r9d, 6
0x14005bef4  mov     [rsp+88h+var_50], r9d
0x14005bef9  test    r15d, r15d
0x14005befc  jz      short loc_14005BF02
0x14005befe  bts     dword ptr [rsi], 10h
0x14005bf02  btr     dword ptr [rsi], 0Fh
0x14005bf06  mov     r8d, [rsi]
0x14005bf09  mov     ecx, r13d
0x14005bf0c  call    SkmiMakeProtectionMask
0x14005bf11  shl     eax, 9
0x14005bf14  xor     eax, r8d
0x14005bf17  and     eax, 1E00h
0x14005bf1c  xor     eax, r8d
0x14005bf1f  mov     [rsi], eax
0x14005bf21  test    r9d, r9d
0x14005bf24  jz      loc_14005C13D
0x14005bf2a  mov     r15d, edi
0x14005bf2d  mov     r13, 0FFFFFFFFFFh
0x14005bf37  cmp     [rsi+4], edi
0x14005bf3a  jbe     loc_14005C103
0x14005bf40  mov     ecx, r15d
0x14005bf43  mov     rax, [rsi+8]
0x14005bf47  mov     r12, [rax+rcx*8]
0x14005bf4b  shr     r12, 0Ch
0x14005bf4f  mov     rbx, r12
0x14005bf52  and     rbx, r13
0x14005bf55  mov     r8d, r9d
0x14005bf58  xor     edx, edx
0x14005bf5a  mov     rcx, rbx
0x14005bf5d  call    SkmiClaimTrustedPage
0x14005bf62  mov     r14d, eax
0x14005bf65  test    eax, eax
0x14005bf67  js      loc_14005C0FE
0x14005bf6d  test    dword ptr [rsi], 10000h
0x14005bf73  jz      loc_14005C0EC
0x14005bf79  shl     r12, 0Ch
0x14005bf7d  shl     rbx, 0Ch
0x14005bf81  xor     rbx, r12
0x14005bf84  mov     rax, 0FFF0000000000FFFh
0x14005bf8e  and     rbx, rax
0x14005bf91  xor     rbx, r12
0x14005bf94  mov     rax, 800000000000007Bh
0x14005bf9e  xor     rbx, rax
0x14005bfa1  or      rbx, 18h
0x14005bfa5  mov     rax, cr8
0x14005bfa9  mov     [rsp+88h+var_30], rax
0x14005bfae  mov     eax, 2
0x14005bfb3  mov     cr8, rax
0x14005bfb7  call    SkmiGetHyperspacePte
0x14005bfbc  mov     r12, rax
0x14005bfbf  mov     rcx, [rax]
0x14005bfc2  mov     [rsp+88h+var_68], rcx
0x14005bfc7  mov     r9, rbx
0x14005bfca  xor     r8d, r8d
0x14005bfcd  mov     rdx, rax
0x14005bfd0  xor     ecx, ecx
0x14005bfd2  call    SkmiGetPteTrace
0x14005bfd7  mov     [rsp+88h+var_38], rax
0x14005bfdc  test    rax, rax
0x14005bfdf  jz      short loc_14005C048
0x14005bfe1  lea     r13, [rax+20h]
0x14005bfe5  xor     edx, edx; Val
0x14005bfe7  lea     r8d, [rdx+40h]; Size
0x14005bfeb  mov     rcx, r13; void *
0x14005bfee  call    memset_0
0x14005bff3  test    cs:SkmiFlags, 400000h
0x14005bffd  jz      short loc_14005C03E
0x14005bfff  mov     rcx, gs:8; FramesToSkip
0x14005c008  test    rcx, rcx
0x14005c00b  jz      short loc_14005C03E
0x14005c00d  lea     r9, [rsp+88h+BackTraceHash]; BackTraceHash
0x14005c012  mov     r8, r13; BackTrace
0x14005c015  mov     edx, 8; FramesToCapture
0x14005c01a  call    RtlCaptureStackBackTrace
0x14005c01f  test    ax, ax
0x14005c022  jnz     short loc_14005C03E
0x14005c024  mov     rax, [rsp+88h]
0x14005c02c  mov     rcx, [rsp+88h+var_38]
0x14005c031  mov     [rcx+28h], rax
0x14005c035  call    SkmiGetInstructionPointer
0x14005c03a  mov     [r13+0], rax
0x14005c03e  mov     r13, 0FFFFFFFFFFh
0x14005c048  mov     rax, 0FFFFF6FB7DBED000h
0x14005c052  cmp     r12, rax
0x14005c055  jb      short loc_14005C0B6
0x14005c057  mov     rax, 0FFFFF6FB7DBED800h
0x14005c061  cmp     r12, rax
0x14005c064  jnb     short loc_14005C0B6
0x14005c066  mov     rax, gs:8
0x14005c06f  test    rax, rax
0x14005c072  jz      short loc_14005C07A
0x14005c074  mov     rcx, [rax+50h]
0x14005c078  jmp     short loc_14005C07D
0x14005c07a  mov     rcx, rdi
0x14005c07d  mov     rdx, [rcx+0E8h]
0x14005c084  test    rdx, rdx
0x14005c087  jz      short loc_14005C0B6
0x14005c089  mov     ecx, cs:SkiKvaShadowMode
0x14005c08f  mov     rax, r12
0x14005c092  sar     rax, 3
0x14005c096  and     eax, 1FFh
0x14005c09b  mov     [rdx+rax*8], rbx
0x14005c09f  cmp     ecx, 2
0x14005c0a2  jz      short loc_14005C0B6
0x14005c0a4  test    bl, 1
0x14005c0a7  jz      short loc_14005C0B6
0x14005c0a9  mov     rax, 8000000000000000h
0x14005c0b3  or      rbx, rax
0x14005c0b6  mov     [r12], rbx
0x14005c0ba  mov     rcx, r12
0x14005c0bd  shl     rcx, 19h
0x14005c0c1  mov     rax, 0FFFFF68000000000h
0x14005c0cb  shl     rax, 19h
0x14005c0cf  sub     rcx, rax
0x14005c0d2  sar     rcx, 10h
0x14005c0d6  call    SkeCacheInvalidatePage
0x14005c0db  mov     rcx, r12
0x14005c0de  call    SkmiReleaseHyperspacePte
0x14005c0e3  mov     cl, byte ptr [rsp+88h+var_30]
0x14005c0e7  call    SkeLowerIrql
0x14005c0ec  inc     r15d
0x14005c0ef  cmp     r15d, [rsi+4]
0x14005c0f3  mov     r9d, [rsp+88h+var_50]
0x14005c0f8  jb      loc_14005BF40
0x14005c0fe  mov     r12d, [rsp+88h+var_54]
0x14005c103  test    r14d, r14d
0x14005c106  jns     short loc_14005C13D
0x14005c108  test    r15d, r15d
0x14005c10b  jz      short loc_14005C134
0x14005c10d  dec     r15d
0x14005c110  mov     rax, [rsi+8]
0x14005c114  mov     rcx, [rax+r15*8]
0x14005c118  shr     rcx, 0Ch
0x14005c11c  and     rcx, r13; BugCheckParameter3
0x14005c11f  xor     edx, edx
0x14005c121  lea     r8d, [rdx+2]
0x14005c125  call    SkmiReleaseTrustedPage
0x14005c12a  test    r15d, r15d
0x14005c12d  jnz     short loc_14005C10D
0x14005c12f  mov     r12d, [rsp+88h+var_54]
0x14005c134  btr     dword ptr [rsi], 11h
0x14005c138  test    r14d, r14d
0x14005c13b  js      short loc_14005C189
0x14005c13d  lea     r9, [rsp+88h+var_40]
0x14005c142  xor     r8d, r8d
0x14005c145  mov     dl, r12b
0x14005c148  mov     rcx, rsi
0x14005c14b  call    SkobCreateHandle
0x14005c150  mov     r14d, eax
0x14005c153  test    eax, eax
0x14005c155  js      short loc_14005C189
0x14005c157  mov     rax, [rsp+88h+var_40]
0x14005c15c  mov     rcx, [rsp+88h+arg_0]
0x14005c164  cmp     [rsp+88h+var_58], dil
0x14005c169  jz      short loc_14005C175
0x14005c16b  mov     rdx, rax
0x14005c16e  call    RtlWriteULong64ToUser
0x14005c173  jmp     short loc_14005C178
0x14005c175  mov     [rcx], rax
0x14005c178  mov     [rsp+88h+var_40], rdi
0x14005c17d  jmp     short loc_14005C189
0x14005c17f  mov     r14d, eax
0x14005c182  xor     edi, edi
0x14005c184  mov     rsi, [rsp+88h+var_48]
0x14005c189  mov     rcx, [rsp+88h+var_40]
0x14005c18e  test    rcx, rcx
0x14005c191  jz      short loc_14005C1A5
0x14005c193  mov     [rsp+88h+var_68], rdi
0x14005c198  xor     r9d, r9d
0x14005c19b  xor     r8d, r8d
0x14005c19e  xor     edx, edx
0x14005c1a0  call    SkobCloseHandleEx
0x14005c1a5  mov     rcx, rsi
0x14005c1a8  call    SkobDereferenceObject
0x14005c1ad  mov     eax, r14d
0x14005c1b0  jmp     short loc_14005C1BE
0x14005c1b2  mov     eax, 0C00000F4h
0x14005c1b7  jmp     short loc_14005C1BE
0x14005c1b9  mov     eax, 0C0000045h
0x14005c1be  lea     r11, [rsp+88h+var_28]
0x14005c1c3  mov     rbx, [r11+40h]
0x14005c1c7  mov     rsi, [r11+48h]
0x14005c1cb  mov     rsp, r11
0x14005c1ce  pop     r15
0x14005c1d0  pop     r14
0x14005c1d2  pop     r13
0x14005c1d4  pop     r12
0x14005c1d6  pop     rdi
0x14005c1d7  retn
```
