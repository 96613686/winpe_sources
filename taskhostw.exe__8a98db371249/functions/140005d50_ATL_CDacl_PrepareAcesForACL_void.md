# ATL::CDacl::PrepareAcesForACL(void)

- ea: `0x140005d50`
- end: `0x140005eed`
- name: `?PrepareAcesForACL@CDacl@ATL@@EEBAXXZ`
- size: `413`
- prototype: `void __fastcall(ATL::CDacl *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x140005d04`
- `0x140005d50`
- `0x140005f00`
- `0x140005f40`
- `0x140006770`
- `0x1400072bc`
- `0x14000c010`

## pseudocode

```c
void __fastcall ATL::CDacl::PrepareAcesForACL(ATL::CDacl *this)
{
  unsigned __int64 v2; // rbx
  unsigned __int64 v3; // rbp
  const struct ATL::CDacl::CAccessAce *v4; // r14
  unsigned __int64 v5; // rsi
  const struct ATL::CDacl::CAccessAce **v6; // rdi
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // r13
  _QWORD *v9; // rdi
  __int64 (__fastcall ****v10)(_QWORD, __int64); // rax
  const struct ATL::CDacl::CAccessAce **v11; // rdi
  unsigned __int128 v12; // rax
  __int64 (__fastcall ***v13[11])(_QWORD, __int64); // [rsp+20h] [rbp-58h] BYREF
  unsigned __int64 v14; // [rsp+80h] [rbp+8h]

  v2 = 1;
  v3 = *((_QWORD *)this + 4);
  v4 = 0;
  v13[0] = 0;
  if ( v3 <= 4 )
    goto LABEL_29;
  do
    v2 = 3 * v2 + 1;
  while ( v2 + 2 * v2 + 1 < v3 );
  if ( v2 )
  {
LABEL_29:
    while ( 1 )
    {
      v5 = v2 - 1;
      if ( v2 - 1 < v3 )
        break;
LABEL_22:
      v12 = v2 * (unsigned __int128)0xAAAAAAAAAAAAAAABuLL;
      v2 /= 3u;
      if ( !(*((_QWORD *)&v12 + 1) >> 1) )
        goto LABEL_23;
    }
    while ( 1 )
    {
      if ( v5 >= *((_QWORD *)this + 4) )
        goto LABEL_26;
      v6 = (const struct ATL::CDacl::CAccessAce **)(*((_QWORD *)this + 3) + 8 * v5);
      if ( v4 != *v6 )
        break;
      if ( v13 != (__int64 (__fastcall ****)(_QWORD, __int64))v6 )
        goto LABEL_10;
LABEL_11:
      v7 = v5;
      v14 = v5;
      if ( v5 >= v2 )
      {
        while ( 1 )
        {
          v8 = v7 - v2;
          if ( v7 - v2 >= *((_QWORD *)this + 4) )
            break;
          if ( (unsigned int)ATL::CDacl::CAccessAce::Order(
                               *(const struct ATL::CDacl::CAccessAce **)(*((_QWORD *)this + 3) + 8 * v8),
                               v4) == -1 )
          {
            v9 = (_QWORD *)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                             (_QWORD *)this + 3,
                             v7 - v2);
            v10 = (__int64 (__fastcall ****)(_QWORD, __int64))ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                                                                (_QWORD *)this + 3,
                                                                v14);
            ATL::CAutoPtr<ATL::CDacl::CAccessAce>::operator=(v10, v9);
            v7 = v8;
            v14 = v8;
            if ( v8 >= v2 )
              continue;
          }
          goto LABEL_15;
        }
LABEL_26:
        ATL::PrivateAtlThrow(-2147024809);
      }
LABEL_15:
      if ( v7 >= *((_QWORD *)this + 4) )
        goto LABEL_26;
      v11 = (const struct ATL::CDacl::CAccessAce **)(*((_QWORD *)this + 3) + 8 * v7);
      if ( *v11 == v4 )
      {
        if ( v11 == (const struct ATL::CDacl::CAccessAce **)v13 )
          goto LABEL_21;
      }
      else
      {
        ATL::CAutoPtr<ATL::CDacl::CAccessAce>::~CAutoPtr<ATL::CDacl::CAccessAce>((__int64 (__fastcall ****)(_QWORD, __int64))v11);
        *v11 = v4;
      }
      v4 = 0;
      v13[0] = 0;
LABEL_21:
      if ( ++v5 >= v3 )
        goto LABEL_22;
    }
    ATL::CAutoPtr<ATL::CDacl::CAccessAce>::~CAutoPtr<ATL::CDacl::CAccessAce>(v13);
    v4 = *v6;
    v13[0] = (__int64 (__fastcall ***)(_QWORD, __int64))*v6;
LABEL_10:
    *v6 = 0;
    goto LABEL_11;
  }
LABEL_23:
  if ( v4 )
    (**(void (__fastcall ***)(const struct ATL::CDacl::CAccessAce *, __int64))v4)(v4, 1);
}

```

## disassembly

```asm
0x140005d50  push    rbx
0x140005d52  push    rbp
0x140005d53  push    rsi
0x140005d54  push    rdi
0x140005d55  push    r12
0x140005d57  push    r13
0x140005d59  push    r14
0x140005d5b  push    r15
0x140005d5d  sub     rsp, 38h
0x140005d61  mov     r15, rcx
0x140005d64  mov     ebx, 1
0x140005d69  mov     rbp, [rcx+20h]
0x140005d6d  xor     r14d, r14d
0x140005d70  mov     [rsp+78h+var_58], r14
0x140005d75  cmp     rbp, 4
0x140005d79  jbe     short loc_140005D9B
0x140005d7b  lea     rbx, [rbx+rbx*2]
0x140005d7f  inc     rbx
0x140005d82  lea     rax, ds:1[rbx*2]
0x140005d8a  add     rax, rbx
0x140005d8d  cmp     rax, rbp
0x140005d90  jb      short loc_140005D7B
0x140005d92  test    rbx, rbx
0x140005d95  jz      loc_140005EB8
0x140005d9b  mov     rax, 0AAAAAAAAAAAAAAABh
0x140005da5  lea     rsi, [rbx-1]
0x140005da9  cmp     rsi, rbp
0x140005dac  jnb     loc_140005EA9
0x140005db2  cmp     rsi, [r15+20h]
0x140005db6  jnb     loc_140005EE2
0x140005dbc  mov     rax, [r15+18h]
0x140005dc0  lea     rdi, [rax+rsi*8]
0x140005dc4  cmp     r14, [rdi]
0x140005dc7  jnz     short loc_140005DD5
0x140005dc9  lea     rax, [rsp+78h+var_58]
0x140005dce  cmp     rax, rdi
0x140005dd1  jnz     short loc_140005DE7
0x140005dd3  jmp     short loc_140005DEE
0x140005dd5  lea     rcx, [rsp+78h+var_58]
0x140005dda  call    ??1?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@QEAA@XZ; ATL::CAutoPtr<ATL::CDacl::CAccessAce>::~CAutoPtr<ATL::CDacl::CAccessAce>(void)
0x140005ddf  mov     r14, [rdi]
0x140005de2  mov     [rsp+78h+var_58], r14
0x140005de7  mov     qword ptr [rdi], 0
0x140005dee  mov     rdi, rsi
0x140005df1  mov     [rsp+78h+arg_0], rsi
0x140005df9  cmp     rsi, rbx
0x140005dfc  jb      short loc_140005E5E
0x140005dfe  mov     r13, rdi
0x140005e01  sub     r13, rbx
0x140005e04  cmp     r13, [r15+20h]
0x140005e08  jnb     loc_140005EE2
0x140005e0e  mov     rcx, [r15+18h]
0x140005e12  mov     rdx, r14; struct ATL::CDacl::CAccessAce *
0x140005e15  mov     rcx, [rcx+r13*8]; struct ATL::CDacl::CAccessAce *
0x140005e19  call    ?Order@CAccessAce@CDacl@ATL@@SAHAEBV123@0@Z; ATL::CDacl::CAccessAce::Order(ATL::CDacl::CAccessAce const &,ATL::CDacl::CAccessAce const &)
0x140005e1e  cmp     eax, 0FFFFFFFFh
0x140005e21  jnz     short loc_140005E5E
0x140005e23  mov     rdx, r13
0x140005e26  lea     rcx, [r15+18h]
0x140005e2a  call    ??A?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAAAEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](unsigned __int64)
0x140005e2f  mov     rdi, rax
0x140005e32  mov     rdx, [rsp+78h+arg_0]
0x140005e3a  lea     rcx, [r15+18h]
0x140005e3e  call    ??A?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAAAEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](unsigned __int64)
0x140005e43  mov     rcx, rax
0x140005e46  mov     rdx, rdi
0x140005e49  call    ??4?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@QEAAAEAV01@AEAV01@@Z; ATL::CAutoPtr<ATL::CDacl::CAccessAce>::operator=(ATL::CAutoPtr<ATL::CDacl::CAccessAce> &)
0x140005e4e  mov     rdi, r13
0x140005e51  mov     [rsp+78h+arg_0], r13
0x140005e59  cmp     r13, rbx
0x140005e5c  jnb     short loc_140005DFE
0x140005e5e  cmp     rdi, [r15+20h]
0x140005e62  jnb     short loc_140005EE2
0x140005e64  mov     rax, [r15+18h]
0x140005e68  lea     rdi, [rax+rdi*8]
0x140005e6c  mov     r13, r14
0x140005e6f  cmp     [rdi], r14
0x140005e72  jnz     short loc_140005E80
0x140005e74  lea     rax, [rsp+78h+var_58]
0x140005e79  cmp     rdi, rax
0x140005e7c  jnz     short loc_140005E8B
0x140005e7e  jmp     short loc_140005E93
0x140005e80  mov     rcx, rdi
0x140005e83  call    ??1?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@QEAA@XZ; ATL::CAutoPtr<ATL::CDacl::CAccessAce>::~CAutoPtr<ATL::CDacl::CAccessAce>(void)
0x140005e88  mov     [rdi], r13
0x140005e8b  xor     r14d, r14d
0x140005e8e  mov     [rsp+78h+var_58], r14
0x140005e93  inc     rsi
0x140005e96  cmp     rsi, rbp
0x140005e99  jb      loc_140005DB2
0x140005e9f  mov     rax, 0AAAAAAAAAAAAAAABh
0x140005ea9  mul     rbx
0x140005eac  mov     rbx, rdx
0x140005eaf  shr     rbx, 1
0x140005eb2  jnz     loc_140005D9B
0x140005eb8  test    r14, r14
0x140005ebb  jz      short loc_140005ED1
0x140005ebd  mov     rax, [r14]
0x140005ec0  mov     edx, 1
0x140005ec5  mov     rcx, r14
0x140005ec8  mov     rax, [rax]
0x140005ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ed0  nop
0x140005ed1  add     rsp, 38h
0x140005ed5  pop     r15
0x140005ed7  pop     r14
0x140005ed9  pop     r13
0x140005edb  pop     r12
0x140005edd  pop     rdi
0x140005ede  pop     rsi
0x140005edf  pop     rbp
0x140005ee0  pop     rbx
0x140005ee1  retn
0x140005ee2  mov     ecx, 80070057h; int
0x140005ee7  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
