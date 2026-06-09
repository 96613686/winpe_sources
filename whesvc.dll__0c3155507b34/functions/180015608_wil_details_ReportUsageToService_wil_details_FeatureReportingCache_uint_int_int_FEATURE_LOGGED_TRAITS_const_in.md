# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180015608`
- end: `0x180015738`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `42`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180013a04`
- `0x180013b74`
- `0x180013ce4`
- `0x180013e54`
- `0x180013fc4`
- `0x180014134`
- `0x18001737c`
- `0x18001741c`
- `0x1800174bc`
- `0x180017558`
- `0x1800175f4`
- `0x180017690`
- `0x18001772c`
- `0x1800177c8`
- `0x18001fff0`
- `0x180020160`
- `0x180023660`
- `0x1800245cc`
- `0x180024668`
- `0x180024788`
- `0x180024828`
- `0x1800248c8`
- `0x180024968`
- `0x180024a08`
- `0x180024aa8`
- `0x180024b48`
- `0x180024be8`
- `0x180024c88`
- `0x180024d28`
- `0x180024dc8`
- `0x180024e68`
- `0x180024f08`
- `0x180024fa8`
- `0x180025048`
- `0x1800250e8`
- `0x180025188`
- `0x180025224`
- `0x1800252c4`
- `0x180025364`
- `0x180025404`
- `0x1800254a0`
- `0x180025540`

## callees

- `0x180015608`
- `0x180015740`
- `0x180029010`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  _UNKNOWN **result; // rax
  char v9; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(a1);
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        v9 = 0;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v9, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015608  mov     rax, rsp
0x18001560b  push    rbx
0x18001560c  push    rbp
0x18001560d  push    rsi
0x18001560e  push    rdi
0x18001560f  sub     rsp, 58h
0x180015613  mov     r11d, [rax+38h]
0x180015617  mov     esi, edx
0x180015619  mov     rbp, rcx
0x18001561c  test    r11d, r11d
0x18001561f  jz      loc_18001572F
0x180015625  mov     ebx, [rsp+78h+arg_28]
0x18001562c  mov     r10d, r11d
0x18001562f  sub     r10d, 1
0x180015633  jz      loc_1800156BE
0x180015639  sub     r10d, 1
0x18001563d  jz      short loc_1800156B0
0x18001563f  sub     r10d, 1
0x180015643  jz      short loc_1800156A2
0x180015645  sub     r10d, 1
0x180015649  jz      short loc_180015694
0x18001564b  sub     r10d, 1
0x18001564f  jz      short loc_180015686
0x180015651  cmp     r10d, 1
0x180015655  jz      short loc_180015678
0x180015657  sub     r11b, 64h ; 'd'
0x18001565b  cmp     r11b, 31h ; '1'
0x18001565f  ja      short loc_1800156CB
0x180015661  mov     eax, ebx
0x180015663  neg     eax
0x180015665  movzx   eax, r11b
0x180015669  sbb     ecx, ecx
0x18001566b  and     ecx, 0FFFFFFCEh
0x18001566e  add     ecx, 96h
0x180015674  add     ecx, eax
0x180015676  jmp     short loc_1800156D0
0x180015678  mov     eax, ebx
0x18001567a  neg     eax
0x18001567c  sbb     ecx, ecx
0x18001567e  and     ecx, 0FFFFFFFEh
0x180015681  add     ecx, 0Bh
0x180015684  jmp     short loc_1800156D0
0x180015686  mov     eax, ebx
0x180015688  neg     eax
0x18001568a  sbb     ecx, ecx
0x18001568c  and     ecx, 0FFFFFFFEh
0x18001568f  add     ecx, 0Ah
0x180015692  jmp     short loc_1800156D0
0x180015694  mov     eax, ebx
0x180015696  neg     eax
0x180015698  sbb     ecx, ecx
0x18001569a  and     ecx, 0FFFFFFFCh
0x18001569d  add     ecx, 7
0x1800156a0  jmp     short loc_1800156D0
0x1800156a2  mov     eax, ebx
0x1800156a4  neg     eax
0x1800156a6  sbb     ecx, ecx
0x1800156a8  and     ecx, 0FFFFFFFCh
0x1800156ab  add     ecx, 6
0x1800156ae  jmp     short loc_1800156D0
0x1800156b0  mov     eax, ebx
0x1800156b2  neg     eax
0x1800156b4  sbb     ecx, ecx
0x1800156b6  and     ecx, 0FFFFFFFCh
0x1800156b9  add     ecx, 5
0x1800156bc  jmp     short loc_1800156D0
0x1800156be  mov     eax, ebx
0x1800156c0  neg     eax
0x1800156c2  sbb     ecx, ecx
0x1800156c4  not     ecx
0x1800156c6  and     ecx, 4
0x1800156c9  jmp     short loc_1800156D0
0x1800156cb  mov     ecx, 0FFh
0x1800156d0  mov     rdi, [rsp+78h+arg_20]
0x1800156d8  mov     al, [rdi+4]
0x1800156db  mov     byte ptr [rsp+78h+var_40], al
0x1800156df  mov     dword ptr [rsp+78h+var_58], ecx
0x1800156e3  mov     rcx, rbp
0x1800156e6  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x1800156eb  test    eax, eax
0x1800156ed  jz      short loc_18001572F
0x1800156ef  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800156f6  test    rax, rax
0x1800156f9  jz      short loc_18001572F
0x1800156fb  mov     [rsp+78h+var_40], 1
0x180015704  lea     rcx, [rsp+78h+arg_30]
0x18001570c  mov     [rsp+78h+var_48], 0
0x180015711  mov     r9d, ebx
0x180015714  mov     [rsp+78h+var_50], 0
0x18001571d  xor     r8d, r8d
0x180015720  mov     [rsp+78h+var_58], rcx
0x180015725  mov     rdx, rdi
0x180015728  mov     ecx, esi
0x18001572a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001572f  add     rsp, 58h
0x180015733  pop     rdi
0x180015734  pop     rsi
0x180015735  pop     rbp
0x180015736  pop     rbx
0x180015737  retn
```
