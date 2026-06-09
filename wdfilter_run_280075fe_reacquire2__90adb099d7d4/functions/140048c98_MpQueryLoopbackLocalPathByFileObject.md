# MpQueryLoopbackLocalPathByFileObject

- ea: `0x140048c98`
- end: `0x140048ef9`
- name: `MpQueryLoopbackLocalPathByFileObject`
- size: `609`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x140040680`
- `0x140046090`
- `0x1400484fc`

## callees

- `0x1400026c0`
- `0x1400051bc`
- `0x1400118d0`
- `0x140038710`
- `0x140048c98`
- `0x140048efc`
- `0x140066180`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140048dd3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140048dd3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140048d6e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140048d6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048eba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048eba`

## pseudocode

```c
__int64 __fastcall MpQueryLoopbackLocalPathByFileObject(
        __int64 a1,
        __int64 a2,
        struct _UNICODE_STRING **a3,
        _QWORD *a4)
{
  int LoopbackEa; // eax
  char *v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rbp
  USHORT Length; // bx
  struct _UNICODE_STRING *PoolWithTag; // rax
  struct _UNICODE_STRING *v12; // rdi
  __int16 v13; // ax
  int v14; // r8d
  PVOID P[2]; // [rsp+30h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-58h] BYREF

  P[0] = 0;
  if ( !a1 || !a2 || !a3 )
    return 3221225485LL;
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  LoopbackEa = MpQueryLoopbackEa(a1, a2, P);
  v7 = (char *)P[0];
  v8 = LoopbackEa;
  if ( LoopbackEa >= 0 )
  {
    v9 = *((unsigned __int8 *)P[0] + 5);
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)((char *)P[0] + v9 + 21));
    Length = DestinationString.Length;
    if ( !DestinationString.Length || (DestinationString.Length & 1) != 0 )
    {
      v8 = -1073741811;
    }
    else
    {
      PoolWithTag = (struct _UNICODE_STRING *)MpAllocatePoolWithTag(1, DestinationString.Length + 18LL, 1937076301);
      v12 = PoolWithTag;
      if ( PoolWithTag )
      {
        PoolWithTag->Buffer = &PoolWithTag[1].Length;
        PoolWithTag->Length = 0;
        PoolWithTag->MaximumLength = Length + 2;
        RtlCopyUnicodeString(PoolWithTag, &DestinationString);
        *a3 = v12;
        if ( a4 )
        {
          v13 = *(_WORD *)&v7[v9 + 17];
          *(struct _UNICODE_STRING *)P = DestinationString;
          LOWORD(P[0]) = v13;
          v14 = MpDuplicateString((PCUNICODE_STRING)P);
          if ( v14 < 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              12,
              WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids,
              KeGetCurrentThread(),
              v14);
          }
        }
        v8 = 0;
        goto LABEL_24;
      }
      v8 = -1073741670;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids,
        KeGetCurrentThread(),
        v8);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids,
      KeGetCurrentThread(),
      LoopbackEa);
  }
LABEL_24:
  if ( v7 )
    ExFreePoolWithTag(v7, 0x6165504Du);
  return v8;
}

```

## disassembly

```asm
0x140048c98  push    rbx
0x140048c9a  push    rbp
0x140048c9b  push    rsi
0x140048c9c  push    rdi
0x140048c9d  push    r12
0x140048c9f  push    r14
0x140048ca1  push    r15
0x140048ca3  sub     rsp, 60h
0x140048ca7  mov     rax, cs:__security_cookie
0x140048cae  xor     rax, rsp
0x140048cb1  mov     [rsp+98h+var_48], rax
0x140048cb6  xor     r12d, r12d
0x140048cb9  mov     r14, r9
0x140048cbc  mov     [rsp+98h+P], r12
0x140048cc1  mov     r15, r8
0x140048cc4  mov     edi, r12d
0x140048cc7  test    rcx, rcx
0x140048cca  jz      loc_140048ED7
0x140048cd0  test    rdx, rdx
0x140048cd3  jz      loc_140048ED7
0x140048cd9  test    r8, r8
0x140048cdc  jz      loc_140048ED7
0x140048ce2  mov     [r8], r12
0x140048ce5  test    r9, r9
0x140048ce8  jz      short loc_140048CED
0x140048cea  mov     [r9], r12
0x140048ced  lea     r8, [rsp+98h+P]
0x140048cf2  call    MpQueryLoopbackEa
0x140048cf7  mov     rsi, [rsp+98h+P]
0x140048cfc  mov     ebx, eax
0x140048cfe  test    eax, eax
0x140048d00  jns     short loc_140048D56
0x140048d02  mov     rcx, cs:WPP_GLOBAL_Control
0x140048d09  lea     rax, WPP_GLOBAL_Control
0x140048d10  cmp     rcx, rax
0x140048d13  jz      loc_140048EAD
0x140048d19  mov     ecx, [rcx+2Ch]
0x140048d1c  test    cl, 1
0x140048d1f  jz      loc_140048EAD
0x140048d25  lfence
0x140048d28  mov     r9, gs:188h
0x140048d31  lea     r8, WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids
0x140048d38  mov     rcx, cs:WPP_GLOBAL_Control
0x140048d3f  mov     edx, 0Ah
0x140048d44  mov     [rsp+98h+var_78], ebx
0x140048d48  mov     rcx, [rcx+18h]
0x140048d4c  call    WPP_SF_qD
0x140048d51  jmp     loc_140048EAD
0x140048d56  movzx   ebp, byte ptr [rsi+5]
0x140048d5a  lea     rdx, [rsi+15h]
0x140048d5e  xorps   xmm0, xmm0
0x140048d61  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x140048d66  add     rdx, rbp; SourceString
0x140048d69  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x140048d6e  call    cs:__imp_RtlInitUnicodeString
0x140048d75  nop     dword ptr [rax+rax+00h]
0x140048d7a  movzx   ebx, [rsp+98h+DestinationString.Length]
0x140048d7f  test    bx, bx
0x140048d82  jz      loc_140048E60
0x140048d88  test    bl, 1
0x140048d8b  jnz     loc_140048E60
0x140048d91  lea     rdx, [rbx+12h]
0x140048d95  mov     ecx, 1
0x140048d9a  mov     r8d, 7375704Dh
0x140048da0  call    MpAllocatePoolWithTag
0x140048da5  mov     rdi, rax
0x140048da8  test    rax, rax
0x140048dab  jnz     short loc_140048DB7
0x140048dad  mov     ebx, 0C000009Ah
0x140048db2  jmp     loc_140048E65
0x140048db7  add     rax, 10h
0x140048dbb  lea     rdx, [rsp+98h+DestinationString]; SourceString
0x140048dc0  mov     [rdi+8], rax
0x140048dc4  add     bx, 2
0x140048dc8  mov     [rdi], r12w
0x140048dcc  mov     rcx, rdi; DestinationString
0x140048dcf  mov     [rdi+2], bx
0x140048dd3  call    cs:__imp_RtlCopyUnicodeString
0x140048dda  nop     dword ptr [rax+rax+00h]
0x140048ddf  mov     [r15], rdi
0x140048de2  mov     rdi, r12
0x140048de5  test    r14, r14
0x140048de8  jz      short loc_140048E5B
0x140048dea  movaps  xmm0, xmmword ptr [rsp+98h+DestinationString.Length]
0x140048def  lea     rcx, [rsp+98h+P]; SourceString
0x140048df4  movzx   eax, word ptr [rsi+rbp+11h]
0x140048df9  mov     rdx, r14
0x140048dfc  movdqa  xmmword ptr [rsp+98h+P], xmm0
0x140048e02  mov     word ptr [rsp+98h+P], ax
0x140048e07  call    MpDuplicateString
0x140048e0c  mov     r8d, eax
0x140048e0f  test    eax, eax
0x140048e11  jns     short loc_140048E5B
0x140048e13  mov     rcx, cs:WPP_GLOBAL_Control
0x140048e1a  lea     rax, WPP_GLOBAL_Control
0x140048e21  cmp     rcx, rax
0x140048e24  jz      short loc_140048E5B
0x140048e26  mov     ecx, [rcx+2Ch]
0x140048e29  test    cl, 1
0x140048e2c  jz      short loc_140048E5B
0x140048e2e  lfence
0x140048e31  mov     r9, gs:188h
0x140048e3a  mov     edx, 0Ch
0x140048e3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140048e46  mov     [rsp+98h+var_78], r8d
0x140048e4b  lea     r8, WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids
0x140048e52  mov     rcx, [rcx+18h]
0x140048e56  call    WPP_SF_qD
0x140048e5b  mov     ebx, r12d
0x140048e5e  jmp     short loc_140048EAD
0x140048e60  mov     ebx, 0C000000Dh
0x140048e65  mov     ecx, ebx
0x140048e67  mov     rdx, cs:WPP_GLOBAL_Control
0x140048e6e  lea     rax, WPP_GLOBAL_Control
0x140048e75  cmp     rdx, rax
0x140048e78  jz      short loc_140048EAD
0x140048e7a  mov     eax, [rdx+2Ch]
0x140048e7d  test    al, 1
0x140048e7f  jz      short loc_140048EAD
0x140048e81  lfence
0x140048e84  mov     r9, gs:188h
0x140048e8d  lea     r8, WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids
0x140048e94  mov     rcx, cs:WPP_GLOBAL_Control
0x140048e9b  mov     edx, 0Bh
0x140048ea0  mov     [rsp+98h+var_78], ebx
0x140048ea4  mov     rcx, [rcx+18h]
0x140048ea8  call    WPP_SF_qD
0x140048ead  test    rsi, rsi
0x140048eb0  jz      short loc_140048EC6
0x140048eb2  mov     edx, 6165504Dh; Tag
0x140048eb7  mov     rcx, rsi; P
0x140048eba  call    cs:__imp_ExFreePoolWithTag
0x140048ec1  nop     dword ptr [rax+rax+00h]
0x140048ec6  test    rdi, rdi
0x140048ec9  jz      short loc_140048ED3
0x140048ecb  mov     rcx, rdi
0x140048ece  call    MpFreeString
0x140048ed3  mov     eax, ebx
0x140048ed5  jmp     short loc_140048EDC
0x140048ed7  mov     eax, 0C000000Dh
0x140048edc  mov     rcx, [rsp+98h+var_48]
0x140048ee1  xor     rcx, rsp; StackCookie
0x140048ee4  call    __security_check_cookie
0x140048ee9  add     rsp, 60h
0x140048eed  pop     r15
0x140048eef  pop     r14
0x140048ef1  pop     r12
0x140048ef3  pop     rdi
0x140048ef4  pop     rsi
0x140048ef5  pop     rbp
0x140048ef6  pop     rbx
0x140048ef7  retn
```
