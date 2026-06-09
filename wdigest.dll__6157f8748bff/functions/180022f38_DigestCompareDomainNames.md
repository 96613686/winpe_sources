# DigestCompareDomainNames

- ea: `0x180022f38`
- end: `0x180022ff6`
- name: `DigestCompareDomainNames`
- size: `190`
- prototype: `__int64 __fastcall(PUNICODE_STRING DomainName1, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bf40`
- `0x18001d5e8`

## callees

- `0x180009770`
- `0x180022a60`
- `0x180022f38`

## import_xrefs

- `ntdll!RtlEqualDomainName` at `0x180022f98`
- `ntdll!RtlEqualDomainName` at `0x180022f98`
- `DNSAPI!DnsNameCompare_W` at `0x180022fad`
- `DNSAPI!DnsNameCompare_W` at `0x180022fad`

## pseudocode

```c
_BOOL8 __fastcall DigestCompareDomainNames(
        PUNICODE_STRING DomainName1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3)
{
  char v5; // bl
  WCHAR *v6; // rdi
  struct _UNICODE_STRING *v8; // rdx
  BOOLEAN v9; // al
  unsigned __int8 v11[8]; // [rsp+20h] [rbp-28h] BYREF
  PCWSTR pName2; // [rsp+28h] [rbp-20h] BYREF
  PCWSTR pName1; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int8 v14; // [rsp+98h] [rbp+50h] BYREF

  pName1 = 0;
  v5 = 0;
  v6 = 0;
  v14 = 0;
  pName2 = 0;
  v11[0] = 0;
  if ( (int)DigestNullTerminateUnicodeString(DomainName1, (unsigned __int16 **)&pName1, &v14) >= 0 )
  {
    if ( (int)DigestNullTerminateUnicodeString(a2, (unsigned __int16 **)&pName2, v11) < 0 )
    {
      v6 = (WCHAR *)pName2;
    }
    else
    {
      if ( a3 )
        v8 = a3;
      else
        v8 = a2;
      v9 = RtlEqualDomainName(DomainName1, v8);
      v6 = (WCHAR *)pName2;
      if ( v9 || DnsNameCompare_W(pName1, pName2) )
        v5 = 1;
    }
  }
  if ( v14 )
    DigestFreeMemory((HLOCAL)pName1);
  if ( v11[0] )
    DigestFreeMemory(v6);
  return v5 != 0;
}

```

## disassembly

```asm
0x180022f38  push    rbp
0x180022f3a  push    rbx
0x180022f3b  push    rdi
0x180022f3c  push    r12
0x180022f3e  push    r14
0x180022f40  push    r15
0x180022f42  mov     rbp, rsp
0x180022f45  sub     rsp, 48h
0x180022f49  mov     r14, r8
0x180022f4c  mov     [rbp+pName1], 0
0x180022f54  mov     r12, rdx
0x180022f57  lea     r8, [rbp+arg_18]; unsigned __int8 *
0x180022f5b  xor     bl, bl
0x180022f5d  lea     rdx, [rbp+pName1]; unsigned __int16 **
0x180022f61  xor     edi, edi
0x180022f63  mov     [rbp+arg_18], bl
0x180022f66  mov     [rbp+pName2], rdi
0x180022f6a  mov     r15, rcx
0x180022f6d  mov     [rbp+var_28], bl
0x180022f70  call    ?DigestNullTerminateUnicodeString@@YAJPEAU_UNICODE_STRING@@PEAPEAGPEAE@Z; DigestNullTerminateUnicodeString(_UNICODE_STRING *,ushort * *,uchar *)
0x180022f75  test    eax, eax
0x180022f77  js      short loc_180022FC4
0x180022f79  lea     r8, [rbp+var_28]; unsigned __int8 *
0x180022f7d  mov     rcx, r12; struct _UNICODE_STRING *
0x180022f80  lea     rdx, [rbp+pName2]; unsigned __int16 **
0x180022f84  call    ?DigestNullTerminateUnicodeString@@YAJPEAU_UNICODE_STRING@@PEAPEAGPEAE@Z; DigestNullTerminateUnicodeString(_UNICODE_STRING *,ushort * *,uchar *)
0x180022f89  test    eax, eax
0x180022f8b  js      short loc_180022FC0
0x180022f8d  mov     rcx, r15; DomainName1
0x180022f90  test    r14, r14
0x180022f93  jnz     short loc_180022FBB
0x180022f95  mov     rdx, r12; DomainName2
0x180022f98  call    cs:__imp_RtlEqualDomainName
0x180022f9e  mov     rdi, [rbp+pName2]
0x180022fa2  test    al, al
0x180022fa4  jnz     short loc_180022FB7
0x180022fa6  mov     rcx, [rbp+pName1]; pName1
0x180022faa  mov     rdx, rdi; pName2
0x180022fad  call    cs:__imp_DnsNameCompare_W
0x180022fb3  test    eax, eax
0x180022fb5  jz      short loc_180022FC4
0x180022fb7  mov     bl, 1
0x180022fb9  jmp     short loc_180022FC4
0x180022fbb  mov     rdx, r14
0x180022fbe  jmp     short loc_180022F98
0x180022fc0  mov     rdi, [rbp+pName2]
0x180022fc4  cmp     [rbp+arg_18], 0
0x180022fc8  jz      short loc_180022FD3
0x180022fca  mov     rcx, [rbp+pName1]; hMem
0x180022fce  call    DigestFreeMemory
0x180022fd3  cmp     [rbp+var_28], 0
0x180022fd7  jz      short loc_180022FE1
0x180022fd9  mov     rcx, rdi; hMem
0x180022fdc  call    DigestFreeMemory
0x180022fe1  xor     eax, eax
0x180022fe3  test    bl, bl
0x180022fe5  setnz   al
0x180022fe8  add     rsp, 48h
0x180022fec  pop     r15
0x180022fee  pop     r14
0x180022ff0  pop     r12
0x180022ff2  pop     rdi
0x180022ff3  pop     rbx
0x180022ff4  pop     rbp
0x180022ff5  retn
```
