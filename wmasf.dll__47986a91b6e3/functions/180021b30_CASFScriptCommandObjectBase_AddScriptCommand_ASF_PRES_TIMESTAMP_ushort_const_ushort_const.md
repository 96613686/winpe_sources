# CASFScriptCommandObjectBase::AddScriptCommand(_ASF_PRES_TIMESTAMP *,ushort const *,ushort const *)

- ea: `0x180021b30`
- end: `0x180021d29`
- name: `?AddScriptCommand@CASFScriptCommandObjectBase@@UEAAJPEAU_ASF_PRES_TIMESTAMP@@PEBG1@Z`
- size: `505`
- prototype: `int(CASFScriptCommandObjectBase *__hidden this, struct _ASF_PRES_TIMESTAMP *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800021dc`
- `0x18000220c`
- `0x18000c334`
- `0x18000c36c`
- `0x18000f12c`
- `0x18000ff88`
- `0x180021b30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180021bb5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180021bb5`

## pseudocode

```c
__int64 __fastcall CASFScriptCommandObjectBase::AddScriptCommand(
        struct IWMSCriticalSection **this,
        struct _ASF_PRES_TIMESTAMP *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v5; // r15
  unsigned int v7; // ebx
  int v8; // edi
  unsigned __int16 v9; // r12
  char *v10; // r13
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rcx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // eax
  unsigned __int16 *v19; // rax
  _BYTE v21[16]; // [rsp+20h] [rbp-30h] BYREF
  __int128 v22; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v23; // [rsp+40h] [rbp-10h]
  int v24; // [rsp+90h] [rbp+40h] BYREF
  struct _ASF_PRES_TIMESTAMP *v25; // [rsp+98h] [rbp+48h]
  unsigned __int16 *v26; // [rsp+A8h] [rbp+58h]

  v26 = a4;
  v25 = a2;
  v5 = a4;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v21, this[4]);
  if ( !this[5] )
  {
    v7 = -1072887818;
LABEL_26:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v21);
    return v7;
  }
  if ( a3 && v5 )
  {
    v8 = -1;
    v9 = 0;
    v24 = -1;
    if ( *((_WORD *)this + 148) )
    {
      do
      {
        v10 = (char *)(this + 10);
        v11 = CTDynArray<unsigned short *,20>::operator[](this + 10, v9);
        if ( !(unsigned int)_o__wcsicmp(a3, v11) )
          v8 = v9;
        ++v9;
      }
      while ( v9 < *((_WORD *)this + 148) );
      v5 = v26;
      v24 = v8;
    }
    else
    {
      v10 = (char *)(this + 10);
    }
    v12 = -1;
    if ( v8 == -1 )
    {
      v13 = -1;
      do
        ++v13;
      while ( a3[v13] );
      v14 = (unsigned __int16 *)operator new[](saturated_mul(v13 + 1, 2u));
      v15 = v14;
      if ( !v14 )
        goto LABEL_25;
      v16 = -1;
      do
        ++v16;
      while ( a3[v16] );
      StringCchCopyW(v14, v16 + 1, a3);
      if ( !(unsigned int)CTDynArray<unsigned short *,20>::Add(v10, v15, &v24) )
        goto LABEL_24;
      LOWORD(v8) = v24;
    }
    v22 = 0;
    v23 = 0;
    v17 = -1;
    WORD6(v22) = v8;
    v18 = *((_DWORD *)v25 + 2);
    *(_QWORD *)&v22 = *(_QWORD *)v25;
    DWORD2(v22) = v18;
    do
      ++v17;
    while ( v5[v17] );
    v19 = (unsigned __int16 *)operator new[](saturated_mul(v17 + 1, 2u));
    v15 = v19;
    if ( !v19 )
      goto LABEL_25;
    do
      ++v12;
    while ( v5[v12] );
    StringCchCopyW(v19, v12 + 1, v5);
    v23 = v15;
    if ( !(unsigned int)CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::Add(this + 38, &v22) )
    {
LABEL_24:
      operator delete(v15);
LABEL_25:
      v7 = -2147024882;
      goto LABEL_26;
    }
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v21);
    return 0;
  }
  else
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v21);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180021b30  mov     [rsp-38h+arg_10], rbx
0x180021b35  mov     [rsp-38h+arg_18], r9
0x180021b3a  mov     [rsp-38h+arg_8], rdx
0x180021b3f  push    rbp
0x180021b40  push    rsi
0x180021b41  push    rdi
0x180021b42  push    r12
0x180021b44  push    r13
0x180021b46  push    r14
0x180021b48  push    r15
0x180021b4a  mov     rbp, rsp
0x180021b4d  sub     rsp, 50h
0x180021b51  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180021b55  mov     rsi, rcx
0x180021b58  lea     rcx, [rbp+var_30]; this
0x180021b5c  mov     r15, r9
0x180021b5f  mov     r14, r8
0x180021b62  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180021b67  xor     edx, edx
0x180021b69  cmp     [rsi+28h], rdx
0x180021b6d  jnz     short loc_180021B79
0x180021b6f  mov     ebx, 0C00D07F6h
0x180021b74  jmp     loc_180021CE9
0x180021b79  test    r14, r14
0x180021b7c  jz      loc_180021D03
0x180021b82  test    r15, r15
0x180021b85  jz      loc_180021D03
0x180021b8b  or      edi, 0FFFFFFFFh
0x180021b8e  mov     r12d, edx
0x180021b91  mov     [rbp+arg_0], edi
0x180021b94  cmp     dx, [rsi+128h]
0x180021b9b  jnb     short loc_180021BD9
0x180021b9d  movzx   ebx, r12w
0x180021ba1  lea     r13, [rsi+50h]
0x180021ba5  mov     edx, ebx
0x180021ba7  mov     rcx, r13
0x180021baa  call    ??A?$CTDynArray@PEAG$0BE@@@QEBAPEAGK@Z; CTDynArray<ushort *,20>::operator[](ulong)
0x180021baf  mov     rdx, rax
0x180021bb2  mov     rcx, r14
0x180021bb5  call    cs:__imp__o__wcsicmp
0x180021bbb  test    eax, eax
0x180021bbd  cmovz   edi, ebx
0x180021bc0  inc     r12w
0x180021bc4  cmp     r12w, [rsi+128h]
0x180021bcc  jb      short loc_180021B9D
0x180021bce  mov     r15, [rbp+arg_18]
0x180021bd2  xor     edx, edx
0x180021bd4  mov     [rbp+arg_0], edi
0x180021bd7  jmp     short loc_180021BDD
0x180021bd9  lea     r13, [rsi+50h]
0x180021bdd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180021be1  cmp     edi, 0FFFFFFFFh
0x180021be4  jnz     short loc_180021C50
0x180021be6  mov     rcx, rbx
0x180021be9  inc     rcx
0x180021bec  cmp     [r14+rcx*2], dx
0x180021bf1  jnz     short loc_180021BE9
0x180021bf3  inc     rcx
0x180021bf6  mov     eax, 2
0x180021bfb  mul     rcx
0x180021bfe  cmovb   rax, rbx
0x180021c02  mov     rcx, rax; unsigned __int64
0x180021c05  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180021c0a  xor     r12d, r12d
0x180021c0d  mov     rdi, rax
0x180021c10  test    rax, rax
0x180021c13  jz      loc_180021CE4
0x180021c19  mov     rdx, rbx
0x180021c1c  inc     rdx
0x180021c1f  cmp     [r14+rdx*2], r12w
0x180021c24  jnz     short loc_180021C1C
0x180021c26  inc     rdx; unsigned __int64
0x180021c29  mov     r8, r14; unsigned __int16 *
0x180021c2c  mov     rcx, rdi; unsigned __int16 *
0x180021c2f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021c34  lea     r8, [rbp+arg_0]
0x180021c38  mov     rdx, rdi
0x180021c3b  mov     rcx, r13
0x180021c3e  call    ?Add@?$CTDynArray@PEAG$0BE@@@QEAAHPEAGPEAK@Z; CTDynArray<ushort *,20>::Add(ushort *,ulong *)
0x180021c43  xor     edx, edx
0x180021c45  test    eax, eax
0x180021c47  jz      loc_180021CDC
0x180021c4d  mov     edi, [rbp+arg_0]
0x180021c50  xor     eax, eax
0x180021c52  xorps   xmm0, xmm0
0x180021c55  movups  [rbp+var_20], xmm0
0x180021c59  mov     [rbp+var_10], rax
0x180021c5d  mov     rcx, rbx
0x180021c60  mov     rax, [rbp+arg_8]
0x180021c64  mov     word ptr [rbp+var_20+0Ch], di
0x180021c68  movsd   xmm0, qword ptr [rax]
0x180021c6c  mov     eax, [rax+8]
0x180021c6f  movsd   qword ptr [rbp+var_20], xmm0
0x180021c74  mov     dword ptr [rbp+var_20+8], eax
0x180021c77  inc     rcx
0x180021c7a  cmp     [r15+rcx*2], dx
0x180021c7f  jnz     short loc_180021C77
0x180021c81  inc     rcx
0x180021c84  mov     eax, 2
0x180021c89  mul     rcx
0x180021c8c  cmovb   rax, rbx
0x180021c90  mov     rcx, rax; unsigned __int64
0x180021c93  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180021c98  xor     r12d, r12d
0x180021c9b  mov     rdi, rax
0x180021c9e  test    rax, rax
0x180021ca1  jz      short loc_180021CE4
0x180021ca3  inc     rbx
0x180021ca6  cmp     [r15+rbx*2], r12w
0x180021cab  jnz     short loc_180021CA3
0x180021cad  lea     rdx, [rbx+1]; unsigned __int64
0x180021cb1  mov     r8, r15; unsigned __int16 *
0x180021cb4  mov     rcx, rdi; unsigned __int16 *
0x180021cb7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021cbc  movups  xmm0, [rbp+var_20]
0x180021cc0  lea     rcx, [rsi+130h]
0x180021cc7  mov     [rbp+var_10], rdi
0x180021ccb  lea     rdx, [rbp+var_20]
0x180021ccf  movaps  [rbp+var_20], xmm0
0x180021cd3  call    ?Add@?$CTDynArray@UCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@@@QEAAHUCOMMAND_RECORD@CASFScriptCommandObjectBase@@PEAK@Z; CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::Add(CASFScriptCommandObjectBase::COMMAND_RECORD,ulong *)
0x180021cd8  test    eax, eax
0x180021cda  jnz     short loc_180021CF6
0x180021cdc  mov     rcx, rdi; Block
0x180021cdf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021ce4  mov     ebx, 8007000Eh
0x180021ce9  lea     rcx, [rbp+var_30]; this
0x180021ced  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180021cf2  mov     eax, ebx
0x180021cf4  jmp     short loc_180021D11
0x180021cf6  lea     rcx, [rbp+var_30]; this
0x180021cfa  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180021cff  xor     eax, eax
0x180021d01  jmp     short loc_180021D11
0x180021d03  lea     rcx, [rbp+var_30]; this
0x180021d07  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180021d0c  mov     eax, 80070057h
0x180021d11  mov     rbx, [rsp+50h+arg_10]
0x180021d19  add     rsp, 50h
0x180021d1d  pop     r15
0x180021d1f  pop     r14
0x180021d21  pop     r13
0x180021d23  pop     r12
0x180021d25  pop     rdi
0x180021d26  pop     rsi
0x180021d27  pop     rbp
0x180021d28  retn
```
