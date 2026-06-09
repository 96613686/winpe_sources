# ?RunEx@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJUtagVARIANT@@JJPEAGPEAPEAUIRunningTask@@@Z

- ea: `0x1800201c0`
- end: `0x180020637`
- name: `?RunEx@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJUtagVARIANT@@JJPEAGPEAPEAUIRunningTask@@@Z`
- size: `1143`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x18001f540`
- `0x18001fc20`
- `0x1800201c0`
- `0x180020860`
- `0x180020888`
- `0x180020994`
- `0x1800351ec`
- `0x180039524`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020393`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020393`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020276`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020276`
- `OLEAUT32!__imp_VariantClear` at `0x18002039f`
- `OLEAUT32!__imp_VariantClear` at `0x1800204bb`
- `OLEAUT32!__imp_VariantClear` at `0x1800204eb`
- `OLEAUT32!__imp_VariantClear` at `0x18002050c`
- `OLEAUT32!__imp_VariantClear` at `0x180020521`
- `OLEAUT32!__imp_VariantClear` at `0x180020536`
- `OLEAUT32!__imp_VariantClear` at `0x18002054b`
- `OLEAUT32!__imp_VariantClear` at `0x180020560`
- `OLEAUT32!__imp_VariantClear` at `0x180020620`
- `OLEAUT32!__imp_VariantClear` at `0x18002039f`
- `OLEAUT32!__imp_VariantClear` at `0x1800204bb`
- `OLEAUT32!__imp_VariantClear` at `0x1800204eb`
- `OLEAUT32!__imp_VariantClear` at `0x18002050c`
- `OLEAUT32!__imp_VariantClear` at `0x180020521`
- `OLEAUT32!__imp_VariantClear` at `0x180020536`
- `OLEAUT32!__imp_VariantClear` at `0x18002054b`
- `OLEAUT32!__imp_VariantClear` at `0x180020560`
- `OLEAUT32!__imp_VariantClear` at `0x180020620`
- `OLEAUT32!__imp_VariantCopy` at `0x18002021e`
- `OLEAUT32!__imp_VariantCopy` at `0x18002021e`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800204cf`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800204cf`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002042e`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002042e`

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
0x1800201c0  push    rbx
0x1800201c2  push    rsi
0x1800201c3  push    rdi
0x1800201c4  push    r12
0x1800201c6  push    r13
0x1800201c8  push    r14
0x1800201ca  push    r15
0x1800201cc  sub     rsp, 0A0h
0x1800201d3  mov     rax, cs:__security_cookie
0x1800201da  xor     rax, rsp
0x1800201dd  mov     [rsp+0D8h+var_48], rax
0x1800201e5  mov     [rsp+0D8h+var_90], r9d
0x1800201ea  mov     [rsp+0D8h+var_88], r8d
0x1800201ef  mov     rbx, rdx
0x1800201f2  mov     rsi, rcx
0x1800201f5  mov     r12, [rsp+0D8h+arg_20]
0x1800201fd  mov     rax, [rsp+0D8h+arg_28]
0x180020205  mov     [rsp+0D8h+var_68], rax
0x18002020a  mov     [rsp+0D8h+var_98], 0
0x180020212  xor     eax, eax
0x180020214  mov     word ptr [rsp+0D8h+pvargDest], ax
0x180020219  lea     rcx, [rsp+0D8h+pvargDest]; pvargDest
0x18002021e  call    cs:__imp_VariantCopy
0x180020224  xor     r8d, r8d
0x180020227  test    eax, eax
0x180020229  js      loc_180020483
0x18002022f  mov     rcx, rbx; struct tagVARIANT *
0x180020232  call    ?IsVariantEmpty@@YA_NAEBUtagVARIANT@@@Z; IsVariantEmpty(tagVARIANT const &)
0x180020237  lea     r14d, [r8+8]
0x18002023b  test    al, al
0x18002023d  jz      loc_180020499
0x180020243  movzx   eax, word ptr [rsp+0D8h+pvargDest]
0x180020248  cmp     eax, 2
0x18002024b  jnb     loc_18002040C
0x180020251  mov     edi, r8d
0x180020254  mov     r15, r8
0x180020257  test    r12, r12
0x18002025a  jnz     loc_1800203F9
0x180020260  mov     rax, rsi
0x180020263  lea     rcx, [rsi+10h]
0x180020267  neg     rax
0x18002026a  sbb     rbx, rbx
0x18002026d  and     rbx, rcx
0x180020270  jz      short loc_18002027F
0x180020272  lea     rcx, [rbx+8]; lpCriticalSection
0x180020276  call    cs:__imp_EnterCriticalSection
0x18002027c  xor     r8d, r8d
0x18002027f  mov     [rsp+0D8h+var_60], rbx
0x180020284  xorps   xmm0, xmm0
0x180020287  movups  xmmword ptr [rsp+0D8h+var_58.Data1], xmm0
0x18002028f  lea     r13, [rsi+80h]
0x180020296  add     rsi, 50h ; 'P'
0x18002029a  cmp     [rsi+18h], r14
0x18002029e  jb      loc_1800203E3
0x1800202a4  mov     rdx, [rsi]; unsigned __int16 *
0x1800202a7  cmp     [r13+0], r8d
0x1800202ab  jz      loc_180020570
0x1800202b1  mov     rcx, [r13+8]; this
0x1800202b5  test    rcx, rcx
0x1800202b8  jz      loc_18002057A
0x1800202be  lea     rax, [rsp+0D8h+var_58]
0x1800202c6  mov     [rsp+0D8h+var_A0], rax; struct _GUID *
0x1800202cb  mov     [rsp+0D8h+var_A8], r12; unsigned __int16 *
0x1800202d0  mov     eax, [rsp+0D8h+var_90]
0x1800202d4  mov     [rsp+0D8h+var_B0], eax; unsigned int
0x1800202d8  mov     eax, [rsp+0D8h+var_88]
0x1800202dc  mov     [rsp+0D8h+var_B8], eax; unsigned int
0x1800202e0  mov     r9, r15; unsigned __int16 **
0x1800202e3  mov     r8d, edi; unsigned int
0x1800202e6  call    ?RunTask@RpcSession@@QEBAJPEBGKPEAPEBGKK0PEAU_GUID@@@Z; RpcSession::RunTask(ushort const *,ulong,ushort const * *,ulong,ulong,ushort const *,_GUID *)
0x1800202eb  mov     edi, eax
0x1800202ed  xor     r12d, r12d
0x1800202f0  mov     [rsp+0D8h+var_98], edi
0x1800202f4  test    edi, edi
0x1800202f6  js      loc_180020610
0x1800202fc  mov     r15, [rsp+0D8h+var_68]
0x180020301  test    r15, r15
0x180020304  jz      loc_18002038A
0x18002030a  cmp     [rsi+18h], r14
0x18002030e  jb      short loc_180020313
0x180020310  mov     rsi, [rsi]
0x180020313  mov     qword ptr [rsp+0D8h+var_90], r12
0x180020318  mov     qword ptr [rsp+0D8h+var_88], r12
0x18002031d  lea     rcx, [rsp+0D8h+var_88]
0x180020322  call    ?CreateInstance@?$CComObject@VRunningTaskImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<RunningTaskImpl>::CreateInstance(ATL::CComObject<RunningTaskImpl> * *)
0x180020327  mov     edi, eax
0x180020329  test    eax, eax
0x18002032b  js      loc_1800205F8
0x180020331  mov     r14, qword ptr [rsp+0D8h+var_88]
0x180020336  mov     rax, [r14]
0x180020339  lea     r8, [rsp+0D8h+var_90]
0x18002033e  lea     rdx, _GUID_653758fb_7b9a_4f1e_a471_beeb8e9b834e
0x180020345  mov     rcx, r14
0x180020348  mov     rax, [rax]
0x18002034b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020350  mov     edi, eax
0x180020352  test    eax, eax
0x180020354  js      short loc_1800203CA
0x180020356  lea     rcx, [r14+40h]
0x18002035a  mov     rdx, r13
0x18002035d  call    ??4UniSession@@QEAAAEAV0@AEBV0@@Z; UniSession::operator=(UniSession const &)
0x180020362  movups  xmm0, xmmword ptr [rsp+0D8h+var_58.Data1]
0x18002036a  movdqu  xmmword ptr [r14+80h], xmm0
0x180020373  test    rsi, rsi
0x180020376  jz      short loc_18002037E
0x180020378  cmp     [rsi], r12w
0x18002037c  jnz     short loc_1800203EB
0x18002037e  mov     rax, qword ptr [rsp+0D8h+var_90]
0x180020383  mov     [r15], rax
0x180020386  mov     [rsp+0D8h+var_98], edi
0x18002038a  test    rbx, rbx
0x18002038d  jz      short loc_18002039A
0x18002038f  lea     rcx, [rbx+8]; lpCriticalSection
0x180020393  call    cs:__imp_LeaveCriticalSection
0x180020399  nop
0x18002039a  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x18002039f  call    cs:__imp_VariantClear
0x1800203a5  mov     eax, edi
0x1800203a7  mov     rcx, [rsp+0D8h+var_48]
0x1800203af  xor     rcx, rsp; StackCookie
0x1800203b2  call    __security_check_cookie
0x1800203b7  add     rsp, 0A0h
0x1800203be  pop     r15
0x1800203c0  pop     r14
0x1800203c2  pop     r13
0x1800203c4  pop     r12
0x1800203c6  pop     rdi
0x1800203c7  pop     rsi
0x1800203c8  pop     rbx
0x1800203c9  retn
0x1800203ca  mov     rcx, qword ptr [rsp+0D8h+var_90]
0x1800203cf  test    rcx, rcx
0x1800203d2  jz      short loc_1800203E1
0x1800203d4  mov     rax, [rcx]
0x1800203d7  mov     rax, [rax+10h]
0x1800203db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203e0  nop
0x1800203e1  jmp     short loc_180020386
0x1800203e3  mov     rdx, rsi
0x1800203e6  jmp     loc_1800202A7
0x1800203eb  lea     rcx, [r14+60h]; void *
0x1800203ef  mov     rdx, rsi; Src
0x1800203f2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800203f7  jmp     short loc_18002037E
0x1800203f9  movzx   eax, word ptr [r12]
0x1800203fe  neg     ax
0x180020401  sbb     rcx, rcx
0x180020404  and     r12, rcx
0x180020407  jmp     loc_180020260
0x18002040c  cmp     r14w, ax
0x180020410  jz      loc_1800204F8
0x180020416  and     eax, 0FFFFF000h
0x18002041b  cmp     eax, 2000h
0x180020420  jnz     loc_18002055B
0x180020426  mov     rbx, qword ptr [rsp+0D8h+pvargDest+8]
0x18002042b  mov     rcx, rbx; psa
0x18002042e  call    cs:__imp_SafeArrayGetDim
0x180020434  cmp     eax, 1
0x180020437  jnz     loc_180020507
0x18002043d  movzx   eax, word ptr [rsp+0D8h+pvargDest]
0x180020442  mov     ecx, 0FFFh
0x180020447  and     ax, cx
0x18002044a  cmp     r14w, ax
0x18002044e  jnz     loc_18002051C
0x180020454  mov     edi, [rbx+18h]
0x180020457  cmp     edi, 20h ; ' '
0x18002045a  jg      loc_180020531
0x180020460  mov     r15, [rbx+10h]
0x180020464  xor     r8d, r8d
0x180020467  mov     ecx, r8d
0x18002046a  cmp     ecx, edi
0x18002046c  jge     loc_180020257
0x180020472  movsxd  rax, ecx
0x180020475  cmp     [r15+rax*8], r8
0x180020479  jz      loc_180020546
0x18002047f  inc     ecx
0x180020481  jmp     short loc_18002046A
0x180020483  mov     ecx, 0Ah
0x180020488  mov     word ptr [rsp+0D8h+pvargDest], cx
0x18002048d  mov     dword ptr [rsp+0D8h+pvargDest+8], eax
0x180020491  mov     ecx, eax; int
0x180020493  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180020499  cmp     r14w, [rbx]
0x18002049d  jz      loc_180020243
0x1800204a3  movzx   eax, word ptr [rbx]
0x1800204a6  and     eax, 0FFFFF000h
0x1800204ab  cmp     eax, 2000h
0x1800204b0  jz      loc_180020243
0x1800204b6  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x1800204bb  call    cs:__imp_VariantClear
0x1800204c1  mov     r9d, r14d; vt
0x1800204c4  xor     r8d, r8d; wFlags
0x1800204c7  mov     rdx, rbx; pvarSrc
0x1800204ca  lea     rcx, [rsp+0D8h+pvargDest]; pvargDest
0x1800204cf  call    cs:__imp_VariantChangeType
0x1800204d5  mov     ebx, eax
0x1800204d7  mov     [rsp+0D8h+var_98], eax
0x1800204db  xor     r8d, r8d
0x1800204de  test    eax, eax
0x1800204e0  jns     loc_180020243
0x1800204e6  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x1800204eb  call    cs:__imp_VariantClear
0x1800204f1  mov     eax, ebx
0x1800204f3  jmp     loc_1800203A7
0x1800204f8  mov     edi, 1
0x1800204fd  lea     r15, [rsp+0D8h+pvargDest+8]
0x180020502  jmp     loc_180020257
0x180020507  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x18002050c  call    cs:__imp_VariantClear
0x180020512  mov     eax, 80070057h
0x180020517  jmp     loc_1800203A7
0x18002051c  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x180020521  call    cs:__imp_VariantClear
0x180020527  mov     eax, 80070057h
0x18002052c  jmp     loc_1800203A7
0x180020531  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x180020536  call    cs:__imp_VariantClear
0x18002053c  mov     eax, 80070057h
0x180020541  jmp     loc_1800203A7
0x180020546  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x18002054b  call    cs:__imp_VariantClear
0x180020551  mov     eax, 80070057h
0x180020556  jmp     loc_1800203A7
0x18002055b  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x180020560  call    cs:__imp_VariantClear
0x180020566  mov     eax, 80070057h
0x18002056b  jmp     loc_1800203A7
0x180020570  mov     edi, 800704E3h
0x180020575  jmp     loc_18002060C
0x18002057a  test    rdx, rdx
0x18002057d  jz      short loc_180020589
0x18002057f  cmp     word ptr [rdx], 5Ch ; '\'
0x180020583  jnz     short loc_180020589
0x180020585  add     rdx, 2
0x180020589  test    edi, edi
0x18002058b  jnz     short loc_180020607
0x18002058d  cmp     [rsp+0D8h+var_88], edi
0x180020591  jnz     short loc_180020607
0x180020593  test    r12, r12
0x180020596  jnz     short loc_180020607
0x180020598  mov     qword ptr [rsp+0D8h+var_90], r8
0x18002059d  mov     rcx, [r13+10h]
0x1800205a1  mov     rax, [rcx]
0x1800205a4  lea     r9, [rsp+0D8h+var_90]
0x1800205a9  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x1800205b0  mov     rax, [rax+30h]
0x1800205b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205b9  mov     edi, eax
0x1800205bb  test    eax, eax
0x1800205bd  jns     short loc_1800205CB
0x1800205bf  lea     rcx, [rsp+0D8h+var_90]
0x1800205c4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800205c9  jmp     short loc_18002060C
0x1800205cb  xorps   xmm0, xmm0
0x1800205ce  movups  xmmword ptr [rsp+0D8h+var_58.Data1], xmm0
0x1800205d6  mov     rcx, qword ptr [rsp+0D8h+var_90]
0x1800205db  mov     rax, [rcx]
0x1800205de  mov     rax, [rax+60h]
0x1800205e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205e7  mov     edi, eax
0x1800205e9  lea     rcx, [rsp+0D8h+var_90]
0x1800205ee  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800205f3  jmp     loc_1800202F0
0x1800205f8  lea     rcx, [rsp+0D8h+var_90]
0x1800205fd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020602  jmp     loc_180020386
0x180020607  mov     edi, 80070032h
0x18002060c  mov     [rsp+0D8h+var_98], edi
0x180020610  lea     rcx, [rsp+0D8h+var_60]
0x180020615  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x18002061a  nop
0x18002061b  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x180020620  call    cs:__imp_VariantClear
0x180020626  mov     eax, edi
0x180020628  jmp     loc_1800203A7
0x18002062d  mov     edi, [rsp+0D8h+var_98]
0x180020631  jmp     loc_18002039A
```
