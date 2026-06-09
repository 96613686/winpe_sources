# Smb2ComputeValidateNegotiateInfoHash

- ea: `0x1400955d8`
- end: `0x140095791`
- name: `Smb2ComputeValidateNegotiateInfoHash`
- size: `441`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int16, __int64, __int64, ULONG Tag)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14006d87c`
- `0x140090290`

## callees

- `0x1400955d8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14009564b`
- `ntoskrnl!ExAllocatePool2` at `0x14009564b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009575d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009575d`
- `srvnet!SmbCryptoHashCreate` at `0x140095610`
- `srvnet!SmbCryptoHashCreate` at `0x140095610`
- `srvnet!SmbCryptoHashGetOutputLength` at `0x140095632`
- `srvnet!SmbCryptoHashGetOutputLength` at `0x140095632`
- `srvnet!SmbCryptoHashUpdate` at `0x14009567a`
- `srvnet!SmbCryptoHashUpdate` at `0x14009569e`
- `srvnet!SmbCryptoHashUpdate` at `0x1400956c1`
- `srvnet!SmbCryptoHashUpdate` at `0x1400956e1`
- `srvnet!SmbCryptoHashUpdate` at `0x140095703`
- `srvnet!SmbCryptoHashUpdate` at `0x14009567a`
- `srvnet!SmbCryptoHashUpdate` at `0x14009569e`
- `srvnet!SmbCryptoHashUpdate` at `0x1400956c1`
- `srvnet!SmbCryptoHashUpdate` at `0x1400956e1`
- `srvnet!SmbCryptoHashUpdate` at `0x140095703`
- `srvnet!SmbCryptoHashFinish` at `0x14009571f`
- `srvnet!SmbCryptoHashFinish` at `0x14009571f`
- `srvnet!SmbCryptoHashDestroy` at `0x140095742`
- `srvnet!SmbCryptoHashDestroy` at `0x140095742`

## pseudocode

```c
__int64 __fastcall Smb2ComputeValidateNegotiateInfoHash(
        unsigned int a1,
        int a2,
        __int64 a3,
        __int16 a4,
        __int64 a5,
        unsigned __int16 a6,
        _QWORD *a7,
        _DWORD *a8,
        ULONG Tag)
{
  void *Pool2; // rdi
  int v11; // eax
  _DWORD *v12; // r14
  int v13; // ebx
  _QWORD *v14; // r15
  __int64 OutputLength; // rsi
  __int64 v17; // [rsp+20h] [rbp-10h] BYREF
  int v18; // [rsp+68h] [rbp+38h] BYREF
  __int16 v19; // [rsp+78h] [rbp+48h] BYREF

  v19 = a4;
  v18 = a2;
  v17 = 0;
  Pool2 = 0;
  v11 = SmbCryptoHashCreate(&v17, a1, 0);
  v12 = a8;
  v13 = v11;
  v14 = a7;
  if ( v11 >= 0 )
  {
    OutputLength = (unsigned int)SmbCryptoHashGetOutputLength(v17);
    Pool2 = (void *)ExAllocatePool2(258, OutputLength, Tag);
    if ( Pool2 )
    {
      v13 = SmbCryptoHashUpdate(v17, &Smb2SaltBuffer, 32);
      if ( v13 >= 0 )
      {
        v13 = SmbCryptoHashUpdate(v17, &v18, 4);
        if ( v13 >= 0 )
        {
          v13 = SmbCryptoHashUpdate(v17, a3, 16);
          if ( v13 >= 0 )
          {
            v13 = SmbCryptoHashUpdate(v17, &v19, 2);
            if ( v13 >= 0 )
            {
              v13 = SmbCryptoHashUpdate(v17, a5, 2 * (unsigned int)a6);
              if ( v13 >= 0 )
              {
                v13 = SmbCryptoHashFinish(v17, Pool2, (unsigned int)OutputLength);
                if ( v13 >= 0 )
                {
                  *v14 = Pool2;
                  v13 = 0;
                  *v12 = OutputLength;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      v13 = -1073741670;
    }
  }
  if ( v17 )
    SmbCryptoHashDestroy();
  if ( v13 < 0 )
  {
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, Tag);
    *v14 = 0;
    *v12 = 0;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400955d8  mov     rax, rsp
0x1400955db  mov     [rax+8], rbx
0x1400955df  mov     [rax+18h], rsi
0x1400955e3  mov     [rax+20h], r9w
0x1400955e8  mov     [rax+10h], edx
0x1400955eb  push    rbp
0x1400955ec  push    rdi
0x1400955ed  push    r12
0x1400955ef  push    r14
0x1400955f1  push    r15
0x1400955f3  mov     rbp, rsp
0x1400955f6  sub     rsp, 30h
0x1400955fa  mov     r12, r8
0x1400955fd  mov     [rbp+var_10], 0
0x140095605  mov     edx, ecx
0x140095607  xor     r8d, r8d
0x14009560a  lea     rcx, [rbp+var_10]
0x14009560e  xor     edi, edi
0x140095610  call    cs:__imp_SmbCryptoHashCreate
0x140095617  nop     dword ptr [rax+rax+00h]
0x14009561c  mov     r14, [rbp+arg_38]
0x140095620  mov     ebx, eax
0x140095622  mov     r15, [rbp+arg_30]
0x140095626  test    eax, eax
0x140095628  js      loc_140095739
0x14009562e  mov     rcx, [rbp+var_10]
0x140095632  call    cs:__imp_SmbCryptoHashGetOutputLength
0x140095639  nop     dword ptr [rax+rax+00h]
0x14009563e  mov     r8d, [rbp+Tag]
0x140095642  mov     ecx, 102h
0x140095647  mov     edx, eax
0x140095649  mov     esi, eax
0x14009564b  call    cs:__imp_ExAllocatePool2
0x140095652  nop     dword ptr [rax+rax+00h]
0x140095657  mov     rdi, rax
0x14009565a  test    rax, rax
0x14009565d  jnz     short loc_140095669
0x14009565f  mov     ebx, 0C000009Ah
0x140095664  jmp     loc_140095739
0x140095669  mov     rcx, [rbp+var_10]
0x14009566d  lea     rdx, Smb2SaltBuffer
0x140095674  mov     r8d, 20h ; ' '
0x14009567a  call    cs:__imp_SmbCryptoHashUpdate
0x140095681  nop     dword ptr [rax+rax+00h]
0x140095686  mov     ebx, eax
0x140095688  test    eax, eax
0x14009568a  js      loc_140095739
0x140095690  mov     rcx, [rbp+var_10]
0x140095694  lea     rdx, [rbp+arg_8]
0x140095698  mov     r8d, 4
0x14009569e  call    cs:__imp_SmbCryptoHashUpdate
0x1400956a5  nop     dword ptr [rax+rax+00h]
0x1400956aa  mov     ebx, eax
0x1400956ac  test    eax, eax
0x1400956ae  js      loc_140095739
0x1400956b4  mov     rcx, [rbp+var_10]
0x1400956b8  mov     r8d, 10h
0x1400956be  mov     rdx, r12
0x1400956c1  call    cs:__imp_SmbCryptoHashUpdate
0x1400956c8  nop     dword ptr [rax+rax+00h]
0x1400956cd  mov     ebx, eax
0x1400956cf  test    eax, eax
0x1400956d1  js      short loc_140095739
0x1400956d3  mov     rcx, [rbp+var_10]
0x1400956d7  lea     rdx, [rbp+arg_18]
0x1400956db  mov     r8d, 2
0x1400956e1  call    cs:__imp_SmbCryptoHashUpdate
0x1400956e8  nop     dword ptr [rax+rax+00h]
0x1400956ed  mov     ebx, eax
0x1400956ef  test    eax, eax
0x1400956f1  js      short loc_140095739
0x1400956f3  movzx   r8d, [rbp+arg_28]
0x1400956f8  mov     rdx, [rbp+arg_20]
0x1400956fc  add     r8d, r8d
0x1400956ff  mov     rcx, [rbp+var_10]
0x140095703  call    cs:__imp_SmbCryptoHashUpdate
0x14009570a  nop     dword ptr [rax+rax+00h]
0x14009570f  mov     ebx, eax
0x140095711  test    eax, eax
0x140095713  js      short loc_140095739
0x140095715  mov     rcx, [rbp+var_10]
0x140095719  mov     r8d, esi
0x14009571c  mov     rdx, rdi
0x14009571f  call    cs:__imp_SmbCryptoHashFinish
0x140095726  nop     dword ptr [rax+rax+00h]
0x14009572b  mov     ebx, eax
0x14009572d  test    eax, eax
0x14009572f  js      short loc_140095739
0x140095731  mov     [r15], rdi
0x140095734  xor     ebx, ebx
0x140095736  mov     [r14], esi
0x140095739  mov     rcx, [rbp+var_10]
0x14009573d  test    rcx, rcx
0x140095740  jz      short loc_14009574E
0x140095742  call    cs:__imp_SmbCryptoHashDestroy
0x140095749  nop     dword ptr [rax+rax+00h]
0x14009574e  test    ebx, ebx
0x140095750  jns     short loc_140095777
0x140095752  test    rdi, rdi
0x140095755  jz      short loc_140095769
0x140095757  mov     edx, [rbp+Tag]; Tag
0x14009575a  mov     rcx, rdi; P
0x14009575d  call    cs:__imp_ExFreePoolWithTag
0x140095764  nop     dword ptr [rax+rax+00h]
0x140095769  mov     qword ptr [r15], 0
0x140095770  mov     dword ptr [r14], 0
0x140095777  mov     rsi, [rsp+30h+arg_10]
0x14009577c  mov     eax, ebx
0x14009577e  mov     rbx, [rsp+30h+arg_0]
0x140095783  add     rsp, 30h
0x140095787  pop     r15
0x140095789  pop     r14
0x14009578b  pop     r12
0x14009578d  pop     rdi
0x14009578e  pop     rbp
0x14009578f  retn
```
