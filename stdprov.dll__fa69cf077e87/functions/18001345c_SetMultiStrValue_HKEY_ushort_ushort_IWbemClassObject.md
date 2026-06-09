# SetMultiStrValue(HKEY__ *,ushort *,ushort *,IWbemClassObject *)

- ea: `0x18001345c`
- end: `0x1800136ae`
- name: `?SetMultiStrValue@@YAJPEAUHKEY__@@PEAG1PEAUIWbemClassObject@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, unsigned __int16 *, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800043c0`

## callees

- `0x180002e10`
- `0x18001345c`
- `0x180015652`
- `0x180017010`

## import_xrefs

- `wbemcomn!?SetMultiStr@Registry@@QEAAHPEBGPEAGK@Z` at `0x180013661`
- `wbemcomn!?SetMultiStr@Registry@@QEAAHPEBGPEAGK@Z` at `0x180013661`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800135d1`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180013691`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800135d1`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180013691`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x18001348c`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x18001348c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001366c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001366c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800135b0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800135b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001357b`
- `OLEAUT32!__imp_SysFreeString` at `0x180013640`
- `OLEAUT32!__imp_SysFreeString` at `0x18001357b`
- `OLEAUT32!__imp_SysFreeString` at `0x180013640`
- `OLEAUT32!__imp_SysStringLen` at `0x18001356d`
- `OLEAUT32!__imp_SysStringLen` at `0x180013630`
- `OLEAUT32!__imp_SysStringLen` at `0x18001356d`
- `OLEAUT32!__imp_SysStringLen` at `0x180013630`
- `OLEAUT32!__imp_VariantInit` at `0x1800134af`
- `OLEAUT32!__imp_VariantInit` at `0x1800134af`
- `OLEAUT32!__imp_VariantClear` at `0x18001358c`
- `OLEAUT32!__imp_VariantClear` at `0x1800135c2`
- `OLEAUT32!__imp_VariantClear` at `0x180013677`
- `OLEAUT32!__imp_VariantClear` at `0x180013686`
- `OLEAUT32!__imp_VariantClear` at `0x18001358c`
- `OLEAUT32!__imp_VariantClear` at `0x1800135c2`
- `OLEAUT32!__imp_VariantClear` at `0x180013677`
- `OLEAUT32!__imp_VariantClear` at `0x180013686`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001352c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001352c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001351b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001351b`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18001355a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180013607`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18001355a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180013607`

## pseudocode

```c
__int64 __fastcall SetMultiStrValue(HKEY a1, unsigned __int16 *a2, unsigned __int16 *a3, struct IWbemClassObject *a4)
{
  unsigned int v6; // ebx
  SAFEARRAY *parray; // rsi
  HRESULT LBound; // ebx
  int v9; // ebx
  int i; // eax
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
  unsigned __int16 *v14; // r15
  int j; // eax
  LONG rgIndices; // [rsp+40h] [rbp-29h] BYREF
  LONG plUbound; // [rsp+44h] [rbp-25h] BYREF
  OLECHAR *pv; // [rsp+48h] [rbp-21h] BYREF
  LONG plLbound; // [rsp+50h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v21[20]; // [rsp+70h] [rbp+7h] BYREF
  unsigned int v22; // [rsp+84h] [rbp+1Bh]
  VARIANTARG *p_pvarg; // [rsp+88h] [rbp+1Fh]

  Registry::Registry((Registry *)v21, a1, 2u, a2);
  v6 = v22;
  if ( v22
    || (memset(&pvarg, 0, sizeof(pvarg)),
        VariantInit(&pvarg),
        (v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a4->lpVtbl->Get)(
                a4,
                L"sValue",
                0,
                &pvarg,
                0,
                0)) != 0) )
  {
LABEL_13:
    Registry::~Registry((Registry *)v21);
    return v6;
  }
  p_pvarg = &pvarg;
  if ( pvarg.vt == 8200 )
  {
    parray = pvarg.parray;
    plLbound = 0;
    plUbound = 0;
    LBound = SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
    if ( !(LBound | SafeArrayGetUBound(parray, 1u, &plUbound)) )
    {
      v9 = 1;
      for ( i = plLbound; ; i = rgIndices + 1 )
      {
        rgIndices = i;
        if ( i > plUbound )
          break;
        pv = 0;
        if ( SafeArrayGetElement(parray, &rgIndices, &pv) || !pv )
        {
          VariantClear(&pvarg);
          v6 = -2147217400;
          goto LABEL_13;
        }
        v9 += SysStringLen(pv) + 1;
        SysFreeString(pv);
      }
      v11 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v9, 2u));
      v12 = v11;
      if ( v11 )
      {
        memset_0(v11, 0, 2LL * v9);
        v14 = v12;
        for ( j = plLbound; ; j = rgIndices + 1 )
        {
          rgIndices = j;
          if ( j > plUbound )
            break;
          pv = 0;
          if ( !SafeArrayGetElement(parray, &rgIndices, &pv) )
          {
            StringCchCopyW(v14, v9 - (v14 - v12), pv);
            v14 += SysStringLen(pv) + 1;
            SysFreeString(pv);
          }
        }
        v6 = Registry::SetMultiStr((Registry *)v21, a3, v12, 2 * v9);
        CWin32DefaultArena::WbemMemFree(v12);
        VariantClear(&pvarg);
      }
      else
      {
        VariantClear(&pvarg);
        v6 = -2147217402;
      }
      goto LABEL_13;
    }
  }
  VariantClear(&pvarg);
  Registry::~Registry((Registry *)v21);
  return 2147749896LL;
}

```

## disassembly

```asm
0x18001345c  push    rbp
0x18001345e  push    rbx
0x18001345f  push    rsi
0x180013460  push    rdi
0x180013461  push    r12
0x180013463  push    r14
0x180013465  push    r15
0x180013467  lea     rbp, [rsp-27h]
0x18001346c  sub     rsp, 90h
0x180013473  mov     rdi, r9
0x180013476  mov     r12, r8
0x180013479  mov     r9, rdx
0x18001347c  mov     r15d, 2
0x180013482  mov     r8d, r15d
0x180013485  mov     rdx, rcx
0x180013488  lea     rcx, [rbp+57h+var_50]
0x18001348c  call    cs:__imp_??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z; Registry::Registry(HKEY__ *,ulong,ushort const *)
0x180013492  nop
0x180013493  mov     ebx, [rbp+57h+var_3C]
0x180013496  test    ebx, ebx
0x180013498  jnz     loc_1800135CD
0x18001349e  xorps   xmm0, xmm0
0x1800134a1  xor     eax, eax
0x1800134a3  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800134a7  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800134ab  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800134af  call    cs:__imp_VariantInit
0x1800134b5  mov     rax, [rdi]
0x1800134b8  mov     [rsp+0C0h+var_98], 0
0x1800134c1  mov     [rsp+0C0h+var_A0], 0
0x1800134ca  lea     r9, [rbp+57h+pvarg]
0x1800134ce  xor     r8d, r8d
0x1800134d1  lea     rdx, aSvalue; "sValue"
0x1800134d8  mov     rcx, rdi
0x1800134db  mov     rax, [rax+20h]
0x1800134df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134e4  mov     ebx, eax
0x1800134e6  test    eax, eax
0x1800134e8  jnz     loc_1800135CD
0x1800134ee  lea     rax, [rbp+57h+pvarg]
0x1800134f2  mov     [rbp+57h+var_38], rax
0x1800134f6  mov     eax, 2008h
0x1800134fb  cmp     word ptr [rbp+57h+pvarg], ax
0x1800134ff  jnz     loc_180013682
0x180013505  mov     rsi, qword ptr [rbp+57h+pvarg+8]
0x180013509  mov     [rbp+57h+plLbound], ebx
0x18001350c  mov     [rbp+57h+plUbound], ebx
0x18001350f  lea     r8, [rbp+57h+plLbound]; plLbound
0x180013513  lea     edi, [rbx+1]
0x180013516  mov     edx, edi; nDim
0x180013518  mov     rcx, rsi; psa
0x18001351b  call    cs:__imp_SafeArrayGetLBound
0x180013521  mov     ebx, eax
0x180013523  lea     r8, [rbp+57h+plUbound]; plUbound
0x180013527  mov     edx, edi; nDim
0x180013529  mov     rcx, rsi; psa
0x18001352c  call    cs:__imp_SafeArrayGetUBound
0x180013532  or      eax, ebx
0x180013534  jnz     loc_180013682
0x18001353a  mov     ebx, edi
0x18001353c  mov     eax, [rbp+57h+plLbound]
0x18001353f  mov     [rbp+57h+rgIndices], eax
0x180013542  cmp     eax, [rbp+57h+plUbound]
0x180013545  jg      short loc_180013599
0x180013547  mov     [rbp+57h+pv], 0
0x18001354f  lea     r8, [rbp+57h+pv]; pv
0x180013553  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180013557  mov     rcx, rsi; psa
0x18001355a  call    cs:__imp_SafeArrayGetElement
0x180013560  test    eax, eax
0x180013562  jnz     short loc_180013588
0x180013564  mov     rcx, [rbp+57h+pv]; pbstr
0x180013568  test    rcx, rcx
0x18001356b  jz      short loc_180013588
0x18001356d  call    cs:__imp_SysStringLen
0x180013573  inc     eax
0x180013575  add     ebx, eax
0x180013577  mov     rcx, [rbp+57h+pv]; bstrString
0x18001357b  call    cs:__imp_SysFreeString
0x180013581  mov     eax, [rbp+57h+rgIndices]
0x180013584  add     eax, edi
0x180013586  jmp     short loc_18001353F
0x180013588  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001358c  call    cs:__imp_VariantClear
0x180013592  mov     ebx, 80041008h
0x180013597  jmp     short loc_1800135CD
0x180013599  movsxd  r14, ebx
0x18001359c  mov     rax, r15
0x18001359f  mul     r14
0x1800135a2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800135a9  cmovb   rax, rcx
0x1800135ad  mov     rcx, rax
0x1800135b0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800135b6  mov     rdi, rax
0x1800135b9  test    rax, rax
0x1800135bc  jnz     short loc_1800135DE
0x1800135be  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800135c2  call    cs:__imp_VariantClear
0x1800135c8  mov     ebx, 80041006h
0x1800135cd  lea     rcx, [rbp+57h+var_50]
0x1800135d1  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x1800135d7  mov     eax, ebx
0x1800135d9  jmp     loc_18001369C
0x1800135de  lea     r8, [r14+r14]; Size
0x1800135e2  xor     edx, edx; Val
0x1800135e4  mov     rcx, rdi; void *
0x1800135e7  call    memset_0
0x1800135ec  mov     r15, rdi
0x1800135ef  mov     eax, [rbp+57h+plLbound]
0x1800135f2  jmp     short loc_18001364B
0x1800135f4  mov     [rbp+57h+pv], 0
0x1800135fc  lea     r8, [rbp+57h+pv]; pv
0x180013600  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180013604  mov     rcx, rsi; psa
0x180013607  call    cs:__imp_SafeArrayGetElement
0x18001360d  test    eax, eax
0x18001360f  jnz     short loc_180013646
0x180013611  mov     rax, r15
0x180013614  sub     rax, rdi
0x180013617  sar     rax, 1
0x18001361a  mov     rdx, r14
0x18001361d  sub     rdx, rax; unsigned __int64
0x180013620  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x180013624  mov     rcx, r15; unsigned __int16 *
0x180013627  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001362c  mov     rcx, [rbp+57h+pv]; pbstr
0x180013630  call    cs:__imp_SysStringLen
0x180013636  inc     eax
0x180013638  lea     r15, [r15+rax*2]
0x18001363c  mov     rcx, [rbp+57h+pv]; bstrString
0x180013640  call    cs:__imp_SysFreeString
0x180013646  mov     eax, [rbp+57h+rgIndices]
0x180013649  inc     eax
0x18001364b  cmp     eax, [rbp+57h+plUbound]
0x18001364e  mov     [rbp+57h+rgIndices], eax
0x180013651  jle     short loc_1800135F4
0x180013653  lea     r9d, [rbx+rbx]
0x180013657  mov     r8, rdi
0x18001365a  mov     rdx, r12
0x18001365d  lea     rcx, [rbp+57h+var_50]
0x180013661  call    cs:__imp_?SetMultiStr@Registry@@QEAAHPEBGPEAGK@Z; Registry::SetMultiStr(ushort const *,ushort *,ulong)
0x180013667  mov     ebx, eax
0x180013669  mov     rcx, rdi
0x18001366c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013672  nop
0x180013673  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180013677  call    cs:__imp_VariantClear
0x18001367d  jmp     loc_1800135CD
0x180013682  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180013686  call    cs:__imp_VariantClear
0x18001368c  nop
0x18001368d  lea     rcx, [rbp+57h+var_50]
0x180013691  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180013697  mov     eax, 80041008h
0x18001369c  add     rsp, 90h
0x1800136a3  pop     r15
0x1800136a5  pop     r14
0x1800136a7  pop     r12
0x1800136a9  pop     rdi
0x1800136aa  pop     rsi
0x1800136ab  pop     rbx
0x1800136ac  pop     rbp
0x1800136ad  retn
```
