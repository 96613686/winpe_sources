# NetrUseDel

- ea: `0x1800012a0`
- end: `0x1800015b8`
- name: `NetrUseDel`
- size: `792`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting`

## callees

- `0x1800012a0`
- `0x180002c20`
- `0x180009010`
- `0x180009090`
- `0x180009110`
- `0x18000a3a0`
- `0x18000a830`
- `0x18000e518`
- `0x18001fbd0`
- `0x18002bce8`
- `0x18002bd5c`
- `0x1800314a8`
- `0x180031538`
- `0x180031968`
- `0x1800319cc`
- `0x180031b70`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800013a9`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800013a9`
- `ntdll!NtClose` at `0x180001485`
- `ntdll!NtClose` at `0x180001485`
- `ntdll!RtlReleaseResource` at `0x180001435`
- `ntdll!RtlReleaseResource` at `0x180001459`
- `ntdll!RtlReleaseResource` at `0x1800014b6`
- `ntdll!RtlReleaseResource` at `0x180001435`
- `ntdll!RtlReleaseResource` at `0x180001459`
- `ntdll!RtlReleaseResource` at `0x1800014b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000154b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000154b`
- `netutils!NetpwPathCanonicalize` at `0x180001353`
- `netutils!NetpwPathCanonicalize` at `0x180001353`

## pseudocode

```c
__int64 __fastcall NetrUseDel(__int64 a1, __int64 a2, int a3)
{
  DWORD v3; // r14d
  int v4; // edi
  bool v5; // r15
  __int64 result; // rax
  __int64 *v7; // rdx
  unsigned int Use; // ebx
  _QWORD *v9; // rbx
  DWORD v10; // esi
  __int64 v11; // r8
  wchar_t *v12; // r8
  unsigned int v13; // r14d
  char v14; // bl
  int v15; // [rsp+20h] [rbp-E0h]
  unsigned int v16; // [rsp+30h] [rbp-D0h] BYREF
  struct _LUID SourceLuid; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszSrc[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[264]; // [rsp+270h] [rbp+170h] BYREF

  v3 = (unsigned __int16)a3;
  v4 = a3 & 0x10000;
  SourceLuid = 0;
  v16 = 0;
  v5 = (a3 & 0x10000) != 0;
  hMem = 0;
  v21 = 0;
  Handle = 0;
  v19 = 0;
  if ( (_WORD)a3 && (unsigned int)(unsigned __int16)a3 - 1 >= 2 )
    return 87;
  if ( (unsigned int)NetpwPathCanonicalize(a2, pszSrc, 522, 0, &v19, 0) )
    return 2250;
  if ( v4 )
  {
    result = WsImpersonateAndCheckPrivilege(0x1Cu);
    if ( (_DWORD)result )
      return result;
    SourceLuid = (struct _LUID)-1LL;
  }
  else
  {
    result = WsImpersonateAndGetLogonId(&SourceLuid);
    if ( (_DWORD)result )
      return result;
  }
  if ( !RtlAcquireResourceExclusive(&Resource, 1u) )
    return 2140;
  if ( (unsigned int)WsGetUserEntry((__int64)&::Use, &SourceLuid, &v16, 0, 0) )
    v7 = 0;
  else
    v7 = *(__int64 **)(::Use + 24LL * v16);
  Use = WsFindUse(&SourceLuid, v7, pszSrc, &Handle, &hMem, &v21);
  if ( Use )
  {
    RtlReleaseResource(&Resource);
    return Use;
  }
  v9 = hMem;
  if ( !hMem )
  {
    RtlReleaseResource(&Resource);
    Use = WsDeleteConnectionEx(&SourceLuid, Handle, v3, 1);
    if ( Use )
      NtClose(Handle);
    return Use;
  }
  v10 = 2;
  if ( *((_QWORD *)hMem + 2) && *((_DWORD *)hMem + 6) > 2u && (unsigned int)WsRedirectionPaused() )
  {
    RtlReleaseResource(&Resource);
    return 72;
  }
  else
  {
    if ( v4 )
    {
      v11 = v9[1];
      if ( v11 )
        v12 = (wchar_t *)(v11 + 8);
      else
        v12 = pszSrc;
      StringCbCopyW(pszDest, 0x20Au, v12);
    }
    LOBYTE(v15) = v5;
    v13 = WsDeleteUse(&SourceLuid, v3, v9, v16, v15);
    if ( !v13 && v4 && !WsImpersonateClient2(0, 0) )
    {
      hMem = 0;
      v14 = 0;
      if ( !(unsigned int)WsQueryGlobalMappingFromRegistry(pszSrc, &hMem) )
      {
        v10 = *((_DWORD *)hMem + 5);
        LocalFree(hMem);
        v14 = 1;
      }
      WsDeleteGlobalMappingFromRegistry(pszSrc);
      WsRevertToSelf2(0, 0);
      if ( v14 && !(unsigned __int8)WsGlobalMappingsToSameTargetExist(pszDest) )
        WsDeleteNetUseCredential((__int64)pszDest, v10);
    }
    return v13;
  }
}

```

## disassembly

```asm
0x1800012a0  mov     [rsp-8+arg_0], rbx
0x1800012a5  push    rbp
0x1800012a6  push    rsi
0x1800012a7  push    rdi
0x1800012a8  push    r14
0x1800012aa  push    r15
0x1800012ac  lea     rbp, [rsp-390h]
0x1800012b4  sub     rsp, 490h
0x1800012bb  mov     rax, cs:__security_cookie
0x1800012c2  xor     rax, rsp
0x1800012c5  mov     [rbp+3B0h+var_30], rax
0x1800012cc  movzx   r14d, r8w
0x1800012d0  mov     edi, r8d
0x1800012d3  and     edi, 10000h
0x1800012d9  mov     qword ptr [rsp+4B0h+SourceLuid.LowPart], 0
0x1800012e2  mov     r10, rdx
0x1800012e5  mov     [rsp+4B0h+var_480], 0
0x1800012ed  setnz   r15b
0x1800012f1  mov     [rsp+4B0h+hMem], 0
0x1800012fa  mov     [rsp+4B0h+var_458], 0
0x180001303  mov     eax, r14d
0x180001306  mov     [rsp+4B0h+Handle], 0
0x18000130f  mov     [rsp+4B0h+var_468], 0
0x180001317  test    r14d, r14d
0x18000131a  jz      short loc_180001330
0x18000131c  sub     eax, 1
0x18000131f  jz      short loc_180001330
0x180001321  cmp     eax, 1
0x180001324  jz      short loc_180001330
0x180001326  mov     eax, 57h ; 'W'
0x18000132b  jmp     loc_180001591
0x180001330  lea     rax, [rsp+4B0h+var_468]
0x180001335  mov     dword ptr [rsp+4B0h+var_488], 0
0x18000133d  xor     r9d, r9d
0x180001340  mov     [rsp+4B0h+var_490], rax
0x180001345  mov     r8d, 20Ah
0x18000134b  lea     rdx, [rsp+4B0h+pszSrc]
0x180001350  mov     rcx, r10
0x180001353  call    cs:__imp_NetpwPathCanonicalize
0x18000135a  nop     dword ptr [rax+rax+00h]
0x18000135f  test    eax, eax
0x180001361  jz      short loc_18000136D
0x180001363  mov     eax, 8CAh
0x180001368  jmp     loc_180001591
0x18000136d  test    edi, edi
0x18000136f  jz      short loc_18000138E
0x180001371  mov     ecx, 1Ch
0x180001376  call    WsImpersonateAndCheckPrivilege
0x18000137b  test    eax, eax
0x18000137d  jnz     loc_180001591
0x180001383  mov     qword ptr [rsp+4B0h+SourceLuid.LowPart], 0FFFFFFFFFFFFFFFFh
0x18000138c  jmp     short loc_1800013A0
0x18000138e  lea     rcx, [rsp+4B0h+SourceLuid]; DestinationLuid
0x180001393  call    WsImpersonateAndGetLogonId
0x180001398  test    eax, eax
0x18000139a  jnz     loc_180001591
0x1800013a0  mov     dl, 1; Wait
0x1800013a2  lea     rcx, Resource; Resource
0x1800013a9  call    cs:__imp_RtlAcquireResourceExclusive
0x1800013b0  nop     dword ptr [rax+rax+00h]
0x1800013b5  test    al, al
0x1800013b7  jnz     short loc_1800013C3
0x1800013b9  mov     eax, 85Ch
0x1800013be  jmp     loc_180001591
0x1800013c3  xor     r9d, r9d
0x1800013c6  mov     [rsp+4B0h+var_490], 0
0x1800013cf  lea     r8, [rsp+4B0h+var_480]
0x1800013d4  lea     rdx, [rsp+4B0h+SourceLuid]
0x1800013d9  lea     rcx, Use
0x1800013e0  call    WsGetUserEntry
0x1800013e5  test    eax, eax
0x1800013e7  jnz     short loc_1800013FE
0x1800013e9  mov     eax, [rsp+4B0h+var_480]
0x1800013ed  lea     rcx, [rax+rax*2]
0x1800013f1  mov     rax, cs:Use
0x1800013f8  mov     rdx, [rax+rcx*8]
0x1800013fc  jmp     short loc_180001400
0x1800013fe  xor     edx, edx
0x180001400  lea     rax, [rsp+4B0h+var_458]
0x180001405  mov     [rsp+4B0h+var_488], rax; __int64
0x18000140a  lea     r9, [rsp+4B0h+Handle]
0x18000140f  lea     rax, [rsp+4B0h+hMem]
0x180001414  lea     r8, [rsp+4B0h+pszSrc]
0x180001419  mov     [rsp+4B0h+var_490], rax; __int64
0x18000141e  lea     rcx, [rsp+4B0h+SourceLuid]; SourceLuid
0x180001423  call    WsFindUse
0x180001428  mov     ebx, eax
0x18000142a  test    eax, eax
0x18000142c  jz      short loc_180001448
0x18000142e  lea     rcx, Resource; Resource
0x180001435  call    cs:__imp_RtlReleaseResource
0x18000143c  nop     dword ptr [rax+rax+00h]
0x180001441  mov     eax, ebx
0x180001443  jmp     loc_180001591
0x180001448  mov     rbx, [rsp+4B0h+hMem]
0x18000144d  test    rbx, rbx
0x180001450  jnz     short loc_180001493
0x180001452  lea     rcx, Resource; Resource
0x180001459  call    cs:__imp_RtlReleaseResource
0x180001460  nop     dword ptr [rax+rax+00h]
0x180001465  mov     rdx, [rsp+4B0h+Handle]; Handle
0x18000146a  lea     rcx, [rsp+4B0h+SourceLuid]; SourceLuid
0x18000146f  mov     r9b, 1
0x180001472  mov     r8d, r14d
0x180001475  call    WsDeleteConnectionEx
0x18000147a  mov     ebx, eax
0x18000147c  test    eax, eax
0x18000147e  jz      short loc_180001441
0x180001480  mov     rcx, [rsp+4B0h+Handle]; Handle
0x180001485  call    cs:__imp_NtClose
0x18000148c  nop     dword ptr [rax+rax+00h]
0x180001491  jmp     short loc_180001441
0x180001493  mov     rcx, [rbx+10h]
0x180001497  mov     esi, 2
0x18000149c  test    rcx, rcx
0x18000149f  jz      short loc_1800014CA
0x1800014a1  cmp     [rbx+18h], esi
0x1800014a4  jbe     short loc_1800014CA
0x1800014a6  call    WsRedirectionPaused
0x1800014ab  test    eax, eax
0x1800014ad  jz      short loc_1800014CA
0x1800014af  lea     rcx, Resource; Resource
0x1800014b6  call    cs:__imp_RtlReleaseResource
0x1800014bd  nop     dword ptr [rax+rax+00h]
0x1800014c2  lea     eax, [rsi+46h]
0x1800014c5  jmp     loc_180001591
0x1800014ca  test    edi, edi
0x1800014cc  jz      short loc_1800014F3
0x1800014ce  mov     r8, [rbx+8]
0x1800014d2  lea     rcx, [rbp+3B0h+pszDest]; pszDest
0x1800014d9  mov     edx, 20Ah; cbDest
0x1800014de  test    r8, r8
0x1800014e1  jz      short loc_1800014E9
0x1800014e3  add     r8, 8
0x1800014e7  jmp     short loc_1800014EE
0x1800014e9  lea     r8, [rsp+4B0h+pszSrc]; pszSrc
0x1800014ee  call    StringCbCopyW
0x1800014f3  mov     r9d, [rsp+4B0h+var_480]
0x1800014f8  lea     rcx, [rsp+4B0h+SourceLuid]
0x1800014fd  mov     r8, rbx
0x180001500  mov     byte ptr [rsp+4B0h+var_490], r15b
0x180001505  mov     edx, r14d
0x180001508  call    WsDeleteUse
0x18000150d  mov     r14d, eax
0x180001510  test    eax, eax
0x180001512  jnz     short loc_18000158E
0x180001514  test    edi, edi
0x180001516  jz      short loc_18000158E
0x180001518  xor     edx, edx
0x18000151a  xor     ecx, ecx
0x18000151c  call    WsImpersonateClient2
0x180001521  test    eax, eax
0x180001523  jnz     short loc_18000158E
0x180001525  lea     rdx, [rsp+4B0h+hMem]
0x18000152a  mov     [rsp+4B0h+hMem], 0
0x180001533  lea     rcx, [rsp+4B0h+pszSrc]; SourceString
0x180001538  xor     bl, bl
0x18000153a  call    WsQueryGlobalMappingFromRegistry
0x18000153f  test    eax, eax
0x180001541  jnz     short loc_180001559
0x180001543  mov     rcx, [rsp+4B0h+hMem]; hMem
0x180001548  mov     esi, [rcx+14h]
0x18000154b  call    cs:__imp_LocalFree
0x180001552  nop     dword ptr [rax+rax+00h]
0x180001557  mov     bl, 1
0x180001559  lea     rcx, [rsp+4B0h+pszSrc]; SourceString
0x18000155e  call    WsDeleteGlobalMappingFromRegistry
0x180001563  xor     edx, edx
0x180001565  xor     ecx, ecx
0x180001567  call    WsRevertToSelf2
0x18000156c  test    bl, bl
0x18000156e  jz      short loc_18000158E
0x180001570  lea     rcx, [rbp+3B0h+pszDest]
0x180001577  call    WsGlobalMappingsToSameTargetExist
0x18000157c  test    al, al
0x18000157e  jnz     short loc_18000158E
0x180001580  mov     edx, esi
0x180001582  lea     rcx, [rbp+3B0h+pszDest]
0x180001589  call    WsDeleteNetUseCredential
0x18000158e  mov     eax, r14d
0x180001591  mov     rcx, [rbp+3B0h+var_30]
0x180001598  xor     rcx, rsp; StackCookie
0x18000159b  call    __security_check_cookie
0x1800015a0  mov     rbx, [rsp+4B0h+arg_0]
0x1800015a8  add     rsp, 490h
0x1800015af  pop     r15
0x1800015b1  pop     r14
0x1800015b3  pop     rdi
0x1800015b4  pop     rsi
0x1800015b5  pop     rbp
0x1800015b6  retn
```
