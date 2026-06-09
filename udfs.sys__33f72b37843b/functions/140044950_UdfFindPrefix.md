# UdfFindPrefix

- ea: `0x140044950`
- end: `0x140044f87`
- name: `UdfFindPrefix`
- size: `1591`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PUNICODE_STRING DestinationString, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140042c40`

## callees

- `0x140009148`
- `0x14000cad4`
- `0x14001bd80`
- `0x14002fac4`
- `0x14003803c`
- `0x140044950`
- `0x140045f10`
- `0x14004ce50`
- `0x140056040`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140044d5d`
- `ntoskrnl!ExRaiseStatus` at `0x140044f7a`
- `ntoskrnl!ExRaiseStatus` at `0x140044d5d`
- `ntoskrnl!ExRaiseStatus` at `0x140044f7a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044ba0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044e92`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044ba0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044e92`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140044b7d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140044b7d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140044e30`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140044eca`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140044e30`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140044eca`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140044e77`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140044f11`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140044e77`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140044f11`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140044a3f`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140044a3f`
- `ntoskrnl!RtlCompareMemory` at `0x140044ace`
- `ntoskrnl!RtlCompareMemory` at `0x140044ca4`
- `ntoskrnl!RtlCompareMemory` at `0x140044ace`
- `ntoskrnl!RtlCompareMemory` at `0x140044ca4`
- `ntoskrnl!RtlSplay` at `0x140044b2c`
- `ntoskrnl!RtlSplay` at `0x140044d07`
- `ntoskrnl!RtlSplay` at `0x140044b2c`
- `ntoskrnl!RtlSplay` at `0x140044d07`

## pseudocode

```c
__int64 __fastcall UdfFindPrefix(
        __int64 a1,
        char a2,
        __int64 *a3,
        __int64 *a4,
        UNICODE_STRING *a5,
        PUNICODE_STRING DestinationString,
        _BYTE *a7)
{
  UNICODE_STRING *v7; // rsi
  __int64 v8; // r13
  __int64 v9; // r15
  __int64 v10; // rbx
  unsigned __int16 Length; // dx
  char *Buffer; // r8
  WCHAR *v13; // rdi
  char v14; // r12
  unsigned int i; // ebx
  unsigned __int16 v16; // cx
  const void *v17; // r9
  __int64 v19; // rdi
  USHORT v20; // dx
  unsigned int v21; // esi
  int v22; // ebx
  unsigned int v23; // eax
  __int64 NameLink; // rdi
  void **v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // r8
  unsigned __int64 v28; // rdx
  _WORD *v29; // r9
  __int64 v30; // rdi
  unsigned __int16 v31; // dx
  unsigned int v32; // esi
  int v33; // ebx
  unsigned int v34; // eax
  UNICODE_STRING v35; // xmm0
  void *Src[2]; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING Source2; // [rsp+30h] [rbp-18h] BYREF

  v7 = a5;
  v8 = 0;
  v9 = *a3;
  v10 = a1;
  *a7 = 0;
  *(_OWORD *)Src = 0;
  Source2 = *a5;
  do
  {
    UdfVerifyScbOperation(v10, v9, 0);
    Length = Source2.Length;
    if ( !Source2.Length )
      break;
    Buffer = (char *)Source2.Buffer;
    v13 = Source2.Buffer;
    if ( *Source2.Buffer == 58 )
    {
      v13 = Source2.Buffer + 1;
      Length = Source2.Length - 2;
      Source2.Buffer = v13;
      Source2.Length -= 2;
      v14 = 1;
      Buffer = (char *)v13;
    }
    else
    {
      v14 = 0;
    }
    for ( i = 0; i < Length; ++v13 )
    {
      if ( *v13 == 92 )
        break;
      if ( *v13 == 58 )
        break;
      i += 2;
    }
    WORD1(Src[0]) = i;
    v16 = i;
    LOWORD(Src[0]) = i;
    v17 = Buffer;
    Src[1] = Buffer;
    if ( DestinationString )
    {
      UdfEnsureStringBufferEnough((__int64)DestinationString, i);
      memmove(DestinationString->Buffer, Src[1], LOWORD(Src[0]));
      DestinationString->Length = (USHORT)Src[0];
      RtlUpcaseUnicodeString(DestinationString, DestinationString, 0);
      Buffer = (char *)Source2.Buffer;
      Length = Source2.Length;
      v17 = Src[1];
      v16 = (unsigned __int16)Src[0];
    }
    if ( i == Length )
    {
      Source2.Length = 0;
    }
    else
    {
      if ( *v13 != 58 )
        i += 2;
      Source2.MaximumLength -= i;
      Source2.Length = Length - i;
      Source2.Buffer = (PWSTR)&Buffer[i];
    }
    if ( v14 )
    {
      UdfValidateAndRemoveStreamSuffix(a1, Src, &Source2);
      v16 = (unsigned __int16)Src[0];
      if ( !LOWORD(Src[0]) )
      {
        v7->Length = 0;
        *a4 = 0;
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x8000) != 0 )
        {
          WPP_SF_(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            13,
            WPP_681754f669f536b2650fcdb0f5d35810_Traceguids);
        }
        return v8;
      }
      if ( (*(_DWORD *)(v9 + 212) & 0x10) != 0 )
      {
        *(_DWORD *)(a1 + 24) = -1073741811;
        ExRaiseStatus(-1073741811);
      }
      v9 = *(_QWORD *)(*(_QWORD *)(v9 + 136) + 24LL);
      if ( !v9 )
        return v8;
      v17 = Src[1];
    }
    if ( *(_WORD *)v9 != 2355 )
      return v8;
    if ( a2 )
    {
      v19 = *(_QWORD *)(v9 + 520);
      while ( v19 )
      {
        v20 = *(_WORD *)(v19 + 24);
        if ( v20 <= DestinationString->Length )
        {
          v22 = -1;
          v21 = *(unsigned __int16 *)(v19 + 24);
          if ( v20 == DestinationString->Length )
            v22 = 0;
        }
        else
        {
          v21 = DestinationString->Length;
          v22 = 1;
        }
        v23 = RtlCompareMemory(*(const void **)(v19 + 32), DestinationString->Buffer, v21);
        if ( v23 < v21 )
        {
          v22 = -1;
          if ( *(_WORD *)(2 * ((unsigned __int64)v23 >> 1) + *(_QWORD *)(v19 + 32)) >= DestinationString->Buffer[(unsigned __int64)v23 >> 1] )
            v22 = 1;
        }
        if ( v22 == 1 )
        {
          v19 = *(_QWORD *)(v19 + 8);
        }
        else
        {
          if ( v22 != -1 )
          {
            *(_QWORD *)(v9 + 520) = RtlSplay((PRTL_SPLAY_LINKS)v19);
            NameLink = v19 - 144;
            goto LABEL_31;
          }
          v19 = *(_QWORD *)(v19 + 16);
        }
      }
    }
    else
    {
      v30 = *(_QWORD *)(v9 + 512);
      while ( v30 )
      {
        v31 = *(_WORD *)(v30 + 24);
        if ( v31 <= v16 )
        {
          v33 = -1;
          v32 = *(unsigned __int16 *)(v30 + 24);
          if ( v31 == v16 )
            v33 = 0;
        }
        else
        {
          v32 = v16;
          v33 = 1;
        }
        v34 = RtlCompareMemory(*(const void **)(v30 + 32), v17, v32);
        v17 = Src[1];
        if ( v34 < v32 )
        {
          v33 = -1;
          if ( *(_WORD *)(2 * ((unsigned __int64)v34 >> 1) + *(_QWORD *)(v30 + 32)) >= *((_WORD *)Src[1]
                                                                                       + ((unsigned __int64)v34 >> 1)) )
            v33 = 1;
        }
        if ( v33 == 1 )
        {
          v30 = *(_QWORD *)(v30 + 8);
          v16 = (unsigned __int16)Src[0];
        }
        else
        {
          if ( v33 != -1 )
          {
            *(_QWORD *)(v9 + 512) = RtlSplay((PRTL_SPLAY_LINKS)v30);
            NameLink = v30 - 104;
            goto LABEL_31;
          }
          v30 = *(_QWORD *)(v30 + 16);
          v16 = (unsigned __int16)Src[0];
        }
      }
    }
    NameLink = 0;
LABEL_31:
    if ( !NameLink )
    {
      v25 = Src;
      if ( a2 )
        v25 = (void **)DestinationString;
      v26 = *(unsigned __int16 *)v25;
      if ( (unsigned __int16)(v26 - 8) <= 0x10u )
      {
        v27 = 0;
        v28 = ((unsigned __int64)*(unsigned __int16 *)v25 >> 1) - 4;
        while ( (unsigned int)v27 <= v28 )
        {
          v29 = v25[1];
          if ( v29[v27] == 35 && ((unsigned int)v27 == v28 || v29[(unsigned int)(v27 + 4)] == 46) )
          {
            if ( (*(_DWORD *)(v9 + 212) & 0x800000) == 0 )
              UdfBuildScbShortNameIndex(a1, v9);
            NameLink = UdfFindNameLink(v26, v9 + 528, v25, 184);
            if ( NameLink )
            {
              *a7 = 1;
              goto LABEL_32;
            }
            return v8;
          }
          v27 = (unsigned int)(v27 + 1);
        }
      }
      return v8;
    }
LABEL_32:
    if ( v14 && v8 )
    {
      v7 = a5;
      v35 = Source2;
      *a4 = v8;
      *a5 = v35;
    }
    else
    {
      v7 = a5;
      *a5 = Source2;
      if ( !v14 )
      {
        if ( !ExAcquireResourceExclusiveLite(
                (PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(NameLink + 48) + 136LL) + 80LL) + 8LL),
                0) )
        {
          v10 = a1;
          if ( (*(_DWORD *)(a1 + 28) & 4) == 0 )
          {
            *(_DWORD *)(a1 + 24) = -1073741608;
            ExRaiseStatus(-1073741608);
          }
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 1584LL));
          *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1640LL) = KeGetCurrentThread();
          ++*(_DWORD *)(*(_QWORD *)(NameLink + 48) + 204LL);
          ++*(_DWORD *)(NameLink + 64);
          *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1640LL) = 0;
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 1584LL));
          ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v9 + 136) + 80LL) + 8LL));
          UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(NameLink + 48) + 136LL) + 80LL) + 8LL, 0, 0);
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 1584LL));
          *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1640LL) = KeGetCurrentThread();
          --*(_DWORD *)(*(_QWORD *)(NameLink + 48) + 204LL);
          --*(_DWORD *)(NameLink + 64);
          *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1640LL) = 0;
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 1584LL));
          goto LABEL_37;
        }
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v9 + 136) + 80LL) + 8LL));
      }
    }
    v10 = a1;
LABEL_37:
    v8 = NameLink;
    v9 = *(_QWORD *)(NameLink + 48);
    *a3 = v9;
  }
  while ( (*(_DWORD *)(NameLink + 68) & 2) == 0 && *(int *)(v9 + 216) < 2 );
  return v8;
}

```

## disassembly

```asm
0x140044950  mov     [rsp-40h+arg_18], r9
0x140044955  mov     [rsp-40h+arg_10], r8
0x14004495a  mov     [rsp-40h+arg_8], dl
0x14004495e  mov     qword ptr [rsp-40h+arg_0], rcx
0x140044963  push    rbp
0x140044964  push    rbx
0x140044965  push    rsi
0x140044966  push    rdi
0x140044967  push    r12
0x140044969  push    r13
0x14004496b  push    r14
0x14004496d  push    r15
0x14004496f  mov     rbp, rsp
0x140044972  sub     rsp, 48h
0x140044976  mov     rax, [rbp+arg_30]
0x14004497a  xorps   xmm0, xmm0
0x14004497d  mov     rsi, [rbp+arg_20]
0x140044981  xor     r13d, r13d
0x140044984  mov     r15, [r8]
0x140044987  mov     rbx, rcx
0x14004498a  mov     r14, [rbp+DestinationString]
0x14004498e  mov     [rax], r13b
0x140044991  movups  xmmword ptr [rbp+Src], xmm0
0x140044995  movups  xmm0, xmmword ptr [rsi]
0x140044998  movups  xmmword ptr [rbp+Source2.Length], xmm0
0x14004499c  xor     r8d, r8d
0x14004499f  mov     rdx, r15
0x1400449a2  mov     rcx, rbx
0x1400449a5  mov     r12d, 3Ah ; ':'
0x1400449ab  call    UdfVerifyScbOperation
0x1400449b0  movzx   edx, [rbp+Source2.Length]
0x1400449b4  test    dx, dx
0x1400449b7  jz      loc_140044A80
0x1400449bd  mov     r8, [rbp+Source2.Buffer]
0x1400449c1  mov     rdi, r8
0x1400449c4  cmp     r12w, [r8]
0x1400449c8  jz      loc_140044C54
0x1400449ce  xor     r12b, r12b
0x1400449d1  xor     ebx, ebx
0x1400449d3  movzx   ecx, dx
0x1400449d6  test    ecx, ecx
0x1400449d8  jz      short loc_1400449FA
0x1400449da  nop     word ptr [rax+rax+00h]
0x1400449e0  movzx   eax, word ptr [rdi]
0x1400449e3  cmp     ax, 5Ch ; '\'
0x1400449e7  jz      short loc_1400449FA
0x1400449e9  cmp     ax, 3Ah ; ':'
0x1400449ed  jz      short loc_1400449FA
0x1400449ef  add     ebx, 2
0x1400449f2  add     rdi, 2
0x1400449f6  cmp     ebx, ecx
0x1400449f8  jb      short loc_1400449E0
0x1400449fa  mov     word ptr [rbp+Src+2], bx
0x1400449fe  movzx   ecx, bx
0x140044a01  mov     word ptr [rbp+Src], bx
0x140044a05  mov     r9, r8
0x140044a08  mov     [rbp+Src+8], r8
0x140044a0c  test    r14, r14
0x140044a0f  jz      short loc_140044A5B
0x140044a11  movzx   edx, bx
0x140044a14  mov     rcx, r14
0x140044a17  call    UdfEnsureStringBufferEnough
0x140044a1c  movzx   r8d, word ptr [rbp+Src]; Size
0x140044a21  mov     rdx, [rbp+Src+8]; Src
0x140044a25  mov     rcx, [r14+8]; void *
0x140044a29  call    memmove
0x140044a2e  movzx   eax, word ptr [rbp+Src]
0x140044a32  xor     r8d, r8d; AllocateDestinationString
0x140044a35  mov     rdx, r14; SourceString
0x140044a38  mov     [r14], ax
0x140044a3c  mov     rcx, r14; DestinationString
0x140044a3f  call    cs:__imp_RtlUpcaseUnicodeString
0x140044a46  nop     dword ptr [rax+rax+00h]
0x140044a4b  mov     r8, [rbp+Source2.Buffer]
0x140044a4f  movzx   edx, [rbp+Source2.Length]
0x140044a53  mov     r9, [rbp+Src+8]
0x140044a57  movzx   ecx, word ptr [rbp+Src]
0x140044a5b  movzx   eax, dx
0x140044a5e  cmp     ebx, eax
0x140044a60  jnz     loc_140044BDC
0x140044a66  xor     eax, eax
0x140044a68  mov     [rbp+Source2.Length], ax
0x140044a6c  test    r12b, r12b
0x140044a6f  jnz     loc_140044D23
0x140044a75  mov     eax, 933h
0x140044a7a  cmp     [r15], ax
0x140044a7e  jz      short loc_140044A95
0x140044a80  mov     rax, r13
0x140044a83  add     rsp, 48h
0x140044a87  pop     r15
0x140044a89  pop     r14
0x140044a8b  pop     r13
0x140044a8d  pop     r12
0x140044a8f  pop     rdi
0x140044a90  pop     rsi
0x140044a91  pop     rbx
0x140044a92  pop     rbp
0x140044a93  retn
0x140044a95  cmp     [rbp+arg_8], 0
0x140044a99  jz      loc_140044C73
0x140044a9f  mov     rdi, [r15+208h]
0x140044aa6  test    rdi, rdi
0x140044aa9  jz      loc_140044D6A
0x140044aaf  movzx   edx, word ptr [rdi+18h]
0x140044ab3  movzx   ecx, word ptr [r14]
0x140044ab7  cmp     dx, cx
0x140044aba  jbe     short loc_140044B18
0x140044abc  mov     esi, ecx
0x140044abe  mov     ebx, 1
0x140044ac3  mov     rdx, [r14+8]; Source2
0x140044ac7  mov     rcx, [rdi+20h]; Source1
0x140044acb  mov     r8d, esi; Length
0x140044ace  call    cs:__imp_RtlCompareMemory
0x140044ad5  nop     dword ptr [rax+rax+00h]
0x140044ada  cmp     eax, esi
0x140044adc  jnb     short loc_140044B04
0x140044ade  mov     rcx, [rdi+20h]
0x140044ae2  mov     ebx, 0FFFFFFFFh
0x140044ae7  mov     eax, eax
0x140044ae9  shr     rax, 1
0x140044aec  lea     rdx, [rax+rax]
0x140044af0  mov     rax, [r14+8]
0x140044af4  movzx   eax, word ptr [rdx+rax]
0x140044af8  cmp     [rdx+rcx], ax
0x140044afc  mov     eax, 1
0x140044b01  cmovnb  ebx, eax
0x140044b04  cmp     ebx, 1
0x140044b07  jz      loc_140044C02
0x140044b0d  cmp     ebx, 0FFFFFFFFh
0x140044b10  jnz     short loc_140044B29
0x140044b12  mov     rdi, [rdi+10h]
0x140044b16  jmp     short loc_140044AA6
0x140044b18  xor     eax, eax
0x140044b1a  mov     ebx, 0FFFFFFFFh
0x140044b1f  cmp     dx, cx
0x140044b22  mov     esi, edx
0x140044b24  cmovz   ebx, eax
0x140044b27  jmp     short loc_140044AC3
0x140044b29  mov     rcx, rdi; Links
0x140044b2c  call    cs:__imp_RtlSplay
0x140044b33  nop     dword ptr [rax+rax+00h]
0x140044b38  mov     [r15+208h], rax
0x140044b3f  add     rdi, 0FFFFFFFFFFFFFF70h
0x140044b46  test    rdi, rdi
0x140044b49  jz      loc_140044C0B
0x140044b4f  test    r12b, r12b
0x140044b52  jnz     loc_140044DF6
0x140044b58  mov     rsi, [rbp+arg_20]
0x140044b5c  movups  xmm0, xmmword ptr [rbp+Source2.Length]
0x140044b60  movups  xmmword ptr [rsi], xmm0
0x140044b63  test    r12b, r12b
0x140044b66  jnz     short loc_140044BAC
0x140044b68  mov     rax, [rdi+30h]
0x140044b6c  xor     edx, edx; Wait
0x140044b6e  mov     rcx, [rax+88h]
0x140044b75  mov     rcx, [rcx+50h]
0x140044b79  add     rcx, 8; Resource
0x140044b7d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140044b84  nop     dword ptr [rax+rax+00h]
0x140044b89  test    al, al
0x140044b8b  jz      loc_140044E16
0x140044b91  mov     rax, [r15+88h]
0x140044b98  mov     rcx, [rax+50h]
0x140044b9c  add     rcx, 8; Resource
0x140044ba0  call    cs:__imp_ExReleaseResourceLite
0x140044ba7  nop     dword ptr [rax+rax+00h]
0x140044bac  mov     rbx, qword ptr [rbp+arg_0]
0x140044bb0  mov     rax, [rbp+arg_10]
0x140044bb4  mov     r13, rdi
0x140044bb7  mov     r15, [rdi+30h]
0x140044bbb  mov     [rax], r15
0x140044bbe  mov     eax, [rdi+44h]
0x140044bc1  test    al, 2
0x140044bc3  jnz     loc_140044A80
0x140044bc9  cmp     dword ptr [r15+0D8h], 2
0x140044bd1  jl      loc_14004499C
0x140044bd7  jmp     loc_140044A80
0x140044bdc  mov     eax, 3Ah ; ':'
0x140044be1  cmp     ax, [rdi]
0x140044be4  jz      short loc_140044BE9
0x140044be6  add     ebx, 2
0x140044be9  sub     [rbp+Source2.MaximumLength], bx
0x140044bed  sub     dx, bx
0x140044bf0  mov     eax, ebx
0x140044bf2  add     r8, rax
0x140044bf5  mov     [rbp+Source2.Length], dx
0x140044bf9  mov     [rbp+Source2.Buffer], r8
0x140044bfd  jmp     loc_140044A6C
0x140044c02  mov     rdi, [rdi+8]
0x140044c06  jmp     loc_140044AA6
0x140044c0b  cmp     [rbp+arg_8], 0
0x140044c0f  lea     rbx, [rbp+Src]
0x140044c13  cmovnz  rbx, r14
0x140044c17  movzx   ecx, word ptr [rbx]
0x140044c1a  lea     eax, [rcx-8]
0x140044c1d  cmp     ax, 10h
0x140044c21  ja      loc_140044A80
0x140044c27  mov     edx, ecx
0x140044c29  xor     r8d, r8d
0x140044c2c  shr     rdx, 1
0x140044c2f  sub     rdx, 4
0x140044c33  mov     eax, r8d
0x140044c36  cmp     rax, rdx
0x140044c39  ja      loc_140044A80
0x140044c3f  mov     r9, [rbx+8]
0x140044c43  cmp     word ptr [r9+r8*2], 23h ; '#'
0x140044c49  jz      loc_140044D9B
0x140044c4f  inc     r8d
0x140044c52  jmp     short loc_140044C33
0x140044c54  add     rdi, 2
0x140044c58  mov     eax, 0FFFEh
0x140044c5d  add     dx, ax
0x140044c60  mov     [rbp+Source2.Buffer], rdi
0x140044c64  mov     [rbp+Source2.Length], dx
0x140044c68  mov     r12b, 1
0x140044c6b  mov     r8, rdi
0x140044c6e  jmp     loc_1400449D1
0x140044c73  mov     rdi, [r15+200h]
0x140044c7a  nop     word ptr [rax+rax+00h]
0x140044c80  test    rdi, rdi
0x140044c83  jz      loc_140044D6A
0x140044c89  movzx   edx, word ptr [rdi+18h]
0x140044c8d  cmp     dx, cx
0x140044c90  jbe     short loc_140044CF3
0x140044c92  movzx   esi, cx
0x140044c95  mov     ebx, 1
0x140044c9a  mov     rcx, [rdi+20h]; Source1
0x140044c9e  mov     rdx, r9; Source2
0x140044ca1  mov     r8d, esi; Length
0x140044ca4  call    cs:__imp_RtlCompareMemory
0x140044cab  nop     dword ptr [rax+rax+00h]
0x140044cb0  mov     r9, [rbp+Src+8]
0x140044cb4  cmp     eax, esi
0x140044cb6  jnb     short loc_140044CDB
0x140044cb8  mov     rcx, [rdi+20h]
0x140044cbc  mov     ebx, 0FFFFFFFFh
0x140044cc1  mov     eax, eax
0x140044cc3  shr     rax, 1
0x140044cc6  lea     rdx, [rax+rax]
0x140044cca  movzx   eax, word ptr [rdx+r9]
0x140044ccf  cmp     [rdx+rcx], ax
0x140044cd3  mov     eax, 1
0x140044cd8  cmovnb  ebx, eax
0x140044cdb  cmp     ebx, 1
0x140044cde  jz      loc_140044D71
0x140044ce4  cmp     ebx, 0FFFFFFFFh
0x140044ce7  jnz     short loc_140044D04
0x140044ce9  mov     rdi, [rdi+10h]
0x140044ced  movzx   ecx, word ptr [rbp+Src]
0x140044cf1  jmp     short loc_140044C80
0x140044cf3  xor     eax, eax
0x140044cf5  mov     ebx, 0FFFFFFFFh
0x140044cfa  cmp     dx, cx
0x140044cfd  mov     esi, edx
0x140044cff  cmovz   ebx, eax
0x140044d02  jmp     short loc_140044C9A
0x140044d04  mov     rcx, rdi; Links
0x140044d07  call    cs:__imp_RtlSplay
0x140044d0e  nop     dword ptr [rax+rax+00h]
0x140044d13  mov     [r15+200h], rax
0x140044d1a  add     rdi, 0FFFFFFFFFFFFFF98h
0x140044d1e  jmp     loc_140044B46
0x140044d23  mov     rbx, qword ptr [rbp+arg_0]
0x140044d27  lea     r8, [rbp+Source2]
0x140044d2b  mov     rcx, rbx
0x140044d2e  lea     rdx, [rbp+Src]
0x140044d32  call    UdfValidateAndRemoveStreamSuffix
0x140044d37  movzx   ecx, word ptr [rbp+Src]
0x140044d3b  xor     eax, eax
0x140044d3d  cmp     ax, cx
0x140044d40  jz      loc_140044F22
0x140044d46  mov     eax, [r15+0D4h]
0x140044d4d  test    al, 10h
0x140044d4f  jz      short loc_140044D7E
0x140044d51  mov     ecx, 0C000000Dh; Status
0x140044d56  mov     dword ptr [rbx+18h], 0C000000Dh
0x140044d5d  call    cs:__imp_ExRaiseStatus
0x140044d6a  xor     edi, edi
0x140044d6c  jmp     loc_140044B46
0x140044d71  mov     rdi, [rdi+8]
0x140044d75  movzx   ecx, word ptr [rbp+Src]
0x140044d79  jmp     loc_140044C80
0x140044d7e  mov     rax, [r15+88h]
0x140044d85  mov     r15, [rax+18h]
0x140044d89  test    r15, r15
0x140044d8c  jz      loc_140044A80
0x140044d92  mov     r9, [rbp+Src+8]
0x140044d96  jmp     loc_140044A75
0x140044d9b  cmp     rax, rdx
0x140044d9e  jz      short loc_140044DB0
0x140044da0  lea     eax, [r8+4]
0x140044da4  cmp     word ptr [r9+rax*2], 2Eh ; '.'
0x140044daa  jnz     loc_140044C4F
0x140044db0  test    dword ptr [r15+0D4h], 800000h
0x140044dbb  jnz     short loc_140044DC9
0x140044dbd  mov     rcx, qword ptr [rbp+arg_0]; int
0x140044dc1  mov     rdx, r15; int
0x140044dc4  call    UdfBuildScbShortNameIndex
0x140044dc9  lea     rdx, [r15+210h]
0x140044dd0  mov     r9d, 0B8h
  ... truncated ...
```
