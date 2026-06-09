# BinXmlReader::NumTemplateInstanceValues(void)

- ea: `0x1800131e8`
- end: `0x180013390`
- name: `?NumTemplateInstanceValues@BinXmlReader@@QEAAKXZ`
- size: `424`
- prototype: `__int64 __fastcall(BinXmlReader *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007ae4`

## callees

- `0x1800131e8`
- `0x1800135c0`
- `0x180023548`
- `0x180038fa4`

## pseudocode

```c
__int64 __fastcall BinXmlReader::NumTemplateInstanceValues(BinXmlReader *this)
{
  __int64 v1; // rbx
  unsigned int v2; // ecx
  unsigned int v3; // eax
  unsigned int v4; // eax
  _QWORD v6[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 pExceptionObject; // [rsp+30h] [rbp-30h] BYREF
  __int64 v8; // [rsp+40h] [rbp-20h]
  int v9; // [rsp+48h] [rbp-18h]
  int v10; // [rsp+4Ch] [rbp-14h]
  int v11; // [rsp+50h] [rbp-10h]

  v1 = *((_QWORD *)this + 9);
  if ( *((_QWORD *)this + 8) == v1 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    v8 = 0;
    v9 = 13;
    v10 = -1;
    pExceptionObject = 0;
    v11 = 2185;
    throw (EvtException *)&pExceptionObject;
  }
  v6[0] = 0;
  v6[1] = 0;
  BinXmlReader::GetValueSpecStrm(this, (const struct BinXmlReader::TmplInstInfo *)(v1 - 32), (struct UserBuffer *)v6);
  v2 = *(_DWORD *)(v1 - 16);
  if ( !v2 )
    v2 = 4;
  v3 = *(_DWORD *)(v1 - 12);
  if ( v2 > v3 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    v8 = 0;
    v9 = 13;
    v10 = -1;
    pExceptionObject = 0;
    v11 = 2202;
    throw (EvtException *)&pExceptionObject;
  }
  v4 = v3 - v2;
  if ( (v4 & 3) != 0 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    v8 = 0;
    v9 = 13;
    v10 = -1;
    pExceptionObject = 0;
    v11 = 2209;
    throw (EvtException *)&pExceptionObject;
  }
  return v4 >> 2;
}

```

## disassembly

```asm
0x1800131e8  mov     [rsp-8+arg_0], rbx
0x1800131ed  push    rbp
0x1800131ee  mov     rbp, rsp
0x1800131f1  sub     rsp, 60h
0x1800131f5  mov     rbx, [rcx+48h]
0x1800131f9  cmp     [rcx+40h], rbx
0x1800131fd  jz      short loc_18001324C
0x1800131ff  lea     r8, [rbp+var_40]; struct UserBuffer *
0x180013203  mov     [rbp+var_40], 0
0x18001320b  lea     rdx, [rbx-20h]; struct BinXmlReader::TmplInstInfo *
0x18001320f  mov     [rbp+var_38], 0
0x180013217  call    ?GetValueSpecStrm@BinXmlReader@@AEAAXAEBUTmplInstInfo@1@AEAVUserBuffer@@@Z; BinXmlReader::GetValueSpecStrm(BinXmlReader::TmplInstInfo const &,UserBuffer &)
0x18001321c  mov     ecx, [rbx-10h]
0x18001321f  mov     eax, 4
0x180013224  test    ecx, ecx
0x180013226  cmovz   ecx, eax
0x180013229  mov     eax, [rbx-0Ch]
0x18001322c  cmp     ecx, eax
0x18001322e  ja      loc_1800132B8
0x180013234  sub     eax, ecx
0x180013236  test    al, 3
0x180013238  jnz     loc_180013324
0x18001323e  mov     rbx, [rsp+60h+arg_0]
0x180013243  shr     eax, 2
0x180013246  add     rsp, 60h
0x18001324a  pop     rbp
0x18001324b  retn
0x18001324c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013253  lea     rax, WPP_GLOBAL_Control
0x18001325a  mov     ebx, 0Dh
0x18001325f  cmp     rcx, rax
0x180013262  jz      short loc_180013286
0x180013264  test    byte ptr [rcx+1Ch], 2
0x180013268  jz      short loc_180013286
0x18001326a  cmp     byte ptr [rcx+19h], 2
0x18001326e  jb      short loc_180013286
0x180013270  mov     rcx, [rcx+10h]
0x180013274  lea     edx, [rbx+1Dh]
0x180013277  mov     r9d, ebx
0x18001327a  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180013281  call    WPP_SF_D
0x180013286  xorps   xmm0, xmm0
0x180013289  mov     [rbp+var_20], 0
0x180013291  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180013298  mov     [rbp+var_18], ebx
0x18001329b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001329f  mov     [rbp+var_14], 0FFFFFFFFh
0x1800132a6  movdqu  [rbp+pExceptionObject], xmm0
0x1800132ab  mov     [rbp+var_10], 889h
0x1800132b2  call    _CxxThrowException_0
0x1800132b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132bf  lea     rax, WPP_GLOBAL_Control
0x1800132c6  mov     ebx, 0Dh
0x1800132cb  cmp     rcx, rax
0x1800132ce  jz      short loc_1800132F2
0x1800132d0  test    byte ptr [rcx+1Ch], 2
0x1800132d4  jz      short loc_1800132F2
0x1800132d6  cmp     byte ptr [rcx+19h], 2
0x1800132da  jb      short loc_1800132F2
0x1800132dc  mov     rcx, [rcx+10h]
0x1800132e0  lea     edx, [rbx+1Eh]
0x1800132e3  mov     r9d, ebx
0x1800132e6  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x1800132ed  call    WPP_SF_D
0x1800132f2  xorps   xmm0, xmm0
0x1800132f5  mov     [rbp+var_20], 0
0x1800132fd  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180013304  mov     [rbp+var_18], ebx
0x180013307  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001330b  mov     [rbp+var_14], 0FFFFFFFFh
0x180013312  movdqu  [rbp+pExceptionObject], xmm0
0x180013317  mov     [rbp+var_10], 89Ah
0x18001331e  call    _CxxThrowException_0
0x180013324  mov     rcx, cs:WPP_GLOBAL_Control
0x18001332b  lea     rax, WPP_GLOBAL_Control
0x180013332  mov     ebx, 0Dh
0x180013337  cmp     rcx, rax
0x18001333a  jz      short loc_18001335E
0x18001333c  test    byte ptr [rcx+1Ch], 2
0x180013340  jz      short loc_18001335E
0x180013342  cmp     byte ptr [rcx+19h], 2
0x180013346  jb      short loc_18001335E
0x180013348  mov     rcx, [rcx+10h]
0x18001334c  lea     edx, [rbx+1Fh]
0x18001334f  mov     r9d, ebx
0x180013352  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180013359  call    WPP_SF_D
0x18001335e  xorps   xmm0, xmm0
0x180013361  mov     [rbp+var_20], 0
0x180013369  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180013370  mov     [rbp+var_18], ebx
0x180013373  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013377  mov     [rbp+var_14], 0FFFFFFFFh
0x18001337e  movdqu  [rbp+pExceptionObject], xmm0
0x180013383  mov     [rbp+var_10], 8A1h
0x18001338a  call    _CxxThrowException_0
```
