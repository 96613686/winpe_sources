# Smb2AdmRegisterSession

- ea: `0x140065980`
- end: `0x140065bfb`
- name: `Smb2AdmRegisterSession`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140092240`

## callees

- `0x14001a150`
- `0x140029170`
- `0x140065980`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140065a38`
- `ntoskrnl!RtlInitUnicodeString` at `0x140065a38`
- `srvnet!SrvAdminRegisterSession` at `0x140065b67`
- `srvnet!SrvAdminRegisterSession` at `0x140065b67`
- `ksecdd!FreeContextBuffer` at `0x140065bd8`
- `ksecdd!FreeContextBuffer` at `0x140065bd8`
- `ksecdd!MapSecurityError` at `0x140065a07`
- `ksecdd!MapSecurityError` at `0x140065a07`
- `ksecdd!QueryContextAttributesW` at `0x1400659f9`
- `ksecdd!QueryContextAttributesW` at `0x1400659f9`

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
0x140065980  push    rbp
0x140065982  push    rbx
0x140065983  push    rsi
0x140065984  push    rdi
0x140065985  push    r12
0x140065987  push    r13
0x140065989  push    r14
0x14006598b  push    r15
0x14006598d  lea     rbp, [rsp-1Fh]
0x140065992  sub     rsp, 0B8h
0x140065999  mov     rax, [rdx+20h]
0x14006599d  xor     r12d, r12d
0x1400659a0  mov     qword ptr [rbp+57h+DestinationString.Length], r12
0x1400659a4  mov     r15, rcx
0x1400659a7  mov     [rbp+57h+DestinationString.Buffer], r12
0x1400659ab  mov     ecx, r12d; pvContextBuffer
0x1400659ae  mov     [rbp+57h+pBuffer], rcx
0x1400659b2  mov     rsi, r8
0x1400659b5  mov     [rbp+57h+var_70], r12
0x1400659b9  mov     rdi, rdx
0x1400659bc  mov     [rbp+57h+var_68], r12
0x1400659c0  mov     [rbp+57h+var_60], r12
0x1400659c4  mov     [rbp+57h+var_58], r12
0x1400659c8  test    rax, rax
0x1400659cb  jz      loc_140065BCE
0x1400659d1  cmp     [rax+20h], r12
0x1400659d5  jnz     short loc_1400659E1
0x1400659d7  cmp     [rax+28h], r12
0x1400659db  jz      loc_140065BCE
0x1400659e1  mov     r14, [r8+1F0h]
0x1400659e8  lea     rcx, [rax+20h]; phContext
0x1400659ec  mov     r13d, 1
0x1400659f2  lea     r8, [rbp+57h+pBuffer]; pBuffer
0x1400659f6  mov     edx, r13d; ulAttribute
0x1400659f9  call    cs:__imp_QueryContextAttributesW
0x140065a00  nop     dword ptr [rax+rax+00h]
0x140065a05  mov     ecx, eax; SecStatus
0x140065a07  call    cs:__imp_MapSecurityError
0x140065a0e  nop     dword ptr [rax+rax+00h]
0x140065a13  mov     ebx, eax
0x140065a15  test    eax, eax
0x140065a17  js      loc_140065BC8
0x140065a1d  mov     rdx, [rbp+57h+pBuffer]; SourceString
0x140065a21  lea     ebx, [r13+1]
0x140065a25  test    rdx, rdx
0x140065a28  jz      loc_140065AB1
0x140065a2e  cmp     [rdx], r12w
0x140065a32  jz      short loc_140065AB1
0x140065a34  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140065a38  call    cs:__imp_RtlInitUnicodeString
0x140065a3f  nop     dword ptr [rax+rax+00h]
0x140065a44  movzx   edx, [rbp+57h+DestinationString.Length]
0x140065a48  mov     ecx, r12d
0x140065a4b  mov     r8, [rbp+57h+DestinationString.Buffer]
0x140065a4f  movzx   r9d, dx
0x140065a53  shr     r9w, 1
0x140065a57  mov     [rbp+57h+var_58], r8
0x140065a5b  cmp     r12w, r9w
0x140065a5f  jnb     short loc_140065A76
0x140065a61  movzx   eax, cx
0x140065a64  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140065a6a  jz      short loc_140065A76
0x140065a6c  add     cx, r13w
0x140065a70  cmp     cx, r9w
0x140065a74  jb      short loc_140065A61
0x140065a76  movzx   eax, cx
0x140065a79  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140065a7f  jnz     short loc_140065AA7
0x140065a81  add     cx, cx
0x140065a84  inc     rax
0x140065a87  sub     dx, cx
0x140065a8a  mov     word ptr [rbp+57h+var_60], cx
0x140065a8e  mov     word ptr [rbp+57h+var_60+2], cx
0x140065a92  sub     dx, bx
0x140065a95  lea     rax, [r8+rax*2]
0x140065a99  mov     [rbp+57h+var_68], rax
0x140065a9d  mov     word ptr [rbp+57h+var_70], dx
0x140065aa1  mov     word ptr [rbp+57h+var_70+2], dx
0x140065aa5  jmp     short loc_140065ABB
0x140065aa7  mov     dword ptr [rbp+57h+var_60], r12d
0x140065aab  mov     [rbp+57h+var_68], r8
0x140065aaf  jmp     short loc_140065A9D
0x140065ab1  mov     word ptr [rbp+57h+var_70], r12w
0x140065ab6  mov     word ptr [rbp+57h+var_60], r12w
0x140065abb  xor     edx, edx
0x140065abd  mov     rcx, rsi
0x140065ac0  call    Srv2QuerySocketAddress
0x140065ac5  cmp     [rdi+110h], r12b
0x140065acc  lea     r10, [rdi+40h]
0x140065ad0  mov     rax, [rdi+138h]
0x140065ad7  lea     r8, [rsi+0D8h]
0x140065ade  mov     [rsp+0F0h+var_80], r10
0x140065ae3  mov     ecx, r12d
0x140065ae6  setnz   cl
0x140065ae9  mov     r11d, ecx
0x140065aec  movzx   edx, byte ptr [rax]
0x140065aef  or      r11d, ebx
0x140065af2  cmp     [rdi+111h], r12b
0x140065af9  lea     rbx, [rdi+10h]
0x140065afd  movzx   eax, word ptr [r14+2Ch]
0x140065b02  mov     [rsp+0F0h+var_88], edx
0x140065b06  cmovz   r11d, ecx
0x140065b0a  mov     [rsp+0F0h+var_90], r8
0x140065b0f  lea     rcx, [rsi+168h]
0x140065b16  mov     [rsp+0F0h+var_98], ax
0x140065b1b  lea     r8, [rbp+57h+var_60]
0x140065b1f  mov     rax, [rdi]
0x140065b22  lea     rdx, [rbp+57h+var_70]
0x140065b26  mov     r9d, r11d
0x140065b29  or      r9d, 4
0x140065b2d  cmp     [rdi+11Dh], r12b
0x140065b34  cmovz   r9d, r11d
0x140065b38  lea     r11, [rdi+70h]
0x140065b3c  mov     [rsp+0F0h+var_A0], r9d
0x140065b41  xor     r9d, r9d
0x140065b44  mov     [rsp+0F0h+var_A8], rax
0x140065b49  mov     eax, cs:Smb2ProviderId
0x140065b4f  mov     dword ptr [rsp+0F0h+var_B0], eax
0x140065b53  mov     [rsp+0F0h+var_B8], r12d
0x140065b58  mov     [rsp+0F0h+var_C0], r11
0x140065b5d  mov     [rsp+0F0h+var_C8], rbx
0x140065b62  mov     [rsp+0F0h+var_D0], r12
0x140065b67  call    cs:__imp_SrvAdminRegisterSession
0x140065b6e  nop     dword ptr [rax+rax+00h]
0x140065b73  mov     ebx, eax
0x140065b75  test    eax, eax
0x140065b77  js      short loc_140065BC8
0x140065b79  test    cs:Microsoft_Windows_SMBServerEnableBits, 40h
0x140065b80  jz      short loc_140065BC8
0x140065b82  mov     rax, [rbp+57h+var_58]
0x140065b86  lea     rdx, [r14+48h]
0x140065b8a  movzx   ecx, word ptr [rbp+57h+var_60]
0x140065b8e  lea     r9, [rdi+48h]
0x140065b92  movzx   r10d, word ptr [rbp+57h+var_70]
0x140065b97  lea     r8, [r15+248h]
0x140065b9e  mov     [rsp+0F0h+var_B0], rax
0x140065ba3  mov     rax, [rbp+57h+var_68]
0x140065ba7  shr     cx, 1
0x140065baa  mov     word ptr [rsp+0F0h+var_B8], cx
0x140065baf  mov     [rsp+0F0h+var_C0], rax
0x140065bb4  shr     r10w, 1
0x140065bb8  mov     word ptr [rsp+0F0h+var_C8], r10w
0x140065bbe  mov     [rsp+0F0h+var_D0], rdx
0x140065bc3  call    McTemplateK0jjhzr2hzr4_EtwWriteTransfer
0x140065bc8  mov     rcx, [rbp+57h+pBuffer]
0x140065bcc  jmp     short loc_140065BD3
0x140065bce  mov     ebx, 0C0000008h
0x140065bd3  test    rcx, rcx
0x140065bd6  jz      short loc_140065BE4
0x140065bd8  call    cs:__imp_FreeContextBuffer
0x140065bdf  nop     dword ptr [rax+rax+00h]
0x140065be4  mov     eax, ebx
0x140065be6  add     rsp, 0B8h
0x140065bed  pop     r15
0x140065bef  pop     r14
0x140065bf1  pop     r13
0x140065bf3  pop     r12
0x140065bf5  pop     rdi
0x140065bf6  pop     rsi
0x140065bf7  pop     rbx
0x140065bf8  pop     rbp
0x140065bf9  retn
```
