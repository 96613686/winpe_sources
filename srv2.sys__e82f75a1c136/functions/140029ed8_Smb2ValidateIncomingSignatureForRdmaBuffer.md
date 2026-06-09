# Smb2ValidateIncomingSignatureForRdmaBuffer

- ea: `0x140029ed8`
- end: `0x14002a122`
- name: `Smb2ValidateIncomingSignatureForRdmaBuffer`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14007ea50`

## callees

- `0x14000a9e8`
- `0x14000aab4`
- `0x140022958`
- `0x140029ed8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14002a0b8`
- `ntoskrnl!RtlCompareMemory` at `0x14002a0b8`
- `ksecdd!BCryptDuplicateHash` at `0x140029f3c`
- `ksecdd!BCryptDuplicateHash` at `0x140029f3c`
- `ksecdd!BCryptHashData` at `0x14002a01c`
- `ksecdd!BCryptHashData` at `0x14002a01c`
- `ksecdd!BCryptFinishHash` at `0x14002a058`
- `ksecdd!BCryptFinishHash` at `0x14002a058`
- `ksecdd!BCryptDestroyHash` at `0x14002a0e6`
- `ksecdd!BCryptDestroyHash` at `0x14002a0e6`
- `ksecdd!BCryptSetProperty` at `0x140029fc6`
- `ksecdd!BCryptSetProperty` at `0x140029fc6`

## pseudocode

```c
__int64 __fastcall Smb2ValidateIncomingSignatureForRdmaBuffer(__int64 a1, unsigned __int16 *a2, UCHAR *a3, ULONG a4)
{
  __int64 v4; // rbx
  UCHAR *SigningHashObject; // rax
  UCHAR *v10; // r14
  NTSTATUS v11; // edi
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  ULONG v14; // ecx
  __int64 v15; // rcx
  UCHAR *v16; // rbp
  SIZE_T v17; // rbx
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+60h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 560);
  phNewHash = 0;
  SigningHashObject = (UCHAR *)Smb2AllocateSigningHashObject(*(unsigned int *)(v4 + 120));
  v10 = SigningHashObject;
  if ( !SigningHashObject )
  {
    v11 = -1073741670;
    goto LABEL_27;
  }
  v11 = BCryptDuplicateHash(*(BCRYPT_HASH_HANDLE *)(v4 + 112), &phNewHash, SigningHashObject, *(_DWORD *)(v4 + 120), 0);
  if ( v11 >= 0 )
  {
    v14 = a2[2];
    if ( (_WORD)v14 && (v11 = BCryptSetProperty(phNewHash, L"IV", (PUCHAR)a2 + a2[1] + 8, v14, 0), v11 < 0) )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v13 = 27;
        goto LABEL_8;
      }
    }
    else
    {
      v11 = BCryptHashData(phNewHash, a3, a4, 0);
      if ( v11 >= 0 )
      {
        v15 = a2[1];
        if ( (unsigned int)v15 > MaxHashObjectLength )
          __int2c();
        v16 = (UCHAR *)Smb2AllocateSigningHashObject(v15);
        v11 = BCryptFinishHash(phNewHash, v16, a2[1], 0);
        if ( v11 >= 0 )
        {
          v17 = a2[1];
          if ( v17 != RtlCompareMemory(a2 + 4, v16, v17) )
            v11 = -1073700864;
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids, a1, v11);
        }
        if ( v16 )
          Smb2DeallocateSigningHashObject(v16);
      }
    }
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v13 = 26;
LABEL_8:
      WPP_SF_qD(v12->AttachedDevice, v13, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids, a1, v11);
    }
  }
LABEL_27:
  if ( phNewHash )
  {
    BCryptDestroyHash(phNewHash);
    phNewHash = 0;
  }
  if ( v10 )
    Smb2DeallocateSigningHashObject(v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140029ed8  mov     [rsp+arg_8], rbx
0x140029edd  mov     [rsp+arg_10], rbp
0x140029ee2  push    rsi
0x140029ee3  push    rdi
0x140029ee4  push    r12
0x140029ee6  push    r14
0x140029ee8  push    r15
0x140029eea  sub     rsp, 30h
0x140029eee  mov     rbx, [rcx+230h]
0x140029ef5  mov     r15, rcx
0x140029ef8  mov     [rsp+58h+phNewHash], 0
0x140029f01  mov     ebp, r9d
0x140029f04  mov     r12, r8
0x140029f07  mov     rsi, rdx
0x140029f0a  mov     ecx, [rbx+78h]
0x140029f0d  call    Smb2AllocateSigningHashObject
0x140029f12  mov     r14, rax
0x140029f15  test    rax, rax
0x140029f18  jnz     short loc_140029F24
0x140029f1a  mov     edi, 0C000009Ah
0x140029f1f  jmp     loc_14002A0DC
0x140029f24  mov     r9d, [rbx+78h]; cbHashObject
0x140029f28  lea     rdx, [rsp+58h+phNewHash]; phNewHash
0x140029f2d  mov     rcx, [rbx+70h]; hHash
0x140029f31  mov     r8, r14; pbHashObject
0x140029f34  mov     [rsp+58h+dwFlags], 0; dwFlags
0x140029f3c  call    cs:__imp_BCryptDuplicateHash
0x140029f43  nop     dword ptr [rax+rax+00h]
0x140029f48  mov     edi, eax
0x140029f4a  test    eax, eax
0x140029f4c  jns     short loc_140029F9C
0x140029f4e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029f55  lea     rax, WPP_GLOBAL_Control
0x140029f5c  cmp     rcx, rax
0x140029f5f  jz      loc_14002A0DC
0x140029f65  mov     edx, [rcx+2Ch]
0x140029f68  test    dl, 1
0x140029f6b  jz      loc_14002A0DC
0x140029f71  cmp     byte ptr [rcx+29h], 1
0x140029f75  jb      loc_14002A0DC
0x140029f7b  mov     edx, 1Ah
0x140029f80  mov     rcx, [rcx+18h]
0x140029f84  lea     r8, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids
0x140029f8b  mov     r9, r15
0x140029f8e  mov     [rsp+58h+dwFlags], edi
0x140029f92  call    WPP_SF_qD
0x140029f97  jmp     loc_14002A0DC
0x140029f9c  movzx   ecx, word ptr [rsi+4]
0x140029fa0  xor     eax, eax
0x140029fa2  cmp     ax, cx
0x140029fa5  jnb     short loc_14002A00E
0x140029fa7  movzx   r8d, word ptr [rsi+2]
0x140029fac  lea     rdx, pszProperty; "IV"
0x140029fb3  add     r8, 8
0x140029fb7  mov     [rsp+58h+dwFlags], eax; dwFlags
0x140029fbb  mov     r9d, ecx; cbInput
0x140029fbe  add     r8, rsi; pbInput
0x140029fc1  mov     rcx, [rsp+58h+phNewHash]; hObject
0x140029fc6  call    cs:__imp_BCryptSetProperty
0x140029fcd  nop     dword ptr [rax+rax+00h]
0x140029fd2  mov     edi, eax
0x140029fd4  test    eax, eax
0x140029fd6  jns     short loc_14002A00E
0x140029fd8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029fdf  lea     rax, WPP_GLOBAL_Control
0x140029fe6  cmp     rcx, rax
0x140029fe9  jz      loc_14002A0DC
0x140029fef  mov     eax, [rcx+2Ch]
0x140029ff2  test    al, 1
0x140029ff4  jz      loc_14002A0DC
0x140029ffa  cmp     byte ptr [rcx+29h], 1
0x140029ffe  jb      loc_14002A0DC
0x14002a004  mov     edx, 1Bh
0x14002a009  jmp     loc_140029F80
0x14002a00e  mov     rcx, [rsp+58h+phNewHash]; hHash
0x14002a013  xor     r9d, r9d; dwFlags
0x14002a016  mov     r8d, ebp; cbInput
0x14002a019  mov     rdx, r12; pbInput
0x14002a01c  call    cs:__imp_BCryptHashData
0x14002a023  nop     dword ptr [rax+rax+00h]
0x14002a028  mov     edi, eax
0x14002a02a  test    eax, eax
0x14002a02c  js      loc_14002A0DC
0x14002a032  movzx   ecx, word ptr [rsi+2]
0x14002a036  cmp     ecx, cs:MaxHashObjectLength
0x14002a03c  jbe     short loc_14002A040
0x14002a03e  int     2Ch; Windows NT - assertion failure
0x14002a040  call    Smb2AllocateSigningHashObject
0x14002a045  movzx   r8d, word ptr [rsi+2]; cbOutput
0x14002a04a  xor     r9d, r9d; dwFlags
0x14002a04d  mov     rcx, [rsp+58h+phNewHash]; hHash
0x14002a052  mov     rdx, rax; pbOutput
0x14002a055  mov     rbp, rax
0x14002a058  call    cs:__imp_BCryptFinishHash
0x14002a05f  nop     dword ptr [rax+rax+00h]
0x14002a064  mov     edi, eax
0x14002a066  test    eax, eax
0x14002a068  jns     short loc_14002A0A8
0x14002a06a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a071  lea     rax, WPP_GLOBAL_Control
0x14002a078  cmp     rcx, rax
0x14002a07b  jz      short loc_14002A0CF
0x14002a07d  mov     eax, [rcx+2Ch]
0x14002a080  test    al, 1
0x14002a082  jz      short loc_14002A0CF
0x14002a084  cmp     byte ptr [rcx+29h], 1
0x14002a088  jb      short loc_14002A0CF
0x14002a08a  mov     rcx, [rcx+18h]
0x14002a08e  lea     r8, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids
0x14002a095  mov     edx, 1Ch
0x14002a09a  mov     [rsp+58h+dwFlags], edi
0x14002a09e  mov     r9, r15
0x14002a0a1  call    WPP_SF_qD
0x14002a0a6  jmp     short loc_14002A0CF
0x14002a0a8  movzx   r8d, word ptr [rsi+2]; Length
0x14002a0ad  lea     rcx, [rsi+8]; Source1
0x14002a0b1  movzx   ebx, word ptr [rsi+2]
0x14002a0b5  mov     rdx, rbp; Source2
0x14002a0b8  call    cs:__imp_RtlCompareMemory
0x14002a0bf  nop     dword ptr [rax+rax+00h]
0x14002a0c4  cmp     rbx, rax
0x14002a0c7  mov     ecx, 0C000A000h
0x14002a0cc  cmovnz  edi, ecx
0x14002a0cf  test    rbp, rbp
0x14002a0d2  jz      short loc_14002A0DC
0x14002a0d4  mov     rcx, rbp
0x14002a0d7  call    Smb2DeallocateSigningHashObject
0x14002a0dc  mov     rcx, [rsp+58h+phNewHash]; hHash
0x14002a0e1  test    rcx, rcx
0x14002a0e4  jz      short loc_14002A0FB
0x14002a0e6  call    cs:__imp_BCryptDestroyHash
0x14002a0ed  nop     dword ptr [rax+rax+00h]
0x14002a0f2  mov     [rsp+58h+phNewHash], 0
0x14002a0fb  test    r14, r14
0x14002a0fe  jz      short loc_14002A108
0x14002a100  mov     rcx, r14
0x14002a103  call    Smb2DeallocateSigningHashObject
0x14002a108  mov     rbx, [rsp+58h+arg_8]
0x14002a10d  mov     eax, edi
0x14002a10f  mov     rbp, [rsp+58h+arg_10]
0x14002a114  add     rsp, 30h
0x14002a118  pop     r15
0x14002a11a  pop     r14
0x14002a11c  pop     r12
0x14002a11e  pop     rdi
0x14002a11f  pop     rsi
0x14002a120  retn
```
