# PublisherConfigWriteData::AddChannelReference(wchar_t const *,ulong,ulong)

- ea: `0x1400034c4`
- end: `0x1400036f6`
- name: `?AddChannelReference@PublisherConfigWriteData@@QEAAXPEB_WKK@Z`
- size: `562`
- prototype: `void __fastcall(PublisherConfigWriteData *__hidden this, const wchar_t *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140001738`

## callees

- `0x1400034c4`
- `0x140003700`
- `0x140004ae0`
- `0x140005600`
- `0x140022cec`
- `0x14002c880`
- `0x14002c920`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140003571`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140003571`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PublisherConfigWriteData::AddChannelReference(
        PublisherConfigWriteData *this,
        const wchar_t *a2,
        const char *a3,
        int a4)
{
  int v5; // r13d
  _QWORD *v8; // rsi
  _QWORD *v9; // rdi
  _QWORD *i; // rbx
  const char *v11; // r8
  _QWORD *v12; // rcx
  _QWORD *v13; // rbx
  _BYTE *v14; // rdx
  const char *v15; // r8
  _BYTE *v16; // r8
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-49h] BYREF
  _BYTE v18[32]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v19; // [rsp+68h] [rbp-1h]
  int v20; // [rsp+70h] [rbp+7h]

  v5 = (int)a3;
  v8 = (_QWORD *)((char *)this + 160);
  v9 = (_QWORD *)((char *)this + 168);
  if ( *((_BYTE *)this + 190) )
  {
    for ( i = (_QWORD *)*v8; (_QWORD *)*v9 != i; i += 6 )
    {
      if ( !(unsigned int)_o__wcsicmp(*i, a2) )
        goto LABEL_3;
    }
  }
  else
  {
    i = (_QWORD *)*v9;
LABEL_3:
    if ( (_QWORD *)*v9 != i )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ff2da5a7c3d7353b6f9322ae42c4201e_Traceguids, 183);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xB7u, a3, 93);
      throw (EvtException *)pExceptionObject;
    }
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v18);
  v19 = 0;
  v20 = 0;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v18, a2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_ff2da5a7c3d7353b6f9322ae42c4201e_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v11, 99);
    throw (EvtException *)pExceptionObject;
  }
  LODWORD(v19) = v5;
  v12 = (_QWORD *)*v9;
  v13 = (_QWORD *)*v8;
  HIDWORD(v19) = -1431655765 * ((__int64)(*v9 - *v8) >> 4);
  v20 = a4;
  if ( v12 == (_QWORD *)v8[2] )
  {
    if ( !(unsigned __int8)utl::vector<ChannelReference,utl::allocator<ChannelReference>>::_Grow(v8) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ff2da5a7c3d7353b6f9322ae42c4201e_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v15, 107);
      throw (EvtException *)pExceptionObject;
    }
    v16 = v18;
    if ( (unsigned __int64)(v18 - (_BYTE *)v13) < *v9 - *v8 )
      v16 = (_BYTE *)(v18 - (_BYTE *)v13 + *v8);
    v14 = v16;
    v12 = (_QWORD *)*v9;
  }
  else
  {
    v14 = v18;
  }
  ChannelReference::ChannelReference(v12, v14);
  *v9 += 48LL;
  *((_BYTE *)this + 190) = 1;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v18);
}

```

## disassembly

```asm
0x1400034c4  push    rbp
0x1400034c6  push    rbx
0x1400034c7  push    rsi
0x1400034c8  push    rdi
0x1400034c9  push    r12
0x1400034cb  push    r13
0x1400034cd  push    r14
0x1400034cf  push    r15
0x1400034d1  lea     rbp, [rsp-1Fh]
0x1400034d6  sub     rsp, 88h
0x1400034dd  mov     r12d, r9d
0x1400034e0  mov     r13d, r8d
0x1400034e3  mov     r15, rdx
0x1400034e6  mov     r14, rcx
0x1400034e9  lea     rsi, [rcx+0A0h]
0x1400034f0  lea     rdi, [rsi+8]
0x1400034f4  cmp     byte ptr [rcx+0BEh], 0
0x1400034fb  jnz     short loc_140003563
0x1400034fd  mov     rbx, [rdi]
0x140003500  cmp     [rdi], rbx
0x140003503  jz      short loc_140003581
0x140003505  lea     rax, WPP_GLOBAL_Control
0x14000350c  mov     ebx, 0B7h
0x140003511  mov     rcx, cs:WPP_GLOBAL_Control
0x140003518  cmp     rcx, rax
0x14000351b  jz      short loc_140003541
0x14000351d  test    byte ptr [rcx+1Ch], 4
0x140003521  jz      short loc_140003541
0x140003523  cmp     byte ptr [rcx+19h], 2
0x140003527  jb      short loc_140003541
0x140003529  mov     edx, 10h
0x14000352e  mov     r9d, ebx
0x140003531  lea     r8, WPP_ff2da5a7c3d7353b6f9322ae42c4201e_Traceguids
0x140003538  mov     rcx, [rcx+10h]
0x14000353c  call    WPP_SF_d
0x140003541  mov     r9d, 5Dh ; ']'; int
0x140003547  mov     edx, ebx; unsigned int
0x140003549  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000354d  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140003552  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140003559  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000355d  call    _CxxThrowException_0
0x140003563  mov     rbx, [rsi]
0x140003566  cmp     [rdi], rbx
0x140003569  jz      short loc_140003581
0x14000356b  mov     rdx, r15
0x14000356e  mov     rcx, [rbx]
0x140003571  call    cs:__imp__o__wcsicmp
0x140003577  test    eax, eax
0x140003579  jz      short loc_140003500
0x14000357b  add     rbx, 30h ; '0'
0x14000357f  jmp     short loc_140003566
0x140003581  lea     rcx, [rbp+57h+var_78]
0x140003585  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14000358a  mov     [rbp+57h+var_58], 0
0x140003592  mov     [rbp+57h+var_50], 0
0x140003599  mov     rdx, r15
0x14000359c  lea     rcx, [rbp+57h+var_78]
0x1400035a0  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1400035a5  test    al, al
0x1400035a7  jnz     short loc_140003605
0x1400035a9  lea     rax, WPP_GLOBAL_Control
0x1400035b0  mov     ebx, 0Eh
0x1400035b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400035bc  cmp     rcx, rax
0x1400035bf  jz      short loc_1400035E3
0x1400035c1  test    byte ptr [rcx+1Ch], 4
0x1400035c5  jz      short loc_1400035E3
0x1400035c7  cmp     byte ptr [rcx+19h], 2
0x1400035cb  jb      short loc_1400035E3
0x1400035cd  lea     edx, [rbx+3]
0x1400035d0  mov     r9d, ebx
0x1400035d3  lea     r8, WPP_ff2da5a7c3d7353b6f9322ae42c4201e_Traceguids
0x1400035da  mov     rcx, [rcx+10h]
0x1400035de  call    WPP_SF_d
0x1400035e3  mov     r9d, 63h ; 'c'; int
0x1400035e9  mov     edx, ebx; unsigned int
0x1400035eb  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400035ef  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400035f4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400035fb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400035ff  call    _CxxThrowException_0
0x140003605  mov     dword ptr [rbp+57h+var_58], r13d
0x140003609  mov     rcx, [rdi]
0x14000360c  mov     rbx, [rsi]
0x14000360f  mov     rax, rcx
0x140003612  sub     rax, rbx
0x140003615  sar     rax, 4
0x140003619  mov     rdx, 0AAAAAAAAAAAAAAABh
0x140003623  imul    rax, rdx
0x140003627  mov     dword ptr [rbp+57h+var_58+4], eax
0x14000362a  mov     [rbp+57h+var_50], r12d
0x14000362e  cmp     rcx, [rsi+10h]
0x140003632  jz      short loc_14000363D
0x140003634  lea     rdx, [rbp+57h+var_78]
0x140003638  jmp     loc_1400036C8
0x14000363d  mov     rcx, rsi
0x140003640  call    ?_Grow@?$vector@UChannelReference@@V?$allocator@UChannelReference@@@utl@@@utl@@AEAA_NXZ; utl::vector<ChannelReference,utl::allocator<ChannelReference>>::_Grow(void)
0x140003645  test    al, al
0x140003647  jnz     short loc_1400036A5
0x140003649  lea     rax, WPP_GLOBAL_Control
0x140003650  mov     ebx, 0Eh
0x140003655  mov     rcx, cs:WPP_GLOBAL_Control
0x14000365c  cmp     rcx, rax
0x14000365f  jz      short loc_140003683
0x140003661  test    byte ptr [rcx+1Ch], 4
0x140003665  jz      short loc_140003683
0x140003667  cmp     byte ptr [rcx+19h], 2
0x14000366b  jb      short loc_140003683
0x14000366d  lea     edx, [rbx+4]
0x140003670  mov     r9d, ebx
0x140003673  lea     r8, WPP_ff2da5a7c3d7353b6f9322ae42c4201e_Traceguids
0x14000367a  mov     rcx, [rcx+10h]
0x14000367e  call    WPP_SF_d
0x140003683  mov     r9d, 6Bh ; 'k'; int
0x140003689  mov     edx, ebx; unsigned int
0x14000368b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000368f  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140003694  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000369b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000369f  call    _CxxThrowException_0
0x1400036a5  lea     r8, [rbp+57h+var_78]
0x1400036a9  lea     rdx, [rbp+57h+var_78]
0x1400036ad  sub     rdx, rbx
0x1400036b0  mov     r9, [rsi]
0x1400036b3  mov     rax, [rdi]
0x1400036b6  sub     rax, r9
0x1400036b9  cmp     rdx, rax
0x1400036bc  jnb     short loc_1400036C2
0x1400036be  lea     r8, [rdx+r9]
0x1400036c2  mov     rdx, r8
0x1400036c5  mov     rcx, [rdi]
0x1400036c8  call    ??0ChannelReference@@QEAA@$$QEAU0@@Z; ChannelReference::ChannelReference(ChannelReference &&)
0x1400036cd  add     qword ptr [rdi], 30h ; '0'
0x1400036d1  mov     byte ptr [r14+0BEh], 1
0x1400036d9  lea     rcx, [rbp+57h+var_78]
0x1400036dd  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400036e2  add     rsp, 88h
0x1400036e9  pop     r15
0x1400036eb  pop     r14
0x1400036ed  pop     r13
0x1400036ef  pop     r12
0x1400036f1  pop     rdi
0x1400036f2  pop     rsi
0x1400036f3  pop     rbx
0x1400036f4  pop     rbp
0x1400036f5  retn
```
