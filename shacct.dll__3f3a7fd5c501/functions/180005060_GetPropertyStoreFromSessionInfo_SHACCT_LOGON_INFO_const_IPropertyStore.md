# _GetPropertyStoreFromSessionInfo(_SHACCT_LOGON_INFO const *,IPropertyStore * *)

- ea: `0x180005060`
- end: `0x1800052ec`
- name: `?_GetPropertyStoreFromSessionInfo@@YAJPEBU_SHACCT_LOGON_INFO@@PEAPEAUIPropertyStore@@@Z`
- size: `652`
- prototype: `__int64 __fastcall(const struct _SHACCT_LOGON_INFO *, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013ad0`

## callees

- `0x180005060`
- `0x180005300`
- `0x1800059f0`
- `0x18000b598`
- `0x18000bcc0`
- `0x18000c240`
- `0x18000d740`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800051c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800051c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005289`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800052a4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800052b8`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800052a4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800052b8`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800050ac`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800050f8`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800050ac`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800050f8`

## pseudocode

```c
__int64 __fastcall _GetPropertyStoreFromSessionInfo(DWORD *a1, struct IPropertyStore **a2)
{
  DWORD v3; // edx
  int Error; // ebx
  DWORD v6; // edx
  unsigned __int16 *v7; // rcx
  LPWSTR v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rax
  void *v11; // rsi
  char *v12; // rax
  char *v13; // rdi
  LPWSTR ppBuffer; // [rsp+30h] [rbp-478h] BYREF
  DWORD pBytesReturned; // [rsp+38h] [rbp-470h] BYREF
  DWORD v17; // [rsp+3Ch] [rbp-46Ch] BYREF
  LPWSTR v18; // [rsp+40h] [rbp-468h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-460h] BYREF
  unsigned __int16 *v20; // [rsp+50h] [rbp-458h] BYREF
  unsigned __int16 v21[520]; // [rsp+60h] [rbp-448h] BYREF

  *a2 = 0;
  ppBuffer = 0;
  v3 = *a1;
  pBytesReturned = 0;
  if ( !WTSQuerySessionInformationW(0, v3, WTSUserName, &ppBuffer, &pBytesReturned) )
    return ResultFromKnownLastError();
  Error = -2147024809;
  if ( *ppBuffer )
  {
    v6 = *a1;
    v18 = 0;
    v17 = 0;
    if ( WTSQuerySessionInformationW(0, v6, WTSDomainName, &v18, &v17) )
    {
      v7 = v21;
      if ( v18 )
      {
        Error = StringCchPrintfW(v21, 0x201u, L"%s\\%s");
      }
      else
      {
        v8 = ppBuffer;
        v9 = 2147483646;
        v10 = 513;
        Error = 0;
        while ( v9 && *v8 )
        {
          *v7++ = *v8++;
          --v9;
          if ( !--v10 )
          {
            --v7;
            Error = -2147024774;
            break;
          }
        }
        *v7 = 0;
      }
      if ( Error >= 0 )
      {
        pv = 0;
        v20 = v21;
        Error = LookupNames((void *)1, (const unsigned __int16 *const *)&v20, (void ***)&pv);
        if ( Error >= 0 )
        {
          v11 = *(void **)pv;
          CoTaskMemFree(pv);
          *a2 = 0;
          Error = -2147024882;
          v12 = (char *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
          v13 = v12;
          if ( v12 )
          {
            *((_DWORD *)v12 + 4) = 1;
            *(_QWORD *)v12 = &CLoggedOnPropStore::`vftable'{for `IPropertyStore'};
            *((_QWORD *)v12 + 3) = 0;
            *((_QWORD *)v12 + 1) = &CLoggedOnPropStore::`vftable'{for `IPersistSerializedPropStorage'};
            *((_QWORD *)v12 + 4) = 0;
            *((_QWORD *)v12 + 5) = 0;
            *((_QWORD *)v12 + 6) = 0;
            *((_QWORD *)v12 + 7) = 0;
            *((_DWORD *)v12 + 16) = 0;
            *((_QWORD *)v12 + 9) = 0;
            *((_QWORD *)v12 + 10) = 0;
            *((_QWORD *)v12 + 11) = 0;
            *((_QWORD *)v12 + 12) = 0;
            *(_OWORD *)(v12 + 104) = 0;
            *((_QWORD *)v12 + 15) = 0;
            _InterlockedIncrement(&g_cRefCount);
            Error = CLoggedOnPropStore::Init((CLoggedOnPropStore *)v12, (const struct _SHACCT_LOGON_INFO *)a1, v11);
            if ( Error >= 0 )
              Error = (**(__int64 (__fastcall ***)(char *, GUID *, struct IPropertyStore **))v13)(
                        v13,
                        &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                        a2);
            (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 16LL))(v13);
          }
          CoTaskMemFree(v11);
        }
      }
      WTSFreeMemory(v18);
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
  }
  WTSFreeMemory(ppBuffer);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180005060  push    rbp
0x180005062  push    r14
0x180005064  push    r15
0x180005066  sub     rsp, 490h
0x18000506d  mov     rax, cs:__security_cookie
0x180005074  xor     rax, rsp
0x180005077  mov     [rsp+4A8h+var_38], rax
0x18000507f  xor     ebp, ebp
0x180005081  lea     rax, [rsp+4A8h+var_470]
0x180005086  mov     [rdx], rbp
0x180005089  lea     r9, [rsp+4A8h+ppBuffer]; ppBuffer
0x18000508e  mov     r14, rdx
0x180005091  mov     [rsp+4A8h+ppBuffer], rbp
0x180005096  mov     edx, [rcx]; SessionId
0x180005098  mov     r15, rcx
0x18000509b  xor     ecx, ecx; hServer
0x18000509d  mov     [rsp+4A8h+var_470], ebp
0x1800050a1  mov     r8d, 5; WTSInfoClass
0x1800050a7  mov     [rsp+4A8h+pBytesReturned], rax; pBytesReturned
0x1800050ac  call    cs:__imp_WTSQuerySessionInformationW
0x1800050b2  test    eax, eax
0x1800050b4  jz      loc_1800052CA
0x1800050ba  mov     rax, [rsp+4A8h+ppBuffer]
0x1800050bf  mov     [rsp+4A8h+arg_10], rbx
0x1800050c7  mov     ebx, 80070057h
0x1800050cc  cmp     [rax], bp
0x1800050cf  jz      loc_1800052B3
0x1800050d5  mov     edx, [r15]; SessionId
0x1800050d8  lea     rax, [rsp+4A8h+var_46C]
0x1800050dd  lea     r9, [rsp+4A8h+var_468]; ppBuffer
0x1800050e2  mov     [rsp+4A8h+pBytesReturned], rax; pBytesReturned
0x1800050e7  mov     r8d, 7; WTSInfoClass
0x1800050ed  mov     [rsp+4A8h+var_468], rbp
0x1800050f2  xor     ecx, ecx; hServer
0x1800050f4  mov     [rsp+4A8h+var_46C], ebp
0x1800050f8  call    cs:__imp_WTSQuerySessionInformationW
0x1800050fe  test    eax, eax
0x180005100  jz      loc_1800052AC
0x180005106  mov     r9, [rsp+4A8h+var_468]
0x18000510b  lea     rcx, [rsp+4A8h+var_448]; unsigned __int16 *
0x180005110  test    r9, r9
0x180005113  jz      short loc_180005134
0x180005115  mov     rax, [rsp+4A8h+ppBuffer]
0x18000511a  lea     r8, aSS; "%s\\%s"
0x180005121  mov     edx, 201h; unsigned __int64
0x180005126  mov     [rsp+4A8h+pBytesReturned], rax
0x18000512b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005130  mov     ebx, eax
0x180005132  jmp     short loc_18000517C
0x180005134  mov     r8, [rsp+4A8h+ppBuffer]
0x180005139  mov     edx, 7FFFFFFEh
0x18000513e  mov     eax, 201h
0x180005143  mov     ebx, ebp
0x180005145  test    rdx, rdx
0x180005148  jz      short loc_180005179
0x18000514a  movzx   r9d, word ptr [r8]
0x18000514e  test    r9w, r9w
0x180005152  jz      short loc_18000516B
0x180005154  mov     [rcx], r9w
0x180005158  add     r8, 2
0x18000515c  add     rcx, 2
0x180005160  dec     rdx
0x180005163  sub     rax, 1
0x180005167  jnz     short loc_180005145
0x180005169  jmp     short loc_180005170
0x18000516b  test    rax, rax
0x18000516e  jnz     short loc_180005179
0x180005170  sub     rcx, 2
0x180005174  mov     ebx, 8007007Ah
0x180005179  mov     [rcx], bp
0x18000517c  test    ebx, ebx
0x18000517e  js      loc_18000529F
0x180005184  lea     rax, [rsp+4A8h+var_448]
0x180005189  mov     [rsp+4A8h+pv], rbp
0x18000518e  lea     r8, [rsp+4A8h+pv]; void ***
0x180005193  mov     [rsp+4A8h+var_458], rax
0x180005198  lea     rdx, [rsp+4A8h+var_458]; unsigned __int16 **
0x18000519d  mov     ecx, 1; Count
0x1800051a2  call    ?LookupNames@@YAJKPEBQEBGPEAPEAPEAX@Z; LookupNames(ulong,ushort const * const *,void * * *)
0x1800051a7  mov     ebx, eax
0x1800051a9  test    eax, eax
0x1800051ab  js      loc_18000529F
0x1800051b1  mov     rcx, [rsp+4A8h+pv]; pv
0x1800051b6  mov     [rsp+4A8h+var_20], rsi
0x1800051be  mov     [rsp+4A8h+var_28], rdi
0x1800051c6  mov     rsi, [rcx]
0x1800051c9  call    cs:__imp_CoTaskMemFree
0x1800051cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800051d6  mov     [r14], rbp
0x1800051d9  mov     ecx, 80h; unsigned __int64
0x1800051de  mov     ebx, 8007000Eh
0x1800051e3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800051e8  mov     rdi, rax
0x1800051eb  test    rax, rax
0x1800051ee  jz      loc_180005286
0x1800051f4  lea     rax, ??_7CLoggedOnPropStore@@6BIPropertyStore@@@; const CLoggedOnPropStore::`vftable'{for `IPropertyStore'}
0x1800051fb  mov     dword ptr [rdi+10h], 1
0x180005202  mov     [rdi], rax
0x180005205  xorps   xmm0, xmm0
0x180005208  lea     rax, ??_7CLoggedOnPropStore@@6BIPersistSerializedPropStorage@@@; const CLoggedOnPropStore::`vftable'{for `IPersistSerializedPropStorage'}
0x18000520f  mov     [rdi+18h], rbp
0x180005213  mov     [rdi+8], rax
0x180005217  mov     [rdi+20h], rbp
0x18000521b  mov     [rdi+28h], rbp
0x18000521f  mov     [rdi+30h], rbp
0x180005223  mov     [rdi+38h], rbp
0x180005227  mov     [rdi+40h], ebp
0x18000522a  mov     [rdi+48h], rbp
0x18000522e  mov     [rdi+50h], rbp
0x180005232  mov     [rdi+58h], rbp
0x180005236  mov     [rdi+60h], rbp
0x18000523a  movups  xmmword ptr [rdi+68h], xmm0
0x18000523e  mov     [rdi+78h], rbp
0x180005242  lock inc cs:?g_cRefCount@@3JA; long g_cRefCount
0x180005249  mov     r8, rsi; void *
0x18000524c  mov     rdx, r15; struct _SHACCT_LOGON_INFO *
0x18000524f  mov     rcx, rdi; this
0x180005252  call    ?Init@CLoggedOnPropStore@@QEAAJPEBU_SHACCT_LOGON_INFO@@PEAX@Z; CLoggedOnPropStore::Init(_SHACCT_LOGON_INFO const *,void *)
0x180005257  mov     ebx, eax
0x180005259  test    eax, eax
0x18000525b  js      short loc_180005277
0x18000525d  mov     rax, [rdi]
0x180005260  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180005267  mov     r8, r14
0x18000526a  mov     rcx, rdi
0x18000526d  mov     rax, [rax]
0x180005270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005275  mov     ebx, eax
0x180005277  mov     rax, [rdi]
0x18000527a  mov     rcx, rdi
0x18000527d  mov     rax, [rax+10h]
0x180005281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005286  mov     rcx, rsi; pv
0x180005289  call    cs:__imp_CoTaskMemFree
0x18000528f  mov     rdi, [rsp+4A8h+var_28]
0x180005297  mov     rsi, [rsp+4A8h+var_20]
0x18000529f  mov     rcx, [rsp+4A8h+var_468]; pMemory
0x1800052a4  call    cs:__imp_WTSFreeMemory
0x1800052aa  jmp     short loc_1800052B3
0x1800052ac  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800052b1  mov     ebx, eax
0x1800052b3  mov     rcx, [rsp+4A8h+ppBuffer]; pMemory
0x1800052b8  call    cs:__imp_WTSFreeMemory
0x1800052be  mov     eax, ebx
0x1800052c0  mov     rbx, [rsp+4A8h+arg_10]
0x1800052c8  jmp     short loc_1800052CF
0x1800052ca  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800052cf  mov     rcx, [rsp+4A8h+var_38]
0x1800052d7  xor     rcx, rsp; StackCookie
0x1800052da  call    __security_check_cookie
0x1800052df  add     rsp, 490h
0x1800052e6  pop     r15
0x1800052e8  pop     r14
0x1800052ea  pop     rbp
0x1800052eb  retn
```
