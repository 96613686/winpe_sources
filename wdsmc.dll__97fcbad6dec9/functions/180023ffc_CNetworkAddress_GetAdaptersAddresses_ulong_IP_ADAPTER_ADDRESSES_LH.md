# CNetworkAddress::GetAdaptersAddresses(ulong,_IP_ADAPTER_ADDRESSES_LH * *)

- ea: `0x180023ffc`
- end: `0x1800240ef`
- name: `?GetAdaptersAddresses@CNetworkAddress@@SAKKPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z`
- size: `243`
- prototype: `unsigned int __fastcall(ULONG Family, struct _IP_ADAPTER_ADDRESSES_LH **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023404`
- `0x180023b60`

## callees

- `0x18001a9a8`
- `0x180023ffc`
- `0x180025850`
- `0x180026694`

## import_xrefs

- `IPHLPAPI!GetAdaptersAddresses` at `0x18002404e`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180024081`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18002404e`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180024081`

## string_xrefs

- `0x180024094`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`
- `0x1800240d3`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`

## pseudocode

```c
__int64 __fastcall CNetworkAddress::GetAdaptersAddresses(ULONG Family, struct _IP_ADAPTER_ADDRESSES_LH **a2)
{
  ULONG i; // esi
  struct _IP_ADAPTER_ADDRESSES_LH *v4; // rdi
  ULONG v5; // eax
  const char *v6; // rdx
  ULONG v7; // ebx
  ULONG AdaptersAddresses; // eax
  const char *v9; // rdx
  ULONG SizePointer; // [rsp+50h] [rbp+18h] BYREF

  SizePointer = 0;
  for ( i = Family; ; Family = i )
  {
    AdaptersAddresses = GetAdaptersAddresses(Family, 8u, 0, 0, &SizePointer);
    v7 = AdaptersAddresses;
    if ( AdaptersAddresses != 111 )
    {
      ElValidateWin32(AdaptersAddresses, v9, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0xC09u);
      v4 = 0;
      goto LABEL_8;
    }
    v4 = (struct _IP_ADAPTER_ADDRESSES_LH *)operator new[](SizePointer, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v4 )
      return 8;
    v5 = GetAdaptersAddresses(i, 8u, 0, v4, &SizePointer);
    v7 = v5;
    if ( !v5 )
    {
      *a2 = v4;
      return v7;
    }
    if ( v5 != 111 )
      break;
    operator delete(v4);
  }
  ElValidateWin32(v5, v6, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0xC03u);
LABEL_8:
  if ( v7 && v4 )
    operator delete(v4);
  return v7;
}

```

## disassembly

```asm
0x180023ffc  mov     rax, rsp
0x180023fff  mov     [rax+8], rbx
0x180024003  mov     [rax+10h], rsi
0x180024007  mov     [rax+20h], rdi
0x18002400b  push    r14
0x18002400d  sub     rsp, 30h
0x180024011  and     dword ptr [rax+18h], 0
0x180024015  mov     r14, rdx
0x180024018  mov     esi, ecx
0x18002401a  jmp     short loc_18002406D
0x18002401c  mov     ecx, [rsp+38h+arg_10]; unsigned __int64
0x180024020  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024027  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002402c  mov     rdi, rax
0x18002402f  test    rax, rax
0x180024032  jz      loc_1800240E8
0x180024038  xor     r8d, r8d; Reserved
0x18002403b  lea     rax, [rsp+38h+arg_10]
0x180024040  mov     r9, rdi; AdapterAddresses
0x180024043  mov     [rsp+38h+SizePointer], rax; SizePointer
0x180024048  mov     ecx, esi; Family
0x18002404a  lea     edx, [r8+8]; Flags
0x18002404e  call    cs:__imp_GetAdaptersAddresses
0x180024054  mov     ebx, eax
0x180024056  test    eax, eax
0x180024058  jz      loc_1800240E3
0x18002405e  cmp     eax, 6Fh ; 'o'
0x180024061  jnz     short loc_1800240CD
0x180024063  mov     rcx, rdi; void *
0x180024066  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002406b  mov     ecx, esi; Family
0x18002406d  xor     r9d, r9d; AdapterAddresses
0x180024070  lea     rax, [rsp+38h+arg_10]
0x180024075  xor     r8d, r8d; Reserved
0x180024078  mov     [rsp+38h+SizePointer], rax; SizePointer
0x18002407d  lea     edx, [r9+8]; Flags
0x180024081  call    cs:__imp_GetAdaptersAddresses
0x180024087  mov     ebx, eax
0x180024089  cmp     eax, 6Fh ; 'o'
0x18002408c  jz      short loc_18002401C
0x18002408e  mov     r9d, 0C09h; unsigned int
0x180024094  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002409b  mov     ecx, eax; unsigned int
0x18002409d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800240a2  xor     edi, edi
0x1800240a4  test    ebx, ebx
0x1800240a6  jz      short loc_1800240B5
0x1800240a8  test    rdi, rdi
0x1800240ab  jz      short loc_1800240B5
0x1800240ad  mov     rcx, rdi; void *
0x1800240b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800240b5  mov     rsi, [rsp+38h+arg_8]
0x1800240ba  mov     eax, ebx
0x1800240bc  mov     rbx, [rsp+38h+arg_0]
0x1800240c1  mov     rdi, [rsp+38h+arg_18]
0x1800240c6  add     rsp, 30h
0x1800240ca  pop     r14
0x1800240cc  retn
0x1800240cd  mov     r9d, 0C03h; unsigned int
0x1800240d3  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800240da  mov     ecx, eax; unsigned int
0x1800240dc  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800240e1  jmp     short loc_1800240A4
0x1800240e3  mov     [r14], rdi
0x1800240e6  jmp     short loc_1800240B5
0x1800240e8  mov     ebx, 8
0x1800240ed  jmp     short loc_1800240B5
```
