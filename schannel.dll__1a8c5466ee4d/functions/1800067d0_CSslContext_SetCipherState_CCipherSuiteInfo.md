# CSslContext::SetCipherState(CCipherSuiteInfo *)

- ea: `0x1800067d0`
- end: `0x18000699c`
- name: `?SetCipherState@CSslContext@@QEAAKPEAVCCipherSuiteInfo@@@Z`
- size: `460`
- prototype: `unsigned int __fastcall(CSslContext *__hidden this, struct CCipherSuiteInfo *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007168`
- `0x180007b50`

## callees

- `0x180005fa0`
- `0x180005fe0`
- `0x1800067d0`
- `0x180041600`
- `0x1800597b0`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000694e`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000694e`
- `ntdll!RtlReleaseResource` at `0x18000688b`
- `ntdll!RtlReleaseResource` at `0x18000688b`
- `ntdll!RtlAcquireResourceShared` at `0x18000684a`
- `ntdll!RtlAcquireResourceShared` at `0x18000684a`
- `ncrypt!SslLookupCipherLengths` at `0x1800068cd`
- `ncrypt!SslLookupCipherLengths` at `0x1800068cd`

## pseudocode

```c
__int64 __fastcall CSslContext::SetCipherState(CSslContext *this, struct CCipherSuiteInfo *a2)
{
  __int64 v4; // rax
  __int64 v5; // rbp
  __int64 v6; // rdi
  CSslServerKey *v7; // rcx
  __int64 v8; // r14
  unsigned int i; // edx
  __int64 v10; // r8
  __int64 v11; // rcx
  unsigned int v12; // edi
  int v13; // eax
  __int64 result; // rax
  unsigned int v15; // ecx
  int v16; // eax
  __int64 v17; // rcx
  _BYTE Source1[20]; // [rsp+40h] [rbp-48h] BYREF

  v4 = (*(__int64 (**)(void))(*(_QWORD *)this + 264LL))();
  v5 = *((_QWORD *)this + 1);
  v6 = v4;
  memset(Source1, 0, sizeof(Source1));
  if ( v5 )
  {
    v17 = *(_QWORD *)(v5 + 848);
    if ( v17 )
      CMasterEccCurveInfo::Dereference(*(CMasterEccCurveInfo **)(v17 + 16));
    CMasterCipherInfo::Dereference(*(CMasterCipherInfo **)(v5 + 856));
  }
  v7 = (CSslServerKey *)*((_QWORD *)this + 3);
  if ( v7 )
  {
    CSslServerKey::Dereference(v7);
    *((_QWORD *)this + 3) = 0;
  }
  if ( v6 )
  {
    v8 = *(_QWORD *)a2;
    RtlAcquireResourceShared((PRTL_RESOURCE)(v6 + 552), 1u);
    for ( i = 0; i < *(_DWORD *)(v6 + 96); ++i )
    {
      v10 = 8LL * i;
      v11 = *(_QWORD *)(v10 + *(_QWORD *)(v6 + 88));
      if ( *(_QWORD *)(v11 + 16) == v8 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v11 + 24));
        *((_QWORD *)this + 3) = *(_QWORD *)(v10 + *(_QWORD *)(v6 + 88));
        break;
      }
    }
    RtlReleaseResource((PRTL_RESOURCE)(v6 + 552));
  }
  if ( (*((_DWORD *)this + 22) & 0xF3F00) != 0 )
  {
    v12 = SslLookupCipherLengths(
            *(_QWORD *)a2,
            *((unsigned __int16 *)this + 17),
            *((unsigned int *)a2 + 7),
            *((unsigned int *)this + 4),
            Source1,
            20,
            0);
    if ( v12 )
      goto LABEL_14;
  }
  else
  {
    v15 = *((_DWORD *)a2 + 3);
    v12 = 0;
    v16 = *((_DWORD *)a2 + 4);
    *(_QWORD *)Source1 = 20;
    *(_QWORD *)&Source1[12] = 0;
    *(_DWORD *)&Source1[8] = v16;
    if ( v15 > 1 )
    {
      *(_DWORD *)&Source1[12] = v15;
      *(_DWORD *)&Source1[16] = 1;
    }
  }
  if ( (*((_BYTE *)this + 32) & 1) == 0 || RtlCompareMemory(Source1, (char *)this + 40, 0x14u) == 20 )
  {
    v13 = *(_DWORD *)&Source1[16];
    *(_OWORD *)((char *)this + 40) = *(_OWORD *)Source1;
    *((_DWORD *)this + 14) = v13;
  }
  else
  {
    v12 = -2146893007;
  }
LABEL_14:
  *((_WORD *)this + 16) |= 1u;
  result = v12;
  *((_QWORD *)this + 1) = a2;
  return result;
}

```

## disassembly

```asm
0x1800067d0  push    rbx
0x1800067d2  push    rsi
0x1800067d3  push    rdi
0x1800067d4  push    r15
0x1800067d6  sub     rsp, 68h
0x1800067da  mov     rax, cs:__security_cookie
0x1800067e1  xor     rax, rsp
0x1800067e4  mov     [rsp+88h+var_30], rax
0x1800067e9  mov     rax, [rcx]
0x1800067ec  mov     rsi, rdx
0x1800067ef  mov     [rsp+88h+arg_10], rbp
0x1800067f7  mov     rbx, rcx
0x1800067fa  mov     rax, [rax+108h]
0x180006801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006806  mov     rbp, [rbx+8]
0x18000680a  mov     rdi, rax
0x18000680d  xor     eax, eax
0x18000680f  xorps   xmm0, xmm0
0x180006812  mov     [rsp+88h+var_38], eax
0x180006816  movups  [rsp+88h+Source1], xmm0
0x18000681b  test    rbp, rbp
0x18000681e  jnz     loc_180006968
0x180006824  mov     rcx, [rbx+18h]; this
0x180006828  xor     r15d, r15d
0x18000682b  test    rcx, rcx
0x18000682e  jnz     loc_18000698E
0x180006834  test    rdi, rdi
0x180006837  jz      short loc_180006896
0x180006839  mov     [rsp+88h+var_28], r14
0x18000683e  lea     rcx, [rdi+228h]; Resource
0x180006845  mov     r14, [rsi]
0x180006848  mov     dl, 1; Wait
0x18000684a  call    cs:__imp_RtlAcquireResourceShared
0x180006850  mov     edx, r15d
0x180006853  cmp     edx, [rdi+60h]
0x180006856  jnb     short loc_180006884
0x180006858  mov     eax, edx
0x18000685a  lea     r8, ds:0[rax*8]
0x180006862  mov     rax, [rdi+58h]
0x180006866  mov     rcx, [r8+rax]
0x18000686a  cmp     [rcx+10h], r14
0x18000686e  jnz     loc_180006961
0x180006874  lock inc dword ptr [rcx+18h]
0x180006878  mov     rax, [rdi+58h]
0x18000687c  mov     rdx, [r8+rax]
0x180006880  mov     [rbx+18h], rdx
0x180006884  lea     rcx, [rdi+228h]; Resource
0x18000688b  call    cs:__imp_RtlReleaseResource
0x180006891  mov     r14, [rsp+88h+var_28]
0x180006896  test    dword ptr [rbx+58h], 0F3F00h
0x18000689d  mov     rbp, [rsp+88h+arg_10]
0x1800068a5  jz      short loc_180006911
0x1800068a7  movzx   edx, word ptr [rbx+22h]
0x1800068ab  lea     rax, [rsp+88h+Source1]
0x1800068b0  mov     r9d, [rbx+10h]
0x1800068b4  mov     r8d, [rsi+1Ch]
0x1800068b8  mov     rcx, [rsi]
0x1800068bb  mov     [rsp+88h+var_58], r15d
0x1800068c0  mov     [rsp+88h+var_60], 14h
0x1800068c8  mov     [rsp+88h+var_68], rax
0x1800068cd  call    cs:__imp_SslLookupCipherLengths
0x1800068d3  mov     edi, eax
0x1800068d5  test    eax, eax
0x1800068d7  jnz     short loc_1800068EF
0x1800068d9  test    byte ptr [rbx+20h], 1
0x1800068dd  jnz     short loc_18000693F
0x1800068df  movups  xmm0, [rsp+88h+Source1]
0x1800068e4  mov     eax, [rsp+88h+var_38]
0x1800068e8  movups  xmmword ptr [rbx+28h], xmm0
0x1800068ec  mov     [rbx+38h], eax
0x1800068ef  or      word ptr [rbx+20h], 1
0x1800068f4  mov     eax, edi
0x1800068f6  mov     [rbx+8], rsi
0x1800068fa  mov     rcx, [rsp+88h+var_30]
0x1800068ff  xor     rcx, rsp; StackCookie
0x180006902  call    __security_check_cookie
0x180006907  add     rsp, 68h
0x18000690b  pop     r15
0x18000690d  pop     rdi
0x18000690e  pop     rsi
0x18000690f  pop     rbx
0x180006910  retn
0x180006911  mov     ecx, [rsi+0Ch]
0x180006914  mov     edi, r15d
0x180006917  mov     eax, [rsi+10h]
0x18000691a  mov     qword ptr [rsp+88h+Source1], 14h
0x180006923  mov     qword ptr [rsp+88h+Source1+0Ch], r15
0x180006928  mov     dword ptr [rsp+88h+Source1+8], eax
0x18000692c  cmp     ecx, 1
0x18000692f  jbe     short loc_1800068D9
0x180006931  mov     dword ptr [rsp+88h+Source1+0Ch], ecx
0x180006935  mov     [rsp+88h+var_38], 1
0x18000693d  jmp     short loc_1800068D9
0x18000693f  lea     rdx, [rbx+28h]; Source2
0x180006943  mov     r8d, 14h; Length
0x180006949  lea     rcx, [rsp+88h+Source1]; Source1
0x18000694e  call    cs:__imp_RtlCompareMemory
0x180006954  cmp     rax, 14h
0x180006958  jz      short loc_1800068DF
0x18000695a  mov     edi, 80090331h
0x18000695f  jmp     short loc_1800068EF
0x180006961  inc     edx
0x180006963  jmp     loc_180006853
0x180006968  mov     rcx, [rbp+350h]
0x18000696f  test    rcx, rcx
0x180006972  jz      short loc_18000697D
0x180006974  mov     rcx, [rcx+10h]; this
0x180006978  call    ?Dereference@CMasterEccCurveInfo@@QEAAJXZ; CMasterEccCurveInfo::Dereference(void)
0x18000697d  mov     rcx, [rbp+358h]; this
0x180006984  call    ?Dereference@CMasterCipherInfo@@QEAAJXZ; CMasterCipherInfo::Dereference(void)
0x180006989  jmp     loc_180006824
0x18000698e  call    ?Dereference@CSslServerKey@@QEAAXXZ; CSslServerKey::Dereference(void)
0x180006993  mov     [rbx+18h], r15
0x180006997  jmp     loc_180006834
```
