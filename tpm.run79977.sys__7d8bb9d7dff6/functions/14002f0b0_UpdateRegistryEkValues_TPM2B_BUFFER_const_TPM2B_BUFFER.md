# UpdateRegistryEkValues(TPM2B_BUFFER const *,TPM2B_BUFFER *)

- ea: `0x14002f0b0`
- end: `0x14002f490`
- name: `?UpdateRegistryEkValues@@YAJPEBVTPM2B_BUFFER@@PEAV1@@Z`
- size: `992`
- prototype: `__int64 __fastcall(const struct TPM2B_BUFFER *, struct TPM2B_BUFFER *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x14002d050`

## callees

- `0x1400055dc`
- `0x1400078b8`
- `0x140009278`
- `0x14000a164`
- `0x14000b6c8`
- `0x14001ac60`
- `0x14002ecec`
- `0x14002f0b0`
- `0x14002fe48`
- `0x140030470`
- `0x140039740`
- `0x140039b40`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall UpdateRegistryEkValues(const void **a1, struct TPM2B_BUFFER *a2)
{
  int v4; // edi
  unsigned __int16 v5; // r8
  unsigned __int64 v6; // r14
  unsigned int v7; // eax
  int v8; // edx
  int v9; // r8d
  unsigned int v10; // r9d
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  int inited; // edi
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned __int16 v17; // r9
  unsigned int v18; // r8d
  unsigned int v19; // edx
  unsigned __int32 v20; // edi
  unsigned int v21; // ecx
  char *v22; // rdi
  int v23; // esp
  int v24; // edi
  struct _UNICODE_STRING v26; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v27[68]; // [rsp+40h] [rbp-C0h] BYREF

  memset(v27, 0, 0x21Cu);
  if ( *(_WORD *)a1 > 0x200u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
    return (unsigned int)-1073741811;
  }
  v6 = SizeOfDigest(__ROR2__(*(_WORD *)(*((_QWORD *)a2 + 1) + 2LL), 8));
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids, v5);
    return (unsigned int)-1073741811;
  }
  v7 = TpmRegistry::DeleteKeyValue(4u, L"EKPub");
  v10 = v7;
  if ( v7 )
  {
    if ( v7 == -1073741772 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        v12 = 28;
        goto LABEL_18;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids, v7);
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v12 = 27;
LABEL_18:
      WPP_SF_(v11->AttachedDevice, v12, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
    }
  }
  v26 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_ds(WPP_GLOBAL_Control->AttachedDevice, v8, v9, v10, (__int64)"true");
  inited = TpmRegistry::InitRegistryKey(&v26, 22);
  if ( inited >= 0 )
    inited = TpmRegistry::DeleteKey(&v26, 1);
  TpmFree(v26.Buffer);
  if ( inited )
  {
    if ( inited == -1073741772 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        v15 = 31;
        goto LABEL_35;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        32,
        WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids,
        (unsigned int)inited);
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v15 = 30;
LABEL_35:
      WPP_SF_(v14->AttachedDevice, v15, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
    }
  }
  v16 = *((_QWORD *)a2 + 1);
  v17 = __ROR2__(*(_WORD *)(v6 + v16 + 18), 8);
  v18 = 3;
  v19 = 0;
  v20 = _byteswap_ulong(*(_DWORD *)(v6 + v16 + 20));
  while ( v19 < 4 )
  {
    if ( ((0xFF000000 >> (8 * v19)) & v20) != 0 )
    {
      v18 = 4 - v19;
      break;
    }
    ++v19;
  }
  v21 = *(unsigned __int16 *)a1;
  HIDWORD(v27[0]) = v17;
  LODWORD(v27[0]) = 826364754;
  v27[1] = __PAIR64__(v21, v18);
  v27[2] = 0;
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids, v20);
      LOWORD(v21) = *(_WORD *)a1;
      v18 = v27[1];
    }
    LODWORD(v27[3]) = v20;
  }
  else
  {
    LODWORD(v27[3]) = 65537;
  }
  v22 = (char *)&v27[3] + v18;
  if ( memcpy_s(v22, 516LL - v18, a1[1], (unsigned __int16)v21) )
  {
    return (unsigned int)-1073741595;
  }
  else
  {
    v24 = (_DWORD)v22 - (v23 + 64);
    v4 = TpmRegistry::AssignValue(4, L"EKPub", 3, v27, (unsigned int)*(unsigned __int16 *)a1 + v24);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          35,
          WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids,
          (unsigned int)v4);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14002f0b0  mov     [rsp-8+arg_10], rbx
0x14002f0b5  push    rbp
0x14002f0b6  push    rsi
0x14002f0b7  push    rdi
0x14002f0b8  push    r12
0x14002f0ba  push    r13
0x14002f0bc  push    r14
0x14002f0be  push    r15
0x14002f0c0  lea     rbp, [rsp-170h]
0x14002f0c8  sub     rsp, 270h
0x14002f0cf  mov     rax, cs:__security_cookie
0x14002f0d6  xor     rax, rsp
0x14002f0d9  mov     [rbp+1A0h+var_40], rax
0x14002f0e0  mov     r13, rdx
0x14002f0e3  mov     r15, rcx
0x14002f0e6  xor     edx, edx; Val
0x14002f0e8  lea     rcx, [rsp+2A0h+var_260]; void *
0x14002f0ed  mov     r8d, 21Ch; Size
0x14002f0f3  call    memset
0x14002f0f8  mov     eax, 200h
0x14002f0fd  cmp     [r15], ax
0x14002f101  jbe     short loc_14002F13C
0x14002f103  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f10a  lea     rbx, WPP_GLOBAL_Control
0x14002f111  cmp     rcx, rbx
0x14002f114  jz      short loc_14002F132
0x14002f116  mov     eax, [rcx+2Ch]
0x14002f119  test    al, 1
0x14002f11b  jz      short loc_14002F132
0x14002f11d  mov     rcx, [rcx+18h]
0x14002f121  lea     r8, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids
0x14002f128  mov     edx, 19h
0x14002f12d  call    WPP_SF_
0x14002f132  mov     edi, 0C000000Dh
0x14002f137  jmp     loc_14002F463
0x14002f13c  mov     rax, [r13+8]
0x14002f140  movzx   r8d, word ptr [rax+2]
0x14002f145  ror     r8w, 8
0x14002f14a  movzx   ecx, r8w; unsigned __int16
0x14002f14e  call    ?SizeOfDigest@@YA_KG@Z; SizeOfDigest(ushort)
0x14002f153  mov     r14, rax
0x14002f156  test    rax, rax
0x14002f159  jnz     short loc_14002F18F
0x14002f15b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f162  lea     rbx, WPP_GLOBAL_Control
0x14002f169  cmp     rcx, rbx
0x14002f16c  jz      short loc_14002F132
0x14002f16e  mov     eax, [rcx+2Ch]
0x14002f171  test    al, 1
0x14002f173  jz      short loc_14002F132
0x14002f175  mov     rcx, [rcx+18h]
0x14002f179  lea     edx, [r14+1Ah]
0x14002f17d  movzx   r9d, r8w
0x14002f181  lea     r8, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids
0x14002f188  call    WPP_SF_d
0x14002f18d  jmp     short loc_14002F132
0x14002f18f  mov     r12d, 4
0x14002f195  lea     rdx, aEkpub; "EKPub"
0x14002f19c  mov     ecx, r12d
0x14002f19f  call    ?DeleteKeyValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBG@Z; TpmRegistry::DeleteKeyValue(TpmRegistry::KEY_VALUES,ushort const *)
0x14002f1a4  lea     rsi, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids
0x14002f1ab  mov     r9d, eax
0x14002f1ae  test    eax, eax
0x14002f1b0  jnz     short loc_14002F1D4
0x14002f1b2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f1b9  lea     rbx, WPP_GLOBAL_Control
0x14002f1c0  cmp     rcx, rbx
0x14002f1c3  jz      short loc_14002F237
0x14002f1c5  mov     eax, [rcx+2Ch]
0x14002f1c8  test    r12b, al
0x14002f1cb  jz      short loc_14002F237
0x14002f1cd  lea     edx, [r12+17h]
0x14002f1d2  jmp     short loc_14002F1FD
0x14002f1d4  cmp     r9d, 0C0000034h
0x14002f1db  jnz     short loc_14002F20B
0x14002f1dd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f1e4  lea     rbx, WPP_GLOBAL_Control
0x14002f1eb  cmp     rcx, rbx
0x14002f1ee  jz      short loc_14002F237
0x14002f1f0  mov     eax, [rcx+2Ch]
0x14002f1f3  test    r12b, al
0x14002f1f6  jz      short loc_14002F237
0x14002f1f8  mov     edx, 1Ch
0x14002f1fd  mov     rcx, [rcx+18h]
0x14002f201  mov     r8, rsi
0x14002f204  call    WPP_SF_
0x14002f209  jmp     short loc_14002F237
0x14002f20b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f212  lea     rbx, WPP_GLOBAL_Control
0x14002f219  cmp     rcx, rbx
0x14002f21c  jz      short loc_14002F237
0x14002f21e  mov     eax, [rcx+2Ch]
0x14002f221  test    r12b, al
0x14002f224  jz      short loc_14002F237
0x14002f226  mov     rcx, [rcx+18h]
0x14002f22a  mov     edx, 1Dh
0x14002f22f  mov     r8, rsi
0x14002f232  call    WPP_SF_d
0x14002f237  xorps   xmm0, xmm0
0x14002f23a  movups  xmmword ptr [rsp+2A0h+var_270.Length], xmm0
0x14002f23f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f246  cmp     rcx, rbx
0x14002f249  jz      short loc_14002F268
0x14002f24b  mov     eax, [rcx+2Ch]
0x14002f24e  test    r12b, al
0x14002f251  jz      short loc_14002F268
0x14002f253  mov     rcx, [rcx+18h]
0x14002f257  lea     rax, aTrue; "true"
0x14002f25e  mov     [rsp+2A0h+var_280], rax
0x14002f263  call    WPP_SF_ds
0x14002f268  mov     edx, 16h
0x14002f26d  lea     rcx, [rsp+2A0h+var_270]
0x14002f272  call    ?InitRegistryKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@W4KEY_VALUES@1@@Z; TpmRegistry::InitRegistryKey(_UNICODE_STRING *,TpmRegistry::KEY_VALUES)
0x14002f277  mov     edi, eax
0x14002f279  test    eax, eax
0x14002f27b  js      short loc_14002F28E
0x14002f27d  mov     edx, 1; int
0x14002f282  lea     rcx, [rsp+2A0h+var_270]; struct _UNICODE_STRING *
0x14002f287  call    ?DeleteKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@H@Z; TpmRegistry::DeleteKey(_UNICODE_STRING *,int)
0x14002f28c  mov     edi, eax
0x14002f28e  mov     rcx, [rsp+2A0h+var_270.Buffer]; void *
0x14002f293  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14002f298  test    edi, edi
0x14002f29a  jnz     short loc_14002F2B5
0x14002f29c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f2a3  cmp     rcx, rbx
0x14002f2a6  jz      short loc_14002F30C
0x14002f2a8  mov     eax, [rcx+2Ch]
0x14002f2ab  test    r12b, al
0x14002f2ae  jz      short loc_14002F30C
0x14002f2b0  lea     edx, [rdi+1Eh]
0x14002f2b3  jmp     short loc_14002F2D6
0x14002f2b5  cmp     edi, 0C0000034h
0x14002f2bb  jnz     short loc_14002F2E4
0x14002f2bd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f2c4  cmp     rcx, rbx
0x14002f2c7  jz      short loc_14002F30C
0x14002f2c9  mov     eax, [rcx+2Ch]
0x14002f2cc  test    r12b, al
0x14002f2cf  jz      short loc_14002F30C
0x14002f2d1  mov     edx, 1Fh
0x14002f2d6  mov     rcx, [rcx+18h]
0x14002f2da  mov     r8, rsi
0x14002f2dd  call    WPP_SF_
0x14002f2e2  jmp     short loc_14002F30C
0x14002f2e4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f2eb  cmp     rcx, rbx
0x14002f2ee  jz      short loc_14002F30C
0x14002f2f0  mov     eax, [rcx+2Ch]
0x14002f2f3  test    r12b, al
0x14002f2f6  jz      short loc_14002F30C
0x14002f2f8  mov     rcx, [rcx+18h]
0x14002f2fc  mov     edx, 20h ; ' '
0x14002f301  mov     r9d, edi
0x14002f304  mov     r8, rsi
0x14002f307  call    WPP_SF_d
0x14002f30c  mov     rax, [r13+8]
0x14002f310  movzx   r9d, word ptr [r14+rax+12h]
0x14002f316  mov     edi, [r14+rax+14h]
0x14002f31b  mov     r14d, 3
0x14002f321  ror     r9w, 8
0x14002f326  mov     r8d, r14d
0x14002f329  xor     edx, edx
0x14002f32b  bswap   edi
0x14002f32d  cmp     edx, r12d
0x14002f330  jnb     short loc_14002F34E
0x14002f332  lea     ecx, ds:0[rdx*8]
0x14002f339  mov     eax, 0FF000000h
0x14002f33e  shr     eax, cl
0x14002f340  test    edi, eax
0x14002f342  jnz     short loc_14002F348
0x14002f344  inc     edx
0x14002f346  jmp     short loc_14002F32D
0x14002f348  mov     r8d, r12d
0x14002f34b  sub     r8d, edx
0x14002f34e  movzx   ecx, word ptr [r15]
0x14002f352  movzx   eax, r9w
0x14002f356  mov     [rsp+2A0h+var_25C], eax
0x14002f35a  mov     [rsp+2A0h+var_254], ecx
0x14002f35e  mov     [rsp+2A0h+var_260], 31415352h
0x14002f366  mov     [rsp+2A0h+var_258], r8d
0x14002f36b  mov     [rsp+2A0h+var_250], 0
0x14002f374  test    edi, edi
0x14002f376  jnz     short loc_14002F382
0x14002f378  mov     [rsp+2A0h+var_248], 10001h
0x14002f380  jmp     short loc_14002F3B8
0x14002f382  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f389  cmp     r10, rbx
0x14002f38c  jz      short loc_14002F3B4
0x14002f38e  mov     eax, [r10+2Ch]
0x14002f392  test    r12b, al
0x14002f395  jz      short loc_14002F3B4
0x14002f397  mov     rcx, [r10+18h]
0x14002f39b  mov     edx, 21h ; '!'
0x14002f3a0  mov     r9d, edi
0x14002f3a3  mov     r8, rsi
0x14002f3a6  call    WPP_SF_d
0x14002f3ab  movzx   ecx, word ptr [r15]
0x14002f3af  mov     r8d, [rsp+2A0h+var_258]
0x14002f3b4  mov     [rsp+2A0h+var_248], edi
0x14002f3b8  mov     eax, r8d
0x14002f3bb  lea     rdi, [rsp+2A0h+var_248]
0x14002f3c0  mov     r8, [r15+8]; Src
0x14002f3c4  add     rdi, rax
0x14002f3c7  movzx   r9d, cx; MaxCount
0x14002f3cb  mov     edx, 204h
0x14002f3d0  mov     rcx, rdi; void *
0x14002f3d3  sub     rdx, rax; DstSize
0x14002f3d6  call    memcpy_s
0x14002f3db  test    eax, eax
0x14002f3dd  jz      short loc_14002F3E6
0x14002f3df  mov     edi, 0C00000E5h
0x14002f3e4  jmp     short loc_14002F463
0x14002f3e6  lea     rax, [rsp+2A0h+var_260]
0x14002f3eb  mov     r8d, r14d
0x14002f3ee  sub     edi, eax
0x14002f3f0  lea     r9, [rsp+2A0h+var_260]
0x14002f3f5  movzx   eax, word ptr [r15]
0x14002f3f9  lea     rdx, aEkpub; "EKPub"
0x14002f400  add     edi, eax
0x14002f402  mov     ecx, r12d
0x14002f405  mov     dword ptr [rsp+2A0h+var_280], edi
0x14002f409  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x14002f40e  mov     edi, eax
0x14002f410  test    eax, eax
0x14002f412  js      short loc_14002F43B
0x14002f414  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f41b  cmp     rcx, rbx
0x14002f41e  jz      short loc_14002F463
0x14002f420  mov     edx, [rcx+2Ch]
0x14002f423  test    r12b, dl
0x14002f426  jz      short loc_14002F463
0x14002f428  mov     rcx, [rcx+18h]
0x14002f42c  mov     edx, 22h ; '"'
0x14002f431  mov     r8, rsi
0x14002f434  call    WPP_SF_
0x14002f439  jmp     short loc_14002F463
0x14002f43b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f442  cmp     rcx, rbx
0x14002f445  jz      short loc_14002F463
0x14002f447  mov     eax, [rcx+2Ch]
0x14002f44a  test    r12b, al
0x14002f44d  jz      short loc_14002F463
0x14002f44f  mov     rcx, [rcx+18h]
0x14002f453  mov     edx, 23h ; '#'
0x14002f458  mov     r9d, edi
0x14002f45b  mov     r8, rsi
0x14002f45e  call    WPP_SF_d
0x14002f463  mov     eax, edi
0x14002f465  mov     rcx, [rbp+1A0h+var_40]
0x14002f46c  xor     rcx, rsp; StackCookie
0x14002f46f  call    __security_check_cookie
0x14002f474  mov     rbx, [rsp+2A0h+arg_10]
0x14002f47c  add     rsp, 270h
0x14002f483  pop     r15
0x14002f485  pop     r14
0x14002f487  pop     r13
0x14002f489  pop     r12
0x14002f48b  pop     rdi
0x14002f48c  pop     rsi
0x14002f48d  pop     rbp
0x14002f48e  retn
```
