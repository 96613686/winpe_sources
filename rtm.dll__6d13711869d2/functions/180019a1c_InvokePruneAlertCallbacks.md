# InvokePruneAlertCallbacks

- ea: `0x180019a1c`
- end: `0x180019c8b`
- name: `InvokePruneAlertCallbacks`
- size: `623`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001aa4c`
- `0x18001d378`

## callees

- `0x180018dd4`
- `0x180019a1c`
- `0x18001b548`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## string_xrefs

- `0x180019b37`: `Invoked Prune Alert for protocol %x, %x`
- `0x180019bed`: `Invoked Prune Alert for protocol %x, %x`
- `0x180019ae1`: `InvokePruneAlertCallbacks : Could not find protocol (%x, %x)`

## pseudocode

```c
__int64 __fastcall InvokePruneAlertCallbacks(__int64 a1, __int64 a2, int a3, int a4, __int64 a5)
{
  int v9; // ecx
  __int64 result; // rax
  __int64 v11; // r11
  __int64 v12; // rbx
  __int64 i; // rbx
  int v14; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v9 = *(_DWORD *)(a2 + 104);
  result = *(unsigned int *)(a2 + 40);
  if ( v9 )
  {
    if ( !(_DWORD)result )
      return AddToOutstandingJoinList(v9, *(_DWORD *)(a2 + 108), *(_DWORD *)(a1 + 32), *(_DWORD *)(a1 + 36), a3, a4, 0);
  }
  else if ( (_DWORD)result == 1 )
  {
    result = GetProtocolEntry(
               &qword_18002B9A8,
               *(unsigned int *)(*(_QWORD *)(a2 + 48) + 24LL),
               *(unsigned int *)(*(_QWORD *)(a2 + 48) + 28LL));
    v12 = result;
    if ( result )
    {
      if ( *(_QWORD *)(result + 56) )
      {
        if ( qword_18002B8A8 )
        {
          LOWORD(v14) = 0;
          FormatRRASErrorString(
            &v14,
            L"Invoked Prune Alert for protocol %x, %x",
            *(unsigned int *)(result + 16),
            *(unsigned int *)(result + 20));
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v14);
        }
        return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, int, int, _QWORD))(v12 + 56))(
                 *(unsigned int *)(a2 + 104),
                 *(unsigned int *)(a2 + 108),
                 *(unsigned int *)(a1 + 32),
                 *(unsigned int *)(a1 + 36),
                 a3,
                 a4,
                 1,
                 0);
      }
    }
    else if ( qword_18002B8A8 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(
        &v14,
        L"InvokePruneAlertCallbacks : Could not find protocol (%x, %x)",
        *(unsigned int *)(v11 + 24),
        *(unsigned int *)(v11 + 28));
      return ((__int64 (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v14);
    }
  }
  else if ( !(_DWORD)result )
  {
    for ( i = qword_18002B9A8; (__int64 *)i != &qword_18002B9A8; i = *(_QWORD *)i )
    {
      result = *(unsigned int *)(a5 + 16);
      if ( *(_DWORD *)(i + 16) == (_DWORD)result )
      {
        result = *(unsigned int *)(a5 + 20);
        if ( *(_DWORD *)(i + 20) == (_DWORD)result )
          continue;
      }
      if ( *(_QWORD *)(i + 56) )
      {
        if ( qword_18002B8A8 )
        {
          LOWORD(v14) = 0;
          FormatRRASErrorString(
            &v14,
            L"Invoked Prune Alert for protocol %x, %x",
            *(unsigned int *)(i + 16),
            *(unsigned int *)(i + 20));
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v14);
        }
        result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, int, int, _QWORD))(i + 56))(
                   *(unsigned int *)(a2 + 104),
                   *(unsigned int *)(a2 + 108),
                   *(unsigned int *)(a1 + 32),
                   *(unsigned int *)(a1 + 36),
                   a3,
                   a4,
                   1,
                   0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019a1c  push    rbp
0x180019a1e  push    rbx
0x180019a1f  push    rsi
0x180019a20  push    rdi
0x180019a21  push    r12
0x180019a23  push    r13
0x180019a25  push    r14
0x180019a27  push    r15
0x180019a29  lea     rbp, [rsp-768h]
0x180019a31  sub     rsp, 868h
0x180019a38  mov     rax, cs:__security_cookie
0x180019a3f  xor     rax, rsp
0x180019a42  mov     [rbp+7A0h+var_50], rax
0x180019a49  mov     r12d, r8d
0x180019a4c  mov     rdi, rdx
0x180019a4f  mov     rsi, rcx
0x180019a52  xor     r15d, r15d
0x180019a55  xor     edx, edx; Val
0x180019a57  mov     [rsp+8A0h+var_850], r15d
0x180019a5c  mov     r8d, 7FCh; Size
0x180019a62  lea     rcx, [rsp+8A0h+var_84C]; void *
0x180019a67  mov     r13d, r9d
0x180019a6a  call    memset_0
0x180019a6f  mov     ecx, [rdi+68h]
0x180019a72  mov     eax, [rdi+28h]
0x180019a75  test    ecx, ecx
0x180019a77  jz      short loc_180019AA5
0x180019a79  test    eax, eax
0x180019a7b  jnz     loc_180019C68
0x180019a81  mov     r9d, [rsi+24h]
0x180019a85  mov     r8d, [rsi+20h]
0x180019a89  mov     edx, [rdi+6Ch]
0x180019a8c  mov     [rsp+8A0h+var_870], r15d
0x180019a91  mov     [rsp+8A0h+var_878], r13d
0x180019a96  mov     [rsp+8A0h+var_880], r12d
0x180019a9b  call    AddToOutstandingJoinList
0x180019aa0  jmp     loc_180019C68
0x180019aa5  cmp     eax, 1
0x180019aa8  jnz     loc_180019BA2
0x180019aae  mov     r11, [rdi+30h]
0x180019ab2  lea     rcx, qword_18002B9A8
0x180019ab9  mov     r8d, [r11+1Ch]
0x180019abd  mov     edx, [r11+18h]
0x180019ac1  call    GetProtocolEntry
0x180019ac6  mov     rbx, rax
0x180019ac9  test    rax, rax
0x180019acc  jnz     short loc_180019B1E
0x180019ace  cmp     cs:qword_18002B8A8, r15
0x180019ad5  jz      loc_180019C68
0x180019adb  mov     word ptr [rsp+8A0h+var_850], r15w
0x180019ae1  lea     rdx, aInvokepruneale; "InvokePruneAlertCallbacks : Could not f"...
0x180019ae8  mov     r9d, [r11+1Ch]
0x180019aec  lea     rcx, [rsp+8A0h+var_850]
0x180019af1  mov     r8d, [r11+18h]
0x180019af5  call    FormatRRASErrorString
0x180019afa  mov     rdx, cs:qword_18002B8A8
0x180019b01  lea     r8, [rsp+8A0h+var_850]
0x180019b06  mov     rcx, cs:gMgmEtwContext
0x180019b0d  mov     rax, cs:gMgmTemplateFunc
0x180019b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b19  jmp     loc_180019C68
0x180019b1e  cmp     [rax+38h], r15
0x180019b22  jz      loc_180019C68
0x180019b28  cmp     cs:qword_18002B8A8, r15
0x180019b2f  jz      short loc_180019B6F
0x180019b31  mov     word ptr [rsp+8A0h+var_850], r15w
0x180019b37  lea     rdx, aInvokedPruneAl; "Invoked Prune Alert for protocol %x, %x"
0x180019b3e  mov     r9d, [rax+14h]
0x180019b42  lea     rcx, [rsp+8A0h+var_850]
0x180019b47  mov     r8d, [rax+10h]
0x180019b4b  call    FormatRRASErrorString
0x180019b50  mov     rdx, cs:qword_18002B8A8
0x180019b57  lea     r8, [rsp+8A0h+var_850]
0x180019b5c  mov     rcx, cs:gMgmEtwContext
0x180019b63  mov     rax, cs:gMgmTemplateFunc
0x180019b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b6f  mov     r9d, [rsi+24h]
0x180019b73  mov     r8d, [rsi+20h]
0x180019b77  mov     edx, [rdi+6Ch]
0x180019b7a  mov     ecx, [rdi+68h]
0x180019b7d  mov     rax, [rbx+38h]
0x180019b81  mov     [rsp+8A0h+var_868], r15
0x180019b86  mov     [rsp+8A0h+var_870], 1
0x180019b8e  mov     [rsp+8A0h+var_878], r13d
0x180019b93  mov     [rsp+8A0h+var_880], r12d
0x180019b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b9d  jmp     loc_180019C68
0x180019ba2  test    eax, eax
0x180019ba4  jnz     loc_180019C68
0x180019baa  mov     r15, [rbp+7A0h+arg_20]
0x180019bb1  lea     r14, qword_18002B9A8
0x180019bb8  mov     rbx, cs:qword_18002B9A8
0x180019bbf  jmp     loc_180019C5F
0x180019bc4  mov     eax, [r15+10h]
0x180019bc8  cmp     [rbx+10h], eax
0x180019bcb  jnz     short loc_180019BDA
0x180019bcd  mov     eax, [r15+14h]
0x180019bd1  cmp     [rbx+14h], eax
0x180019bd4  jz      loc_180019C5C
0x180019bda  cmp     qword ptr [rbx+38h], 0
0x180019bdf  jz      short loc_180019C5C
0x180019be1  cmp     cs:qword_18002B8A8, 0
0x180019be9  jz      short loc_180019C2A
0x180019beb  xor     eax, eax
0x180019bed  lea     rdx, aInvokedPruneAl; "Invoked Prune Alert for protocol %x, %x"
0x180019bf4  mov     word ptr [rsp+8A0h+var_850], ax
0x180019bf9  lea     rcx, [rsp+8A0h+var_850]
0x180019bfe  mov     r9d, [rbx+14h]
0x180019c02  mov     r8d, [rbx+10h]
0x180019c06  call    FormatRRASErrorString
0x180019c0b  mov     rdx, cs:qword_18002B8A8
0x180019c12  lea     r8, [rsp+8A0h+var_850]
0x180019c17  mov     rcx, cs:gMgmEtwContext
0x180019c1e  mov     rax, cs:gMgmTemplateFunc
0x180019c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c2a  mov     r9d, [rsi+24h]
0x180019c2e  mov     r8d, [rsi+20h]
0x180019c32  mov     edx, [rdi+6Ch]
0x180019c35  mov     ecx, [rdi+68h]
0x180019c38  mov     rax, [rbx+38h]
0x180019c3c  mov     [rsp+8A0h+var_868], 0
0x180019c45  mov     [rsp+8A0h+var_870], 1
0x180019c4d  mov     [rsp+8A0h+var_878], r13d
0x180019c52  mov     [rsp+8A0h+var_880], r12d
0x180019c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c5c  mov     rbx, [rbx]
0x180019c5f  cmp     rbx, r14
0x180019c62  jnz     loc_180019BC4
0x180019c68  mov     rcx, [rbp+7A0h+var_50]
0x180019c6f  xor     rcx, rsp; StackCookie
0x180019c72  call    __security_check_cookie
0x180019c77  add     rsp, 868h
0x180019c7e  pop     r15
0x180019c80  pop     r14
0x180019c82  pop     r13
0x180019c84  pop     r12
0x180019c86  pop     rdi
0x180019c87  pop     rsi
0x180019c88  pop     rbx
0x180019c89  pop     rbp
0x180019c8a  retn
```
