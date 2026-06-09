# CCipherMill::SetServerHelloCipher(CSsl3TlsClientContext *,ulong)

- ea: `0x18000c610`
- end: `0x18000c9a8`
- name: `?SetServerHelloCipher@CCipherMill@@QEAAKPEAVCSsl3TlsClientContext@@K@Z`
- size: `920`
- prototype: `unsigned int __fastcall(CCipherMill *__hidden this, struct CSsl3TlsClientContext *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aee0`

## callees

- `0x180005fa0`
- `0x180005fe0`
- `0x18000c610`
- `0x18000cb90`
- `0x180041600`
- `0x180056c68`
- `0x180057c8c`
- `0x1800597b0`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000c92b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000c92b`
- `ntdll!RtlReleaseResource` at `0x18000c7ea`
- `ntdll!RtlReleaseResource` at `0x18000c85c`
- `ntdll!RtlReleaseResource` at `0x18000c8b7`
- `ntdll!RtlReleaseResource` at `0x18000c7ea`
- `ntdll!RtlReleaseResource` at `0x18000c85c`
- `ntdll!RtlReleaseResource` at `0x18000c8b7`
- `ntdll!RtlAcquireResourceShared` at `0x18000c668`
- `ntdll!RtlAcquireResourceShared` at `0x18000c7a7`
- `ntdll!RtlAcquireResourceShared` at `0x18000c668`
- `ntdll!RtlAcquireResourceShared` at `0x18000c7a7`
- `ncrypt!SslLookupCipherLengths` at `0x18000c823`
- `ncrypt!SslLookupCipherLengths` at `0x18000c823`

## pseudocode

```c
__int64 __fastcall CCipherMill::SetServerHelloCipher(CCipherMill *this, struct CSsl3TlsClientContext *a2, int a3)
{
  __int64 v3; // rbp
  unsigned int v4; // r14d
  __int64 v7; // r15
  unsigned int v8; // r12d
  unsigned int v9; // r13d
  CMasterCipherInfo *v10; // r8
  __int64 v11; // r9
  unsigned int v12; // r8d
  unsigned int i; // edx
  __int64 *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rbp
  __int64 v18; // rsi
  CSslServerKey *v19; // rcx
  __int64 v20; // r14
  unsigned int j; // r8d
  __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned int v24; // esi
  int v25; // eax
  unsigned int v27; // ecx
  int v28; // eax
  __int64 v29; // rcx
  _BYTE Source1[20]; // [rsp+70h] [rbp-48h] BYREF

  v3 = *((_QWORD *)a2 + 13);
  v4 = *((_DWORD *)a2 + 22);
  v7 = *(_QWORD *)(v3 + 248);
  v8 = *(_DWORD *)(v3 + 240);
  v9 = *(_DWORD *)(v3 + 256);
  RtlAcquireResourceShared(&Resource, 1u);
  v10 = xmmword_1800AE5B0;
  if ( (*((_DWORD *)a2 + 464) & 0x20000000) != 0 )
    v10 = *(&xmmword_1800AE5B0 + 1);
  if ( v10 )
  {
    v11 = *(_QWORD *)v10;
    v12 = *((_DWORD *)v10 + 2);
  }
  else
  {
    v11 = 0;
    v12 = 0;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v12 )
      goto LABEL_27;
    v14 = (__int64 *)(v11 + 864LL * i);
    if ( *((_DWORD *)v14 + 7) == a3 )
      break;
  }
  if ( (unsigned __int8)CCipherMill::IsCipherSuiteAllowed(
                          &g_cCipherMill,
                          v7,
                          v8,
                          v9,
                          (*(_DWORD *)(v3 + 220) >> 12) & 1,
                          *(_DWORD *)(v3 + 220) & 0x800,
                          *(_DWORD *)(v3 + 232),
                          *(_DWORD *)(v3 + 228),
                          v4,
                          v14,
                          0,
                          0,
                          0,
                          1) )
  {
    v15 = v14[106];
    if ( v15 )
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v15 + 16) + 12LL));
    _InterlockedIncrement((volatile signed __int32 *)(v14[107] + 12));
    v16 = (*(__int64 (__fastcall **)(struct CSsl3TlsClientContext *))(*(_QWORD *)a2 + 264LL))(a2);
    v17 = *((_QWORD *)a2 + 1);
    v18 = v16;
    memset(Source1, 0, sizeof(Source1));
    if ( v17 )
    {
      v29 = *(_QWORD *)(v17 + 848);
      if ( v29 )
        CMasterEccCurveInfo::Dereference(*(CMasterEccCurveInfo **)(v29 + 16));
      CMasterCipherInfo::Dereference(*(CMasterCipherInfo **)(v17 + 856));
    }
    v19 = (CSslServerKey *)*((_QWORD *)a2 + 3);
    if ( v19 )
    {
      CSslServerKey::Dereference(v19);
      *((_QWORD *)a2 + 3) = 0;
    }
    if ( v18 )
    {
      v20 = *v14;
      RtlAcquireResourceShared((PRTL_RESOURCE)(v18 + 552), 1u);
      for ( j = 0; j < *(_DWORD *)(v18 + 96); ++j )
      {
        v22 = 8LL * j;
        v23 = *(_QWORD *)(v22 + *(_QWORD *)(v18 + 88));
        if ( *(_QWORD *)(v23 + 16) == v20 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v23 + 24));
          *((_QWORD *)a2 + 3) = *(_QWORD *)(v22 + *(_QWORD *)(v18 + 88));
          break;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)(v18 + 552));
    }
    if ( (*((_DWORD *)a2 + 22) & 0xF3F00) != 0 )
    {
      v24 = SslLookupCipherLengths(
              *v14,
              *((unsigned __int16 *)a2 + 17),
              *((unsigned int *)v14 + 7),
              *((unsigned int *)a2 + 4),
              Source1,
              20,
              0);
      if ( v24 )
      {
LABEL_25:
        *((_WORD *)a2 + 16) |= 1u;
        *((_QWORD *)a2 + 1) = v14;
        RtlReleaseResource(&Resource);
        return v24;
      }
    }
    else
    {
      v27 = *((_DWORD *)v14 + 3);
      v24 = 0;
      v28 = *((_DWORD *)v14 + 4);
      *(_QWORD *)Source1 = 20;
      *(_QWORD *)&Source1[12] = 0;
      *(_DWORD *)&Source1[8] = v28;
      if ( v27 > 1 )
      {
        *(_DWORD *)&Source1[12] = v27;
        *(_DWORD *)&Source1[16] = 1;
      }
    }
    if ( (*((_BYTE *)a2 + 32) & 1) == 0 || RtlCompareMemory(Source1, (char *)a2 + 40, 0x14u) == 20 )
    {
      v25 = *(_DWORD *)&Source1[16];
      *(_OWORD *)((char *)a2 + 40) = *(_OWORD *)Source1;
      *((_DWORD *)a2 + 14) = v25;
    }
    else
    {
      v24 = -2146893007;
    }
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_09dceeee5ffe36f0dedb0b1d6c80af61_Traceguids);
LABEL_27:
  RtlReleaseResource(&Resource);
  LogCipherMismatchEvent(*(_DWORD *)(v3 + 276), (const unsigned __int16 *)(v3 + 280), v4);
  return 2148074289LL;
}

```

## disassembly

```asm
0x18000c610  mov     [rsp+arg_10], rbx
0x18000c615  mov     [rsp+arg_18], rbp
0x18000c61a  push    rsi
0x18000c61b  push    r12
0x18000c61d  push    r13
0x18000c61f  push    r14
0x18000c621  push    r15
0x18000c623  sub     rsp, 90h
0x18000c62a  mov     rax, cs:__security_cookie
0x18000c631  xor     rax, rsp
0x18000c634  mov     [rsp+0B8h+var_30], rax
0x18000c63c  mov     rbp, [rdx+68h]
0x18000c640  lea     rcx, Resource; Resource
0x18000c647  mov     r14d, [rdx+58h]
0x18000c64b  mov     rbx, rdx
0x18000c64e  mov     dl, 1; Wait
0x18000c650  mov     esi, r8d
0x18000c653  mov     r15, [rbp+0F8h]
0x18000c65a  mov     r12d, [rbp+0F0h]
0x18000c661  mov     r13d, [rbp+100h]
0x18000c668  call    cs:__imp_RtlAcquireResourceShared
0x18000c66e  mov     eax, [rbx+740h]
0x18000c674  bt      rax, 1Dh
0x18000c679  mov     r8, qword ptr cs:xmmword_1800AE5B0
0x18000c680  cmovb   r8, qword ptr cs:xmmword_1800AE5B0+8
0x18000c688  xor     r11d, r11d
0x18000c68b  test    r8, r8
0x18000c68e  jz      loc_18000C8D9
0x18000c694  mov     r9, [r8]
0x18000c697  mov     r8d, [r8+8]
0x18000c69b  mov     edx, r11d
0x18000c69e  mov     [rsp+0B8h+arg_0], rdi
0x18000c6a6  cmp     edx, r8d
0x18000c6a9  jnb     loc_18000C8B0
0x18000c6af  mov     eax, edx
0x18000c6b1  imul    rdi, rax, 360h
0x18000c6b8  add     rdi, r9
0x18000c6bb  cmp     [rdi+1Ch], esi
0x18000c6be  jz      short loc_18000C6C4
0x18000c6c0  inc     edx
0x18000c6c2  jmp     short loc_18000C6A6
0x18000c6c4  mov     r10d, [rbp+0DCh]
0x18000c6cb  mov     r9d, r13d
0x18000c6ce  mov     eax, [rbp+0E4h]
0x18000c6d4  mov     ecx, r10d
0x18000c6d7  mov     [rsp+0B8h+var_50], 1
0x18000c6dc  and     ecx, 800h
0x18000c6e2  mov     [rsp+0B8h+var_58], r11d
0x18000c6e7  mov     r8d, r12d
0x18000c6ea  mov     [rsp+0B8h+var_60], r11
0x18000c6ef  mov     rdx, r15
0x18000c6f2  mov     [rsp+0B8h+var_68], r11
0x18000c6f7  mov     [rsp+0B8h+var_70], rdi
0x18000c6fc  mov     [rsp+0B8h+var_78], r14d
0x18000c701  mov     [rsp+0B8h+var_80], eax
0x18000c705  mov     eax, [rbp+0E8h]
0x18000c70b  mov     [rsp+0B8h+var_88], eax
0x18000c70f  mov     [rsp+0B8h+var_90], ecx
0x18000c713  lea     rcx, ?g_cCipherMill@@3VCCipherMill@@A; CCipherMill g_cCipherMill
0x18000c71a  shr     r10d, 0Ch
0x18000c71e  and     r10d, 1
0x18000c722  mov     dword ptr [rsp+0B8h+var_98], r10d
0x18000c727  call    ?IsCipherSuiteAllowed@CCipherMill@@QEAAEPEAIKW4efAlgFlags@@HHKKKPEAVCCipherSuiteInfo@@PEAU_UNICODE_STRING@@PEAU_TLS_PARAMETERS@@KE@Z; CCipherMill::IsCipherSuiteAllowed(uint *,ulong,efAlgFlags,int,int,ulong,ulong,ulong,CCipherSuiteInfo *,_UNICODE_STRING *,_TLS_PARAMETERS *,ulong,uchar)
0x18000c72c  test    al, al
0x18000c72e  jz      loc_18000C899
0x18000c734  mov     rax, [rdi+350h]
0x18000c73b  test    rax, rax
0x18000c73e  jz      short loc_18000C748
0x18000c740  mov     rax, [rax+10h]
0x18000c744  lock inc dword ptr [rax+0Ch]
0x18000c748  mov     rax, [rdi+358h]
0x18000c74f  lock inc dword ptr [rax+0Ch]
0x18000c753  mov     rax, [rbx]
0x18000c756  mov     rcx, rbx
0x18000c759  mov     rax, [rax+108h]
0x18000c760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c765  mov     rbp, [rbx+8]
0x18000c769  mov     rsi, rax
0x18000c76c  xor     eax, eax
0x18000c76e  xorps   xmm0, xmm0
0x18000c771  mov     [rsp+0B8h+var_38], eax
0x18000c778  movups  [rsp+0B8h+Source1], xmm0
0x18000c77d  test    rbp, rbp
0x18000c780  jnz     loc_18000C94D
0x18000c786  mov     rcx, [rbx+18h]; this
0x18000c78a  test    rcx, rcx
0x18000c78d  jnz     loc_18000C997
0x18000c793  xor     r15d, r15d
0x18000c796  test    rsi, rsi
0x18000c799  jz      short loc_18000C7F0
0x18000c79b  mov     r14, [rdi]
0x18000c79e  lea     rcx, [rsi+228h]; Resource
0x18000c7a5  mov     dl, 1; Wait
0x18000c7a7  call    cs:__imp_RtlAcquireResourceShared
0x18000c7ad  mov     r8d, r15d
0x18000c7b0  cmp     r8d, [rsi+60h]
0x18000c7b4  jnb     short loc_18000C7E3
0x18000c7b6  mov     eax, r8d
0x18000c7b9  lea     rdx, ds:0[rax*8]
0x18000c7c1  mov     rax, [rsi+58h]
0x18000c7c5  mov     rcx, [rdx+rax]
0x18000c7c9  cmp     [rcx+10h], r14
0x18000c7cd  jnz     loc_18000C945
0x18000c7d3  lock inc dword ptr [rcx+18h]
0x18000c7d7  mov     rax, [rsi+58h]
0x18000c7db  mov     rcx, [rdx+rax]
0x18000c7df  mov     [rbx+18h], rcx
0x18000c7e3  lea     rcx, [rsi+228h]; Resource
0x18000c7ea  call    cs:__imp_RtlReleaseResource
0x18000c7f0  test    dword ptr [rbx+58h], 0F3F00h
0x18000c7f7  jz      loc_18000C8E4
0x18000c7fd  movzx   edx, word ptr [rbx+22h]
0x18000c801  lea     rax, [rsp+0B8h+Source1]
0x18000c806  mov     r9d, [rbx+10h]
0x18000c80a  mov     r8d, [rdi+1Ch]
0x18000c80e  mov     rcx, [rdi]
0x18000c811  mov     [rsp+0B8h+var_88], r15d
0x18000c816  mov     [rsp+0B8h+var_90], 14h
0x18000c81e  mov     [rsp+0B8h+var_98], rax
0x18000c823  call    cs:__imp_SslLookupCipherLengths
0x18000c829  mov     esi, eax
0x18000c82b  test    eax, eax
0x18000c82d  jnz     short loc_18000C84C
0x18000c82f  test    byte ptr [rbx+20h], 1
0x18000c833  jnz     loc_18000C91C
0x18000c839  movups  xmm0, [rsp+0B8h+Source1]
0x18000c83e  mov     eax, [rsp+0B8h+var_38]
0x18000c845  movups  xmmword ptr [rbx+28h], xmm0
0x18000c849  mov     [rbx+38h], eax
0x18000c84c  or      word ptr [rbx+20h], 1
0x18000c851  lea     rcx, Resource; Resource
0x18000c858  mov     [rbx+8], rdi
0x18000c85c  call    cs:__imp_RtlReleaseResource
0x18000c862  mov     eax, esi
0x18000c864  mov     rdi, [rsp+0B8h+arg_0]
0x18000c86c  mov     rcx, [rsp+0B8h+var_30]
0x18000c874  xor     rcx, rsp; StackCookie
0x18000c877  call    __security_check_cookie
0x18000c87c  lea     r11, [rsp+0B8h+var_28]
0x18000c884  mov     rbx, [r11+40h]
0x18000c888  mov     rbp, [r11+48h]
0x18000c88c  mov     rsp, r11
0x18000c88f  pop     r15
0x18000c891  pop     r14
0x18000c893  pop     r13
0x18000c895  pop     r12
0x18000c897  pop     rsi
0x18000c898  retn
0x18000c899  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8a0  lea     rax, WPP_GLOBAL_Control
0x18000c8a7  cmp     rcx, rax
0x18000c8aa  jnz     loc_18000C973
0x18000c8b0  lea     rcx, Resource; Resource
0x18000c8b7  call    cs:__imp_RtlReleaseResource
0x18000c8bd  mov     ecx, [rbp+114h]; unsigned int
0x18000c8c3  lea     rdx, [rbp+118h]; unsigned __int16 *
0x18000c8ca  mov     r8d, r14d; unsigned int
0x18000c8cd  call    ?LogCipherMismatchEvent@@YAXKPEBGK@Z; LogCipherMismatchEvent(ulong,ushort const *,ulong)
0x18000c8d2  mov     eax, 80090331h
0x18000c8d7  jmp     short loc_18000C864
0x18000c8d9  mov     r9, r11
0x18000c8dc  mov     r8d, r11d
0x18000c8df  jmp     loc_18000C69B
0x18000c8e4  mov     ecx, [rdi+0Ch]
0x18000c8e7  mov     esi, r15d
0x18000c8ea  mov     eax, [rdi+10h]
0x18000c8ed  mov     qword ptr [rsp+0B8h+Source1], 14h
0x18000c8f6  mov     qword ptr [rsp+0B8h+Source1+0Ch], r15
0x18000c8fb  mov     dword ptr [rsp+0B8h+Source1+8], eax
0x18000c8ff  cmp     ecx, 1
0x18000c902  jbe     loc_18000C82F
0x18000c908  mov     dword ptr [rsp+0B8h+Source1+0Ch], ecx
0x18000c90c  mov     [rsp+0B8h+var_38], 1
0x18000c917  jmp     loc_18000C82F
0x18000c91c  lea     rdx, [rbx+28h]; Source2
0x18000c920  mov     r8d, 14h; Length
0x18000c926  lea     rcx, [rsp+0B8h+Source1]; Source1
0x18000c92b  call    cs:__imp_RtlCompareMemory
0x18000c931  cmp     rax, 14h
0x18000c935  jz      loc_18000C839
0x18000c93b  mov     esi, 80090331h
0x18000c940  jmp     loc_18000C84C
0x18000c945  inc     r8d
0x18000c948  jmp     loc_18000C7B0
0x18000c94d  mov     rcx, [rbp+350h]
0x18000c954  test    rcx, rcx
0x18000c957  jz      short loc_18000C962
0x18000c959  mov     rcx, [rcx+10h]; this
0x18000c95d  call    ?Dereference@CMasterEccCurveInfo@@QEAAJXZ; CMasterEccCurveInfo::Dereference(void)
0x18000c962  mov     rcx, [rbp+358h]; this
0x18000c969  call    ?Dereference@CMasterCipherInfo@@QEAAJXZ; CMasterCipherInfo::Dereference(void)
0x18000c96e  jmp     loc_18000C786
0x18000c973  test    byte ptr [rcx+1Ch], 1
0x18000c977  jz      loc_18000C8B0
0x18000c97d  mov     rcx, [rcx+10h]
0x18000c981  lea     r8, WPP_09dceeee5ffe36f0dedb0b1d6c80af61_Traceguids
0x18000c988  mov     edx, 3Ch ; '<'
0x18000c98d  call    WPP_SF_
0x18000c992  jmp     loc_18000C8B0
0x18000c997  call    ?Dereference@CSslServerKey@@QEAAXXZ; CSslServerKey::Dereference(void)
0x18000c99c  xor     r15d, r15d
0x18000c99f  mov     [rbx+18h], r15
0x18000c9a3  jmp     loc_18000C796
```
