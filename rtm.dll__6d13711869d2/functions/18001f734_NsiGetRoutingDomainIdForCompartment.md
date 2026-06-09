# NsiGetRoutingDomainIdForCompartment

- ea: `0x18001f734`
- end: `0x18001f7e0`
- name: `NsiGetRoutingDomainIdForCompartment`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009d14`

## callees

- `0x18001f734`
- `0x18001f980`

## import_xrefs

- `NSI!NsiGetParameter` at `0x18001f7b3`
- `NSI!NsiGetParameter` at `0x18001f7b3`

## pseudocode

```c
__int64 __fastcall NsiGetRoutingDomainIdForCompartment(int a1, GUID *a2)
{
  __int64 result; // rax
  int v4; // [rsp+50h] [rbp-28h] BYREF
  GUID v5; // [rsp+58h] [rbp-20h] BYREF

  v4 = a1;
  v5 = GUID_NULL;
  if ( !a2 || !a1 )
    return 87;
  if ( a1 == 1 )
  {
    result = 0;
    *a2 = GUID_NULL;
  }
  else
  {
    result = NsiGetParameter(1, &NPI_MS_NDIS_MODULEID, 7, &v4, 4, 0, &v5, 16, 1080);
    if ( !(_DWORD)result )
      *a2 = v5;
  }
  return result;
}

```

## disassembly

```asm
0x18001f734  push    rbx
0x18001f736  sub     rsp, 70h
0x18001f73a  mov     rax, cs:__security_cookie
0x18001f741  xor     rax, rsp
0x18001f744  mov     [rsp+78h+var_10], rax
0x18001f749  mov     [rsp+78h+var_28], ecx
0x18001f74d  mov     rbx, rdx
0x18001f750  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001f757  movdqu  [rsp+78h+var_20], xmm0
0x18001f75d  test    rdx, rdx
0x18001f760  jz      short loc_18001F7C8
0x18001f762  test    ecx, ecx
0x18001f764  jz      short loc_18001F7C8
0x18001f766  cmp     ecx, 1
0x18001f769  jnz     short loc_18001F773
0x18001f76b  xor     eax, eax
0x18001f76d  movdqu  xmmword ptr [rdx], xmm0
0x18001f771  jmp     short loc_18001F7CD
0x18001f773  mov     [rsp+78h+var_38], 438h
0x18001f77b  lea     rax, [rsp+78h+var_20]
0x18001f780  mov     [rsp+78h+var_40], 10h
0x18001f788  lea     r9, [rsp+78h+var_28]
0x18001f78d  mov     [rsp+78h+var_48], rax
0x18001f792  lea     rdx, NPI_MS_NDIS_MODULEID
0x18001f799  mov     r8d, 7
0x18001f79f  mov     [rsp+78h+var_50], 0
0x18001f7a7  mov     [rsp+78h+var_58], 4
0x18001f7af  lea     ecx, [r8-6]
0x18001f7b3  call    cs:__imp_NsiGetParameter
0x18001f7b9  test    eax, eax
0x18001f7bb  jnz     short loc_18001F7CD
0x18001f7bd  movups  xmm0, [rsp+78h+var_20]
0x18001f7c2  movdqu  xmmword ptr [rbx], xmm0
0x18001f7c6  jmp     short loc_18001F7CD
0x18001f7c8  mov     eax, 57h ; 'W'
0x18001f7cd  mov     rcx, [rsp+78h+var_10]
0x18001f7d2  xor     rcx, rsp; StackCookie
0x18001f7d5  call    __security_check_cookie
0x18001f7da  add     rsp, 70h
0x18001f7de  pop     rbx
0x18001f7df  retn
```
