# GetSyncEngine(_GUID const &,void * *)

- ea: `0x18003e1e8`
- end: `0x18003e3c7`
- name: `?GetSyncEngine@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `479`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d2c4`
- `0x18003df3c`
- `0x1800b7c14`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x180022ee0`
- `0x18003e1e8`
- `0x180058490`
- `0x18006fa00`
- `0x180079030`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e20e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e2d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e20e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e2d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e241`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e317`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e241`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e317`
- `WinSync!__imp_CreateSyncServiceInstance` at `0x18003e28b`
- `WinSync!__imp_CreateSyncServiceInstance` at `0x18003e28b`

## string_xrefs

- `0x18003e2ff`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\globalclean.h`

## pseudocode

```c
__int64 __fastcall GetSyncEngine(const struct _GUID *a1, void **a2)
{
  __int64 (__fastcall ***v4)(_QWORD, const struct _GUID *, void **); // rcx
  int v5; // eax
  __int64 v6; // r8
  unsigned int v7; // ebx
  int IsShuttingDown; // eax
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // r8
  _QWORD *v13; // rax
  __int64 v14; // r9
  _QWORD *v15; // rcx
  _RTL_CRITICAL_SECTION *v16; // [rsp+30h] [rbp-38h] BYREF
  char v17; // [rsp+38h] [rbp-30h]
  __int64 v18; // [rsp+78h] [rbp+10h] BYREF

  *a2 = 0;
  v16 = &g_csGlobalLock;
  EnterCriticalSection(&g_csGlobalLock);
  v4 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))qword_18010DB60;
  v17 = 1;
  if ( !qword_18010DB60 )
  {
    IsShuttingDown = FailIfServiceIsShuttingDown();
    v7 = IsShuttingDown;
    if ( IsShuttingDown < 0 )
    {
      Log_UnistoreHREvent_6((unsigned int)IsShuttingDown, 1, v10, 208);
    }
    else
    {
      v18 = 0;
      v11 = CreateSyncServiceInstance(&GUID_8ed97ec6_e77c_452e_9866_3747bc305db5, &v18);
      v7 = v11;
      if ( v11 < 0 )
      {
        v14 = 212;
      }
      else
      {
        v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 24LL))(v18, qword_1800DC290);
        v7 = v11;
        if ( v11 >= 0 )
        {
          qword_18010DB60 = v18;
          v18 = 0;
          EnterCriticalSection(&g_us_cleanup);
          v13 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
          if ( v13 )
          {
            v13[2] = USReleaseObject;
            v13[3] = &qword_18010DB60;
            v15 = Block;
            v13[1] = Block;
            *v13 = &qword_18010C2A8;
            *v15 = v13;
            ++qword_18010C2B8;
            Block = v13;
          }
          else
          {
            Log_UnistoreHREvent_0(
              2147942414LL,
              0,
              "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\globalclean.h",
              111);
          }
          LeaveCriticalSection(&g_us_cleanup);
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          v4 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))qword_18010DB60;
          goto LABEL_2;
        }
        v14 = 213;
      }
      Log_UnistoreHREvent_6((unsigned int)v11, 1, v12, v14);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v18);
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v16);
    return v7;
  }
LABEL_2:
  v5 = (**v4)(v4, a1, a2);
  v7 = v5;
  if ( v5 < 0 )
    Log_UnistoreHREvent_6((unsigned int)v5, 1, v6, 219);
  else
    v7 = 0;
  LeaveCriticalSection(&g_csGlobalLock);
  return v7;
}

```

## disassembly

```asm
0x18003e1e8  push    rbx
0x18003e1ea  push    rsi
0x18003e1eb  push    rdi
0x18003e1ec  push    r15
0x18003e1ee  sub     rsp, 48h
0x18003e1f2  lea     r15, ?g_csGlobalLock@@3VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection g_csGlobalLock
0x18003e1f9  mov     qword ptr [rdx], 0
0x18003e200  mov     rsi, rcx
0x18003e203  mov     [rsp+68h+var_38], r15
0x18003e208  mov     rcx, r15; lpCriticalSection
0x18003e20b  mov     rdi, rdx
0x18003e20e  call    cs:__imp_EnterCriticalSection
0x18003e214  mov     rcx, cs:qword_18010DB60
0x18003e21b  mov     [rsp+68h+var_30], 1
0x18003e220  test    rcx, rcx
0x18003e223  jz      short loc_18003E267
0x18003e225  mov     rax, [rcx]
0x18003e228  mov     r8, rdi
0x18003e22b  mov     rdx, rsi
0x18003e22e  mov     rax, [rax]
0x18003e231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e236  mov     ebx, eax
0x18003e238  test    eax, eax
0x18003e23a  js      short loc_18003E253
0x18003e23c  xor     ebx, ebx
0x18003e23e  mov     rcx, r15; lpCriticalSection
0x18003e241  call    cs:__imp_LeaveCriticalSection
0x18003e247  mov     eax, ebx
0x18003e249  add     rsp, 48h
0x18003e24d  pop     r15
0x18003e24f  pop     rdi
0x18003e250  pop     rsi
0x18003e251  pop     rbx
0x18003e252  retn
0x18003e253  mov     edx, 1
0x18003e258  mov     r9d, 0DBh
0x18003e25e  mov     ecx, eax
0x18003e260  call    Log_UnistoreHREvent_6
0x18003e265  jmp     short loc_18003E23E
0x18003e267  call    ?FailIfServiceIsShuttingDown@@YAJXZ; FailIfServiceIsShuttingDown(void)
0x18003e26c  mov     ebx, eax
0x18003e26e  test    eax, eax
0x18003e270  js      loc_18003E33F
0x18003e276  lea     rdx, [rsp+68h+arg_8]
0x18003e27b  mov     [rsp+68h+arg_8], 0
0x18003e284  lea     rcx, _GUID_8ed97ec6_e77c_452e_9866_3747bc305db5
0x18003e28b  call    cs:__imp_CreateSyncServiceInstance
0x18003e291  mov     ebx, eax
0x18003e293  test    eax, eax
0x18003e295  js      loc_18003E353
0x18003e29b  mov     rcx, [rsp+68h+arg_8]
0x18003e2a0  lea     rdx, qword_1800DC290
0x18003e2a7  mov     rax, [rcx]
0x18003e2aa  mov     rax, [rax+18h]
0x18003e2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2b3  mov     ebx, eax
0x18003e2b5  test    eax, eax
0x18003e2b7  js      loc_18003E35B
0x18003e2bd  mov     rax, [rsp+68h+arg_8]
0x18003e2c2  lea     rcx, ?g_us_cleanup@@3VGlobalCleanup@@A; lpCriticalSection
0x18003e2c9  mov     cs:qword_18010DB60, rax
0x18003e2d0  mov     [rsp+68h+arg_8], 0
0x18003e2d9  call    cs:__imp_EnterCriticalSection
0x18003e2df  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003e2e6  mov     ecx, 20h ; ' '; unsigned __int64
0x18003e2eb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e2f0  test    rax, rax
0x18003e2f3  jnz     loc_18003E386
0x18003e2f9  lea     r9d, [rax+6Fh]
0x18003e2fd  xor     edx, edx
0x18003e2ff  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x18003e306  mov     ecx, 8007000Eh
0x18003e30b  call    Log_UnistoreHREvent_0
0x18003e310  lea     rcx, ?g_us_cleanup@@3VGlobalCleanup@@A; lpCriticalSection
0x18003e317  call    cs:__imp_LeaveCriticalSection
0x18003e31d  mov     rcx, [rsp+68h+arg_8]
0x18003e322  test    rcx, rcx
0x18003e325  jz      short loc_18003E333
0x18003e327  mov     rax, [rcx]
0x18003e32a  mov     rax, [rax+10h]
0x18003e32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e333  mov     rcx, cs:qword_18010DB60
0x18003e33a  jmp     loc_18003E225
0x18003e33f  mov     edx, 1
0x18003e344  mov     r9d, 0D0h
0x18003e34a  mov     ecx, eax
0x18003e34c  call    Log_UnistoreHREvent_6
0x18003e351  jmp     short loc_18003E377
0x18003e353  mov     r9d, 0D4h
0x18003e359  jmp     short loc_18003E361
0x18003e35b  mov     r9d, 0D5h
0x18003e361  mov     edx, 1
0x18003e366  mov     ecx, eax
0x18003e368  call    Log_UnistoreHREvent_6
0x18003e36d  lea     rcx, [rsp+68h+arg_8]; void *
0x18003e372  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18003e377  lea     rcx, [rsp+68h+var_38]
0x18003e37c  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18003e381  jmp     loc_18003E247
0x18003e386  lea     rcx, ?USReleaseObject@@YAX_K@Z; USReleaseObject(unsigned __int64)
0x18003e38d  mov     [rax+10h], rcx
0x18003e391  lea     rdx, qword_18010C2A8
0x18003e398  lea     rcx, qword_18010DB60
0x18003e39f  mov     [rax+18h], rcx
0x18003e3a3  mov     rcx, cs:Block
0x18003e3aa  mov     [rax+8], rcx
0x18003e3ae  mov     [rax], rdx
0x18003e3b1  mov     [rcx], rax
0x18003e3b4  inc     cs:qword_18010C2B8
0x18003e3bb  mov     cs:Block, rax
0x18003e3c2  jmp     loc_18003E310
```
