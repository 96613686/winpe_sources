# CTftpSession::SendErrorResponse(void *)

- ea: `0x180006420`
- end: `0x180006587`
- name: `?SendErrorResponse@CTftpSession@@AEAAKPEAX@Z`
- size: `359`
- prototype: `__int64 __fastcall(CTftpSession *this, void *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000683c`
- `0x1800077e8`
- `0x180008180`

## callees

- `0x180006420`
- `0x180007b78`
- `0x18000b754`
- `0x18003ce78`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006443`
- `KERNEL32!EnterCriticalSection` at `0x180006443`
- `KERNEL32!LeaveCriticalSection` at `0x180006566`
- `KERNEL32!LeaveCriticalSection` at `0x180006566`

## string_xrefs

- `0x1800064dc`: `Access violation.`
- `0x1800064b8`: `The specified file already exists.`

## pseudocode

```c
__int64 __fastcall CTftpSession::SendErrorResponse(CTftpSession *this, void *a2)
{
  unsigned int v3; // edi
  u_short v5; // r9
  const char *v6; // rdx
  const char *v7; // rdx
  unsigned int v8; // eax
  struct CMemoryBuffer *v9; // rbx
  const char *v10; // rdx
  struct CMemoryBuffer *v12; // [rsp+40h] [rbp+8h] BYREF

  v3 = 0;
  v12 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = *((_WORD *)this + 1232);
  if ( v5 == 255 )
    goto LABEL_26;
  v6 = (const char *)*((_QWORD *)this + 309);
  if ( !v6 )
  {
    if ( v5 )
    {
      switch ( v5 )
      {
        case 1u:
          v6 = "The specified file was not found.";
          goto LABEL_21;
        case 2u:
          v6 = "Access violation.";
          goto LABEL_21;
        case 3u:
          v6 = "Disk full.";
          goto LABEL_21;
        case 4u:
          v6 = "Illegal operation error.";
          goto LABEL_21;
        case 5u:
          v6 = "Unknown transfer id.";
          goto LABEL_21;
        case 6u:
          v6 = "The specified file already exists.";
          goto LABEL_21;
        case 7u:
          v6 = "No such user exists.";
          goto LABEL_21;
        case 8u:
          v6 = "Option negotiation failed.";
LABEL_21:
          *((_QWORD *)this + 309) = v6;
          goto LABEL_22;
      }
    }
    v6 = "Undefined error.";
    goto LABEL_21;
  }
LABEL_22:
  v3 = CTftpPacket::CreateErrorPacket(v5, v6, &v12);
  v8 = ElValidateWin32(v3, v7, "base\\eco\\wds\\transport\\server\\tftp\\tftpsession.cpp", 0x199u);
  v9 = v12;
  if ( !v8 )
  {
    v3 = CTftpSession::SendReply(this, a2, v12);
    ElValidateWin32(v3, v10, "base\\eco\\wds\\transport\\server\\tftp\\tftpsession.cpp", 0x19Fu);
  }
  if ( v9 )
    (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v9 + 8LL))(v9);
LABEL_26:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v3;
}

```

## disassembly

```asm
0x180006420  mov     [rsp+arg_8], rbx
0x180006425  mov     [rsp+arg_10], rbp
0x18000642a  push    rsi
0x18000642b  push    rdi
0x18000642c  push    r14
0x18000642e  sub     rsp, 20h
0x180006432  mov     rsi, rcx
0x180006435  xor     edi, edi
0x180006437  and     [rsp+38h+arg_0], rdi
0x18000643c  add     rcx, 18h; lpCriticalSection
0x180006440  mov     r14, rdx
0x180006443  call    cs:__imp_EnterCriticalSection
0x18000644a  nop     dword ptr [rax+rax+00h]
0x18000644f  movzx   r9d, word ptr [rsi+9A0h]
0x180006457  mov     eax, 0FFh
0x18000645c  cmp     r9w, ax
0x180006460  jz      loc_180006562
0x180006466  mov     rdx, [rsi+9A8h]
0x18000646d  test    rdx, rdx
0x180006470  jnz     loc_1800064FC
0x180006476  movzx   ecx, r9w
0x18000647a  test    ecx, ecx
0x18000647c  jz      short loc_1800064EE
0x18000647e  sub     ecx, 1
0x180006481  jz      short loc_1800064E5
0x180006483  sub     ecx, 1
0x180006486  jz      short loc_1800064DC
0x180006488  sub     ecx, 1
0x18000648b  jz      short loc_1800064D3
0x18000648d  sub     ecx, 1
0x180006490  jz      short loc_1800064CA
0x180006492  sub     ecx, 1
0x180006495  jz      short loc_1800064C1
0x180006497  sub     ecx, 1
0x18000649a  jz      short loc_1800064B8
0x18000649c  sub     ecx, 1
0x18000649f  jz      short loc_1800064AF
0x1800064a1  cmp     ecx, 1
0x1800064a4  jnz     short loc_1800064EE
0x1800064a6  lea     rdx, aOptionNegotiat; "Option negotiation failed."
0x1800064ad  jmp     short loc_1800064F5
0x1800064af  lea     rdx, aNoSuchUserExis; "No such user exists."
0x1800064b6  jmp     short loc_1800064F5
0x1800064b8  lea     rdx, aTheSpecifiedFi_0; "The specified file already exists."
0x1800064bf  jmp     short loc_1800064F5
0x1800064c1  lea     rdx, aUnknownTransfe; "Unknown transfer id."
0x1800064c8  jmp     short loc_1800064F5
0x1800064ca  lea     rdx, aIllegalOperati; "Illegal operation error."
0x1800064d1  jmp     short loc_1800064F5
0x1800064d3  lea     rdx, aDiskFull; "Disk full."
0x1800064da  jmp     short loc_1800064F5
0x1800064dc  lea     rdx, aAccessViolatio; "Access violation."
0x1800064e3  jmp     short loc_1800064F5
0x1800064e5  lea     rdx, aTheSpecifiedFi; "The specified file was not found."
0x1800064ec  jmp     short loc_1800064F5
0x1800064ee  lea     rdx, aUndefinedError; "Undefined error."
0x1800064f5  mov     [rsi+9A8h], rdx
0x1800064fc  lea     r8, [rsp+38h+arg_0]; struct CMemoryBuffer **
0x180006501  movzx   ecx, r9w; unsigned __int16
0x180006505  call    ?CreateErrorPacket@CTftpPacket@@SAKGPEBDPEAPEAVCMemoryBuffer@@@Z; CTftpPacket::CreateErrorPacket(ushort,char const *,CMemoryBuffer * *)
0x18000650a  mov     r9d, 199h; unsigned int
0x180006510  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\tftp"...
0x180006517  mov     ecx, eax; unsigned int
0x180006519  mov     edi, eax
0x18000651b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180006520  mov     rbx, [rsp+38h+arg_0]
0x180006525  test    eax, eax
0x180006527  jnz     short loc_18000654D
0x180006529  mov     r8, rbx; struct CMemoryBuffer *
0x18000652c  mov     rdx, r14; void *
0x18000652f  mov     rcx, rsi; this
0x180006532  call    ?SendReply@CTftpSession@@AEAAKPEAXPEAVCMemoryBuffer@@@Z; CTftpSession::SendReply(void *,CMemoryBuffer *)
0x180006537  mov     r9d, 19Fh; unsigned int
0x18000653d  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\tftp"...
0x180006544  mov     ecx, eax; unsigned int
0x180006546  mov     edi, eax
0x180006548  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000654d  test    rbx, rbx
0x180006550  jz      short loc_180006562
0x180006552  mov     rax, [rbx]
0x180006555  mov     rcx, rbx
0x180006558  mov     rax, [rax+8]
0x18000655c  call    cs:__guard_dispatch_icall_fptr
0x180006562  lea     rcx, [rsi+18h]; lpCriticalSection
0x180006566  call    cs:__imp_LeaveCriticalSection
0x18000656d  nop     dword ptr [rax+rax+00h]
0x180006572  mov     rbx, [rsp+38h+arg_8]
0x180006577  mov     eax, edi
0x180006579  mov     rbp, [rsp+38h+arg_10]
0x18000657e  add     rsp, 20h
0x180006582  pop     r14
0x180006584  pop     rdi
0x180006585  pop     rsi
0x180006586  retn
```
