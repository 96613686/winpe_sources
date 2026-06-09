# CTls13Context::GenerateApplicationWriteKeys(unsigned __int64,unsigned __int64,unsigned __int64 *,unsigned __int64 *,eSslErrorState *)

- ea: `0x1800328e0`
- end: `0x180032b0e`
- name: `?GenerateApplicationWriteKeys@CTls13Context@@IEAAK_K0PEA_K1PEAW4eSslErrorState@@@Z`
- size: `558`
- prototype: `unsigned int __usercall@<eax>(CTls13Context *__hidden this@<rcx>, unsigned __int64@<rdx>, unsigned __int64@<r8>, unsigned __int64 *@<r9>, unsigned __int64 *, enum eSslErrorState *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180033188`
- `0x180050f90`

## callees

- `0x1800328e0`
- `0x180032b20`

## import_xrefs

- `ncrypt!SslExpandExporterMasterKey` at `0x1800329c8`
- `ncrypt!SslExpandExporterMasterKey` at `0x1800329c8`
- `ncrypt!SslExpandTrafficKeys` at `0x180032a57`
- `ncrypt!SslExpandTrafficKeys` at `0x180032a57`
- `ncrypt!SslExtractMasterKey` at `0x180032983`
- `ncrypt!SslExtractMasterKey` at `0x180032983`
- `ncrypt!SslExpandWriteKey` at `0x180032a79`
- `ncrypt!SslExpandWriteKey` at `0x180032a93`
- `ncrypt!SslExpandWriteKey` at `0x180032a79`
- `ncrypt!SslExpandWriteKey` at `0x180032a93`
- `ncrypt!SslFreeObject` at `0x180032996`
- `ncrypt!SslFreeObject` at `0x180032acd`
- `ncrypt!SslFreeObject` at `0x180032996`
- `ncrypt!SslFreeObject` at `0x180032acd`

## pseudocode

```c
__int64 __fastcall CTls13Context::GenerateApplicationWriteKeys(
        CTls13Context *this,
        __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        unsigned __int64 *a5,
        enum eSslErrorState *a6)
{
  __int64 v10; // rdx
  __int64 result; // rax
  __int64 v12; // r13
  _QWORD *v13; // rdi
  _QWORD *v14; // r14
  __int64 v15; // rcx
  unsigned int MasterKey; // [rsp+98h] [rbp+10h]

  if ( !a2 )
    return 87;
  if ( !a3 )
    return 87;
  if ( !a4 )
    return 87;
  if ( !a5 )
    return 87;
  if ( *a4 )
    return 87;
  if ( *a5 )
    return 87;
  if ( !a6 )
    return 87;
  v10 = *((_QWORD *)this + 6);
  if ( !v10 || *((_QWORD *)this + 9) || *((_QWORD *)this + 12) )
    return 87;
  MasterKey = SslExtractMasterKey(a2, v10, (char *)this + 72, 0, 0);
  SslFreeObject(*((_QWORD *)this + 6), 0);
  result = MasterKey;
  *((_QWORD *)this + 6) = 0;
  if ( MasterKey )
  {
    *(_DWORD *)a6 = 711;
    return result;
  }
  result = SslExpandExporterMasterKey(a2, *((_QWORD *)this + 9), a3, (char *)this + 96, 0, 0);
  if ( (_DWORD)result )
  {
    *(_DWORD *)a6 = 608;
    return result;
  }
  v12 = *((_QWORD *)this + 9);
  if ( !v12 )
    return 87;
  v13 = (_QWORD *)((char *)this + 80);
  if ( this == (CTls13Context *)-80LL )
    return 87;
  v14 = (_QWORD *)((char *)this + 88);
  if ( this == (CTls13Context *)-88LL || *v13 || *v14 || *a4 || *a5 )
    return 87;
  CTls13Context::FreeEarlyKey(this);
  v15 = *((_QWORD *)this + 5);
  if ( v15 )
  {
    SslFreeObject(v15, 0);
    *((_QWORD *)this + 5) = 0;
  }
  result = SslExpandTrafficKeys(a2, v12, a3, (char *)this + 80, (char *)this + 88, 0, 0);
  if ( (_DWORD)result )
  {
    *(_DWORD *)a6 = 605;
  }
  else
  {
    if ( !*((_BYTE *)this + 201) )
      return 0;
    result = SslExpandWriteKey(a2, *v13, a4, 0, 0);
    if ( (_DWORD)result )
    {
      *(_DWORD *)a6 = 606;
    }
    else
    {
      result = SslExpandWriteKey(a2, *v14, a5, 0, 0);
      if ( !(_DWORD)result )
        return 0;
      *(_DWORD *)a6 = 607;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800328e0  push    rbx
0x1800328e2  push    rbp
0x1800328e3  push    rsi
0x1800328e4  push    rdi
0x1800328e5  push    r12
0x1800328e7  push    r13
0x1800328e9  push    r14
0x1800328eb  push    r15
0x1800328ed  sub     rsp, 48h
0x1800328f1  mov     rbp, r9
0x1800328f4  mov     r12, r8
0x1800328f7  mov     r15, rdx
0x1800328fa  mov     rbx, rcx
0x1800328fd  test    rdx, rdx
0x180032900  jz      loc_180032AB0
0x180032906  test    r8, r8
0x180032909  jz      loc_180032AB0
0x18003290f  test    r9, r9
0x180032912  jz      loc_180032AB0
0x180032918  mov     rsi, [rsp+88h+arg_20]
0x180032920  test    rsi, rsi
0x180032923  jz      loc_180032AB0
0x180032929  cmp     qword ptr [r9], 0
0x18003292d  jnz     loc_180032AB0
0x180032933  cmp     qword ptr [rsi], 0
0x180032937  jnz     loc_180032AB0
0x18003293d  mov     r13, [rsp+88h+arg_28]
0x180032945  test    r13, r13
0x180032948  jz      loc_180032AB0
0x18003294e  mov     rdx, [rcx+30h]
0x180032952  test    rdx, rdx
0x180032955  jz      loc_180032AB0
0x18003295b  cmp     qword ptr [rcx+48h], 0
0x180032960  jnz     loc_180032AB0
0x180032966  cmp     qword ptr [rcx+60h], 0
0x18003296b  jnz     loc_180032AB0
0x180032971  lea     r8, [rcx+48h]
0x180032975  mov     dword ptr [rsp+88h+var_68], 0
0x18003297d  mov     rcx, r15
0x180032980  xor     r9d, r9d
0x180032983  call    cs:__imp_SslExtractMasterKey
0x180032989  mov     rcx, [rbx+30h]
0x18003298d  xor     edx, edx
0x18003298f  mov     [rsp+88h+arg_8], eax
0x180032996  call    cs:__imp_SslFreeObject
0x18003299c  mov     eax, [rsp+88h+arg_8]
0x1800329a3  xor     ecx, ecx
0x1800329a5  mov     [rbx+30h], rcx
0x1800329a9  test    eax, eax
0x1800329ab  jnz     loc_180032AC1
0x1800329b1  mov     rdx, [rbx+48h]
0x1800329b5  lea     r9, [rbx+60h]
0x1800329b9  mov     dword ptr [rsp+88h+var_60], ecx
0x1800329bd  mov     r8, r12
0x1800329c0  mov     [rsp+88h+var_68], rcx
0x1800329c5  mov     rcx, r15
0x1800329c8  call    cs:__imp_SslExpandExporterMasterKey
0x1800329ce  test    eax, eax
0x1800329d0  jnz     loc_180032AB7
0x1800329d6  mov     r13, [rbx+48h]
0x1800329da  test    r13, r13
0x1800329dd  jz      loc_180032AB0
0x1800329e3  lea     rdi, [rbx+50h]
0x1800329e7  test    rdi, rdi
0x1800329ea  jz      loc_180032AB0
0x1800329f0  lea     r14, [rbx+58h]
0x1800329f4  test    r14, r14
0x1800329f7  jz      loc_180032AB0
0x1800329fd  cmp     qword ptr [rdi], 0
0x180032a01  jnz     loc_180032AB0
0x180032a07  cmp     qword ptr [r14], 0
0x180032a0b  jnz     loc_180032AB0
0x180032a11  cmp     qword ptr [rbp+0], 0
0x180032a16  jnz     loc_180032AB0
0x180032a1c  cmp     qword ptr [rsi], 0
0x180032a20  jnz     loc_180032AB0
0x180032a26  mov     rcx, rbx; this
0x180032a29  call    ?FreeEarlyKey@CTls13Context@@AEAAXXZ; CTls13Context::FreeEarlyKey(void)
0x180032a2e  mov     rcx, [rbx+28h]
0x180032a32  test    rcx, rcx
0x180032a35  jnz     loc_180032ACB
0x180032a3b  xor     eax, eax
0x180032a3d  mov     [rsp+88h+var_58], eax
0x180032a41  mov     r9, rdi
0x180032a44  mov     [rsp+88h+var_60], rax
0x180032a49  mov     r8, r12
0x180032a4c  mov     rdx, r13
0x180032a4f  mov     [rsp+88h+var_68], r14
0x180032a54  mov     rcx, r15
0x180032a57  call    cs:__imp_SslExpandTrafficKeys
0x180032a5d  test    eax, eax
0x180032a5f  jnz     short loc_180032ADE
0x180032a61  cmp     [rbx+0C9h], al
0x180032a67  jz      short loc_180032A9D
0x180032a69  mov     rdx, [rdi]
0x180032a6c  xor     r9d, r9d
0x180032a6f  mov     r8, rbp
0x180032a72  mov     dword ptr [rsp+88h+var_68], eax
0x180032a76  mov     rcx, r15
0x180032a79  call    cs:__imp_SslExpandWriteKey
0x180032a7f  test    eax, eax
0x180032a81  jnz     short loc_180032AEE
0x180032a83  mov     rdx, [r14]
0x180032a86  xor     r9d, r9d
0x180032a89  mov     r8, rsi
0x180032a8c  mov     dword ptr [rsp+88h+var_68], eax
0x180032a90  mov     rcx, r15
0x180032a93  call    cs:__imp_SslExpandWriteKey
0x180032a99  test    eax, eax
0x180032a9b  jnz     short loc_180032AFE
0x180032a9d  xor     eax, eax
0x180032a9f  add     rsp, 48h
0x180032aa3  pop     r15
0x180032aa5  pop     r14
0x180032aa7  pop     r13
0x180032aa9  pop     r12
0x180032aab  pop     rdi
0x180032aac  pop     rsi
0x180032aad  pop     rbp
0x180032aae  pop     rbx
0x180032aaf  retn
0x180032ab0  mov     eax, 57h ; 'W'
0x180032ab5  jmp     short loc_180032A9F
0x180032ab7  mov     dword ptr [r13+0], 260h
0x180032abf  jmp     short loc_180032A9F
0x180032ac1  mov     dword ptr [r13+0], 2C7h
0x180032ac9  jmp     short loc_180032A9F
0x180032acb  xor     edx, edx
0x180032acd  call    cs:__imp_SslFreeObject
0x180032ad3  xor     eax, eax
0x180032ad5  mov     [rbx+28h], rax
0x180032ad9  jmp     loc_180032A3D
0x180032ade  mov     rcx, [rsp+88h+arg_28]
0x180032ae6  mov     dword ptr [rcx], 25Dh
0x180032aec  jmp     short loc_180032A9F
0x180032aee  mov     rcx, [rsp+88h+arg_28]
0x180032af6  mov     dword ptr [rcx], 25Eh
0x180032afc  jmp     short loc_180032A9F
0x180032afe  mov     rcx, [rsp+88h+arg_28]
0x180032b06  mov     dword ptr [rcx], 25Fh
0x180032b0c  jmp     short loc_180032A9F
```
