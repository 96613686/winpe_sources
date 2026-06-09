# CEnumLogonAccounts::Next(ulong,IPropertyStore * *,ulong *)

- ea: `0x180004c90`
- end: `0x180004fbd`
- name: `?Next@CEnumLogonAccounts@@UEAAJKPEAPEAUIPropertyStore@@PEAK@Z`
- size: `813`
- prototype: `__int64 __fastcall(CEnumLogonAccounts *__hidden this, unsigned int, struct IPropertyStore **, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004c90`
- `0x180005300`
- `0x1800059f0`
- `0x18000b598`
- `0x18000bcc0`
- `0x18000c240`
- `0x18000d740`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f11`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180004f22`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180004f2d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180004f41`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180004f22`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180004f2d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180004f41`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180004d41`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180004d86`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180004d41`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180004d86`

## pseudocode

```c
__int64 __fastcall CEnumLogonAccounts::Next(
        CEnumLogonAccounts *this,
        int a2,
        struct IPropertyStore **a3,
        unsigned int *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rax
  const struct _SHACCT_LOGON_INFO *v9; // r15
  int Error; // edi
  DWORD v11; // edx
  unsigned __int16 *v12; // rcx
  LPWSTR v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rax
  void *v16; // rsi
  char *v17; // rax
  char *v18; // rbx
  int v20; // [rsp+38h] [rbp-D0h]
  LPWSTR ppBuffer; // [rsp+40h] [rbp-C8h] BYREF
  DWORD pBytesReturned[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPWSTR v23; // [rsp+50h] [rbp-B8h] BYREF
  struct IPropertyStore *v24; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int16 *v26; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 v27[520]; // [rsp+78h] [rbp-90h] BYREF

  if ( a3 && a4 && a2 )
  {
    v7 = 1;
    *a3 = 0;
    *a4 = 0;
    v20 = 1;
    while ( 1 )
    {
      v8 = *((unsigned int *)this + 6);
      if ( (unsigned int)v8 >= *((_DWORD *)this + 3) )
        return v7;
      v24 = 0;
      v9 = (const struct _SHACCT_LOGON_INFO *)(*((_QWORD *)this + 2) + 528 * v8);
      ppBuffer = 0;
      pBytesReturned[0] = 0;
      if ( WTSQuerySessionInformationW(0, *(_DWORD *)v9, WTSUserName, &ppBuffer, pBytesReturned) )
      {
        Error = -2147024809;
        if ( *ppBuffer )
        {
          v11 = *(_DWORD *)v9;
          v23 = 0;
          pBytesReturned[1] = 0;
          if ( WTSQuerySessionInformationW(0, v11, WTSDomainName, &v23, &pBytesReturned[1]) )
          {
            v12 = v27;
            if ( v23 )
            {
              Error = StringCchPrintfW(v27, 0x201u, L"%s\\%s");
            }
            else
            {
              v13 = ppBuffer;
              v14 = 2147483646;
              v15 = 513;
              Error = 0;
              while ( v14 && *v13 )
              {
                *v12++ = *v13++;
                --v14;
                if ( !--v15 )
                {
                  --v12;
                  Error = -2147024774;
                  break;
                }
              }
              *v12 = 0;
            }
            if ( Error >= 0 )
            {
              pv = 0;
              v26 = v27;
              Error = LookupNames((void *)1, (const unsigned __int16 *const *)&v26, (void ***)&pv);
              if ( Error >= 0 )
              {
                v16 = *(void **)pv;
                CoTaskMemFree(pv);
                v24 = 0;
                Error = -2147024882;
                v17 = (char *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
                v18 = v17;
                if ( v17 )
                {
                  *((_DWORD *)v17 + 4) = 1;
                  *(_QWORD *)v17 = &CLoggedOnPropStore::`vftable'{for `IPropertyStore'};
                  *((_QWORD *)v17 + 1) = &CLoggedOnPropStore::`vftable'{for `IPersistSerializedPropStorage'};
                  *((_QWORD *)v17 + 3) = 0;
                  *((_QWORD *)v17 + 4) = 0;
                  *((_QWORD *)v17 + 5) = 0;
                  *((_QWORD *)v17 + 6) = 0;
                  *((_QWORD *)v17 + 7) = 0;
                  *((_DWORD *)v17 + 16) = 0;
                  *((_QWORD *)v17 + 9) = 0;
                  *((_QWORD *)v17 + 10) = 0;
                  *((_QWORD *)v17 + 11) = 0;
                  *((_QWORD *)v17 + 12) = 0;
                  *(_OWORD *)(v17 + 104) = 0;
                  *((_QWORD *)v17 + 15) = 0;
                  _InterlockedIncrement(&g_cRefCount);
                  Error = CLoggedOnPropStore::Init((CLoggedOnPropStore *)v17, v9, v16);
                  if ( Error >= 0 )
                    Error = (**(__int64 (__fastcall ***)(char *, GUID *, struct IPropertyStore **))v18)(
                              v18,
                              &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                              &v24);
                  (*(void (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))(v18);
                }
                CoTaskMemFree(v16);
                v7 = v20;
              }
            }
            WTSFreeMemory(v23);
            WTSFreeMemory(ppBuffer);
            goto LABEL_28;
          }
          Error = ResultFromKnownLastError();
        }
        WTSFreeMemory(ppBuffer);
      }
      else
      {
        Error = ResultFromKnownLastError();
      }
LABEL_28:
      if ( Error >= 0 )
      {
        v7 = 0;
        *a3 = v24;
        ++*a4;
        v20 = 0;
      }
      ++*((_DWORD *)this + 6);
      if ( *a4 )
        return v7;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180004c90  mov     r11, rsp
0x180004c93  push    rbp
0x180004c94  push    r12
0x180004c96  push    r13
0x180004c98  push    r14
0x180004c9a  lea     rbp, [r11-3C8h]
0x180004ca1  sub     rsp, 4A8h
0x180004ca8  mov     rax, cs:__security_cookie
0x180004caf  xor     rax, rsp
0x180004cb2  mov     [rbp+3C0h+var_40], rax
0x180004cb9  mov     r13, r9
0x180004cbc  mov     r12, r8
0x180004cbf  mov     r14, rcx
0x180004cc2  test    r8, r8
0x180004cc5  jz      loc_180004FB6
0x180004ccb  test    r9, r9
0x180004cce  jz      loc_180004FB6
0x180004cd4  test    edx, edx
0x180004cd6  jz      loc_180004FB6
0x180004cdc  mov     [r11+10h], rbx
0x180004ce0  mov     ebx, 1
0x180004ce5  mov     [r11-28h], rsi
0x180004ce9  xor     esi, esi
0x180004ceb  mov     [r8], rsi
0x180004cee  mov     [r11-30h], rdi
0x180004cf2  mov     [r9], esi
0x180004cf5  mov     dword ptr [rsp+4C0h+var_490], ebx
0x180004cf9  mov     [r11-38h], r15
0x180004cfd  nop     dword ptr [rax]
0x180004d00  mov     eax, [r14+18h]
0x180004d04  cmp     eax, [r14+0Ch]
0x180004d08  jnb     loc_180004F76
0x180004d0e  imul    r15, rax, 210h
0x180004d15  mov     [rsp+4C0h+var_470], rsi
0x180004d1a  lea     rax, [rsp+4C0h+pBytesReturned]
0x180004d1f  add     r15, [r14+10h]
0x180004d23  lea     r9, [rsp+4C0h+ppBuffer]; ppBuffer
0x180004d28  mov     r8d, 5; WTSInfoClass
0x180004d2e  mov     [rsp+4C0h+ppBuffer], rsi
0x180004d33  xor     ecx, ecx; hServer
0x180004d35  mov     [rsp+4C0h+pBytesReturned], esi
0x180004d39  mov     [rsp+20h], rax; pBytesReturned
0x180004d3e  mov     edx, [r15]; SessionId
0x180004d41  call    cs:__imp_WTSQuerySessionInformationW
0x180004d47  test    eax, eax
0x180004d49  jz      loc_180004F49
0x180004d4f  mov     rax, [rsp+4C0h+ppBuffer]
0x180004d54  mov     edi, 80070057h
0x180004d59  cmp     word ptr [rax], 0
0x180004d5d  jz      loc_180004F3C
0x180004d63  mov     edx, [r15]; SessionId
0x180004d66  lea     rax, [rsp+4C0h+pBytesReturned+4]
0x180004d6b  lea     r9, [rsp+4C0h+var_478]; ppBuffer
0x180004d70  mov     [rsp+20h], rax; pBytesReturned
0x180004d75  mov     r8d, 7; WTSInfoClass
0x180004d7b  mov     [rsp+4C0h+var_478], rsi
0x180004d80  xor     ecx, ecx; hServer
0x180004d82  mov     [rsp+4C0h+pBytesReturned+4], esi
0x180004d86  call    cs:__imp_WTSQuerySessionInformationW
0x180004d8c  test    eax, eax
0x180004d8e  jz      loc_180004F35
0x180004d94  mov     r9, [rsp+4C0h+var_478]
0x180004d99  lea     rcx, [rsp+4C0h+var_450]; unsigned __int16 *
0x180004d9e  test    r9, r9
0x180004da1  jz      short loc_180004DC2
0x180004da3  mov     rax, [rsp+4C0h+ppBuffer]
0x180004da8  lea     r8, aSS; "%s\\%s"
0x180004daf  mov     edx, 201h; unsigned __int64
0x180004db4  mov     [rsp+20h], rax
0x180004db9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004dbe  mov     edi, eax
0x180004dc0  jmp     short loc_180004E0A
0x180004dc2  mov     r8, [rsp+4C0h+ppBuffer]
0x180004dc7  mov     edx, 7FFFFFFEh
0x180004dcc  mov     eax, 201h
0x180004dd1  mov     edi, esi
0x180004dd3  test    rdx, rdx
0x180004dd6  jz      short loc_180004E07
0x180004dd8  movzx   r9d, word ptr [r8]
0x180004ddc  test    r9w, r9w
0x180004de0  jz      short loc_180004DF9
0x180004de2  mov     [rcx], r9w
0x180004de6  add     r8, 2
0x180004dea  add     rcx, 2
0x180004dee  dec     rdx
0x180004df1  sub     rax, 1
0x180004df5  jnz     short loc_180004DD3
0x180004df7  jmp     short loc_180004DFE
0x180004df9  test    rax, rax
0x180004dfc  jnz     short loc_180004E07
0x180004dfe  sub     rcx, 2
0x180004e02  mov     edi, 8007007Ah
0x180004e07  mov     [rcx], si
0x180004e0a  test    edi, edi
0x180004e0c  js      loc_180004F1D
0x180004e12  lea     rax, [rsp+4C0h+var_450]
0x180004e17  mov     [rsp+4C0h+pv], rsi
0x180004e1c  lea     r8, [rsp+4C0h+pv]; void ***
0x180004e21  mov     [rsp+4C0h+var_460], rax
0x180004e26  lea     rdx, [rsp+4C0h+var_460]; unsigned __int16 **
0x180004e2b  mov     ecx, 1; Count
0x180004e30  call    ?LookupNames@@YAJKPEBQEBGPEAPEAPEAX@Z; LookupNames(ulong,ushort const * const *,void * * *)
0x180004e35  mov     edi, eax
0x180004e37  test    eax, eax
0x180004e39  js      loc_180004F1D
0x180004e3f  mov     rcx, [rsp+4C0h+pv]; pv
0x180004e44  mov     rsi, [rcx]
0x180004e47  call    cs:__imp_CoTaskMemFree
0x180004e4d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004e54  mov     [rsp+4C0h+var_470], 0
0x180004e5d  mov     ecx, 80h; unsigned __int64
0x180004e62  mov     edi, 8007000Eh
0x180004e67  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004e6c  mov     rbx, rax
0x180004e6f  test    rax, rax
0x180004e72  jz      loc_180004F0E
0x180004e78  lea     rax, ??_7CLoggedOnPropStore@@6BIPropertyStore@@@; const CLoggedOnPropStore::`vftable'{for `IPropertyStore'}
0x180004e7f  mov     dword ptr [rbx+10h], 1
0x180004e86  mov     [rbx], rax
0x180004e89  xorps   xmm0, xmm0
0x180004e8c  lea     rax, ??_7CLoggedOnPropStore@@6BIPersistSerializedPropStorage@@@; const CLoggedOnPropStore::`vftable'{for `IPersistSerializedPropStorage'}
0x180004e93  mov     [rbx+8], rax
0x180004e97  xor     eax, eax
0x180004e99  mov     [rbx+18h], rax
0x180004e9d  mov     [rbx+20h], rax
0x180004ea1  mov     [rbx+28h], rax
0x180004ea5  mov     [rbx+30h], rax
0x180004ea9  mov     [rbx+38h], rax
0x180004ead  mov     [rbx+40h], eax
0x180004eb0  mov     [rbx+48h], rax
0x180004eb4  mov     [rbx+50h], rax
0x180004eb8  mov     [rbx+58h], rax
0x180004ebc  mov     [rbx+60h], rax
0x180004ec0  movups  xmmword ptr [rbx+68h], xmm0
0x180004ec4  mov     [rbx+78h], rax
0x180004ec8  lock inc cs:?g_cRefCount@@3JA; long g_cRefCount
0x180004ecf  mov     r8, rsi; void *
0x180004ed2  mov     rdx, r15; struct _SHACCT_LOGON_INFO *
0x180004ed5  mov     rcx, rbx; this
0x180004ed8  call    ?Init@CLoggedOnPropStore@@QEAAJPEBU_SHACCT_LOGON_INFO@@PEAX@Z; CLoggedOnPropStore::Init(_SHACCT_LOGON_INFO const *,void *)
0x180004edd  mov     edi, eax
0x180004edf  test    eax, eax
0x180004ee1  js      short loc_180004EFF
0x180004ee3  mov     rax, [rbx]
0x180004ee6  lea     r8, [rsp+4C0h+var_470]
0x180004eeb  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180004ef2  mov     rcx, rbx
0x180004ef5  mov     rax, [rax]
0x180004ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004efd  mov     edi, eax
0x180004eff  mov     rax, [rbx]
0x180004f02  mov     rcx, rbx
0x180004f05  mov     rax, [rax+10h]
0x180004f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f0e  mov     rcx, rsi; pv
0x180004f11  call    cs:__imp_CoTaskMemFree
0x180004f17  mov     ebx, dword ptr [rsp+4C0h+var_490]
0x180004f1b  xor     esi, esi
0x180004f1d  mov     rcx, [rsp+4C0h+var_478]; pMemory
0x180004f22  call    cs:__imp_WTSFreeMemory
0x180004f28  mov     rcx, [rsp+4C0h+ppBuffer]; pMemory
0x180004f2d  call    cs:__imp_WTSFreeMemory
0x180004f33  jmp     short loc_180004F50
0x180004f35  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004f3a  mov     edi, eax
0x180004f3c  mov     rcx, [rsp+4C0h+ppBuffer]; pMemory
0x180004f41  call    cs:__imp_WTSFreeMemory
0x180004f47  jmp     short loc_180004F50
0x180004f49  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004f4e  mov     edi, eax
0x180004f50  test    edi, edi
0x180004f52  js      short loc_180004F67
0x180004f54  mov     rax, [rsp+4C0h+var_470]
0x180004f59  mov     ebx, esi
0x180004f5b  mov     [r12], rax
0x180004f5f  inc     dword ptr [r13+0]
0x180004f63  mov     dword ptr [rsp+4C0h+var_490], ebx
0x180004f67  inc     dword ptr [r14+18h]
0x180004f6b  cmp     dword ptr [r13+0], 0
0x180004f70  jz      loc_180004D00
0x180004f76  mov     rdi, [rsp+4C0h+var_28]
0x180004f7e  mov     eax, ebx
0x180004f80  mov     rbx, [rsp+4C0h+arg_8]
0x180004f88  mov     r15, [rsp+4C0h+var_30]
0x180004f90  mov     rsi, [rsp+4A0h]
0x180004f98  mov     rcx, [rbp+3C0h+var_40]
0x180004f9f  xor     rcx, rsp; StackCookie
0x180004fa2  call    __security_check_cookie
0x180004fa7  add     rsp, 4A8h
0x180004fae  pop     r14
0x180004fb0  pop     r13
0x180004fb2  pop     r12
0x180004fb4  pop     rbp
0x180004fb5  retn
0x180004fb6  mov     eax, 80070057h
0x180004fbb  jmp     short loc_180004F98
```
