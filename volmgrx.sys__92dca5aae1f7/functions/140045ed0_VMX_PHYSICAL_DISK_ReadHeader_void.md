# VMX_PHYSICAL_DISK::ReadHeader(void)

- ea: `0x140045ed0`
- end: `0x1400462e5`
- name: `?ReadHeader@VMX_PHYSICAL_DISK@@AEAAXXZ`
- size: `1045`
- prototype: `void __fastcall(VMX_PHYSICAL_DISK *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14003261c`

## callees

- `0x140005f80`
- `0x140005fb0`
- `0x14001be80`
- `0x140045ed0`
- `0x1400465b0`
- `0x1400468ac`
- `0x140047e38`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400461d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046214`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004624b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400462bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400461d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046214`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004624b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400462bf`
- `ntoskrnl!RtlCompareMemory` at `0x140045ffc`
- `ntoskrnl!RtlCompareMemory` at `0x1400460fe`
- `ntoskrnl!RtlCompareMemory` at `0x140045ffc`
- `ntoskrnl!RtlCompareMemory` at `0x1400460fe`

## pseudocode

```c
void __fastcall VMX_PHYSICAL_DISK::ReadHeader(VMX_PHYSICAL_DISK *this)
{
  VMX_DISK_HEADER *v1; // r14
  VMX_DISK_HEADER *v2; // rsi
  unsigned __int8 *v3; // rbx
  __int64 v5; // rax
  char v6; // r13
  int v7; // r12d
  int Sectors; // eax
  VMX_DISK_HEADER *v9; // rax
  unsigned __int8 *v10; // r15
  unsigned int v11; // r8d
  VMX_DISK_HEADER *v12; // rcx
  char v13; // r12
  bool v14; // r15
  int v15; // eax
  unsigned __int8 *v16; // r15
  VMX_DISK_HEADER *v17; // rax
  unsigned int v18; // r8d
  unsigned __int64 v19; // rdx
  int v20; // eax
  void *v21; // rax
  VMX_DISK_HEADER *v22; // r15
  unsigned int v23; // r8d
  unsigned __int8 *v24; // [rsp+20h] [rbp-28h] BYREF
  void *Source2; // [rsp+28h] [rbp-20h] BYREF
  PVOID P; // [rsp+30h] [rbp-18h] BYREF
  void *Source1; // [rsp+38h] [rbp-10h] BYREF
  char v28; // [rsp+90h] [rbp+48h]
  int i; // [rsp+98h] [rbp+50h]
  VMX_DISK_HEADER *v30; // [rsp+A0h] [rbp+58h]
  void *v31; // [rsp+A8h] [rbp+60h]

  v31 = 0;
  v1 = 0;
  v30 = 0;
  v2 = 0;
  Source1 = 0;
  v3 = 0;
  P = 0;
  v5 = *((_QWORD *)this + 2);
  v6 = 0;
  Source2 = 0;
  v7 = *(_DWORD *)(v5 + 36);
  for ( i = v7; ; v7 = i )
  {
    Sectors = VMX_PHYSICAL_DISK::ReadSectors(this, *((_QWORD *)this + 8), 1u, (unsigned __int8 **)&Source1);
    if ( Sectors >= 0 )
    {
      v9 = (VMX_DISK_HEADER *)VMX_ALLOCATED_OBJECT::operator new(0x138u, 0x102u, 0x68446D56u);
      v1 = v9;
      if ( !v9 )
      {
        v1 = 0;
        goto LABEL_11;
      }
      memset(v9, 0, 0x138u);
      v10 = (unsigned __int8 *)Source1;
      v24 = (unsigned __int8 *)Source1;
      Sectors = VMX_DISK_HEADER::Unformat(v1, &v24, v11);
      if ( Sectors >= 0 )
      {
        if ( *((_DWORD *)v1 + 30) == v7 && *((_QWORD *)v1 + 3) + *((_QWORD *)v1 + 19) == *((_QWORD *)this + 8) )
        {
          v30 = v1;
          v3 = v10;
          v28 = 0;
        }
        else
        {
LABEL_14:
          v28 = 1;
        }
        v15 = VMX_PHYSICAL_DISK::ReadSectors(this, *((_QWORD *)this + 9), 1u, (unsigned __int8 **)&Source2);
        if ( v15 >= 0 )
        {
          v16 = (unsigned __int8 *)Source2;
          if ( v3 )
          {
            v13 = 0;
            if ( RtlCompareMemory(v3, Source2, 0x200u) == 512 )
              goto LABEL_30;
          }
          v17 = (VMX_DISK_HEADER *)VMX_ALLOCATED_OBJECT::operator new(0x138u, 0x102u, 0x68446D56u);
          v2 = v17;
          if ( !v17 )
          {
            v2 = 0;
LABEL_28:
            v12 = 0;
            goto LABEL_12;
          }
          memset(v17, 0, 0x138u);
          v24 = v16;
          v15 = VMX_DISK_HEADER::Unformat(v2, &v24, v18);
          if ( v15 >= 0 )
          {
            if ( *((_DWORD *)v2 + 30) == i && *((_QWORD *)v2 + 4) + *((_QWORD *)v2 + 19) == *((_QWORD *)this + 9) )
            {
              v12 = v30;
              if ( v30 && *((_QWORD *)v30 + 2) >= *((_QWORD *)v2 + 2) )
              {
                v13 = 1;
              }
              else
              {
                v12 = v2;
                v28 = 1;
                v30 = v2;
                v3 = v16;
                v13 = 0;
              }
            }
            else
            {
LABEL_29:
              v13 = 1;
LABEL_30:
              v12 = v30;
            }
            v19 = *((_QWORD *)this + 10);
            if ( !v19 || v6 && !v3 )
            {
LABEL_32:
              v6 = 0;
              goto LABEL_13;
            }
            v20 = VMX_PHYSICAL_DISK::ReadSectors(this, v19, 1u, (unsigned __int8 **)&P);
            if ( v20 >= 0 )
            {
              if ( v3 )
              {
                v6 = 0;
                v14 = RtlCompareMemory(v3, P, 0x200u) != 512;
LABEL_45:
                v12 = v30;
                goto LABEL_46;
              }
              v21 = VMX_ALLOCATED_OBJECT::operator new(0x138u, 0x102u, 0x68446D56u);
              v31 = v21;
              v22 = (VMX_DISK_HEADER *)v21;
              if ( !v21 )
              {
                v31 = 0;
LABEL_43:
                v12 = 0;
                v30 = 0;
                v3 = 0;
                goto LABEL_32;
              }
              memset(v21, 0, 0x138u);
              v24 = (unsigned __int8 *)P;
              v20 = VMX_DISK_HEADER::Unformat(v22, &v24, v23);
              if ( v20 >= 0 )
              {
                v6 = 1;
                *((_QWORD *)this + 8) = *((_QWORD *)v22 + 19) + *((_QWORD *)v22 + 3);
                *((_QWORD *)this + 9) = *((_QWORD *)v22 + 19) + *((_QWORD *)v22 + 4);
                v14 = 0;
                goto LABEL_45;
              }
            }
            if ( v20 != -1073741670 )
            {
              v14 = 1;
              v6 = 0;
              goto LABEL_45;
            }
            goto LABEL_43;
          }
        }
        if ( v15 != -1073741670 )
          goto LABEL_29;
        goto LABEL_28;
      }
    }
    if ( Sectors != -1073741670 )
      goto LABEL_14;
LABEL_11:
    v12 = 0;
    v28 = 0;
LABEL_12:
    v3 = 0;
    v30 = 0;
    v6 = 0;
    v13 = 0;
LABEL_13:
    v14 = 0;
LABEL_46:
    if ( v1 && v1 != v12 )
    {
      VMX_ALLOCATED_OBJECT::operator delete(v1);
      v1 = 0;
    }
    if ( Source1 && Source1 != v3 )
    {
      ExFreePoolWithTag(Source1, 0);
      Source1 = 0;
    }
    if ( v2 && v2 != v30 )
    {
      VMX_ALLOCATED_OBJECT::operator delete(v2);
      v2 = 0;
    }
    if ( Source2 && Source2 != v3 )
    {
      ExFreePoolWithTag(Source2, 0);
      Source2 = 0;
    }
    if ( v31 )
    {
      VMX_ALLOCATED_OBJECT::operator delete(v31);
      v31 = 0;
    }
    if ( P )
    {
      ExFreePoolWithTag(P, 0);
      P = 0;
    }
    if ( !v6 )
      break;
  }
  if ( v3 )
  {
    if ( v28 )
      VMX_PHYSICAL_DISK::WriteSectors(this, *((_QWORD *)this + 8), 1u, v3);
    if ( v13 )
      VMX_PHYSICAL_DISK::WriteSectors(this, *((_QWORD *)this + 9), 1u, v3);
    if ( v14 )
      VMX_PHYSICAL_DISK::WriteSectors(this, *((_QWORD *)this + 10), 1u, v3);
    ExFreePoolWithTag(v3, 0);
  }
  *((_QWORD *)this + 11) = v30;
}

```

## disassembly

```asm
0x140045ed0  push    rbp
0x140045ed2  push    rbx
0x140045ed3  push    rsi
0x140045ed4  push    rdi
0x140045ed5  push    r12
0x140045ed7  push    r13
0x140045ed9  push    r14
0x140045edb  push    r15
0x140045edd  mov     rbp, rsp
0x140045ee0  sub     rsp, 48h
0x140045ee4  xor     eax, eax
0x140045ee6  xor     r15d, r15d
0x140045ee9  mov     [rbp+arg_18], rax
0x140045eed  xor     r14d, r14d
0x140045ef0  mov     [rbp+arg_10], rax
0x140045ef4  xor     esi, esi
0x140045ef6  mov     [rbp+Source1], rax
0x140045efa  xor     ebx, ebx
0x140045efc  mov     [rbp+P], rax
0x140045f00  mov     rdi, rcx
0x140045f03  mov     rax, [rcx+10h]
0x140045f07  xor     r13b, r13b
0x140045f0a  mov     [rbp+Source2], r15
0x140045f0e  mov     r12d, [rax+24h]
0x140045f12  mov     [rbp+arg_8], r12d
0x140045f16  jmp     short loc_140045F1C
0x140045f18  mov     r12d, [rbp+arg_8]
0x140045f1c  mov     rdx, [rdi+40h]; unsigned __int64
0x140045f20  lea     r9, [rbp+Source1]; unsigned __int8 **
0x140045f24  mov     r8d, 1; unsigned int
0x140045f2a  mov     rcx, rdi; this
0x140045f2d  call    ?ReadSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAPEAE@Z; VMX_PHYSICAL_DISK::ReadSectors(unsigned __int64,ulong,uchar * *)
0x140045f32  test    eax, eax
0x140045f34  js      short loc_140045FA2
0x140045f36  mov     edx, 102h; unsigned __int64
0x140045f3b  mov     r8d, 68446D56h; unsigned int
0x140045f41  lea     ecx, [rdx+36h]; unsigned __int64
0x140045f44  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x140045f49  mov     r14, rax
0x140045f4c  test    rax, rax
0x140045f4f  jz      short loc_140045F9D
0x140045f51  xor     edx, edx; Val
0x140045f53  mov     r8d, 138h; Size
0x140045f59  mov     rcx, rax; void *
0x140045f5c  call    memset
0x140045f61  mov     r15, [rbp+Source1]
0x140045f65  lea     rdx, [rbp+var_28]; unsigned __int8 **
0x140045f69  mov     rcx, r14; this
0x140045f6c  mov     [rbp+var_28], r15
0x140045f70  call    ?Unformat@VMX_DISK_HEADER@@QEAAJPEAPEAEK@Z; VMX_DISK_HEADER::Unformat(uchar * *,ulong)
0x140045f75  test    eax, eax
0x140045f77  js      short loc_140045FA2
0x140045f79  cmp     [r14+78h], r12d
0x140045f7d  jnz     short loc_140045FC2
0x140045f7f  mov     rax, [r14+98h]
0x140045f86  add     rax, [r14+18h]
0x140045f8a  cmp     rax, [rdi+40h]
0x140045f8e  jnz     short loc_140045FC2
0x140045f90  mov     [rbp+arg_10], r14
0x140045f94  mov     rbx, r15
0x140045f97  mov     [rbp+arg_0], 0
0x140045f9b  jmp     short loc_140045FC6
0x140045f9d  xor     r14d, r14d
0x140045fa0  jmp     short loc_140045FA9
0x140045fa2  cmp     eax, 0C000009Ah
0x140045fa7  jnz     short loc_140045FC2
0x140045fa9  xor     ecx, ecx
0x140045fab  mov     [rbp+arg_0], cl
0x140045fae  xor     ebx, ebx
0x140045fb0  mov     [rbp+arg_10], rcx
0x140045fb4  xor     r13b, r13b
0x140045fb7  xor     r12b, r12b
0x140045fba  xor     r15b, r15b
0x140045fbd  jmp     loc_1400461B0
0x140045fc2  mov     [rbp+arg_0], 1
0x140045fc6  mov     rdx, [rdi+48h]; unsigned __int64
0x140045fca  lea     r9, [rbp+Source2]; unsigned __int8 **
0x140045fce  mov     r8d, 1; unsigned int
0x140045fd4  mov     rcx, rdi; this
0x140045fd7  call    ?ReadSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAPEAE@Z; VMX_PHYSICAL_DISK::ReadSectors(unsigned __int64,ulong,uchar * *)
0x140045fdc  test    eax, eax
0x140045fde  js      loc_14004609C
0x140045fe4  mov     r15, [rbp+Source2]
0x140045fe8  test    rbx, rbx
0x140045feb  jz      short loc_140046014
0x140045fed  mov     r8d, 200h; Length
0x140045ff3  mov     rdx, r15; Source2
0x140045ff6  mov     rcx, rbx; Source1
0x140045ff9  xor     r12b, r12b
0x140045ffc  call    cs:__imp_RtlCompareMemory
0x140046003  nop     dword ptr [rax+rax+00h]
0x140046008  cmp     rax, 200h
0x14004600e  jz      loc_1400460AD
0x140046014  mov     edx, 102h; unsigned __int64
0x140046019  mov     r8d, 68446D56h; unsigned int
0x14004601f  lea     r12d, [rdx+36h]
0x140046023  mov     ecx, r12d; unsigned __int64
0x140046026  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14004602b  mov     rsi, rax
0x14004602e  test    rax, rax
0x140046031  jz      short loc_140046098
0x140046033  mov     r8d, r12d; Size
0x140046036  xor     edx, edx; Val
0x140046038  mov     rcx, rax; void *
0x14004603b  call    memset
0x140046040  lea     rdx, [rbp+var_28]; unsigned __int8 **
0x140046044  mov     [rbp+var_28], r15
0x140046048  mov     rcx, rsi; this
0x14004604b  call    ?Unformat@VMX_DISK_HEADER@@QEAAJPEAPEAEK@Z; VMX_DISK_HEADER::Unformat(uchar * *,ulong)
0x140046050  test    eax, eax
0x140046052  js      short loc_14004609C
0x140046054  mov     eax, [rbp+arg_8]
0x140046057  cmp     [rsi+78h], eax
0x14004605a  jnz     short loc_1400460AA
0x14004605c  mov     rax, [rsi+98h]
0x140046063  add     rax, [rsi+20h]
0x140046067  cmp     rax, [rdi+48h]
0x14004606b  jnz     short loc_1400460AA
0x14004606d  mov     rcx, [rbp+arg_10]
0x140046071  test    rcx, rcx
0x140046074  jz      short loc_140046085
0x140046076  mov     rax, [rsi+10h]
0x14004607a  cmp     [rcx+10h], rax
0x14004607e  jb      short loc_140046085
0x140046080  mov     r12b, 1
0x140046083  jmp     short loc_1400460B1
0x140046085  mov     rcx, rsi
0x140046088  mov     [rbp+arg_0], 1
0x14004608c  mov     [rbp+arg_10], rcx
0x140046090  mov     rbx, r15
0x140046093  xor     r12b, r12b
0x140046096  jmp     short loc_1400460B1
0x140046098  xor     esi, esi
0x14004609a  jmp     short loc_1400460A3
0x14004609c  cmp     eax, 0C000009Ah
0x1400460a1  jnz     short loc_1400460AA
0x1400460a3  xor     ecx, ecx
0x1400460a5  jmp     loc_140045FAE
0x1400460aa  mov     r12b, 1
0x1400460ad  mov     rcx, [rbp+arg_10]
0x1400460b1  mov     rdx, [rdi+50h]; unsigned __int64
0x1400460b5  test    rdx, rdx
0x1400460b8  jnz     short loc_1400460C2
0x1400460ba  xor     r13b, r13b
0x1400460bd  jmp     loc_140045FBA
0x1400460c2  test    r13b, r13b
0x1400460c5  jz      short loc_1400460CC
0x1400460c7  test    rbx, rbx
0x1400460ca  jz      short loc_1400460BA
0x1400460cc  lea     r9, [rbp+P]; unsigned __int8 **
0x1400460d0  mov     r8d, 1; unsigned int
0x1400460d6  mov     rcx, rdi; this
0x1400460d9  call    ?ReadSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAPEAE@Z; VMX_PHYSICAL_DISK::ReadSectors(unsigned __int64,ulong,uchar * *)
0x1400460de  test    eax, eax
0x1400460e0  js      loc_140046192
0x1400460e6  test    rbx, rbx
0x1400460e9  jz      short loc_140046116
0x1400460eb  mov     rdx, [rbp+P]; Source2
0x1400460ef  mov     r15d, 200h
0x1400460f5  mov     r8d, r15d; Length
0x1400460f8  mov     rcx, rbx; Source1
0x1400460fb  xor     r13b, r13b
0x1400460fe  call    cs:__imp_RtlCompareMemory
0x140046105  nop     dword ptr [rax+rax+00h]
0x14004610a  cmp     rax, r15
0x14004610d  setnz   r15b
0x140046111  jmp     loc_1400461AC
0x140046116  mov     edx, 102h; unsigned __int64
0x14004611b  mov     r8d, 68446D56h; unsigned int
0x140046121  lea     r13d, [rdx+36h]
0x140046125  mov     ecx, r13d; unsigned __int64
0x140046128  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14004612d  mov     [rbp+arg_18], rax
0x140046131  mov     r15, rax
0x140046134  test    rax, rax
0x140046137  jz      short loc_14004618C
0x140046139  mov     r8d, r13d; Size
0x14004613c  xor     edx, edx; Val
0x14004613e  mov     rcx, rax; void *
0x140046141  call    memset
0x140046146  mov     rax, [rbp+P]
0x14004614a  lea     rdx, [rbp+var_28]; unsigned __int8 **
0x14004614e  mov     rcx, r15; this
0x140046151  mov     [rbp+var_28], rax
0x140046155  call    ?Unformat@VMX_DISK_HEADER@@QEAAJPEAPEAEK@Z; VMX_DISK_HEADER::Unformat(uchar * *,ulong)
0x14004615a  test    eax, eax
0x14004615c  js      short loc_140046192
0x14004615e  mov     rax, [r15+18h]
0x140046162  mov     r13b, 1
0x140046165  add     rax, [r15+98h]
0x14004616c  mov     [rdi+40h], rax
0x140046170  mov     rax, [r15+20h]
0x140046174  add     rax, [r15+98h]
0x14004617b  mov     [rdi+48h], rax
0x14004617f  xor     r15b, r15b
0x140046182  mov     rax, [rbp+arg_18]
0x140046186  mov     [rbp+arg_18], rax
0x14004618a  jmp     short loc_1400461AC
0x14004618c  mov     [rbp+arg_18], rax
0x140046190  jmp     short loc_140046199
0x140046192  cmp     eax, 0C000009Ah
0x140046197  jnz     short loc_1400461A6
0x140046199  xor     ecx, ecx
0x14004619b  mov     [rbp+arg_10], rcx
0x14004619f  xor     ebx, ebx
0x1400461a1  jmp     loc_1400460BA
0x1400461a6  mov     r15b, 1
0x1400461a9  xor     r13b, r13b
0x1400461ac  mov     rcx, [rbp+arg_10]
0x1400461b0  test    r14, r14
0x1400461b3  jz      short loc_1400461C5
0x1400461b5  cmp     r14, rcx
0x1400461b8  jz      short loc_1400461C5
0x1400461ba  mov     rcx, r14; void *
0x1400461bd  call    ??3VMX_ALLOCATED_OBJECT@@SAXPEAX@Z; VMX_ALLOCATED_OBJECT::operator delete(void *)
0x1400461c2  xor     r14d, r14d
0x1400461c5  mov     rax, [rbp+Source1]
0x1400461c9  test    rax, rax
0x1400461cc  jz      short loc_1400461EC
0x1400461ce  cmp     rax, rbx
0x1400461d1  jz      short loc_1400461EC
0x1400461d3  xor     edx, edx; Tag
0x1400461d5  mov     rcx, rax; P
0x1400461d8  call    cs:__imp_ExFreePoolWithTag
0x1400461df  nop     dword ptr [rax+rax+00h]
0x1400461e4  mov     [rbp+Source1], 0
0x1400461ec  test    rsi, rsi
0x1400461ef  jz      short loc_140046201
0x1400461f1  cmp     rsi, [rbp+arg_10]
0x1400461f5  jz      short loc_140046201
0x1400461f7  mov     rcx, rsi; void *
0x1400461fa  call    ??3VMX_ALLOCATED_OBJECT@@SAXPEAX@Z; VMX_ALLOCATED_OBJECT::operator delete(void *)
0x1400461ff  xor     esi, esi
0x140046201  mov     rax, [rbp+Source2]
0x140046205  test    rax, rax
0x140046208  jz      short loc_140046226
0x14004620a  cmp     rax, rbx
0x14004620d  jz      short loc_140046226
0x14004620f  xor     edx, edx; Tag
0x140046211  mov     rcx, rax; P
0x140046214  call    cs:__imp_ExFreePoolWithTag
0x14004621b  nop     dword ptr [rax+rax+00h]
0x140046220  xor     eax, eax
0x140046222  mov     [rbp+Source2], rax
0x140046226  mov     rax, [rbp+arg_18]
0x14004622a  test    rax, rax
0x14004622d  jz      short loc_14004623D
0x14004622f  mov     rcx, rax; void *
0x140046232  call    ??3VMX_ALLOCATED_OBJECT@@SAXPEAX@Z; VMX_ALLOCATED_OBJECT::operator delete(void *)
0x140046237  xor     eax, eax
0x140046239  mov     [rbp+arg_18], rax
0x14004623d  mov     rax, [rbp+P]
0x140046241  test    rax, rax
0x140046244  jz      short loc_14004625D
0x140046246  xor     edx, edx; Tag
0x140046248  mov     rcx, rax; P
0x14004624b  call    cs:__imp_ExFreePoolWithTag
0x140046252  nop     dword ptr [rax+rax+00h]
0x140046257  xor     eax, eax
0x140046259  mov     [rbp+P], rax
0x14004625d  test    r13b, r13b
0x140046260  jnz     loc_140045F18
0x140046266  test    rbx, rbx
0x140046269  jz      short loc_1400462CB
0x14004626b  cmp     [rbp+arg_0], r13b
0x14004626f  jz      short loc_140046286
0x140046271  mov     rdx, [rdi+40h]; unsigned __int64
0x140046275  mov     r9, rbx; unsigned __int8 *
0x140046278  mov     r8d, 1; unsigned int
0x14004627e  mov     rcx, rdi; this
0x140046281  call    ?WriteSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAE@Z; VMX_PHYSICAL_DISK::WriteSectors(unsigned __int64,ulong,uchar *)
0x140046286  test    r12b, r12b
0x140046289  jz      short loc_1400462A0
0x14004628b  mov     rdx, [rdi+48h]; unsigned __int64
0x14004628f  mov     r9, rbx; unsigned __int8 *
0x140046292  mov     r8d, 1; unsigned int
0x140046298  mov     rcx, rdi; this
0x14004629b  call    ?WriteSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAE@Z; VMX_PHYSICAL_DISK::WriteSectors(unsigned __int64,ulong,uchar *)
0x1400462a0  test    r15b, r15b
0x1400462a3  jz      short loc_1400462BA
0x1400462a5  mov     rdx, [rdi+50h]; unsigned __int64
0x1400462a9  mov     r9, rbx; unsigned __int8 *
0x1400462ac  mov     r8d, 1; unsigned int
0x1400462b2  mov     rcx, rdi; this
0x1400462b5  call    ?WriteSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAE@Z; VMX_PHYSICAL_DISK::WriteSectors(unsigned __int64,ulong,uchar *)
0x1400462ba  xor     edx, edx; Tag
0x1400462bc  mov     rcx, rbx; P
0x1400462bf  call    cs:__imp_ExFreePoolWithTag
0x1400462c6  nop     dword ptr [rax+rax+00h]
0x1400462cb  mov     rax, [rbp+arg_10]
0x1400462cf  mov     [rdi+58h], rax
0x1400462d3  add     rsp, 48h
0x1400462d7  pop     r15
0x1400462d9  pop     r14
0x1400462db  pop     r13
0x1400462dd  pop     r12
0x1400462df  pop     rdi
0x1400462e0  pop     rsi
0x1400462e1  pop     rbx
0x1400462e2  pop     rbp
  ... truncated ...
```
