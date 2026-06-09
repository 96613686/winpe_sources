# BinXmlReader::StartTemplateInstanceToken(void)

- ea: `0x180005ad4`
- end: `0x180005c4c`
- name: `?StartTemplateInstanceToken@BinXmlReader@@AEAAXXZ`
- size: `376`
- prototype: `void __fastcall(BinXmlReader *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180004070`

## callees

- `0x180005ad4`
- `0x180013830`
- `0x18001e384`
- `0x1800231d0`
- `0x180023548`
- `0x180024a50`
- `0x180038fa4`

## pseudocode

```c
void __fastcall BinXmlReader::StartTemplateInstanceToken(BinXmlReader *this)
{
  __int64 *v2; // r8
  __int64 v3; // r9
  __int64 v4; // rax
  int v5; // edx
  _OWORD *v6; // rax
  __int128 v7; // xmm1
  __int128 pExceptionObject; // [rsp+20h] [rbp-60h] BYREF
  __int128 v9; // [rsp+30h] [rbp-50h]
  int v10; // [rsp+40h] [rbp-40h]
  __int64 v11; // [rsp+48h] [rbp-38h] BYREF
  __int64 v12; // [rsp+50h] [rbp-30h]
  __int128 v13; // [rsp+58h] [rbp-28h]
  __int128 v14; // [rsp+68h] [rbp-18h]

  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  BinXmlReader::ReadTemplateDefinition(this, (struct BinXmlTemplate *)&v11);
  v2 = (__int64 *)*((_QWORD *)this + 2);
  v3 = *((unsigned int *)v2 + 2);
  if ( (unsigned int)(*((_DWORD *)v2 + 3) - v3) < 4 )
    UserBuffer::ThrowUnexpectedEOFException();
  v4 = *v2;
  DWORD2(pExceptionObject) = 0;
  v5 = *(_DWORD *)(v3 + v4);
  *((_DWORD *)v2 + 2) = v3 + 4;
  LODWORD(v9) = *(_DWORD *)(*((_QWORD *)this + 2) + 8LL);
  DWORD1(v9) = v9 + 4 * v5;
  WORD4(v9) = *((_WORD *)this + 18);
  *(_QWORD *)&pExceptionObject = v11;
  LOWORD(v4) = ((__int64)(unsigned int)(*((_DWORD *)this + 12) - *((_DWORD *)this + 10)) >> 4) + 1;
  HIDWORD(pExceptionObject) = v12;
  WORD5(v9) = v4;
  v6 = (_OWORD *)*((_QWORD *)this + 9);
  if ( v6 == *((_OWORD **)this + 10) )
  {
    if ( !(unsigned __int8)utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::_PushBackOne2<BinXmlReader::TmplInstInfo>(
                             (char *)this + 64,
                             &pExceptionObject) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 14);
      }
      *(_QWORD *)&v9 = 0;
      *((_QWORD *)&v9 + 1) = -4294967282LL;
      pExceptionObject = 0;
      v10 = 1444;
      throw (EvtException *)&pExceptionObject;
    }
  }
  else
  {
    v7 = v9;
    *v6 = pExceptionObject;
    v6[1] = v7;
    *((_QWORD *)this + 9) += 32LL;
  }
  *((_QWORD *)this + 2) = *((_QWORD *)this + 9) - 32LL;
}

```

## disassembly

```asm
0x180005ad4  mov     [rsp-8+arg_8], rbx
0x180005ad9  push    rbp
0x180005ada  mov     rbp, rsp
0x180005add  sub     rsp, 80h
0x180005ae4  mov     rax, cs:__security_cookie
0x180005aeb  xor     rax, rsp
0x180005aee  mov     [rbp+var_8], rax
0x180005af2  xorps   xmm0, xmm0
0x180005af5  mov     [rbp+var_38], 0
0x180005afd  xorps   xmm1, xmm1
0x180005b00  mov     [rbp+var_30], 0
0x180005b08  lea     rdx, [rbp+var_38]; struct BinXmlTemplate *
0x180005b0c  mov     rbx, rcx
0x180005b0f  movups  [rbp+var_28], xmm0
0x180005b13  movdqu  [rbp+var_18], xmm1
0x180005b18  call    ?ReadTemplateDefinition@BinXmlReader@@QEAAXAEAVBinXmlTemplate@@@Z; BinXmlReader::ReadTemplateDefinition(BinXmlTemplate &)
0x180005b1d  mov     r8, [rbx+10h]
0x180005b21  mov     r9d, [r8+8]
0x180005b25  mov     eax, [r8+0Ch]
0x180005b29  sub     eax, r9d
0x180005b2c  cmp     eax, 4
0x180005b2f  jb      loc_180005BCD
0x180005b35  mov     rax, [r8]
0x180005b38  mov     dword ptr [rbp+pExceptionObject+8], 0
0x180005b3f  mov     edx, [r9+rax]
0x180005b43  lea     eax, [r9+4]
0x180005b47  mov     [r8+8], eax
0x180005b4b  mov     rax, [rbx+10h]
0x180005b4f  mov     ecx, [rax+8]
0x180005b52  mov     dword ptr [rbp+var_50], ecx
0x180005b55  lea     eax, [rcx+rdx*4]
0x180005b58  mov     ecx, dword ptr [rbp+var_30]
0x180005b5b  mov     dword ptr [rbp+var_50+4], eax
0x180005b5e  movzx   eax, word ptr [rbx+24h]
0x180005b62  mov     word ptr [rbp+var_50+8], ax
0x180005b66  mov     rax, [rbp+var_38]
0x180005b6a  mov     qword ptr [rbp+pExceptionObject], rax
0x180005b6e  mov     eax, [rbx+30h]
0x180005b71  sub     eax, [rbx+28h]
0x180005b74  sar     rax, 4
0x180005b78  inc     ax
0x180005b7b  mov     dword ptr [rbp+pExceptionObject+0Ch], ecx
0x180005b7e  lea     rcx, [rbx+40h]
0x180005b82  mov     word ptr [rbp+var_50+0Ah], ax
0x180005b86  mov     rax, [rcx+8]
0x180005b8a  cmp     rax, [rcx+10h]
0x180005b8e  jz      short loc_180005BD3
0x180005b90  movups  xmm0, [rbp+pExceptionObject]
0x180005b94  movups  xmm1, [rbp+var_50]
0x180005b98  movups  xmmword ptr [rax], xmm0
0x180005b9b  movups  xmmword ptr [rax+10h], xmm1
0x180005b9f  add     qword ptr [rcx+8], 20h ; ' '
0x180005ba4  mov     rax, [rbx+48h]
0x180005ba8  sub     rax, 20h ; ' '
0x180005bac  mov     [rbx+10h], rax
0x180005bb0  mov     rcx, [rbp+var_8]
0x180005bb4  xor     rcx, rsp; StackCookie
0x180005bb7  call    __security_check_cookie
0x180005bbc  mov     rbx, [rsp+80h+arg_8]
0x180005bc4  add     rsp, 80h
0x180005bcb  pop     rbp
0x180005bcc  retn
0x180005bcd  call    ?ThrowUnexpectedEOFException@UserBuffer@@CAXXZ; UserBuffer::ThrowUnexpectedEOFException(void)
0x180005bd3  lea     rdx, [rbp+pExceptionObject]
0x180005bd7  call    ??$_PushBackOne2@UTmplInstInfo@BinXmlReader@@@?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@AEAA_N$$QEAUTmplInstInfo@BinXmlReader@@@Z; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::_PushBackOne2<BinXmlReader::TmplInstInfo>(BinXmlReader::TmplInstInfo &&)
0x180005bdc  test    al, al
0x180005bde  jnz     short loc_180005BA4
0x180005be0  mov     rcx, cs:WPP_GLOBAL_Control
0x180005be7  lea     rax, WPP_GLOBAL_Control
0x180005bee  mov     ebx, 0Eh
0x180005bf3  cmp     rcx, rax
0x180005bf6  jz      short loc_180005C1A
0x180005bf8  test    byte ptr [rcx+1Ch], 2
0x180005bfc  jz      short loc_180005C1A
0x180005bfe  cmp     byte ptr [rcx+19h], 2
0x180005c02  jb      short loc_180005C1A
0x180005c04  mov     rcx, [rcx+10h]
0x180005c08  lea     edx, [rbx+17h]
0x180005c0b  mov     r9d, ebx
0x180005c0e  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180005c15  call    WPP_SF_D
0x180005c1a  xorps   xmm0, xmm0
0x180005c1d  mov     qword ptr [rbp+var_50], 0
0x180005c25  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180005c2c  mov     dword ptr [rbp+var_50+8], ebx
0x180005c2f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180005c33  mov     dword ptr [rbp+var_50+0Ch], 0FFFFFFFFh
0x180005c3a  movdqu  [rbp+pExceptionObject], xmm0
0x180005c3f  mov     [rbp+var_40], 5A4h
0x180005c46  call    _CxxThrowException_0
```
