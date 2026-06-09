# ?RunEx@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJUtagVARIANT@@JJPEAGPEAPEAUIRunningTask@@@Z

- ea: `0x180021450`
- end: `0x180021923`
- name: `?RunEx@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJUtagVARIANT@@JJPEAGPEAPEAUIRunningTask@@@Z`
- size: `1235`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x1800205c0`
- `0x180020cc0`
- `0x180021450`
- `0x180021b80`
- `0x180022160`
- `0x180022274`
- `0x180037cf0`
- `0x18003c664`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021633`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021633`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002150c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002150c`
- `OLEAUT32!__imp_VariantClear` at `0x180021645`
- `OLEAUT32!__imp_VariantClear` at `0x180021771`
- `OLEAUT32!__imp_VariantClear` at `0x1800217ad`
- `OLEAUT32!__imp_VariantClear` at `0x1800217d4`
- `OLEAUT32!__imp_VariantClear` at `0x1800217ef`
- `OLEAUT32!__imp_VariantClear` at `0x18002180a`
- `OLEAUT32!__imp_VariantClear` at `0x180021825`
- `OLEAUT32!__imp_VariantClear` at `0x180021840`
- `OLEAUT32!__imp_VariantClear` at `0x180021906`
- `OLEAUT32!__imp_VariantClear` at `0x180021645`
- `OLEAUT32!__imp_VariantClear` at `0x180021771`
- `OLEAUT32!__imp_VariantClear` at `0x1800217ad`
- `OLEAUT32!__imp_VariantClear` at `0x1800217d4`
- `OLEAUT32!__imp_VariantClear` at `0x1800217ef`
- `OLEAUT32!__imp_VariantClear` at `0x18002180a`
- `OLEAUT32!__imp_VariantClear` at `0x180021825`
- `OLEAUT32!__imp_VariantClear` at `0x180021840`
- `OLEAUT32!__imp_VariantClear` at `0x180021906`
- `OLEAUT32!__imp_VariantCopy` at `0x1800214ae`
- `OLEAUT32!__imp_VariantCopy` at `0x1800214ae`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002178b`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002178b`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800216de`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800216de`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall _RunEx__QIRegisteredTask__RegisteredTaskImpl__UEAAJUtagVARIANT__JJPEAGPEAPEAUIRunningTask___Z(
        __int64 a1,
        const VARIANTARG *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        _QWORD *a6)
{
  const unsigned __int16 *v8; // r12
  HRESULT v9; // eax
  bool v10; // al
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *v11; // r8
  unsigned __int64 v12; // r14
  signed int v13; // edi
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // r15
  __int64 v15; // rbx
  __int64 v16; // r13
  unsigned __int16 *v17; // rsi
  const unsigned __int16 *v18; // rdx
  RpcSession *v19; // rcx
  int Instance; // edi
  _QWORD *v21; // r15
  struct _GUID *v22; // r14
  LONGLONG llVal; // rbx
  signed int i; // ecx
  HRESULT v26; // ebx
  unsigned int v27[2]; // [rsp+48h] [rbp-90h] BYREF
  unsigned int v28[2]; // [rsp+50h] [rbp-88h] BYREF
  VARIANTARG pvargDest; // [rsp+58h] [rbp-80h] BYREF
  _QWORD *v30; // [rsp+70h] [rbp-68h]
  __int64 v31; // [rsp+78h] [rbp-60h] BYREF
  struct _GUID v32; // [rsp+80h] [rbp-58h] BYREF

  v27[0] = a4;
  v28[0] = a3;
  v8 = a5;
  v30 = a6;
  pvargDest.vt = 0;
  v9 = VariantCopy(&pvargDest, a2);
  if ( v9 < 0 )
  {
    pvargDest.vt = 10;
    pvargDest.lVal = v9;
    ATL::PrivateAtlThrow(v9);
  }
  v10 = IsVariantEmpty(a2);
  v12 = (unsigned int)((_DWORD)v11 + 8);
  if ( !v10 && (_WORD)v11 + 8 != a2->vt && (a2->vt & 0xF000) != 0x2000 )
  {
    VariantClear(&pvargDest);
    v26 = VariantChangeType(&pvargDest, a2, 0, v12);
    v11 = 0;
    if ( v26 < 0 )
    {
      VariantClear(&pvargDest);
      return (unsigned int)v26;
    }
  }
  if ( pvargDest.vt >= 2u )
  {
    if ( (_WORD)v12 == pvargDest.vt )
    {
      v13 = 1;
      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvargDest.llVal;
    }
    else
    {
      if ( (pvargDest.vt & 0xF000) != 0x2000
        || (llVal = pvargDest.llVal, SafeArrayGetDim(pvargDest.parray) != 1)
        || (_WORD)v12 != (pvargDest.vt & 0xFFF)
        || (v13 = *(_DWORD *)(llVal + 24), v13 > 32) )
      {
LABEL_45:
        VariantClear(&pvargDest);
        return 2147942487LL;
      }
      p_llVal = *(union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 **)(llVal + 16);
      v11 = 0;
      for ( i = 0; i < v13; ++i )
      {
        if ( !*(&p_llVal->llVal + i) )
          goto LABEL_45;
      }
    }
  }
  else
  {
    v13 = (int)v11;
    p_llVal = v11;
  }
  if ( a5 )
    v8 = (const unsigned __int16 *)(-(__int64)(*a5 != 0) & (unsigned __int64)a5);
  v15 = (a1 + 16) & -(__int64)(a1 != 0);
  if ( v15 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
    v11 = 0;
  }
  v31 = (a1 + 16) & -(__int64)(a1 != 0);
  v32 = 0;
  v16 = a1 + 128;
  v17 = (unsigned __int16 *)(a1 + 80);
  if ( *((_QWORD *)v17 + 3) < v12 )
    v18 = v17;
  else
    v18 = *(const unsigned __int16 **)v17;
  if ( *(_DWORD *)v16 == (_DWORD)v11 )
  {
    Instance = -2147023645;
    goto LABEL_58;
  }
  v19 = *(RpcSession **)(v16 + 8);
  if ( v19 )
  {
    Instance = RpcSession::RunTask(v19, v18, v13, (const unsigned __int16 **)p_llVal, v28[0], v27[0], v8, &v32);
  }
  else
  {
    if ( v18 && *v18 == 92 )
      ++v18;
    if ( v13 || v28[0] || v8 )
    {
      Instance = -2147024846;
      goto LABEL_58;
    }
    *(_QWORD *)v27 = v11;
    Instance = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, GUID *, unsigned int *))(**(_QWORD **)(v16 + 16) + 48LL))(
                 *(_QWORD *)(v16 + 16),
                 v18,
                 &GUID_148bd524_a2ab_11ce_b11f_00aa00530503,
                 v27);
    if ( Instance < 0 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v27);
      goto LABEL_58;
    }
    v32 = 0;
    Instance = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 96LL))(*(_QWORD *)v27);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v27);
  }
  if ( Instance < 0 )
  {
LABEL_58:
    ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v31);
    VariantClear(&pvargDest);
    return (unsigned int)Instance;
  }
  v21 = v30;
  if ( v30 )
  {
    if ( *((_QWORD *)v17 + 3) >= v12 )
      v17 = *(unsigned __int16 **)v17;
    *(_QWORD *)v27 = 0;
    *(_QWORD *)v28 = 0;
    Instance = ATL::CComObject<RunningTaskImpl>::CreateInstance(v28);
    if ( Instance < 0 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v27);
    }
    else
    {
      v22 = *(struct _GUID **)v28;
      Instance = (***(__int64 (__fastcall ****)(_QWORD, GUID *, unsigned int *))v28)(
                   *(_QWORD *)v28,
                   &GUID_653758fb_7b9a_4f1e_a471_beeb8e9b834e,
                   v27);
      if ( Instance < 0 )
      {
        if ( *(_QWORD *)v27 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 16LL))(*(_QWORD *)v27);
      }
      else
      {
        UniSession::operator=(&v22[4], v16);
        v22[8] = v32;
        if ( v17 && *v17 )
          std::wstring::assign(&v22[6], v17);
        *v21 = *(_QWORD *)v27;
      }
    }
  }
  if ( v15 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
  VariantClear(&pvargDest);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180021450  push    rbx
0x180021452  push    rsi
0x180021453  push    rdi
0x180021454  push    r12
0x180021456  push    r13
0x180021458  push    r14
0x18002145a  push    r15
0x18002145c  sub     rsp, 0A0h
0x180021463  mov     rax, cs:__security_cookie
0x18002146a  xor     rax, rsp
0x18002146d  mov     [rsp+0D8h+var_48], rax
0x180021475  mov     [rsp+0D8h+var_90], r9d
0x18002147a  mov     [rsp+0D8h+var_88], r8d
0x18002147f  mov     rbx, rdx
0x180021482  mov     rsi, rcx
0x180021485  mov     r12, [rsp+0D8h+arg_20]
0x18002148d  mov     rax, [rsp+0D8h+arg_28]
0x180021495  mov     [rsp+0D8h+var_68], rax
0x18002149a  mov     [rsp+0D8h+var_98], 0
0x1800214a2  xor     eax, eax
0x1800214a4  mov     word ptr [rsp+0D8h+pvargDest], ax
0x1800214a9  lea     rcx, [rsp+0D8h+pvargDest]; pvargDest
0x1800214ae  call    cs:__imp_VariantCopy
0x1800214b5  nop     dword ptr [rax+rax+00h]
0x1800214ba  xor     r8d, r8d
0x1800214bd  test    eax, eax
0x1800214bf  js      loc_180021739
0x1800214c5  mov     rcx, rbx; struct tagVARIANT *
0x1800214c8  call    ?IsVariantEmpty@@YA_NAEBUtagVARIANT@@@Z; IsVariantEmpty(tagVARIANT const &)
0x1800214cd  lea     r14d, [r8+8]
0x1800214d1  test    al, al
0x1800214d3  jz      loc_18002174F
0x1800214d9  movzx   eax, word ptr [rsp+0D8h+pvargDest]
0x1800214de  cmp     eax, 2
0x1800214e1  jnb     loc_1800216BC
0x1800214e7  mov     edi, r8d
0x1800214ea  mov     r15, r8
0x1800214ed  test    r12, r12
0x1800214f0  jnz     loc_1800216A9
0x1800214f6  mov     rax, rsi
0x1800214f9  lea     rcx, [rsi+10h]
0x1800214fd  neg     rax
0x180021500  sbb     rbx, rbx
0x180021503  and     rbx, rcx
0x180021506  jz      short loc_18002151B
0x180021508  lea     rcx, [rbx+8]; lpCriticalSection
0x18002150c  call    cs:__imp_EnterCriticalSection
0x180021513  nop     dword ptr [rax+rax+00h]
0x180021518  xor     r8d, r8d
0x18002151b  mov     [rsp+0D8h+var_60], rbx
0x180021520  xorps   xmm0, xmm0
0x180021523  movups  xmmword ptr [rsp+0D8h+var_58.Data1], xmm0
0x18002152b  lea     r13, [rsi+80h]
0x180021532  add     rsi, 50h ; 'P'
0x180021536  cmp     [rsi+18h], r14
0x18002153a  jb      loc_180021690
0x180021540  mov     rdx, [rsi]; unsigned __int16 *
0x180021543  cmp     [r13+0], r8d
0x180021547  jz      loc_180021856
0x18002154d  mov     rcx, [r13+8]; this
0x180021551  test    rcx, rcx
0x180021554  jz      loc_180021860
0x18002155a  lea     rax, [rsp+0D8h+var_58]
0x180021562  mov     [rsp+0D8h+var_A0], rax; struct _GUID *
0x180021567  mov     [rsp+0D8h+var_A8], r12; unsigned __int16 *
0x18002156c  mov     eax, [rsp+0D8h+var_90]
0x180021570  mov     [rsp+0D8h+var_B0], eax; unsigned int
0x180021574  mov     eax, [rsp+0D8h+var_88]
0x180021578  mov     [rsp+0D8h+var_B8], eax; unsigned int
0x18002157c  mov     r9, r15; unsigned __int16 **
0x18002157f  mov     r8d, edi; unsigned int
0x180021582  call    ?RunTask@RpcSession@@QEBAJPEBGKPEAPEBGKK0PEAU_GUID@@@Z; RpcSession::RunTask(ushort const *,ulong,ushort const * *,ulong,ulong,ushort const *,_GUID *)
0x180021587  mov     edi, eax
0x180021589  xor     r12d, r12d
0x18002158c  mov     [rsp+0D8h+var_98], edi
0x180021590  test    edi, edi
0x180021592  js      loc_1800218F6
0x180021598  mov     r15, [rsp+0D8h+var_68]
0x18002159d  test    r15, r15
0x1800215a0  jz      loc_18002162A
0x1800215a6  cmp     [rsi+18h], r14
0x1800215aa  jb      short loc_1800215AF
0x1800215ac  mov     rsi, [rsi]
0x1800215af  mov     qword ptr [rsp+0D8h+var_90], r12
0x1800215b4  mov     qword ptr [rsp+0D8h+var_88], r12
0x1800215b9  lea     rcx, [rsp+0D8h+var_88]
0x1800215be  call    ?CreateInstance@?$CComObject@VRunningTaskImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<RunningTaskImpl>::CreateInstance(ATL::CComObject<RunningTaskImpl> * *)
0x1800215c3  mov     edi, eax
0x1800215c5  test    eax, eax
0x1800215c7  js      loc_1800218DE
0x1800215cd  mov     r14, qword ptr [rsp+0D8h+var_88]
0x1800215d2  mov     rax, [r14]
0x1800215d5  lea     r8, [rsp+0D8h+var_90]
0x1800215da  lea     rdx, _GUID_653758fb_7b9a_4f1e_a471_beeb8e9b834e
0x1800215e1  mov     rcx, r14
0x1800215e4  mov     rax, [rax]
0x1800215e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215ec  mov     edi, eax
0x1800215ee  test    eax, eax
0x1800215f0  js      loc_180021677
0x1800215f6  lea     rcx, [r14+40h]
0x1800215fa  mov     rdx, r13
0x1800215fd  call    ??4UniSession@@QEAAAEAV0@AEBV0@@Z; UniSession::operator=(UniSession const &)
0x180021602  movups  xmm0, xmmword ptr [rsp+0D8h+var_58.Data1]
0x18002160a  movdqu  xmmword ptr [r14+80h], xmm0
0x180021613  test    rsi, rsi
0x180021616  jz      short loc_18002161E
0x180021618  cmp     [rsi], r12w
0x18002161c  jnz     short loc_180021698
0x18002161e  mov     rax, qword ptr [rsp+0D8h+var_90]
0x180021623  mov     [r15], rax
0x180021626  mov     [rsp+0D8h+var_98], edi
0x18002162a  test    rbx, rbx
0x18002162d  jz      short loc_180021640
0x18002162f  lea     rcx, [rbx+8]; lpCriticalSection
0x180021633  call    cs:__imp_LeaveCriticalSection
0x18002163a  nop     dword ptr [rax+rax+00h]
0x18002163f  nop
0x180021640  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x180021645  call    cs:__imp_VariantClear
0x18002164c  nop     dword ptr [rax+rax+00h]
0x180021651  mov     eax, edi
0x180021653  mov     rcx, [rsp+0D8h+var_48]
0x18002165b  xor     rcx, rsp; StackCookie
0x18002165e  call    __security_check_cookie
0x180021663  add     rsp, 0A0h
0x18002166a  pop     r15
0x18002166c  pop     r14
0x18002166e  pop     r13
0x180021670  pop     r12
0x180021672  pop     rdi
0x180021673  pop     rsi
0x180021674  pop     rbx
0x180021675  retn
0x180021677  mov     rcx, qword ptr [rsp+0D8h+var_90]
0x18002167c  test    rcx, rcx
0x18002167f  jz      short loc_18002168E
0x180021681  mov     rax, [rcx]
0x180021684  mov     rax, [rax+10h]
0x180021688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002168d  nop
0x18002168e  jmp     short loc_180021626
0x180021690  mov     rdx, rsi
0x180021693  jmp     loc_180021543
0x180021698  lea     rcx, [r14+60h]; void *
0x18002169c  mov     rdx, rsi; Src
0x18002169f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800216a4  jmp     loc_18002161E
0x1800216a9  movzx   eax, word ptr [r12]
0x1800216ae  neg     ax
0x1800216b1  sbb     rcx, rcx
0x1800216b4  and     r12, rcx
0x1800216b7  jmp     loc_1800214F6
0x1800216bc  cmp     r14w, ax
0x1800216c0  jz      loc_1800217C0
0x1800216c6  and     eax, 0FFFFF000h
0x1800216cb  cmp     eax, 2000h
0x1800216d0  jnz     loc_18002183B
0x1800216d6  mov     rbx, qword ptr [rsp+0D8h+pvargDest+8]
0x1800216db  mov     rcx, rbx; psa
0x1800216de  call    cs:__imp_SafeArrayGetDim
0x1800216e5  nop     dword ptr [rax+rax+00h]
0x1800216ea  cmp     eax, 1
0x1800216ed  jnz     loc_1800217CF
0x1800216f3  movzx   eax, word ptr [rsp+0D8h+pvargDest]
0x1800216f8  mov     ecx, 0FFFh
0x1800216fd  and     ax, cx
0x180021700  cmp     r14w, ax
0x180021704  jnz     loc_1800217EA
0x18002170a  mov     edi, [rbx+18h]
0x18002170d  cmp     edi, 20h ; ' '
0x180021710  jg      loc_180021805
0x180021716  mov     r15, [rbx+10h]
0x18002171a  xor     r8d, r8d
0x18002171d  mov     ecx, r8d
0x180021720  cmp     ecx, edi
0x180021722  jge     loc_1800214ED
0x180021728  movsxd  rax, ecx
0x18002172b  cmp     [r15+rax*8], r8
0x18002172f  jz      loc_180021820
0x180021735  inc     ecx
0x180021737  jmp     short loc_180021720
0x180021739  mov     ecx, 0Ah
0x18002173e  mov     word ptr [rsp+0D8h+pvargDest], cx
0x180021743  mov     dword ptr [rsp+0D8h+pvargDest+8], eax
0x180021747  mov     ecx, eax; int
0x180021749  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002174f  cmp     r14w, [rbx]
0x180021753  jz      loc_1800214D9
0x180021759  movzx   eax, word ptr [rbx]
0x18002175c  and     eax, 0FFFFF000h
0x180021761  cmp     eax, 2000h
0x180021766  jz      loc_1800214D9
0x18002176c  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x180021771  call    cs:__imp_VariantClear
0x180021778  nop     dword ptr [rax+rax+00h]
0x18002177d  mov     r9d, r14d; vt
0x180021780  xor     r8d, r8d; wFlags
0x180021783  mov     rdx, rbx; pvarSrc
0x180021786  lea     rcx, [rsp+0D8h+pvargDest]; pvargDest
0x18002178b  call    cs:__imp_VariantChangeType
0x180021792  nop     dword ptr [rax+rax+00h]
0x180021797  mov     ebx, eax
0x180021799  mov     [rsp+0D8h+var_98], eax
0x18002179d  xor     r8d, r8d
0x1800217a0  test    eax, eax
0x1800217a2  jns     loc_1800214D9
0x1800217a8  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x1800217ad  call    cs:__imp_VariantClear
0x1800217b4  nop     dword ptr [rax+rax+00h]
0x1800217b9  mov     eax, ebx
0x1800217bb  jmp     loc_180021653
0x1800217c0  mov     edi, 1
0x1800217c5  lea     r15, [rsp+0D8h+pvargDest+8]
0x1800217ca  jmp     loc_1800214ED
0x1800217cf  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x1800217d4  call    cs:__imp_VariantClear
0x1800217db  nop     dword ptr [rax+rax+00h]
0x1800217e0  mov     eax, 80070057h
0x1800217e5  jmp     loc_180021653
0x1800217ea  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x1800217ef  call    cs:__imp_VariantClear
0x1800217f6  nop     dword ptr [rax+rax+00h]
0x1800217fb  mov     eax, 80070057h
0x180021800  jmp     loc_180021653
0x180021805  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x18002180a  call    cs:__imp_VariantClear
0x180021811  nop     dword ptr [rax+rax+00h]
0x180021816  mov     eax, 80070057h
0x18002181b  jmp     loc_180021653
0x180021820  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x180021825  call    cs:__imp_VariantClear
0x18002182c  nop     dword ptr [rax+rax+00h]
0x180021831  mov     eax, 80070057h
0x180021836  jmp     loc_180021653
0x18002183b  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x180021840  call    cs:__imp_VariantClear
0x180021847  nop     dword ptr [rax+rax+00h]
0x18002184c  mov     eax, 80070057h
0x180021851  jmp     loc_180021653
0x180021856  mov     edi, 800704E3h
0x18002185b  jmp     loc_1800218F2
0x180021860  test    rdx, rdx
0x180021863  jz      short loc_18002186F
0x180021865  cmp     word ptr [rdx], 5Ch ; '\'
0x180021869  jnz     short loc_18002186F
0x18002186b  add     rdx, 2
0x18002186f  test    edi, edi
0x180021871  jnz     short loc_1800218ED
0x180021873  cmp     [rsp+0D8h+var_88], edi
0x180021877  jnz     short loc_1800218ED
0x180021879  test    r12, r12
0x18002187c  jnz     short loc_1800218ED
0x18002187e  mov     qword ptr [rsp+0D8h+var_90], r8
0x180021883  mov     rcx, [r13+10h]
0x180021887  mov     rax, [rcx]
0x18002188a  lea     r9, [rsp+0D8h+var_90]
0x18002188f  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x180021896  mov     rax, [rax+30h]
0x18002189a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002189f  mov     edi, eax
0x1800218a1  test    eax, eax
0x1800218a3  jns     short loc_1800218B1
0x1800218a5  lea     rcx, [rsp+0D8h+var_90]
0x1800218aa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800218af  jmp     short loc_1800218F2
0x1800218b1  xorps   xmm0, xmm0
0x1800218b4  movups  xmmword ptr [rsp+0D8h+var_58.Data1], xmm0
0x1800218bc  mov     rcx, qword ptr [rsp+0D8h+var_90]
0x1800218c1  mov     rax, [rcx]
0x1800218c4  mov     rax, [rax+60h]
0x1800218c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218cd  mov     edi, eax
0x1800218cf  lea     rcx, [rsp+0D8h+var_90]
0x1800218d4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800218d9  jmp     loc_18002158C
0x1800218de  lea     rcx, [rsp+0D8h+var_90]
0x1800218e3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800218e8  jmp     loc_180021626
0x1800218ed  mov     edi, 80070032h
0x1800218f2  mov     [rsp+0D8h+var_98], edi
0x1800218f6  lea     rcx, [rsp+0D8h+var_60]
0x1800218fb  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180021900  nop
0x180021901  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x180021906  call    cs:__imp_VariantClear
0x18002190d  nop     dword ptr [rax+rax+00h]
0x180021912  mov     eax, edi
0x180021914  jmp     loc_180021653
0x180021919  mov     edi, [rsp+0D8h+var_98]
0x18002191d  jmp     loc_180021640
```
