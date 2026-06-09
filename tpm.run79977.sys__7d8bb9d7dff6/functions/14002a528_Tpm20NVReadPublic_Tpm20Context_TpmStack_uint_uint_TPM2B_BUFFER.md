# Tpm20NVReadPublic(Tpm20Context *,TpmStack *,uint,uint *,TPM2B_BUFFER *)

- ea: `0x14002a528`
- end: `0x14002a6bb`
- name: `?Tpm20NVReadPublic@@YAJPEAVTpm20Context@@PEAVTpmStack@@IPEAIPEAVTPM2B_BUFFER@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(struct Tpm20Context *, struct TpmStack *this, unsigned int, unsigned int *, struct TPM2B_BUFFER *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002d050`

## callees

- `0x1400078b8`
- `0x140009278`
- `0x14001c7cc`
- `0x14002a528`
- `0x140039b40`
- `0x140045430`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall Tpm20NVReadPublic(
        struct Tpm20Context *a1,
        TpmSWAntiHammeringMgr ***this,
        unsigned int a3,
        unsigned int *a4)
{
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rbx
  int v10; // edi
  unsigned __int16 v11; // si
  unsigned int v12; // r8d
  unsigned __int16 v13; // dx
  unsigned __int16 v14; // cx
  unsigned __int64 retaddr; // [rsp+78h] [rbp+0h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids);
  v8 = TpmAlloc(1, 0x61u, retaddr);
  v9 = v8;
  if ( v8 )
  {
    memset(v8, 0, 0x61u);
    dword_1400478E2 = _byteswap_ulong(a3);
    v10 = TpmStack::Tpm20SubmitInternalCommand(
            this,
            a1,
            (struct _TPM20_CMD_HEADER *)&unk_1400478D8,
            0xEu,
            (struct _TPM20_REPLY_HEADER *)v9,
            0x61u);
    if ( v10 >= 0 )
    {
      v11 = 0;
      v12 = _byteswap_ulong(*(_DWORD *)(v9 + 2));
      v13 = __ROR2__(*((_WORD *)v9 + 5), 8);
      if ( v12 < 0x1C || v13 < 0xEu || _byteswap_ulong(*((_DWORD *)v9 + 3)) != a3 )
      {
LABEL_19:
        if ( a4 )
          *a4 = v11;
        goto LABEL_21;
      }
      v14 = __ROR2__(*((_WORD *)v9 + 11), 8);
      if ( !v14 )
      {
        v11 = __ROR2__(*((_WORD *)v9 + 12), 8);
        goto LABEL_15;
      }
      if ( v12 >= (unsigned int)v14 + 28 && v13 >= (unsigned __int64)v14 + 14 )
      {
        v11 = v9[v14 + 25] + (v9[v14 + 24] << 8);
LABEL_15:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids, v11);
        v10 = 0;
        goto LABEL_19;
      }
      v10 = -1073741823;
    }
LABEL_21:
    TpmFree(v9);
    return (unsigned int)v10;
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x14002a528  push    rbx
0x14002a52a  push    rbp
0x14002a52b  push    rsi
0x14002a52c  push    rdi
0x14002a52d  push    r12
0x14002a52f  push    r13
0x14002a531  push    r14
0x14002a533  push    r15
0x14002a535  sub     rsp, 38h
0x14002a539  mov     r14, r9
0x14002a53c  mov     ebp, r8d
0x14002a53f  mov     rdi, rdx
0x14002a542  mov     rsi, rcx
0x14002a545  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a54c  lea     r13, WPP_GLOBAL_Control
0x14002a553  cmp     rcx, r13
0x14002a556  jz      short loc_14002A574
0x14002a558  mov     eax, [rcx+2Ch]
0x14002a55b  test    al, 4
0x14002a55d  jz      short loc_14002A574
0x14002a55f  mov     rcx, [rcx+18h]
0x14002a563  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x14002a56a  mov     edx, 40h ; '@'
0x14002a56f  call    WPP_SF_
0x14002a574  mov     r8, [rsp+78h]; unsigned __int64
0x14002a579  mov     r12d, 61h ; 'a'
0x14002a57f  mov     edx, r12d; unsigned __int64
0x14002a582  mov     cl, 1; bool
0x14002a584  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14002a589  xor     r15d, r15d
0x14002a58c  mov     rbx, rax
0x14002a58f  test    rax, rax
0x14002a592  jnz     short loc_14002A59E
0x14002a594  mov     edi, 0C000009Ah
0x14002a599  jmp     loc_14002A6A0
0x14002a59e  mov     r8, r12; Size
0x14002a5a1  xor     edx, edx; Val
0x14002a5a3  mov     rcx, rbx; void *
0x14002a5a6  call    memset
0x14002a5ab  mov     eax, ebp
0x14002a5ad  mov     [rsp+78h+var_50], r12d; unsigned int
0x14002a5b2  bswap   eax
0x14002a5b4  mov     r12d, 0Eh
0x14002a5ba  mov     cs:dword_1400478E2, eax
0x14002a5c0  mov     r9d, r12d; unsigned int
0x14002a5c3  mov     [rsp+78h+var_58], rbx; struct _TPM20_REPLY_HEADER *
0x14002a5c8  lea     r8, unk_1400478D8; struct _TPM20_CMD_HEADER *
0x14002a5cf  mov     rdx, rsi; struct Tpm20Context *
0x14002a5d2  mov     rcx, rdi; this
0x14002a5d5  call    ?Tpm20SubmitInternalCommand@TpmStack@@QEAAJPEAVTpm20Context@@PEAU_TPM20_CMD_HEADER@@IPEAU_TPM20_REPLY_HEADER@@I@Z; TpmStack::Tpm20SubmitInternalCommand(Tpm20Context *,_TPM20_CMD_HEADER *,uint,_TPM20_REPLY_HEADER *,uint)
0x14002a5da  mov     edi, eax
0x14002a5dc  test    eax, eax
0x14002a5de  js      loc_14002A698
0x14002a5e4  mov     r8d, [rbx+2]
0x14002a5e8  mov     esi, r15d
0x14002a5eb  movzx   edx, word ptr [rbx+0Ah]
0x14002a5ef  bswap   r8d
0x14002a5f2  ror     dx, 8
0x14002a5f6  cmp     r8d, 1Ch
0x14002a5fa  jb      loc_14002A68D
0x14002a600  cmp     dx, r12w
0x14002a604  jb      loc_14002A68D
0x14002a60a  mov     eax, [rbx+0Ch]
0x14002a60d  bswap   eax
0x14002a60f  cmp     eax, ebp
0x14002a611  jnz     short loc_14002A68D
0x14002a613  movzx   ecx, word ptr [rbx+16h]
0x14002a617  ror     cx, 8
0x14002a61b  test    cx, cx
0x14002a61e  jnz     short loc_14002A62A
0x14002a620  movzx   esi, word ptr [rbx+18h]
0x14002a624  ror     si, 8
0x14002a628  jmp     short loc_14002A65E
0x14002a62a  movzx   r9d, cx
0x14002a62e  lea     eax, [r9+1Ch]
0x14002a632  cmp     r8d, eax
0x14002a635  jb      short loc_14002A6B4
0x14002a637  movzx   r8d, cx
0x14002a63b  movzx   eax, dx
0x14002a63e  lea     rcx, [r8+0Eh]
0x14002a642  cmp     rax, rcx
0x14002a645  jb      short loc_14002A6B4
0x14002a647  movzx   esi, byte ptr [r8+rbx+18h]
0x14002a64d  mov     ecx, 100h
0x14002a652  imul    esi, ecx
0x14002a655  movzx   ecx, byte ptr [r9+rbx+19h]
0x14002a65b  add     si, cx
0x14002a65e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a665  cmp     rcx, r13
0x14002a668  jz      short loc_14002A68A
0x14002a66a  mov     eax, [rcx+2Ch]
0x14002a66d  test    al, 4
0x14002a66f  jz      short loc_14002A68A
0x14002a671  mov     rcx, [rcx+18h]
0x14002a675  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x14002a67c  movzx   r9d, si
0x14002a680  mov     edx, 41h ; 'A'
0x14002a685  call    WPP_SF_d
0x14002a68a  mov     edi, r15d
0x14002a68d  test    r14, r14
0x14002a690  jz      short loc_14002A698
0x14002a692  movzx   eax, si
0x14002a695  mov     [r14], eax
0x14002a698  mov     rcx, rbx; void *
0x14002a69b  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14002a6a0  mov     eax, edi
0x14002a6a2  add     rsp, 38h
0x14002a6a6  pop     r15
0x14002a6a8  pop     r14
0x14002a6aa  pop     r13
0x14002a6ac  pop     r12
0x14002a6ae  pop     rdi
0x14002a6af  pop     rsi
0x14002a6b0  pop     rbp
0x14002a6b1  pop     rbx
0x14002a6b2  retn
0x14002a6b4  mov     edi, 0C0000001h
0x14002a6b9  jmp     short loc_14002A698
```
