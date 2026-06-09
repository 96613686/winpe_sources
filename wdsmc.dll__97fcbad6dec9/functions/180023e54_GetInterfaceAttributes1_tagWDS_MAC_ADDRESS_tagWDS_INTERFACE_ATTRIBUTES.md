# GetInterfaceAttributes1(tagWDS_MAC_ADDRESS *,tagWDS_INTERFACE_ATTRIBUTES * *)

- ea: `0x180023e54`
- end: `0x180023ff6`
- name: `?GetInterfaceAttributes1@@YAKPEAUtagWDS_MAC_ADDRESS@@PEAPEAUtagWDS_INTERFACE_ATTRIBUTES@@@Z`
- size: `418`
- prototype: `unsigned int __fastcall(struct tagWDS_MAC_ADDRESS *Buf2, struct tagWDS_INTERFACE_ATTRIBUTES **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018240`

## callees

- `0x18001a9a8`
- `0x180023e54`
- `0x180025850`
- `0x180026694`
- `0x1800266a0`
- `0x180026d22`

## import_xrefs

- `IPHLPAPI!GetIfTable` at `0x180023ec4`
- `IPHLPAPI!GetIfTable` at `0x180023f07`
- `IPHLPAPI!GetIfTable` at `0x180023ec4`
- `IPHLPAPI!GetIfTable` at `0x180023f07`

## string_xrefs

- `0x180023e87`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`
- `0x180023edb`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`
- `0x180023f6d`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`

## pseudocode

```c
__int64 __fastcall GetInterfaceAttributes1(struct tagWDS_MAC_ADDRESS *Buf2, struct tagWDS_INTERFACE_ATTRIBUTES **a2)
{
  unsigned int *wszName; // rdi
  struct _MIB_IFTABLE *v5; // rax
  struct _MIB_IFTABLE *v6; // rsi
  DWORD v7; // eax
  const char *v8; // rdx
  unsigned int v9; // ebx
  DWORD IfTable; // eax
  DWORD v11; // ebp
  size_t v12; // r14
  struct tagWDS_INTERFACE_ATTRIBUTES *v13; // rax
  ULONG pdwSize; // [rsp+60h] [rbp+18h] BYREF

  pdwSize = 0;
  wszName = 0;
  while ( 1 )
  {
    IfTable = GetIfTable(0, &pdwSize, 0);
    v9 = IfTable;
    if ( !IfTable )
      break;
    if ( IfTable != 122
      && ElValidateWin32(IfTable, v8, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0xB4Bu) )
    {
      return v9;
    }
    v5 = (struct _MIB_IFTABLE *)operator new[](pdwSize, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v5;
    if ( !v5 )
      return 8;
    v7 = GetIfTable(v5, &pdwSize, 0);
    v9 = v7;
    if ( !v7 )
      goto LABEL_11;
    if ( v7 != 122 && ElValidateWin32(v7, v8, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0xB58u) )
      goto LABEL_23;
    operator delete(v6);
    pdwSize = 0;
  }
  v6 = 0;
LABEL_11:
  v11 = 0;
  if ( v6->dwNumEntries )
  {
    v12 = *((unsigned int *)Buf2 + 4);
    do
    {
      wszName = (unsigned int *)v6->table[v11].wszName;
      if ( wszName[132] == (_DWORD)v12 && !memcmp_0(wszName + 133, Buf2, v12) && wszName[136] == 5 )
        break;
      wszName = 0;
      ++v11;
    }
    while ( v11 < v6->dwNumEntries );
    if ( wszName )
      goto LABEL_19;
  }
  v9 = 2;
  if ( !ElValidateWin32(2u, v8, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0xB77u) )
  {
LABEL_19:
    v13 = (struct tagWDS_INTERFACE_ATTRIBUTES *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v13 )
    {
      *(_QWORD *)v13 = wszName[131];
      *((_QWORD *)v13 + 1) = wszName[131];
      *((_QWORD *)v13 + 2) = wszName[138];
      *((_QWORD *)v13 + 3) = wszName[144];
      *a2 = v13;
    }
    else
    {
      v9 = 8;
    }
  }
LABEL_23:
  operator delete(v6);
  return v9;
}

```

## disassembly

```asm
0x180023e54  mov     [rsp+arg_0], rbx
0x180023e59  mov     [rsp+arg_8], rbp
0x180023e5e  push    rsi
0x180023e5f  push    rdi
0x180023e60  push    r12
0x180023e62  push    r14
0x180023e64  push    r15
0x180023e66  sub     rsp, 20h
0x180023e6a  and     [rsp+48h+pdwSize], 0
0x180023e6f  mov     r12, rdx
0x180023e72  xor     edi, edi
0x180023e74  mov     r15, rcx
0x180023e77  jmp     loc_180023EFD
0x180023e7c  cmp     ebx, 7Ah ; 'z'
0x180023e7f  jz      short loc_180023E9D
0x180023e81  mov     r9d, 0B4Bh; unsigned int
0x180023e87  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180023e8e  mov     ecx, ebx; unsigned int
0x180023e90  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180023e95  test    eax, eax
0x180023e97  jnz     loc_180023FDD
0x180023e9d  mov     ecx, [rsp+48h+pdwSize]; unsigned __int64
0x180023ea1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023ea8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180023ead  mov     rsi, rax
0x180023eb0  test    rax, rax
0x180023eb3  jz      loc_180023FA3
0x180023eb9  xor     r8d, r8d; bOrder
0x180023ebc  lea     rdx, [rsp+48h+pdwSize]; pdwSize
0x180023ec1  mov     rcx, rax; pIfTable
0x180023ec4  call    cs:__imp_GetIfTable
0x180023eca  mov     ebx, eax
0x180023ecc  test    eax, eax
0x180023ece  jz      short loc_180023F19
0x180023ed0  cmp     eax, 7Ah ; 'z'
0x180023ed3  jz      short loc_180023EF1
0x180023ed5  mov     r9d, 0B58h; unsigned int
0x180023edb  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180023ee2  mov     ecx, eax; unsigned int
0x180023ee4  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180023ee9  test    eax, eax
0x180023eeb  jnz     loc_180023FD5
0x180023ef1  mov     rcx, rsi; void *
0x180023ef4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023ef9  and     [rsp+48h+pdwSize], edi
0x180023efd  xor     r8d, r8d; bOrder
0x180023f00  lea     rdx, [rsp+48h+pdwSize]; pdwSize
0x180023f05  xor     ecx, ecx; pIfTable
0x180023f07  call    cs:__imp_GetIfTable
0x180023f0d  mov     ebx, eax
0x180023f0f  test    eax, eax
0x180023f11  jnz     loc_180023E7C
0x180023f17  xor     esi, esi
0x180023f19  xor     ebp, ebp
0x180023f1b  cmp     [rsi], edi
0x180023f1d  jbe     short loc_180023F68
0x180023f1f  mov     r14d, [r15+10h]
0x180023f23  mov     eax, ebp
0x180023f25  lea     rdi, [rsi+4]
0x180023f29  imul    rcx, rax, 35Ch
0x180023f30  add     rdi, rcx
0x180023f33  cmp     [rdi+210h], r14d
0x180023f3a  jnz     short loc_180023F5B
0x180023f3c  mov     r8, r14; Size
0x180023f3f  lea     rcx, [rdi+214h]; Buf1
0x180023f46  mov     rdx, r15; Buf2
0x180023f49  call    memcmp_0
0x180023f4e  test    eax, eax
0x180023f50  jnz     short loc_180023F5B
0x180023f52  cmp     dword ptr [rdi+220h], 5
0x180023f59  jz      short loc_180023F63
0x180023f5b  xor     edi, edi
0x180023f5d  inc     ebp
0x180023f5f  cmp     ebp, [rsi]
0x180023f61  jb      short loc_180023F23
0x180023f63  test    rdi, rdi
0x180023f66  jnz     short loc_180023F85
0x180023f68  mov     ebx, 2
0x180023f6d  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180023f74  mov     ecx, ebx; unsigned int
0x180023f76  mov     r9d, 0B77h; unsigned int
0x180023f7c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180023f81  test    eax, eax
0x180023f83  jnz     short loc_180023FD5
0x180023f85  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023f8c  mov     ecx, 20h ; ' '; unsigned __int64
0x180023f91  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180023f96  mov     rcx, rax
0x180023f99  test    rax, rax
0x180023f9c  jnz     short loc_180023FAA
0x180023f9e  lea     ebx, [rax+8]
0x180023fa1  jmp     short loc_180023FD5
0x180023fa3  mov     ebx, 8
0x180023fa8  jmp     short loc_180023FDD
0x180023faa  mov     eax, [rdi+20Ch]
0x180023fb0  mov     [rcx], rax
0x180023fb3  mov     eax, [rdi+20Ch]
0x180023fb9  mov     [rcx+8], rax
0x180023fbd  mov     eax, [rdi+228h]
0x180023fc3  mov     [rcx+10h], rax
0x180023fc7  mov     eax, [rdi+240h]
0x180023fcd  mov     [rcx+18h], rax
0x180023fd1  mov     [r12], rcx
0x180023fd5  mov     rcx, rsi; void *
0x180023fd8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023fdd  mov     rbp, [rsp+48h+arg_8]
0x180023fe2  mov     eax, ebx
0x180023fe4  mov     rbx, [rsp+48h+arg_0]
0x180023fe9  add     rsp, 20h
0x180023fed  pop     r15
0x180023fef  pop     r14
0x180023ff1  pop     r12
0x180023ff3  pop     rdi
0x180023ff4  pop     rsi
0x180023ff5  retn
```
