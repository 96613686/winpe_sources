# CollectorService::GetSubscriptionNames(ulong,ulong &,ushort * * &)

- ea: `0x180004434`
- end: `0x180004602`
- name: `?GetSubscriptionNames@CollectorService@@QEAAXKAEAKAEAPEAPEAG@Z`
- size: `462`
- prototype: `void __fastcall(CollectorService *this, __int64, unsigned int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x1800035e0`

## callees

- `0x180003430`
- `0x180003ae0`
- `0x180003c10`
- `0x180004434`
- `0x180005d08`
- `0x180005d7c`
- `0x1800062d4`
- `0x180006370`
- `0x18000669c`
- `0x180006898`
- `0x180014310`
- `0x180016380`
- `0x180016450`
- `0x18001fe13`
- `0x18001fe50`

## pseudocode

```c
void __fastcall CollectorService::GetSubscriptionNames(
        CollectorService *this,
        __int64 a2,
        unsigned int *a3,
        unsigned __int16 ***a4)
{
  unsigned int *v5; // r15
  HKEY v6; // rdx
  const unsigned __int16 *v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r13
  unsigned __int64 v10; // rbx
  unsigned __int16 **v11; // rax
  unsigned __int64 v12; // rsi
  __int64 *v13; // rdi
  _QWORD *v14; // r12
  unsigned __int64 v15; // rcx
  SIZE_T v16; // rax
  __int128 v17; // [rsp+20h] [rbp-A9h] BYREF
  __int64 v18; // [rsp+30h] [rbp-99h]
  unsigned int *v19; // [rsp+38h] [rbp-91h]
  __int16 v20; // [rsp+40h] [rbp-89h] BYREF
  void (*v21)(unsigned int, unsigned __int16 **, bool); // [rsp+48h] [rbp-81h]
  unsigned __int64 v22; // [rsp+50h] [rbp-79h]
  __int64 v23; // [rsp+58h] [rbp-71h]
  char v24; // [rsp+60h] [rbp-69h]
  _BYTE v25[56]; // [rsp+70h] [rbp-59h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-21h]

  v5 = a3;
  v19 = a3;
  CollectorService::WaitForInit(this);
  *v5 = 0;
  *a4 = 0;
  SubscriptionConfigEnumerator::SubscriptionConfigEnumerator((SubscriptionConfigEnumerator *)v25, v6, v7);
  v17 = 0;
  v18 = 0;
  if ( ConfigEnumerator::MoveFirst((ConfigEnumerator *)v25) )
  {
    do
    {
      v23 = 7;
      v22 = 0;
      v20 = 0;
      std::wstring::assign(&v20, v26);
      std::vector<std::wstring>::push_back(&v17, &v20);
      LOBYTE(v8) = 1;
      std::wstring::_Tidy(&v20, v8, 0);
    }
    while ( ConfigEnumerator::MoveNext((ConfigEnumerator *)v25) );
    v9 = v17;
    v10 = (__int64)(*((_QWORD *)&v17 + 1) - v17) >> 5;
    v11 = (unsigned __int16 **)operator new(saturated_mul(v10, 8u));
    *a4 = v11;
    memset_0(v11, 0, 8 * v10);
    LOBYTE(v20) = 0;
    v21 = CleanupStringVector;
    v22 = v10;
    v23 = (__int64)*a4;
    v24 = 0;
    v12 = 0;
    if ( v10 )
    {
      do
      {
        v13 = (__int64 *)(v9 + 32 * v12);
        v14 = v13 + 2;
        v15 = v13[2] + 1;
        v16 = 2 * v15;
        if ( !is_mul_ok(v15, 2u) )
          v16 = -1;
        (*a4)[v12] = (unsigned __int16 *)operator new(v16);
        if ( (unsigned __int64)v13[3] >= 8 )
          v13 = (__int64 *)*v13;
        StringCchCopyW((*a4)[v12++], *v14 + 1LL, (const unsigned __int16 *)v13);
      }
      while ( v12 < v10 );
      v5 = v19;
    }
    LOBYTE(v20) = 1;
    *v5 = v10;
    wmi::ScopeGuardImpl3<void (*)(unsigned long,unsigned short * *,bool),unsigned __int64,unsigned short * *,bool>::~ScopeGuardImpl3<void (*)(unsigned long,unsigned short * *,bool),unsigned __int64,unsigned short * *,bool>(&v20);
  }
  std::vector<std::wstring>::_Tidy(&v17);
  ConfigEnumerator::~ConfigEnumerator((ConfigEnumerator *)v25);
}

```

## disassembly

```asm
0x180004434  mov     [rsp-8+arg_8], rbx
0x180004439  push    rbp
0x18000443a  push    rsi
0x18000443b  push    rdi
0x18000443c  push    r12
0x18000443e  push    r13
0x180004440  push    r14
0x180004442  push    r15
0x180004444  lea     rbp, [rsp-27h]
0x180004449  sub     rsp, 0F0h
0x180004450  mov     rax, cs:__security_cookie
0x180004457  xor     rax, rsp
0x18000445a  mov     [rbp+57h+var_40], rax
0x18000445e  mov     r14, r9
0x180004461  mov     r15, r8
0x180004464  mov     [rsp+120h+var_E8], r8
0x180004469  call    ?WaitForInit@CollectorService@@AEAAXXZ; CollectorService::WaitForInit(void)
0x18000446e  xor     edi, edi
0x180004470  mov     [r15], edi
0x180004473  mov     [r14], rdi
0x180004476  lea     rcx, [rbp+57h+var_B0]; this
0x18000447a  call    ??0SubscriptionConfigEnumerator@@QEAA@PEAUHKEY__@@PEBG@Z; SubscriptionConfigEnumerator::SubscriptionConfigEnumerator(HKEY__ *,ushort const *)
0x18000447f  nop
0x180004480  xorps   xmm0, xmm0
0x180004483  movdqu  [rsp+120h+var_100], xmm0
0x180004489  mov     [rsp+120h+var_F0], rdi
0x18000448e  lea     rcx, [rbp+57h+var_B0]; this
0x180004492  call    ?MoveFirst@ConfigEnumerator@@UEAA_NXZ; ConfigEnumerator::MoveFirst(void)
0x180004497  test    al, al
0x180004499  jz      loc_1800045C7
0x18000449f  mov     [rbp+57h+var_C8], 7
0x1800044a7  mov     [rbp+57h+var_D0], rdi
0x1800044ab  mov     [rsp+120h+var_E0], di
0x1800044b0  mov     rdx, [rbp+57h+var_78]
0x1800044b4  lea     rcx, [rsp+120h+var_E0]
0x1800044b9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800044be  lea     rdx, [rsp+120h+var_E0]
0x1800044c3  lea     rcx, [rsp+120h+var_100]
0x1800044c8  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x1800044cd  nop
0x1800044ce  xor     r8d, r8d
0x1800044d1  mov     dl, 1
0x1800044d3  lea     rcx, [rsp+120h+var_E0]
0x1800044d8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800044dd  lea     rcx, [rbp+57h+var_B0]; this
0x1800044e1  call    ?MoveNext@ConfigEnumerator@@UEAA_NXZ; ConfigEnumerator::MoveNext(void)
0x1800044e6  test    al, al
0x1800044e8  jnz     short loc_18000449F
0x1800044ea  mov     rbx, qword ptr [rsp+120h+var_100+8]
0x1800044ef  mov     r13, qword ptr [rsp+120h+var_100]
0x1800044f4  sub     rbx, r13
0x1800044f7  sar     rbx, 5
0x1800044fb  mov     eax, 8
0x180004500  mul     rbx
0x180004503  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000450a  cmovb   rax, rcx
0x18000450e  mov     rcx, rax; dwBytes
0x180004511  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004516  mov     [r14], rax
0x180004519  lea     r8, ds:0[rbx*8]; Size
0x180004521  xor     edx, edx; Val
0x180004523  mov     rcx, rax; void *
0x180004526  call    memset_0
0x18000452b  mov     byte ptr [rsp+120h+var_E0], dil
0x180004530  lea     rax, ?CleanupStringVector@@YAXKPEAPEAG_N@Z; CleanupStringVector(ulong,ushort * *,bool)
0x180004537  mov     [rsp+120h+var_D8], rax
0x18000453c  mov     [rbp+57h+var_D0], rbx
0x180004540  mov     rax, [r14]
0x180004543  mov     [rbp+57h+var_C8], rax
0x180004547  mov     [rbp+57h+var_C0], dil
0x18000454b  mov     rsi, rdi
0x18000454e  test    rbx, rbx
0x180004551  jz      short loc_1800045B4
0x180004553  or      r15, 0FFFFFFFFFFFFFFFFh
0x180004557  mov     rdi, rsi
0x18000455a  shl     rdi, 5
0x18000455e  add     rdi, r13
0x180004561  lea     r12, [rdi+10h]
0x180004565  mov     rcx, [r12]
0x180004569  inc     rcx
0x18000456c  mov     eax, 2
0x180004571  mul     rcx
0x180004574  cmovb   rax, r15
0x180004578  mov     rcx, rax; dwBytes
0x18000457b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004580  mov     rcx, [r14]
0x180004583  mov     [rcx+rsi*8], rax
0x180004587  cmp     qword ptr [rdi+18h], 8
0x18000458c  jb      short loc_180004591
0x18000458e  mov     rdi, [rdi]
0x180004591  mov     rdx, [r12]
0x180004595  inc     rdx; unsigned __int64
0x180004598  mov     rcx, [r14]
0x18000459b  mov     r8, rdi; unsigned __int16 *
0x18000459e  mov     rcx, [rcx+rsi*8]; unsigned __int16 *
0x1800045a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800045a7  inc     rsi
0x1800045aa  cmp     rsi, rbx
0x1800045ad  jb      short loc_180004557
0x1800045af  mov     r15, [rsp+120h+var_E8]
0x1800045b4  mov     byte ptr [rsp+120h+var_E0], 1
0x1800045b9  mov     [r15], ebx
0x1800045bc  lea     rcx, [rsp+120h+var_E0]
0x1800045c1  call    ??1?$ScopeGuardImpl3@P6AXKPEAPEAG_N@Z_KPEAPEAG_N@wmi@@QEAA@XZ; wmi::ScopeGuardImpl3<void (*)(ulong,ushort * *,bool),unsigned __int64,ushort * *,bool>::~ScopeGuardImpl3<void (*)(ulong,ushort * *,bool),unsigned __int64,ushort * *,bool>(void)
0x1800045c6  nop
0x1800045c7  lea     rcx, [rsp+120h+var_100]
0x1800045cc  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800045d1  nop
0x1800045d2  lea     rcx, [rbp+57h+var_B0]; this
0x1800045d6  call    ??1ConfigEnumerator@@UEAA@XZ; ConfigEnumerator::~ConfigEnumerator(void)
0x1800045db  mov     rcx, [rbp+57h+var_40]
0x1800045df  xor     rcx, rsp; StackCookie
0x1800045e2  call    __security_check_cookie
0x1800045e7  mov     rbx, [rsp+120h+arg_8]
0x1800045ef  add     rsp, 0F0h
0x1800045f6  pop     r15
0x1800045f8  pop     r14
0x1800045fa  pop     r13
0x1800045fc  pop     r12
0x1800045fe  pop     rdi
0x1800045ff  pop     rsi
0x180004600  pop     rbp
0x180004601  retn
```
