# BinXmlReader::NextReaderData(void)

- ea: `0x1800058f4`
- end: `0x180005acc`
- name: `?NextReaderData@BinXmlReader@@AEAAXXZ`
- size: `472`
- prototype: `void __fastcall(BinXmlReader *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003a68`
- `0x180003dc0`
- `0x180004070`
- `0x1800071b0`
- `0x180024428`

## callees

- `0x1800058f4`
- `0x18001e384`
- `0x180023548`
- `0x180038fa4`

## pseudocode

```c
void __fastcall BinXmlReader::NextReaderData(BinXmlReader *this)
{
  __int64 v2; // rax
  __int64 v3; // r14
  __int64 v4; // rsi
  int v5; // ecx
  __int64 v6; // rax
  __int16 v7; // ax
  __int64 v8; // rcx
  _OWORD *v9; // rax
  __int64 *v10; // rax
  __int128 v11; // xmm1
  __int128 pExceptionObject; // [rsp+20h] [rbp-30h] BYREF
  __int128 v13; // [rsp+30h] [rbp-20h]
  int v14; // [rsp+40h] [rbp-10h]

  v2 = (unsigned int)++*((_DWORD *)this + 9);
  if ( (unsigned int)v2 >= *((_DWORD *)this + 8) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    *((_QWORD *)&v13 + 1) = -4294967283LL;
    *(_QWORD *)&v13 = 0;
    v14 = 706;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v3 = *((_QWORD *)this + 3);
  v4 = 5 * v2;
  if ( !*(_QWORD *)(v3 + 40 * v2) )
  {
    *((_BYTE *)this + 188) = 0;
    v5 = *(_DWORD *)(v3 + 40 * v2 + 16);
    v6 = *(_QWORD *)(v3 + 40 * v2 + 8);
LABEL_4:
    *((_QWORD *)this + 2) = this;
    goto LABEL_5;
  }
  if ( !*(_QWORD *)(v3 + 40 * v2 + 16) && !*(_QWORD *)(v3 + 40 * v2 + 32) )
  {
    *((_BYTE *)this + 188) = 1;
    v10 = *(__int64 **)(v3 + 40 * v2);
    v5 = *((_DWORD *)v10 + 2);
    v6 = *v10;
    goto LABEL_4;
  }
  v7 = *((_WORD *)this + 18);
  *((_BYTE *)this + 188) = 0;
  WORD4(v13) = v7;
  WORD5(v13) = 1;
  v8 = *(_QWORD *)(v3 + 8 * v4);
  *(_QWORD *)&v13 = 0;
  DWORD2(pExceptionObject) = 0;
  *(_QWORD *)&pExceptionObject = *(_QWORD *)v8;
  HIDWORD(pExceptionObject) = *(_DWORD *)(v8 + 8);
  v9 = (_OWORD *)*((_QWORD *)this + 9);
  if ( v9 == *((_OWORD **)this + 10) )
  {
    if ( !(unsigned __int8)utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::_PushBackOne2<BinXmlReader::TmplInstInfo>(
                             (char *)this + 64,
                             &pExceptionObject) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 14);
      }
      *(_QWORD *)&v13 = 0;
      *((_QWORD *)&v13 + 1) = -4294967282LL;
      pExceptionObject = 0;
      v14 = 762;
      throw (EvtException *)&pExceptionObject;
    }
  }
  else
  {
    v11 = v13;
    *v9 = pExceptionObject;
    v9[1] = v11;
    *((_QWORD *)this + 9) += 32LL;
  }
  *((_QWORD *)this + 2) = *((_QWORD *)this + 9) - 32LL;
  v5 = *(_DWORD *)(v3 + 8 * v4 + 16);
  v6 = *(_QWORD *)(v3 + 8 * v4 + 8);
LABEL_5:
  *(_QWORD *)this = v6;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 3) = v5;
}

```

## disassembly

```asm
0x1800058f4  push    rbp
0x1800058f6  push    rbx
0x1800058f7  push    rsi
0x1800058f8  push    rdi
0x1800058f9  push    r14
0x1800058fb  mov     rbp, rsp
0x1800058fe  sub     rsp, 50h
0x180005902  mov     rbx, rcx
0x180005905  mov     ecx, 1
0x18000590a  add     [rbx+24h], ecx
0x18000590d  mov     eax, [rbx+24h]
0x180005910  cmp     eax, [rbx+20h]
0x180005913  jnb     loc_180005A33
0x180005919  mov     r14, [rbx+18h]
0x18000591d  lea     rsi, [rax+rax*4]
0x180005921  xor     edi, edi
0x180005923  cmp     [r14+rsi*8], rdi
0x180005927  jnz     short loc_180005952
0x180005929  mov     [rbx+0BCh], dil
0x180005930  mov     ecx, [r14+rsi*8+10h]
0x180005935  mov     rax, [r14+rsi*8+8]
0x18000593a  mov     [rbx+10h], rbx
0x18000593e  mov     [rbx], rax
0x180005941  mov     [rbx+8], edi
0x180005944  mov     [rbx+0Ch], ecx
0x180005947  add     rsp, 50h
0x18000594b  pop     r14
0x18000594d  pop     rdi
0x18000594e  pop     rsi
0x18000594f  pop     rbx
0x180005950  pop     rbp
0x180005951  retn
0x180005952  cmp     [r14+rsi*8+10h], rdi
0x180005957  jz      loc_180005A13
0x18000595d  movzx   eax, word ptr [rbx+24h]
0x180005961  mov     [rbx+0BCh], dil
0x180005968  mov     word ptr [rbp+var_20+8], ax
0x18000596c  mov     word ptr [rbp+var_20+0Ah], cx
0x180005970  mov     rcx, [r14+rsi*8]
0x180005974  mov     qword ptr [rbp+var_20], rdi
0x180005978  mov     dword ptr [rbp+pExceptionObject+8], edi
0x18000597b  mov     rax, [rcx]
0x18000597e  mov     qword ptr [rbp+pExceptionObject], rax
0x180005982  mov     eax, [rcx+8]
0x180005985  lea     rcx, [rbx+40h]
0x180005989  mov     dword ptr [rbp+pExceptionObject+0Ch], eax
0x18000598c  mov     rax, [rcx+8]
0x180005990  cmp     rax, [rcx+10h]
0x180005994  jnz     loc_180005A9D
0x18000599a  lea     rdx, [rbp+pExceptionObject]
0x18000599e  call    ??$_PushBackOne2@UTmplInstInfo@BinXmlReader@@@?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@AEAA_N$$QEAUTmplInstInfo@BinXmlReader@@@Z; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::_PushBackOne2<BinXmlReader::TmplInstInfo>(BinXmlReader::TmplInstInfo &&)
0x1800059a3  test    al, al
0x1800059a5  jnz     loc_180005AB1
0x1800059ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059b2  lea     rax, WPP_GLOBAL_Control
0x1800059b9  mov     ebx, 0Eh
0x1800059be  cmp     rcx, rax
0x1800059c1  jz      short loc_1800059E5
0x1800059c3  test    byte ptr [rcx+1Ch], 2
0x1800059c7  jz      short loc_1800059E5
0x1800059c9  cmp     byte ptr [rcx+19h], 2
0x1800059cd  jb      short loc_1800059E5
0x1800059cf  mov     rcx, [rcx+10h]
0x1800059d3  lea     edx, [rbx+6]
0x1800059d6  mov     r9d, ebx
0x1800059d9  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x1800059e0  call    WPP_SF_D
0x1800059e5  xorps   xmm0, xmm0
0x1800059e8  mov     qword ptr [rbp+var_20], rdi
0x1800059ec  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800059f3  mov     dword ptr [rbp+var_20+8], ebx
0x1800059f6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800059fa  mov     dword ptr [rbp+var_20+0Ch], 0FFFFFFFFh
0x180005a01  movdqu  [rbp+pExceptionObject], xmm0
0x180005a06  mov     [rbp+var_10], 2FAh
0x180005a0d  call    _CxxThrowException_0
0x180005a13  cmp     [r14+rsi*8+20h], rdi
0x180005a18  jnz     loc_18000595D
0x180005a1e  mov     [rbx+0BCh], cl
0x180005a24  mov     rax, [r14+rsi*8]
0x180005a28  mov     ecx, [rax+8]
0x180005a2b  mov     rax, [rax]
0x180005a2e  jmp     loc_18000593A
0x180005a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a3a  lea     rax, WPP_GLOBAL_Control
0x180005a41  mov     ebx, 0Dh
0x180005a46  cmp     rcx, rax
0x180005a49  jz      short loc_180005A6D
0x180005a4b  test    byte ptr [rcx+1Ch], 2
0x180005a4f  jz      short loc_180005A6D
0x180005a51  cmp     byte ptr [rcx+19h], 2
0x180005a55  jb      short loc_180005A6D
0x180005a57  mov     rcx, [rcx+10h]
0x180005a5b  lea     edx, [rbx+6]
0x180005a5e  mov     r9d, ebx
0x180005a61  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180005a68  call    WPP_SF_D
0x180005a6d  xorps   xmm0, xmm0
0x180005a70  mov     dword ptr [rbp+var_20+8], ebx
0x180005a73  xor     edi, edi
0x180005a75  mov     dword ptr [rbp+var_20+0Ch], 0FFFFFFFFh
0x180005a7c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180005a83  mov     qword ptr [rbp+var_20], rdi
0x180005a87  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180005a8b  mov     [rbp+var_10], 2C2h
0x180005a92  movdqu  [rbp+pExceptionObject], xmm0
0x180005a97  call    _CxxThrowException_0
0x180005a9d  movups  xmm0, [rbp+pExceptionObject]
0x180005aa1  movups  xmm1, [rbp+var_20]
0x180005aa5  movups  xmmword ptr [rax], xmm0
0x180005aa8  movups  xmmword ptr [rax+10h], xmm1
0x180005aac  add     qword ptr [rcx+8], 20h ; ' '
0x180005ab1  mov     rax, [rbx+48h]
0x180005ab5  sub     rax, 20h ; ' '
0x180005ab9  mov     [rbx+10h], rax
0x180005abd  mov     ecx, [r14+rsi*8+10h]
0x180005ac2  mov     rax, [r14+rsi*8+8]
0x180005ac7  jmp     loc_18000593E
```
