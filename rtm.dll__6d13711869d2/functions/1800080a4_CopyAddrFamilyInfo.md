# CopyAddrFamilyInfo

- ea: `0x1800080a4`
- end: `0x18000821d`
- name: `CopyAddrFamilyInfo`
- size: `377`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008230`
- `0x1800084c0`

## callees

- `0x180002cb0`
- `0x1800080a4`
- `0x180009d14`
- `0x18001f980`

## string_xrefs

- `0x180008115`: `Entered: CopyAddrFamilyInfo`
- `0x1800081c2`: `Leaving: CopyAddrFamilyInfo`

## pseudocode

```c
__int64 __fastcall CopyAddrFamilyInfo(struct _SPropValue *a1, __int64 a2, __int64 a3)
{
  __int16 v5; // r14
  __int64 v6; // rsi
  __int128 *v7; // r9
  __int64 result; // rax
  __int128 *v9; // r9
  ULONG uliInst[2]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v11; // [rsp+38h] [rbp-48h] BYREF
  int v12; // [rsp+48h] [rbp-38h] BYREF
  __int128 v13; // [rsp+4Ch] [rbp-34h]
  __int128 v14; // [rsp+5Ch] [rbp-24h]
  int v15; // [rsp+6Ch] [rbp-14h]

  *(_QWORD *)uliInst = 0;
  v12 = 0;
  v15 = 0;
  v5 = (__int16)a1;
  v13 = 0;
  v14 = 0;
  v11 = 0;
  GetInstance(a1, 0, (ULONG)uliInst);
  v6 = *(_QWORD *)uliInst;
  if ( (byte_18002BD1A & 8) != 0 )
  {
    v7 = &v11;
    LOWORD(v12) = 0;
    if ( *(_QWORD *)uliInst != -48 )
      LODWORD(v7) = uliInst[0] + 48;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
      (unsigned int)L"Entered: CopyAddrFamilyInfo",
      (_DWORD)v7,
      0,
      (__int64)&v12);
  }
  *(_WORD *)a3 = v5;
  *(_WORD *)(a3 + 2) = *(_WORD *)(a2 + 4);
  *(_DWORD *)(a3 + 4) = *(_DWORD *)(a2 + 40);
  *(_DWORD *)(a3 + 8) = *(_DWORD *)(a2 + 304);
  *(_DWORD *)(a3 + 12) = *(_DWORD *)(a2 + 308);
  *(_DWORD *)(a3 + 16) = *(_DWORD *)(a2 + 312);
  *(_DWORD *)(a3 + 20) = *(_DWORD *)(a2 + 316);
  *(_DWORD *)(a3 + 24) = *(_DWORD *)(a2 + 328);
  *(_DWORD *)(a3 + 28) = *(_DWORD *)(a2 + 720);
  *(_DWORD *)(a3 + 32) = *(_DWORD *)(a2 + 724);
  *(_DWORD *)(a3 + 36) = *(_DWORD *)(a2 + 844);
  result = *(unsigned int *)(a2 + 848);
  *(_DWORD *)(a3 + 40) = result;
  if ( (byte_18002BD1A & 8) != 0 )
  {
    v9 = &v11;
    LOWORD(v12) = 0;
    if ( v6 != -48 )
      LODWORD(v9) = v6 + 48;
    return McTemplateU0zjzz_EventWriteTransfer(
             (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
             (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
             (unsigned int)L"Leaving: CopyAddrFamilyInfo",
             (_DWORD)v9,
             0,
             (__int64)&v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800080a4  mov     [rsp-18h+arg_8], rbx
0x1800080a9  mov     [rsp-18h+arg_18], rsi
0x1800080ae  push    rbp
0x1800080af  push    rdi
0x1800080b0  push    r14
0x1800080b2  mov     rbp, rsp
0x1800080b5  sub     rsp, 80h
0x1800080bc  mov     rax, cs:__security_cookie
0x1800080c3  xor     rax, rsp
0x1800080c6  mov     [rbp+var_10], rax
0x1800080ca  xorps   xmm0, xmm0
0x1800080cd  mov     qword ptr [rbp+uliInst], 0
0x1800080d5  xor     eax, eax
0x1800080d7  mov     rbx, r8
0x1800080da  mov     rdi, rdx
0x1800080dd  mov     [rbp+var_38], eax
0x1800080e0  lea     r8, [rbp+uliInst]; uliInst
0x1800080e4  mov     [rbp+var_14], eax
0x1800080e7  xor     edx, edx; lpPropSv
0x1800080e9  movzx   r14d, cx
0x1800080ed  movups  [rbp+var_34], xmm0
0x1800080f1  movups  [rbp+var_24], xmm0
0x1800080f5  movups  [rbp+var_48], xmm0
0x1800080f9  call    GetInstance
0x1800080fe  test    cs:byte_18002BD1A, 8
0x180008105  mov     rsi, qword ptr [rbp+uliInst]
0x180008109  jz      short loc_18000814C
0x18000810b  xor     eax, eax
0x18000810d  lea     r9, [rbp+var_48]
0x180008111  mov     word ptr [rbp+var_38], ax
0x180008115  lea     r8, aEnteredCopyadd; "Entered: CopyAddrFamilyInfo"
0x18000811c  lea     rax, [rsi+30h]
0x180008120  test    rax, rax
0x180008123  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x18000812a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008131  cmovnz  r9, rax
0x180008135  lea     rax, [rbp+var_38]
0x180008139  mov     [rsp+80h+var_58], rax
0x18000813e  mov     [rsp+80h+var_60], 0
0x180008147  call    McTemplateU0zjzz_EventWriteTransfer
0x18000814c  mov     [rbx], r14w
0x180008150  movzx   eax, word ptr [rdi+4]
0x180008154  mov     [rbx+2], ax
0x180008158  mov     eax, [rdi+28h]
0x18000815b  mov     [rbx+4], eax
0x18000815e  mov     eax, [rdi+130h]
0x180008164  mov     [rbx+8], eax
0x180008167  mov     eax, [rdi+134h]
0x18000816d  mov     [rbx+0Ch], eax
0x180008170  mov     eax, [rdi+138h]
0x180008176  mov     [rbx+10h], eax
0x180008179  mov     eax, [rdi+13Ch]
0x18000817f  mov     [rbx+14h], eax
0x180008182  mov     eax, [rdi+148h]
0x180008188  mov     [rbx+18h], eax
0x18000818b  mov     eax, [rdi+2D0h]
0x180008191  mov     [rbx+1Ch], eax
0x180008194  mov     eax, [rdi+2D4h]
0x18000819a  mov     [rbx+20h], eax
0x18000819d  mov     eax, [rdi+34Ch]
0x1800081a3  mov     [rbx+24h], eax
0x1800081a6  mov     eax, [rdi+350h]
0x1800081ac  mov     [rbx+28h], eax
0x1800081af  test    cs:byte_18002BD1A, 8
0x1800081b6  jz      short loc_1800081F9
0x1800081b8  xor     eax, eax
0x1800081ba  lea     r9, [rbp+var_48]
0x1800081be  mov     word ptr [rbp+var_38], ax
0x1800081c2  lea     r8, aLeavingCopyadd; "Leaving: CopyAddrFamilyInfo"
0x1800081c9  lea     rax, [rsi+30h]
0x1800081cd  test    rax, rax
0x1800081d0  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x1800081d7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800081de  cmovnz  r9, rax
0x1800081e2  lea     rax, [rbp+var_38]
0x1800081e6  mov     [rsp+80h+var_58], rax
0x1800081eb  mov     [rsp+80h+var_60], 0
0x1800081f4  call    McTemplateU0zjzz_EventWriteTransfer
0x1800081f9  mov     rcx, [rbp+var_10]
0x1800081fd  xor     rcx, rsp; StackCookie
0x180008200  call    __security_check_cookie
0x180008205  lea     r11, [rsp+80h+var_s0]
0x18000820d  mov     rbx, [r11+28h]
0x180008211  mov     rsi, [r11+38h]
0x180008215  mov     rsp, r11
0x180008218  pop     r14
0x18000821a  pop     rdi
0x18000821b  pop     rbp
0x18000821c  retn
```
