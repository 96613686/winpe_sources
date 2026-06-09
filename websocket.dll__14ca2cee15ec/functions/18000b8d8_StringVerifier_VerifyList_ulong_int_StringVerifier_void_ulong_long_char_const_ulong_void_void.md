# StringVerifier::VerifyList(ulong,int (StringVerifier::*)(void),ulong,long (*)(char const *,ulong,void *),void *)

- ea: `0x18000b8d8`
- end: `0x18000ba5d`
- name: `?VerifyList@StringVerifier@@AEAAJKP81@EAAHXZKP6AJPEBDKPEAX@Z2@Z`
- size: `389`
- prototype: `__int64 __fastcall(StringVerifier *this, UINT uID, unsigned int (__fastcall *)(StringVerifier *), unsigned int, __int64 (__fastcall *)(__int64, unsigned __int64, __int64), __int64)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x180009710`
- `0x180009800`
- `0x180009870`
- `0x18000a438`
- `0x18000a950`
- `0x18000a9d0`
- `0x18000aa30`
- `0x18000b88c`

## callees

- `0x180002578`
- `0x1800026b4`
- `0x18000b77c`
- `0x18000b8d8`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall StringVerifier::VerifyList(
        StringVerifier *this,
        UINT uID,
        unsigned int (__fastcall *a3)(StringVerifier *),
        unsigned int a4,
        __int64 (__fastcall *a5)(__int64, unsigned __int64, __int64),
        __int64 a6)
{
  unsigned __int64 v8; // rcx
  int v11; // ebx
  const unsigned __int16 *String; // rax
  __int64 result; // rax
  int v14; // ebx
  __int64 v15; // rsi
  unsigned __int64 v16; // rdx
  _BYTE *v17; // rax
  _BYTE *v18; // rax
  int v19; // r8d
  unsigned int v20; // edx
  int v21; // [rsp+28h] [rbp-40h]

  v8 = *((_QWORD *)this + 2);
  if ( *((_QWORD *)this + 1) == v8 )
  {
LABEL_2:
    v11 = *((_DWORD *)this + 4) - *((_DWORD *)this + 2);
    String = Trace::GetString(uID);
    v21 = v11;
    Trace::Error(
      -2089418750,
      0xD000000C,
      (unsigned int)(*((_DWORD *)this + 4) - *(_DWORD *)this),
      *(_QWORD *)this,
      String,
      v21);
    return 2205548546LL;
  }
  else
  {
    result = 0;
    v14 = 0;
    if ( *((_QWORD *)this + 1) >= v8 )
      return result;
    while ( 1 )
    {
      while ( (unsigned int)StringVerifier::TryDecodeLWS(this) )
        ;
      v15 = *((_QWORD *)this + 1);
      if ( !a3(this) && **((_BYTE **)this + 1) != 44 )
        goto LABEL_2;
      v16 = *((_QWORD *)this + 1) - v15;
      if ( v16 > 0xFFFFFFFF )
        return 2147942934LL;
      if ( (_DWORD)v16 )
      {
        if ( a5 )
        {
          result = a5(v15, v16, a6);
          if ( (int)result < 0 )
            return result;
        }
      }
      if ( *((_QWORD *)this + 1) >= *((_QWORD *)this + 2) )
        return 0;
      if ( ++v14 >= a4 )
      {
        v19 = *((_DWORD *)this + 4);
        v20 = -805306355;
        goto LABEL_21;
      }
      while ( (unsigned int)StringVerifier::TryDecodeLWS(this) )
        ;
      v17 = (_BYTE *)*((_QWORD *)this + 1);
      if ( (unsigned __int64)v17 >= *((_QWORD *)this + 2) || *v17 != 44 )
      {
        v19 = *((_DWORD *)this + 4);
        v20 = -805306354;
LABEL_21:
        Trace::Error(-2089418750, v20, v19 - (unsigned int)*(_QWORD *)this);
        return 2205548546LL;
      }
      v18 = v17 + 1;
      *((_QWORD *)this + 1) = v18;
      if ( (unsigned __int64)v18 >= *((_QWORD *)this + 2) )
      {
        Trace::Error(-2089418750, 0xD000000F, (unsigned int)(*((_DWORD *)this + 4) - *(_DWORD *)this), *(_QWORD *)this);
        return 2205548546LL;
      }
    }
  }
}

```

## disassembly

```asm
0x18000b8d8  push    rbx
0x18000b8da  push    rbp
0x18000b8db  push    rsi
0x18000b8dc  push    rdi
0x18000b8dd  push    r12
0x18000b8df  push    r15
0x18000b8e1  sub     rsp, 38h
0x18000b8e5  mov     rdi, rcx
0x18000b8e8  mov     ebp, r9d
0x18000b8eb  mov     rcx, [rcx+10h]
0x18000b8ef  mov     r12, r8
0x18000b8f2  mov     r15d, edx
0x18000b8f5  cmp     [rdi+8], rcx
0x18000b8f9  jnz     short loc_18000B934
0x18000b8fb  mov     ebx, [rdi+10h]
0x18000b8fe  mov     ecx, r15d; uID
0x18000b901  sub     ebx, [rdi+8]
0x18000b904  call    ?GetString@Trace@@SAPEBGK@Z; Trace::GetString(ulong)
0x18000b909  mov     r8d, [rdi+10h]
0x18000b90d  mov     edx, 0D000000Ch; unsigned int
0x18000b912  sub     r8d, [rdi]
0x18000b915  mov     r9, [rdi]
0x18000b918  mov     [rsp+68h+var_40], ebx
0x18000b91c  mov     ebx, 83760002h
0x18000b921  mov     ecx, ebx; int
0x18000b923  mov     [rsp+68h+var_48], rax
0x18000b928  call    ?Error@Trace@@SAJJKZZ; Trace::Error(long,ulong,...)
0x18000b92d  mov     eax, ebx
0x18000b92f  jmp     loc_18000BA50
0x18000b934  xor     eax, eax
0x18000b936  xor     ebx, ebx
0x18000b938  cmp     [rdi+8], rcx
0x18000b93c  jnb     loc_18000BA50
0x18000b942  mov     rcx, rdi; this
0x18000b945  call    ?TryDecodeLWS@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeLWS(void)
0x18000b94a  test    eax, eax
0x18000b94c  jnz     short loc_18000B942
0x18000b94e  mov     rsi, [rdi+8]
0x18000b952  mov     rcx, rdi
0x18000b955  mov     rax, r12
0x18000b958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b95d  test    eax, eax
0x18000b95f  jnz     short loc_18000B96A
0x18000b961  mov     rax, [rdi+8]
0x18000b965  cmp     byte ptr [rax], 2Ch ; ','
0x18000b968  jnz     short loc_18000B8FB
0x18000b96a  mov     rdx, [rdi+8]
0x18000b96e  mov     eax, 0FFFFFFFFh
0x18000b973  sub     rdx, rsi
0x18000b976  cmp     rdx, rax
0x18000b979  ja      loc_18000BA4B
0x18000b97f  test    edx, edx
0x18000b981  jz      short loc_18000B9AE
0x18000b983  cmp     [rsp+68h+arg_20], 0
0x18000b98c  jz      short loc_18000B9AE
0x18000b98e  mov     r8, [rsp+68h+arg_28]
0x18000b996  mov     rcx, rsi
0x18000b999  mov     rax, [rsp+68h+arg_20]
0x18000b9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9a6  test    eax, eax
0x18000b9a8  js      loc_18000BA50
0x18000b9ae  mov     rax, [rdi+10h]
0x18000b9b2  cmp     [rdi+8], rax
0x18000b9b6  jnb     loc_18000BA47
0x18000b9bc  inc     ebx
0x18000b9be  cmp     ebx, ebp
0x18000b9c0  jnb     short loc_18000BA23
0x18000b9c2  mov     rcx, rdi; this
0x18000b9c5  call    ?TryDecodeLWS@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeLWS(void)
0x18000b9ca  test    eax, eax
0x18000b9cc  jnz     short loc_18000B9C2
0x18000b9ce  mov     rax, [rdi+8]
0x18000b9d2  cmp     rax, [rdi+10h]
0x18000b9d6  jnb     short loc_18000BA0E
0x18000b9d8  cmp     byte ptr [rax], 2Ch ; ','
0x18000b9db  jnz     short loc_18000BA0E
0x18000b9dd  inc     rax
0x18000b9e0  mov     [rdi+8], rax
0x18000b9e4  cmp     rax, [rdi+10h]
0x18000b9e8  jb      loc_18000B942
0x18000b9ee  mov     r8d, [rdi+10h]
0x18000b9f2  mov     ebx, 83760002h
0x18000b9f7  sub     r8d, [rdi]
0x18000b9fa  mov     ecx, ebx; int
0x18000b9fc  mov     r9, [rdi]
0x18000b9ff  mov     edx, 0D000000Fh; unsigned int
0x18000ba04  call    ?Error@Trace@@SAJJKZZ; Trace::Error(long,ulong,...)
0x18000ba09  jmp     loc_18000B92D
0x18000ba0e  mov     r8d, [rdi+10h]
0x18000ba12  mov     edx, 0D000000Eh
0x18000ba17  mov     eax, r8d
0x18000ba1a  sub     eax, [rdi+8]
0x18000ba1d  mov     dword ptr [rsp+68h+var_48], eax
0x18000ba21  jmp     short loc_18000BA30
0x18000ba23  mov     r8d, [rdi+10h]
0x18000ba27  mov     edx, 0D000000Dh; unsigned int
0x18000ba2c  mov     dword ptr [rsp+68h+var_48], ebp
0x18000ba30  mov     r9, [rdi]
0x18000ba33  mov     ebx, 83760002h
0x18000ba38  sub     r8d, r9d
0x18000ba3b  mov     ecx, ebx; int
0x18000ba3d  call    ?Error@Trace@@SAJJKZZ; Trace::Error(long,ulong,...)
0x18000ba42  jmp     loc_18000B92D
0x18000ba47  xor     eax, eax
0x18000ba49  jmp     short loc_18000BA50
0x18000ba4b  mov     eax, 80070216h
0x18000ba50  add     rsp, 38h
0x18000ba54  pop     r15
0x18000ba56  pop     r12
0x18000ba58  pop     rdi
0x18000ba59  pop     rsi
0x18000ba5a  pop     rbp
0x18000ba5b  pop     rbx
0x18000ba5c  retn
```
