# ResolveMRTText(unsigned __int64,ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180008560`
- end: `0x1800087c4`
- name: `?ResolveMRTText@@YAX_KPEBG11PEAPEAG@Z`
- size: `612`
- prototype: `void __usercall(unsigned __int64@<rcx>, LPCWCH lpString2@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009890`

## callees

- `0x180005670`
- `0x18000735c`
- `0x180008560`
- `0x18001b848`
- `0x180020d34`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800085c1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800085c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800085fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800085fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ResolveMRTText(
        unsigned __int64 a1,
        LPCWCH lpString2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  unsigned __int16 **v9; // r14
  unsigned __int64 v10; // rbx
  __int64 v11; // rax
  int v12; // r9d
  unsigned __int64 v13; // rsi
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r11
  __int64 v16; // r9
  const OLECHAR *v17; // rcx
  unsigned __int64 v18; // rdx
  unsigned __int16 *v19; // r8
  __int64 v20; // r9
  OLECHAR v21; // ax
  __int64 v22; // r10
  unsigned __int16 *v23; // rcx
  __int64 v24; // rsi
  bool v25; // cf
  int MrtHelper; // eax
  int v27; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v9 = a5;
  *a5 = 0;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( lpString2[v11] );
  v12 = 12;
  if ( (int)v11 < 12 )
    v12 = v11;
  if ( CompareStringOrdinal(L"ms-resource:", 12, lpString2, v12, 1) != 2 )
  {
    do
      ++v10;
    while ( lpString2[v10] );
    *v9 = 0;
    v13 = v10 + 1;
    if ( v10 + 1 >= v10 && is_mul_ok(v13, 2u) )
    {
      v14 = (unsigned __int16 *)CoTaskMemAlloc(2 * v13);
      v15 = v14;
      *v9 = v14;
      v16 = 2147942414LL;
      if ( v14 )
        v16 = 0;
      if ( (int)v16 >= 0 )
      {
        if ( (v14 || v10 == -1) && v13 <= 0x7FFFFFFF )
        {
          if ( v10 < 0x7FFFFFFF )
          {
            if ( !lpString2 )
              v10 = 0;
            v17 = &pwzBaseUrl;
            if ( lpString2 )
              v17 = lpString2;
            if ( v13 )
            {
              v18 = v13;
              v19 = v14;
              v20 = 0;
              do
              {
                if ( !v10 )
                  break;
                v21 = *v17;
                if ( !*v17 )
                  break;
                ++v17;
                *v19++ = v21;
                --v10;
                ++v20;
                --v18;
              }
              while ( v18 );
              v22 = v20 - 1;
              if ( v18 )
                v22 = v20;
              v23 = v19 - 1;
              if ( v18 )
                v23 = v19;
              *v23 = 0;
              if ( v18 )
              {
                v25 = v13 == v22;
                v24 = v13 - v22;
                if ( !v25 && v24 != 1 && (unsigned __int64)(2 * v24) > 2 )
                  memset_0(&v15[v22 + 1], 0, 2 * v24 - 2);
              }
            }
            return;
          }
          if ( v10 == -1 )
            return;
        }
        *v14 = 0;
        return;
      }
    }
    else
    {
      v16 = 2147942934LL;
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)v16,
      bIgnoreCase);
  }
  a5 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&a5);
  MrtHelper = CreateMrtHelper(a1, (struct IWpnMrtHelper **)&a5);
  if ( MrtHelper < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)MrtHelper,
      bIgnoreCase);
  v27 = (*((__int64 (__fastcall **)(unsigned __int16 **, LPCWCH, const unsigned __int16 *, const unsigned __int16 *))*a5
         + 3))(
          a5,
          lpString2,
          a3,
          a4);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v27,
      (int)v9);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&a5);
}

```

## disassembly

```asm
0x180008560  push    rbx
0x180008562  push    rbp
0x180008563  push    rsi
0x180008564  push    rdi
0x180008565  push    r12
0x180008567  push    r14
0x180008569  push    r15
0x18000856b  sub     rsp, 30h
0x18000856f  mov     rbp, r9
0x180008572  mov     r15, r8
0x180008575  mov     rdi, rdx
0x180008578  mov     rsi, rcx
0x18000857b  xor     r12d, r12d
0x18000857e  mov     r14, [rsp+68h+arg_20]
0x180008586  mov     [r14], r12
0x180008589  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180008590  mov     rax, rbx
0x180008593  inc     rax
0x180008596  cmp     [rdx+rax*2], r12w
0x18000859b  jnz     short loc_180008593
0x18000859d  mov     r9d, 0Ch
0x1800085a3  cmp     eax, r9d
0x1800085a6  cmovl   r9d, eax; cchCount2
0x1800085aa  mov     [rsp+68h+bIgnoreCase], 1; int
0x1800085b2  mov     r8, rdi; lpString2
0x1800085b5  mov     edx, 0Ch; cchCount1
0x1800085ba  lea     rcx, String1; "ms-resource:"
0x1800085c1  call    cs:__imp_CompareStringOrdinal
0x1800085c7  cmp     eax, 2
0x1800085ca  jz      loc_1800086F2
0x1800085d0  inc     rbx
0x1800085d3  cmp     [rdi+rbx*2], r12w
0x1800085d8  jnz     short loc_1800085D0
0x1800085da  mov     [r14], r12
0x1800085dd  lea     rsi, [rbx+1]
0x1800085e1  cmp     rsi, rbx
0x1800085e4  jb      loc_1800086BD
0x1800085ea  mov     eax, 2
0x1800085ef  mul     rsi
0x1800085f2  test    rdx, rdx
0x1800085f5  jnz     loc_1800086BD
0x1800085fb  mov     rcx, rax; cb
0x1800085fe  call    cs:__imp_CoTaskMemAlloc
0x180008604  mov     r11, rax
0x180008607  mov     [r14], rax
0x18000860a  mov     r9d, 8007000Eh
0x180008610  test    rax, rax
0x180008613  cmovnz  r9d, r12d
0x180008617  test    r9d, r9d
0x18000861a  js      loc_1800086C3
0x180008620  test    rax, rax
0x180008623  jz      loc_180008791
0x180008629  cmp     rsi, 7FFFFFFFh
0x180008630  ja      loc_1800086DF
0x180008636  cmp     rbx, 7FFFFFFFh
0x18000863d  jnb     loc_1800086DA
0x180008643  test    rdi, rdi
0x180008646  cmovz   rbx, r12
0x18000864a  lea     rcx, pwzBaseUrl
0x180008651  cmovnz  rcx, rdi
0x180008655  test    rsi, rsi
0x180008658  jz      short loc_1800086AE
0x18000865a  mov     rdx, rsi
0x18000865d  mov     r8, r11
0x180008660  mov     r9, r12
0x180008663  test    rbx, rbx
0x180008666  jz      short loc_180008688
0x180008668  movzx   eax, word ptr [rcx]
0x18000866b  test    ax, ax
0x18000866e  jz      short loc_180008688
0x180008670  add     rcx, 2
0x180008674  mov     [r8], ax
0x180008678  add     r8, 2
0x18000867c  dec     rbx
0x18000867f  inc     r9
0x180008682  sub     rdx, 1
0x180008686  jnz     short loc_180008663
0x180008688  lea     r10, [r9-1]
0x18000868c  test    rdx, rdx
0x18000868f  cmovnz  r10, r9
0x180008693  lea     rcx, [r8-2]
0x180008697  cmovnz  rcx, r8
0x18000869b  mov     [rcx], r12w
0x18000869f  jz      short loc_1800086AE
0x1800086a1  sub     rsi, r10
0x1800086a4  cmp     rsi, 1
0x1800086a8  ja      loc_18000879F
0x1800086ae  add     rsp, 30h
0x1800086b2  pop     r15
0x1800086b4  pop     r14
0x1800086b6  pop     r12
0x1800086b8  pop     rdi
0x1800086b9  pop     rsi
0x1800086ba  pop     rbp
0x1800086bb  pop     rbx
0x1800086bc  retn
0x1800086bd  mov     r9d, 80070216h; char *
0x1800086c3  mov     rcx, [rsp+68h]; this
0x1800086c8  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800086cf  mov     edx, 0DCh; void *
0x1800086d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800086da  test    rsi, rsi
0x1800086dd  jz      short loc_1800086AE
0x1800086df  mov     [rax], r12w
0x1800086e3  add     rsp, 30h
0x1800086e7  pop     r15
0x1800086e9  pop     r14
0x1800086eb  pop     r12
0x1800086ed  pop     rdi
0x1800086ee  pop     rsi
0x1800086ef  pop     rbp
0x1800086f0  pop     rbx
0x1800086f1  retn
0x1800086f2  mov     [rsp+68h+arg_20], r12
0x1800086fa  lea     rcx, [rsp+68h+arg_20]
0x180008702  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008707  lea     rdx, [rsp+68h+arg_20]; struct IWpnMrtHelper **
0x18000870f  mov     rcx, rsi; unsigned __int64
0x180008712  call    ?CreateMrtHelper@@YAJ_KPEAPEAUIWpnMrtHelper@@@Z; CreateMrtHelper(unsigned __int64,IWpnMrtHelper * *)
0x180008717  mov     rcx, [rsp+68h]; this
0x18000871c  test    eax, eax
0x18000871e  js      short loc_180008767
0x180008720  mov     rcx, [rsp+68h+arg_20]
0x180008728  mov     rax, [rcx]
0x18000872b  mov     qword ptr [rsp+68h+bIgnoreCase], r14; int
0x180008730  mov     r9, rbp
0x180008733  mov     r8, r15
0x180008736  mov     rdx, rdi
0x180008739  mov     rax, [rax+18h]
0x18000873d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008742  mov     rcx, [rsp+68h]; this
0x180008747  test    eax, eax
0x180008749  js      short loc_18000877C
0x18000874b  lea     rcx, [rsp+68h+arg_20]
0x180008753  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008758  add     rsp, 30h
0x18000875c  pop     r15
0x18000875e  pop     r14
0x180008760  pop     r12
0x180008762  pop     rdi
0x180008763  pop     rsi
0x180008764  pop     rbp
0x180008765  pop     rbx
0x180008766  retn
0x180008767  mov     r9d, eax; char *
0x18000876a  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180008771  mov     edx, 0D6h; void *
0x180008776  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000877c  mov     r9d, eax; char *
0x18000877f  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180008786  mov     edx, 0D8h; void *
0x18000878b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180008791  test    rsi, rsi
0x180008794  jnz     loc_1800086DF
0x18000879a  jmp     loc_180008629
0x18000879f  lea     r8, [rsi+rsi]
0x1800087a3  cmp     r8, 2
0x1800087a7  jbe     loc_1800086AE
0x1800087ad  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1800087b1  inc     r10
0x1800087b4  lea     rcx, [r11+r10*2]; void *
0x1800087b8  xor     edx, edx; Val
0x1800087ba  call    memset_0
0x1800087bf  jmp     loc_1800086AE
```
