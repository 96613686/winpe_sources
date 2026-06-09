# CollectorService::GetSubscriptionRunTimeEventSources(ushort const *,ulong &,ushort * * &)

- ea: `0x180004608`
- end: `0x180004757`
- name: `?GetSubscriptionRunTimeEventSources@CollectorService@@QEAAXPEBGAEAKAEAPEAPEAG@Z`
- size: `335`
- prototype: `void __fastcall(CollectorService *__hidden this, const unsigned __int16 *, unsigned int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180003620`

## callees

- `0x180003430`
- `0x180003ae0`
- `0x180004608`
- `0x180005d08`
- `0x180005d7c`
- `0x180006370`
- `0x18000d15c`
- `0x18001fe13`

## pseudocode

```c
void __fastcall CollectorService::GetSubscriptionRunTimeEventSources(
        CollectorService *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 ***a4)
{
  unsigned __int16 **v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned __int64 v10; // rdi
  __int64 v11; // rbx
  unsigned __int64 v12; // rcx
  SIZE_T v13; // rax
  __int64 v14; // rdx
  const unsigned __int16 *v15; // r8
  __int64 v16; // [rsp+20h] [rbp-48h] BYREF
  __int64 v17; // [rsp+28h] [rbp-40h]
  char v18[8]; // [rsp+38h] [rbp-30h] BYREF
  void (*v19)(unsigned int, unsigned __int16 **, bool); // [rsp+40h] [rbp-28h]
  __int64 v20; // [rsp+48h] [rbp-20h]
  __int64 v21; // [rsp+50h] [rbp-18h]
  char v22; // [rsp+58h] [rbp-10h]

  CollectorService::WaitForInit(this);
  *a3 = 0;
  *a4 = 0;
  GetEventSourcesForSubscription(&v16, a2);
  v7 = (unsigned __int16 **)operator new(saturated_mul((v17 - v16) >> 5, 8u));
  *a4 = v7;
  memset_0(v7, 0, 8 * ((v17 - v16) >> 5));
  v8 = v17;
  v9 = v16;
  v18[0] = 0;
  v19 = CleanupStringVector;
  v20 = (v17 - v16) >> 5;
  v21 = (__int64)*a4;
  v22 = 0;
  v10 = 0;
  if ( v20 )
  {
    do
    {
      v11 = 32 * v10;
      v12 = *(_QWORD *)(32 * v10 + v9 + 16) + 1LL;
      v13 = 2 * v12;
      if ( !is_mul_ok(v12, 2u) )
        v13 = -1;
      (*a4)[v10] = (unsigned __int16 *)operator new(v13);
      v14 = v11 + v16;
      if ( *(_QWORD *)(v11 + v16 + 24) < 8u )
        v15 = (const unsigned __int16 *)(v11 + v16);
      else
        v15 = *(const unsigned __int16 **)v14;
      StringCchCopyW((*a4)[v10++], *(_QWORD *)(v14 + 16) + 1LL, v15);
      v8 = v17;
      v9 = v16;
    }
    while ( v10 < (v17 - v16) >> 5 );
  }
  v18[0] = 1;
  *a3 = (v8 - v9) >> 5;
  wmi::ScopeGuardImpl3<void (*)(unsigned long,unsigned short * *,bool),unsigned __int64,unsigned short * *,bool>::~ScopeGuardImpl3<void (*)(unsigned long,unsigned short * *,bool),unsigned __int64,unsigned short * *,bool>(v18);
  std::vector<std::wstring>::_Tidy(&v16);
}

```

## disassembly

```asm
0x180004608  push    rbp
0x18000460a  push    rbx
0x18000460b  push    rsi
0x18000460c  push    rdi
0x18000460d  push    r12
0x18000460f  push    r14
0x180004611  mov     rbp, rsp
0x180004614  sub     rsp, 68h
0x180004618  mov     rsi, r9
0x18000461b  mov     r14, r8
0x18000461e  mov     rbx, rdx
0x180004621  call    ?WaitForInit@CollectorService@@AEAAXXZ; CollectorService::WaitForInit(void)
0x180004626  mov     dword ptr [r14], 0
0x18000462d  mov     qword ptr [rsi], 0
0x180004634  mov     rdx, rbx
0x180004637  lea     rcx, [rbp+var_48]
0x18000463b  call    ?GetEventSourcesForSubscription@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBG@Z; GetEventSourcesForSubscription(ushort const *)
0x180004640  nop
0x180004641  mov     rcx, [rbp+var_40]
0x180004645  sub     rcx, [rbp+var_48]
0x180004649  sar     rcx, 5
0x18000464d  mov     eax, 8
0x180004652  mul     rcx
0x180004655  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000465c  cmovb   rax, r12
0x180004660  mov     rcx, rax; dwBytes
0x180004663  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004668  mov     [rsi], rax
0x18000466b  mov     r8, [rbp+var_40]
0x18000466f  sub     r8, [rbp+var_48]
0x180004673  sar     r8, 5
0x180004677  shl     r8, 3; Size
0x18000467b  xor     edx, edx; Val
0x18000467d  mov     rcx, rax; void *
0x180004680  call    memset_0
0x180004685  mov     rdx, [rbp+var_40]
0x180004689  mov     rcx, rdx
0x18000468c  mov     r8, [rbp+var_48]
0x180004690  sub     rcx, r8
0x180004693  sar     rcx, 5
0x180004697  mov     [rbp+var_30], 0
0x18000469b  lea     rax, ?CleanupStringVector@@YAXKPEAPEAG_N@Z; CleanupStringVector(ulong,ushort * *,bool)
0x1800046a2  mov     [rbp+var_28], rax
0x1800046a6  mov     [rbp+var_20], rcx
0x1800046aa  mov     rax, [rsi]
0x1800046ad  mov     [rbp+var_18], rax
0x1800046b1  mov     [rbp+var_10], 0
0x1800046b5  xor     edi, edi
0x1800046b7  test    rcx, rcx
0x1800046ba  jz      short loc_180004729
0x1800046bc  mov     rbx, rdi
0x1800046bf  shl     rbx, 5
0x1800046c3  mov     rcx, [rbx+r8+10h]
0x1800046c8  inc     rcx
0x1800046cb  mov     eax, 2
0x1800046d0  mul     rcx
0x1800046d3  cmovb   rax, r12
0x1800046d7  mov     rcx, rax; dwBytes
0x1800046da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800046df  mov     rcx, [rsi]
0x1800046e2  mov     [rcx+rdi*8], rax
0x1800046e6  mov     rdx, [rbp+var_48]
0x1800046ea  add     rdx, rbx
0x1800046ed  cmp     qword ptr [rdx+18h], 8
0x1800046f2  jb      short loc_1800046F9
0x1800046f4  mov     r8, [rdx]
0x1800046f7  jmp     short loc_1800046FC
0x1800046f9  mov     r8, rdx; unsigned __int16 *
0x1800046fc  mov     rdx, [rdx+10h]
0x180004700  inc     rdx; unsigned __int64
0x180004703  mov     rcx, [rsi]
0x180004706  mov     rcx, [rcx+rdi*8]; unsigned __int16 *
0x18000470a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000470f  inc     rdi
0x180004712  mov     rdx, [rbp+var_40]
0x180004716  mov     rax, rdx
0x180004719  mov     r8, [rbp+var_48]
0x18000471d  sub     rax, r8
0x180004720  sar     rax, 5
0x180004724  cmp     rdi, rax
0x180004727  jb      short loc_1800046BC
0x180004729  mov     [rbp+var_30], 1
0x18000472d  sub     rdx, r8
0x180004730  sar     rdx, 5
0x180004734  mov     [r14], edx
0x180004737  lea     rcx, [rbp+var_30]
0x18000473b  call    ??1?$ScopeGuardImpl3@P6AXKPEAPEAG_N@Z_KPEAPEAG_N@wmi@@QEAA@XZ; wmi::ScopeGuardImpl3<void (*)(ulong,ushort * *,bool),unsigned __int64,ushort * *,bool>::~ScopeGuardImpl3<void (*)(ulong,ushort * *,bool),unsigned __int64,ushort * *,bool>(void)
0x180004740  nop
0x180004741  lea     rcx, [rbp+var_48]
0x180004745  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000474a  add     rsp, 68h
0x18000474e  pop     r14
0x180004750  pop     r12
0x180004752  pop     rdi
0x180004753  pop     rsi
0x180004754  pop     rbx
0x180004755  pop     rbp
0x180004756  retn
```
