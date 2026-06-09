# ProcessTokenIntoAddress(ushort const *,ushort const *,_PARSE_PROXY_STRING_TOKEN_TYPE,sockaddr_storage *,long *)

- ea: `0x18000f5f8`
- end: `0x18000f700`
- name: `?ProcessTokenIntoAddress@@YAXPEBG0W4_PARSE_PROXY_STRING_TOKEN_TYPE@@PEAUsockaddr_storage@@PEAJ@Z`
- size: `264`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000f3e0`
- `0x18000f4c4`

## callees

- `0x18000c998`
- `0x18000f5f8`
- `0x180010450`
- `0x180012db0`

## import_xrefs

- `ntdll!RtlIpv6StringToAddressW` at `0x18000f6ca`
- `ntdll!RtlIpv6StringToAddressW` at `0x18000f6ca`
- `ntdll!RtlIpv4StringToAddressW` at `0x18000f6ad`
- `ntdll!RtlIpv4StringToAddressW` at `0x18000f6ad`

## pseudocode

```c
void __fastcall ProcessTokenIntoAddress(const unsigned __int16 *a1, __int64 a2, int a3, __int64 a4, int *a5)
{
  unsigned __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r11
  LPCWSTR Terminator[2]; // [rsp+20h] [rbp-248h] BYREF
  WCHAR S[264]; // [rsp+30h] [rbp-238h] BYREF

  v6 = (a2 - (__int64)a1 + 2) >> 1;
  if ( v6 <= 0x101 )
  {
    v7 = StringCchCopyW(S, v6, a1);
    if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147024774 )
    {
      if ( a3 == 1 || a3 == 2 )
      {
        Terminator[0] = 0;
        if ( a3 == 1 )
        {
          *(_WORD *)v9 = 2;
          v7 = RtlIpv4StringToAddressW(S, 1u, Terminator, (struct in_addr *)(v9 + 4));
        }
        else
        {
          *(_WORD *)v9 = 23;
          v7 = RtlIpv6StringToAddressW(S, Terminator, (struct in6_addr *)(v9 + 8));
        }
      }
      else
      {
        if ( a3 != 3 )
        {
          *a5 = -2147467259;
          return;
        }
        v7 = ExecuteDNSQuery(S, 0x80000000LL, v8, (struct sockaddr_storage *)v9);
      }
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
    }
    *a5 = v7;
  }
}

```

## disassembly

```asm
0x18000f5f8  push    rbx
0x18000f5fa  push    rsi
0x18000f5fb  push    rdi
0x18000f5fc  sub     rsp, 250h
0x18000f603  mov     rax, cs:__security_cookie
0x18000f60a  xor     rax, rsp
0x18000f60d  mov     [rsp+268h+var_28], rax
0x18000f615  mov     rbx, [rsp+268h+arg_20]
0x18000f61d  sub     rdx, rcx
0x18000f620  mov     esi, 2
0x18000f625  mov     r11, r9
0x18000f628  add     rdx, rsi
0x18000f62b  mov     edi, r8d
0x18000f62e  sar     rdx, 1; unsigned __int64
0x18000f631  cmp     rdx, 101h
0x18000f638  ja      loc_18000F6E4
0x18000f63e  mov     r8, rcx; unsigned __int16 *
0x18000f641  lea     rcx, [rsp+268h+S]; unsigned __int16 *
0x18000f646  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f64b  mov     edx, 80000000h; unsigned __int16
0x18000f650  lea     ecx, [rax+rdx]
0x18000f653  test    edx, ecx
0x18000f655  jnz     short loc_18000F662
0x18000f657  cmp     eax, 8007007Ah
0x18000f65c  jnz     loc_18000F6E2
0x18000f662  mov     ecx, edi
0x18000f664  sub     ecx, 1
0x18000f667  jz      short loc_18000F68A
0x18000f669  sub     ecx, 1
0x18000f66c  jz      short loc_18000F68A
0x18000f66e  cmp     ecx, 1
0x18000f671  jz      short loc_18000F67B
0x18000f673  mov     dword ptr [rbx], 80004005h
0x18000f679  jmp     short loc_18000F6E4
0x18000f67b  mov     r9, r11; struct sockaddr_storage *
0x18000f67e  lea     rcx, [rsp+268h+S]; pNodeName
0x18000f683  call    ?ExecuteDNSQuery@@YAJPEBGGKPEAUsockaddr_storage@@@Z; ExecuteDNSQuery(ushort const *,ushort,ulong,sockaddr_storage *)
0x18000f688  jmp     short loc_18000F6D6
0x18000f68a  mov     [rsp+268h+Terminator], 0
0x18000f693  lea     rcx, [rsp+268h+S]; S
0x18000f698  cmp     edi, 1
0x18000f69b  jnz     short loc_18000F6BB
0x18000f69d  lea     r9, [r11+4]; Addr
0x18000f6a1  mov     [r11], si
0x18000f6a5  lea     r8, [rsp+268h+Terminator]; Terminator
0x18000f6aa  mov     dl, dil; Strict
0x18000f6ad  call    cs:__imp_RtlIpv4StringToAddressW
0x18000f6b4  nop     dword ptr [rax+rax+00h]
0x18000f6b9  jmp     short loc_18000F6D6
0x18000f6bb  lea     r8, [r11+8]; Addr
0x18000f6bf  mov     word ptr [r11], 17h
0x18000f6c5  lea     rdx, [rsp+268h+Terminator]; Terminator
0x18000f6ca  call    cs:__imp_RtlIpv6StringToAddressW
0x18000f6d1  nop     dword ptr [rax+rax+00h]
0x18000f6d6  test    eax, eax
0x18000f6d8  jle     short loc_18000F6E2
0x18000f6da  movzx   eax, ax
0x18000f6dd  or      eax, 80070000h
0x18000f6e2  mov     [rbx], eax
0x18000f6e4  mov     rcx, [rsp+268h+var_28]
0x18000f6ec  xor     rcx, rsp; StackCookie
0x18000f6ef  call    __security_check_cookie
0x18000f6f4  add     rsp, 250h
0x18000f6fb  pop     rdi
0x18000f6fc  pop     rsi
0x18000f6fd  pop     rbx
0x18000f6fe  retn
```
