# CollectorService::SecondPhaseInitialize(void)

- ea: `0x180005ad0`
- end: `0x180005d01`
- name: `?SecondPhaseInitialize@CollectorService@@QEAAXXZ`
- size: `561`
- prototype: `void __fastcall(SubscriptionManager **this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x1800029d0`

## callees

- `0x180003430`
- `0x180003c10`
- `0x18000526c`
- `0x180005ad0`
- `0x1800062d4`
- `0x18000669c`
- `0x18000a938`
- `0x180014310`
- `0x18001483c`
- `0x180015b88`
- `0x180016380`
- `0x180016450`
- `0x18001ab58`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005cb6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005cb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005cce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005cce`

## pseudocode

```c
void __fastcall CollectorService::SecondPhaseInitialize(SubscriptionManager **this)
{
  SubscriptionManager **v1; // r12
  CollectorService *v2; // r15
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  const unsigned __int16 *v4; // rdx
  CredentialManager *v5; // rcx
  _DWORD *v6; // r14
  HKEY v7; // rdx
  const unsigned __int16 *v8; // r8
  void *v9; // rcx
  HKEY **CurrentReader; // r13
  HKEY *v11; // rdi
  SubscriptionConfigSnapshot *v12; // rax
  SubscriptionConfigSnapshot *v13; // rax
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rdx
  wmi::Exception *v16; // rbx
  char v17; // al
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // r9d
  unsigned __int16 **v21; // rax
  const wchar_t *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // [rsp+0h] [rbp-198h] BYREF
  int v25; // [rsp+40h] [rbp-158h] BYREF
  HKEY *v26; // [rsp+48h] [rbp-150h] BYREF
  CollectorService *v27; // [rsp+50h] [rbp-148h]
  SubscriptionConfigSnapshot *v28; // [rsp+58h] [rbp-140h] BYREF
  _BYTE v29[8]; // [rsp+60h] [rbp-138h] BYREF
  wmi::Exception *v30; // [rsp+68h] [rbp-130h] BYREF
  struct _RTL_CRITICAL_SECTION *v31; // [rsp+70h] [rbp-128h]
  _DWORD *v32; // [rsp+80h] [rbp-118h]
  __int128 v33; // [rsp+88h] [rbp-110h] BYREF
  unsigned __int16 *v34[3]; // [rsp+98h] [rbp-100h] BYREF
  unsigned __int64 v35; // [rsp+B0h] [rbp-E8h]
  _BYTE v36[56]; // [rsp+C0h] [rbp-D8h] BYREF
  __int64 v37; // [rsp+F8h] [rbp-A0h]
  const wchar_t *v38; // [rsp+130h] [rbp-68h] BYREF
  int v39; // [rsp+138h] [rbp-60h]
  int v40; // [rsp+13Ch] [rbp-5Ch]
  const wchar_t *v41; // [rsp+140h] [rbp-58h]
  __int64 v42; // [rsp+148h] [rbp-50h]
  int *v43; // [rsp+150h] [rbp-48h]
  __int64 v44; // [rsp+158h] [rbp-40h]

  v1 = this;
  v2 = (CollectorService *)this;
  v27 = (CollectorService *)this;
  v3 = (struct _RTL_CRITICAL_SECTION *)(this + 8);
  v31 = (struct _RTL_CRITICAL_SECTION *)(this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 8));
  v6 = (_DWORD *)((char *)v2 + 104);
  if ( *((_DWORD *)v2 + 26) != 3 )
  {
    *v6 = 1;
    CredentialManager::BuildStore(v5, v4);
    SubscriptionConfigEnumerator::SubscriptionConfigEnumerator((SubscriptionConfigEnumerator *)v36, v7, v8);
    if ( ConfigEnumerator::MoveFirst((ConfigEnumerator *)v36) )
    {
      v32 = (_DWORD *)((char *)v2 + 104);
      do
      {
        v35 = 7;
        v34[2] = 0;
        LOWORD(v34[0]) = 0;
        std::wstring::assign((__int64)v34, v37);
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          v26 = 0;
          CurrentReader = (HKEY **)SubscriptionConfigEnumerator::GetCurrentReader((__int64)v36, v29);
          wmi::AutoRef<AbstractEventProcessor>::Release((wmi::RefBase **)&v26);
          v11 = *CurrentReader;
          v26 = *CurrentReader;
          *CurrentReader = 0;
          wmi::AutoRef<AbstractEventProcessor>::Release((wmi::RefBase **)v29);
          v33 = 0;
          v12 = (SubscriptionConfigSnapshot *)operator new(0x20u);
          v28 = v12;
          if ( v12 )
            v13 = SubscriptionConfigSnapshot::SubscriptionConfigSnapshot(
                    v12,
                    v11,
                    0,
                    (struct tag_EcRpcMetadataPropertyList *)&v33,
                    1,
                    1,
                    1);
          else
            v13 = 0;
          v28 = v13;
          if ( v13 )
            _InterlockedIncrement((volatile signed __int32 *)v13 + 2);
          v14 = (const unsigned __int16 *)v34;
          if ( v35 >= 8 )
            v14 = v34[0];
          SubscriptionManager::AssertSubscription(*v1, v14, 0, (const struct tag_EcRpcMetadataPropertyList **)v13 + 2);
          wmi::AutoRef<AbstractEventProcessor>::Release(&v28);
          wmi::AutoRef<AbstractEventProcessor>::Release((wmi::RefBase **)&v26);
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &wmi::Exception `RTTI Type Descriptor', &v30) )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              v16 = v30;
            }
            else
            {
              v16 = v30;
              v17 = (**(__int64 (__fastcall ***)(wmi::Exception *))v30)(v30);
              v20 = (unsigned int)&v24 + 152;
              if ( v35 >= 8 )
                v20 = (unsigned int)v34[0];
              WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, v20, v17);
            }
            v25 = (**(__int64 (__fastcall ***)(wmi::Exception *))v16)(v16);
            v21 = v34;
            if ( v35 >= 8 )
              v21 = (unsigned __int16 **)v34[0];
            v22 = &word_180026AD8;
            if ( v21 )
              v22 = (const wchar_t *)v21;
            v23 = -1;
            do
              ++v23;
            while ( v22[v23] );
            v38 = v22;
            v39 = 2 * v23 + 2;
            v40 = 0;
            v41 = &word_180026AD8;
            v42 = 2;
            v43 = &v25;
            v44 = 4;
            (*(void (__fastcall **)(_QWORD, __int64 *, __int64, const wchar_t **))(**((_QWORD **)v27 + 2) + 8LL))(
              *((_QWORD *)v27 + 2),
              EVTCOLL_SUBSCRIPTION_ACTIVATION_ERROR,
              3,
              &v38);
            v3 = v31;
            v2 = v27;
            v1 = (SubscriptionManager **)v27;
            v6 = v32;
            __eh34_try_continuation(0, &wmi::Exception `RTTI Type Descriptor', &loc_180005C6D);
          }
        }
        LOBYTE(v15) = 1;
        std::wstring::_Tidy(v34, v15, 0);
      }
      while ( ConfigEnumerator::MoveNext((ConfigEnumerator *)v36) );
      v9 = (void *)*((_QWORD *)v2 + 14);
    }
    else
    {
      v9 = (void *)*((_QWORD *)v2 + 14);
    }
    *v6 = 2;
    SetEvent(v9);
    ((void (__fastcall *)(ConfigEnumerator *))ConfigEnumerator::~ConfigEnumerator)((ConfigEnumerator *)v36);
  }
  LeaveCriticalSection(v3);
}

```

## disassembly

```asm
0x180005ad0  mov     [rsp+arg_8], rbx
0x180005ad5  mov     [rsp+arg_10], rsi
0x180005ada  push    rdi
0x180005adb  push    r12
0x180005add  push    r13
0x180005adf  push    r14
0x180005ae1  push    r15
0x180005ae3  sub     rsp, 170h
0x180005aea  mov     rax, cs:__security_cookie
0x180005af1  xor     rax, rsp
0x180005af4  mov     [rsp+198h+var_38], rax
0x180005afc  mov     r12, rcx
0x180005aff  mov     r15, rcx
0x180005b02  mov     [rsp+198h+var_148], rcx
0x180005b07  lea     rbx, [rcx+40h]
0x180005b0b  mov     [rsp+198h+var_128], rbx
0x180005b10  mov     rcx, rbx; lpCriticalSection
0x180005b13  call    cs:__imp_EnterCriticalSection
0x180005b19  nop
0x180005b1a  lea     r14, [r15+68h]
0x180005b1e  cmp     dword ptr [r14], 3
0x180005b22  jz      loc_180005CCB
0x180005b28  mov     dword ptr [r14], 1
0x180005b2f  call    ?BuildStore@CredentialManager@@QEAAXPEBG@Z; CredentialManager::BuildStore(ushort const *)
0x180005b34  lea     rcx, [rsp+198h+var_D8]; this
0x180005b3c  call    ??0SubscriptionConfigEnumerator@@QEAA@PEAUHKEY__@@PEBG@Z; SubscriptionConfigEnumerator::SubscriptionConfigEnumerator(HKEY__ *,ushort const *)
0x180005b41  nop
0x180005b42  lea     rcx, [rsp+198h+var_D8]; this
0x180005b4a  call    ?MoveFirst@ConfigEnumerator@@UEAA_NXZ; ConfigEnumerator::MoveFirst(void)
0x180005b4f  xor     esi, esi
0x180005b51  test    al, al
0x180005b53  jnz     short loc_180005B5E
0x180005b55  mov     rcx, [r15+70h]
0x180005b59  jmp     loc_180005CAF
0x180005b5e  mov     [rsp+198h+var_118], r14
0x180005b66  mov     [rsp+198h+var_E8], 7
0x180005b72  mov     [rsp+198h+var_F0], rsi
0x180005b7a  mov     word ptr [rsp+198h+var_100], si
0x180005b82  mov     rdx, [rsp+198h+var_A0]
0x180005b8a  lea     rcx, [rsp+198h+var_100]
0x180005b92  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180005b97  nop
0x180005b98  mov     [rsp+198h+var_150], rsi
0x180005b9d  lea     rdx, [rsp+198h+var_138]
0x180005ba2  lea     rcx, [rsp+198h+var_D8]
0x180005baa  call    ?GetCurrentReader@SubscriptionConfigEnumerator@@QEAA?AV?$AutoRef@VSubscriptionConfigReader@@@wmi@@XZ; SubscriptionConfigEnumerator::GetCurrentReader(void)
0x180005baf  mov     r13, rax
0x180005bb2  lea     rcx, [rsp+198h+var_150]
0x180005bb7  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x180005bbc  mov     rdi, [r13+0]
0x180005bc0  mov     [rsp+198h+var_150], rdi
0x180005bc5  mov     [r13+0], rsi
0x180005bc9  lea     rcx, [rsp+198h+var_138]
0x180005bce  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x180005bd3  xorps   xmm0, xmm0
0x180005bd6  movups  [rsp+198h+var_110], xmm0
0x180005bde  mov     ecx, 20h ; ' '; dwBytes
0x180005be3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005be8  mov     [rsp+198h+var_140], rax
0x180005bed  test    rax, rax
0x180005bf0  jz      short loc_180005C19
0x180005bf2  mov     [rsp+198h+var_168], 1; bool
0x180005bf7  mov     [rsp+198h+var_170], 1; bool
0x180005bfc  mov     [rsp+198h+var_178], 1; bool
0x180005c01  lea     r9, [rsp+198h+var_110]; struct tag_EcRpcMetadataPropertyList *
0x180005c09  xor     r8d, r8d; unsigned __int16 *
0x180005c0c  mov     rdx, rdi; struct SubscriptionConfigReader *
0x180005c0f  mov     rcx, rax; this
0x180005c12  call    ??0SubscriptionConfigSnapshot@@QEAA@AEBVSubscriptionConfigReader@@PEBGAEAUtag_EcRpcMetadataPropertyList@@_N33@Z; SubscriptionConfigSnapshot::SubscriptionConfigSnapshot(SubscriptionConfigReader const &,ushort const *,tag_EcRpcMetadataPropertyList &,bool,bool,bool)
0x180005c17  jmp     short loc_180005C1C
0x180005c19  mov     rax, rsi
0x180005c1c  mov     [rsp+198h+var_140], rax
0x180005c21  test    rax, rax
0x180005c24  jz      short loc_180005C2A
0x180005c26  lock inc dword ptr [rax+8]
0x180005c2a  lea     rdx, [rsp+198h+var_100]
0x180005c32  cmp     [rsp+198h+var_E8], 8
0x180005c3b  cmovnb  rdx, [rsp+198h+var_100]; unsigned __int16 *
0x180005c44  lea     r9, [rax+10h]; struct SubscriptionReadData *
0x180005c48  xor     r8d, r8d; unsigned __int16 *
0x180005c4b  mov     rcx, [r12]; this
0x180005c4f  call    ?AssertSubscription@SubscriptionManager@@QEAAXPEBG0AEBVSubscriptionReadData@@@Z; SubscriptionManager::AssertSubscription(ushort const *,ushort const *,SubscriptionReadData const &)
0x180005c54  nop
0x180005c55  lea     rcx, [rsp+198h+var_140]
0x180005c5a  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x180005c5f  nop
0x180005c60  lea     rcx, [rsp+198h+var_150]
0x180005c65  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x180005c6a  nop
0x180005c6b  jmp     short loc_180005C84
0x180005c6d  xor     esi, esi
0x180005c6f  mov     rbx, [rsp+198h+var_128]
0x180005c74  mov     r15, [rsp+198h+var_148]
0x180005c79  mov     r12, r15
0x180005c7c  mov     r14, [rsp+198h+var_118]
0x180005c84  xor     r8d, r8d
0x180005c87  mov     dl, 1
0x180005c89  lea     rcx, [rsp+198h+var_100]
0x180005c91  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180005c96  lea     rcx, [rsp+198h+var_D8]; this
0x180005c9e  call    ?MoveNext@ConfigEnumerator@@UEAA_NXZ; ConfigEnumerator::MoveNext(void)
0x180005ca3  test    al, al
0x180005ca5  jnz     loc_180005B66
0x180005cab  mov     rcx, [r15+70h]; hEvent
0x180005caf  mov     dword ptr [r14], 2
0x180005cb6  call    cs:__imp_SetEvent
0x180005cbc  nop
0x180005cbd  lea     rcx, [rsp+198h+var_D8]; this
0x180005cc5  call    ??1ConfigEnumerator@@UEAA@XZ; ConfigEnumerator::~ConfigEnumerator(void)
0x180005cca  nop
0x180005ccb  mov     rcx, rbx; lpCriticalSection
0x180005cce  call    cs:__imp_LeaveCriticalSection
0x180005cd4  mov     rcx, [rsp+198h+var_38]
0x180005cdc  xor     rcx, rsp; StackCookie
0x180005cdf  call    __security_check_cookie
0x180005ce4  lea     r11, [rsp+198h+var_28]
0x180005cec  mov     rbx, [r11+38h]
0x180005cf0  mov     rsi, [r11+40h]
0x180005cf4  mov     rsp, r11
0x180005cf7  pop     r15
0x180005cf9  pop     r14
0x180005cfb  pop     r13
0x180005cfd  pop     r12
0x180005cff  pop     rdi
0x180005d00  retn
```
