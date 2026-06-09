# CSWbemNamedValueSet::CContextDispatchHelp::HandleError(long,ushort,tagDISPPARAMS *,tagVARIANT *,uint *,long)

- ea: `0x180023810`
- end: `0x18002399a`
- name: `?HandleError@CContextDispatchHelp@CSWbemNamedValueSet@@UEAAJJGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAIJ@Z`
- size: `394`
- prototype: `__int64 __fastcall(CSWbemNamedValueSet::CContextDispatchHelp *__hidden this, int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, unsigned int *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180023810`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002388f`
- `OLEAUT32!__imp_VariantInit` at `0x1800238bb`
- `OLEAUT32!__imp_VariantInit` at `0x18002388f`
- `OLEAUT32!__imp_VariantInit` at `0x1800238bb`
- `OLEAUT32!__imp_VariantClear` at `0x180023966`
- `OLEAUT32!__imp_VariantClear` at `0x180023970`
- `OLEAUT32!__imp_VariantClear` at `0x180023966`
- `OLEAUT32!__imp_VariantClear` at `0x180023970`
- `OLEAUT32!__imp_VariantCopy` at `0x18002389c`
- `OLEAUT32!__imp_VariantCopy` at `0x1800238cc`
- `OLEAUT32!__imp_VariantCopy` at `0x18002389c`
- `OLEAUT32!__imp_VariantCopy` at `0x1800238cc`

## pseudocode

```c
__int64 __fastcall CSWbemNamedValueSet::CContextDispatchHelp::HandleError(
        CSWbemNamedValueSet::CContextDispatchHelp *this,
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
    if ( (**v9)(v9, &IID_ISWbemNamedValueSet, &v12) >= 0 )
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
0x180023810  mov     [rsp-8+arg_0], rbx
0x180023815  mov     [rsp-8+arg_8], rdi
0x18002381a  push    rbp
0x18002381b  mov     rbp, rsp
0x18002381e  sub     rsp, 70h
0x180023822  mov     ebx, [rbp+arg_30]
0x180023825  mov     rdi, r9
0x180023828  test    edx, edx
0x18002382a  jnz     loc_180023986
0x180023830  cmp     ebx, 80020003h
0x180023836  jnz     loc_180023986
0x18002383c  cmp     dword ptr [r9+10h], 2
0x180023841  jnz     loc_180023986
0x180023847  lea     eax, [rdx+4]
0x18002384a  cmp     ax, r8w
0x18002384e  jnz     loc_180023986
0x180023854  mov     rcx, [rcx+28h]
0x180023858  lea     r8, [rbp+var_38]
0x18002385c  mov     [rbp+var_38], 0
0x180023864  lea     rdx, IID_ISWbemNamedValueSet
0x18002386b  mov     rax, [rcx]
0x18002386e  mov     rax, [rax]
0x180023871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023876  test    eax, eax
0x180023878  js      loc_180023986
0x18002387e  xorps   xmm0, xmm0
0x180023881  lea     rcx, [rbp+pvarg]; pvarg
0x180023885  xor     eax, eax
0x180023887  movups  xmmword ptr [rbp+pvarg], xmm0
0x18002388b  mov     qword ptr [rbp+pvarg+10h], rax
0x18002388f  call    cs:__imp_VariantInit
0x180023895  mov     rdx, [rdi]; pvargSrc
0x180023898  lea     rcx, [rbp+pvarg]; pvargDest
0x18002389c  call    cs:__imp_VariantCopy
0x1800238a2  test    eax, eax
0x1800238a4  js      loc_180023976
0x1800238aa  xorps   xmm0, xmm0
0x1800238ad  lea     rcx, [rbp+pvargDest]; pvarg
0x1800238b1  xor     eax, eax
0x1800238b3  movups  xmmword ptr [rbp+pvargDest], xmm0
0x1800238b7  mov     qword ptr [rbp+pvargDest+10h], rax
0x1800238bb  call    cs:__imp_VariantInit
0x1800238c1  mov     rdx, [rdi]
0x1800238c4  lea     rcx, [rbp+pvargDest]; pvargDest
0x1800238c8  add     rdx, 18h; pvargSrc
0x1800238cc  call    cs:__imp_VariantCopy
0x1800238d2  test    eax, eax
0x1800238d4  js      loc_18002396C
0x1800238da  mov     eax, 8
0x1800238df  cmp     ax, word ptr [rbp+pvargDest]
0x1800238e3  jnz     short loc_18002394E
0x1800238e5  mov     rcx, [rbp+var_38]
0x1800238e9  lea     r9, [rbp+var_40]
0x1800238ed  mov     rdx, qword ptr [rbp+pvargDest+8]
0x1800238f1  xor     r8d, r8d
0x1800238f4  mov     [rbp+var_40], 0
0x1800238fc  mov     rax, [rcx]
0x1800238ff  mov     rax, [rax+40h]
0x180023903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023908  test    eax, eax
0x18002390a  js      short loc_180023962
0x18002390c  mov     rcx, [rbp+var_40]
0x180023910  lea     rdx, [rbp+pvarg]
0x180023914  mov     rax, [rcx]
0x180023917  mov     rax, [rax+40h]
0x18002391b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023920  test    eax, eax
0x180023922  js      short loc_180023928
0x180023924  xor     ebx, ebx
0x180023926  jmp     short loc_18002393C
0x180023928  mov     rax, [rbp+arg_28]
0x18002392c  mov     ebx, 80020005h
0x180023931  test    rax, rax
0x180023934  jz      short loc_18002393C
0x180023936  mov     dword ptr [rax], 0
0x18002393c  mov     rcx, [rbp+var_40]
0x180023940  mov     rax, [rcx]
0x180023943  mov     rax, [rax+10h]
0x180023947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002394c  jmp     short loc_180023962
0x18002394e  mov     rax, [rbp+arg_28]
0x180023952  mov     ebx, 80020005h
0x180023957  test    rax, rax
0x18002395a  jz      short loc_180023962
0x18002395c  mov     dword ptr [rax], 1
0x180023962  lea     rcx, [rbp+pvargDest]; pvarg
0x180023966  call    cs:__imp_VariantClear
0x18002396c  lea     rcx, [rbp+pvarg]; pvarg
0x180023970  call    cs:__imp_VariantClear
0x180023976  mov     rcx, [rbp+var_38]
0x18002397a  mov     rax, [rcx]
0x18002397d  mov     rax, [rax+10h]
0x180023981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023986  lea     r11, [rsp+70h+var_s0]
0x18002398b  mov     eax, ebx
0x18002398d  mov     rbx, [r11+10h]
0x180023991  mov     rdi, [r11+18h]
0x180023995  mov     rsp, r11
0x180023998  pop     rbp
0x180023999  retn
```
