# PublisherTaskCollection::GetCount(void)

- ea: `0x18000f650`
- end: `0x18000f8e2`
- name: `?GetCount@PublisherTaskCollection@@UEBAKXZ`
- size: `658`
- prototype: `__int64 __fastcall(PublisherTaskCollection *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180006870`
- `0x18000f650`
- `0x1800103a0`
- `0x180010d9c`
- `0x180023548`
- `0x180038fa4`

## pseudocode

```c
__int64 __fastcall PublisherTaskCollection::GetCount(PublisherTaskCollection *this)
{
  PropertyCollection *v1; // rcx
  wmi::RefBase *v2; // rbx
  _DWORD *v3; // rdi
  int v4; // eax
  unsigned int v5; // ecx
  unsigned int v6; // eax
  unsigned int v7; // edi
  __int128 pExceptionObject; // [rsp+20h] [rbp-30h] BYREF
  __int64 v10; // [rsp+30h] [rbp-20h]
  int v11; // [rsp+38h] [rbp-18h]
  int v12; // [rsp+3Ch] [rbp-14h]
  int v13; // [rsp+40h] [rbp-10h]
  wmi::RefBase *v14; // [rsp+60h] [rbp+10h] BYREF

  v14 = 0;
  PropertyCollection::GetPublisher(this, *((_QWORD *)this + 4), &v14);
  v2 = v14;
  if ( *((_DWORD *)v14 + 8) < 0x15u )
  {
    if ( !v14 )
      return 0;
    goto LABEL_14;
  }
  PropertyCollection::LazyGetProperty(v1, *((void **)v14 + 6), (wmi::RefBase *)((char *)v14 + 32), 0x10u);
  v3 = (_DWORD *)*((_QWORD *)v2 + 5);
  v4 = v3[102];
  if ( !v4 )
  {
LABEL_14:
    wmi::RefBase::Release(v2);
    return 0;
  }
  if ( v4 != 9 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_374a7e7c65f63b44902744a4ab2d8332_Traceguids, 13);
    }
    pExceptionObject = 0;
    v10 = 0;
    v11 = 13;
    v12 = -1;
    v13 = 467;
    throw (EvtException *)&pExceptionObject;
  }
  if ( v3[114] != 7 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_374a7e7c65f63b44902744a4ab2d8332_Traceguids, 13);
    }
    pExceptionObject = 0;
    v10 = 0;
    v11 = 13;
    v12 = -1;
    v13 = 474;
    throw (EvtException *)&pExceptionObject;
  }
  v5 = v3[116];
  if ( v3[104] <= v5 )
    v5 = v3[104];
  if ( v3[108] != 10 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_374a7e7c65f63b44902744a4ab2d8332_Traceguids, 13);
    }
    pExceptionObject = 0;
    v10 = 0;
    v11 = 13;
    v12 = -1;
    v13 = 485;
    throw (EvtException *)&pExceptionObject;
  }
  v6 = v3[110];
  if ( v5 <= v6 )
    v6 = v5;
  if ( v3[120] != 7 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_374a7e7c65f63b44902744a4ab2d8332_Traceguids, 13);
    }
    pExceptionObject = 0;
    v10 = 0;
    v11 = 13;
    v12 = -1;
    v13 = 496;
    throw (EvtException *)&pExceptionObject;
  }
  v7 = v3[122];
  if ( v6 <= v7 )
    v7 = v6;
  wmi::RefBase::Release(v2);
  return v7;
}

```

## disassembly

```asm
0x18000f650  mov     [rsp-8+arg_8], rbx
0x18000f655  mov     [rsp-8+arg_10], rdi
0x18000f65a  push    rbp
0x18000f65b  mov     rbp, rsp
0x18000f65e  sub     rsp, 50h
0x18000f662  mov     [rbp+arg_0], 0
0x18000f66a  lea     r8, [rbp+arg_0]
0x18000f66e  mov     rdx, [rcx+20h]
0x18000f672  call    ?GetPublisher@PropertyCollection@@IEBAXPEAXAEAV?$AutoRef@VPublisherMetadataObject@@@wmi@@@Z; PropertyCollection::GetPublisher(void *,wmi::AutoRef<PublisherMetadataObject> &)
0x18000f677  mov     rbx, [rbp+arg_0]
0x18000f67b  cmp     dword ptr [rbx+20h], 15h
0x18000f67f  jb      loc_18000F71F
0x18000f685  mov     r9d, 10h; unsigned int
0x18000f68b  lea     r8, [rbx+20h]; struct tag_EvtRpcVariantList *
0x18000f68f  mov     rdx, [rbx+30h]; void *
0x18000f693  call    ?LazyGetProperty@PropertyCollection@@IEBAXPEAXAEAUtag_EvtRpcVariantList@@K@Z; PropertyCollection::LazyGetProperty(void *,tag_EvtRpcVariantList &,ulong)
0x18000f698  mov     rdi, [rbx+28h]
0x18000f69c  mov     eax, [rdi+198h]
0x18000f6a2  test    eax, eax
0x18000f6a4  jz      short loc_18000F705
0x18000f6a6  cmp     eax, 9
0x18000f6a9  jnz     short loc_18000F726
0x18000f6ab  cmp     dword ptr [rdi+1C8h], 7
0x18000f6b2  jnz     loc_18000F795
0x18000f6b8  mov     eax, [rdi+1A0h]
0x18000f6be  mov     ecx, [rdi+1D0h]
0x18000f6c4  cmp     eax, ecx
0x18000f6c6  cmovbe  ecx, eax
0x18000f6c9  cmp     dword ptr [rdi+1B0h], 0Ah
0x18000f6d0  jnz     loc_18000F804
0x18000f6d6  mov     eax, [rdi+1B8h]
0x18000f6dc  cmp     ecx, eax
0x18000f6de  cmovbe  eax, ecx
0x18000f6e1  cmp     dword ptr [rdi+1E0h], 7
0x18000f6e8  jnz     loc_18000F873
0x18000f6ee  mov     edi, [rdi+1E8h]
0x18000f6f4  cmp     eax, edi
0x18000f6f6  cmovbe  edi, eax
0x18000f6f9  mov     rcx, rbx; this
0x18000f6fc  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18000f701  mov     eax, edi
0x18000f703  jmp     short loc_18000F70F
0x18000f705  mov     rcx, rbx; this
0x18000f708  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18000f70d  xor     eax, eax
0x18000f70f  mov     rbx, [rsp+50h+arg_8]
0x18000f714  mov     rdi, [rsp+50h+arg_10]
0x18000f719  add     rsp, 50h
0x18000f71d  pop     rbp
0x18000f71e  retn
0x18000f71f  test    rbx, rbx
0x18000f722  jnz     short loc_18000F705
0x18000f724  jmp     short loc_18000F70D
0x18000f726  lea     rax, WPP_GLOBAL_Control
0x18000f72d  mov     ebx, 0Dh
0x18000f732  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f739  cmp     rcx, rax
0x18000f73c  jz      short loc_18000F763
0x18000f73e  test    dword ptr [rcx+1Ch], 40000h
0x18000f745  jz      short loc_18000F763
0x18000f747  cmp     byte ptr [rcx+19h], 2
0x18000f74b  jb      short loc_18000F763
0x18000f74d  lea     edx, [rbx+5]
0x18000f750  mov     r9d, ebx
0x18000f753  lea     r8, WPP_374a7e7c65f63b44902744a4ab2d8332_Traceguids
0x18000f75a  mov     rcx, [rcx+10h]
0x18000f75e  call    WPP_SF_D
0x18000f763  xorps   xmm0, xmm0
0x18000f766  movdqu  [rbp+pExceptionObject], xmm0
0x18000f76b  mov     [rbp+var_20], 0
0x18000f773  mov     [rbp+var_18], ebx
0x18000f776  mov     [rbp+var_14], 0FFFFFFFFh
0x18000f77d  mov     [rbp+var_10], 1D3h
0x18000f784  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000f78b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f78f  call    _CxxThrowException_0
0x18000f795  lea     rax, WPP_GLOBAL_Control
0x18000f79c  mov     ebx, 0Dh
0x18000f7a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7a8  cmp     rcx, rax
0x18000f7ab  jz      short loc_18000F7D2
0x18000f7ad  test    dword ptr [rcx+1Ch], 40000h
0x18000f7b4  jz      short loc_18000F7D2
0x18000f7b6  cmp     byte ptr [rcx+19h], 2
0x18000f7ba  jb      short loc_18000F7D2
0x18000f7bc  lea     edx, [rbx+6]
0x18000f7bf  mov     r9d, ebx
0x18000f7c2  lea     r8, WPP_374a7e7c65f63b44902744a4ab2d8332_Traceguids
0x18000f7c9  mov     rcx, [rcx+10h]
0x18000f7cd  call    WPP_SF_D
0x18000f7d2  xorps   xmm0, xmm0
0x18000f7d5  movdqu  [rbp+pExceptionObject], xmm0
0x18000f7da  mov     [rbp+var_20], 0
0x18000f7e2  mov     [rbp+var_18], ebx
0x18000f7e5  mov     [rbp+var_14], 0FFFFFFFFh
0x18000f7ec  mov     [rbp+var_10], 1DAh
0x18000f7f3  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000f7fa  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f7fe  call    _CxxThrowException_0
0x18000f804  lea     rax, WPP_GLOBAL_Control
0x18000f80b  mov     ebx, 0Dh
0x18000f810  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f817  cmp     rcx, rax
0x18000f81a  jz      short loc_18000F841
0x18000f81c  test    dword ptr [rcx+1Ch], 40000h
0x18000f823  jz      short loc_18000F841
0x18000f825  cmp     byte ptr [rcx+19h], 2
0x18000f829  jb      short loc_18000F841
0x18000f82b  lea     edx, [rbx+7]
0x18000f82e  mov     r9d, ebx
0x18000f831  lea     r8, WPP_374a7e7c65f63b44902744a4ab2d8332_Traceguids
0x18000f838  mov     rcx, [rcx+10h]
0x18000f83c  call    WPP_SF_D
0x18000f841  xorps   xmm0, xmm0
0x18000f844  movdqu  [rbp+pExceptionObject], xmm0
0x18000f849  mov     [rbp+var_20], 0
0x18000f851  mov     [rbp+var_18], ebx
0x18000f854  mov     [rbp+var_14], 0FFFFFFFFh
0x18000f85b  mov     [rbp+var_10], 1E5h
0x18000f862  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000f869  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f86d  call    _CxxThrowException_0
0x18000f873  lea     rax, WPP_GLOBAL_Control
0x18000f87a  mov     ebx, 0Dh
0x18000f87f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f886  cmp     rcx, rax
0x18000f889  jz      short loc_18000F8B0
0x18000f88b  test    dword ptr [rcx+1Ch], 40000h
0x18000f892  jz      short loc_18000F8B0
0x18000f894  cmp     byte ptr [rcx+19h], 2
0x18000f898  jb      short loc_18000F8B0
0x18000f89a  lea     edx, [rbx+8]
0x18000f89d  mov     r9d, ebx
0x18000f8a0  lea     r8, WPP_374a7e7c65f63b44902744a4ab2d8332_Traceguids
0x18000f8a7  mov     rcx, [rcx+10h]
0x18000f8ab  call    WPP_SF_D
0x18000f8b0  xorps   xmm0, xmm0
0x18000f8b3  movdqu  [rbp+pExceptionObject], xmm0
0x18000f8b8  mov     [rbp+var_20], 0
0x18000f8c0  mov     [rbp+var_18], ebx
0x18000f8c3  mov     [rbp+var_14], 0FFFFFFFFh
0x18000f8ca  mov     [rbp+var_10], 1F0h
0x18000f8d1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000f8d8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f8dc  call    _CxxThrowException_0
```
