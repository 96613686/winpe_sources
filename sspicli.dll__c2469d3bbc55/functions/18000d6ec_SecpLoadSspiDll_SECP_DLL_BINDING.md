# SecpLoadSspiDll(_SECP_DLL_BINDING *)

- ea: `0x18000d6ec`
- end: `0x18000d8a5`
- name: `?SecpLoadSspiDll@@YAJPEAU_SECP_DLL_BINDING@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(struct _SECP_DLL_BINDING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800070d0`

## callees

- `0x180007520`
- `0x180007d30`
- `0x18000d6ec`
- `0x18000d8ac`
- `0x18000e084`
- `0x18000e178`
- `0x18001d478`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000d7f3`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000d7f3`
- `ntdll!RtlReleaseResource` at `0x18000d871`
- `ntdll!RtlReleaseResource` at `0x18000d871`

## pseudocode

```c
__int64 __fastcall SecpLoadSspiDll(struct _LIST_ENTRY *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r8
  unsigned int v6; // esi
  int v7; // ecx
  struct _LIST_ENTRY *Flink; // rbx
  struct _LIST_ENTRY *v9; // rax
  __int64 v10; // rdi
  __int64 v11; // r8
  __int64 i; // rbx
  struct _LIST_ENTRY v13; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v14; // [rsp+58h] [rbp+10h] BYREF

  v14 = 0;
  v13 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, a3, a1[1].Blink);
  if ( (unsigned int)SecpRefDllFromCache((struct _SECP_DLL_BINDING *)a1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v4, a1[1].Blink);
    return 0;
  }
  else
  {
    v6 = SecpSnapDll(a1, &v13, &v14);
    if ( !v6 )
    {
      HIDWORD(a1[2].Flink) = v14;
      v7 = SecPackageListLockCount;
      while ( 1 )
      {
        Flink = v13.Flink;
        if ( v13.Flink == &v13 )
          break;
        if ( v13.Flink->Blink != &v13 || (v9 = v13.Flink->Flink, v13.Flink->Flink->Blink != v13.Flink) )
          __fastfail(3u);
        v10 = 0;
        v13.Flink = v13.Flink->Flink;
        v9->Blink = &v13;
        if ( v7 )
        {
          do
          {
            RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * v10], 1u);
            v10 = (unsigned int)(v10 + 1);
          }
          while ( (unsigned int)v10 < SecPackageListLockCount );
        }
        if ( SecpScanPackageListEx(0, 8u, (struct _UNICODE_STRING *)&Flink[6], 0xFFFFFFFFFFFFFFFFuLL) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v11, Flink[6].Blink);
          SecpFreePackage(Flink, 1);
        }
        else
        {
          SecpAddDllPackage((struct _DLL_SECURITY_PACKAGE *)Flink);
        }
        v7 = SecPackageListLockCount;
        for ( i = 0; (unsigned int)i < SecPackageListLockCount; i = (unsigned int)(i + 1) )
        {
          RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * i]);
          v7 = SecPackageListLockCount;
        }
      }
    }
    return v6;
  }
}

```

## disassembly

```asm
0x18000d6ec  mov     rax, rsp
0x18000d6ef  mov     [rax+8], rbx
0x18000d6f3  mov     [rax+18h], rsi
0x18000d6f7  push    rdi
0x18000d6f8  push    r14
0x18000d6fa  push    r15
0x18000d6fc  sub     rsp, 30h
0x18000d700  xorps   xmm0, xmm0
0x18000d703  mov     dword ptr [rax+10h], 0
0x18000d70a  movups  xmmword ptr [rax-28h], xmm0
0x18000d70e  mov     rbx, rcx
0x18000d711  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d718  lea     r14, WPP_GLOBAL_Control
0x18000d71f  cmp     rcx, r14
0x18000d722  jz      short loc_18000D73C
0x18000d724  test    byte ptr [rcx+1Ch], 4
0x18000d728  jz      short loc_18000D73C
0x18000d72a  mov     r9, [rbx+18h]
0x18000d72e  mov     edx, 20h ; ' '
0x18000d733  mov     rcx, [rcx+10h]
0x18000d737  call    WPP_SF_S
0x18000d73c  mov     rcx, rbx; struct _SECP_DLL_BINDING *
0x18000d73f  call    ?SecpRefDllFromCache@@YAHPEAU_SECP_DLL_BINDING@@@Z; SecpRefDllFromCache(_SECP_DLL_BINDING *)
0x18000d744  test    eax, eax
0x18000d746  jz      short loc_18000D773
0x18000d748  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d74f  cmp     rcx, r14
0x18000d752  jz      short loc_18000D76C
0x18000d754  test    byte ptr [rcx+1Ch], 4
0x18000d758  jz      short loc_18000D76C
0x18000d75a  mov     r9, [rbx+18h]
0x18000d75e  mov     edx, 21h ; '!'
0x18000d763  mov     rcx, [rcx+10h]
0x18000d767  call    WPP_SF_S
0x18000d76c  xor     eax, eax
0x18000d76e  jmp     loc_18000D891
0x18000d773  lea     r8, [rsp+48h+arg_8]; unsigned int *
0x18000d778  mov     rcx, rbx; struct _SECP_DLL_BINDING *
0x18000d77b  lea     rdx, [rsp+48h+var_28]; struct _LIST_ENTRY *
0x18000d780  call    ?SecpSnapDll@@YAJPEAU_SECP_DLL_BINDING@@PEAU_LIST_ENTRY@@PEAK@Z; SecpSnapDll(_SECP_DLL_BINDING *,_LIST_ENTRY *,ulong *)
0x18000d785  mov     esi, eax
0x18000d787  test    eax, eax
0x18000d789  jnz     loc_18000D88F
0x18000d78f  mov     ecx, [rsp+48h+arg_8]
0x18000d793  lea     r15, SecPackageListLock
0x18000d79a  mov     [rbx+24h], ecx
0x18000d79d  mov     ecx, cs:SecPackageListLockCount
0x18000d7a3  mov     rbx, [rsp+48h+var_28.Flink]
0x18000d7a8  lea     rax, [rsp+48h+var_28]
0x18000d7ad  cmp     rbx, rax
0x18000d7b0  jz      loc_18000D88F
0x18000d7b6  lea     rax, [rsp+48h+var_28]
0x18000d7bb  cmp     [rbx+8], rax
0x18000d7bf  jnz     loc_18000D888
0x18000d7c5  mov     rax, [rbx]
0x18000d7c8  cmp     [rax+8], rbx
0x18000d7cc  jnz     loc_18000D888
0x18000d7d2  xor     edi, edi
0x18000d7d4  mov     [rsp+48h+var_28.Flink], rax
0x18000d7d9  lea     rdx, [rsp+48h+var_28]
0x18000d7de  mov     [rax+8], rdx
0x18000d7e2  test    ecx, ecx
0x18000d7e4  jz      short loc_18000D803
0x18000d7e6  lea     rcx, [rdi+rdi*2]
0x18000d7ea  mov     dl, 1; Wait
0x18000d7ec  shl     rcx, 5
0x18000d7f0  add     rcx, r15; Resource
0x18000d7f3  call    cs:__imp_RtlAcquireResourceExclusive
0x18000d7f9  inc     edi
0x18000d7fb  cmp     edi, cs:SecPackageListLockCount
0x18000d801  jb      short loc_18000D7E6
0x18000d803  or      r9, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x18000d807  lea     r8, [rbx+60h]; struct _UNICODE_STRING *
0x18000d80b  xor     ecx, ecx; int
0x18000d80d  lea     edx, [r9+9]; unsigned int
0x18000d811  call    ?SecpScanPackageListEx@@YAPEAU_DLL_SECURITY_PACKAGE@@HKPEAU_UNICODE_STRING@@_K@Z; SecpScanPackageListEx(int,ulong,_UNICODE_STRING *,unsigned __int64)
0x18000d816  test    rax, rax
0x18000d819  jnz     short loc_18000D825
0x18000d81b  mov     rcx, rbx; struct _DLL_SECURITY_PACKAGE *
0x18000d81e  call    ?SecpAddDllPackage@@YAXPEAU_DLL_SECURITY_PACKAGE@@@Z; SecpAddDllPackage(_DLL_SECURITY_PACKAGE *)
0x18000d823  jmp     short loc_18000D856
0x18000d825  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d82c  cmp     rcx, r14
0x18000d82f  jz      short loc_18000D849
0x18000d831  test    byte ptr [rcx+1Ch], 4
0x18000d835  jz      short loc_18000D849
0x18000d837  mov     r9, [rbx+68h]
0x18000d83b  mov     edx, 22h ; '"'
0x18000d840  mov     rcx, [rcx+10h]
0x18000d844  call    WPP_SF_S
0x18000d849  mov     edx, 1
0x18000d84e  mov     rcx, rbx
0x18000d851  call    SecpFreePackage
0x18000d856  mov     ecx, cs:SecPackageListLockCount
0x18000d85c  xor     ebx, ebx
0x18000d85e  test    ecx, ecx
0x18000d860  jz      loc_18000D7A3
0x18000d866  lea     rcx, [rbx+rbx*2]
0x18000d86a  shl     rcx, 5
0x18000d86e  add     rcx, r15; Resource
0x18000d871  call    cs:__imp_RtlReleaseResource
0x18000d877  mov     ecx, cs:SecPackageListLockCount
0x18000d87d  inc     ebx
0x18000d87f  cmp     ebx, ecx
0x18000d881  jb      short loc_18000D866
0x18000d883  jmp     loc_18000D7A3
0x18000d888  mov     ecx, 3
0x18000d88d  int     29h; Win8: RtlFailFast(ecx)
0x18000d88f  mov     eax, esi
0x18000d891  mov     rbx, [rsp+48h+arg_0]
0x18000d896  mov     rsi, [rsp+48h+arg_10]
0x18000d89b  add     rsp, 30h
0x18000d89f  pop     r15
0x18000d8a1  pop     r14
0x18000d8a3  pop     rdi
0x18000d8a4  retn
```
