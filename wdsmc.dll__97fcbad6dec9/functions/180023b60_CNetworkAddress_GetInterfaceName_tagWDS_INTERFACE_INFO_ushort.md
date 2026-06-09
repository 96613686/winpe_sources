# CNetworkAddress::GetInterfaceName(tagWDS_INTERFACE_INFO *,ushort * *)

- ea: `0x180023b60`
- end: `0x180023c49`
- name: `?GetInterfaceName@CNetworkAddress@@SAKPEAUtagWDS_INTERFACE_INFO@@PEAPEAG@Z`
- size: `233`
- prototype: `static unsigned int(struct tagWDS_INTERFACE_INFO *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800148b4`

## callees

- `0x18001a9a8`
- `0x180023b60`
- `0x180023ffc`
- `0x1800244bc`
- `0x180025850`
- `0x180026670`
- `0x180026d22`
- `0x180026d3a`

## string_xrefs

- `0x180023bb9`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`

## pseudocode

```c
__int64 __fastcall CNetworkAddress::GetInterfaceName(struct tagWDS_INTERFACE_INFO *a1, unsigned __int16 **a2)
{
  size_t v2; // r8
  unsigned int AdaptersAddresses; // ebx
  const char *v5; // rdx
  struct _IP_ADAPTER_ADDRESSES_LH *v6; // rbx
  size_t v7; // rsi
  struct _IP_ADAPTER_ADDRESSES_LH *v9; // [rsp+20h] [rbp-38h] BYREF
  _QWORD Buf2[2]; // [rsp+28h] [rbp-30h] BYREF
  size_t Size; // [rsp+38h] [rbp-20h]

  v2 = *((unsigned int *)a1 + 9);
  Buf2[0] = 0;
  Buf2[1] = 0;
  LODWORD(Size) = v2;
  memmove_0(Buf2, (char *)a1 + 20, v2);
  v9 = 0;
  AdaptersAddresses = CNetworkAddress::GetAdaptersAddresses(0, &v9);
  if ( !ElValidateWin32(AdaptersAddresses, v5, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0x9F8u) )
  {
    v6 = v9;
    if ( !v9 )
      goto LABEL_9;
    v7 = (unsigned int)Size;
    do
    {
      if ( v6->PhysicalAddressLength == (_DWORD)v7 && !memcmp_0(v6->PhysicalAddress, Buf2, v7) )
        break;
      v6 = v6->Next;
    }
    while ( v6 );
    if ( v6 )
      AdaptersAddresses = DuplicateStringW(v6->Description, a2);
    else
LABEL_9:
      AdaptersAddresses = 2;
  }
  if ( v9 )
    operator delete(v9);
  return AdaptersAddresses;
}

```

## disassembly

```asm
0x180023b60  mov     r11, rsp
0x180023b63  mov     [r11+18h], rbx
0x180023b67  mov     [r11+20h], rbp
0x180023b6b  push    rsi
0x180023b6c  sub     rsp, 50h
0x180023b70  mov     rax, cs:__security_cookie
0x180023b77  xor     rax, rsp
0x180023b7a  mov     [rsp+58h+var_18], rax
0x180023b7f  mov     r8d, [rcx+24h]; Size
0x180023b83  xor     eax, eax
0x180023b85  mov     rbp, rdx
0x180023b88  mov     [r11-30h], rax
0x180023b8c  lea     rdx, [rcx+14h]; Src
0x180023b90  mov     [r11-28h], rax
0x180023b94  lea     rcx, [r11-30h]; void *
0x180023b98  mov     [r11-20h], r8d
0x180023b9c  call    memmove_0
0x180023ba1  and     [rsp+58h+var_38], 0
0x180023ba7  lea     rdx, [rsp+58h+var_38]; struct _IP_ADAPTER_ADDRESSES_LH **
0x180023bac  xor     ecx, ecx; Family
0x180023bae  call    ?GetAdaptersAddresses@CNetworkAddress@@SAKKPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; CNetworkAddress::GetAdaptersAddresses(ulong,_IP_ADAPTER_ADDRESSES_LH * *)
0x180023bb3  mov     r9d, 9F8h; unsigned int
0x180023bb9  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180023bc0  mov     ecx, eax; unsigned int
0x180023bc2  mov     ebx, eax
0x180023bc4  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180023bc9  test    eax, eax
0x180023bcb  jnz     short loc_180023C18
0x180023bcd  mov     rbx, [rsp+58h+var_38]
0x180023bd2  test    rbx, rbx
0x180023bd5  jz      short loc_180023C13
0x180023bd7  mov     esi, dword ptr [rsp+58h+Size]
0x180023bdb  cmp     [rbx+58h], esi
0x180023bde  jnz     short loc_180023BF5
0x180023be0  mov     r8, rsi; Size
0x180023be3  lea     rcx, [rbx+50h]; Buf1
0x180023be7  lea     rdx, [rsp+58h+Buf2]; Buf2
0x180023bec  call    memcmp_0
0x180023bf1  test    eax, eax
0x180023bf3  jz      short loc_180023BFE
0x180023bf5  mov     rbx, [rbx+8]
0x180023bf9  test    rbx, rbx
0x180023bfc  jnz     short loc_180023BDB
0x180023bfe  test    rbx, rbx
0x180023c01  jz      short loc_180023C13
0x180023c03  mov     rcx, [rbx+40h]; unsigned __int16 *
0x180023c07  mov     rdx, rbp; unsigned __int16 **
0x180023c0a  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180023c0f  mov     ebx, eax
0x180023c11  jmp     short loc_180023C18
0x180023c13  mov     ebx, 2
0x180023c18  cmp     [rsp+58h+var_38], 0
0x180023c1e  jz      short loc_180023C2A
0x180023c20  mov     rcx, [rsp+58h+var_38]; void *
0x180023c25  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023c2a  mov     eax, ebx
0x180023c2c  mov     rcx, [rsp+58h+var_18]
0x180023c31  xor     rcx, rsp; StackCookie
0x180023c34  call    __security_check_cookie
0x180023c39  mov     rbx, [rsp+58h+arg_10]
0x180023c3e  mov     rbp, [rsp+58h+arg_18]
0x180023c43  add     rsp, 50h
0x180023c47  pop     rsi
0x180023c48  retn
```
