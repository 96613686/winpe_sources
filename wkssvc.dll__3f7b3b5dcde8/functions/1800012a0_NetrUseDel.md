# NetrUseDel

- ea: `0x1800012a0`
- end: `0x18000158d`
- name: `NetrUseDel`
- size: `749`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting`

## callees

- `0x1800012a0`
- `0x180002a60`
- `0x180008950`
- `0x1800089d0`
- `0x180008a4c`
- `0x180009b80`
- `0x180009f80`
- `0x18000d8ac`
- `0x18001e420`
- `0x180029818`
- `0x18002988c`
- `0x18002e944`
- `0x18002e9c4`
- `0x18002eda0`
- `0x18002edfc`
- `0x18002ef7c`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800013a3`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800013a3`
- `ntdll!NtClose` at `0x18000146d`
- `ntdll!NtClose` at `0x18000146d`
- `ntdll!RtlReleaseResource` at `0x180001429`
- `ntdll!RtlReleaseResource` at `0x180001447`
- `ntdll!RtlReleaseResource` at `0x180001498`
- `ntdll!RtlReleaseResource` at `0x180001429`
- `ntdll!RtlReleaseResource` at `0x180001447`
- `ntdll!RtlReleaseResource` at `0x180001498`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001527`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001527`
- `netutils!NetpwPathCanonicalize` at `0x180001353`
- `netutils!NetpwPathCanonicalize` at `0x180001353`

## pseudocode

```c
__int64 __fastcall NetrUseDel(__int64 a1, __int64 a2, int a3)
{
  unsigned int v3; // r14d
  int v4; // edi
  bool v5; // r15
  __int64 result; // rax
  __int64 *v7; // rdx
  unsigned int Use; // ebx
  _QWORD *v9; // rbx
  unsigned int v10; // esi
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
    result = WsImpersonateAndCheckPrivilege(28);
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
  if ( (unsigned int)WsGetUserEntry(&::Use, &SourceLuid, &v16, 0, 0) )
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
    Use = WsDeleteConnectionEx(&SourceLuid, Handle);
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
    if ( !v13 && v4 && !(unsigned int)WsImpersonateClient2(0, 0) )
    {
      hMem = 0;
      v14 = 0;
      if ( !(unsigned int)WsQueryGlobalMappingFromRegistry(pszSrc) )
      {
        v10 = *((_DWORD *)hMem + 5);
        LocalFree(hMem);
        v14 = 1;
      }
      WsDeleteGlobalMappingFromRegistry(pszSrc);
      WsRevertToSelf2(0, 0);
      if ( v14 && !(unsigned __int8)WsGlobalMappingsToSameTargetExist(pszDest) )
        WsDeleteNetUseCredential(pszDest, v10);
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
0x18000132b  jmp     loc_180001567
0x180001330  lea     rax, [rsp+4B0h+var_468]
0x180001335  mov     dword ptr [rsp+4B0h+var_488], 0
0x18000133d  xor     r9d, r9d
0x180001340  mov     [rsp+4B0h+var_490], rax
0x180001345  mov     r8d, 20Ah
0x18000134b  lea     rdx, [rsp+4B0h+pszSrc]
0x180001350  mov     rcx, r10
0x180001353  call    cs:__imp_NetpwPathCanonicalize
0x180001359  test    eax, eax
0x18000135b  jz      short loc_180001367
0x18000135d  mov     eax, 8CAh
0x180001362  jmp     loc_180001567
0x180001367  test    edi, edi
0x180001369  jz      short loc_180001388
0x18000136b  mov     ecx, 1Ch
0x180001370  call    WsImpersonateAndCheckPrivilege
0x180001375  test    eax, eax
0x180001377  jnz     loc_180001567
0x18000137d  mov     qword ptr [rsp+4B0h+SourceLuid.LowPart], 0FFFFFFFFFFFFFFFFh
0x180001386  jmp     short loc_18000139A
0x180001388  lea     rcx, [rsp+4B0h+SourceLuid]; DestinationLuid
0x18000138d  call    WsImpersonateAndGetLogonId
0x180001392  test    eax, eax
0x180001394  jnz     loc_180001567
0x18000139a  mov     dl, 1; Wait
0x18000139c  lea     rcx, Resource; Resource
0x1800013a3  call    cs:__imp_RtlAcquireResourceExclusive
0x1800013a9  test    al, al
0x1800013ab  jnz     short loc_1800013B7
0x1800013ad  mov     eax, 85Ch
0x1800013b2  jmp     loc_180001567
0x1800013b7  xor     r9d, r9d
0x1800013ba  mov     [rsp+4B0h+var_490], 0
0x1800013c3  lea     r8, [rsp+4B0h+var_480]
0x1800013c8  lea     rdx, [rsp+4B0h+SourceLuid]
0x1800013cd  lea     rcx, Use
0x1800013d4  call    WsGetUserEntry
0x1800013d9  test    eax, eax
0x1800013db  jnz     short loc_1800013F2
0x1800013dd  mov     eax, [rsp+4B0h+var_480]
0x1800013e1  lea     rcx, [rax+rax*2]
0x1800013e5  mov     rax, cs:Use
0x1800013ec  mov     rdx, [rax+rcx*8]
0x1800013f0  jmp     short loc_1800013F4
0x1800013f2  xor     edx, edx
0x1800013f4  lea     rax, [rsp+4B0h+var_458]
0x1800013f9  mov     [rsp+4B0h+var_488], rax; __int64
0x1800013fe  lea     r9, [rsp+4B0h+Handle]
0x180001403  lea     rax, [rsp+4B0h+hMem]
0x180001408  lea     r8, [rsp+4B0h+pszSrc]
0x18000140d  mov     [rsp+4B0h+var_490], rax; __int64
0x180001412  lea     rcx, [rsp+4B0h+SourceLuid]; SourceLuid
0x180001417  call    WsFindUse
0x18000141c  mov     ebx, eax
0x18000141e  test    eax, eax
0x180001420  jz      short loc_180001436
0x180001422  lea     rcx, Resource; Resource
0x180001429  call    cs:__imp_RtlReleaseResource
0x18000142f  mov     eax, ebx
0x180001431  jmp     loc_180001567
0x180001436  mov     rbx, [rsp+4B0h+hMem]
0x18000143b  test    rbx, rbx
0x18000143e  jnz     short loc_180001475
0x180001440  lea     rcx, Resource; Resource
0x180001447  call    cs:__imp_RtlReleaseResource
0x18000144d  mov     rdx, [rsp+4B0h+Handle]; Handle
0x180001452  lea     rcx, [rsp+4B0h+SourceLuid]; SourceLuid
0x180001457  mov     r9b, 1
0x18000145a  mov     r8d, r14d
0x18000145d  call    WsDeleteConnectionEx
0x180001462  mov     ebx, eax
0x180001464  test    eax, eax
0x180001466  jz      short loc_18000142F
0x180001468  mov     rcx, [rsp+4B0h+Handle]; Handle
0x18000146d  call    cs:__imp_NtClose
0x180001473  jmp     short loc_18000142F
0x180001475  mov     rcx, [rbx+10h]
0x180001479  mov     esi, 2
0x18000147e  test    rcx, rcx
0x180001481  jz      short loc_1800014A6
0x180001483  cmp     [rbx+18h], esi
0x180001486  jbe     short loc_1800014A6
0x180001488  call    WsRedirectionPaused
0x18000148d  test    eax, eax
0x18000148f  jz      short loc_1800014A6
0x180001491  lea     rcx, Resource; Resource
0x180001498  call    cs:__imp_RtlReleaseResource
0x18000149e  lea     eax, [rsi+46h]
0x1800014a1  jmp     loc_180001567
0x1800014a6  test    edi, edi
0x1800014a8  jz      short loc_1800014CF
0x1800014aa  mov     r8, [rbx+8]
0x1800014ae  lea     rcx, [rbp+3B0h+pszDest]; pszDest
0x1800014b5  mov     edx, 20Ah; cbDest
0x1800014ba  test    r8, r8
0x1800014bd  jz      short loc_1800014C5
0x1800014bf  add     r8, 8
0x1800014c3  jmp     short loc_1800014CA
0x1800014c5  lea     r8, [rsp+4B0h+pszSrc]; pszSrc
0x1800014ca  call    StringCbCopyW
0x1800014cf  mov     r9d, [rsp+4B0h+var_480]
0x1800014d4  lea     rcx, [rsp+4B0h+SourceLuid]
0x1800014d9  mov     r8, rbx
0x1800014dc  mov     byte ptr [rsp+4B0h+var_490], r15b
0x1800014e1  mov     edx, r14d
0x1800014e4  call    WsDeleteUse
0x1800014e9  mov     r14d, eax
0x1800014ec  test    eax, eax
0x1800014ee  jnz     short loc_180001564
0x1800014f0  test    edi, edi
0x1800014f2  jz      short loc_180001564
0x1800014f4  xor     edx, edx
0x1800014f6  xor     ecx, ecx
0x1800014f8  call    WsImpersonateClient2
0x1800014fd  test    eax, eax
0x1800014ff  jnz     short loc_180001564
0x180001501  lea     rdx, [rsp+4B0h+hMem]
0x180001506  mov     [rsp+4B0h+hMem], 0
0x18000150f  lea     rcx, [rsp+4B0h+pszSrc]; SourceString
0x180001514  xor     bl, bl
0x180001516  call    WsQueryGlobalMappingFromRegistry
0x18000151b  test    eax, eax
0x18000151d  jnz     short loc_18000152F
0x18000151f  mov     rcx, [rsp+4B0h+hMem]; hMem
0x180001524  mov     esi, [rcx+14h]
0x180001527  call    cs:__imp_LocalFree
0x18000152d  mov     bl, 1
0x18000152f  lea     rcx, [rsp+4B0h+pszSrc]; SourceString
0x180001534  call    WsDeleteGlobalMappingFromRegistry
0x180001539  xor     edx, edx
0x18000153b  xor     ecx, ecx
0x18000153d  call    WsRevertToSelf2
0x180001542  test    bl, bl
0x180001544  jz      short loc_180001564
0x180001546  lea     rcx, [rbp+3B0h+pszDest]
0x18000154d  call    WsGlobalMappingsToSameTargetExist
0x180001552  test    al, al
0x180001554  jnz     short loc_180001564
0x180001556  mov     edx, esi
0x180001558  lea     rcx, [rbp+3B0h+pszDest]
0x18000155f  call    WsDeleteNetUseCredential
0x180001564  mov     eax, r14d
0x180001567  mov     rcx, [rbp+3B0h+var_30]
0x18000156e  xor     rcx, rsp; StackCookie
0x180001571  call    __security_check_cookie
0x180001576  mov     rbx, [rsp+4B0h+arg_0]
0x18000157e  add     rsp, 490h
0x180001585  pop     r15
0x180001587  pop     r14
0x180001589  pop     rdi
0x18000158a  pop     rsi
0x18000158b  pop     rbp
0x18000158c  retn
```
