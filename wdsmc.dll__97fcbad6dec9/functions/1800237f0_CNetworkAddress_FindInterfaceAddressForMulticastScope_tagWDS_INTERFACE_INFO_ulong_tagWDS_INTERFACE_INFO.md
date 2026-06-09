# CNetworkAddress::FindInterfaceAddressForMulticastScope(tagWDS_INTERFACE_INFO *,ulong,tagWDS_INTERFACE_INFO *)

- ea: `0x1800237f0`
- end: `0x18002398b`
- name: `?FindInterfaceAddressForMulticastScope@CNetworkAddress@@SAHPEAUtagWDS_INTERFACE_INFO@@K0@Z`
- size: `411`
- prototype: `__int64 __fastcall(struct tagWDS_INTERFACE_INFO *, unsigned int, struct tagWDS_INTERFACE_INFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015e94`

## callees

- `0x18001a9a8`
- `0x180023404`
- `0x1800237f0`
- `0x180023a78`
- `0x180025850`
- `0x180026670`
- `0x180026d22`
- `0x180026d3a`

## string_xrefs

- `0x18002384f`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`

## pseudocode

```c
__int64 __fastcall CNetworkAddress::FindInterfaceAddressForMulticastScope(
        struct tagWDS_INTERFACE_INFO *a1,
        unsigned int a2,
        struct tagWDS_INTERFACE_INFO *a3)
{
  __int64 v3; // rdi
  int v4; // esi
  unsigned int v5; // r12d
  unsigned int v6; // eax
  const char *v7; // rdx
  unsigned int v8; // eax
  struct tagWDS_INTERFACE_INFO *v9; // rbx
  struct tagWDS_INTERFACE_INFO *v10; // r13
  char *v11; // r14
  unsigned int v12; // eax
  unsigned int v13; // edx
  struct tagWDS_INTERFACE_INFO *v14; // r13
  unsigned int v16; // [rsp+20h] [rbp-39h] BYREF
  int v17; // [rsp+24h] [rbp-35h]
  unsigned int v18; // [rsp+28h] [rbp-31h]
  struct tagWDS_INTERFACE_INFO *v19; // [rsp+30h] [rbp-29h] BYREF
  struct tagWDS_INTERFACE_INFO *v20; // [rsp+38h] [rbp-21h]
  struct tagWDS_INTERFACE_INFO *v21; // [rsp+40h] [rbp-19h]
  __int128 v22; // [rsp+50h] [rbp-9h] BYREF
  unsigned int v23; // [rsp+60h] [rbp+7h]
  __int128 v24; // [rsp+70h] [rbp+17h] BYREF
  unsigned int v25; // [rsp+80h] [rbp+27h]

  v3 = 0;
  v21 = a3;
  v19 = 0;
  v16 = 0;
  v4 = -1;
  v18 = a2;
  v5 = 0;
  v20 = a1;
  v17 = 0;
  v6 = CNetworkAddress::EnumInterfaces(0x17u, &v19, &v16);
  v8 = ElValidateWin32(v6, v7, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0x890u);
  v9 = v19;
  if ( !v8 && v16 )
  {
    v10 = v20;
    do
    {
      v11 = (char *)v9 + 48 * v3;
      v12 = *((_DWORD *)v11 + 9);
      if ( v12 == *((_DWORD *)v10 + 9) && !memcmp_0(v11 + 20, (char *)v10 + 20, v12) )
      {
        v25 = *((_DWORD *)v11 + 4);
        v24 = 0u;
        memmove_0(&v24, (char *)v9 + 48 * v3, v25);
        v23 = v25;
        v22 = v24;
        v13 = v25 == 16 ? CNetworkAddress::GetIPv6MulticastAddressScope(&v22) : 0;
        if ( v13 >= v18 && (v4 < 0 || v5 > v13 || v5 == v13 && !v11[44] && *((_BYTE *)v9 + 48 * v4 + 44) == 1) )
        {
          v4 = v3;
          v5 = v13;
        }
      }
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < v16 );
    v14 = v21;
    if ( v4 < 0 )
    {
      LODWORD(v3) = v17;
    }
    else
    {
      LODWORD(v3) = 1;
      *(_OWORD *)v21 = *((_OWORD *)v9 + 3 * v4);
      *((_OWORD *)v14 + 1) = *((_OWORD *)v9 + 3 * v4 + 1);
      *((_OWORD *)v14 + 2) = *((_OWORD *)v9 + 3 * v4 + 2);
    }
  }
  if ( v9 )
    operator delete(v9);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800237f0  mov     [rsp-8+arg_0], rbx
0x1800237f5  mov     [rsp-8+arg_8], rsi
0x1800237fa  push    rbp
0x1800237fb  push    rdi
0x1800237fc  push    r12
0x1800237fe  push    r13
0x180023800  push    r14
0x180023802  lea     rbp, [rsp-37h]
0x180023807  sub     rsp, 90h
0x18002380e  mov     rax, cs:__security_cookie
0x180023815  xor     rax, rsp
0x180023818  mov     [rbp+57h+var_28], rax
0x18002381c  xor     edi, edi
0x18002381e  mov     [rbp+57h+var_70], r8
0x180023822  and     [rbp+57h+var_80], rdi
0x180023826  lea     r8, [rbp+57h+var_90]; unsigned int *
0x18002382a  and     [rbp+57h+var_90], edi
0x18002382d  or      esi, 0FFFFFFFFh
0x180023830  mov     [rbp+57h+var_88], edx
0x180023833  xor     r12d, r12d
0x180023836  mov     [rbp+57h+var_78], rcx
0x18002383a  lea     rdx, [rbp+57h+var_80]; struct tagWDS_INTERFACE_INFO **
0x18002383e  lea     ecx, [rdi+17h]; Family
0x180023841  mov     [rbp+57h+var_8C], edi
0x180023844  call    ?EnumInterfaces@CNetworkAddress@@SAKKPEAPEAUtagWDS_INTERFACE_INFO@@PEAK@Z; CNetworkAddress::EnumInterfaces(ulong,tagWDS_INTERFACE_INFO * *,ulong *)
0x180023849  mov     r9d, 890h; unsigned int
0x18002384f  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180023856  mov     ecx, eax; unsigned int
0x180023858  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18002385d  mov     rbx, [rbp+57h+var_80]
0x180023861  test    eax, eax
0x180023863  jnz     loc_180023954
0x180023869  cmp     [rbp+57h+var_90], edi
0x18002386c  jbe     loc_180023954
0x180023872  mov     r13, [rbp+57h+var_78]
0x180023876  lea     r14, [rdi+rdi*2]
0x18002387a  shl     r14, 4
0x18002387e  add     r14, rbx
0x180023881  mov     eax, [r14+24h]
0x180023885  cmp     eax, [r13+24h]
0x180023889  jnz     loc_180023910
0x18002388f  mov     r8d, eax; Size
0x180023892  lea     rdx, [r13+14h]; Buf2
0x180023896  lea     rcx, [r14+14h]; Buf1
0x18002389a  call    memcmp_0
0x18002389f  test    eax, eax
0x1800238a1  jnz     short loc_180023910
0x1800238a3  mov     r8d, [r14+10h]; Size
0x1800238a7  lea     rcx, [rbp+57h+var_40]; void *
0x1800238ab  xor     eax, eax
0x1800238ad  mov     [rbp+57h+var_30], r8d
0x1800238b1  mov     rdx, r14; Src
0x1800238b4  mov     qword ptr [rbp+57h+var_40], rax
0x1800238b8  mov     qword ptr [rbp+57h+var_40+8], rax
0x1800238bc  call    memmove_0
0x1800238c1  mov     eax, [rbp+57h+var_30]
0x1800238c4  mov     [rbp+57h+var_50], eax
0x1800238c7  movups  xmm0, [rbp+57h+var_40]
0x1800238cb  movaps  [rbp+57h+var_60], xmm0
0x1800238cf  cmp     eax, 10h
0x1800238d2  jz      short loc_1800238D8
0x1800238d4  xor     edx, edx
0x1800238d6  jmp     short loc_1800238E3
0x1800238d8  lea     rcx, [rbp+57h+var_60]
0x1800238dc  call    ?GetIPv6MulticastAddressScope@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@@Z; CNetworkAddress::GetIPv6MulticastAddressScope(tagWDS_IP_ADDRESS6)
0x1800238e1  mov     edx, eax
0x1800238e3  cmp     edx, [rbp+57h+var_88]
0x1800238e6  jb      short loc_180023910
0x1800238e8  test    esi, esi
0x1800238ea  js      short loc_18002390B
0x1800238ec  cmp     r12d, edx
0x1800238ef  ja      short loc_18002390B
0x1800238f1  jnz     short loc_180023910
0x1800238f3  cmp     byte ptr [r14+2Ch], 0
0x1800238f8  jnz     short loc_180023910
0x1800238fa  movsxd  rax, esi
0x1800238fd  lea     rcx, [rax+rax*2]
0x180023901  add     rcx, rcx
0x180023904  cmp     byte ptr [rbx+rcx*8+2Ch], 1
0x180023909  jnz     short loc_180023910
0x18002390b  mov     esi, edi
0x18002390d  mov     r12d, edx
0x180023910  inc     edi
0x180023912  cmp     edi, [rbp+57h+var_90]
0x180023915  jb      loc_180023876
0x18002391b  mov     r13, [rbp+57h+var_70]
0x18002391f  test    esi, esi
0x180023921  js      short loc_180023951
0x180023923  movsxd  rax, esi
0x180023926  mov     edi, 1
0x18002392b  lea     rdx, [rax+rax*2]
0x18002392f  add     rdx, rdx
0x180023932  movups  xmm0, xmmword ptr [rbx+rdx*8]
0x180023936  movups  xmmword ptr [r13+0], xmm0
0x18002393b  movups  xmm1, xmmword ptr [rbx+rdx*8+10h]
0x180023940  movups  xmmword ptr [r13+10h], xmm1
0x180023945  movups  xmm0, xmmword ptr [rbx+rdx*8+20h]
0x18002394a  movups  xmmword ptr [r13+20h], xmm0
0x18002394f  jmp     short loc_180023954
0x180023951  mov     edi, [rbp+57h+var_8C]
0x180023954  test    rbx, rbx
0x180023957  jz      short loc_180023961
0x180023959  mov     rcx, rbx; void *
0x18002395c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023961  mov     eax, edi
0x180023963  mov     rcx, [rbp+57h+var_28]
0x180023967  xor     rcx, rsp; StackCookie
0x18002396a  call    __security_check_cookie
0x18002396f  lea     r11, [rsp+0B0h+var_20]
0x180023977  mov     rbx, [r11+30h]
0x18002397b  mov     rsi, [r11+38h]
0x18002397f  mov     rsp, r11
0x180023982  pop     r14
0x180023984  pop     r13
0x180023986  pop     r12
0x180023988  pop     rdi
0x180023989  pop     rbp
0x18002398a  retn
```
