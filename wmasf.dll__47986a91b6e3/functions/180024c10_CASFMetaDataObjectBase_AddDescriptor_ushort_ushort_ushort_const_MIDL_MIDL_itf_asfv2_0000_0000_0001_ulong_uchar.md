# CASFMetaDataObjectBase::AddDescriptor(ushort,ushort,ushort const *,__MIDL___MIDL_itf_asfv2_0000_0000_0001,ulong,uchar *)

- ea: `0x180024c10`
- end: `0x180024d95`
- name: `?AddDescriptor@CASFMetaDataObjectBase@@UEAAJGGPEBGW4__MIDL___MIDL_itf_asfv2_0000_0000_0001@@KPEAE@Z`
- size: `389`
- prototype: `int __high(unsigned __int16, unsigned __int16, const unsigned __int16 *, enum __MIDL___MIDL_itf_asfv2_0000_0000_0001, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800021dc`
- `0x18000220c`
- `0x18000da0c`
- `0x18000ff88`
- `0x180024c10`
- `0x18003f2a0`

## pseudocode

```c
__int64 __fastcall CASFMetaDataObjectBase::AddDescriptor(
        __int64 a1,
        __int16 a2,
        __int16 a3,
        unsigned __int16 *a4,
        int a5,
        size_t Size,
        void *Src)
{
  unsigned int v11; // ebx
  unsigned __int64 v12; // r15
  __int16 v13; // ax
  unsigned __int16 *v14; // rbx
  __int64 v15; // rdi
  __int64 v16; // rcx
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rsi
  void *v19; // r14
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rcx
  __int128 v23; // [rsp+20h] [rbp-48h]
  __int128 v24; // [rsp+30h] [rbp-38h]
  _OWORD v25[2]; // [rsp+40h] [rbp-28h] BYREF
  char v26; // [rsp+B0h] [rbp+48h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v26, *(struct IWMSCriticalSection **)(a1 + 32));
  if ( *(_QWORD *)(a1 + 40) )
  {
    if ( a4 )
    {
      v12 = (unsigned int)Size;
      switch ( a5 )
      {
        case 2:
        case 3:
          v13 = 4;
          break;
        case 4:
          v13 = 8;
          break;
        case 5:
          v13 = 2;
          break;
        default:
LABEL_12:
          WORD1(v23) = a2;
          v14 = 0;
          LOWORD(v23) = a3;
          v15 = -1;
          v16 = -1;
          DWORD1(v23) = a5;
          v24 = (unsigned int)Size;
          do
            ++v16;
          while ( a4[v16] );
          v17 = (unsigned __int16 *)operator new[](saturated_mul(v16 + 1, 2u));
          *((_QWORD *)&v23 + 1) = v17;
          v18 = v17;
          if ( !v17 )
            goto LABEL_15;
          do
            ++v15;
          while ( a4[v15] );
          StringCchCopyW(v17, v15 + 1, a4);
          v19 = Src;
          if ( Src )
          {
            v20 = (unsigned __int16 *)operator new[](v12);
            *((_QWORD *)&v24 + 1) = v20;
            v14 = v20;
            if ( !v20 )
            {
              v21 = v18;
LABEL_20:
              operator delete(v21);
LABEL_15:
              v11 = -2147024882;
              goto LABEL_26;
            }
            memcpy_0(v20, v19, v12);
          }
          v25[0] = v23;
          v25[1] = v24;
          if ( (unsigned int)CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::Add(a1 + 80, v25) )
          {
            v11 = 0;
            goto LABEL_26;
          }
          operator delete(v18);
          v21 = v14;
          goto LABEL_20;
      }
      if ( v13 == (_WORD)Size )
        goto LABEL_12;
    }
    v11 = -2147024809;
    goto LABEL_26;
  }
  v11 = -1072887818;
LABEL_26:
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v26);
  return v11;
}

```

## disassembly

```asm
0x180024c10  push    rbp
0x180024c12  push    rbx
0x180024c13  push    rsi
0x180024c14  push    rdi
0x180024c15  push    r12
0x180024c17  push    r13
0x180024c19  push    r14
0x180024c1b  push    r15
0x180024c1d  mov     rbp, rsp
0x180024c20  sub     rsp, 68h
0x180024c24  movzx   ebx, dx
0x180024c27  mov     r13, rcx
0x180024c2a  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180024c2e  mov     r14, r9
0x180024c31  lea     rcx, [rbp+arg_0]; this
0x180024c35  movzx   edi, r8w
0x180024c39  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180024c3e  xor     r12d, r12d
0x180024c41  cmp     [r13+28h], r12
0x180024c45  jnz     short loc_180024C51
0x180024c47  mov     ebx, 0C00D07F6h
0x180024c4c  jmp     loc_180024D79
0x180024c51  test    r14, r14
0x180024c54  jz      loc_180024D74
0x180024c5a  mov     edx, [rbp+arg_20]
0x180024c5d  mov     r8d, 2
0x180024c63  mov     r15d, dword ptr [rbp+Size]
0x180024c67  mov     ecx, edx
0x180024c69  sub     ecx, r8d
0x180024c6c  jz      short loc_180024C8A
0x180024c6e  sub     ecx, 1
0x180024c71  jz      short loc_180024C8A
0x180024c73  sub     ecx, 1
0x180024c76  jz      short loc_180024C83
0x180024c78  cmp     ecx, 1
0x180024c7b  jnz     short loc_180024C99
0x180024c7d  movzx   eax, r8w
0x180024c81  jmp     short loc_180024C8F
0x180024c83  mov     eax, 8
0x180024c88  jmp     short loc_180024C8F
0x180024c8a  mov     eax, 4
0x180024c8f  cmp     ax, r15w
0x180024c93  jnz     loc_180024D74
0x180024c99  mov     word ptr [rbp+var_48+2], bx
0x180024c9d  mov     rbx, r12
0x180024ca0  mov     word ptr [rbp+var_48], di
0x180024ca4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180024ca8  mov     qword ptr [rbp+var_38+4], r12
0x180024cac  mov     rcx, rdi
0x180024caf  mov     qword ptr [rbp+var_38+8], rbx
0x180024cb3  mov     qword ptr [rbp+var_48+8], r12
0x180024cb7  mov     dword ptr [rbp+var_48+4], edx
0x180024cba  mov     dword ptr [rbp+var_38], r15d
0x180024cbe  inc     rcx
0x180024cc1  cmp     [r14+rcx*2], r12w
0x180024cc6  jnz     short loc_180024CBE
0x180024cc8  inc     rcx
0x180024ccb  mov     rax, r8
0x180024cce  mul     rcx
0x180024cd1  cmovb   rax, rdi
0x180024cd5  mov     rcx, rax; unsigned __int64
0x180024cd8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180024cdd  mov     qword ptr [rbp+var_48+8], rax
0x180024ce1  mov     rsi, rax
0x180024ce4  test    rax, rax
0x180024ce7  jnz     short loc_180024CF3
0x180024ce9  mov     ebx, 8007000Eh
0x180024cee  jmp     loc_180024D79
0x180024cf3  inc     rdi
0x180024cf6  cmp     [r14+rdi*2], r12w
0x180024cfb  jnz     short loc_180024CF3
0x180024cfd  lea     rdx, [rdi+1]; unsigned __int64
0x180024d01  mov     r8, r14; unsigned __int16 *
0x180024d04  mov     rcx, rsi; unsigned __int16 *
0x180024d07  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024d0c  mov     r14, [rbp+Src]
0x180024d10  test    r14, r14
0x180024d13  jz      short loc_180024D41
0x180024d15  mov     rcx, r15; unsigned __int64
0x180024d18  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180024d1d  mov     qword ptr [rbp+var_38+8], rax
0x180024d21  mov     rbx, rax
0x180024d24  test    rax, rax
0x180024d27  jnz     short loc_180024D33
0x180024d29  mov     rcx, rsi; Block
0x180024d2c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024d31  jmp     short loc_180024CE9
0x180024d33  mov     r8, r15; Size
0x180024d36  mov     rdx, r14; Src
0x180024d39  mov     rcx, rax; void *
0x180024d3c  call    memcpy_0
0x180024d41  movups  xmm0, [rbp+var_48]
0x180024d45  lea     rcx, [r13+50h]
0x180024d49  movups  xmm1, [rbp+var_38]
0x180024d4d  lea     rdx, [rbp+var_28]
0x180024d51  movaps  [rbp+var_28], xmm0
0x180024d55  movaps  [rbp+var_18], xmm1
0x180024d59  call    ?Add@?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEAAHUMETADATA_REC@CASFMetaDataObjectBase@@PEAK@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::Add(CASFMetaDataObjectBase::METADATA_REC,ulong *)
0x180024d5e  test    eax, eax
0x180024d60  jnz     short loc_180024D6F
0x180024d62  mov     rcx, rsi; Block
0x180024d65  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024d6a  mov     rcx, rbx
0x180024d6d  jmp     short loc_180024D2C
0x180024d6f  mov     ebx, r12d
0x180024d72  jmp     short loc_180024D79
0x180024d74  mov     ebx, 80070057h
0x180024d79  lea     rcx, [rbp+arg_0]; this
0x180024d7d  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180024d82  mov     eax, ebx
0x180024d84  add     rsp, 68h
0x180024d88  pop     r15
0x180024d8a  pop     r14
0x180024d8c  pop     r13
0x180024d8e  pop     r12
0x180024d90  pop     rdi
0x180024d91  pop     rsi
0x180024d92  pop     rbx
0x180024d93  pop     rbp
0x180024d94  retn
```
