# TetheringDataStore::OpenRecord(HKEY__ *,TetheringDataRecord * *)

- ea: `0x18002df40`
- end: `0x18002e0b9`
- name: `?OpenRecord@TetheringDataStore@@QEAAJPEAUHKEY__@@PEAPEAVTetheringDataRecord@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(TetheringDataStore *__hidden this, HKEY, struct TetheringDataRecord **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18002ade8`

## callees

- `0x18000299c`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18002df40`

## pseudocode

```c
__int64 __fastcall TetheringDataStore::OpenRecord(TetheringDataStore *this, HKEY a2, struct TetheringDataRecord **a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  TetheringServiceTelemetry *v8; // rcx
  unsigned int v9; // ebx

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_fba0584bb98c356501b09d8c4620c3b4_Traceguids);
  }
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    memset_0(v6, 0, 0x68u);
    v7[3] = v7 + 8;
    v7[2] = v7 + 4;
    v7[7] = L"NetworkType";
    v7[4] = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::EncryptedDwordProperty>::`vftable';
    v7[11] = L"ConnectionTimeout";
    *((_WORD *)v7 + 36) = 0;
    *((_BYTE *)v7 + 74) = 0;
    v7[10] = 0;
    v7[8] = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::EncryptedDwordProperty>::`vftable';
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fba0584bb98c356501b09d8c4620c3b4_Traceguids);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v8 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)v8 + 2), 10, WPP_fba0584bb98c356501b09d8c4620c3b4_Traceguids);
    }
    v7[12] = a2;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fba0584bb98c356501b09d8c4620c3b4_Traceguids, 0);
    }
    v9 = 0;
    *a3 = (struct TetheringDataRecord *)v7;
  }
  else
  {
    v9 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_fba0584bb98c356501b09d8c4620c3b4_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x18002df40  push    rbx
0x18002df42  push    rsi
0x18002df43  push    rdi
0x18002df44  push    r12
0x18002df46  push    r15
0x18002df48  sub     rsp, 20h
0x18002df4c  mov     rsi, r8
0x18002df4f  mov     rbx, rdx
0x18002df52  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df59  lea     r12, WPP_GLOBAL_Control
0x18002df60  lea     r15, WPP_fba0584bb98c356501b09d8c4620c3b4_Traceguids
0x18002df67  cmp     rcx, r12
0x18002df6a  jz      short loc_18002DF83
0x18002df6c  test    byte ptr [rcx+1Ch], 8
0x18002df70  jz      short loc_18002DF83
0x18002df72  mov     rcx, [rcx+10h]
0x18002df76  mov     edx, 16h
0x18002df7b  mov     r8, r15
0x18002df7e  call    WPP_SF_
0x18002df83  test    rsi, rsi
0x18002df86  jnz     short loc_18002DF92
0x18002df88  mov     eax, 80004003h
0x18002df8d  jmp     loc_18002E0AD
0x18002df92  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002df99  mov     qword ptr [rsi], 0
0x18002dfa0  mov     ecx, 68h ; 'h'; unsigned __int64
0x18002dfa5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002dfaa  mov     rdi, rax
0x18002dfad  test    rax, rax
0x18002dfb0  jz      loc_18002E080
0x18002dfb6  xor     edx, edx; Val
0x18002dfb8  mov     rcx, rax; void *
0x18002dfbb  lea     r8d, [rdx+68h]; Size
0x18002dfbf  call    memset_0
0x18002dfc4  lea     rdx, [rdi+40h]
0x18002dfc8  lea     rcx, [rdi+20h]
0x18002dfcc  mov     [rdi+18h], rdx
0x18002dfd0  lea     rax, aNetworktype; "NetworkType"
0x18002dfd7  mov     [rdi+10h], rcx
0x18002dfdb  lea     r8, ??_7?$AdminView@VEncryptedDwordProperty@RegistryPropertyBag@@@?$PersistablePropertyBag@PEAUHKEY__@@PEBG@@6B@; const PersistablePropertyBag<HKEY__ *,ushort const *>::AdminView<RegistryPropertyBag::EncryptedDwordProperty>::`vftable'
0x18002dfe2  mov     [rcx+18h], rax
0x18002dfe6  lea     rax, aConnectiontime; "ConnectionTimeout"
0x18002dfed  mov     [rcx], r8
0x18002dff0  mov     [rdx+18h], rax
0x18002dff4  mov     word ptr [rdx+8], 0
0x18002dffa  mov     byte ptr [rdx+0Ah], 0
0x18002dffe  mov     qword ptr [rdx+10h], 0
0x18002e006  mov     [rdx], r8
0x18002e009  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e010  cmp     rcx, r12
0x18002e013  jz      short loc_18002E04F
0x18002e015  test    byte ptr [rcx+1Ch], 8
0x18002e019  jz      short loc_18002E033
0x18002e01b  mov     rcx, [rcx+10h]
0x18002e01f  mov     edx, 0Ch
0x18002e024  mov     r8, r15
0x18002e027  call    WPP_SF_
0x18002e02c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e033  cmp     rcx, r12
0x18002e036  jz      short loc_18002E04F
0x18002e038  test    byte ptr [rcx+1Ch], 8
0x18002e03c  jz      short loc_18002E04F
0x18002e03e  mov     rcx, [rcx+10h]
0x18002e042  mov     edx, 0Ah
0x18002e047  mov     r8, r15
0x18002e04a  call    WPP_SF_
0x18002e04f  mov     [rdi+60h], rbx
0x18002e053  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e05a  cmp     rcx, r12
0x18002e05d  jz      short loc_18002E079
0x18002e05f  test    byte ptr [rcx+1Ch], 8
0x18002e063  jz      short loc_18002E079
0x18002e065  mov     rcx, [rcx+10h]
0x18002e069  mov     edx, 0Bh
0x18002e06e  xor     r9d, r9d
0x18002e071  mov     r8, r15
0x18002e074  call    WPP_SF_d
0x18002e079  xor     ebx, ebx
0x18002e07b  mov     [rsi], rdi
0x18002e07e  jmp     short loc_18002E085
0x18002e080  mov     ebx, 8007000Eh
0x18002e085  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e08c  cmp     rcx, r12
0x18002e08f  jz      short loc_18002E0AB
0x18002e091  test    byte ptr [rcx+1Ch], 8
0x18002e095  jz      short loc_18002E0AB
0x18002e097  mov     rcx, [rcx+10h]
0x18002e09b  mov     edx, 17h
0x18002e0a0  mov     r9d, ebx
0x18002e0a3  mov     r8, r15
0x18002e0a6  call    WPP_SF_d
0x18002e0ab  mov     eax, ebx
0x18002e0ad  add     rsp, 20h
0x18002e0b1  pop     r15
0x18002e0b3  pop     r12
0x18002e0b5  pop     rdi
0x18002e0b6  pop     rsi
0x18002e0b7  pop     rbx
0x18002e0b8  retn
```
