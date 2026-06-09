# ThemeServiceMain(ulong,ushort * *)

- ea: `0x18000db00`
- end: `0x18000dca5`
- name: `?ThemeServiceMain@@YAXKPEAPEAG@Z`
- size: `421`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x1800035e0`
- `0x180003f90`
- `0x180004430`
- `0x1800045a0`
- `0x18000ab04`
- `0x18000b3dc`
- `0x18000db00`
- `0x18000ecd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000db10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000db10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dc1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dc1d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db57`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db82`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db57`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db82`

## pseudocode

```c
void __fastcall ThemeServiceMain(__int64 a1, unsigned __int16 **a2)
{
  _BYTE *v2; // rax
  _BYTE *v3; // rbx
  CAPIConnection *v4; // rax
  volatile signed __int32 *v5; // rdi
  char *v6; // rax
  CService *v7; // rsi
  CCriticalSection *v8; // rbp
  _QWORD *v9; // rax

  EnterCriticalSection(&g_csThemeService);
  if ( (int)CThemeManagerAPIRequest::InitializeServerChangeNumber() >= 0 )
  {
    v2 = LocalAlloc(0, 0x10u);
    v3 = v2;
    if ( v2 )
    {
      v2[12] = 0;
      *((_DWORD *)v2 + 2) = 1;
      *(_QWORD *)v2 = &CThemeManagerAPIServer::`vftable';
      v4 = (CAPIConnection *)LocalAlloc(0, 0x70u);
      if ( v4 )
      {
        v5 = (volatile signed __int32 *)CAPIConnection::CAPIConnection(v4, (struct CServerAPI *)v3);
        if ( v5 )
        {
          v6 = (char *)LocalAlloc(0, 0x68u);
          v7 = (CService *)v6;
          if ( v6 )
          {
            *((_DWORD *)v6 + 2) = 1;
            v6[12] = 0;
            *(_QWORD *)v6 = &CService::`vftable';
            *((_QWORD *)v6 + 8) = L"Themes";
            *((_QWORD *)v6 + 3) = 0;
            *((_QWORD *)v6 + 9) = v5;
            *((_QWORD *)v6 + 10) = 0;
            *((_QWORD *)v6 + 11) = v3;
            *((_DWORD *)v6 + 4) = 1129730883;
            *((_OWORD *)v6 + 2) = 0;
            *(_OWORD *)(v6 + 44) = 0;
            _InterlockedAdd(v5 + 2, 1u);
            _InterlockedAdd((volatile signed __int32 *)v3 + 2, 1u);
            *(_QWORD *)v6 = &CThemeManagerService::`vftable';
            _InterlockedAdd(v5 + 2, 1u);
            v8 = CThemeManagerAPIRequest::s_pLock;
            CThemeManagerSessionData::s_pAPIConnection = (CCountedObject *)v5;
            CCriticalSection::Acquire(CThemeManagerAPIRequest::s_pLock);
            if ( !CThemeManagerAPIRequest::s_pSessionData )
            {
              v9 = HeapAlloc(s_hHeapToUse, 0, 0x10u);
              if ( v9 )
              {
                *v9 = 0;
                v9[1] = 0;
                CThemeManagerAPIRequest::s_pSessionData = v9;
              }
              else
              {
                CThemeManagerAPIRequest::s_pSessionData = 0;
              }
            }
            CCriticalSection::Release(v8);
            CService::Start(v7);
            CThemeManagerAPIRequest::ArrayTerminate();
            CCountedObject::Release(CThemeManagerSessionData::s_pAPIConnection);
            CThemeManagerSessionData::s_pAPIConnection = 0;
            CCountedObject::Release(v7);
          }
          CCountedObject::Release((CCountedObject *)v5);
        }
      }
      CCountedObject::Release((CCountedObject *)v3);
    }
  }
  LeaveCriticalSection(&g_csThemeService);
}

```

## disassembly

```asm
0x18000db00  push    rbx
0x18000db02  push    rbp
0x18000db03  push    rsi
0x18000db04  push    rdi
0x18000db05  sub     rsp, 28h
0x18000db09  lea     rcx, ?g_csThemeService@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000db10  call    cs:__imp_EnterCriticalSection
0x18000db16  call    ?InitializeServerChangeNumber@CThemeManagerAPIRequest@@SAJXZ; CThemeManagerAPIRequest::InitializeServerChangeNumber(void)
0x18000db1b  test    eax, eax
0x18000db1d  js      loc_18000DC8F
0x18000db23  mov     edx, 10h; uBytes
0x18000db28  xor     ecx, ecx; uFlags
0x18000db2a  call    cs:__imp_LocalAlloc
0x18000db30  mov     rbx, rax
0x18000db33  test    rax, rax
0x18000db36  jz      loc_18000DC8F
0x18000db3c  mov     ebp, 1
0x18000db41  mov     byte ptr [rax+0Ch], 0
0x18000db45  mov     [rax+8], ebp
0x18000db48  xor     ecx, ecx; uFlags
0x18000db4a  lea     rax, ??_7CThemeManagerAPIServer@@6B@; const CThemeManagerAPIServer::`vftable'
0x18000db51  mov     [rbx], rax
0x18000db54  lea     edx, [rbp+6Fh]; uBytes
0x18000db57  call    cs:__imp_LocalAlloc
0x18000db5d  test    rax, rax
0x18000db60  jz      loc_18000DC87
0x18000db66  mov     rdx, rbx; struct CServerAPI *
0x18000db69  mov     rcx, rax; this
0x18000db6c  call    ??0CAPIConnection@@QEAA@PEAVCServerAPI@@@Z; CAPIConnection::CAPIConnection(CServerAPI *)
0x18000db71  mov     rdi, rax
0x18000db74  test    rax, rax
0x18000db77  jz      loc_18000DC87
0x18000db7d  lea     edx, [rbp+67h]; uBytes
0x18000db80  xor     ecx, ecx; uFlags
0x18000db82  call    cs:__imp_LocalAlloc
0x18000db88  mov     rsi, rax
0x18000db8b  test    rax, rax
0x18000db8e  jz      loc_18000DC7F
0x18000db94  mov     [rax+8], ebp
0x18000db97  xorps   xmm0, xmm0
0x18000db9a  mov     byte ptr [rax+0Ch], 0
0x18000db9e  lea     rax, ??_7CService@@6B@; const CService::`vftable'
0x18000dba5  mov     [rsi], rax
0x18000dba8  lea     rax, ?s_szName@CThemeManagerService@@0QBGB; "Themes"
0x18000dbaf  mov     [rsi+40h], rax
0x18000dbb3  mov     qword ptr [rsi+18h], 0
0x18000dbbb  mov     [rsi+48h], rdi
0x18000dbbf  mov     qword ptr [rsi+50h], 0
0x18000dbc7  mov     [rsi+58h], rbx
0x18000dbcb  mov     dword ptr [rsi+10h], 43565343h
0x18000dbd2  movups  xmmword ptr [rsi+20h], xmm0
0x18000dbd6  movups  xmmword ptr [rsi+2Ch], xmm0
0x18000dbda  lock add [rdi+8], ebp
0x18000dbde  lock add [rbx+8], ebp
0x18000dbe2  lea     rax, ??_7CThemeManagerService@@6B@; const CThemeManagerService::`vftable'
0x18000dbe9  mov     [rsi], rax
0x18000dbec  lock add [rdi+8], ebp
0x18000dbf0  mov     rbp, cs:?s_pLock@CThemeManagerAPIRequest@@0PEAVCCriticalSection@@EA; CCriticalSection * CThemeManagerAPIRequest::s_pLock
0x18000dbf7  mov     rcx, rbp; this
0x18000dbfa  mov     cs:?s_pAPIConnection@CThemeManagerSessionData@@0PEAVCAPIConnection@@EA, rdi; CAPIConnection * CThemeManagerSessionData::s_pAPIConnection
0x18000dc01  call    ?Acquire@CCriticalSection@@QEAAXXZ; CCriticalSection::Acquire(void)
0x18000dc06  cmp     cs:?s_pSessionData@CThemeManagerAPIRequest@@0PEAVCDynamicCountedObjectArray@@EA, 0; CDynamicCountedObjectArray * CThemeManagerAPIRequest::s_pSessionData
0x18000dc0e  jnz     short loc_18000DC4B
0x18000dc10  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x18000dc17  xor     edx, edx; dwFlags
0x18000dc19  lea     r8d, [rdx+10h]; dwBytes
0x18000dc1d  call    cs:__imp_HeapAlloc
0x18000dc23  test    rax, rax
0x18000dc26  jz      short loc_18000DC40
0x18000dc28  mov     qword ptr [rax], 0
0x18000dc2f  mov     qword ptr [rax+8], 0
0x18000dc37  mov     cs:?s_pSessionData@CThemeManagerAPIRequest@@0PEAVCDynamicCountedObjectArray@@EA, rax; CDynamicCountedObjectArray * CThemeManagerAPIRequest::s_pSessionData
0x18000dc3e  jmp     short loc_18000DC4B
0x18000dc40  mov     cs:?s_pSessionData@CThemeManagerAPIRequest@@0PEAVCDynamicCountedObjectArray@@EA, 0; CDynamicCountedObjectArray * CThemeManagerAPIRequest::s_pSessionData
0x18000dc4b  mov     rcx, rbp; this
0x18000dc4e  call    ?Release@CCriticalSection@@QEAAXXZ; CCriticalSection::Release(void)
0x18000dc53  mov     rcx, rsi; this
0x18000dc56  call    ?Start@CService@@QEAAXXZ; CService::Start(void)
0x18000dc5b  call    ?ArrayTerminate@CThemeManagerAPIRequest@@SAJXZ; CThemeManagerAPIRequest::ArrayTerminate(void)
0x18000dc60  mov     rcx, cs:?s_pAPIConnection@CThemeManagerSessionData@@0PEAVCAPIConnection@@EA; this
0x18000dc67  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x18000dc6c  mov     rcx, rsi; this
0x18000dc6f  mov     cs:?s_pAPIConnection@CThemeManagerSessionData@@0PEAVCAPIConnection@@EA, 0; CAPIConnection * CThemeManagerSessionData::s_pAPIConnection
0x18000dc7a  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x18000dc7f  mov     rcx, rdi; this
0x18000dc82  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x18000dc87  mov     rcx, rbx; this
0x18000dc8a  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x18000dc8f  lea     rcx, ?g_csThemeService@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csThemeService
0x18000dc96  add     rsp, 28h
0x18000dc9a  pop     rdi
0x18000dc9b  pop     rsi
0x18000dc9c  pop     rbp
0x18000dc9d  pop     rbx
0x18000dc9e  jmp     cs:__imp_LeaveCriticalSection
```
