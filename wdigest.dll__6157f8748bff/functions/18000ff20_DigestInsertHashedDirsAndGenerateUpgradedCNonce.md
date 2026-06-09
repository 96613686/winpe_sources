# DigestInsertHashedDirsAndGenerateUpgradedCNonce

- ea: `0x18000ff20`
- end: `0x18001013f`
- name: `DigestInsertHashedDirsAndGenerateUpgradedCNonce`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x1800206d0`

## callees

- `0x1800076b0`
- `0x18000c6f0`
- `0x18000c850`
- `0x18000eff0`
- `0x18000ff20`
- `0x180011e48`
- `0x180012880`
- `0x180018298`
- `0x18002b934`
- `0x180034398`
- `0x1800377bc`

## import_xrefs

- `ntdll!RtlInitString` at `0x180010071`
- `ntdll!RtlInitString` at `0x180010071`

## string_xrefs

- `0x180010044`: `service-name,channel-binding`

## pseudocode

```c
__int64 __fastcall DigestInsertHashedDirsAndGenerateUpgradedCNonce(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _BYTE *v7; // r13
  unsigned __int16 v8; // r12
  __int64 result; // rax
  __int64 v10; // rcx
  unsigned __int16 v11; // bx
  __int64 v12; // r8
  __int64 v13; // rbx
  _OWORD *v14; // rcx
  __int16 *v15; // r8
  __int16 v16; // cx
  __int64 v17; // xmm0_8
  __int16 v18; // ax
  __int64 v19; // r8
  __int64 v20; // rsi
  char *v21; // rax
  __int64 v22; // rcx
  __int128 v23; // xmm1
  _BYTE v24[8]; // [rsp+20h] [rbp-B1h] BYREF
  __int64 v25; // [rsp+28h] [rbp-A9h] BYREF
  void *Src; // [rsp+30h] [rbp-A1h]
  __int64 v27; // [rsp+38h] [rbp-99h] BYREF
  __int64 v28; // [rsp+40h] [rbp-91h] BYREF
  char *v29; // [rsp+48h] [rbp-89h]
  __int64 v30; // [rsp+50h] [rbp-81h]
  __int64 v31; // [rsp+58h] [rbp-79h]
  _OWORD v32[2]; // [rsp+60h] [rbp-71h] BYREF
  _BYTE v33[16]; // [rsp+80h] [rbp-51h] BYREF
  _BYTE v34[40]; // [rsp+90h] [rbp-41h] BYREF
  char v35; // [rsp+B8h] [rbp-19h] BYREF

  v29 = &v35;
  v30 = a4;
  v7 = v34;
  v31 = a1;
  Src = v34;
  v27 = 0;
  v24[0] = 0;
  v8 = 0;
  v25 = 2162688;
  v28 = 2162688;
  result = SspGetChannelBindings(a1, a1, &v27);
  if ( (int)result >= 0 )
  {
    result = SspHashIscChannelBindings(v10, v27, v33, v24);
    if ( (int)result >= 0 )
    {
      v11 = 32;
      if ( v24[0] )
      {
        v20 = 0;
      }
      else
      {
        memset((char *)v32 + 2, 0, 30);
        result = StringAllocate(a5, 32);
        if ( (int)result < 0 )
          return result;
        v12 = *(_QWORD *)(a5 + 8);
        *(_WORD *)a5 = 32;
        BinToHex(v33, 16, v12);
        StringReference(a2 + 392, a5);
        v13 = v30;
        v32[1] = *v14;
        result = GetIscServiceName(v31, v30);
        if ( (int)result < 0 )
          return result;
        StringReference(a2 + 376, v13);
        v16 = *v15;
        v17 = *(_QWORD *)(v15 + 1);
        *(_DWORD *)((char *)v32 + 10) = *(_DWORD *)(v15 + 5);
        v18 = v15[7];
        LOWORD(v32[0]) = v16;
        HIWORD(v32[0]) = v18;
        *(_QWORD *)((char *)v32 + 2) = v17;
        RtlInitString((PSTRING)(a2 + 360), "service-name,channel-binding");
        result = DigestHashN((__int64)v32, 2u, v19, (__int64)&v25);
        if ( (int)result < 0 )
          return result;
        v7 = Src;
        v11 = 76;
        v8 = v25;
        *(_WORD *)(a2 + 4) |= 0x100u;
        v20 = 44;
      }
      result = StringAllocate(a3, v11);
      if ( (int)result >= 0 )
      {
        result = OpaqueCreate(&v28);
        if ( (int)result >= 0 )
        {
          if ( !v24[0] )
          {
            qmemcpy(*(void **)(a3 + 8), "+Upgraded+v1", 12);
            memcpy_0((void *)(*(_QWORD *)(a3 + 8) + 12LL), v7, v8);
          }
          v21 = v29;
          v22 = *(_QWORD *)(a3 + 8);
          *(_OWORD *)(v22 + v20) = *(_OWORD *)v29;
          v23 = *((_OWORD *)v21 + 1);
          result = 0;
          *(_OWORD *)(v22 + v20 + 16) = v23;
          *(_WORD *)a3 = v11;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ff20  push    rbp
0x18000ff22  push    rbx
0x18000ff23  push    rsi
0x18000ff24  push    rdi
0x18000ff25  push    r12
0x18000ff27  push    r13
0x18000ff29  push    r15
0x18000ff2b  lea     rbp, [rsp-1Fh]
0x18000ff30  sub     rsp, 0F0h
0x18000ff37  mov     rax, cs:__security_cookie
0x18000ff3e  xor     rax, rsp
0x18000ff41  mov     [rbp+4Fh+var_40], rax
0x18000ff45  mov     r15, [rbp+4Fh+arg_20]
0x18000ff49  lea     rax, [rbp+4Fh+var_68]
0x18000ff4d  mov     rdi, r8
0x18000ff50  mov     [rsp+120h+var_D8], rax
0x18000ff55  mov     rsi, rdx
0x18000ff58  mov     [rsp+120h+var_D0], r9
0x18000ff5d  lea     r13, [rbp+4Fh+var_90]
0x18000ff61  mov     [rbp+4Fh+var_C8], rcx
0x18000ff65  lea     r8, [rsp+120h+var_E8]
0x18000ff6a  mov     [rsp+120h+Src], r13
0x18000ff6f  mov     rdx, rcx
0x18000ff72  mov     [rsp+120h+var_E8], 0
0x18000ff7b  mov     [rsp+120h+var_100], 0
0x18000ff80  xor     r12d, r12d
0x18000ff83  mov     [rsp+120h+var_F8], 210000h
0x18000ff8c  mov     [rsp+120h+var_E0], 210000h
0x18000ff95  call    SspGetChannelBindings
0x18000ff9a  test    eax, eax
0x18000ff9c  js      loc_180010121
0x18000ffa2  mov     rdx, [rsp+120h+var_E8]
0x18000ffa7  lea     r9, [rsp+120h+var_100]
0x18000ffac  lea     r8, [rbp+4Fh+var_A0]
0x18000ffb0  call    SspHashIscChannelBindings
0x18000ffb5  test    eax, eax
0x18000ffb7  js      loc_180010121
0x18000ffbd  lea     ebx, [r12+20h]
0x18000ffc2  cmp     [rsp+120h+var_100], r12b
0x18000ffc7  jnz     loc_1800100B0
0x18000ffcd  xorps   xmm0, xmm0
0x18000ffd0  mov     edx, ebx
0x18000ffd2  movups  xmmword ptr [rbp+4Fh+var_BE], xmm0
0x18000ffd6  mov     rcx, r15
0x18000ffd9  movups  xmmword ptr [rbp+4Fh+var_BE+0Eh], xmm0
0x18000ffdd  call    StringAllocate
0x18000ffe2  test    eax, eax
0x18000ffe4  js      loc_180010121
0x18000ffea  mov     r8, [r15+8]
0x18000ffee  lea     edx, [rbx-10h]
0x18000fff1  lea     rcx, [rbp+4Fh+var_A0]
0x18000fff5  mov     [r15], bx
0x18000fff9  call    BinToHex
0x18000fffe  lea     rcx, [rsi+188h]
0x180010005  mov     rdx, r15
0x180010008  call    StringReference
0x18001000d  movups  xmm1, xmmword ptr [rcx]
0x180010010  mov     rbx, [rsp+120h+var_D0]
0x180010015  mov     rcx, [rbp+4Fh+var_C8]
0x180010019  mov     rdx, rbx
0x18001001c  movdqu  xmmword ptr [rbp+4Fh+var_BE+0Eh], xmm1
0x180010021  call    GetIscServiceName
0x180010026  test    eax, eax
0x180010028  js      loc_180010121
0x18001002e  lea     r8, [rsi+178h]
0x180010035  mov     rdx, rbx
0x180010038  mov     rcx, r8
0x18001003b  call    StringReference
0x180010040  mov     eax, [r8+0Ah]
0x180010044  lea     rdx, aServiceNameCha; "service-name,channel-binding"
0x18001004b  movzx   ecx, word ptr [r8]
0x18001004f  movsd   xmm0, qword ptr [r8+2]
0x180010055  mov     dword ptr [rbp+4Fh+var_BE+8], eax
0x180010058  movzx   eax, word ptr [r8+0Eh]
0x18001005d  mov     [rbp+4Fh+var_C0], cx
0x180010061  lea     rcx, [rsi+168h]; DestinationString
0x180010068  mov     word ptr [rbp+4Fh+var_BE+0Ch], ax
0x18001006c  movsd   qword ptr [rbp+4Fh+var_BE], xmm0
0x180010071  call    cs:__imp_RtlInitString
0x180010077  lea     r9, [rsp+120h+var_F8]
0x18001007c  lea     edx, [r12+2]
0x180010081  lea     rcx, [rbp+4Fh+var_C0]
0x180010085  call    DigestHashN
0x18001008a  test    eax, eax
0x18001008c  js      loc_180010121
0x180010092  mov     r13, [rsp+120h+Src]
0x180010097  lea     ebx, [r12+4Ch]
0x18001009c  movzx   r12d, word ptr [rsp+120h+var_F8]
0x1800100a2  mov     eax, 100h
0x1800100a7  or      [rsi+4], ax
0x1800100ab  lea     esi, [rbx-20h]
0x1800100ae  jmp     short loc_1800100B2
0x1800100b0  xor     esi, esi
0x1800100b2  movzx   edx, bx
0x1800100b5  mov     rcx, rdi
0x1800100b8  call    StringAllocate
0x1800100bd  test    eax, eax
0x1800100bf  js      short loc_180010121
0x1800100c1  lea     rcx, [rsp+120h+var_E0]
0x1800100c6  call    OpaqueCreate
0x1800100cb  test    eax, eax
0x1800100cd  js      short loc_180010121
0x1800100cf  cmp     [rsp+120h+var_100], 0
0x1800100d4  jnz     short loc_180010103
0x1800100d6  mov     rcx, [rdi+8]
0x1800100da  mov     rdx, r13; Src
0x1800100dd  movsd   xmm0, qword ptr cs:aUpgradedV1; "+Upgraded+v1"
0x1800100e5  movzx   r8d, r12w; Size
0x1800100e9  movsd   qword ptr [rcx], xmm0
0x1800100ed  mov     eax, dword ptr cs:aUpgradedV1+8; "d+v1"
0x1800100f3  mov     [rcx+8], eax
0x1800100f6  mov     rcx, [rdi+8]
0x1800100fa  add     rcx, 0Ch; void *
0x1800100fe  call    memcpy_0
0x180010103  mov     rax, [rsp+120h+var_D8]
0x180010108  mov     rcx, [rdi+8]
0x18001010c  movups  xmm0, xmmword ptr [rax]
0x18001010f  movups  xmmword ptr [rcx+rsi], xmm0
0x180010113  movups  xmm1, xmmword ptr [rax+10h]
0x180010117  xor     eax, eax
0x180010119  movups  xmmword ptr [rcx+rsi+10h], xmm1
0x18001011e  mov     [rdi], bx
0x180010121  mov     rcx, [rbp+4Fh+var_40]
0x180010125  xor     rcx, rsp; StackCookie
0x180010128  call    __security_check_cookie
0x18001012d  add     rsp, 0F0h
0x180010134  pop     r15
0x180010136  pop     r13
0x180010138  pop     r12
0x18001013a  pop     rdi
0x18001013b  pop     rsi
0x18001013c  pop     rbx
0x18001013d  pop     rbp
0x18001013e  retn
```
