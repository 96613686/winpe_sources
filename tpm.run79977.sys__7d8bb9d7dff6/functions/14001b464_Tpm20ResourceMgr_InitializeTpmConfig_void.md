# Tpm20ResourceMgr::InitializeTpmConfig(void)

- ea: `0x14001b464`
- end: `0x14001b5ab`
- name: `?InitializeTpmConfig@Tpm20ResourceMgr@@QEAAJXZ`
- size: `327`
- prototype: `__int64 __fastcall(Tpm20ResourceMgr *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001db10`

## callees

- `0x140009278`
- `0x1400157a0`
- `0x140015b10`
- `0x14001b1ac`
- `0x14001b464`
- `0x140029130`
- `0x140029560`
- `0x140039740`

## pseudocode

```c
__int64 __fastcall Tpm20ResourceMgr::InitializeTpmConfig(struct TpmTransport **this)
{
  int Sizes; // ebx
  const union _TPM20_CMD_INFO **v3; // r8
  PDEVICE_OBJECT v4; // rcx
  __int128 v6; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v7; // [rsp+40h] [rbp-30h]
  unsigned int v8[4]; // [rsp+48h] [rbp-28h] BYREF
  __int128 v9; // [rsp+58h] [rbp-18h]

  Sizes = 0;
  v7 = 0;
  v6 = 0;
  *(_OWORD *)v8 = 0;
  v9 = 0;
  if ( !*((_BYTE *)this + 168) )
  {
    Sizes = Tpm20CmdGetSizes(*this, (struct _TPM20CMD_SIZES *)&v6);
    if ( Sizes >= 0 )
    {
      Tpm20ResourceMgr::m_TpmCmdSizes = v6;
      LODWORD(NumOfElements) = v7;
      *(&Tpm20ResourceMgr::m_TpmCmdSizes + 2) = DWORD2(v6) + 10;
      *(&Tpm20ResourceMgr::m_TpmCmdSizes + 3) = HIDWORD(v6) + 10;
      Sizes = Tpm20CmdGetCommandInfos(*this, v7, v3);
      if ( Sizes >= 0 )
      {
        Sizes = Tpm20GetTpmInformation(*this, v8);
        if ( Sizes >= 0 )
        {
          *((_DWORD *)this + 43) = v8[0];
          this[22] = (struct TpmTransport *)*((_QWORD *)&v9 + 1);
        }
      }
    }
    if ( Sizes )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids,
          (unsigned int)Sizes);
      if ( (TPMEnableBits & 1) != 0 )
        McTemplateK0dqq_EtwWriteTransfer(
          (__int64)v4,
          (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR,
          (__int64)v3,
          30,
          79,
          Sizes);
      Tpm20ResourceMgr::LogFailureModeInformation((Tpm20ResourceMgr *)this);
    }
  }
  return (unsigned int)Sizes;
}

```

## disassembly

```asm
0x14001b464  mov     [rsp-8+arg_8], rbx
0x14001b469  mov     [rsp-8+arg_10], rdi
0x14001b46e  push    rbp
0x14001b46f  mov     rbp, rsp
0x14001b472  sub     rsp, 70h
0x14001b476  mov     rax, cs:__security_cookie
0x14001b47d  xor     rax, rsp
0x14001b480  mov     [rbp+var_8], rax
0x14001b484  xor     eax, eax
0x14001b486  xorps   xmm1, xmm1
0x14001b489  xor     ebx, ebx
0x14001b48b  mov     [rbp+var_30], eax
0x14001b48e  xorps   xmm0, xmm0
0x14001b491  mov     rdi, rcx
0x14001b494  movups  [rbp+var_40], xmm0
0x14001b498  movups  xmmword ptr [rbp+var_28], xmm1
0x14001b49c  movups  [rbp+var_18], xmm1
0x14001b4a0  cmp     [rcx+0A8h], al
0x14001b4a6  jnz     loc_14001B58A
0x14001b4ac  mov     rcx, [rcx]; this
0x14001b4af  lea     rdx, [rbp+var_40]; struct _TPM20CMD_SIZES *
0x14001b4b3  call    ?Tpm20CmdGetSizes@@YAJPEAVTpmTransport@@PEAU_TPM20CMD_SIZES@@@Z; Tpm20CmdGetSizes(TpmTransport *,_TPM20CMD_SIZES *)
0x14001b4b8  mov     ebx, eax
0x14001b4ba  test    eax, eax
0x14001b4bc  js      short loc_14001B525
0x14001b4be  mov     rax, qword ptr [rbp+var_40]
0x14001b4c2  mov     edx, [rbp+var_30]; unsigned int
0x14001b4c5  mov     qword ptr cs:?m_TpmCmdSizes@Tpm20ResourceMgr@@0U_TPM20CMD_SIZES@@A, rax; _TPM20CMD_SIZES Tpm20ResourceMgr::m_TpmCmdSizes
0x14001b4cc  mov     eax, dword ptr [rbp+var_40+8]
0x14001b4cf  add     eax, 0Ah
0x14001b4d2  mov     cs:NumOfElements, edx
0x14001b4d8  mov     dword ptr cs:?m_TpmCmdSizes@Tpm20ResourceMgr@@0U_TPM20CMD_SIZES@@A+8, eax; _TPM20CMD_SIZES Tpm20ResourceMgr::m_TpmCmdSizes
0x14001b4de  mov     eax, dword ptr [rbp+var_40+0Ch]
0x14001b4e1  add     eax, 0Ah
0x14001b4e4  mov     dword ptr cs:?m_TpmCmdSizes@Tpm20ResourceMgr@@0U_TPM20CMD_SIZES@@A+0Ch, eax; _TPM20CMD_SIZES Tpm20ResourceMgr::m_TpmCmdSizes
0x14001b4ea  mov     rcx, [rdi]; this
0x14001b4ed  call    ?Tpm20CmdGetCommandInfos@@YAJPEAVTpmTransport@@IPEAPEBT_TPM20_CMD_INFO@@@Z; Tpm20CmdGetCommandInfos(TpmTransport *,uint,_TPM20_CMD_INFO const * *)
0x14001b4f2  mov     ebx, eax
0x14001b4f4  test    eax, eax
0x14001b4f6  js      short loc_14001B525
0x14001b4f8  mov     rcx, [rdi]; this
0x14001b4fb  lea     rdx, [rbp+var_28]; unsigned int *
0x14001b4ff  call    ?Tpm20GetTpmInformation@@YAJPEAVTpmTransport@@PEAI@Z; Tpm20GetTpmInformation(TpmTransport *,uint *)
0x14001b504  mov     ebx, eax
0x14001b506  test    eax, eax
0x14001b508  js      short loc_14001B525
0x14001b50a  mov     eax, [rbp+var_28]
0x14001b50d  mov     [rdi+0ACh], eax
0x14001b513  mov     eax, dword ptr [rbp+var_18+8]
0x14001b516  mov     [rdi+0B0h], eax
0x14001b51c  mov     eax, dword ptr [rbp+var_18+0Ch]
0x14001b51f  mov     [rdi+0B4h], eax
0x14001b525  test    ebx, ebx
0x14001b527  jz      short loc_14001B58A
0x14001b529  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001b530  lea     rax, WPP_GLOBAL_Control
0x14001b537  cmp     rcx, rax
0x14001b53a  jz      short loc_14001B55B
0x14001b53c  mov     eax, [rcx+2Ch]
0x14001b53f  test    al, 1
0x14001b541  jz      short loc_14001B55B
0x14001b543  mov     rcx, [rcx+18h]
0x14001b547  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x14001b54e  mov     edx, 0Bh
0x14001b553  mov     r9d, ebx
0x14001b556  call    WPP_SF_d
0x14001b55b  test    cs:TPMEnableBits, 1
0x14001b562  jz      short loc_14001B582
0x14001b564  mov     [rsp+70h+var_48], ebx
0x14001b568  lea     rdx, TPM_HW_PROTOCOL_ERROR
0x14001b56f  mov     r9d, 1Eh
0x14001b575  mov     [rsp+70h+var_50], 14Fh
0x14001b57d  call    McTemplateK0dqq_EtwWriteTransfer
0x14001b582  mov     rcx, rdi; this
0x14001b585  call    ?LogFailureModeInformation@Tpm20ResourceMgr@@AEAAXXZ; Tpm20ResourceMgr::LogFailureModeInformation(void)
0x14001b58a  mov     eax, ebx
0x14001b58c  mov     rcx, [rbp+var_8]
0x14001b590  xor     rcx, rsp; StackCookie
0x14001b593  call    __security_check_cookie
0x14001b598  lea     r11, [rsp+70h+var_s0]
0x14001b59d  mov     rbx, [r11+18h]
0x14001b5a1  mov     rdi, [r11+20h]
0x14001b5a5  mov     rsp, r11
0x14001b5a8  pop     rbp
0x14001b5a9  retn
```
