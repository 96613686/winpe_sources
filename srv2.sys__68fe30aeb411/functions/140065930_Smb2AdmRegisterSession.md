# Smb2AdmRegisterSession

- ea: `0x140065930`
- end: `0x140065bab`
- name: `Smb2AdmRegisterSession`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400921f0`

## callees

- `0x14001a150`
- `0x140029170`
- `0x140065930`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400659e8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400659e8`
- `srvnet!SrvAdminRegisterSession` at `0x140065b17`
- `srvnet!SrvAdminRegisterSession` at `0x140065b17`
- `ksecdd!FreeContextBuffer` at `0x140065b88`
- `ksecdd!FreeContextBuffer` at `0x140065b88`
- `ksecdd!MapSecurityError` at `0x1400659b7`
- `ksecdd!MapSecurityError` at `0x1400659b7`
- `ksecdd!QueryContextAttributesW` at `0x1400659a9`
- `ksecdd!QueryContextAttributesW` at `0x1400659a9`

## pseudocode

```c
__int64 __fastcall Smb2AdmRegisterSession(int a1, __int64 a2, __int64 a3)
{
  struct _SecHandle *v3; // rax
  WCHAR *v5; // rcx
  __int64 v8; // r14
  SECURITY_STATUS v9; // eax
  NTSTATUS v10; // ebx
  USHORT Length; // dx
  unsigned __int16 v12; // cx
  int v13; // r11d
  int v14; // r9d
  __int16 v16; // [rsp+58h] [rbp-41h]
  __int64 v17; // [rsp+80h] [rbp-19h] BYREF
  PWSTR v18; // [rsp+88h] [rbp-11h]
  __int64 v19; // [rsp+90h] [rbp-9h] BYREF
  PWSTR Buffer; // [rsp+98h] [rbp-1h]
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp+7h] BYREF
  WCHAR *pBuffer; // [rsp+108h] [rbp+6Fh] BYREF

  v3 = *(struct _SecHandle **)(a2 + 32);
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v5 = 0;
  pBuffer = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  Buffer = 0;
  if ( v3 && (v3[2].dwLower || v3[2].dwUpper) )
  {
    v8 = *(_QWORD *)(a3 + 496);
    v9 = QueryContextAttributesW(v3 + 2, 1u, &pBuffer);
    v10 = MapSecurityError(v9);
    if ( v10 >= 0 )
    {
      if ( pBuffer && *pBuffer )
      {
        RtlInitUnicodeString(&DestinationString, pBuffer);
        Length = DestinationString.Length;
        v12 = 0;
        Buffer = DestinationString.Buffer;
        if ( DestinationString.Length >> 1 )
        {
          do
          {
            if ( DestinationString.Buffer[v12] == 92 )
              break;
            ++v12;
          }
          while ( v12 < (unsigned __int16)(DestinationString.Length >> 1) );
        }
        if ( DestinationString.Buffer[v12] == 92 )
        {
          LOWORD(v19) = 2 * v12;
          WORD1(v19) = 2 * v12;
          Length = DestinationString.Length - 2 * v12 - 2;
          v18 = &DestinationString.Buffer[v12 + 1];
        }
        else
        {
          LODWORD(v19) = 0;
          v18 = DestinationString.Buffer;
        }
        LOWORD(v17) = Length;
        WORD1(v17) = Length;
      }
      else
      {
        LOWORD(v17) = 0;
        LOWORD(v19) = 0;
      }
      Srv2QuerySocketAddress(a3, 0);
      v13 = (*(_BYTE *)(a2 + 272) != 0) | 2;
      if ( !*(_BYTE *)(a2 + 273) )
        v13 = *(_BYTE *)(a2 + 272) != 0;
      v14 = v13 | 4;
      if ( !*(_BYTE *)(a2 + 285) )
        v14 = v13;
      v16 = *(_WORD *)(v8 + 44);
      v10 = SrvAdminRegisterSession(
              a3 + 360,
              &v17,
              &v19,
              0,
              0,
              a2 + 16,
              a2 + 112,
              0,
              Smb2ProviderId,
              *(_QWORD *)a2,
              v14,
              v16,
              a3 + 216,
              **(unsigned __int8 **)(a2 + 312),
              a2 + 64);
      if ( v10 >= 0 && (Microsoft_Windows_SMBServerEnableBits & 0x40) != 0 )
        McTemplateK0jjhzr2hzr4_EtwWriteTransfer(
          (unsigned __int16)v19 >> 1,
          v8 + 72,
          a1 + 584,
          a2 + 72,
          v8 + 72,
          (unsigned __int16)v17 >> 1,
          (__int64)v18,
          (unsigned __int16)v19 >> 1,
          (__int64)Buffer);
    }
    v5 = pBuffer;
  }
  else
  {
    v10 = -1073741816;
  }
  if ( v5 )
    FreeContextBuffer(v5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140065930  push    rbp
0x140065932  push    rbx
0x140065933  push    rsi
0x140065934  push    rdi
0x140065935  push    r12
0x140065937  push    r13
0x140065939  push    r14
0x14006593b  push    r15
0x14006593d  lea     rbp, [rsp-1Fh]
0x140065942  sub     rsp, 0B8h
0x140065949  mov     rax, [rdx+20h]
0x14006594d  xor     r12d, r12d
0x140065950  mov     qword ptr [rbp+57h+DestinationString.Length], r12
0x140065954  mov     r15, rcx
0x140065957  mov     [rbp+57h+DestinationString.Buffer], r12
0x14006595b  mov     ecx, r12d; pvContextBuffer
0x14006595e  mov     [rbp+57h+pBuffer], rcx
0x140065962  mov     rsi, r8
0x140065965  mov     [rbp+57h+var_70], r12
0x140065969  mov     rdi, rdx
0x14006596c  mov     [rbp+57h+var_68], r12
0x140065970  mov     [rbp+57h+var_60], r12
0x140065974  mov     [rbp+57h+var_58], r12
0x140065978  test    rax, rax
0x14006597b  jz      loc_140065B7E
0x140065981  cmp     [rax+20h], r12
0x140065985  jnz     short loc_140065991
0x140065987  cmp     [rax+28h], r12
0x14006598b  jz      loc_140065B7E
0x140065991  mov     r14, [r8+1F0h]
0x140065998  lea     rcx, [rax+20h]; phContext
0x14006599c  mov     r13d, 1
0x1400659a2  lea     r8, [rbp+57h+pBuffer]; pBuffer
0x1400659a6  mov     edx, r13d; ulAttribute
0x1400659a9  call    cs:__imp_QueryContextAttributesW
0x1400659b0  nop     dword ptr [rax+rax+00h]
0x1400659b5  mov     ecx, eax; SecStatus
0x1400659b7  call    cs:__imp_MapSecurityError
0x1400659be  nop     dword ptr [rax+rax+00h]
0x1400659c3  mov     ebx, eax
0x1400659c5  test    eax, eax
0x1400659c7  js      loc_140065B78
0x1400659cd  mov     rdx, [rbp+57h+pBuffer]; SourceString
0x1400659d1  lea     ebx, [r13+1]
0x1400659d5  test    rdx, rdx
0x1400659d8  jz      loc_140065A61
0x1400659de  cmp     [rdx], r12w
0x1400659e2  jz      short loc_140065A61
0x1400659e4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400659e8  call    cs:__imp_RtlInitUnicodeString
0x1400659ef  nop     dword ptr [rax+rax+00h]
0x1400659f4  movzx   edx, [rbp+57h+DestinationString.Length]
0x1400659f8  mov     ecx, r12d
0x1400659fb  mov     r8, [rbp+57h+DestinationString.Buffer]
0x1400659ff  movzx   r9d, dx
0x140065a03  shr     r9w, 1
0x140065a07  mov     [rbp+57h+var_58], r8
0x140065a0b  cmp     r12w, r9w
0x140065a0f  jnb     short loc_140065A26
0x140065a11  movzx   eax, cx
0x140065a14  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140065a1a  jz      short loc_140065A26
0x140065a1c  add     cx, r13w
0x140065a20  cmp     cx, r9w
0x140065a24  jb      short loc_140065A11
0x140065a26  movzx   eax, cx
0x140065a29  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140065a2f  jnz     short loc_140065A57
0x140065a31  add     cx, cx
0x140065a34  inc     rax
0x140065a37  sub     dx, cx
0x140065a3a  mov     word ptr [rbp+57h+var_60], cx
0x140065a3e  mov     word ptr [rbp+57h+var_60+2], cx
0x140065a42  sub     dx, bx
0x140065a45  lea     rax, [r8+rax*2]
0x140065a49  mov     [rbp+57h+var_68], rax
0x140065a4d  mov     word ptr [rbp+57h+var_70], dx
0x140065a51  mov     word ptr [rbp+57h+var_70+2], dx
0x140065a55  jmp     short loc_140065A6B
0x140065a57  mov     dword ptr [rbp+57h+var_60], r12d
0x140065a5b  mov     [rbp+57h+var_68], r8
0x140065a5f  jmp     short loc_140065A4D
0x140065a61  mov     word ptr [rbp+57h+var_70], r12w
0x140065a66  mov     word ptr [rbp+57h+var_60], r12w
0x140065a6b  xor     edx, edx
0x140065a6d  mov     rcx, rsi
0x140065a70  call    Srv2QuerySocketAddress
0x140065a75  cmp     [rdi+110h], r12b
0x140065a7c  lea     r10, [rdi+40h]
0x140065a80  mov     rax, [rdi+138h]
0x140065a87  lea     r8, [rsi+0D8h]
0x140065a8e  mov     [rsp+0F0h+var_80], r10
0x140065a93  mov     ecx, r12d
0x140065a96  setnz   cl
0x140065a99  mov     r11d, ecx
0x140065a9c  movzx   edx, byte ptr [rax]
0x140065a9f  or      r11d, ebx
0x140065aa2  cmp     [rdi+111h], r12b
0x140065aa9  lea     rbx, [rdi+10h]
0x140065aad  movzx   eax, word ptr [r14+2Ch]
0x140065ab2  mov     [rsp+0F0h+var_88], edx
0x140065ab6  cmovz   r11d, ecx
0x140065aba  mov     [rsp+0F0h+var_90], r8
0x140065abf  lea     rcx, [rsi+168h]
0x140065ac6  mov     [rsp+0F0h+var_98], ax
0x140065acb  lea     r8, [rbp+57h+var_60]
0x140065acf  mov     rax, [rdi]
0x140065ad2  lea     rdx, [rbp+57h+var_70]
0x140065ad6  mov     r9d, r11d
0x140065ad9  or      r9d, 4
0x140065add  cmp     [rdi+11Dh], r12b
0x140065ae4  cmovz   r9d, r11d
0x140065ae8  lea     r11, [rdi+70h]
0x140065aec  mov     [rsp+0F0h+var_A0], r9d
0x140065af1  xor     r9d, r9d
0x140065af4  mov     [rsp+0F0h+var_A8], rax
0x140065af9  mov     eax, cs:Smb2ProviderId
0x140065aff  mov     dword ptr [rsp+0F0h+var_B0], eax
0x140065b03  mov     [rsp+0F0h+var_B8], r12d
0x140065b08  mov     [rsp+0F0h+var_C0], r11
0x140065b0d  mov     [rsp+0F0h+var_C8], rbx
0x140065b12  mov     [rsp+0F0h+var_D0], r12
0x140065b17  call    cs:__imp_SrvAdminRegisterSession
0x140065b1e  nop     dword ptr [rax+rax+00h]
0x140065b23  mov     ebx, eax
0x140065b25  test    eax, eax
0x140065b27  js      short loc_140065B78
0x140065b29  test    cs:Microsoft_Windows_SMBServerEnableBits, 40h
0x140065b30  jz      short loc_140065B78
0x140065b32  mov     rax, [rbp+57h+var_58]
0x140065b36  lea     rdx, [r14+48h]
0x140065b3a  movzx   ecx, word ptr [rbp+57h+var_60]
0x140065b3e  lea     r9, [rdi+48h]
0x140065b42  movzx   r10d, word ptr [rbp+57h+var_70]
0x140065b47  lea     r8, [r15+248h]
0x140065b4e  mov     [rsp+0F0h+var_B0], rax
0x140065b53  mov     rax, [rbp+57h+var_68]
0x140065b57  shr     cx, 1
0x140065b5a  mov     word ptr [rsp+0F0h+var_B8], cx
0x140065b5f  mov     [rsp+0F0h+var_C0], rax
0x140065b64  shr     r10w, 1
0x140065b68  mov     word ptr [rsp+0F0h+var_C8], r10w
0x140065b6e  mov     [rsp+0F0h+var_D0], rdx
0x140065b73  call    McTemplateK0jjhzr2hzr4_EtwWriteTransfer
0x140065b78  mov     rcx, [rbp+57h+pBuffer]
0x140065b7c  jmp     short loc_140065B83
0x140065b7e  mov     ebx, 0C0000008h
0x140065b83  test    rcx, rcx
0x140065b86  jz      short loc_140065B94
0x140065b88  call    cs:__imp_FreeContextBuffer
0x140065b8f  nop     dword ptr [rax+rax+00h]
0x140065b94  mov     eax, ebx
0x140065b96  add     rsp, 0B8h
0x140065b9d  pop     r15
0x140065b9f  pop     r14
0x140065ba1  pop     r13
0x140065ba3  pop     r12
0x140065ba5  pop     rdi
0x140065ba6  pop     rsi
0x140065ba7  pop     rbx
0x140065ba8  pop     rbp
0x140065ba9  retn
```
