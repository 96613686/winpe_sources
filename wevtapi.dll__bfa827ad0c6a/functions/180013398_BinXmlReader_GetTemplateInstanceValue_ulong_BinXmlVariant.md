# BinXmlReader::GetTemplateInstanceValue(ulong,BinXmlVariant &)

- ea: `0x180013398`
- end: `0x1800135ae`
- name: `?GetTemplateInstanceValue@BinXmlReader@@QEAAXKAEAUBinXmlVariant@@@Z`
- size: `534`
- prototype: `void __fastcall(BinXmlReader *__hidden this, unsigned int, struct BinXmlVariant *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180007ae4`

## callees

- `0x180004e70`
- `0x180013398`
- `0x1800135c0`
- `0x180013630`
- `0x1800231d0`
- `0x180023548`
- `0x180038fa4`

## pseudocode

```c
void __fastcall BinXmlReader::GetTemplateInstanceValue(BinXmlReader *this, unsigned int a2, struct BinXmlVariant *a3)
{
  __int64 v3; // rax
  __int64 v7; // r14
  unsigned int v8; // ebx
  unsigned int v9; // eax
  unsigned int v10; // r8d
  unsigned int v11; // ecx
  __int64 v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // [rsp+20h] [rbp-48h] BYREF
  __int64 v15; // [rsp+28h] [rbp-40h]
  __int128 pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int64 v17; // [rsp+40h] [rbp-28h]
  int v18; // [rsp+48h] [rbp-20h]
  int v19; // [rsp+4Ch] [rbp-1Ch]
  int v20; // [rsp+50h] [rbp-18h]

  v3 = *((_QWORD *)this + 9);
  if ( *((_QWORD *)this + 8) == v3 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    v18 = 13;
    v19 = -1;
    v17 = 0;
    v20 = 2219;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v7 = v3 - 32;
  v8 = 0;
  v14 = 0;
  v15 = 0;
  BinXmlReader::GetValueSpecStrm(this, (const struct BinXmlReader::TmplInstInfo *)(v3 - 32), (struct UserBuffer *)&v14);
  v9 = *(_DWORD *)(v7 + 16);
  if ( !v9 )
    v9 = 4;
  if ( v9 >= HIDWORD(v15) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    v17 = 0;
    v18 = 13;
    v19 = -1;
    pExceptionObject = 0;
    v20 = 2236;
    throw (EvtException *)&pExceptionObject;
  }
  if ( HIDWORD(v15) - v9 < 4 * a2 + 4 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    v17 = 0;
    v18 = 13;
    v19 = -1;
    pExceptionObject = 0;
    v20 = 2241;
    throw (EvtException *)&pExceptionObject;
  }
  v10 = *(_DWORD *)(v7 + 20);
  v11 = v15;
  if ( a2 )
  {
    while ( HIDWORD(v15) - v11 >= 4 )
    {
      v12 = v11;
      ++v8;
      v11 += 4;
      v10 += *(unsigned __int16 *)(v12 + v14);
      if ( v8 >= a2 )
        goto LABEL_9;
    }
LABEL_11:
    UserBuffer::ThrowUnexpectedEOFException();
  }
LABEL_9:
  if ( HIDWORD(v15) - v11 < 4 )
    goto LABEL_11;
  v13 = *(_DWORD *)(v11 + v14);
  *((_DWORD *)a3 + 3) = HIWORD(v13);
  UserBuffer::SetCurrentIndex(this, v10);
  BinXmlReader::NextValueData(this, this, a3, (unsigned __int16)v13);
}

```

## disassembly

```asm
0x180013398  push    rbp
0x18001339a  push    rbx
0x18001339b  push    rsi
0x18001339c  push    rdi
0x18001339d  push    r14
0x18001339f  push    r15
0x1800133a1  mov     rbp, rsp
0x1800133a4  sub     rsp, 68h
0x1800133a8  mov     rax, [rcx+48h]
0x1800133ac  mov     r15, r8
0x1800133af  mov     esi, edx
0x1800133b1  mov     rdi, rcx
0x1800133b4  cmp     [rcx+40h], rax
0x1800133b8  jz      loc_180013474
0x1800133be  lea     r14, [rax-20h]
0x1800133c2  xor     ebx, ebx
0x1800133c4  mov     rdx, r14; struct BinXmlReader::TmplInstInfo *
0x1800133c7  mov     [rbp+var_48], rbx
0x1800133cb  lea     r8, [rbp+var_48]; struct UserBuffer *
0x1800133cf  mov     [rbp+var_40], rbx
0x1800133d3  call    ?GetValueSpecStrm@BinXmlReader@@AEAAXAEBUTmplInstInfo@1@AEAVUserBuffer@@@Z; BinXmlReader::GetValueSpecStrm(BinXmlReader::TmplInstInfo const &,UserBuffer &)
0x1800133d8  mov     eax, [r14+10h]
0x1800133dc  lea     r10d, [rbx+4]
0x1800133e0  mov     edx, dword ptr [rbp+var_40+4]
0x1800133e3  test    eax, eax
0x1800133e5  cmovz   eax, r10d
0x1800133e9  cmp     eax, edx
0x1800133eb  jnb     loc_1800134DE
0x1800133f1  mov     ecx, edx
0x1800133f3  sub     ecx, eax
0x1800133f5  lea     eax, ds:4[rsi*4]
0x1800133fc  cmp     ecx, eax
0x1800133fe  jb      loc_180013546
0x180013404  mov     r8d, [r14+14h]
0x180013408  mov     r9, [rbp+var_48]
0x18001340c  mov     ecx, dword ptr [rbp+var_40]
0x18001340f  test    esi, esi
0x180013411  jz      short loc_18001342F
0x180013413  mov     eax, edx
0x180013415  sub     eax, ecx
0x180013417  cmp     eax, r10d
0x18001341a  jb      short loc_18001346E
0x18001341c  mov     eax, ecx
0x18001341e  inc     ebx
0x180013420  add     ecx, r10d
0x180013423  movzx   eax, word ptr [rax+r9]
0x180013428  add     r8d, eax
0x18001342b  cmp     ebx, esi
0x18001342d  jb      short loc_180013413
0x18001342f  sub     edx, ecx
0x180013431  cmp     edx, r10d
0x180013434  jb      short loc_18001346E
0x180013436  mov     eax, ecx
0x180013438  mov     edx, r8d; unsigned int
0x18001343b  mov     rcx, rdi; this
0x18001343e  mov     ebx, [rax+r9]
0x180013442  mov     eax, ebx
0x180013444  shr     eax, 10h
0x180013447  mov     [r15+0Ch], eax
0x18001344b  call    ?SetCurrentIndex@UserBuffer@@QEAAXK@Z; UserBuffer::SetCurrentIndex(ulong)
0x180013450  movzx   r9d, bx; unsigned int
0x180013454  mov     r8, r15; struct BinXmlVariant *
0x180013457  mov     rdx, rdi; struct UserBuffer *
0x18001345a  mov     rcx, rdi; this
0x18001345d  add     rsp, 68h
0x180013461  pop     r15
0x180013463  pop     r14
0x180013465  pop     rdi
0x180013466  pop     rsi
0x180013467  pop     rbx
0x180013468  pop     rbp
0x180013469  jmp     ?NextValueData@BinXmlReader@@AEAAXAEAVUserBuffer@@AEAUBinXmlVariant@@K@Z; BinXmlReader::NextValueData(UserBuffer &,BinXmlVariant &,ulong)
0x18001346e  call    ?ThrowUnexpectedEOFException@UserBuffer@@CAXXZ; UserBuffer::ThrowUnexpectedEOFException(void)
0x180013474  mov     rcx, cs:WPP_GLOBAL_Control
0x18001347b  lea     rax, WPP_GLOBAL_Control
0x180013482  mov     edi, 0Dh
0x180013487  cmp     rcx, rax
0x18001348a  jz      short loc_1800134AE
0x18001348c  test    byte ptr [rcx+1Ch], 2
0x180013490  jz      short loc_1800134AE
0x180013492  cmp     byte ptr [rcx+19h], 2
0x180013496  jb      short loc_1800134AE
0x180013498  mov     rcx, [rcx+10h]
0x18001349c  lea     edx, [rdi+20h]
0x18001349f  mov     r9d, edi
0x1800134a2  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x1800134a9  call    WPP_SF_D
0x1800134ae  xorps   xmm0, xmm0
0x1800134b1  mov     [rbp+var_20], edi
0x1800134b4  xor     ebx, ebx
0x1800134b6  mov     [rbp+var_1C], 0FFFFFFFFh
0x1800134bd  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800134c4  mov     [rbp+var_28], rbx
0x1800134c8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800134cc  mov     [rbp+var_18], 8ABh
0x1800134d3  movdqu  [rbp+pExceptionObject], xmm0
0x1800134d8  call    _CxxThrowException_0
0x1800134de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134e5  lea     rax, WPP_GLOBAL_Control
0x1800134ec  mov     edi, 0Dh
0x1800134f1  cmp     rcx, rax
0x1800134f4  jz      short loc_180013518
0x1800134f6  test    byte ptr [rcx+1Ch], 2
0x1800134fa  jz      short loc_180013518
0x1800134fc  cmp     byte ptr [rcx+19h], 2
0x180013500  jb      short loc_180013518
0x180013502  mov     rcx, [rcx+10h]
0x180013506  lea     edx, [rdi+21h]
0x180013509  mov     r9d, edi
0x18001350c  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180013513  call    WPP_SF_D
0x180013518  xorps   xmm0, xmm0
0x18001351b  mov     [rbp+var_28], rbx
0x18001351f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180013526  mov     [rbp+var_20], edi
0x180013529  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001352d  mov     [rbp+var_1C], 0FFFFFFFFh
0x180013534  movdqu  [rbp+pExceptionObject], xmm0
0x180013539  mov     [rbp+var_18], 8BCh
0x180013540  call    _CxxThrowException_0
0x180013546  mov     rcx, cs:WPP_GLOBAL_Control
0x18001354d  lea     rax, WPP_GLOBAL_Control
0x180013554  mov     edi, 0Dh
0x180013559  cmp     rcx, rax
0x18001355c  jz      short loc_180013580
0x18001355e  test    byte ptr [rcx+1Ch], 2
0x180013562  jz      short loc_180013580
0x180013564  cmp     byte ptr [rcx+19h], 2
0x180013568  jb      short loc_180013580
0x18001356a  mov     rcx, [rcx+10h]
0x18001356e  lea     edx, [rdi+22h]
0x180013571  mov     r9d, edi
0x180013574  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x18001357b  call    WPP_SF_D
0x180013580  xorps   xmm0, xmm0
0x180013583  mov     [rbp+var_28], rbx
0x180013587  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001358e  mov     [rbp+var_20], edi
0x180013591  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013595  mov     [rbp+var_1C], 0FFFFFFFFh
0x18001359c  movdqu  [rbp+pExceptionObject], xmm0
0x1800135a1  mov     [rbp+var_18], 8C1h
0x1800135a8  call    _CxxThrowException_0
```
