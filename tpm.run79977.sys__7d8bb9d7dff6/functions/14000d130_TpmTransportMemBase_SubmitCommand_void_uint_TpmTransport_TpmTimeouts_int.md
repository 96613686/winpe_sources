# TpmTransportMemBase::SubmitCommand(void *,uint,TpmTransport::TpmTimeouts *,int)

- ea: `0x14000d130`
- end: `0x14000d52f`
- name: `?SubmitCommand@TpmTransportMemBase@@UEAAJPEAXIPEAVTpmTimeouts@TpmTransport@@H@Z`
- size: `1023`
- prototype: `__int64 __usercall@<rax>(TpmTransportMemBase *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, struct TpmTransport::TpmTimeouts *@<r9>, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1400078b8`
- `0x14000ca88`
- `0x14000d130`
- `0x14000d538`
- `0x14000dbf4`
- `0x14000df1c`
- `0x140019e38`
- `0x14001b1ac`
- `0x140039780`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000d1a5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d1a5`
- `ntoskrnl!KeReleaseMutex` at `0x14000d2a7`
- `ntoskrnl!KeReleaseMutex` at `0x14000d314`
- `ntoskrnl!KeReleaseMutex` at `0x14000d2a7`
- `ntoskrnl!KeReleaseMutex` at `0x14000d314`

## pseudocode

```c
__int64 __fastcall TpmTransportMemBase::SubmitCommand(
        TpmTransportMemBase *this,
        char *a2,
        unsigned int a3,
        struct TpmTransport::TpmTimeouts *a4,
        int a5)
{
  int v9; // esi
  __int64 v10; // r8
  __int64 v11; // rax
  unsigned int v12; // edx
  __int64 v13; // r8
  const unsigned __int8 **v14; // r9
  unsigned __int32 v15; // eax
  unsigned int v16; // esi
  int v17; // eax
  PDEVICE_OBJECT v19; // rcx
  PDEVICE_OBJECT v20; // rcx
  PDEVICE_OBJECT v21; // rcx
  unsigned __int32 v22; // ecx
  __int64 v23; // rdx
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-388h]
  _BYTE v25[56]; // [rsp+30h] [rbp-378h] BYREF
  __int16 v26; // [rsp+68h] [rbp-340h]
  __int16 v27; // [rsp+140h] [rbp-268h]

  tpm12class::TPMW8T_PUBLIC::TPMW8T_PUBLIC((tpm12class::TPMW8T_PUBLIC *)v25);
  v9 = (*(__int64 (__fastcall **)(TpmTransportMemBase *, char *, _QWORD, struct TpmTransport::TpmTimeouts *, int))(*(_QWORD *)this + 144LL))(
         this,
         a2,
         a3,
         a4,
         a5);
  if ( v9 < 0 )
    goto LABEL_17;
  KeWaitForSingleObject((char *)this + 128, Executive, 0, 0, 0);
  v11 = *((_QWORD *)this + 39);
  if ( !v11 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_8de2460abc9d340e43d1e35357ca3f8a_Traceguids);
    v9 = -1073741434;
    if ( (TPMEnableBits & 1) != 0 )
      McTemplateK0dqq_EtwWriteTransfer((__int64)v19, (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR, v10, 34, 159, 134);
    goto LABEL_21;
  }
  if ( *(_DWORD *)(v11 + 12) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_8de2460abc9d340e43d1e35357ca3f8a_Traceguids);
    v9 = -1073740024;
    goto LABEL_21;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 39) + 4LL) )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_8de2460abc9d340e43d1e35357ca3f8a_Traceguids);
    *((_DWORD *)this + 2) = -1073741434;
    if ( (TPMEnableBits & 1) != 0 )
      McTemplateK0dqq_EtwWriteTransfer((__int64)v20, (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR, v10, 34, 186, 134);
    v9 = *((_DWORD *)this + 2);
    goto LABEL_21;
  }
  if ( a3 > (*(unsigned int (__fastcall **)(TpmTransportMemBase *))(*(_QWORD *)this + 96LL))(this) )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_8de2460abc9d340e43d1e35357ca3f8a_Traceguids);
    if ( (TPMEnableBits & 1) != 0 )
      McTemplateK0dqq_EtwWriteTransfer((__int64)v21, (const EVENT_DESCRIPTOR *)TPM_HW_STATE_ERROR, v13, 34, 202, a3);
    v9 = -1073741811;
    goto LABEL_21;
  }
  if ( *((_DWORD *)this + 16) == 2 || a5 && *((_DWORD *)this + 16) == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_8de2460abc9d340e43d1e35357ca3f8a_Traceguids);
    v9 = -1073741536;
    goto LABEL_21;
  }
  *(_DWORD *)(*((_QWORD *)this + 39) + 8LL) = 0;
  v9 = TpmTransportMemBase::CopyToCommandBuffer(this, v12, a2, a3);
  if ( v9 < 0 || (v9 = (*(__int64 (__fastcall **)(TpmTransportMemBase *))(*(_QWORD *)this + 152LL))(this), v9 < 0) )
  {
LABEL_21:
    KeReleaseMutex((PRKMUTEX)((char *)this + 128), 0);
    goto LABEL_17;
  }
  *(_DWORD *)(*((_QWORD *)this + 39) + 12LL) = 1;
  v15 = _byteswap_ulong(*(_DWORD *)(a2 + 6)) - 305;
  if ( !v15 || v15 == 34 )
  {
    v16 = *((_DWORD *)this + 63);
    v22 = _byteswap_ulong(*(_DWORD *)(a2 + 14));
    v23 = (unsigned __int16)__ROR2__(*(_WORD *)&a2[v22 + 18], 8) + v22 + 22;
    if ( (unsigned int)v23 <= a3
      && tpm12class::TpmDataObject::Set(
           (tpm12class::TpmDataObject *)v25,
           (const unsigned __int8 *)&a2[v23],
           a3 - v23,
           v14,
           (unsigned int *)Timeout) >= 0
      && v26 == 1 )
    {
      if ( v27 == 3072 )
      {
        v16 = 260000;
      }
      else if ( v27 == 4096 )
      {
        v16 = 590000;
      }
    }
  }
  else
  {
    v16 = *((_DWORD *)this + 62);
  }
  *((_QWORD *)this + 63) = MEMORY[0xFFFFF78000000008] + 10000LL * v16;
  KeReleaseMutex((PRKMUTEX)((char *)this + 128), 0);
  if ( *((_QWORD *)this + 60) )
    v17 = TpmTransportMemBase::TreeVendorExecuteCommand(this);
  else
    v17 = (*(__int64 (__fastcall **)(TpmTransportMemBase *))(*(_QWORD *)this + 176LL))(this);
  v9 = v17;
LABEL_17:
  tpm12class::TPMW8T_PUBLIC::~TPMW8T_PUBLIC((tpm12class::TPMW8T_PUBLIC *)v25);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000d130  push    rbx
0x14000d132  push    rbp
0x14000d133  push    rsi
0x14000d134  push    rdi
0x14000d135  push    r12
0x14000d137  push    r14
0x14000d139  push    r15
0x14000d13b  sub     rsp, 370h
0x14000d142  mov     rdi, rcx
0x14000d145  mov     rbx, r9
0x14000d148  lea     rcx, [rsp+3A8h+var_378]; this
0x14000d14d  mov     ebp, r8d
0x14000d150  mov     r14, rdx
0x14000d153  call    ??0TPMW8T_PUBLIC@tpm12class@@QEAA@XZ; tpm12class::TPMW8T_PUBLIC::TPMW8T_PUBLIC(void)
0x14000d158  mov     rax, [rdi]
0x14000d15b  mov     r9, rbx
0x14000d15e  mov     r12d, [rsp+3A8h+arg_20]
0x14000d166  mov     r8d, ebp
0x14000d169  mov     rdx, r14
0x14000d16c  mov     dword ptr [rsp+3A8h+Timeout], r12d
0x14000d171  mov     rcx, rdi
0x14000d174  mov     rax, [rax+90h]
0x14000d17b  call    _guard_dispatch_icall
0x14000d180  mov     esi, eax
0x14000d182  test    eax, eax
0x14000d184  js      loc_14000D2C7
0x14000d18a  lea     r15, [rdi+80h]
0x14000d191  mov     [rsp+3A8h+Timeout], 0; unsigned int *
0x14000d19a  mov     rcx, r15; Object
0x14000d19d  xor     r9d, r9d; Alertable
0x14000d1a0  xor     r8d, r8d; WaitMode
0x14000d1a3  xor     edx, edx; WaitReason
0x14000d1a5  call    cs:__imp_KeWaitForSingleObject
0x14000d1ac  nop     dword ptr [rax+rax+00h]
0x14000d1b1  mov     rax, [rdi+138h]
0x14000d1b8  test    rax, rax
0x14000d1bb  jz      loc_14000D343
0x14000d1c1  mov     eax, [rax+0Ch]
0x14000d1c4  test    eax, eax
0x14000d1c6  jnz     loc_14000D2F7
0x14000d1cc  mov     rax, [rdi+138h]
0x14000d1d3  mov     ecx, [rax+4]
0x14000d1d6  test    ecx, ecx
0x14000d1d8  jnz     loc_14000D3A9
0x14000d1de  mov     rax, [rdi]
0x14000d1e1  mov     rcx, rdi
0x14000d1e4  mov     rax, [rax+60h]
0x14000d1e8  call    _guard_dispatch_icall
0x14000d1ed  cmp     ebp, eax
0x14000d1ef  ja      loc_14000D414
0x14000d1f5  mov     eax, [rdi+40h]
0x14000d1f8  cmp     eax, 2
0x14000d1fb  jz      loc_14000D4F6
0x14000d201  mov     ebx, 1
0x14000d206  test    r12d, r12d
0x14000d209  jz      short loc_14000D216
0x14000d20b  mov     eax, [rdi+40h]
0x14000d20e  cmp     eax, ebx
0x14000d210  jz      loc_14000D4F6
0x14000d216  mov     rax, [rdi+138h]
0x14000d21d  mov     r9d, ebp; unsigned int
0x14000d220  mov     r8, r14; void *
0x14000d223  mov     rcx, rdi; this
0x14000d226  mov     dword ptr [rax+8], 0
0x14000d22d  call    ?CopyToCommandBuffer@TpmTransportMemBase@@AEAAJIPEAXI@Z; TpmTransportMemBase::CopyToCommandBuffer(uint,void *,uint)
0x14000d232  mov     esi, eax
0x14000d234  test    eax, eax
0x14000d236  js      loc_14000D30F
0x14000d23c  mov     rax, [rdi]
0x14000d23f  mov     rcx, rdi
0x14000d242  mov     rax, [rax+98h]
0x14000d249  call    _guard_dispatch_icall
0x14000d24e  mov     esi, eax
0x14000d250  test    eax, eax
0x14000d252  js      loc_14000D30F
0x14000d258  mov     rax, [rdi+138h]
0x14000d25f  mov     [rax+0Ch], ebx
0x14000d262  mov     eax, [r14+6]
0x14000d266  bswap   eax
0x14000d268  sub     eax, 131h
0x14000d26d  jz      loc_14000D476
0x14000d273  cmp     eax, 22h ; '"'
0x14000d276  jz      loc_14000D476
0x14000d27c  mov     esi, [rdi+0F8h]
0x14000d282  mov     eax, esi
0x14000d284  mov     r8, 0FFFFF78000000008h
0x14000d28e  imul    rdx, rax, 2710h
0x14000d295  mov     r8, [r8]
0x14000d298  mov     rcx, r15; Mutex
0x14000d29b  add     rdx, r8
0x14000d29e  mov     [rdi+1F8h], rdx
0x14000d2a5  xor     edx, edx; Wait
0x14000d2a7  call    cs:__imp_KeReleaseMutex
0x14000d2ae  nop     dword ptr [rax+rax+00h]
0x14000d2b3  cmp     qword ptr [rdi+1E0h], 0
0x14000d2bb  mov     rcx, rdi; this
0x14000d2be  jz      short loc_14000D2E6
0x14000d2c0  call    ?TreeVendorExecuteCommand@TpmTransportMemBase@@AEAAJXZ; TpmTransportMemBase::TreeVendorExecuteCommand(void)
0x14000d2c5  mov     esi, eax
0x14000d2c7  lea     rcx, [rsp+3A8h+var_378]; this
0x14000d2cc  call    ??1TPMW8T_PUBLIC@tpm12class@@UEAA@XZ; tpm12class::TPMW8T_PUBLIC::~TPMW8T_PUBLIC(void)
0x14000d2d1  mov     eax, esi
0x14000d2d3  add     rsp, 370h
0x14000d2da  pop     r15
0x14000d2dc  pop     r14
0x14000d2de  pop     r12
0x14000d2e0  pop     rdi
0x14000d2e1  pop     rsi
0x14000d2e2  pop     rbp
0x14000d2e3  pop     rbx
0x14000d2e4  retn
0x14000d2e6  mov     rax, [rdi]
0x14000d2e9  mov     rax, [rax+0B0h]
0x14000d2f0  call    _guard_dispatch_icall
0x14000d2f5  jmp     short loc_14000D2C5
0x14000d2f7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000d2fe  lea     rax, WPP_GLOBAL_Control
0x14000d305  cmp     rcx, rax
0x14000d308  jnz     short loc_14000D322
0x14000d30a  mov     esi, 0C0000708h
0x14000d30f  xor     edx, edx; Wait
0x14000d311  mov     rcx, r15; Mutex
0x14000d314  call    cs:__imp_KeReleaseMutex
0x14000d31b  nop     dword ptr [rax+rax+00h]
0x14000d320  jmp     short loc_14000D2C7
0x14000d322  mov     eax, [rcx+2Ch]
0x14000d325  mov     ebx, 1
0x14000d32a  test    bl, al
0x14000d32c  jz      short loc_14000D30A
0x14000d32e  mov     rcx, [rcx+18h]
0x14000d332  lea     edx, [rbx+0Fh]
0x14000d335  lea     r8, WPP_8de2460abc9d340e43d1e35357ca3f8a_Traceguids
0x14000d33c  call    WPP_SF_
0x14000d341  jmp     short loc_14000D30A
0x14000d343  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000d34a  lea     rax, WPP_GLOBAL_Control
0x14000d351  mov     ebx, 1
0x14000d356  cmp     rcx, rax
0x14000d359  jz      short loc_14000D375
0x14000d35b  mov     eax, [rcx+2Ch]
0x14000d35e  test    bl, al
0x14000d360  jz      short loc_14000D375
0x14000d362  mov     rcx, [rcx+18h]
0x14000d366  lea     edx, [rbx+0Eh]
0x14000d369  lea     r8, WPP_8de2460abc9d340e43d1e35357ca3f8a_Traceguids
0x14000d370  call    WPP_SF_
0x14000d375  test    cs:TPMEnableBits, bl
0x14000d37b  mov     esi, 0C0000186h
0x14000d380  jz      short loc_14000D30F
0x14000d382  mov     [rsp+3A8h+var_380], 0C0000186h
0x14000d38a  lea     rdx, TPM_HW_PROTOCOL_ERROR
0x14000d391  mov     r9d, 22h ; '"'
0x14000d397  mov     dword ptr [rsp+3A8h+Timeout], 29Fh
0x14000d39f  call    McTemplateK0dqq_EtwWriteTransfer
0x14000d3a4  jmp     loc_14000D30F
0x14000d3a9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000d3b0  lea     rax, WPP_GLOBAL_Control
0x14000d3b7  mov     ebx, 1
0x14000d3bc  cmp     rcx, rax
0x14000d3bf  jz      short loc_14000D3DB
0x14000d3c1  mov     eax, [rcx+2Ch]
0x14000d3c4  test    bl, al
0x14000d3c6  jz      short loc_14000D3DB
0x14000d3c8  mov     rcx, [rcx+18h]
0x14000d3cc  lea     edx, [rbx+10h]
0x14000d3cf  lea     r8, WPP_8de2460abc9d340e43d1e35357ca3f8a_Traceguids
0x14000d3d6  call    WPP_SF_
0x14000d3db  mov     dword ptr [rdi+8], 0C0000186h
0x14000d3e2  test    cs:TPMEnableBits, bl
0x14000d3e8  jz      short loc_14000D40C
0x14000d3ea  mov     [rsp+3A8h+var_380], 0C0000186h
0x14000d3f2  lea     rdx, TPM_HW_PROTOCOL_ERROR
0x14000d3f9  mov     r9d, 22h ; '"'
0x14000d3ff  mov     dword ptr [rsp+3A8h+Timeout], 2BAh
0x14000d407  call    McTemplateK0dqq_EtwWriteTransfer
0x14000d40c  mov     esi, [rdi+8]
0x14000d40f  jmp     loc_14000D30F
0x14000d414  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000d41b  lea     rax, WPP_GLOBAL_Control
0x14000d422  mov     ebx, 1
0x14000d427  cmp     rcx, rax
0x14000d42a  jz      short loc_14000D446
0x14000d42c  mov     eax, [rcx+2Ch]
0x14000d42f  test    bl, al
0x14000d431  jz      short loc_14000D446
0x14000d433  mov     rcx, [rcx+18h]
0x14000d437  lea     edx, [rbx+11h]
0x14000d43a  lea     r8, WPP_8de2460abc9d340e43d1e35357ca3f8a_Traceguids
0x14000d441  call    WPP_SF_
0x14000d446  test    cs:TPMEnableBits, bl
0x14000d44c  jz      short loc_14000D46C
0x14000d44e  mov     [rsp+3A8h+var_380], ebp
0x14000d452  lea     rdx, TPM_HW_STATE_ERROR
0x14000d459  mov     r9d, 22h ; '"'
0x14000d45f  mov     dword ptr [rsp+3A8h+Timeout], 2CAh
0x14000d467  call    McTemplateK0dqq_EtwWriteTransfer
0x14000d46c  mov     esi, 0C000000Dh
0x14000d471  jmp     loc_14000D30F
0x14000d476  mov     ecx, [r14+0Eh]
0x14000d47a  mov     esi, [rdi+0FCh]
0x14000d480  bswap   ecx
0x14000d482  mov     ecx, ecx
0x14000d484  movzx   eax, word ptr [rcx+r14+12h]
0x14000d48a  lea     edx, [rcx+16h]
0x14000d48d  ror     ax, 8
0x14000d491  movzx   eax, ax
0x14000d494  add     edx, eax
0x14000d496  cmp     edx, ebp
0x14000d498  ja      loc_14000D282
0x14000d49e  sub     ebp, edx
0x14000d4a0  lea     rcx, [rsp+3A8h+var_378]; this
0x14000d4a5  mov     r8d, ebp; unsigned int
0x14000d4a8  add     rdx, r14; unsigned __int8 *
0x14000d4ab  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEBEIPEAPEBEPEAI@Z; tpm12class::TpmDataObject::Set(uchar const *,uint,uchar const * *,uint *)
0x14000d4b0  test    eax, eax
0x14000d4b2  js      loc_14000D282
0x14000d4b8  cmp     [rsp+3A8h+var_340], bx
0x14000d4bd  jnz     loc_14000D282
0x14000d4c3  mov     eax, 0C00h
0x14000d4c8  cmp     [rsp+3A8h+var_268], ax
0x14000d4d0  jnz     short loc_14000D4DC
0x14000d4d2  mov     esi, 3F7A0h
0x14000d4d7  jmp     loc_14000D282
0x14000d4dc  mov     eax, 1000h
0x14000d4e1  mov     ecx, 900B0h
0x14000d4e6  cmp     [rsp+3A8h+var_268], ax
0x14000d4ee  cmovz   esi, ecx
0x14000d4f1  jmp     loc_14000D282
0x14000d4f6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000d4fd  lea     rax, WPP_GLOBAL_Control
0x14000d504  cmp     rcx, rax
0x14000d507  jz      short loc_14000D525
0x14000d509  mov     eax, [rcx+2Ch]
0x14000d50c  test    al, 4
0x14000d50e  jz      short loc_14000D525
0x14000d510  mov     rcx, [rcx+18h]
0x14000d514  lea     r8, WPP_8de2460abc9d340e43d1e35357ca3f8a_Traceguids
0x14000d51b  mov     edx, 13h
0x14000d520  call    WPP_SF_
0x14000d525  mov     esi, 0C0000120h
0x14000d52a  jmp     loc_14000D30F
```
