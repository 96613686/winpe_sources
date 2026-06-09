# Tpm20ReadPublicEk(Tpm20Context *,TpmStack *,TPM2B_BUFFER *,TPM2B_BUFFER *)

- ea: `0x14002a6c4`
- end: `0x14002a896`
- name: `?Tpm20ReadPublicEk@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAVTPM2B_BUFFER@@2@Z`
- size: `466`
- prototype: `int(struct Tpm20Context *, struct TpmStack *, struct TPM2B_BUFFER *, struct TPM2B_BUFFER *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14002d050`

## callees

- `0x1400078b8`
- `0x140009278`
- `0x14000ca88`
- `0x14000d538`
- `0x14000dbf4`
- `0x1400290b4`
- `0x140029100`
- `0x14002a6c4`
- `0x140032eb4`
- `0x140045430`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall Tpm20ReadPublicEk(
        struct Tpm20Context *a1,
        struct TpmStack *a2,
        struct TPM2B_BUFFER *a3,
        struct TPM2B_BUFFER *a4)
{
  unsigned __int8 *v8; // rsi
  int v9; // r8d
  int v10; // r9d
  int v11; // eax
  int v12; // ebx
  const unsigned __int8 **v13; // r9
  int v14; // ebx
  int v16; // [rsp+20h] [rbp-E0h]
  unsigned int *v17; // [rsp+20h] [rbp-E0h]
  int v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct TpmStack *v19; // [rsp+48h] [rbp-B8h]
  struct Tpm20Context *v20; // [rsp+50h] [rbp-B0h]
  _BYTE v21[60]; // [rsp+60h] [rbp-A0h] BYREF
  int v22; // [rsp+9Ch] [rbp-64h]
  unsigned __int16 v23; // [rsp+170h] [rbp+70h]
  unsigned __int16 v24; // [rsp+390h] [rbp+290h]
  unsigned __int8 *v25; // [rsp+398h] [rbp+298h]
  unsigned __int64 retaddr; // [rsp+3C8h] [rbp+2C8h]
  unsigned int v27; // [rsp+3D0h] [rbp+2D0h] BYREF

  v27 = 4096;
  v8 = TpmAlloc(1, 0x1000u, retaddr);
  tpm12class::TPMW8T_PUBLIC::TPMW8T_PUBLIC((tpm12class::TPMW8T_PUBLIC *)v21);
  *(_QWORD *)v18 = 0;
  v19 = a2;
  v20 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids);
  v11 = TpmApiReadPublic20((int)v18, -2130640895, v9, v10, v16, v8, &v27);
  v12 = HRESULTToNTSTATUS(v11);
  if ( v12 >= 0 )
  {
    v14 = tpm12class::TpmDataObject::Set((tpm12class::TpmDataObject *)v21, v8, v27, v13, v17);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids, v23);
    v12 = HRESULTToNTSTATUS(v14);
    if ( v12 >= 0 )
    {
      if ( (v22 & 0x30032) == 0x30032 )
      {
        if ( !a3 || (v12 = TPM2B_BUFFER::CopyFrom(a3, v25, v24), v12 >= 0) )
        {
          if ( a4 )
            v12 = TPM2B_BUFFER::CopyFrom(a4, v8, v27 - (unsigned __int64)v24 - 2);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids);
        v12 = -1073741771;
      }
    }
  }
  if ( v8 )
    TpmFree(v8);
  tpm12class::TPMW8T_PUBLIC::~TPMW8T_PUBLIC((tpm12class::TPMW8T_PUBLIC *)v21);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14002a6c4  mov     [rsp-8+arg_8], rbx
0x14002a6c9  mov     [rsp-8+arg_10], rsi
0x14002a6ce  push    rbp
0x14002a6cf  push    rdi
0x14002a6d0  push    r12
0x14002a6d2  push    r14
0x14002a6d4  push    r15
0x14002a6d6  lea     rbp, [rsp-2A0h]
0x14002a6de  sub     rsp, 3A0h
0x14002a6e5  mov     rbx, rdx
0x14002a6e8  mov     r14, r8
0x14002a6eb  mov     r8, [rbp+2C8h]; unsigned __int64
0x14002a6f2  mov     edx, 1000h; unsigned __int64
0x14002a6f7  mov     rdi, rcx
0x14002a6fa  mov     [rbp+2C0h+arg_0], edx
0x14002a700  mov     cl, 1; bool
0x14002a702  mov     r15, r9
0x14002a705  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14002a70a  lea     rcx, [rsp+3C0h+var_360]; this
0x14002a70f  mov     rsi, rax
0x14002a712  call    ??0TPMW8T_PUBLIC@tpm12class@@QEAA@XZ; tpm12class::TPMW8T_PUBLIC::TPMW8T_PUBLIC(void)
0x14002a717  mov     qword ptr [rsp+3C0h+var_380], 0
0x14002a720  mov     [rsp+3C0h+var_378], rbx
0x14002a725  mov     [rsp+3C0h+var_370], rdi
0x14002a72a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a731  lea     r12, WPP_GLOBAL_Control
0x14002a738  lea     rdi, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x14002a73f  cmp     rcx, r12
0x14002a742  jz      short loc_14002A75C
0x14002a744  mov     eax, [rcx+2Ch]
0x14002a747  test    al, 4
0x14002a749  jz      short loc_14002A75C
0x14002a74b  mov     rcx, [rcx+18h]
0x14002a74f  mov     edx, 38h ; '8'
0x14002a754  mov     r8, rdi
0x14002a757  call    WPP_SF_
0x14002a75c  lea     rax, [rbp+2C0h+arg_0]
0x14002a763  mov     edx, 81010001h; int
0x14002a768  mov     [rsp+3C0h+var_390], rax; unsigned int *
0x14002a76d  lea     rcx, [rsp+3C0h+var_380]; int
0x14002a772  mov     [rsp+3C0h+var_398], rsi; unsigned __int8 *
0x14002a777  call    TpmApiReadPublic20
0x14002a77c  mov     ecx, eax; int
0x14002a77e  call    ?HRESULTToNTSTATUS@@YAJJ@Z; HRESULTToNTSTATUS(long)
0x14002a783  mov     ebx, eax
0x14002a785  test    eax, eax
0x14002a787  js      loc_14002A860
0x14002a78d  mov     r8d, [rbp+2C0h+arg_0]; unsigned int
0x14002a794  lea     rcx, [rsp+3C0h+var_360]; this
0x14002a799  mov     rdx, rsi; unsigned __int8 *
0x14002a79c  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEBEIPEAPEBEPEAI@Z; tpm12class::TpmDataObject::Set(uchar const *,uint,uchar const * *,uint *)
0x14002a7a1  mov     ebx, eax
0x14002a7a3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a7aa  cmp     rcx, r12
0x14002a7ad  jz      short loc_14002A7CD
0x14002a7af  mov     edx, [rcx+2Ch]
0x14002a7b2  test    dl, 4
0x14002a7b5  jz      short loc_14002A7CD
0x14002a7b7  movzx   r9d, [rbp+2C0h+var_250]
0x14002a7bc  mov     edx, 39h ; '9'
0x14002a7c1  mov     rcx, [rcx+18h]
0x14002a7c5  mov     r8, rdi
0x14002a7c8  call    WPP_SF_d
0x14002a7cd  mov     ecx, ebx; int
0x14002a7cf  call    ?HRESULTToNTSTATUS@@YAJJ@Z; HRESULTToNTSTATUS(long)
0x14002a7d4  mov     ebx, eax
0x14002a7d6  test    eax, eax
0x14002a7d8  js      loc_14002A860
0x14002a7de  mov     eax, [rbp+2C0h+var_324]
0x14002a7e1  mov     ecx, 30032h
0x14002a7e6  and     eax, ecx
0x14002a7e8  cmp     eax, ecx
0x14002a7ea  jz      short loc_14002A817
0x14002a7ec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a7f3  cmp     rcx, r12
0x14002a7f6  jz      short loc_14002A810
0x14002a7f8  mov     eax, [rcx+2Ch]
0x14002a7fb  test    al, 1
0x14002a7fd  jz      short loc_14002A810
0x14002a7ff  mov     rcx, [rcx+18h]
0x14002a803  mov     edx, 3Ah ; ':'
0x14002a808  mov     r8, rdi
0x14002a80b  call    WPP_SF_
0x14002a810  mov     ebx, 0C0000035h
0x14002a815  jmp     short loc_14002A860
0x14002a817  test    r14, r14
0x14002a81a  jz      short loc_14002A839
0x14002a81c  movzx   r8d, [rbp+2C0h+var_30]; unsigned __int64
0x14002a824  mov     rcx, r14; this
0x14002a827  mov     rdx, [rbp+2C0h+var_28]; unsigned __int8 *
0x14002a82e  call    ?CopyFrom@TPM2B_BUFFER@@QEAAJPEBE_K@Z; TPM2B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x14002a833  mov     ebx, eax
0x14002a835  test    eax, eax
0x14002a837  js      short loc_14002A860
0x14002a839  test    r15, r15
0x14002a83c  jz      short loc_14002A860
0x14002a83e  movzx   eax, [rbp+2C0h+var_30]
0x14002a845  mov     rdx, rsi; unsigned __int8 *
0x14002a848  mov     r8d, [rbp+2C0h+arg_0]
0x14002a84f  mov     rcx, r15; this
0x14002a852  sub     r8, rax
0x14002a855  sub     r8, 2; unsigned __int64
0x14002a859  call    ?CopyFrom@TPM2B_BUFFER@@QEAAJPEBE_K@Z; TPM2B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x14002a85e  mov     ebx, eax
0x14002a860  test    rsi, rsi
0x14002a863  jz      short loc_14002A86D
0x14002a865  mov     rcx, rsi; void *
0x14002a868  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14002a86d  lea     rcx, [rsp+3C0h+var_360]; this
0x14002a872  call    ??1TPMW8T_PUBLIC@tpm12class@@UEAA@XZ; tpm12class::TPMW8T_PUBLIC::~TPMW8T_PUBLIC(void)
0x14002a877  lea     r11, [rsp+3C0h+var_20]
0x14002a87f  mov     eax, ebx
0x14002a881  mov     rbx, [r11+38h]
0x14002a885  mov     rsi, [r11+40h]
0x14002a889  mov     rsp, r11
0x14002a88c  pop     r15
0x14002a88e  pop     r14
0x14002a890  pop     r12
0x14002a892  pop     rdi
0x14002a893  pop     rbp
0x14002a894  retn
```
