# CSrmAutoPWSZ::Append(ushort const *)

- ea: `0x180016f34`
- end: `0x1800170e6`
- name: `?Append@CSrmAutoPWSZ@@QEAAXPEBG@Z`
- size: `434`
- prototype: `void __fastcall(CSrmAutoPWSZ *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017158`
- `0x180017a24`

## callees

- `0x1800083e0`
- `0x18000ecb8`
- `0x18000f360`
- `0x1800161e8`
- `0x18001623c`
- `0x180016564`
- `0x180016f34`
- `0x1800188cc`
- `0x1800191ec`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001703c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001703c`

## string_xrefs

- `0x1800170cf`: `COM Call %S failed [0x%08lx]`

## pseudocode

```c
void __fastcall CSrmAutoPWSZ::Append(CSrmAutoPWSZ *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rbx
  unsigned int Hr; // ebx
  __int64 v8; // rax
  __int64 v9; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v10; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v11[3]; // [rsp+48h] [rbp-B8h] BYREF
  int v12; // [rsp+60h] [rbp-A0h]
  int v13; // [rsp+64h] [rbp-9Ch]
  int v14; // [rsp+68h] [rbp-98h]
  _BYTE v15[96]; // [rsp+70h] [rbp-90h] BYREF
  int v16; // [rsp+D0h] [rbp-30h]
  _BYTE v17[152]; // [rsp+D8h] [rbp-28h] BYREF
  void **v18; // [rsp+170h] [rbp+70h] BYREF
  int v19; // [rsp+178h] [rbp+78h]

  v10 = (unsigned __int16 *)v11;
  v11[0] = L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h";
  v11[1] = L"CSrmAutoPWSZ::Append";
  v11[2] = L"INCLSTRH";
  v12 = 359;
  v13 = 17;
  v14 = 255;
  v16 = 0x1000000;
  memset_0(v15, 0, sizeof(v15));
  CSrmFunctionTracer::CSrmFunctionTracer(
    (__int64)&v18,
    (const struct CSrmDebugInfo *)v11,
    (__int64)L"CSrmAutoPWSZ::Append");
  if ( *(_QWORD *)this )
  {
    v4 = -1;
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    do
      ++v4;
    while ( *(_WORD *)(*(_QWORD *)this + 2 * v4) );
    v6 = v4 + v5;
    CSrmAutoPWSZ::Reallocate(this, v4 + v5);
    v19 = StringCchCatW(*(unsigned __int16 **)this, v6 + 1, a2);
    if ( v19 < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v18);
      v10 = (unsigned __int16 *)v17;
      v8 = CSrmDebugInfo::CSrmDebugInfo(
             (__int64)v17,
             (__int64)L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h",
             (__int64)L"INCLSTRH",
             (__int64)L"CSrmAutoPWSZ::Append",
             369,
             17);
      LODWORD(v9) = Hr;
      CSrmFunctionTracer::Throw(
        &v18,
        v8,
        Hr,
        L"COM Call %S failed [0x%08lx]",
        "StringCchCatW(m_pwsz, cchNewLength + 1, pwsz)",
        v9);
    }
  }
  else
  {
    v10 = 0;
    SrmDuplicateStr(&v10, a2);
    CoTaskMemFree(*(LPVOID *)this);
    *(_QWORD *)this = v10;
  }
  v18 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v18);
}

```

## disassembly

```asm
0x180016f34  mov     [rsp-8+arg_10], rbx
0x180016f39  push    rbp
0x180016f3a  push    rsi
0x180016f3b  push    rdi
0x180016f3c  push    r12
0x180016f3e  push    r13
0x180016f40  push    r14
0x180016f42  push    r15
0x180016f44  lea     rbp, [rsp-130h]
0x180016f4c  sub     rsp, 230h
0x180016f53  mov     rax, cs:__security_cookie
0x180016f5a  xor     rax, rsp
0x180016f5d  mov     [rbp+160h+var_40], rax
0x180016f64  mov     rsi, rdx
0x180016f67  mov     rdi, rcx
0x180016f6a  lea     rax, [rsp+260h+var_218]
0x180016f6f  mov     [rsp+260h+var_220], rax
0x180016f74  lea     r12, aBaseFsFsrmUtil_0; "base\\fs\\fsrm\\utilities\\inc\\srmstr."...
0x180016f7b  mov     [rsp+260h+var_218], r12
0x180016f80  lea     r15, aCsrmautopwszAp; "CSrmAutoPWSZ::Append"
0x180016f87  mov     [rsp+260h+var_210], r15
0x180016f8c  lea     r13, aInclstrh; "INCLSTRH"
0x180016f93  mov     [rsp+260h+var_208], r13
0x180016f98  mov     [rsp+260h+var_200], 167h
0x180016fa0  mov     [rsp+260h+var_1FC], 11h
0x180016fa8  mov     [rsp+260h+var_1F8], 0FFh
0x180016fb0  xor     r14d, r14d
0x180016fb3  mov     [rbp+160h+var_190], 1000000h
0x180016fba  xor     edx, edx; Val
0x180016fbc  lea     r8d, [r14+60h]; Size
0x180016fc0  lea     rcx, [rsp+260h+var_1F0]; void *
0x180016fc5  call    memset_0
0x180016fca  nop
0x180016fcb  mov     r8, r15
0x180016fce  lea     rdx, [rsp+260h+var_218]
0x180016fd3  lea     rcx, [rbp+160h+var_F0]
0x180016fd7  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180016fdc  nop
0x180016fdd  mov     rdx, [rdi]
0x180016fe0  test    rdx, rdx
0x180016fe3  jz      short loc_180017027
0x180016fe5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016fe9  mov     rcx, rax
0x180016fec  inc     rcx
0x180016fef  cmp     [rsi+rcx*2], r14w
0x180016ff4  jnz     short loc_180016FEC
0x180016ff6  inc     rax
0x180016ff9  cmp     [rdx+rax*2], r14w
0x180016ffe  jnz     short loc_180016FF6
0x180017000  lea     rbx, [rax+rcx]
0x180017004  mov     rdx, rbx; unsigned __int64
0x180017007  mov     rcx, rdi; this
0x18001700a  call    ?Reallocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Reallocate(unsigned __int64)
0x18001700f  lea     rdx, [rbx+1]; unsigned __int64
0x180017013  mov     r8, rsi; unsigned __int16 *
0x180017016  mov     rcx, [rdi]; unsigned __int16 *
0x180017019  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001701e  mov     [rbp+160h+var_E8], eax
0x180017021  test    eax, eax
0x180017023  js      short loc_180017088
0x180017025  jmp     short loc_18001704A
0x180017027  mov     [rsp+260h+var_220], r14
0x18001702c  mov     rdx, rsi; unsigned __int16 *
0x18001702f  lea     rcx, [rsp+260h+var_220]; unsigned __int16 **
0x180017034  call    ?SrmDuplicateStr@@YAXAEAPEAGPEBG@Z; SrmDuplicateStr(ushort * &,ushort const *)
0x180017039  mov     rcx, [rdi]; pv
0x18001703c  call    cs:__imp_CoTaskMemFree
0x180017042  mov     rax, [rsp+260h+var_220]
0x180017047  mov     [rdi], rax
0x18001704a  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180017051  mov     [rbp+160h+var_F0], rax
0x180017055  lea     rcx, [rbp+160h+var_F0]; this
0x180017059  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001705e  mov     rcx, [rbp+160h+var_40]
0x180017065  xor     rcx, rsp; StackCookie
0x180017068  call    __security_check_cookie
0x18001706d  mov     rbx, [rsp+260h+arg_10]
0x180017075  add     rsp, 230h
0x18001707c  pop     r15
0x18001707e  pop     r14
0x180017080  pop     r13
0x180017082  pop     r12
0x180017084  pop     rdi
0x180017085  pop     rsi
0x180017086  pop     rbp
0x180017087  retn
0x180017088  lea     rcx, [rbp+160h+var_F0]; this
0x18001708c  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180017091  mov     ebx, eax
0x180017093  lea     rax, [rbp+160h+var_188]
0x180017097  mov     [rsp+260h+var_220], rax
0x18001709c  mov     dword ptr [rsp+260h+var_238], 11h
0x1800170a4  mov     dword ptr [rsp+260h+var_240], 171h
0x1800170ac  mov     r9, r15
0x1800170af  mov     r8, r13
0x1800170b2  mov     rdx, r12
0x1800170b5  lea     rcx, [rbp+160h+var_188]
0x1800170b9  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800170be  nop
0x1800170bf  mov     dword ptr [rsp+260h+var_238], ebx
0x1800170c3  lea     rcx, aStringcchcatwM; "StringCchCatW(m_pwsz, cchNewLength + 1,"...
0x1800170ca  mov     [rsp+260h+var_240], rcx
0x1800170cf  lea     r9, aComCallSFailed; "COM Call %S failed [0x%08lx]"
0x1800170d6  mov     r8d, ebx
0x1800170d9  mov     rdx, rax
0x1800170dc  lea     rcx, [rbp+160h+var_F0]
0x1800170e0  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
