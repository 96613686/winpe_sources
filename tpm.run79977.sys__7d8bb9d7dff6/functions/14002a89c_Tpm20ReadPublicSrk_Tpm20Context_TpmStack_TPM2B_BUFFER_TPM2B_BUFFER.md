# Tpm20ReadPublicSrk(Tpm20Context *,TpmStack *,TPM2B_BUFFER *,TPM2B_BUFFER *)

- ea: `0x14002a89c`
- end: `0x14002aa29`
- name: `?Tpm20ReadPublicSrk@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAVTPM2B_BUFFER@@2@Z`
- size: `397`
- prototype: `__int64 __fastcall(struct Tpm20Context *, struct TpmStack *, struct TPM2B_BUFFER *, struct TPM2B_BUFFER *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14002d8b4`

## callees

- `0x1400078b8`
- `0x14000ca88`
- `0x14000d538`
- `0x14000dbf4`
- `0x140029100`
- `0x14002a89c`
- `0x140032eb4`
- `0x140045430`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall Tpm20ReadPublicSrk(
        struct Tpm20Context *a1,
        struct TpmStack *a2,
        struct TPM2B_BUFFER *a3,
        struct TPM2B_BUFFER *a4)
{
  unsigned __int8 *v6; // rsi
  int v7; // r8d
  int v8; // r9d
  int v9; // eax
  int v10; // ebx
  const unsigned __int8 **v11; // r9
  int v12; // eax
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned int *v15; // [rsp+20h] [rbp-E0h]
  int v16[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct TpmStack *v17; // [rsp+48h] [rbp-B8h]
  struct Tpm20Context *v18; // [rsp+50h] [rbp-B0h]
  _BYTE v19[56]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v20; // [rsp+98h] [rbp-68h]
  __int16 v21; // [rsp+9Ah] [rbp-66h]
  int v22; // [rsp+9Ch] [rbp-64h]
  __int16 v23; // [rsp+120h] [rbp+20h]
  __int16 v24; // [rsp+122h] [rbp+22h]
  __int16 v25; // [rsp+124h] [rbp+24h]
  __int16 v26; // [rsp+168h] [rbp+68h]
  __int16 v27; // [rsp+170h] [rbp+70h]
  unsigned __int64 retaddr; // [rsp+3C8h] [rbp+2C8h]
  unsigned int v29; // [rsp+3E8h] [rbp+2E8h] BYREF
  int v30; // [rsp+3ECh] [rbp+2ECh]

  v30 = HIDWORD(a4);
  v29 = 4096;
  v6 = TpmAlloc(1, 0x1000u, retaddr);
  tpm12class::TPMW8T_PUBLIC::TPMW8T_PUBLIC((tpm12class::TPMW8T_PUBLIC *)v19);
  *(_QWORD *)v16 = 0;
  v17 = a2;
  v18 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids);
  v9 = TpmApiReadPublic20((int)v16, -2130706431, v7, v8, v14, v6, &v29);
  v10 = HRESULTToNTSTATUS(v9);
  if ( v10 >= 0 )
  {
    v12 = tpm12class::TpmDataObject::Set((tpm12class::TpmDataObject *)v19, v6, v29, v11, v15);
    v10 = HRESULTToNTSTATUS(v12);
    if ( v10 >= 0
      && (v20 != 1
       || v21 != 11
       || (v22 & 0x70CF6) != 0x30472
       || v23 != 6
       || v25 != 67
       || v26 != 16
       || ((v24 - 128) & 0xFF7F) != 0
       || ((v27 - 2048) & 0xFBFF) != 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids);
      v10 = -1073741771;
    }
  }
  if ( v6 )
    TpmFree(v6);
  tpm12class::TPMW8T_PUBLIC::~TPMW8T_PUBLIC((tpm12class::TPMW8T_PUBLIC *)v19);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14002a89c  mov     qword ptr [rsp-8+arg_18], r9
0x14002a8a1  push    rbp
0x14002a8a2  push    rbx
0x14002a8a3  push    rsi
0x14002a8a4  push    rdi
0x14002a8a5  lea     rbp, [rsp-2A8h]
0x14002a8ad  sub     rsp, 3A8h
0x14002a8b4  mov     r8, [rbp+2C8h]; unsigned __int64
0x14002a8bb  mov     rbx, rdx
0x14002a8be  mov     edx, 1000h; unsigned __int64
0x14002a8c3  mov     rdi, rcx
0x14002a8c6  mov     cl, 1; bool
0x14002a8c8  mov     [rbp+2C0h+arg_18], edx
0x14002a8ce  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14002a8d3  lea     rcx, [rsp+3C0h+var_360]; this
0x14002a8d8  mov     rsi, rax
0x14002a8db  call    ??0TPMW8T_PUBLIC@tpm12class@@QEAA@XZ; tpm12class::TPMW8T_PUBLIC::TPMW8T_PUBLIC(void)
0x14002a8e0  mov     qword ptr [rsp+3C0h+var_380], 0
0x14002a8e9  mov     [rsp+3C0h+var_378], rbx
0x14002a8ee  mov     [rsp+3C0h+var_370], rdi
0x14002a8f3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a8fa  lea     rdi, WPP_GLOBAL_Control
0x14002a901  cmp     rcx, rdi
0x14002a904  jz      short loc_14002A922
0x14002a906  mov     eax, [rcx+2Ch]
0x14002a909  test    al, 4
0x14002a90b  jz      short loc_14002A922
0x14002a90d  mov     rcx, [rcx+18h]
0x14002a911  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x14002a918  mov     edx, 36h ; '6'
0x14002a91d  call    WPP_SF_
0x14002a922  lea     rax, [rbp+2C0h+arg_18]
0x14002a929  mov     edx, 81000001h; int
0x14002a92e  mov     [rsp+3C0h+var_390], rax; unsigned int *
0x14002a933  lea     rcx, [rsp+3C0h+var_380]; int
0x14002a938  mov     [rsp+3C0h+var_398], rsi; unsigned __int8 *
0x14002a93d  call    TpmApiReadPublic20
0x14002a942  mov     ecx, eax; int
0x14002a944  call    ?HRESULTToNTSTATUS@@YAJJ@Z; HRESULTToNTSTATUS(long)
0x14002a949  mov     ebx, eax
0x14002a94b  test    eax, eax
0x14002a94d  js      loc_14002AA03
0x14002a953  mov     r8d, [rbp+2C0h+arg_18]; unsigned int
0x14002a95a  lea     rcx, [rsp+3C0h+var_360]; this
0x14002a95f  mov     rdx, rsi; unsigned __int8 *
0x14002a962  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEBEIPEAPEBEPEAI@Z; tpm12class::TpmDataObject::Set(uchar const *,uint,uchar const * *,uint *)
0x14002a967  mov     ecx, eax; int
0x14002a969  call    ?HRESULTToNTSTATUS@@YAJJ@Z; HRESULTToNTSTATUS(long)
0x14002a96e  mov     ebx, eax
0x14002a970  test    eax, eax
0x14002a972  js      loc_14002AA03
0x14002a978  cmp     [rbp+2C0h+var_328], 1
0x14002a97d  jnz     short loc_14002A9D6
0x14002a97f  cmp     [rbp+2C0h+var_326], 0Bh
0x14002a984  jnz     short loc_14002A9D6
0x14002a986  mov     eax, [rbp+2C0h+var_324]
0x14002a989  and     eax, 70CF6h
0x14002a98e  cmp     eax, 30472h
0x14002a993  jnz     short loc_14002A9D6
0x14002a995  cmp     [rbp+2C0h+var_2A0], 6
0x14002a99a  jnz     short loc_14002A9D6
0x14002a99c  cmp     [rbp+2C0h+var_29C], 43h ; 'C'
0x14002a9a1  jnz     short loc_14002A9D6
0x14002a9a3  cmp     [rbp+2C0h+var_258], 10h
0x14002a9a8  jnz     short loc_14002A9D6
0x14002a9aa  movzx   eax, [rbp+2C0h+var_29E]
0x14002a9ae  mov     ecx, 80h
0x14002a9b3  sub     ax, cx
0x14002a9b6  mov     ecx, 0FF7Fh
0x14002a9bb  test    cx, ax
0x14002a9be  jnz     short loc_14002A9D6
0x14002a9c0  movzx   eax, [rbp+2C0h+var_250]
0x14002a9c4  mov     ecx, 800h
0x14002a9c9  sub     ax, cx
0x14002a9cc  mov     ecx, 0FBFFh
0x14002a9d1  test    cx, ax
0x14002a9d4  jz      short loc_14002AA03
0x14002a9d6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a9dd  cmp     rcx, rdi
0x14002a9e0  jz      short loc_14002A9FE
0x14002a9e2  mov     eax, [rcx+2Ch]
0x14002a9e5  test    al, 1
0x14002a9e7  jz      short loc_14002A9FE
0x14002a9e9  mov     rcx, [rcx+18h]
0x14002a9ed  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x14002a9f4  mov     edx, 37h ; '7'
0x14002a9f9  call    WPP_SF_
0x14002a9fe  mov     ebx, 0C0000035h
0x14002aa03  test    rsi, rsi
0x14002aa06  jz      short loc_14002AA10
0x14002aa08  mov     rcx, rsi; void *
0x14002aa0b  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14002aa10  lea     rcx, [rsp+3C0h+var_360]; this
0x14002aa15  call    ??1TPMW8T_PUBLIC@tpm12class@@UEAA@XZ; tpm12class::TPMW8T_PUBLIC::~TPMW8T_PUBLIC(void)
0x14002aa1a  mov     eax, ebx
0x14002aa1c  add     rsp, 3A8h
0x14002aa23  pop     rdi
0x14002aa24  pop     rsi
0x14002aa25  pop     rbx
0x14002aa26  pop     rbp
0x14002aa27  retn
```
