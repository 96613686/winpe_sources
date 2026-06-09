# CWdsMetadata::RemoveEntryByString(ushort const *)

- ea: `0x18000c4e0`
- end: `0x18000c76c`
- name: `?RemoveEntryByString@CWdsMetadata@@QEAAKPEBG@Z`
- size: `652`
- prototype: `unsigned int __fastcall(CWdsMetadata *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180011240`

## callees

- `0x180009838`
- `0x180009c94`
- `0x18000a15c`
- `0x18000a380`
- `0x18000a7ec`
- `0x18000ac50`
- `0x18000c4e0`
- `0x180014d58`
- `0x180015660`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000c631`
- `msvcrt!_wcsicmp` at `0x18000c631`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::RemoveEntryByString(CWdsMetadata *this, wchar_t *a2)
{
  int v3; // r13d
  __int64 v4; // r14
  unsigned int v5; // ebx
  const char *v6; // rdx
  __int64 v7; // rcx
  int GroupIndex; // eax
  const char *v9; // rdx
  __int64 v10; // rdi
  const char *v11; // rdx
  __int64 v12; // rdi
  __int64 v13; // r15
  const char *v14; // rdx
  __int64 i; // rdi
  __int64 v16; // r12
  const char *v17; // rdx
  DWORD v19; // [rsp+20h] [rbp-60h] BYREF
  unsigned int v20; // [rsp+24h] [rbp-5Ch]
  __int128 v21; // [rsp+30h] [rbp-50h] BYREF
  wchar_t *String1[2]; // [rsp+40h] [rbp-40h]
  int v23; // [rsp+50h] [rbp-30h]
  int v24; // [rsp+54h] [rbp-2Ch]
  int v25; // [rsp+58h] [rbp-28h] BYREF
  __int64 v26; // [rsp+60h] [rbp-20h]
  __int64 v27; // [rsp+68h] [rbp-18h]

  v23 = 0;
  v24 = 0;
  v26 = 0;
  v3 = 0;
  v27 = 0;
  v25 = 0;
  v4 = 0;
  v21 = 0;
  *(_OWORD *)String1 = 0;
  v5 = CWdsMetadataEntry::Initialize((CWdsMetadataEntry *)&v21, a2);
  if ( !ElValidateWin32(v5, v6, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x135Du) )
  {
    GroupIndex = CWdsMetadata::FindGroupIndex(v7, this, v21);
    v10 = (unsigned int)GroupIndex;
    if ( GroupIndex >= 0
      || (v5 = 4312, !ElValidateWin32(0x10D8u, v9, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x1368u)) )
    {
      v5 = 0;
      if ( (unsigned int)v10 < *((_DWORD *)this + 3) )
      {
        _mm_lfence();
        v4 = *(_QWORD *)(*(_QWORD *)this + 8 * v10);
      }
      else
      {
        v5 = 1413;
      }
      if ( !ElValidateWin32(v5, v9, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x136Cu) )
      {
        if ( *(_DWORD *)(v4 + 20) )
        {
LABEL_9:
          v20 = -1;
          v12 = 0;
          while ( 1 )
          {
            v13 = 0;
            v5 = 0;
            if ( (unsigned int)v12 < *(_DWORD *)(v4 + 20) )
              v13 = *(_QWORD *)(*(_QWORD *)(v4 + 8) + 8 * v12);
            else
              v5 = 1413;
            if ( ElValidateWin32(v5, v11, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x137Du) )
              goto LABEL_36;
            if ( v23 == *(_DWORD *)(v13 + 32) )
            {
              v11 = *(const char **)(v13 + 24);
              if ( String1[1] )
              {
                if ( !v11 || _wcsicmp(String1[1], (const wchar_t *)v11) )
                  goto LABEL_22;
              }
              else if ( v11 )
              {
                goto LABEL_22;
              }
              v19 = 0;
              v5 = CWdsMetadataValue::Match(&v25, 1, v13 + 40, &v19);
              if ( ElValidateWin32(v5, v14, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x1393u) )
                goto LABEL_36;
              if ( v19 )
              {
                for ( i = 0; (unsigned int)i < *((_DWORD *)this + 15); i = (unsigned int)(i + 1) )
                {
                  v16 = 0;
                  v5 = 0;
                  if ( (unsigned int)i < *((_DWORD *)this + 15) )
                    v16 = *(_QWORD *)(*((_QWORD *)this + 6) + 8 * i);
                  else
                    v5 = 1413;
                  if ( ElValidateWin32(v5, v11, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x13B2u) )
                    goto LABEL_36;
                  if ( v16 == v13 )
                    goto LABEL_32;
                }
                LODWORD(i) = v20;
LABEL_32:
                v5 = CWdsMetadata::RemoveEntry(this, i);
                if ( ElValidateWin32(v5, v17, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x13BCu) )
                  goto LABEL_36;
                ++v3;
                if ( *(_DWORD *)(v4 + 20) )
                  goto LABEL_9;
LABEL_34:
                if ( v3 )
                  goto LABEL_36;
                break;
              }
            }
LABEL_22:
            v12 = (unsigned int)(v12 + 1);
            if ( (unsigned int)v12 >= *(_DWORD *)(v4 + 20) )
              goto LABEL_34;
          }
        }
        v5 = 4312;
        ElValidateWin32(0x10D8u, v11, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x13C9u);
      }
    }
  }
LABEL_36:
  CWdsMetadataEntry::Shutdown((CWdsMetadataEntry *)&v21);
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v25);
  return v5;
}

```

## disassembly

```asm
0x18000c4e0  mov     [rsp-38h+arg_10], rbx
0x18000c4e5  push    rbp
0x18000c4e6  push    rsi
0x18000c4e7  push    rdi
0x18000c4e8  push    r12
0x18000c4ea  push    r13
0x18000c4ec  push    r14
0x18000c4ee  push    r15
0x18000c4f0  mov     rbp, rsp
0x18000c4f3  sub     rsp, 80h
0x18000c4fa  mov     rax, cs:__security_cookie
0x18000c501  xor     rax, rsp
0x18000c504  mov     [rbp+var_10], rax
0x18000c508  xor     eax, eax
0x18000c50a  mov     rsi, rcx
0x18000c50d  and     [rbp+var_30], eax
0x18000c510  lea     rcx, [rbp+var_50]; this
0x18000c514  and     [rbp+var_2C], eax
0x18000c517  xorps   xmm0, xmm0
0x18000c51a  xorps   xmm1, xmm1
0x18000c51d  mov     [rbp+var_20], rax
0x18000c521  xor     r13d, r13d
0x18000c524  mov     [rbp+var_18], rax
0x18000c528  and     [rbp+var_28], r13d
0x18000c52c  xor     r14d, r14d
0x18000c52f  movdqa  [rbp+var_50], xmm0
0x18000c534  movdqa  xmmword ptr [rbp+String1], xmm1
0x18000c539  call    ?Initialize@CWdsMetadataEntry@@QEAAKPEBG@Z; CWdsMetadataEntry::Initialize(ushort const *)
0x18000c53e  lea     r12, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000c545  mov     r9d, 135Dh; unsigned int
0x18000c54b  mov     r8, r12; char *
0x18000c54e  mov     ecx, eax; unsigned int
0x18000c550  mov     ebx, eax
0x18000c552  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c557  test    eax, eax
0x18000c559  jnz     loc_18000C725
0x18000c55f  mov     r8, qword ptr [rbp+var_50]
0x18000c563  mov     rdx, rsi
0x18000c566  call    ?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z; CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)
0x18000c56b  mov     edi, eax
0x18000c56d  mov     r15d, 10D8h
0x18000c573  test    eax, eax
0x18000c575  jns     short loc_18000C593
0x18000c577  mov     r9d, 1368h; unsigned int
0x18000c57d  mov     r8, r12; char *
0x18000c580  mov     ecx, r15d; unsigned int
0x18000c583  mov     ebx, r15d
0x18000c586  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c58b  test    eax, eax
0x18000c58d  jnz     loc_18000C725
0x18000c593  xor     ebx, ebx
0x18000c595  cmp     edi, [rsi+0Ch]
0x18000c598  jb      short loc_18000C5A1
0x18000c59a  mov     ebx, 585h
0x18000c59f  jmp     short loc_18000C5AB
0x18000c5a1  lfence
0x18000c5a4  mov     rax, [rsi]
0x18000c5a7  mov     r14, [rax+rdi*8]
0x18000c5ab  mov     r9d, 136Ch; unsigned int
0x18000c5b1  mov     r8, r12; char *
0x18000c5b4  mov     ecx, ebx; unsigned int
0x18000c5b6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c5bb  test    eax, eax
0x18000c5bd  jnz     loc_18000C725
0x18000c5c3  mov     eax, [r14+14h]
0x18000c5c7  test    eax, eax
0x18000c5c9  jz      loc_18000C711
0x18000c5cf  or      [rbp+var_5C], 0FFFFFFFFh
0x18000c5d3  xor     edi, edi
0x18000c5d5  test    eax, eax
0x18000c5d7  jz      loc_18000C706
0x18000c5dd  xor     r15d, r15d
0x18000c5e0  xor     ebx, ebx
0x18000c5e2  cmp     edi, [r14+14h]
0x18000c5e6  jb      short loc_18000C5EF
0x18000c5e8  mov     ebx, 585h
0x18000c5ed  jmp     short loc_18000C5F7
0x18000c5ef  mov     rax, [r14+8]
0x18000c5f3  mov     r15, [rax+rdi*8]
0x18000c5f7  mov     r9d, 137Dh; unsigned int
0x18000c5fd  mov     r8, r12; char *
0x18000c600  mov     ecx, ebx; unsigned int
0x18000c602  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c607  test    eax, eax
0x18000c609  jnz     loc_18000C725
0x18000c60f  mov     eax, [r15+20h]
0x18000c613  cmp     [rbp+var_30], eax
0x18000c616  jnz     short loc_18000C674
0x18000c618  mov     rcx, [rbp+String1+8]; String1
0x18000c61c  mov     rdx, [r15+18h]; String2
0x18000c620  test    rcx, rcx
0x18000c623  jnz     short loc_18000C62C
0x18000c625  test    rdx, rdx
0x18000c628  jz      short loc_18000C63B
0x18000c62a  jmp     short loc_18000C674
0x18000c62c  test    rdx, rdx
0x18000c62f  jz      short loc_18000C674
0x18000c631  call    cs:__imp__wcsicmp
0x18000c637  test    eax, eax
0x18000c639  jnz     short loc_18000C674
0x18000c63b  and     [rbp+var_60], 0
0x18000c63f  lea     r8, [r15+28h]
0x18000c643  lea     r9, [rbp+var_60]
0x18000c647  mov     edx, 1
0x18000c64c  lea     rcx, [rbp+var_28]
0x18000c650  call    ?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z; CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)
0x18000c655  mov     ebx, eax
0x18000c657  mov     r9d, 1393h; unsigned int
0x18000c65d  mov     r8, r12; char *
0x18000c660  mov     ecx, eax; unsigned int
0x18000c662  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c667  test    eax, eax
0x18000c669  jnz     loc_18000C725
0x18000c66f  cmp     [rbp+var_60], eax
0x18000c672  jnz     short loc_18000C685
0x18000c674  inc     edi
0x18000c676  cmp     edi, [r14+14h]
0x18000c67a  jnb     loc_18000C706
0x18000c680  jmp     loc_18000C5DD
0x18000c685  xor     edi, edi
0x18000c687  cmp     [rsi+3Ch], edi
0x18000c68a  jbe     short loc_18000C6D4
0x18000c68c  xor     r12d, r12d
0x18000c68f  xor     ebx, ebx
0x18000c691  cmp     edi, [rsi+3Ch]
0x18000c694  jb      short loc_18000C69D
0x18000c696  mov     ebx, 585h
0x18000c69b  jmp     short loc_18000C6A5
0x18000c69d  mov     rax, [rsi+30h]
0x18000c6a1  mov     r12, [rax+rdi*8]
0x18000c6a5  mov     r9d, 13B2h; unsigned int
0x18000c6ab  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000c6b2  mov     ecx, ebx; unsigned int
0x18000c6b4  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c6b9  test    eax, eax
0x18000c6bb  jnz     short loc_18000C725
0x18000c6bd  cmp     r12, r15
0x18000c6c0  jz      loc_18000C760
0x18000c6c6  inc     edi
0x18000c6c8  cmp     edi, [rsi+3Ch]
0x18000c6cb  jb      short loc_18000C68C
0x18000c6cd  lea     r12, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000c6d4  mov     edi, [rbp+var_5C]
0x18000c6d7  mov     edx, edi; unsigned int
0x18000c6d9  mov     rcx, rsi; this
0x18000c6dc  call    ?RemoveEntry@CWdsMetadata@@QEAAKK@Z; CWdsMetadata::RemoveEntry(ulong)
0x18000c6e1  mov     r9d, 13BCh; unsigned int
0x18000c6e7  mov     r8, r12; char *
0x18000c6ea  mov     ecx, eax; unsigned int
0x18000c6ec  mov     ebx, eax
0x18000c6ee  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c6f3  test    eax, eax
0x18000c6f5  jnz     short loc_18000C725
0x18000c6f7  mov     eax, [r14+14h]
0x18000c6fb  inc     r13d
0x18000c6fe  test    eax, eax
0x18000c700  jnz     loc_18000C5CF
0x18000c706  test    r13d, r13d
0x18000c709  jnz     short loc_18000C725
0x18000c70b  mov     r15d, 10D8h
0x18000c711  mov     r9d, 13C9h; unsigned int
0x18000c717  mov     r8, r12; char *
0x18000c71a  mov     ecx, r15d; unsigned int
0x18000c71d  mov     ebx, r15d
0x18000c720  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c725  lea     rcx, [rbp+var_50]; this
0x18000c729  call    ?Shutdown@CWdsMetadataEntry@@QEAAXXZ; CWdsMetadataEntry::Shutdown(void)
0x18000c72e  lea     rcx, [rbp+var_28]; this
0x18000c732  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18000c737  mov     eax, ebx
0x18000c739  mov     rcx, [rbp+var_10]
0x18000c73d  xor     rcx, rsp; StackCookie
0x18000c740  call    __security_check_cookie
0x18000c745  mov     rbx, [rsp+80h+arg_10]
0x18000c74d  add     rsp, 80h
0x18000c754  pop     r15
0x18000c756  pop     r14
0x18000c758  pop     r13
0x18000c75a  pop     r12
0x18000c75c  pop     rdi
0x18000c75d  pop     rsi
0x18000c75e  pop     rbp
0x18000c75f  retn
0x18000c760  lea     r12, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000c767  jmp     loc_18000C6D7
```
