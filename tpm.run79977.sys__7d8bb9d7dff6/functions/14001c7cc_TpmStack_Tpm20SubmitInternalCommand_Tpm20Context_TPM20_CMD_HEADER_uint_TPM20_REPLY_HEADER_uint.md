# TpmStack::Tpm20SubmitInternalCommand(Tpm20Context *,_TPM20_CMD_HEADER *,uint,_TPM20_REPLY_HEADER *,uint)

- ea: `0x14001c7cc`
- end: `0x14001c93b`
- name: `?Tpm20SubmitInternalCommand@TpmStack@@QEAAJPEAVTpm20Context@@PEAU_TPM20_CMD_HEADER@@IPEAU_TPM20_REPLY_HEADER@@I@Z`
- size: `367`
- prototype: `int(TpmStack *__hidden this, struct Tpm20Context *, struct _TPM20_CMD_HEADER *, unsigned int, struct _TPM20_REPLY_HEADER *, unsigned int)`
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140008758`
- `0x14001c434`
- `0x14001d840`
- `0x140029eec`
- `0x14002a0ac`
- `0x14002a254`
- `0x14002a350`
- `0x14002a528`

## callees

- `0x1400034a8`
- `0x14000463c`
- `0x1400078b8`
- `0x140009278`
- `0x14000e98c`
- `0x14001c7cc`
- `0x140039b40`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001c8c3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c8c3`

## pseudocode

```c
__int64 __fastcall TpmStack::Tpm20SubmitInternalCommand(
        TpmSWAntiHammeringMgr ***this,
        struct Tpm20Context *a2,
        struct _TPM20_CMD_HEADER *a3,
        unsigned int a4,
        struct _TPM20_REPLY_HEADER *a5,
        unsigned int Size)
{
  unsigned int v11; // eax
  unsigned int v12; // edi
  struct Tpm20Request *v13; // [rsp+40h] [rbp-68h] BYREF
  _BYTE Object[32]; // [rsp+48h] [rbp-60h] BYREF
  int v15; // [rsp+68h] [rbp-40h]
  unsigned int v16; // [rsp+6Ch] [rbp-3Ch]

  v13 = 0;
  if ( TpmTransportType::m_Version != 2 )
    return 3221225659LL;
  memset(a5, 0, Size);
  if ( !Tpm20Context::CreateInternalTpm20Request(a2, (struct _TPM20RM_COMPLETION *)Object, 0, a3, a4, a5, Size, &v13) )
  {
    v11 = Tpm20Scheduler::SubmitRequest(this[2], v13);
    v12 = v11;
    if ( v11 )
    {
      Tpm20Context::CompleteTpm20Request((const void **)v13, v11);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_b13eeff4b5e83ce555d199d430c2416d_Traceguids, v12);
    }
    else
    {
      KeWaitForSingleObject(Object, Executive, 0, 0, 0);
      if ( !v15
        && v16 <= Size
        && v16 == _byteswap_ulong(*(_DWORD *)((char *)a5 + 2))
        && *(_WORD *)a5 == *(_WORD *)a3
        && !*(_DWORD *)((char *)a5 + 6) )
      {
        return 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_b13eeff4b5e83ce555d199d430c2416d_Traceguids);
    }
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x14001c7cc  push    rbx
0x14001c7ce  push    rbp
0x14001c7cf  push    rsi
0x14001c7d0  push    rdi
0x14001c7d1  push    r14
0x14001c7d3  push    r15
0x14001c7d5  sub     rsp, 78h
0x14001c7d9  cmp     cs:?m_Version@TpmTransportType@@0W4VERSION@1@A, 2; TpmTransportType::VERSION TpmTransportType::m_Version
0x14001c7e0  mov     r14d, r9d
0x14001c7e3  mov     rsi, r8
0x14001c7e6  mov     [rsp+0A8h+var_68], 0
0x14001c7ef  mov     r15, rdx
0x14001c7f2  mov     rdi, rcx
0x14001c7f5  jz      short loc_14001C801
0x14001c7f7  mov     eax, 0C00000BBh
0x14001c7fc  jmp     loc_14001C92D
0x14001c801  mov     ebp, dword ptr [rsp+0A8h+Size]
0x14001c808  xor     edx, edx; Val
0x14001c80a  mov     rbx, [rsp+0A8h+arg_20]
0x14001c812  mov     r8d, ebp; Size
0x14001c815  mov     rcx, rbx; void *
0x14001c818  call    memset
0x14001c81d  lea     rax, [rsp+0A8h+var_68]
0x14001c822  mov     r9, rsi; void *
0x14001c825  mov     [rsp+0A8h+var_70], rax; struct Tpm20Request **
0x14001c82a  lea     rdx, [rsp+0A8h+Object]; struct _TPM20RM_COMPLETION *
0x14001c82f  mov     [rsp+0A8h+var_78], ebp; unsigned int
0x14001c833  xor     r8d, r8d; void (*)(struct _TPM20RM_COMPLETION *)
0x14001c836  mov     [rsp+0A8h+var_80], rbx; void *
0x14001c83b  mov     rcx, r15; struct Tpm20Context *
0x14001c83e  mov     dword ptr [rsp+0A8h+Timeout], r14d; unsigned int
0x14001c843  call    ?CreateInternalTpm20Request@Tpm20Context@@SAJPEAV1@PEAU_TPM20RM_COMPLETION@@P6AX1@ZPEAXI3IPEAPEAVTpm20Request@@@Z; Tpm20Context::CreateInternalTpm20Request(Tpm20Context *,_TPM20RM_COMPLETION *,void (*)(_TPM20RM_COMPLETION *),void *,uint,void *,uint,Tpm20Request * *)
0x14001c848  test    eax, eax
0x14001c84a  jnz     loc_14001C928
0x14001c850  mov     rdx, [rsp+0A8h+var_68]; struct Tpm20Request *
0x14001c855  mov     rcx, [rdi+10h]; this
0x14001c859  call    ?SubmitRequest@Tpm20Scheduler@@QEAAJPEAVTpm20Request@@@Z; Tpm20Scheduler::SubmitRequest(Tpm20Request *)
0x14001c85e  mov     edi, eax
0x14001c860  test    eax, eax
0x14001c862  jz      short loc_14001C8AD
0x14001c864  mov     rcx, [rsp+0A8h+var_68]; this
0x14001c869  mov     edx, eax; int
0x14001c86b  call    ?CompleteTpm20Request@Tpm20Context@@SAXPEAVTpm20Request@@J@Z; Tpm20Context::CompleteTpm20Request(Tpm20Request *,long)
0x14001c870  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c877  lea     rdx, WPP_GLOBAL_Control
0x14001c87e  cmp     rcx, rdx
0x14001c881  jz      loc_14001C928
0x14001c887  mov     edx, [rcx+2Ch]
0x14001c88a  test    dl, 1
0x14001c88d  jz      loc_14001C928
0x14001c893  mov     rcx, [rcx+18h]
0x14001c897  lea     r8, WPP_b13eeff4b5e83ce555d199d430c2416d_Traceguids
0x14001c89e  mov     edx, 14h
0x14001c8a3  mov     r9d, edi
0x14001c8a6  call    WPP_SF_d
0x14001c8ab  jmp     short loc_14001C928
0x14001c8ad  xor     r9d, r9d; Alertable
0x14001c8b0  mov     [rsp+0A8h+Timeout], 0; Timeout
0x14001c8b9  xor     r8d, r8d; WaitMode
0x14001c8bc  lea     rcx, [rsp+0A8h+Object]; Object
0x14001c8c1  xor     edx, edx; WaitReason
0x14001c8c3  call    cs:__imp_KeWaitForSingleObject
0x14001c8ca  nop     dword ptr [rax+rax+00h]
0x14001c8cf  cmp     [rsp+0A8h+var_40], 0
0x14001c8d4  jnz     short loc_14001C8F9
0x14001c8d6  cmp     [rsp+0A8h+var_3C], ebp
0x14001c8da  ja      short loc_14001C8F9
0x14001c8dc  mov     eax, [rbx+2]
0x14001c8df  bswap   eax
0x14001c8e1  cmp     [rsp+0A8h+var_3C], eax
0x14001c8e5  jnz     short loc_14001C8F9
0x14001c8e7  movzx   eax, word ptr [rsi]
0x14001c8ea  cmp     [rbx], ax
0x14001c8ed  jnz     short loc_14001C8F9
0x14001c8ef  cmp     dword ptr [rbx+6], 0
0x14001c8f3  jnz     short loc_14001C8F9
0x14001c8f5  xor     eax, eax
0x14001c8f7  jmp     short loc_14001C92D
0x14001c8f9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c900  lea     rdx, WPP_GLOBAL_Control
0x14001c907  cmp     rcx, rdx
0x14001c90a  jz      short loc_14001C928
0x14001c90c  mov     eax, [rcx+2Ch]
0x14001c90f  test    al, 1
0x14001c911  jz      short loc_14001C928
0x14001c913  mov     rcx, [rcx+18h]
0x14001c917  lea     r8, WPP_b13eeff4b5e83ce555d199d430c2416d_Traceguids
0x14001c91e  mov     edx, 15h
0x14001c923  call    WPP_SF_
0x14001c928  mov     eax, 0C0000001h
0x14001c92d  add     rsp, 78h
0x14001c931  pop     r15
0x14001c933  pop     r14
0x14001c935  pop     rdi
0x14001c936  pop     rsi
0x14001c937  pop     rbp
0x14001c938  pop     rbx
0x14001c939  retn
```
