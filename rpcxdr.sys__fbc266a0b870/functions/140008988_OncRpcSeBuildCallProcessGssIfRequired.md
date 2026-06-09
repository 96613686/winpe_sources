# OncRpcSeBuildCallProcessGssIfRequired

- ea: `0x140008988`
- end: `0x140008d6f`
- name: `OncRpcSeBuildCallProcessGssIfRequired`
- size: `999`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140002288`

## callees

- `0x140001020`
- `0x1400020c0`
- `0x140005bac`
- `0x140005c28`
- `0x140008988`
- `0x14000b498`
- `0x14000d1d0`
- `0x140015640`

## import_xrefs

- `ksecdd!FreeContextBuffer` at `0x140008bca`
- `ksecdd!FreeContextBuffer` at `0x140008c5e`
- `ksecdd!FreeContextBuffer` at `0x140008bca`
- `ksecdd!FreeContextBuffer` at `0x140008c5e`
- `ksecdd!QueryContextAttributesW` at `0x140008b2a`
- `ksecdd!QueryContextAttributesW` at `0x140008b2a`
- `ksecdd!MapSecurityError` at `0x140008b38`
- `ksecdd!MapSecurityError` at `0x140008b38`

## pseudocode

```c
__int64 __fastcall OncRpcSeBuildCallProcessGssIfRequired(__int64 a1)
{
  int v1; // esi
  __int64 v3; // rdi
  int v4; // eax
  bool v5; // zf
  int v6; // eax
  unsigned int v7; // r15d
  __int64 v8; // rax
  _DWORD *v9; // rcx
  SECURITY_STATUS v10; // eax
  int v11; // edx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v21; // [rsp+38h] [rbp-51h]
  __int64 v22; // [rsp+40h] [rbp-49h]
  unsigned int v23; // [rsp+48h] [rbp-41h]
  unsigned int v24; // [rsp+70h] [rbp-19h] BYREF
  int v25; // [rsp+74h] [rbp-15h] BYREF
  unsigned int v26; // [rsp+78h] [rbp-11h] BYREF
  PVOID pvContextBuffer; // [rsp+80h] [rbp-9h] BYREF
  SECURITY_INTEGER v28; // [rsp+88h] [rbp-1h] BYREF
  __int128 pBuffer; // [rsp+90h] [rbp+7h] BYREF

  v1 = 0;
  if ( *(_DWORD *)(a1 + 296) != 6 )
    goto LABEL_47;
  v3 = *(_QWORD *)(a1 + 1008);
  if ( !v3 )
    goto LABEL_47;
  v4 = *(_DWORD *)(v3 + 64);
  switch ( v4 )
  {
    case 0:
      v5 = *(_DWORD *)(v3 + 120) == 3;
      *(_QWORD *)&pBuffer = a1 + 32;
      v6 = 1073807362;
      v28.QuadPart = 0;
      if ( !v5 )
        v6 = 65538;
      pvContextBuffer = 0;
      v26 = 0;
      v24 = 0;
      v25 = 0;
      if ( byte_14001AA22 )
        v6 |= 0x400u;
      v1 = OncRpcSepInitializeSecurityContextComplex(
             (struct _SecHandle *)(v3 + 80),
             (__int64)&v24,
             (struct _SecHandle *)(v3 + 96),
             (UNICODE_STRING *)(v3 + 192),
             v6,
             &v24,
             &v25,
             v21,
             v22,
             v23,
             &pvContextBuffer,
             &v26,
             &v28);
      if ( v1 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            66,
            WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
            (unsigned int)v1);
        }
        break;
      }
      if ( v24 && v24 != 590610 )
        break;
      v7 = v26;
      v25 = 1;
      v1 = OncRpcBufMgrAllocate((__int64 *)&pBuffer, v26 + 4, 4);
      if ( v1 >= 0 )
      {
        v8 = *(_QWORD *)(a1 + 72);
        if ( v8 )
          v9 = *(_DWORD **)(v8 + 64);
        else
          v9 = 0;
        *v9 = _byteswap_ulong(v7);
        *(_QWORD *)(*(_QWORD *)(a1 + 72) + 64LL) += 4LL;
        XdrEncodeOpaqueUnsafe(a1, v7);
        if ( !v24 )
        {
          pBuffer = 0;
          v10 = QueryContextAttributesW((PCtxtHandle)(v3 + 96), 0, &pBuffer);
          v1 = MapSecurityError(v10);
          if ( v1 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                67,
                WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
                (unsigned int)v1);
            }
            goto LABEL_27;
          }
          *(_DWORD *)(v3 + 208) = HIDWORD(pBuffer);
          *(_DWORD *)(v3 + 212) = DWORD2(pBuffer);
          *(_QWORD *)(v3 + 216) = pBuffer;
          goto LABEL_26;
        }
        if ( v24 == 590610 )
        {
          *(_BYTE *)(*(_QWORD *)(a1 + 1008) + 56LL) = 1;
LABEL_26:
          *(_DWORD *)(v3 + 64) = 1;
        }
      }
LABEL_27:
      FreeContextBuffer(pvContextBuffer);
      break;
    case 1:
      v11 = *(_DWORD *)(v3 + 40);
      *(_QWORD *)&pBuffer = a1 + 32;
      v25 = 1;
      v1 = OncRpcBufMgrAllocate((__int64 *)&pBuffer, v11, 4);
      if ( v1 >= 0 )
      {
        v12 = *(_QWORD *)(a1 + 72);
        if ( v12 )
          v12 = *(_QWORD *)(v12 + 64);
        *(_DWORD *)v12 = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)(a1 + 1008) + 40LL));
        *(_QWORD *)(*(_QWORD *)(a1 + 72) + 64LL) += 4LL;
        XdrEncodeOpaqueUnsafe(a1, *(unsigned int *)(*(_QWORD *)(a1 + 1008) + 40LL));
        FreeContextBuffer(*(PVOID *)(*(_QWORD *)(a1 + 1008) + 48LL));
        *(_QWORD *)(*(_QWORD *)(a1 + 1008) + 48LL) = 0;
        *(_DWORD *)(*(_QWORD *)(a1 + 1008) + 40LL) = 0;
      }
      break;
    case 2:
      v13 = *(_DWORD *)(v3 + 120);
      if ( v13 == 2 )
      {
        v14 = *(_QWORD *)(a1 + 72);
        if ( v14 )
          v15 = *(_QWORD *)(v14 + 64);
        else
          v15 = 0;
        *(_QWORD *)(a1 + 456) = v15;
        *(_QWORD *)(v14 + 64) += 4LL;
      }
      else
      {
        if ( v13 != 3 )
          break;
        v16 = *(_QWORD *)(a1 + 72);
        if ( v16 )
          v17 = *(_QWORD *)(v16 + 64);
        else
          v17 = 0;
        *(_QWORD *)(a1 + 456) = v17;
        *(_QWORD *)(v16 + 64) += 4LL;
        XdrNextMod4Boundary(a1);
        *(_QWORD *)(*(_QWORD *)(a1 + 72) + 64LL) += *(unsigned int *)(*(_QWORD *)(a1 + 1008) + 208LL);
      }
      XdrNextMod4Boundary(a1);
      v18 = *(_QWORD *)(a1 + 72);
      if ( v18 )
        v18 = *(_QWORD *)(v18 + 64);
      v19 = *(unsigned int *)(a1 + 316);
      *(_QWORD *)(a1 + 464) = v18;
      XdrEncodeInt_0(a1, v19);
      break;
  }
LABEL_47:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140008988  push    rbp
0x14000898a  push    rbx
0x14000898b  push    rsi
0x14000898c  push    rdi
0x14000898d  push    r12
0x14000898f  push    r15
0x140008991  lea     rbp, [rsp-2Fh]
0x140008996  sub     rsp, 0B8h
0x14000899d  mov     rax, cs:__security_cookie
0x1400089a4  xor     rax, rsp
0x1400089a7  mov     [rbp+57h+var_40], rax
0x1400089ab  xor     esi, esi
0x1400089ad  lea     r15, WPP_GLOBAL_Control
0x1400089b4  cmp     dword ptr [rcx+128h], 6
0x1400089bb  mov     rbx, rcx
0x1400089be  jnz     loc_140008D25
0x1400089c4  mov     rdi, [rcx+3F0h]
0x1400089cb  test    rdi, rdi
0x1400089ce  jz      loc_140008D25
0x1400089d4  mov     eax, [rdi+40h]
0x1400089d7  test    eax, eax
0x1400089d9  jnz     loc_140008BDB
0x1400089df  cmp     dword ptr [rdi+78h], 3
0x1400089e3  lea     rax, [rcx+20h]
0x1400089e7  mov     qword ptr [rbp+57h+pBuffer], rax
0x1400089eb  mov     ecx, 10002h
0x1400089f0  mov     eax, 40010002h
0x1400089f5  mov     [rbp+57h+var_58], rsi
0x1400089f9  cmovnz  eax, ecx
0x1400089fc  mov     [rbp+57h+pvContextBuffer], rsi
0x140008a00  cmp     cs:byte_14001AA22, sil
0x140008a07  mov     [rbp+57h+var_68], esi
0x140008a0a  mov     [rbp+57h+var_70], esi
0x140008a0d  mov     [rbp+57h+var_6C], esi
0x140008a10  jz      short loc_140008A16
0x140008a12  bts     eax, 0Ah
0x140008a16  lea     rdx, [rbp+57h+var_58]
0x140008a1a  mov     [rsp+0E0h+var_80], rdx
0x140008a1f  lea     r9, [rdi+0C0h]
0x140008a26  lea     rdx, [rbp+57h+var_68]
0x140008a2a  mov     [rsp+0E0h+var_88], rdx
0x140008a2f  lea     rcx, [rdi+50h]
0x140008a33  lea     rdx, [rbp+57h+pvContextBuffer]
0x140008a37  mov     [rsp+0E0h+var_90], rdx
0x140008a3c  lea     r8, [rdi+60h]
0x140008a40  lea     rdx, [rbp+57h+var_6C]
0x140008a44  mov     [rsp+0E0h+var_B0], rdx
0x140008a49  lea     rdx, [rbp+57h+var_70]
0x140008a4d  mov     [rsp+0E0h+var_B8], rdx
0x140008a52  mov     dword ptr [rsp+0E0h+var_C0], eax
0x140008a56  call    OncRpcSepInitializeSecurityContextComplex
0x140008a5b  mov     esi, eax
0x140008a5d  test    eax, eax
0x140008a5f  jns     short loc_140008A9A
0x140008a61  mov     rax, cs:WPP_GLOBAL_Control
0x140008a68  cmp     rax, r15
0x140008a6b  jz      loc_140008D25
0x140008a71  mov     ecx, [rax+2Ch]
0x140008a74  test    cl, 40h
0x140008a77  jz      loc_140008D25
0x140008a7d  mov     rcx, [rax+18h]
0x140008a81  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x140008a88  mov     edx, 42h ; 'B'
0x140008a8d  mov     r9d, esi
0x140008a90  call    WPP_SF_d
0x140008a95  jmp     loc_140008D25
0x140008a9a  cmp     [rbp+57h+var_70], 0
0x140008a9e  jz      short loc_140008AAD
0x140008aa0  cmp     [rbp+57h+var_70], 90312h
0x140008aa7  jnz     loc_140008D25
0x140008aad  mov     r15d, [rbp+57h+var_68]
0x140008ab1  lea     rax, [rbp+57h+var_6C]
0x140008ab5  xor     r9d, r9d
0x140008ab8  mov     [rbp+57h+var_6C], 1
0x140008abf  lea     rcx, [rbp+57h+pBuffer]
0x140008ac3  mov     [rsp+0E0h+var_C0], rax
0x140008ac8  lea     edx, [r15+4]
0x140008acc  lea     r8d, [r9+4]
0x140008ad0  call    OncRpcBufMgrAllocate
0x140008ad5  mov     esi, eax
0x140008ad7  test    eax, eax
0x140008ad9  js      loc_140008BBF
0x140008adf  mov     rax, [rbx+48h]
0x140008ae3  test    rax, rax
0x140008ae6  jnz     short loc_140008AEC
0x140008ae8  xor     ecx, ecx
0x140008aea  jmp     short loc_140008AF0
0x140008aec  mov     rcx, [rax+40h]
0x140008af0  mov     r8, [rbp+57h+pvContextBuffer]
0x140008af4  mov     eax, r15d
0x140008af7  bswap   eax
0x140008af9  mov     [rcx], eax
0x140008afb  mov     edx, r15d
0x140008afe  mov     rax, [rbx+48h]
0x140008b02  mov     rcx, rbx
0x140008b05  add     qword ptr [rax+40h], 4
0x140008b0a  call    XdrEncodeOpaqueUnsafe
0x140008b0f  cmp     [rbp+57h+var_70], 0
0x140008b13  jnz     loc_140008BA4
0x140008b19  xorps   xmm0, xmm0
0x140008b1c  lea     r8, [rbp+57h+pBuffer]; pBuffer
0x140008b20  xor     edx, edx; ulAttribute
0x140008b22  lea     rcx, [rdi+60h]; phContext
0x140008b26  movups  [rbp+57h+pBuffer], xmm0
0x140008b2a  call    cs:__imp_QueryContextAttributesW
0x140008b31  nop     dword ptr [rax+rax+00h]
0x140008b36  mov     ecx, eax; SecStatus
0x140008b38  call    cs:__imp_MapSecurityError
0x140008b3f  nop     dword ptr [rax+rax+00h]
0x140008b44  mov     esi, eax
0x140008b46  test    eax, eax
0x140008b48  jns     short loc_140008B7E
0x140008b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b51  lea     r15, WPP_GLOBAL_Control
0x140008b58  cmp     rcx, r15
0x140008b5b  jz      short loc_140008BC6
0x140008b5d  mov     eax, [rcx+2Ch]
0x140008b60  test    al, 40h
0x140008b62  jz      short loc_140008BC6
0x140008b64  mov     rcx, [rcx+18h]
0x140008b68  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x140008b6f  mov     edx, 43h ; 'C'
0x140008b74  mov     r9d, esi
0x140008b77  call    WPP_SF_d
0x140008b7c  jmp     short loc_140008BC6
0x140008b7e  mov     eax, dword ptr [rbp+57h+pBuffer+0Ch]
0x140008b81  mov     [rdi+0D0h], eax
0x140008b87  mov     eax, dword ptr [rbp+57h+pBuffer+8]
0x140008b8a  mov     [rdi+0D4h], eax
0x140008b90  mov     eax, dword ptr [rbp+57h+pBuffer]
0x140008b93  mov     [rdi+0D8h], eax
0x140008b99  mov     eax, dword ptr [rbp+57h+pBuffer+4]
0x140008b9c  mov     [rdi+0DCh], eax
0x140008ba2  jmp     short loc_140008BB8
0x140008ba4  cmp     [rbp+57h+var_70], 90312h
0x140008bab  jnz     short loc_140008BBF
0x140008bad  mov     rax, [rbx+3F0h]
0x140008bb4  mov     byte ptr [rax+38h], 1
0x140008bb8  mov     dword ptr [rdi+40h], 1
0x140008bbf  lea     r15, WPP_GLOBAL_Control
0x140008bc6  mov     rcx, [rbp+57h+pvContextBuffer]; pvContextBuffer
0x140008bca  call    cs:__imp_FreeContextBuffer
0x140008bd1  nop     dword ptr [rax+rax+00h]
0x140008bd6  jmp     loc_140008D25
0x140008bdb  cmp     eax, 1
0x140008bde  jnz     loc_140008C8C
0x140008be4  mov     edx, [rdi+28h]
0x140008be7  lea     rax, [rcx+20h]
0x140008beb  xor     r9d, r9d
0x140008bee  mov     qword ptr [rbp+57h+pBuffer], rax
0x140008bf2  lea     rax, [rbp+57h+var_6C]
0x140008bf6  mov     [rbp+57h+var_6C], 1
0x140008bfd  lea     rcx, [rbp+57h+pBuffer]
0x140008c01  mov     [rsp+0E0h+var_C0], rax
0x140008c06  lea     r8d, [r9+4]
0x140008c0a  call    OncRpcBufMgrAllocate
0x140008c0f  mov     esi, eax
0x140008c11  test    eax, eax
0x140008c13  js      loc_140008D25
0x140008c19  mov     rax, [rbx+3F0h]
0x140008c20  mov     ecx, [rax+28h]
0x140008c23  mov     rax, [rbx+48h]
0x140008c27  test    rax, rax
0x140008c2a  jz      short loc_140008C30
0x140008c2c  mov     rax, [rax+40h]
0x140008c30  bswap   ecx
0x140008c32  mov     [rax], ecx
0x140008c34  mov     rcx, rbx
0x140008c37  mov     rax, [rbx+48h]
0x140008c3b  add     qword ptr [rax+40h], 4
0x140008c40  mov     rdx, [rbx+3F0h]
0x140008c47  mov     r8, [rdx+30h]
0x140008c4b  mov     edx, [rdx+28h]
0x140008c4e  call    XdrEncodeOpaqueUnsafe
0x140008c53  mov     rcx, [rbx+3F0h]
0x140008c5a  mov     rcx, [rcx+30h]; pvContextBuffer
0x140008c5e  call    cs:__imp_FreeContextBuffer
0x140008c65  nop     dword ptr [rax+rax+00h]
0x140008c6a  mov     rax, [rbx+3F0h]
0x140008c71  mov     qword ptr [rax+30h], 0
0x140008c79  mov     rax, [rbx+3F0h]
0x140008c80  mov     dword ptr [rax+28h], 0
0x140008c87  jmp     loc_140008D25
0x140008c8c  cmp     eax, 2
0x140008c8f  jnz     loc_140008D25
0x140008c95  mov     eax, [rdi+78h]
0x140008c98  cmp     eax, 2
0x140008c9b  jnz     short loc_140008CBC
0x140008c9d  mov     rax, [rcx+48h]
0x140008ca1  test    rax, rax
0x140008ca4  jnz     short loc_140008CAA
0x140008ca6  xor     ecx, ecx
0x140008ca8  jmp     short loc_140008CAE
0x140008caa  mov     rcx, [rax+40h]
0x140008cae  mov     [rbx+1C8h], rcx
0x140008cb5  add     qword ptr [rax+40h], 4
0x140008cba  jmp     short loc_140008CFB
0x140008cbc  cmp     eax, 3
0x140008cbf  jnz     short loc_140008D25
0x140008cc1  mov     rax, [rcx+48h]
0x140008cc5  test    rax, rax
0x140008cc8  jnz     short loc_140008CCE
0x140008cca  xor     ecx, ecx
0x140008ccc  jmp     short loc_140008CD2
0x140008cce  mov     rcx, [rax+40h]
0x140008cd2  mov     [rbx+1C8h], rcx
0x140008cd9  mov     rcx, rbx
0x140008cdc  add     qword ptr [rax+40h], 4
0x140008ce1  call    XdrNextMod4Boundary
0x140008ce6  mov     rax, [rbx+3F0h]
0x140008ced  mov     r8, [rbx+48h]
0x140008cf1  mov     ecx, [rax+0D0h]
0x140008cf7  add     [r8+40h], rcx
0x140008cfb  mov     rcx, rbx
0x140008cfe  call    XdrNextMod4Boundary
0x140008d03  mov     rax, [rbx+48h]
0x140008d07  test    rax, rax
0x140008d0a  jz      short loc_140008D10
0x140008d0c  mov     rax, [rax+40h]
0x140008d10  mov     edx, [rbx+13Ch]
0x140008d16  mov     rcx, rbx
0x140008d19  mov     [rbx+1D0h], rax
0x140008d20  call    XdrEncodeInt_0
0x140008d25  mov     rcx, cs:WPP_GLOBAL_Control
0x140008d2c  cmp     rcx, r15
0x140008d2f  jz      short loc_140008D50
0x140008d31  mov     eax, [rcx+2Ch]
0x140008d34  test    al, 1
0x140008d36  jz      short loc_140008D50
0x140008d38  mov     rcx, [rcx+18h]
0x140008d3c  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x140008d43  mov     edx, 44h ; 'D'
0x140008d48  mov     r9d, esi
0x140008d4b  call    WPP_SF_d
0x140008d50  mov     eax, esi
0x140008d52  mov     rcx, [rbp+57h+var_40]
0x140008d56  xor     rcx, rsp; StackCookie
0x140008d59  call    __security_check_cookie
0x140008d5e  add     rsp, 0B8h
0x140008d65  pop     r15
0x140008d67  pop     r12
0x140008d69  pop     rdi
0x140008d6a  pop     rsi
0x140008d6b  pop     rbx
0x140008d6c  pop     rbp
0x140008d6d  retn
```
