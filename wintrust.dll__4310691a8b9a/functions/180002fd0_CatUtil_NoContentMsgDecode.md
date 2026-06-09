# CatUtil_NoContentMsgDecode

- ea: `0x180002fd0`
- end: `0x18000307f`
- name: `CatUtil_NoContentMsgDecode`
- size: `175`
- prototype: `HCRYPTMSG __fastcall(BYTE *pbData, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001cd8`
- `0x180002ef0`

## callees

- `0x180002fd0`

## import_xrefs

- `CRYPT32!CryptMsgOpenToDecode` at `0x180003017`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180003017`
- `CRYPT32!CryptMsgUpdate` at `0x180003045`
- `CRYPT32!CryptMsgUpdate` at `0x180003045`
- `CRYPT32!CryptMsgClose` at `0x180003064`
- `CRYPT32!CryptMsgClose` at `0x180003064`

## pseudocode

```c
HCRYPTMSG __fastcall CatUtil_NoContentMsgDecode(BYTE *pbData, unsigned int a2)
{
  HCRYPTMSG v4; // r14
  BOOL v5; // ebp
  DWORD v6; // ebx
  struct _CMSG_STREAM_INFO pStreamInfo; // [rsp+30h] [rbp-58h] BYREF

  pStreamInfo.pfnStreamOutput = (PFN_CMSG_STREAM_OUTPUT)SIPObjectDetachedSignature_::VerifyIndirectData;
  *(_QWORD *)&pStreamInfo.cbContent = 0;
  pStreamInfo.pvArg = 0;
  v4 = CryptMsgOpenToDecode(0x10001u, 0, 0, 0, 0, &pStreamInfo);
  if ( v4 )
  {
    v5 = 0;
    while ( !v5 )
    {
      if ( a2 <= 0x1000 )
      {
        v6 = a2;
        v5 = 1;
      }
      else
      {
        v6 = 4096;
      }
      if ( !CryptMsgUpdate(v4, pbData, v6, v5) )
        goto LABEL_9;
      a2 -= v6;
      pbData += v6;
    }
    return v4;
  }
  else
  {
LABEL_9:
    CryptMsgClose(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x180002fd0  push    rbx
0x180002fd2  push    rbp
0x180002fd3  push    rsi
0x180002fd4  push    rdi
0x180002fd5  push    r14
0x180002fd7  push    r15
0x180002fd9  sub     rsp, 58h
0x180002fdd  xor     r15d, r15d
0x180002fe0  lea     rax, ?VerifyIndirectData@SIPObjectDetachedSignature_@@UEAAHPEAUSIP_SUBJECTINFO_@@PEAUSIP_INDIRECT_DATA_@@@Z; SIPObjectDetachedSignature_::VerifyIndirectData(SIP_SUBJECTINFO_ *,SIP_INDIRECT_DATA_ *)
0x180002fe7  mov     [rsp+88h+var_58.pfnStreamOutput], rax
0x180002fec  mov     edi, edx
0x180002fee  lea     rax, [rsp+88h+var_58]
0x180002ff3  mov     qword ptr [rsp+88h+var_58.cbContent], r15
0x180002ff8  mov     rsi, rcx
0x180002ffb  mov     [rsp+88h+pStreamInfo], rax; pStreamInfo
0x180003000  xor     r9d, r9d; hCryptProv
0x180003003  mov     [rsp+88h+pRecipientInfo], r15; pRecipientInfo
0x180003008  xor     r8d, r8d; dwMsgType
0x18000300b  mov     [rsp+88h+var_58.pvArg], r15
0x180003010  xor     edx, edx; dwFlags
0x180003012  mov     ecx, 10001h; dwMsgEncodingType
0x180003017  call    cs:__imp_CryptMsgOpenToDecode
0x18000301d  mov     r14, rax
0x180003020  test    rax, rax
0x180003023  jz      short loc_180003061
0x180003025  mov     ebp, r15d
0x180003028  test    ebp, ebp
0x18000302a  jnz     short loc_18000307A
0x18000302c  cmp     edi, 1000h
0x180003032  jbe     short loc_180003058
0x180003034  mov     ebx, 1000h
0x180003039  mov     r9d, ebp; fFinal
0x18000303c  mov     r8d, ebx; cbData
0x18000303f  mov     rdx, rsi; pbData
0x180003042  mov     rcx, r14; hCryptMsg
0x180003045  call    cs:__imp_CryptMsgUpdate
0x18000304b  test    eax, eax
0x18000304d  jz      short loc_180003061
0x18000304f  sub     edi, ebx
0x180003051  mov     eax, ebx
0x180003053  add     rsi, rax
0x180003056  jmp     short loc_180003028
0x180003058  mov     ebx, edi
0x18000305a  mov     ebp, 1
0x18000305f  jmp     short loc_180003039
0x180003061  mov     rcx, r14; hCryptMsg
0x180003064  call    cs:__imp_CryptMsgClose
0x18000306a  mov     rax, r15
0x18000306d  add     rsp, 58h
0x180003071  pop     r15
0x180003073  pop     r14
0x180003075  pop     rdi
0x180003076  pop     rsi
0x180003077  pop     rbp
0x180003078  pop     rbx
0x180003079  retn
0x18000307a  mov     rax, r14
0x18000307d  jmp     short loc_18000306D
```
