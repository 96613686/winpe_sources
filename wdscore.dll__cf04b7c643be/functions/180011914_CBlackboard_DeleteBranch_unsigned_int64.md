# CBlackboard::DeleteBranch(unsigned __int64)

- ea: `0x180011914`
- end: `0x180011a97`
- name: `?DeleteBranch@CBlackboard@@AEAAH_K@Z`
- size: `387`
- prototype: `__int64 __fastcall(CBlackboard *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180011914`
- `0x180011c4c`

## callees

- `0x1800104fc`
- `0x180011868`
- `0x180011914`
- `0x180012bfc`
- `0x180012e78`
- `0x1800132f8`
- `0x180017888`
- `0x180027510`

## pseudocode

```c
__int64 __fastcall CBlackboard::DeleteBranch(CTypeManager **this, unsigned __int64 a2)
{
  __int64 result; // rax
  int v5; // edi
  int v6; // ebx
  unsigned __int64 v7; // [rsp+48h] [rbp-1E0h] BYREF
  void *v8; // [rsp+50h] [rbp-1D8h] BYREF
  unsigned __int64 v9[3]; // [rsp+58h] [rbp-1D0h] BYREF
  unsigned __int64 v10[2]; // [rsp+70h] [rbp-1B8h] BYREF
  unsigned __int64 v11; // [rsp+80h] [rbp-1A8h]
  _BYTE v12[368]; // [rsp+90h] [rbp-198h] BYREF

  v9[1] = (unsigned __int64)this;
  v9[2] = a2;
  result = CTypeManager::OpenBin(this[15], (struct CBin *)v12, a2, 1, 0);
  if ( (_DWORD)result )
  {
    v5 = 0;
    *(_OWORD *)v10 = 0;
    v11 = 0;
    if ( (unsigned int)CBin::EnumItemReset((CBin *)v12, 0, 0) )
    {
      v8 = 0;
      v7 = 0;
      v9[0] = 0;
      while ( 1 )
      {
        v8 = CBin::EnumNextItem((CBin *)v12, &v7, v9);
        if ( !v8 )
          break;
        if ( !(unsigned int)CBin::EnumReadWrite((CBin *)v12, 1, (unsigned __int64)v10, 0x18u, &v8, &v7, 0) )
          goto LABEL_10;
        if ( v10[1] )
          CBlackboard::DeleteBranch((CBlackboard *)this, v10[1]);
      }
      v5 = 1;
    }
LABEL_10:
    v6 = CTypeManager::CloseBin(this[15], (struct CBin *)v12, 0) != 0 ? v5 : 0;
    if ( v11 )
      v6 = (unsigned int)CTypeManager::DeleteBin(this[15], v11) != 0 ? v6 : 0;
    return v6 & (unsigned int)-((unsigned int)CTypeManager::DeleteBin(this[15], a2) != 0);
  }
  return result;
}

```

## disassembly

```asm
0x180011914  mov     [rsp+arg_10], rbx
0x180011919  push    rsi
0x18001191a  push    rdi
0x18001191b  push    r14
0x18001191d  sub     rsp, 210h
0x180011924  mov     rax, cs:__security_cookie
0x18001192b  xor     rax, rsp
0x18001192e  mov     [rsp+228h+var_28], rax
0x180011936  mov     r14, rdx
0x180011939  mov     rsi, rcx
0x18001193c  mov     [rsp+228h+var_1C8], rcx
0x180011941  mov     [rsp+228h+var_1C0], rdx
0x180011946  mov     [rsp+228h+var_208], 0; unsigned int *
0x18001194f  mov     ebx, 1
0x180011954  mov     r9d, ebx; int
0x180011957  mov     r8, rdx; unsigned __int64
0x18001195a  lea     rdx, [rsp+228h+var_198]; struct CBin *
0x180011962  mov     rcx, [rcx+78h]; this
0x180011966  call    ?OpenBin@CTypeManager@@QEAAHAEAVCBin@@_KHPEAI@Z; CTypeManager::OpenBin(CBin &,unsigned __int64,int,uint *)
0x18001196b  test    eax, eax
0x18001196d  jz      loc_180011A72
0x180011973  xor     edi, edi
0x180011975  mov     [rsp+228h+var_1E8], edi
0x180011979  xorps   xmm0, xmm0
0x18001197c  xor     eax, eax
0x18001197e  movups  xmmword ptr [rsp+228h+var_1B8], xmm0
0x180011983  mov     [rsp+228h+var_1A8], rax
0x18001198b  xor     r8d, r8d; int
0x18001198e  xor     edx, edx; unsigned __int64
0x180011990  lea     rcx, [rsp+228h+var_198]; this
0x180011998  call    ?EnumItemReset@CBin@@QEAAH_KH@Z; CBin::EnumItemReset(unsigned __int64,int)
0x18001199d  test    eax, eax
0x18001199f  jz      loc_180011A2A
0x1800119a5  mov     [rsp+228h+var_1D8], rdi
0x1800119aa  mov     [rsp+228h+var_1E0], rdi
0x1800119af  mov     [rsp+228h+var_1D0], rdi
0x1800119b4  lea     r8, [rsp+228h+var_1D0]; unsigned __int64 *
0x1800119b9  lea     rdx, [rsp+228h+var_1E0]; unsigned __int64 *
0x1800119be  lea     rcx, [rsp+228h+var_198]; this
0x1800119c6  call    ?EnumNextItem@CBin@@QEAAPEAXAEA_K0@Z; CBin::EnumNextItem(unsigned __int64 &,unsigned __int64 &)
0x1800119cb  mov     [rsp+228h+var_1D8], rax
0x1800119d0  test    rax, rax
0x1800119d3  jz      short loc_180011A24
0x1800119d5  mov     [rsp+228h+var_1F8], 0; unsigned __int64
0x1800119de  lea     rax, [rsp+228h+var_1E0]
0x1800119e3  mov     [rsp+228h+var_200], rax; unsigned __int64 *
0x1800119e8  lea     rax, [rsp+228h+var_1D8]
0x1800119ed  mov     [rsp+228h+var_208], rax; void **
0x1800119f2  mov     r9d, 18h; unsigned __int64
0x1800119f8  lea     r8, [rsp+228h+var_1B8]; void *
0x1800119fd  mov     edx, ebx; int
0x1800119ff  lea     rcx, [rsp+228h+var_198]; this
0x180011a07  call    ?EnumReadWrite@CBin@@QEAAHHPEAX_KAEAPEAXAEA_K1@Z; CBin::EnumReadWrite(int,void *,unsigned __int64,void * &,unsigned __int64 &,unsigned __int64)
0x180011a0c  test    eax, eax
0x180011a0e  jz      short loc_180011A2A
0x180011a10  mov     rdx, [rsp+228h+var_1B8+8]; unsigned __int64
0x180011a15  test    rdx, rdx
0x180011a18  jz      short loc_180011A22
0x180011a1a  mov     rcx, rsi; this
0x180011a1d  call    ?DeleteBranch@CBlackboard@@AEAAH_K@Z; CBlackboard::DeleteBranch(unsigned __int64)
0x180011a22  jmp     short loc_1800119B4
0x180011a24  mov     edi, ebx
0x180011a26  mov     [rsp+228h+var_1E8], ebx
0x180011a2a  xor     r8d, r8d; unsigned __int64 *
0x180011a2d  lea     rdx, [rsp+228h+var_198]; struct CBin *
0x180011a35  mov     rcx, [rsi+78h]; this
0x180011a39  call    ?CloseBin@CTypeManager@@QEAAHAEAVCBin@@PEA_K@Z; CTypeManager::CloseBin(CBin &,unsigned __int64 *)
0x180011a3e  neg     eax
0x180011a40  sbb     ebx, ebx
0x180011a42  and     ebx, edi
0x180011a44  mov     rdx, [rsp+228h+var_1A8]; unsigned __int64
0x180011a4c  test    rdx, rdx
0x180011a4f  jz      short loc_180011A60
0x180011a51  mov     rcx, [rsi+78h]; this
0x180011a55  call    ?DeleteBin@CTypeManager@@QEAAH_K@Z; CTypeManager::DeleteBin(unsigned __int64)
0x180011a5a  neg     eax
0x180011a5c  sbb     ecx, ecx
0x180011a5e  and     ebx, ecx
0x180011a60  mov     rdx, r14; unsigned __int64
0x180011a63  mov     rcx, [rsi+78h]; this
0x180011a67  call    ?DeleteBin@CTypeManager@@QEAAH_K@Z; CTypeManager::DeleteBin(unsigned __int64)
0x180011a6c  neg     eax
0x180011a6e  sbb     eax, eax
0x180011a70  and     eax, ebx
0x180011a72  mov     rcx, [rsp+228h+var_28]
0x180011a7a  xor     rcx, rsp; StackCookie
0x180011a7d  call    __security_check_cookie
0x180011a82  mov     rbx, [rsp+228h+arg_10]
0x180011a8a  add     rsp, 210h
0x180011a91  pop     r14
0x180011a93  pop     rdi
0x180011a94  pop     rsi
0x180011a95  retn
0x180028808  push    rbx
0x18002880a  push    rbp
0x18002880b  push    rdi
0x18002880c  sub     rsp, 40h
0x180028810  mov     rbp, rdx
0x180028813  xor     r8d, r8d; unsigned __int64 *
0x180028816  lea     rdx, [rbp+90h]; struct CBin *
0x18002881d  mov     rdi, [rbp+60h]
0x180028821  mov     rcx, [rdi+78h]; this
0x180028825  call    ?CloseBin@CTypeManager@@QEAAHAEAVCBin@@PEA_K@Z; CTypeManager::CloseBin(CBin &,unsigned __int64 *)
0x18002882a  neg     eax
0x18002882c  sbb     ebx, ebx
0x18002882e  and     ebx, [rbp+40h]
0x180028831  mov     [rbp+40h], ebx
0x180028834  mov     rdx, [rbp+80h]; unsigned __int64
0x18002883b  test    rdx, rdx
0x18002883e  jz      short loc_180028854
0x180028840  mov     rcx, [rdi+78h]; this
0x180028844  call    ?DeleteBin@CTypeManager@@QEAAH_K@Z; CTypeManager::DeleteBin(unsigned __int64)
0x180028849  neg     eax
0x18002884b  sbb     edx, edx
0x18002884d  and     edx, ebx
0x18002884f  mov     ebx, edx
0x180028851  mov     [rbp+40h], edx
0x180028854  mov     rdx, [rbp+68h]; unsigned __int64
0x180028858  mov     rcx, [rdi+78h]; this
0x18002885c  call    ?DeleteBin@CTypeManager@@QEAAH_K@Z; CTypeManager::DeleteBin(unsigned __int64)
0x180028861  neg     eax
0x180028863  sbb     ecx, ecx
0x180028865  and     ecx, ebx
0x180028867  mov     [rbp+40h], ecx
0x18002886a  add     rsp, 40h
0x18002886e  pop     rdi
0x18002886f  pop     rbp
0x180028870  pop     rbx
0x180028871  retn
```
