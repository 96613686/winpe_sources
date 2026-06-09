# CSWbemQualifierSet::CQualifierSetDispatchHelp::HandleError(long,ushort,tagDISPPARAMS *,tagVARIANT *,uint *,long)

- ea: `0x180021210`
- end: `0x18002139a`
- name: `?HandleError@CQualifierSetDispatchHelp@CSWbemQualifierSet@@UEAAJJGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAIJ@Z`
- size: `394`
- prototype: `__int64 __fastcall(CSWbemQualifierSet::CQualifierSetDispatchHelp *__hidden this, int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, unsigned int *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180021210`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002128f`
- `OLEAUT32!__imp_VariantInit` at `0x1800212bb`
- `OLEAUT32!__imp_VariantInit` at `0x18002128f`
- `OLEAUT32!__imp_VariantInit` at `0x1800212bb`
- `OLEAUT32!__imp_VariantClear` at `0x180021366`
- `OLEAUT32!__imp_VariantClear` at `0x180021370`
- `OLEAUT32!__imp_VariantClear` at `0x180021366`
- `OLEAUT32!__imp_VariantClear` at `0x180021370`
- `OLEAUT32!__imp_VariantCopy` at `0x18002129c`
- `OLEAUT32!__imp_VariantCopy` at `0x1800212cc`
- `OLEAUT32!__imp_VariantCopy` at `0x18002129c`
- `OLEAUT32!__imp_VariantCopy` at `0x1800212cc`

## pseudocode

```c
__int64 __fastcall CSWbemQualifierSet::CQualifierSetDispatchHelp::HandleError(
        CSWbemQualifierSet::CQualifierSetDispatchHelp *this,
        int a2,
        __int16 a3,
        struct tagDISPPARAMS *a4,
        struct tagVARIANT *a5,
        unsigned int *a6,
        unsigned int a7)
{
  unsigned int v7; // ebx
  int (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v11; // [rsp+30h] [rbp-40h] BYREF
  __int64 v12; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG pvargDest; // [rsp+40h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF

  v7 = a7;
  if ( !a2 && a7 == -2147352573 && a4->cArgs == 2 && a3 == 4 )
  {
    v9 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
    v12 = 0;
    if ( (**v9)(v9, &IID_ISWbemQualifierSet, &v12) >= 0 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      if ( VariantCopy(&pvarg, a4->rgvarg) >= 0 )
      {
        memset(&pvargDest, 0, sizeof(pvargDest));
        VariantInit(&pvargDest);
        if ( VariantCopy(&pvargDest, (const VARIANTARG *)a4->rgvarg + 1) >= 0 )
        {
          if ( pvargDest.vt == 8 )
          {
            v11 = 0;
            if ( (*(int (__fastcall **)(__int64, LONGLONG, _QWORD, __int64 *))(*(_QWORD *)v12 + 64LL))(
                   v12,
                   pvargDest.llVal,
                   0,
                   &v11) >= 0 )
            {
              if ( (*(int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v11 + 64LL))(v11, &pvarg) < 0 )
              {
                v7 = -2147352571;
                if ( a6 )
                  *a6 = 0;
              }
              else
              {
                v7 = 0;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            }
          }
          else
          {
            v7 = -2147352571;
            if ( a6 )
              *a6 = 1;
          }
          VariantClear(&pvargDest);
        }
        VariantClear(&pvarg);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180021210  mov     [rsp-8+arg_0], rbx
0x180021215  mov     [rsp-8+arg_8], rdi
0x18002121a  push    rbp
0x18002121b  mov     rbp, rsp
0x18002121e  sub     rsp, 70h
0x180021222  mov     ebx, [rbp+arg_30]
0x180021225  mov     rdi, r9
0x180021228  test    edx, edx
0x18002122a  jnz     loc_180021386
0x180021230  cmp     ebx, 80020003h
0x180021236  jnz     loc_180021386
0x18002123c  cmp     dword ptr [r9+10h], 2
0x180021241  jnz     loc_180021386
0x180021247  lea     eax, [rdx+4]
0x18002124a  cmp     ax, r8w
0x18002124e  jnz     loc_180021386
0x180021254  mov     rcx, [rcx+28h]
0x180021258  lea     r8, [rbp+var_38]
0x18002125c  mov     [rbp+var_38], 0
0x180021264  lea     rdx, IID_ISWbemQualifierSet
0x18002126b  mov     rax, [rcx]
0x18002126e  mov     rax, [rax]
0x180021271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021276  test    eax, eax
0x180021278  js      loc_180021386
0x18002127e  xorps   xmm0, xmm0
0x180021281  lea     rcx, [rbp+pvarg]; pvarg
0x180021285  xor     eax, eax
0x180021287  movups  xmmword ptr [rbp+pvarg], xmm0
0x18002128b  mov     qword ptr [rbp+pvarg+10h], rax
0x18002128f  call    cs:__imp_VariantInit
0x180021295  mov     rdx, [rdi]; pvargSrc
0x180021298  lea     rcx, [rbp+pvarg]; pvargDest
0x18002129c  call    cs:__imp_VariantCopy
0x1800212a2  test    eax, eax
0x1800212a4  js      loc_180021376
0x1800212aa  xorps   xmm0, xmm0
0x1800212ad  lea     rcx, [rbp+pvargDest]; pvarg
0x1800212b1  xor     eax, eax
0x1800212b3  movups  xmmword ptr [rbp+pvargDest], xmm0
0x1800212b7  mov     qword ptr [rbp+pvargDest+10h], rax
0x1800212bb  call    cs:__imp_VariantInit
0x1800212c1  mov     rdx, [rdi]
0x1800212c4  lea     rcx, [rbp+pvargDest]; pvargDest
0x1800212c8  add     rdx, 18h; pvargSrc
0x1800212cc  call    cs:__imp_VariantCopy
0x1800212d2  test    eax, eax
0x1800212d4  js      loc_18002136C
0x1800212da  mov     eax, 8
0x1800212df  cmp     ax, word ptr [rbp+pvargDest]
0x1800212e3  jnz     short loc_18002134E
0x1800212e5  mov     rcx, [rbp+var_38]
0x1800212e9  lea     r9, [rbp+var_40]
0x1800212ed  mov     rdx, qword ptr [rbp+pvargDest+8]
0x1800212f1  xor     r8d, r8d
0x1800212f4  mov     [rbp+var_40], 0
0x1800212fc  mov     rax, [rcx]
0x1800212ff  mov     rax, [rax+40h]
0x180021303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021308  test    eax, eax
0x18002130a  js      short loc_180021362
0x18002130c  mov     rcx, [rbp+var_40]
0x180021310  lea     rdx, [rbp+pvarg]
0x180021314  mov     rax, [rcx]
0x180021317  mov     rax, [rax+40h]
0x18002131b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021320  test    eax, eax
0x180021322  js      short loc_180021328
0x180021324  xor     ebx, ebx
0x180021326  jmp     short loc_18002133C
0x180021328  mov     rax, [rbp+arg_28]
0x18002132c  mov     ebx, 80020005h
0x180021331  test    rax, rax
0x180021334  jz      short loc_18002133C
0x180021336  mov     dword ptr [rax], 0
0x18002133c  mov     rcx, [rbp+var_40]
0x180021340  mov     rax, [rcx]
0x180021343  mov     rax, [rax+10h]
0x180021347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002134c  jmp     short loc_180021362
0x18002134e  mov     rax, [rbp+arg_28]
0x180021352  mov     ebx, 80020005h
0x180021357  test    rax, rax
0x18002135a  jz      short loc_180021362
0x18002135c  mov     dword ptr [rax], 1
0x180021362  lea     rcx, [rbp+pvargDest]; pvarg
0x180021366  call    cs:__imp_VariantClear
0x18002136c  lea     rcx, [rbp+pvarg]; pvarg
0x180021370  call    cs:__imp_VariantClear
0x180021376  mov     rcx, [rbp+var_38]
0x18002137a  mov     rax, [rcx]
0x18002137d  mov     rax, [rax+10h]
0x180021381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021386  lea     r11, [rsp+70h+var_s0]
0x18002138b  mov     eax, ebx
0x18002138d  mov     rbx, [r11+10h]
0x180021391  mov     rdi, [r11+18h]
0x180021395  mov     rsp, r11
0x180021398  pop     rbp
0x180021399  retn
```
