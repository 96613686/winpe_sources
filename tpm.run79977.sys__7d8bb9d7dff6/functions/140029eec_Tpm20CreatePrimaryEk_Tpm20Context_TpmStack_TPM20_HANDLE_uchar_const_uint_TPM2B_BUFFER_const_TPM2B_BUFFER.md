# Tpm20CreatePrimaryEk(Tpm20Context *,TpmStack *,_TPM20_HANDLE *,uchar const *,uint,TPM2B_BUFFER const *,TPM2B_BUFFER *)

- ea: `0x140029eec`
- end: `0x14002a0a6`
- name: `?Tpm20CreatePrimaryEk@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAT_TPM20_HANDLE@@PEBEIPEBVTPM2B_BUFFER@@PEAV4@@Z`
- size: `442`
- prototype: `__int64 __usercall@<rax>(struct Tpm20Context *@<rcx>, struct TpmStack *this@<rdx>, union _TPM20_HANDLE *@<r8>, const unsigned __int8 *@<r9>, unsigned int, const struct TPM2B_BUFFER *, struct TPM2B_BUFFER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14002d050`

## callees

- `0x1400078b8`
- `0x14001c7cc`
- `0x140029eec`
- `0x14002a240`
- `0x140039840`
- `0x140039b40`
- `0x140045430`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall Tpm20CreatePrimaryEk(
        struct Tpm20Context *a1,
        TpmSWAntiHammeringMgr ***this,
        union _TPM20_HANDLE *a3,
        const unsigned __int8 *a4,
        unsigned int Size,
        const void **a6)
{
  unsigned int v10; // ebp
  unsigned __int8 *v11; // rax
  unsigned __int8 *v12; // rdi
  int PrimaryResponse; // ebx
  unsigned __int16 v14; // cx
  unsigned __int8 *v15; // rax
  struct _TPM20_REPLY_HEADER *v16; // rsi
  __int64 v17; // rcx
  unsigned __int64 retaddr; // [rsp+78h] [rbp+0h]

  if ( a3 && a4 && Size && (v10 = Size + 61, Size + 61 <= 0x800) )
  {
    v11 = TpmAlloc(1, v10, retaddr);
    v12 = v11;
    if ( v11 )
    {
      memset(v11, 0, v10);
      *(_DWORD *)(v12 + 2) = _byteswap_ulong(v10);
      *(_WORD *)v12 = 640;
      *(_DWORD *)(v12 + 6) = 822149120;
      *(_DWORD *)(v12 + 10) = 184549440;
      *(_DWORD *)(v12 + 14) = 486539264;
      *(_DWORD *)(v12 + 18) = 150995008;
      *((_WORD *)v12 + 11) = 0;
      v12[24] = 0;
      *(_WORD *)(v12 + 25) = 5120;
      if ( a6 )
      {
        v14 = 20;
        if ( *(_WORD *)a6 < 0x14u )
          v14 = *(_WORD *)a6;
        memmove(v12 + 27, a6[1], v14);
      }
      *(_WORD *)(v12 + 53) = __ROR2__(Size, 8);
      memmove(v12 + 55, a4, Size);
      *(_WORD *)(v12 + 47) = 1024;
      v15 = TpmAlloc(1, 0x600u, retaddr);
      v16 = (struct _TPM20_REPLY_HEADER *)v15;
      if ( v15 )
      {
        memset(v15, 0, 0x600u);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids);
        PrimaryResponse = TpmStack::Tpm20SubmitInternalCommand(
                            this,
                            a1,
                            (struct _TPM20_CMD_HEADER *)v12,
                            v10,
                            v16,
                            0x600u);
        if ( PrimaryResponse >= 0 )
          PrimaryResponse = Tpm20DecodeCreatePrimaryResponse(v17, v16, a3);
      }
      else
      {
        PrimaryResponse = -1073741670;
      }
      TpmFree(v12);
      if ( v16 )
        TpmFree(v16);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)PrimaryResponse;
}

```

## disassembly

```asm
0x140029eec  push    rbx
0x140029eee  push    rbp
0x140029eef  push    rsi
0x140029ef0  push    rdi
0x140029ef1  push    r12
0x140029ef3  push    r13
0x140029ef5  push    r14
0x140029ef7  push    r15
0x140029ef9  sub     rsp, 38h
0x140029efd  mov     rsi, r9
0x140029f00  mov     r14, r8
0x140029f03  mov     r12, rdx
0x140029f06  mov     r13, rcx
0x140029f09  test    r8, r8
0x140029f0c  jz      loc_14002A08D
0x140029f12  test    r9, r9
0x140029f15  jz      loc_14002A08D
0x140029f1b  mov     ebx, dword ptr [rsp+78h+Size]
0x140029f22  test    ebx, ebx
0x140029f24  jz      loc_14002A08D
0x140029f2a  lea     ebp, [rbx+3Dh]
0x140029f2d  cmp     ebp, 800h
0x140029f33  ja      loc_14002A08D
0x140029f39  mov     r8, [rsp+78h]; unsigned __int64
0x140029f3e  mov     cl, 1; bool
0x140029f40  mov     edx, ebp; unsigned __int64
0x140029f42  mov     r15d, ebp
0x140029f45  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x140029f4a  mov     rdi, rax
0x140029f4d  test    rax, rax
0x140029f50  jnz     short loc_140029F5C
0x140029f52  mov     ebx, 0C000009Ah
0x140029f57  jmp     loc_14002A092
0x140029f5c  mov     r8, r15; Size
0x140029f5f  xor     edx, edx; Val
0x140029f61  mov     rcx, rdi; void *
0x140029f64  call    memset
0x140029f69  mov     rdx, [rsp+78h+arg_28]
0x140029f71  mov     eax, ebp
0x140029f73  bswap   eax
0x140029f75  mov     [rdi+2], eax
0x140029f78  xor     eax, eax
0x140029f7a  mov     word ptr [rdi], 280h
0x140029f7f  mov     dword ptr [rdi+6], 31010000h
0x140029f86  mov     dword ptr [rdi+0Ah], 0B000040h
0x140029f8d  mov     dword ptr [rdi+0Eh], 1D000000h
0x140029f94  mov     dword ptr [rdi+12h], 9000040h
0x140029f9b  mov     [rdi+16h], ax
0x140029f9f  mov     [rdi+18h], al
0x140029fa2  mov     word ptr [rdi+19h], 1400h
0x140029fa8  test    rdx, rdx
0x140029fab  jz      short loc_140029FCB
0x140029fad  lea     ecx, [rax+14h]
0x140029fb0  movzx   eax, word ptr [rdx]
0x140029fb3  mov     rdx, [rdx+8]; Src
0x140029fb7  cmp     ax, cx
0x140029fba  cmovb   cx, ax
0x140029fbe  movzx   r8d, cx; Size
0x140029fc2  lea     rcx, [rdi+1Bh]; void *
0x140029fc6  call    memmove
0x140029fcb  movzx   eax, bx
0x140029fce  lea     rcx, [rdi+37h]; void *
0x140029fd2  ror     ax, 8
0x140029fd6  mov     r8, rbx; Size
0x140029fd9  mov     rdx, rsi; Src
0x140029fdc  mov     [rdi+35h], ax
0x140029fe0  call    memmove
0x140029fe5  mov     r8, [rsp+78h]; unsigned __int64
0x140029fea  mov     ebx, 600h
0x140029fef  mov     edx, ebx; unsigned __int64
0x140029ff1  mov     word ptr [rdi+2Fh], 400h
0x140029ff7  mov     cl, 1; bool
0x140029ff9  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x140029ffe  mov     rsi, rax
0x14002a001  test    rax, rax
0x14002a004  jnz     short loc_14002A00D
0x14002a006  mov     ebx, 0C000009Ah
0x14002a00b  jmp     short loc_14002A076
0x14002a00d  mov     r8, rbx; Size
0x14002a010  xor     edx, edx; Val
0x14002a012  mov     rcx, rsi; void *
0x14002a015  call    memset
0x14002a01a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a021  lea     rax, WPP_GLOBAL_Control
0x14002a028  cmp     rcx, rax
0x14002a02b  jz      short loc_14002A049
0x14002a02d  mov     eax, [rcx+2Ch]
0x14002a030  test    al, 4
0x14002a032  jz      short loc_14002A049
0x14002a034  mov     rcx, [rcx+18h]
0x14002a038  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x14002a03f  mov     edx, 3Eh ; '>'
0x14002a044  call    WPP_SF_
0x14002a049  mov     [rsp+78h+var_50], ebx; unsigned int
0x14002a04d  mov     r9d, ebp; unsigned int
0x14002a050  mov     r8, rdi; struct _TPM20_CMD_HEADER *
0x14002a053  mov     [rsp+78h+var_58], rsi; struct _TPM20_REPLY_HEADER *
0x14002a058  mov     rdx, r13; struct Tpm20Context *
0x14002a05b  mov     rcx, r12; this
0x14002a05e  call    ?Tpm20SubmitInternalCommand@TpmStack@@QEAAJPEAVTpm20Context@@PEAU_TPM20_CMD_HEADER@@IPEAU_TPM20_REPLY_HEADER@@I@Z; TpmStack::Tpm20SubmitInternalCommand(Tpm20Context *,_TPM20_CMD_HEADER *,uint,_TPM20_REPLY_HEADER *,uint)
0x14002a063  mov     ebx, eax
0x14002a065  test    eax, eax
0x14002a067  js      short loc_14002A076
0x14002a069  mov     r8, r14
0x14002a06c  mov     rdx, rsi
0x14002a06f  call    Tpm20DecodeCreatePrimaryResponse
0x14002a074  mov     ebx, eax
0x14002a076  mov     rcx, rdi; void *
0x14002a079  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14002a07e  test    rsi, rsi
0x14002a081  jz      short loc_14002A092
0x14002a083  mov     rcx, rsi; void *
0x14002a086  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14002a08b  jmp     short loc_14002A092
0x14002a08d  mov     ebx, 0C000000Dh
0x14002a092  mov     eax, ebx
0x14002a094  add     rsp, 38h
0x14002a098  pop     r15
0x14002a09a  pop     r14
0x14002a09c  pop     r13
0x14002a09e  pop     r12
0x14002a0a0  pop     rdi
0x14002a0a1  pop     rsi
0x14002a0a2  pop     rbp
0x14002a0a3  pop     rbx
0x14002a0a4  retn
```
