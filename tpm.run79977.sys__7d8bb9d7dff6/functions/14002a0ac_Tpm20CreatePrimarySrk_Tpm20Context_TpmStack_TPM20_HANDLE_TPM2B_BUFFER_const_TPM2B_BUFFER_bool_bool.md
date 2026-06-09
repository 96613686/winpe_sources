# Tpm20CreatePrimarySrk(Tpm20Context *,TpmStack *,_TPM20_HANDLE *,TPM2B_BUFFER const *,TPM2B_BUFFER *,bool,bool)

- ea: `0x14002a0ac`
- end: `0x14002a237`
- name: `?Tpm20CreatePrimarySrk@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAT_TPM20_HANDLE@@PEBVTPM2B_BUFFER@@PEAV4@_N5@Z`
- size: `395`
- prototype: `__int64 __usercall@<rax>(struct Tpm20Context *@<rcx>, struct TpmStack *this@<rdx>, union _TPM20_HANDLE *@<r8>, const struct TPM2B_BUFFER *@<r9>, struct TPM2B_BUFFER *, bool, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14002d8b4`

## callees

- `0x1400078b8`
- `0x140009278`
- `0x14001c7cc`
- `0x14002a0ac`
- `0x14002a240`
- `0x140039840`
- `0x140039b40`
- `0x140045430`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall Tpm20CreatePrimarySrk(
        struct Tpm20Context *a1,
        TpmSWAntiHammeringMgr ***this,
        union _TPM20_HANDLE *a3,
        const void **a4,
        struct TPM2B_BUFFER *a5,
        bool a6,
        bool a7)
{
  unsigned __int16 v11; // dx
  unsigned __int8 *v12; // rax
  struct _TPM20_REPLY_HEADER *v13; // rdi
  int PrimaryResponse; // ebx
  __int64 v15; // rcx
  unsigned __int64 retaddr; // [rsp+68h] [rbp+0h]

  if ( a7 && !a6 )
    return 3221225485LL;
  dword_14004792A = 16777280;
  dword_140047932 = 150995008;
  word_140047963 = __ROR2__((a6 + 1) << 7, 8);
  word_140047969 = __ROR2__((a7 + 2) << 10, 8);
  if ( a4 )
  {
    v11 = 20;
    if ( *(_WORD *)a4 < 0x14u )
      v11 = *(_WORD *)a4;
    memmove(&unk_14004793B, a4[1], v11);
  }
  v12 = TpmAlloc(1, 0x600u, retaddr);
  v13 = (struct _TPM20_REPLY_HEADER *)v12;
  if ( v12 )
  {
    memset(v12, 0, 0x600u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          60,
          WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids,
          (unsigned __int16)((a6 + 1) << 7));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids);
    }
    PrimaryResponse = TpmStack::Tpm20SubmitInternalCommand(
                        this,
                        a1,
                        (struct _TPM20_CMD_HEADER *)&unk_140047920,
                        0x157u,
                        v13,
                        0x600u);
    if ( PrimaryResponse >= 0 )
      PrimaryResponse = Tpm20DecodeCreatePrimaryResponse(v15, v13, a3);
    TpmFree(v13);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)PrimaryResponse;
}

```

## disassembly

```asm
0x14002a0ac  push    rbx
0x14002a0ae  push    rbp
0x14002a0af  push    rsi
0x14002a0b0  push    rdi
0x14002a0b1  push    r12
0x14002a0b3  push    r14
0x14002a0b5  sub     rsp, 38h
0x14002a0b9  movzx   r10d, [rsp+68h+arg_30]
0x14002a0c2  mov     rsi, r8
0x14002a0c5  movzx   eax, [rsp+68h+arg_28]
0x14002a0cd  mov     rbp, rdx
0x14002a0d0  mov     r14, rcx
0x14002a0d3  test    r10b, r10b
0x14002a0d6  jz      short loc_14002A0E6
0x14002a0d8  test    al, al
0x14002a0da  jnz     short loc_14002A0E6
0x14002a0dc  mov     eax, 0C000000Dh
0x14002a0e1  jmp     loc_14002A229
0x14002a0e6  lea     ecx, [rax+1]
0x14002a0e9  mov     cs:dword_14004792A, 1000040h
0x14002a0f3  mov     eax, 80h
0x14002a0f8  movzx   ebx, cx
0x14002a0fb  imul    ebx, eax
0x14002a0fe  lea     ecx, [r10+2]
0x14002a102  movzx   edx, cx
0x14002a105  mov     cs:dword_140047932, 9000040h
0x14002a10f  movzx   eax, bx
0x14002a112  ror     ax, 8
0x14002a116  mov     cs:word_140047963, ax
0x14002a11d  mov     eax, 400h
0x14002a122  imul    edx, eax
0x14002a125  ror     dx, 8
0x14002a129  mov     cs:word_140047969, dx
0x14002a130  test    r9, r9
0x14002a133  jz      short loc_14002A159
0x14002a135  movzx   eax, word ptr [r9]
0x14002a139  lea     rcx, unk_14004793B; void *
0x14002a140  mov     edx, 14h
0x14002a145  cmp     ax, dx
0x14002a148  cmovb   dx, ax
0x14002a14c  movzx   r8d, dx; Size
0x14002a150  mov     rdx, [r9+8]; Src
0x14002a154  call    memmove
0x14002a159  mov     r8, [rsp+68h]; unsigned __int64
0x14002a15e  mov     edx, 600h; unsigned __int64
0x14002a163  mov     cl, 1; bool
0x14002a165  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14002a16a  mov     rdi, rax
0x14002a16d  test    rax, rax
0x14002a170  jnz     short loc_14002A17C
0x14002a172  mov     ebx, 0C000009Ah
0x14002a177  jmp     loc_14002A227
0x14002a17c  xor     edx, edx; Val
0x14002a17e  mov     r8d, 600h; Size
0x14002a184  mov     rcx, rdi; void *
0x14002a187  call    memset
0x14002a18c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a193  lea     r12, WPP_GLOBAL_Control
0x14002a19a  cmp     rcx, r12
0x14002a19d  jz      short loc_14002A1E7
0x14002a19f  mov     eax, [rcx+2Ch]
0x14002a1a2  test    al, 4
0x14002a1a4  jz      short loc_14002A1BF
0x14002a1a6  mov     rcx, [rcx+18h]
0x14002a1aa  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x14002a1b1  movzx   r9d, bx
0x14002a1b5  mov     edx, 3Ch ; '<'
0x14002a1ba  call    WPP_SF_d
0x14002a1bf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a1c6  cmp     rcx, r12
0x14002a1c9  jz      short loc_14002A1E7
0x14002a1cb  mov     eax, [rcx+2Ch]
0x14002a1ce  test    al, 4
0x14002a1d0  jz      short loc_14002A1E7
0x14002a1d2  mov     rcx, [rcx+18h]
0x14002a1d6  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x14002a1dd  mov     edx, 3Dh ; '='
0x14002a1e2  call    WPP_SF_
0x14002a1e7  mov     [rsp+68h+var_40], 600h; unsigned int
0x14002a1ef  lea     r8, unk_140047920; struct _TPM20_CMD_HEADER *
0x14002a1f6  mov     r9d, 157h; unsigned int
0x14002a1fc  mov     [rsp+68h+var_48], rdi; struct _TPM20_REPLY_HEADER *
0x14002a201  mov     rdx, r14; struct Tpm20Context *
0x14002a204  mov     rcx, rbp; this
0x14002a207  call    ?Tpm20SubmitInternalCommand@TpmStack@@QEAAJPEAVTpm20Context@@PEAU_TPM20_CMD_HEADER@@IPEAU_TPM20_REPLY_HEADER@@I@Z; TpmStack::Tpm20SubmitInternalCommand(Tpm20Context *,_TPM20_CMD_HEADER *,uint,_TPM20_REPLY_HEADER *,uint)
0x14002a20c  mov     ebx, eax
0x14002a20e  test    eax, eax
0x14002a210  js      short loc_14002A21F
0x14002a212  mov     r8, rsi
0x14002a215  mov     rdx, rdi
0x14002a218  call    Tpm20DecodeCreatePrimaryResponse
0x14002a21d  mov     ebx, eax
0x14002a21f  mov     rcx, rdi; void *
0x14002a222  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14002a227  mov     eax, ebx
0x14002a229  add     rsp, 38h
0x14002a22d  pop     r14
0x14002a22f  pop     r12
0x14002a231  pop     rdi
0x14002a232  pop     rsi
0x14002a233  pop     rbp
0x14002a234  pop     rbx
0x14002a235  retn
```
