# GetMultiStrValue(HKEY__ *,ushort *,ushort *,IWbemClassObject *)

- ea: `0x180013138`
- end: `0x1800132ec`
- name: `?GetMultiStrValue@@YAJPEAUHKEY__@@PEAG1PEAUIWbemClassObject@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, unsigned __int16 *, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800043c0`

## callees

- `0x180004390`
- `0x180013138`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800131c6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001321d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180013259`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800131c6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001321d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180013259`
- `wbemcomn!?GetMultiStr@Registry@@QEAAPEAGPEBGAEAK@Z` at `0x180013186`
- `wbemcomn!?GetMultiStr@Registry@@QEAAPEAGPEBGAEAK@Z` at `0x180013186`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800132d2`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800132d2`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180013166`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180013166`
- `OLEAUT32!__imp_SysAllocString` at `0x180013226`
- `OLEAUT32!__imp_SysAllocString` at `0x180013226`
- `OLEAUT32!__imp_SysFreeString` at `0x180013249`
- `OLEAUT32!__imp_SysFreeString` at `0x180013249`
- `OLEAUT32!__imp_VariantClear` at `0x1800132bd`
- `OLEAUT32!__imp_VariantClear` at `0x1800132bd`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800131f0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800131f0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001326f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001326f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001323e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001323e`

## pseudocode

```c
__int64 __fastcall GetMultiStrValue(HKEY a1, unsigned __int16 *a2, unsigned __int16 *a3, struct IWbemClassObject *a4)
{
  HRESULT v6; // edi
  unsigned __int16 *MultiStr; // rax
  const WCHAR *v8; // rbx
  signed int v9; // esi
  unsigned __int16 *v10; // r14
  const WCHAR *i; // rdi
  SAFEARRAY *v12; // r14
  LONG v13; // eax
  BSTR v14; // rax
  OLECHAR *v15; // r15
  LONG rgIndices; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-4Ch] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-48h] BYREF
  void *v20[2]; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v22[20]; // [rsp+68h] [rbp-18h] BYREF
  HRESULT v23; // [rsp+7Ch] [rbp-4h]

  Registry::Registry((Registry *)v22, a1, 1u, a2);
  v6 = v23;
  if ( !v23 )
  {
    v18 = 0;
    MultiStr = Registry::GetMultiStr((Registry *)v22, a3, &v18);
    v8 = MultiStr;
    if ( MultiStr )
    {
      v20[0] = MultiStr;
      v20[1] = 0;
      v9 = 0;
      v10 = &MultiStr[((unsigned __int64)v18 >> 1) - 1];
      for ( i = MultiStr; i < v10; i += lstrlenW(i) + 1 )
        ++v9;
      rgsabound.lLbound = 0;
      rgsabound.cElements = v9;
      v12 = SafeArrayCreate(8u, 1u, &rgsabound);
      if ( v12 )
      {
        v13 = 0;
        rgIndices = 0;
        while ( v13 < v9 )
        {
          lstrlenW(v8);
          v14 = SysAllocString(v8);
          v15 = v14;
          if ( v14 )
          {
            v6 = SafeArrayPutElement(v12, &rgIndices, v14);
            SysFreeString(v15);
            if ( v6 < 0 )
            {
              SafeArrayDestroy(v12);
              goto LABEL_15;
            }
          }
          ++rgIndices;
          v8 += lstrlenW(v8) + 1;
          v13 = rgIndices;
        }
        *(_QWORD *)&pvarg.vt = 8200;
        *(_OWORD *)&pvarg.decVal.Lo32 = (unsigned __int64)v12;
        v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))a4->lpVtbl->Put)(
               a4,
               L"sValue",
               0,
               &pvarg,
               0);
        VariantClear(&pvarg);
LABEL_15:
        CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v20);
      }
      else
      {
        CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v20);
        v6 = -2147217402;
      }
    }
    else
    {
      v6 = v23;
    }
  }
  Registry::~Registry((Registry *)v22);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180013138  push    rbp
0x18001313a  push    rbx
0x18001313b  push    rsi
0x18001313c  push    rdi
0x18001313d  push    r12
0x18001313f  push    r14
0x180013141  push    r15
0x180013143  mov     rbp, rsp
0x180013146  sub     rsp, 80h
0x18001314d  mov     r12, r9
0x180013150  mov     rbx, r8
0x180013153  mov     r9, rdx
0x180013156  mov     r15d, 1
0x18001315c  mov     r8d, r15d
0x18001315f  mov     rdx, rcx
0x180013162  lea     rcx, [rbp+var_18]
0x180013166  call    cs:__imp_??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z; Registry::Registry(HKEY__ *,ulong,ushort const *)
0x18001316c  nop
0x18001316d  mov     edi, [rbp+var_4]
0x180013170  test    edi, edi
0x180013172  jnz     loc_1800132CE
0x180013178  mov     [rbp+var_4C], edi
0x18001317b  lea     r8, [rbp+var_4C]
0x18001317f  mov     rdx, rbx
0x180013182  lea     rcx, [rbp+var_18]
0x180013186  call    cs:__imp_?GetMultiStr@Registry@@QEAAPEAGPEBGAEAK@Z; Registry::GetMultiStr(ushort const *,ulong &)
0x18001318c  mov     rbx, rax
0x18001318f  test    rax, rax
0x180013192  jnz     short loc_18001319C
0x180013194  mov     edi, [rbp+var_4]
0x180013197  jmp     loc_1800132CE
0x18001319c  mov     [rbp+var_40], rax
0x1800131a0  mov     [rbp+var_38], 0
0x1800131a8  xor     esi, esi
0x1800131aa  mov     r14d, [rbp+var_4C]
0x1800131ae  shr     r14, 1
0x1800131b1  dec     r14
0x1800131b4  lea     r14, [rax+r14*2]
0x1800131b8  mov     rdi, rax
0x1800131bb  cmp     rax, r14
0x1800131be  jnb     short loc_1800131DA
0x1800131c0  add     esi, r15d
0x1800131c3  mov     rcx, rdi; lpString
0x1800131c6  call    cs:__imp_lstrlenW
0x1800131cc  add     eax, r15d
0x1800131cf  cdqe
0x1800131d1  lea     rdi, [rdi+rax*2]
0x1800131d5  cmp     rdi, r14
0x1800131d8  jb      short loc_1800131C0
0x1800131da  mov     [rbp+rgsabound.lLbound], 0
0x1800131e1  mov     [rbp+rgsabound.cElements], esi
0x1800131e4  mov     ecx, 8; vt
0x1800131e9  lea     r8, [rbp+rgsabound]; rgsabound
0x1800131ed  mov     edx, r15d; cDims
0x1800131f0  call    cs:__imp_SafeArrayCreate
0x1800131f6  mov     r14, rax
0x1800131f9  test    rax, rax
0x1800131fc  jnz     short loc_180013211
0x1800131fe  lea     rcx, [rbp+var_40]
0x180013202  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180013207  mov     edi, 80041006h
0x18001320c  jmp     loc_1800132CE
0x180013211  xor     eax, eax
0x180013213  mov     [rbp+rgIndices], eax
0x180013216  cmp     eax, esi
0x180013218  jge     short loc_180013277
0x18001321a  mov     rcx, rbx; lpString
0x18001321d  call    cs:__imp_lstrlenW
0x180013223  mov     rcx, rbx; psz
0x180013226  call    cs:__imp_SysAllocString
0x18001322c  mov     r15, rax
0x18001322f  test    rax, rax
0x180013232  jz      short loc_180013253
0x180013234  mov     r8, rax; pv
0x180013237  lea     rdx, [rbp+rgIndices]; rgIndices
0x18001323b  mov     rcx, r14; psa
0x18001323e  call    cs:__imp_SafeArrayPutElement
0x180013244  mov     edi, eax
0x180013246  mov     rcx, r15; bstrString
0x180013249  call    cs:__imp_SysFreeString
0x18001324f  test    edi, edi
0x180013251  js      short loc_18001326C
0x180013253  inc     [rbp+rgIndices]
0x180013256  mov     rcx, rbx; lpString
0x180013259  call    cs:__imp_lstrlenW
0x18001325f  inc     eax
0x180013261  cdqe
0x180013263  lea     rbx, [rbx+rax*2]
0x180013267  mov     eax, [rbp+rgIndices]
0x18001326a  jmp     short loc_180013216
0x18001326c  mov     rcx, r14; psa
0x18001326f  call    cs:__imp_SafeArrayDestroy
0x180013275  jmp     short loc_1800132C4
0x180013277  xorps   xmm0, xmm0
0x18001327a  xor     eax, eax
0x18001327c  movups  xmmword ptr [rbp+pvarg], xmm0
0x180013280  mov     qword ptr [rbp+pvarg+10h], rax
0x180013284  mov     eax, 2008h
0x180013289  mov     word ptr [rbp+pvarg], ax
0x18001328d  mov     qword ptr [rbp+pvarg+8], r14
0x180013291  mov     rax, [r12]
0x180013295  mov     [rsp+80h+var_60], 0
0x18001329d  lea     r9, [rbp+pvarg]
0x1800132a1  xor     r8d, r8d
0x1800132a4  lea     rdx, aSvalue; "sValue"
0x1800132ab  mov     rcx, r12
0x1800132ae  mov     rax, [rax+28h]
0x1800132b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132b7  mov     edi, eax
0x1800132b9  lea     rcx, [rbp+pvarg]; pvarg
0x1800132bd  call    cs:__imp_VariantClear
0x1800132c3  nop
0x1800132c4  lea     rcx, [rbp+var_40]
0x1800132c8  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x1800132cd  nop
0x1800132ce  lea     rcx, [rbp+var_18]
0x1800132d2  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x1800132d8  mov     eax, edi
0x1800132da  add     rsp, 80h
0x1800132e1  pop     r15
0x1800132e3  pop     r14
0x1800132e5  pop     r12
0x1800132e7  pop     rdi
0x1800132e8  pop     rsi
0x1800132e9  pop     rbx
0x1800132ea  pop     rbp
0x1800132eb  retn
```
