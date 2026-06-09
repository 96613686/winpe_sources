# CExternalBase::CopyValuesFrom(CExternalBase *)

- ea: `0x180018d70`
- end: `0x1800191ac`
- name: `?CopyValuesFrom@CExternalBase@@QEAAJPEAV1@@Z`
- size: `1084`
- prototype: `__int64 __fastcall(CExternalBase *this, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018b60`
- `0x180028850`

## callees

- `0x180008e48`
- `0x180018d70`
- `0x1800191c0`
- `0x180019384`
- `0x180019518`
- `0x1800202e8`
- `0x180029e74`
- `0x18002b1ac`
- `0x18002fbb4`
- `0x180037d34`
- `0x180042010`

## pseudocode

```c
__int64 __fastcall CExternalBase::CopyValuesFrom(CExternalBase *this, const unsigned __int16 **a2)
{
  int v4; // ebx
  const unsigned __int16 *v5; // rbx
  unsigned __int64 v6; // rbp
  __int64 v7; // rsi
  __int64 v8; // rdi
  unsigned __int64 v9; // rdi
  size_t v10; // rax
  void *v11; // rax
  void *v12; // r14
  __int64 v13; // rcx
  _WORD *v14; // rdx
  bool v15; // zf
  _WORD *v16; // rax
  void *v17; // rdi
  void *v18; // rcx
  unsigned __int64 v20; // rax
  size_t v21; // rax
  void *v22; // rax
  void *v23; // r14
  _WORD *v24; // rcx
  const unsigned __int16 *v25; // rbx
  _WORD *v26; // rax
  void *v27; // rdi
  void *v28; // rcx
  __int64 v29; // rax

  if ( !a2 )
    return (unsigned int)-2147024809;
  v4 = CExternalBase::SetDisplayName(this, a2[2]);
  if ( v4 >= 0 )
  {
    v5 = a2[3];
    v6 = 255;
    v7 = 2147483646;
    if ( v5 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v5[v8] );
      v9 = v8 + 1;
      if ( v9 >= 0xFF )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
            (unsigned int)v9,
            255);
        }
        v9 = 255;
      }
      v10 = 2 * v9;
      if ( !is_mul_ok(v9, 2u) )
        v10 = -1;
      v11 = operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
      v12 = v11;
      if ( !v11 )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids);
        }
        return (unsigned int)-2147024882;
      }
      if ( v9 )
      {
        v13 = 2147483646;
        v14 = v11;
        do
        {
          if ( !v13 )
            break;
          if ( !*v5 )
            break;
          *v14++ = *v5++;
          --v13;
          --v9;
        }
        while ( v9 );
        v15 = v9 == 0;
        v16 = v14 - 1;
        v17 = v12;
        if ( !v15 )
          v16 = v14;
        v4 = 0;
        *v16 = 0;
      }
      else
      {
        v4 = -2147024809;
        v17 = 0;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
            2147942487LL);
        }
        operator delete(v12);
      }
      if ( v4 < 0 )
        return (unsigned int)v4;
    }
    else
    {
      v17 = 0;
    }
    v18 = (void *)*((_QWORD *)this + 3);
    if ( v18 )
      operator delete(v18);
    *((_QWORD *)this + 3) = v17;
    v4 = CExternalBase::SetCompanyName(this, a2[5]);
    if ( v4 >= 0 )
    {
      v4 = CExternalBase::SetVersionNumber(this, a2[6]);
      if ( v4 >= 0 )
      {
        v25 = a2[4];
        if ( !v25 )
        {
LABEL_44:
          v4 = CExternalBase::SetNotificationMessage(this, a2[7]);
          if ( v4 >= 0 )
            return (unsigned int)(*(__int64 (__fastcall **)(CExternalBase *, const unsigned __int16 **))(*(_QWORD *)this + 48LL))(
                                   this,
                                   a2);
          return (unsigned int)v4;
        }
        v29 = -1;
        do
          ++v29;
        while ( v25[v29] );
        v20 = v29 + 1;
        if ( v20 >= 0xFF )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
              (unsigned int)v20,
              255);
          }
        }
        else
        {
          v6 = v20;
        }
        v21 = 2 * v6;
        if ( !is_mul_ok(v6, 2u) )
          v21 = -1;
        v22 = operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
        v23 = v22;
        if ( !v22 )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids);
          }
          v4 = -2147024882;
LABEL_43:
          if ( v4 < 0 )
            return (unsigned int)v4;
          goto LABEL_44;
        }
        if ( v6 )
        {
          v24 = v22;
          do
          {
            if ( !v7 )
              break;
            if ( !*v25 )
              break;
            *v24++ = *v25++;
            --v7;
            --v6;
          }
          while ( v6 );
          v26 = v24 - 1;
          v27 = v23;
          v4 = 0;
          if ( v6 )
            v26 = v24;
          *v26 = 0;
        }
        else
        {
          v4 = -2147024809;
          v27 = 0;
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
              2147942487LL);
          }
          operator delete(v23);
        }
        if ( v4 >= 0 )
        {
          v28 = (void *)*((_QWORD *)this + 4);
          if ( v28 )
            operator delete(v28);
          *((_QWORD *)this + 4) = v27;
          goto LABEL_43;
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180018d70  push    rbx
0x180018d72  push    r12
0x180018d74  push    r13
0x180018d76  sub     rsp, 40h
0x180018d7a  mov     r13, rdx
0x180018d7d  mov     r12, rcx
0x180018d80  test    rdx, rdx
0x180018d83  jz      loc_18001901F
0x180018d89  mov     rdx, [rdx+10h]; unsigned __int16 *
0x180018d8d  call    ?SetDisplayName@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetDisplayName(ushort const *)
0x180018d92  mov     ebx, eax
0x180018d94  test    eax, eax
0x180018d96  js      loc_180018EB5
0x180018d9c  mov     rbx, [r13+18h]
0x180018da0  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180018da7  mov     [rsp+58h+arg_0], rbp
0x180018dac  mov     ebp, 0FFh
0x180018db1  mov     [rsp+58h+arg_8], rsi
0x180018db6  mov     esi, 7FFFFFFEh
0x180018dbb  mov     [rsp+58h+var_28], r15
0x180018dc0  lea     r15, WPP_GLOBAL_Control
0x180018dc7  mov     [rsp+58h+arg_10], rdi
0x180018dcc  mov     [rsp+58h+var_20], r14
0x180018dd1  test    rbx, rbx
0x180018dd4  jz      loc_180018EDF
0x180018dda  mov     rdi, r8
0x180018ddd  inc     rdi
0x180018de0  cmp     word ptr [rbx+rdi*2], 0
0x180018de5  jnz     short loc_180018DDD
0x180018de7  inc     rdi
0x180018dea  cmp     rdi, rbp
0x180018ded  jnb     loc_180019029
0x180018df3  mov     eax, 2
0x180018df8  mul     rdi
0x180018dfb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018e02  cmovb   rax, r8
0x180018e06  mov     rcx, rax; unsigned __int64
0x180018e09  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018e0e  mov     r14, rax
0x180018e11  test    rax, rax
0x180018e14  jz      loc_180018EC8
0x180018e1a  test    rdi, rdi
0x180018e1d  jz      loc_1800190B3
0x180018e23  cmp     rdi, 7FFFFFFFh
0x180018e2a  ja      loc_180019066
0x180018e30  mov     rcx, rsi
0x180018e33  mov     rdx, rax
0x180018e36  test    rcx, rcx
0x180018e39  jz      short loc_180018E57
0x180018e3b  movzx   eax, word ptr [rbx]
0x180018e3e  test    ax, ax
0x180018e41  jz      short loc_180018E57
0x180018e43  mov     [rdx], ax
0x180018e46  add     rbx, 2
0x180018e4a  add     rdx, 2
0x180018e4e  dec     rcx
0x180018e51  sub     rdi, 1
0x180018e55  jnz     short loc_180018E36
0x180018e57  test    rdi, rdi
0x180018e5a  lea     rax, [rdx-2]
0x180018e5e  mov     rdi, r14
0x180018e61  cmovnz  rax, rdx
0x180018e65  xor     r15d, r15d
0x180018e68  mov     ebx, r15d
0x180018e6b  mov     [rax], r15w
0x180018e6f  test    ebx, ebx
0x180018e71  js      short loc_180018E9C
0x180018e73  mov     rcx, [r12+18h]; Block
0x180018e78  test    rcx, rcx
0x180018e7b  jnz     short loc_180018EC1
0x180018e7d  mov     [r12+18h], rdi
0x180018e82  test    ebx, ebx
0x180018e84  js      short loc_180018E9C
0x180018e86  mov     rdx, [r13+28h]; unsigned __int16 *
0x180018e8a  mov     rcx, r12; this
0x180018e8d  call    ?SetCompanyName@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetCompanyName(ushort const *)
0x180018e92  mov     ebx, eax
0x180018e94  test    eax, eax
0x180018e96  jns     loc_180018FE7
0x180018e9c  mov     r14, [rsp+58h+var_20]
0x180018ea1  mov     rdi, [rsp+58h+arg_10]
0x180018ea6  mov     rsi, [rsp+58h+arg_8]
0x180018eab  mov     rbp, [rsp+58h+arg_0]
0x180018eb0  mov     r15, [rsp+58h+var_28]
0x180018eb5  mov     eax, ebx
0x180018eb7  add     rsp, 40h
0x180018ebb  pop     r13
0x180018ebd  pop     r12
0x180018ebf  pop     rbx
0x180018ec0  retn
0x180018ec1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018ec6  jmp     short loc_180018E7D
0x180018ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ecf  cmp     rcx, r15
0x180018ed2  jnz     loc_180019188
0x180018ed8  mov     ebx, 8007000Eh
0x180018edd  jmp     short loc_180018E9C
0x180018edf  xor     r15d, r15d
0x180018ee2  mov     edi, r15d
0x180018ee5  mov     ebx, r15d
0x180018ee8  jmp     short loc_180018E73
0x180018eea  inc     rax
0x180018eed  cmp     rax, rbp
0x180018ef0  jnb     loc_1800190C2
0x180018ef6  mov     rbp, rax
0x180018ef9  mov     eax, 2
0x180018efe  mul     rbp
0x180018f01  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018f08  cmovb   rax, rdi
0x180018f0c  mov     rcx, rax; unsigned __int64
0x180018f0f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018f14  mov     r14, rax
0x180018f17  test    rax, rax
0x180018f1a  jz      loc_180018FC9
0x180018f20  test    rbp, rbp
0x180018f23  jz      loc_18001910B
0x180018f29  cmp     rbp, 7FFFFFFFh
0x180018f30  ja      loc_180019104
0x180018f36  mov     rcx, rax
0x180018f39  nop     dword ptr [rax+00000000h]
0x180018f40  test    rsi, rsi
0x180018f43  jz      short loc_180018F61
0x180018f45  movzx   eax, word ptr [rbx]
0x180018f48  test    ax, ax
0x180018f4b  jz      short loc_180018F61
0x180018f4d  mov     [rcx], ax
0x180018f50  add     rbx, 2
0x180018f54  add     rcx, 2
0x180018f58  dec     rsi
0x180018f5b  sub     rbp, 1
0x180018f5f  jnz     short loc_180018F40
0x180018f61  test    rbp, rbp
0x180018f64  lea     rax, [rcx-2]
0x180018f68  mov     rdi, r14
0x180018f6b  mov     ebx, r15d
0x180018f6e  cmovnz  rax, rcx
0x180018f72  mov     [rax], r15w
0x180018f76  test    ebx, ebx
0x180018f78  js      loc_180018E9C
0x180018f7e  mov     rcx, [r12+20h]; Block
0x180018f83  test    rcx, rcx
0x180018f86  jnz     loc_18001915A
0x180018f8c  mov     [r12+20h], rdi
0x180018f91  test    ebx, ebx
0x180018f93  js      loc_180018E9C
0x180018f99  mov     rdx, [r13+38h]; unsigned __int16 *
0x180018f9d  mov     rcx, r12; this
0x180018fa0  call    ?SetNotificationMessage@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetNotificationMessage(ushort const *)
0x180018fa5  mov     ebx, eax
0x180018fa7  test    eax, eax
0x180018fa9  js      loc_180018E9C
0x180018faf  mov     rax, [r12]
0x180018fb3  mov     rdx, r13
0x180018fb6  mov     rcx, r12
0x180018fb9  mov     rax, [rax+30h]
0x180018fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fc2  mov     ebx, eax
0x180018fc4  jmp     loc_180018E9C
0x180018fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fd0  lea     rax, WPP_GLOBAL_Control
0x180018fd7  cmp     rcx, rax
0x180018fda  jnz     loc_180019164
0x180018fe0  mov     ebx, 8007000Eh
0x180018fe5  jmp     short loc_180018F91
0x180018fe7  mov     rdx, [r13+30h]; unsigned __int16 *
0x180018feb  mov     rcx, r12; this
0x180018fee  call    ?SetVersionNumber@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetVersionNumber(ushort const *)
0x180018ff3  mov     ebx, eax
0x180018ff5  test    eax, eax
0x180018ff7  js      loc_180018E9C
0x180018ffd  mov     rbx, [r13+20h]
0x180019001  test    rbx, rbx
0x180019004  jz      short loc_180018F99
0x180019006  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001900d  mov     rax, rdi
0x180019010  inc     rax
0x180019013  cmp     word ptr [rbx+rax*2], 0
0x180019018  jnz     short loc_180019010
0x18001901a  jmp     loc_180018EEA
0x18001901f  mov     ebx, 80070057h
0x180019024  jmp     loc_180018EB5
0x180019029  mov     rcx, cs:WPP_GLOBAL_Control
0x180019030  cmp     rcx, r15
0x180019033  jz      short loc_18001905E
0x180019035  test    byte ptr [rcx+1Ch], 4
0x180019039  jz      short loc_18001905E
0x18001903b  mov     rcx, [rcx+10h]
0x18001903f  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x180019046  mov     r9d, edi
0x180019049  mov     [rsp+58h+var_38], ebp
0x18001904d  mov     edx, 0Ah
0x180019052  call    WPP_SF_dd
0x180019057  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001905e  mov     rdi, rbp
0x180019061  jmp     loc_180018DF3
0x180019066  mov     ebx, 80070057h
0x18001906b  xor     r15d, r15d
0x18001906e  mov     [rax], r15w
0x180019072  mov     rdi, r15
0x180019075  mov     rcx, cs:WPP_GLOBAL_Control
0x18001907c  lea     rax, WPP_GLOBAL_Control
0x180019083  cmp     rcx, rax
0x180019086  jz      short loc_1800190A6
0x180019088  test    byte ptr [rcx+1Ch], 1
0x18001908c  jz      short loc_1800190A6
0x18001908e  mov     rcx, [rcx+10h]
0x180019092  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x180019099  mov     edx, 0Bh
0x18001909e  mov     r9d, ebx
0x1800190a1  call    WPP_SF_d
0x1800190a6  mov     rcx, r14; Block
0x1800190a9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800190ae  jmp     loc_180018E6F
0x1800190b3  mov     ebx, 80070057h
0x1800190b8  test    rdi, rdi
0x1800190bb  jnz     short loc_18001906B
0x1800190bd  xor     r15d, r15d
0x1800190c0  jmp     short loc_180019072
0x1800190c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190c9  lea     rdx, WPP_GLOBAL_Control
0x1800190d0  cmp     rcx, rdx
0x1800190d3  jz      loc_180018EF9
0x1800190d9  test    byte ptr [rcx+1Ch], 4
0x1800190dd  jz      loc_180018EF9
0x1800190e3  mov     rcx, [rcx+10h]
0x1800190e7  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x1800190ee  mov     r9d, eax
0x1800190f1  mov     [rsp+58h+var_38], ebp
0x1800190f5  mov     edx, 0Ah
0x1800190fa  call    WPP_SF_dd
0x1800190ff  jmp     loc_180018EF9
0x180019104  mov     ebx, 80070057h
0x180019109  jmp     short loc_180019115
0x18001910b  mov     ebx, 80070057h
0x180019110  test    rbp, rbp
0x180019113  jz      short loc_180019119
0x180019115  mov     [rax], r15w
0x180019119  mov     rdi, r15
0x18001911c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019123  lea     rax, WPP_GLOBAL_Control
0x18001912a  cmp     rcx, rax
0x18001912d  jz      short loc_18001914D
0x18001912f  test    byte ptr [rcx+1Ch], 1
0x180019133  jz      short loc_18001914D
0x180019135  mov     rcx, [rcx+10h]
0x180019139  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x180019140  mov     edx, 0Bh
0x180019145  mov     r9d, ebx
0x180019148  call    WPP_SF_d
0x18001914d  mov     rcx, r14; Block
0x180019150  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019155  jmp     loc_180018F76
0x18001915a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001915f  jmp     loc_180018F8C
0x180019164  test    byte ptr [rcx+1Ch], 1
0x180019168  jz      loc_180018FE0
0x18001916e  mov     rcx, [rcx+10h]
0x180019172  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x180019179  mov     edx, 0Ch
0x18001917e  call    WPP_SF_
0x180019183  jmp     loc_180018FE0
0x180019188  test    byte ptr [rcx+1Ch], 1
0x18001918c  jz      loc_180018ED8
0x180019192  mov     rcx, [rcx+10h]
0x180019196  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x18001919d  mov     edx, 0Ch
0x1800191a2  call    WPP_SF_
0x1800191a7  jmp     loc_180018ED8
```
