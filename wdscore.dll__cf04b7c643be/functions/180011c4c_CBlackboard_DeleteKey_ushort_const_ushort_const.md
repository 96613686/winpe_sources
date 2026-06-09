# CBlackboard::DeleteKey(ushort const *,ushort const *)

- ea: `0x180011c4c`
- end: `0x180011eee`
- name: `?DeleteKey@CBlackboard@@QEAAHPEBG0@Z`
- size: `674`
- prototype: `__int64 __fastcall(CBlackboard *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180018dc0`

## callees

- `0x180009e30`
- `0x18000f200`
- `0x180011868`
- `0x180011914`
- `0x180011c4c`
- `0x180013b28`
- `0x1800142c8`
- `0x180017968`
- `0x180017f10`
- `0x180017f94`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CBlackboard::DeleteKey(CBlackboard *this, size_t *a2, const unsigned __int16 *a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r12
  unsigned __int16 *v7; // r14
  __int64 v8; // r15
  unsigned int v9; // edi
  unsigned int v10; // ecx
  unsigned int v11; // ebx
  unsigned __int16 v12; // ax
  unsigned __int16 *v13; // r13
  __int64 v14; // rdx
  __int64 v15; // rdi
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  __int64 v19; // [rsp+48h] [rbp-49h]
  _QWORD v20[4]; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int16 *v21; // [rsp+70h] [rbp-21h] BYREF
  __int64 v22; // [rsp+78h] [rbp-19h]
  __int64 v23; // [rsp+80h] [rbp-11h]
  __int64 v24; // [rsp+88h] [rbp-9h]
  int v25[2]; // [rsp+90h] [rbp-1h] BYREF
  __int64 v26; // [rsp+98h] [rbp+7h]
  __int64 v27; // [rsp+A0h] [rbp+Fh]
  __int64 v28; // [rsp+A8h] [rbp+17h]
  int v29; // [rsp+100h] [rbp+6Fh]

  v19 = -2;
  if ( !a2 || !*(_WORD *)a2 )
    return 0;
  v5 = -1;
  do
    ++v5;
  while ( *((_WORD *)a2 + v5) );
  v6 = v5 + 1;
  v22 = 0;
  v23 = 0;
  v21 = 0;
  v24 = 10;
  if ( !(unsigned int)CDynamicArray<unsigned short,unsigned short *>::SetSize(&v21, v5 + 1)
    || !v22
    || (v7 = v21) == 0
    || (int)StringCchCopyW(v21, v5 + 1, a2) < 0
    || !(unsigned int)PreProcessPathString(v7, v5) )
  {
    CBuffer::~CBuffer((CBuffer *)&v21);
    return 0;
  }
  memset(v20, 0, 24);
  v20[3] = 10;
  if ( !(unsigned int)CDynamicArray<unsigned char,unsigned char *>::SetSize(v20, 24) )
    goto LABEL_36;
  v26 = 0;
  v27 = 0;
  *(_QWORD *)v25 = 0;
  v28 = 10;
  if ( !(unsigned int)CDynamicArray<unsigned char,unsigned char *>::SetSize(v25, 24) )
    goto LABEL_35;
  v29 = 0;
  v8 = *(_QWORD *)(*((_QWORD *)this + 15) + 16LL);
  v9 = 0;
  v10 = 0;
  v11 = 1;
  while ( 1 )
  {
    if ( v9 >= v6 )
      goto LABEL_34;
    v12 = v7[v9];
    if ( v12 != 92 && v12 != 12079 )
    {
      if ( v12 )
        goto LABEL_24;
      v29 = 1;
    }
    if ( v9 != v10 )
      break;
LABEL_23:
    v10 = v9 + 1;
LABEL_24:
    ++v9;
  }
  v7[v9] = 0;
  v13 = &v7[v10];
  if ( !(unsigned int)CBlackboard::FindKey(this, v8, v13, v20, 0, 0, 0, 0, v19) )
    goto LABEL_35;
  if ( !*(_QWORD *)v20[0] )
    goto LABEL_34;
  if ( !v29 )
  {
    v8 = *(_QWORD *)(v20[0] + 8LL);
    if ( !v8 )
      goto LABEL_34;
    goto LABEL_23;
  }
  if ( !a3 )
  {
    if ( !(unsigned int)CBlackboard::FindKey(this, v8, v13, v20, 0, 0, 0, 1, v19) )
      goto LABEL_35;
    v15 = v20[0];
    v16 = *(_QWORD *)(v20[0] + 8LL);
    if ( !v16 || (unsigned int)CBlackboard::DeleteBranch(this, v16) )
    {
      v17 = *(_QWORD *)(v15 + 16);
      if ( v17 )
        CTypeManager::DeleteBin(*((CTypeManager **)this + 15), v17);
    }
    goto LABEL_34;
  }
  v14 = *(_QWORD *)(v20[0] + 16LL);
  if ( !v14 || (unsigned int)CBlackboard::FindValue((int)this, v14, (int)a3, (int)v25, 0, 0, 1, 0) )
  {
LABEL_34:
    CBuffer::~CBuffer((CBuffer *)v25);
    goto LABEL_37;
  }
LABEL_35:
  CBuffer::~CBuffer((CBuffer *)v25);
LABEL_36:
  v11 = 0;
LABEL_37:
  CBuffer::~CBuffer((CBuffer *)v20);
  CBuffer::~CBuffer((CBuffer *)&v21);
  return v11;
}

```

## disassembly

```asm
0x180011c4c  mov     rax, rsp
0x180011c4f  mov     [rax+18h], r8
0x180011c53  push    rbp
0x180011c54  push    rsi
0x180011c55  push    rdi
0x180011c56  push    r12
0x180011c58  push    r13
0x180011c5a  push    r14
0x180011c5c  push    r15
0x180011c5e  lea     rbp, [rax-5Fh]
0x180011c62  sub     rsp, 0B0h
0x180011c69  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x180011c71  mov     [rax+8], rbx
0x180011c75  mov     rdi, rdx
0x180011c78  mov     rsi, rcx
0x180011c7b  xor     r13d, r13d
0x180011c7e  test    rdx, rdx
0x180011c81  jz      loc_180011ED0
0x180011c87  cmp     [rdx], r13w
0x180011c8b  jz      loc_180011ED0
0x180011c91  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011c95  inc     rbx
0x180011c98  cmp     [rdx+rbx*2], r13w
0x180011c9d  jnz     short loc_180011C95
0x180011c9f  lea     r12, [rbx+1]
0x180011ca3  mov     [rbp+57h+var_70], r13
0x180011ca7  mov     [rbp+57h+var_68], r13
0x180011cab  mov     [rbp+57h+var_78], r13
0x180011caf  mov     r15d, 0Ah
0x180011cb5  mov     [rbp+57h+var_60], r15
0x180011cb9  mov     rdx, r12
0x180011cbc  lea     rcx, [rbp+57h+var_78]
0x180011cc0  call    ?SetSize@?$CDynamicArray@GPEAG@@QEAAH_K@Z; CDynamicArray<ushort,ushort *>::SetSize(unsigned __int64)
0x180011cc5  test    eax, eax
0x180011cc7  jz      loc_180011EC7
0x180011ccd  cmp     [rbp+57h+var_70], r13
0x180011cd1  jz      loc_180011EC7
0x180011cd7  mov     r14, [rbp+57h+var_78]
0x180011cdb  test    r14, r14
0x180011cde  jz      loc_180011EC7
0x180011ce4  mov     r8, rdi; unsigned __int16 *
0x180011ce7  mov     rdx, r12; unsigned __int64
0x180011cea  mov     rcx, r14; unsigned __int16 *
0x180011ced  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011cf2  test    eax, eax
0x180011cf4  js      loc_180011EC7
0x180011cfa  mov     rdx, rbx; unsigned __int64
0x180011cfd  mov     rcx, r14; unsigned __int16 *
0x180011d00  call    ?PreProcessPathString@@YAHPEAG_K@Z; PreProcessPathString(ushort *,unsigned __int64)
0x180011d05  test    eax, eax
0x180011d07  jz      loc_180011EC7
0x180011d0d  mov     [rbp+57h+var_90], r13
0x180011d11  mov     [rbp+57h+var_88], r13
0x180011d15  mov     [rbp+57h+var_98], r13
0x180011d19  mov     [rbp+57h+var_80], r15
0x180011d1d  lea     ebx, [r15+0Eh]
0x180011d21  mov     edx, ebx
0x180011d23  lea     rcx, [rbp+57h+var_98]
0x180011d27  call    ?SetSize@?$CDynamicArray@EPEAE@@QEAAH_K@Z; CDynamicArray<uchar,uchar *>::SetSize(unsigned __int64)
0x180011d2c  test    eax, eax
0x180011d2e  jz      loc_180011EAD
0x180011d34  mov     [rbp+57h+var_50], r13
0x180011d38  mov     [rbp+57h+var_48], r13
0x180011d3c  mov     qword ptr [rbp+57h+var_58], r13
0x180011d40  mov     [rbp+57h+var_40], r15
0x180011d44  mov     edx, ebx
0x180011d46  lea     rcx, [rbp+57h+var_58]
0x180011d4a  call    ?SetSize@?$CDynamicArray@EPEAE@@QEAAH_K@Z; CDynamicArray<uchar,uchar *>::SetSize(unsigned __int64)
0x180011d4f  test    eax, eax
0x180011d51  jz      loc_180011EA4
0x180011d57  mov     [rbp+57h+arg_8], r13d
0x180011d5b  mov     rax, [rsi+78h]
0x180011d5f  mov     r15, [rax+10h]
0x180011d63  mov     edi, r13d
0x180011d66  mov     ecx, r13d
0x180011d69  mov     ebx, 1
0x180011d6e  mov     edx, edi
0x180011d70  cmp     rdx, r12
0x180011d73  jnb     loc_180011E96
0x180011d79  movzx   eax, word ptr [r14+rdx*2]
0x180011d7e  mov     r8d, 5Ch ; '\'
0x180011d84  cmp     r8w, ax
0x180011d88  jz      short loc_180011D9E
0x180011d8a  mov     r8d, 2F2Fh
0x180011d90  cmp     r8w, ax
0x180011d94  jz      short loc_180011D9E
0x180011d96  test    ax, ax
0x180011d99  jnz     short loc_180011E00
0x180011d9b  mov     [rbp+57h+arg_8], ebx
0x180011d9e  cmp     edi, ecx
0x180011da0  jz      short loc_180011DFD
0x180011da2  mov     [r14+rdx*2], r13w
0x180011da7  mov     eax, ecx
0x180011da9  lea     r13, [r14+rax*2]
0x180011dad  xor     eax, eax
0x180011daf  mov     [rsp+38h], eax
0x180011db3  mov     [rsp+0E0h+var_B0], eax
0x180011db7  mov     [rsp+0E0h+var_B8], eax
0x180011dbb  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180011dbf  lea     r9, [rbp+57h+var_98]
0x180011dc3  mov     r8, r13
0x180011dc6  mov     rdx, r15
0x180011dc9  mov     rcx, rsi
0x180011dcc  call    ?FindKey@CBlackboard@@AEAAH_KPEBGAEAV?$CDynamicArray@EPEAUSKey@@@@HHHH@Z; CBlackboard::FindKey(unsigned __int64,ushort const *,CDynamicArray<uchar,SKey *> &,int,int,int,int)
0x180011dd1  xor     ecx, ecx
0x180011dd3  test    eax, eax
0x180011dd5  jz      loc_180011EA1
0x180011ddb  mov     rax, [rbp+57h+var_98]
0x180011ddf  cmp     [rax], rcx
0x180011de2  jz      loc_180011E96
0x180011de8  cmp     [rbp+57h+arg_8], ecx
0x180011deb  jnz     short loc_180011E07
0x180011ded  mov     r15, [rax+8]
0x180011df1  xor     r13d, r13d
0x180011df4  test    r15, r15
0x180011df7  jz      loc_180011E96
0x180011dfd  lea     ecx, [rdi+1]
0x180011e00  add     edi, ebx
0x180011e02  jmp     loc_180011D6E
0x180011e07  mov     r8, qword ptr [rbp+57h+arg_10]; int
0x180011e0b  test    r8, r8
0x180011e0e  jz      short loc_180011E41
0x180011e10  mov     rdx, [rax+10h]; int
0x180011e14  xor     r13d, r13d
0x180011e17  test    rdx, rdx
0x180011e1a  jz      short loc_180011E96
0x180011e1c  mov     [rsp+38h], r13d; int
0x180011e21  mov     [rsp+0E0h+var_B0], ebx; int
0x180011e25  mov     [rsp+0E0h+var_B8], r13d; int
0x180011e2a  mov     [rsp+0E0h+var_C0], r13; struct WDS_DATA *
0x180011e2f  lea     r9, [rbp+57h+var_58]; int
0x180011e33  mov     rcx, rsi; int
0x180011e36  call    ?FindValue@CBlackboard@@AEAAH_KPEBGAEAV?$CDynamicArray@EPEAUSValue@@@@PEAUWDS_DATA@@HHH@Z; CBlackboard::FindValue(unsigned __int64,ushort const *,CDynamicArray<uchar,SValue *> &,WDS_DATA *,int,int,int)
0x180011e3b  test    eax, eax
0x180011e3d  jz      short loc_180011EA4
0x180011e3f  jmp     short loc_180011E96
0x180011e41  mov     [rsp+38h], ebx
0x180011e45  mov     [rsp+0E0h+var_B0], ecx
0x180011e49  mov     [rsp+0E0h+var_B8], ecx
0x180011e4d  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x180011e51  lea     r9, [rbp+57h+var_98]
0x180011e55  mov     r8, r13
0x180011e58  mov     rdx, r15
0x180011e5b  mov     rcx, rsi
0x180011e5e  call    ?FindKey@CBlackboard@@AEAAH_KPEBGAEAV?$CDynamicArray@EPEAUSKey@@@@HHHH@Z; CBlackboard::FindKey(unsigned __int64,ushort const *,CDynamicArray<uchar,SKey *> &,int,int,int,int)
0x180011e63  xor     r13d, r13d
0x180011e66  test    eax, eax
0x180011e68  jz      short loc_180011EA4
0x180011e6a  mov     rdi, [rbp+57h+var_98]
0x180011e6e  mov     rdx, [rdi+8]; unsigned __int64
0x180011e72  test    rdx, rdx
0x180011e75  jz      short loc_180011E83
0x180011e77  mov     rcx, rsi; this
0x180011e7a  call    ?DeleteBranch@CBlackboard@@AEAAH_K@Z; CBlackboard::DeleteBranch(unsigned __int64)
0x180011e7f  test    eax, eax
0x180011e81  jz      short loc_180011E96
0x180011e83  mov     rdx, [rdi+10h]; unsigned __int64
0x180011e87  test    rdx, rdx
0x180011e8a  jz      short loc_180011E96
0x180011e8c  mov     rcx, [rsi+78h]; this
0x180011e90  call    ?DeleteBin@CTypeManager@@QEAAH_K@Z; CTypeManager::DeleteBin(unsigned __int64)
0x180011e95  nop
0x180011e96  lea     rcx, [rbp+57h+var_58]; this
0x180011e9a  call    ??1CBuffer@@QEAA@XZ; CBuffer::~CBuffer(void)
0x180011e9f  jmp     short loc_180011EB0
0x180011ea1  xor     r13d, r13d
0x180011ea4  lea     rcx, [rbp+57h+var_58]; this
0x180011ea8  call    ??1CBuffer@@QEAA@XZ; CBuffer::~CBuffer(void)
0x180011ead  mov     ebx, r13d
0x180011eb0  lea     rcx, [rbp+57h+var_98]; this
0x180011eb4  call    ??1CBuffer@@QEAA@XZ; CBuffer::~CBuffer(void)
0x180011eb9  nop
0x180011eba  lea     rcx, [rbp+57h+var_78]; this
0x180011ebe  call    ??1CBuffer@@QEAA@XZ; CBuffer::~CBuffer(void)
0x180011ec3  mov     eax, ebx
0x180011ec5  jmp     short loc_180011ED2
0x180011ec7  lea     rcx, [rbp+57h+var_78]; this
0x180011ecb  call    ??1CBuffer@@QEAA@XZ; CBuffer::~CBuffer(void)
0x180011ed0  xor     eax, eax
0x180011ed2  mov     rbx, [rsp+0E0h+arg_0]
0x180011eda  add     rsp, 0B0h
0x180011ee1  pop     r15
0x180011ee3  pop     r14
0x180011ee5  pop     r13
0x180011ee7  pop     r12
0x180011ee9  pop     rdi
0x180011eea  pop     rsi
0x180011eeb  pop     rbp
0x180011eec  retn
```
