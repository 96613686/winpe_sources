# CNetworkAddress::EnumInterfaces(ulong,tagWDS_INTERFACE_INFO * *,ulong *)

- ea: `0x180023404`
- end: `0x180023668`
- name: `?EnumInterfaces@CNetworkAddress@@SAKKPEAPEAUtagWDS_INTERFACE_INFO@@PEAK@Z`
- size: `612`
- prototype: `unsigned int __fastcall(ULONG Family, struct tagWDS_INTERFACE_INFO **, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023670`
- `0x1800237f0`
- `0x180023994`

## callees

- `0x18001a9a8`
- `0x18002334c`
- `0x180023404`
- `0x180023ffc`
- `0x180025850`
- `0x180026694`
- `0x180026b98`
- `0x180026c08`
- `0x180026d3a`

## import_xrefs

- `WS2_32!__imp_inet_addr` at `0x18002364b`
- `WS2_32!__imp_inet_addr` at `0x18002364b`

## string_xrefs

- `0x180023468`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`

## pseudocode

```c
__int64 __fastcall CNetworkAddress::EnumInterfaces(ULONG Family, struct tagWDS_INTERFACE_INFO **a2, unsigned int *a3)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  unsigned int v5; // r13d
  struct tagWDS_INTERFACE_INFO *v6; // rsi
  unsigned int AdaptersAddresses; // r15d
  const char *v8; // rdx
  struct _IP_ADAPTER_ADDRESSES_LH *i; // rbx
  PIP_ADAPTER_UNICAST_ADDRESS_LH j; // rdi
  unsigned __int64 v11; // rax
  struct _IP_ADAPTER_ADDRESSES_LH *v12; // rdi
  __int64 v13; // r14
  PIP_ADAPTER_UNICAST_ADDRESS_LH FirstUnicastAddress; // rbp
  __int64 v15; // rbx
  char *v16; // rbx
  struct _IP_ADAPTER_ADDRESSES_LH *v20; // [rsp+78h] [rbp+20h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v5 = 0;
  v20 = 0;
  v6 = 0;
  if ( dword_1800336F8 > *(_DWORD *)(ThreadLocalStoragePointer[tls_index] + 4LL) )
  {
    Init_thread_header(&dword_1800336F8);
    if ( dword_1800336F8 == -1 )
    {
      dword_1800336FC = inet_addr("127.0.0.1");
      Init_thread_footer(&dword_1800336F8);
    }
  }
  AdaptersAddresses = CNetworkAddress::GetAdaptersAddresses(Family, &v20);
  if ( !ElValidateWin32(AdaptersAddresses, v8, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0x78Au) )
  {
    for ( i = v20; i; i = i->Next )
    {
      if ( i->PhysicalAddressLength <= 0x10 && i->OperStatus == IfOperStatusUp )
      {
        for ( j = i->FirstUnicastAddress; j; j = j->Next )
        {
          if ( (unsigned int)CNetworkAddress::IsValidSockAddress(&j->Address) )
            ++v5;
        }
      }
    }
    v11 = 48LL * v5;
    if ( !is_mul_ok(v5, 0x30u) )
      v11 = -1;
    v6 = (struct tagWDS_INTERFACE_INFO *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
    if ( v6 )
    {
      v12 = v20;
      v13 = 0;
      while ( v12 )
      {
        if ( v12->PhysicalAddressLength <= 0x10 && v12->OperStatus == IfOperStatusUp )
        {
          FirstUnicastAddress = v12->FirstUnicastAddress;
          while ( FirstUnicastAddress && (unsigned int)v13 < v5 )
          {
            if ( (unsigned int)CNetworkAddress::IsValidSockAddress(&FirstUnicastAddress->Address) )
            {
              if ( FirstUnicastAddress->Address.iSockaddrLength == 16 )
              {
                v15 = 48 * v13;
                memmove_0((char *)v6 + 48 * v13 + 20, v12->PhysicalAddress, v12->PhysicalAddressLength);
                *(_DWORD *)((char *)v6 + v15 + 36) = v12->PhysicalAddressLength;
                *(_DWORD *)((char *)v6 + v15) = *(_DWORD *)&FirstUnicastAddress->Address.lpSockaddr->sa_data[2];
                *(_DWORD *)((char *)v6 + v15 + 16) = 4;
                *(_DWORD *)((char *)v6 + v15 + 40) = v12->IfIndex;
                *((_BYTE *)v6 + v15 + 44) = 0;
                goto LABEL_27;
              }
              if ( FirstUnicastAddress->Address.iSockaddrLength == 28 )
              {
                v16 = (char *)v6 + 48 * v13;
                memmove_0(v16 + 20, v12->PhysicalAddress, v12->PhysicalAddressLength);
                *((_DWORD *)v16 + 9) = v12->PhysicalAddressLength;
                *((_DWORD *)v16 + 4) = 16;
                memmove_0(v16, &FirstUnicastAddress->Address.lpSockaddr->sa_data[6], 0x10u);
                *((_DWORD *)v16 + 10) = v12->Ipv6IfIndex;
                v16[44] = FirstUnicastAddress->SuffixOrigin == NlsoRandom;
LABEL_27:
                v13 = (unsigned int)(v13 + 1);
              }
            }
            FirstUnicastAddress = FirstUnicastAddress->Next;
            continue;
          }
        }
        v12 = v12->Next;
      }
      *a3 = v13;
      *a2 = v6;
    }
    else
    {
      AdaptersAddresses = 8;
    }
  }
  if ( v20 )
    operator delete(v20);
  if ( AdaptersAddresses && v6 )
    operator delete(v6);
  return AdaptersAddresses;
}

```

## disassembly

```asm
0x180023404  mov     [rsp+arg_10], r8
0x180023409  mov     [rsp+arg_8], rdx
0x18002340e  push    rbx
0x18002340f  push    rbp
0x180023410  push    rsi
0x180023411  push    rdi
0x180023412  push    r13
0x180023414  push    r14
0x180023416  push    r15
0x180023418  sub     rsp, 20h
0x18002341c  mov     rax, gs:58h
0x180023425  mov     ebx, ecx
0x180023427  mov     r9d, cs:_tls_index
0x18002342e  xor     r13d, r13d
0x180023431  and     [rsp+58h+arg_18], 0
0x180023437  xor     esi, esi
0x180023439  mov     ecx, 4
0x18002343e  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180023442  mov     r10, [rax+r9*8]
0x180023446  mov     eax, [rcx+r10]
0x18002344a  cmp     cs:dword_1800336F8, eax
0x180023450  jg      loc_18002362C
0x180023456  lea     rdx, [rsp+58h+arg_18]; struct _IP_ADAPTER_ADDRESSES_LH **
0x18002345b  mov     ecx, ebx; Family
0x18002345d  call    ?GetAdaptersAddresses@CNetworkAddress@@SAKKPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; CNetworkAddress::GetAdaptersAddresses(ulong,_IP_ADAPTER_ADDRESSES_LH * *)
0x180023462  mov     r9d, 78Ah; unsigned int
0x180023468  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002346f  mov     ecx, eax; unsigned int
0x180023471  mov     r15d, eax
0x180023474  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180023479  test    eax, eax
0x18002347b  jnz     loc_1800235F6
0x180023481  mov     rbx, [rsp+58h+arg_18]
0x180023486  jmp     short loc_1800234B7
0x180023488  cmp     dword ptr [rbx+58h], 10h
0x18002348c  ja      short loc_1800234B3
0x18002348e  cmp     dword ptr [rbx+68h], 1
0x180023492  jnz     short loc_1800234B3
0x180023494  mov     rdi, [rbx+18h]
0x180023498  jmp     short loc_1800234AE
0x18002349a  lea     rcx, [rdi+10h]; struct _SOCKET_ADDRESS *
0x18002349e  call    ?IsValidSockAddress@CNetworkAddress@@CAHPEAU_SOCKET_ADDRESS@@@Z; CNetworkAddress::IsValidSockAddress(_SOCKET_ADDRESS *)
0x1800234a3  test    eax, eax
0x1800234a5  jz      short loc_1800234AA
0x1800234a7  inc     r13d
0x1800234aa  mov     rdi, [rdi+8]
0x1800234ae  test    rdi, rdi
0x1800234b1  jnz     short loc_18002349A
0x1800234b3  mov     rbx, [rbx+8]
0x1800234b7  test    rbx, rbx
0x1800234ba  jnz     short loc_180023488
0x1800234bc  mov     ecx, r13d
0x1800234bf  lea     eax, [rbx+30h]
0x1800234c2  mul     rcx
0x1800234c5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800234cc  cmovo   rax, rbp
0x1800234d0  mov     rcx, rax; unsigned __int64
0x1800234d3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800234d8  mov     rsi, rax
0x1800234db  test    rax, rax
0x1800234de  jnz     short loc_1800234E9
0x1800234e0  lea     r15d, [rbx+8]
0x1800234e4  jmp     loc_1800235F6
0x1800234e9  mov     rdi, [rsp+58h+arg_18]
0x1800234ee  xor     r14d, r14d
0x1800234f1  jmp     loc_1800235DD
0x1800234f6  cmp     dword ptr [rdi+58h], 10h
0x1800234fa  ja      loc_1800235D9
0x180023500  cmp     dword ptr [rdi+68h], 1
0x180023504  jnz     loc_1800235D9
0x18002350a  mov     rbp, [rdi+18h]
0x18002350e  jmp     loc_1800235D0
0x180023513  cmp     r14d, r13d
0x180023516  jnb     loc_1800235D9
0x18002351c  lea     rcx, [rbp+10h]; struct _SOCKET_ADDRESS *
0x180023520  call    ?IsValidSockAddress@CNetworkAddress@@CAHPEAU_SOCKET_ADDRESS@@@Z; CNetworkAddress::IsValidSockAddress(_SOCKET_ADDRESS *)
0x180023525  test    eax, eax
0x180023527  jz      loc_1800235CC
0x18002352d  cmp     dword ptr [rbp+18h], 10h
0x180023531  jnz     short loc_180023576
0x180023533  mov     r8d, [rdi+58h]; Size
0x180023537  lea     rbx, [r14+r14*2]
0x18002353b  shl     rbx, 4
0x18002353f  lea     rcx, [rsi+14h]
0x180023543  add     rcx, rbx; void *
0x180023546  lea     rdx, [rdi+50h]; Src
0x18002354a  call    memmove_0
0x18002354f  mov     eax, [rdi+58h]
0x180023552  mov     [rbx+rsi+24h], eax
0x180023556  mov     rax, [rbp+10h]
0x18002355a  mov     ecx, [rax+4]
0x18002355d  mov     [rbx+rsi], ecx
0x180023560  mov     dword ptr [rbx+rsi+10h], 4
0x180023568  mov     eax, [rdi+4]
0x18002356b  mov     [rbx+rsi+28h], eax
0x18002356f  mov     byte ptr [rbx+rsi+2Ch], 0
0x180023574  jmp     short loc_1800235C9
0x180023576  cmp     dword ptr [rbp+18h], 1Ch
0x18002357a  jnz     short loc_1800235CC
0x18002357c  mov     r8d, [rdi+58h]; Size
0x180023580  lea     rbx, [r14+r14*2]
0x180023584  shl     rbx, 4
0x180023588  lea     rdx, [rdi+50h]; Src
0x18002358c  add     rbx, rsi
0x18002358f  lea     rcx, [rbx+14h]; void *
0x180023593  call    memmove_0
0x180023598  mov     eax, [rdi+58h]
0x18002359b  mov     rcx, rbx; void *
0x18002359e  mov     [rbx+24h], eax
0x1800235a1  mov     eax, 10h
0x1800235a6  mov     [rbx+10h], eax
0x1800235a9  mov     r8d, eax; Size
0x1800235ac  mov     rdx, [rbp+10h]
0x1800235b0  add     rdx, 8; Src
0x1800235b4  call    memmove_0
0x1800235b9  mov     eax, [rdi+6Ch]
0x1800235bc  mov     [rbx+28h], eax
0x1800235bf  cmp     dword ptr [rbp+24h], 5
0x1800235c3  setz    al
0x1800235c6  mov     [rbx+2Ch], al
0x1800235c9  inc     r14d
0x1800235cc  mov     rbp, [rbp+8]
0x1800235d0  test    rbp, rbp
0x1800235d3  jnz     loc_180023513
0x1800235d9  mov     rdi, [rdi+8]
0x1800235dd  test    rdi, rdi
0x1800235e0  jnz     loc_1800234F6
0x1800235e6  mov     rax, [rsp+58h+arg_10]
0x1800235eb  mov     [rax], r14d
0x1800235ee  mov     rax, [rsp+58h+arg_8]
0x1800235f3  mov     [rax], rsi
0x1800235f6  cmp     [rsp+58h+arg_18], 0
0x1800235fc  jz      short loc_180023608
0x1800235fe  mov     rcx, [rsp+58h+arg_18]; void *
0x180023603  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023608  test    r15d, r15d
0x18002360b  jz      short loc_18002361A
0x18002360d  test    rsi, rsi
0x180023610  jz      short loc_18002361A
0x180023612  mov     rcx, rsi; void *
0x180023615  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002361a  mov     eax, r15d
0x18002361d  add     rsp, 20h
0x180023621  pop     r15
0x180023623  pop     r14
0x180023625  pop     r13
0x180023627  pop     rdi
0x180023628  pop     rsi
0x180023629  pop     rbp
0x18002362a  pop     rbx
0x18002362b  retn
0x18002362c  lea     rcx, dword_1800336F8
0x180023633  call    _Init_thread_header
0x180023638  cmp     cs:dword_1800336F8, ebp
0x18002363e  jnz     loc_180023456
0x180023644  lea     rcx, cp; "127.0.0.1"
0x18002364b  call    cs:__imp_inet_addr
0x180023651  lea     rcx, dword_1800336F8
0x180023658  mov     cs:dword_1800336FC, eax
0x18002365e  call    _Init_thread_footer
0x180023663  jmp     loc_180023456
```
