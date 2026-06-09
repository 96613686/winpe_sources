# EncodingStream::switchEncodingAt(Encoding *,int)

- ea: `0x180038a28`
- end: `0x180038c37`
- name: `?switchEncodingAt@EncodingStream@@QEAAJPEAVEncoding@@H@Z`
- size: `527`
- prototype: `__int64 __fastcall(EncodingStream *__hidden this, struct Encoding *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800397b4`

## callees

- `0x180038a28`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180038aed`
- `ntdll!RtlCompareUnicodeString` at `0x180038aed`

## pseudocode

```c
__int64 __fastcall EncodingStream::switchEncodingAt(EncodingStream *this, struct Encoding *a2, int a3)
{
  int v4; // r15d
  WCHAR *v6; // r14
  int i; // r12d
  __int64 v8; // rax
  __int64 v9; // r13
  __int64 v10; // rax
  WCHAR *v11; // rcx
  int v12; // r14d
  int (*v13)(unsigned int *, unsigned int, unsigned __int8 *, unsigned int *, unsigned __int16 *, unsigned int *); // r12
  void (__fastcall **v15)(struct Encoding *, __int64); // rax
  void (__fastcall ***v16)(_QWORD, __int64); // rcx
  int v17; // r13d
  UNICODE_STRING String2; // [rsp+20h] [rbp-58h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-48h] BYREF

  v4 = a3 - *((_DWORD *)this + 13);
  if ( v4 < 0 || v4 > *((_DWORD *)this + 11) )
  {
    if ( a2 )
    {
      v15 = *(void (__fastcall ***)(struct Encoding *, __int64))a2;
LABEL_22:
      (*v15)(a2, 1);
    }
    return 2147942487LL;
  }
  else
  {
    v6 = (WCHAR *)*((_QWORD *)a2 + 1);
    for ( i = 2; ; --i )
    {
      if ( i < 0 )
      {
        v15 = *(void (__fastcall ***)(struct Encoding *, __int64))a2;
        goto LABEL_22;
      }
      *(_QWORD *)&String1.Length = 0;
      String1.Buffer = v6;
      v8 = -1;
      String2 = 0;
      do
        ++v8;
      while ( v6[v8] );
      v9 = 32LL * i;
      String1.Length = 2 * v8;
      String1.MaximumLength = 2 * v8;
      v10 = -1;
      v11 = *(WCHAR **)((char *)&CharEncoder::charsetInfo + v9 + 8);
      String2.Buffer = v11;
      do
        ++v10;
      while ( v11[v10] );
      String2.Length = 2 * v10;
      String2.MaximumLength = 2 * v10;
      if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
        break;
    }
    v12 = *((_DWORD *)&CharEncoder::charsetInfo + 8 * i);
    if ( v12 == 1200 )
    {
      v13 = (int (*)(unsigned int *, unsigned int, unsigned __int8 *, unsigned int *, unsigned __int16 *, unsigned int *))CharEncoder::wideCharFromUcs2Bigendian;
      if ( *((_BYTE *)a2 + 16) )
        v13 = CharEncoder::wideCharFromUcs2Littleendian;
    }
    else
    {
      v13 = (int (*)(unsigned int *, unsigned int, unsigned __int8 *, unsigned int *, unsigned __int16 *, unsigned int *))*((_QWORD *)&CharEncoder::charsetInfo + 4 * i + 3);
    }
    if ( *((_DWORD *)this + 4) == v12 )
    {
      (**(void (__fastcall ***)(struct Encoding *, __int64))a2)(a2, 1);
      return 0;
    }
    if ( *((_DWORD *)this + 4) == 1200 )
    {
      if ( v12 != 1200 )
        goto LABEL_25;
    }
    else if ( v12 == 1200 )
    {
LABEL_25:
      (**(void (__fastcall ***)(struct Encoding *, __int64))a2)(a2, 1);
      return 2147500037LL;
    }
    if ( *((_DWORD *)this + 4) == 65001 && v12 != 65001 && *((_BYTE *)this + 83) )
      goto LABEL_25;
    v16 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 3);
    v17 = *(_DWORD *)((char *)&CharEncoder::charsetInfo + v9 + 16);
    if ( v16 )
      (**v16)(v16, 1);
    *((_QWORD *)this + 3) = a2;
    *((_DWORD *)this + 16) = v17;
    *((_DWORD *)this + 4) = v12;
    *((_QWORD *)this + 7) = v13;
    if ( *((_DWORD *)this + 11) == v4 )
      return 0;
    *((_DWORD *)this + 11) = v4;
    return 1;
  }
}

```

## disassembly

```asm
0x180038a28  mov     [rsp+arg_10], rbx
0x180038a2d  mov     [rsp+arg_18], rbp
0x180038a32  push    rdi
0x180038a33  push    r12
0x180038a35  push    r13
0x180038a37  push    r14
0x180038a39  push    r15
0x180038a3b  sub     rsp, 50h
0x180038a3f  mov     rax, cs:__security_cookie
0x180038a46  xor     rax, rsp
0x180038a49  mov     [rsp+78h+var_38], rax
0x180038a4e  mov     r15d, r8d
0x180038a51  mov     rbx, rdx
0x180038a54  sub     r15d, [rcx+34h]
0x180038a58  mov     rdi, rcx
0x180038a5b  js      loc_180038B69
0x180038a61  cmp     r15d, [rcx+2Ch]
0x180038a65  jg      loc_180038B69
0x180038a6b  mov     r14, [rdx+8]
0x180038a6f  xor     ebp, ebp
0x180038a71  lea     r12d, [rbp+2]
0x180038a75  lea     rcx, ?charsetInfo@CharEncoder@@0QBUEncodingEntry@@B; EncodingEntry const near * const CharEncoder::charsetInfo
0x180038a7c  test    r12d, r12d
0x180038a7f  js      loc_180038B93
0x180038a85  xorps   xmm0, xmm0
0x180038a88  xorps   xmm1, xmm1
0x180038a8b  movups  xmmword ptr [rsp+78h+String1.Length], xmm0
0x180038a90  mov     [rsp+78h+String1.Buffer], r14
0x180038a95  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038a99  movups  xmmword ptr [rsp+78h+String2.Length], xmm1
0x180038a9e  inc     rax
0x180038aa1  cmp     [r14+rax*2], bp
0x180038aa6  jnz     short loc_180038A9E
0x180038aa8  add     ax, ax
0x180038aab  movsxd  r13, r12d
0x180038aae  shl     r13, 5
0x180038ab2  mov     [rsp+78h+String1.Length], ax
0x180038ab7  mov     [rsp+78h+String1.MaximumLength], ax
0x180038abc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038ac0  mov     rcx, [rcx+r13+8]
0x180038ac5  mov     [rsp+78h+String2.Buffer], rcx
0x180038aca  inc     rax
0x180038acd  cmp     [rcx+rax*2], bp
0x180038ad1  jnz     short loc_180038ACA
0x180038ad3  add     ax, ax
0x180038ad6  lea     rdx, [rsp+78h+String2]; String2
0x180038adb  mov     r8b, 1; CaseInsensitive
0x180038ade  mov     [rsp+78h+String2.Length], ax
0x180038ae3  lea     rcx, [rsp+78h+String1]; String1
0x180038ae8  mov     [rsp+78h+String2.MaximumLength], ax
0x180038aed  call    cs:__imp_RtlCompareUnicodeString
0x180038af4  nop     dword ptr [rax+rax+00h]
0x180038af9  test    eax, eax
0x180038afb  jz      short loc_180038B05
0x180038afd  dec     r12d
0x180038b00  jmp     loc_180038A75
0x180038b05  lea     rdx, ?charsetInfo@CharEncoder@@0QBUEncodingEntry@@B; EncodingEntry const near * const CharEncoder::charsetInfo
0x180038b0c  mov     ecx, 4B0h
0x180038b11  mov     r14d, [rdx+r13]
0x180038b15  cmp     r14d, ecx
0x180038b18  jz      short loc_180038B7B
0x180038b1a  movsxd  rax, r12d
0x180038b1d  shl     rax, 5
0x180038b21  mov     r12, [rax+rdx+18h]
0x180038b26  cmp     [rdi+10h], r14d
0x180038b2a  jnz     short loc_180038BA8
0x180038b2c  mov     rax, [rbx]
0x180038b2f  mov     edx, 1
0x180038b34  mov     rcx, rbx
0x180038b37  mov     rax, [rax]
0x180038b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b3f  xor     eax, eax
0x180038b41  mov     rcx, [rsp+78h+var_38]
0x180038b46  xor     rcx, rsp; StackCookie
0x180038b49  call    __security_check_cookie
0x180038b4e  lea     r11, [rsp+78h+var_28]
0x180038b53  mov     rbx, [r11+40h]
0x180038b57  mov     rbp, [r11+48h]
0x180038b5b  mov     rsp, r11
0x180038b5e  pop     r15
0x180038b60  pop     r14
0x180038b62  pop     r13
0x180038b64  pop     r12
0x180038b66  pop     rdi
0x180038b67  retn
0x180038b69  xor     ebp, ebp
0x180038b6b  test    rbx, rbx
0x180038b6e  jnz     loc_180038C2F
0x180038b74  mov     eax, 80070057h
0x180038b79  jmp     short loc_180038B41
0x180038b7b  cmp     [rbx+10h], bpl
0x180038b7f  lea     r12, ?wideCharFromUcs2Bigendian@CharEncoder@@SAJPEAKIPEAEPEAIPEAG2@Z; CharEncoder::wideCharFromUcs2Bigendian(ulong *,uint,uchar *,uint *,ushort *,uint *)
0x180038b86  lea     rax, ?wideCharFromUcs2Littleendian@CharEncoder@@SAJPEAKIPEAEPEAIPEAG2@Z; CharEncoder::wideCharFromUcs2Littleendian(ulong *,uint,uchar *,uint *,ushort *,uint *)
0x180038b8d  cmovnz  r12, rax
0x180038b91  jmp     short loc_180038B26
0x180038b93  mov     rax, [rbx]
0x180038b96  mov     rax, [rax]
0x180038b99  mov     edx, 1
0x180038b9e  mov     rcx, rbx
0x180038ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ba6  jmp     short loc_180038B74
0x180038ba8  cmp     [rdi+10h], ecx
0x180038bab  jz      short loc_180038BCF
0x180038bad  cmp     r14d, ecx
0x180038bb0  jnz     short loc_180038BD4
0x180038bb2  mov     rax, [rbx]
0x180038bb5  mov     edx, 1
0x180038bba  mov     rcx, rbx
0x180038bbd  mov     rax, [rax]
0x180038bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bc5  mov     eax, 80004005h
0x180038bca  jmp     loc_180038B41
0x180038bcf  cmp     r14d, ecx
0x180038bd2  jnz     short loc_180038BB2
0x180038bd4  mov     eax, 0FDE9h
0x180038bd9  cmp     [rdi+10h], eax
0x180038bdc  jnz     short loc_180038BE9
0x180038bde  cmp     r14d, eax
0x180038be1  jz      short loc_180038BE9
0x180038be3  cmp     [rdi+53h], bpl
0x180038be7  jnz     short loc_180038BB2
0x180038be9  mov     rcx, [rdi+18h]
0x180038bed  mov     r13d, [rdx+r13+10h]
0x180038bf2  test    rcx, rcx
0x180038bf5  jz      short loc_180038C07
0x180038bf7  mov     rax, [rcx]
0x180038bfa  mov     edx, 1
0x180038bff  mov     rax, [rax]
0x180038c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c07  mov     [rdi+18h], rbx
0x180038c0b  mov     [rdi+40h], r13d
0x180038c0f  mov     [rdi+10h], r14d
0x180038c13  mov     [rdi+38h], r12
0x180038c17  cmp     [rdi+2Ch], r15d
0x180038c1b  jz      loc_180038B3F
0x180038c21  mov     [rdi+2Ch], r15d
0x180038c25  mov     eax, 1
0x180038c2a  jmp     loc_180038B41
0x180038c2f  mov     rax, [rdx]
0x180038c32  jmp     loc_180038B96
```
