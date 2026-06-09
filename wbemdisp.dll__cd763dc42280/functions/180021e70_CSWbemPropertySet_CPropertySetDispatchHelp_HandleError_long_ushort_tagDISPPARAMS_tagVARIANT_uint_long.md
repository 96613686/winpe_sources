# CSWbemPropertySet::CPropertySetDispatchHelp::HandleError(long,ushort,tagDISPPARAMS *,tagVARIANT *,uint *,long)

- ea: `0x180021e70`
- end: `0x180022004`
- name: `?HandleError@CPropertySetDispatchHelp@CSWbemPropertySet@@UEAAJJGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAIJ@Z`
- size: `404`
- prototype: `__int64 __fastcall(CSWbemPropertySet::CPropertySetDispatchHelp *__hidden this, int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, unsigned int *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180021e70`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180021eef`
- `OLEAUT32!__imp_VariantInit` at `0x180021f1b`
- `OLEAUT32!__imp_VariantInit` at `0x180021eef`
- `OLEAUT32!__imp_VariantInit` at `0x180021f1b`
- `OLEAUT32!__imp_VariantClear` at `0x180021fd0`
- `OLEAUT32!__imp_VariantClear` at `0x180021fda`
- `OLEAUT32!__imp_VariantClear` at `0x180021fd0`
- `OLEAUT32!__imp_VariantClear` at `0x180021fda`
- `OLEAUT32!__imp_VariantCopy` at `0x180021efc`
- `OLEAUT32!__imp_VariantCopy` at `0x180021f2c`
- `OLEAUT32!__imp_VariantCopy` at `0x180021efc`
- `OLEAUT32!__imp_VariantCopy` at `0x180021f2c`

## pseudocode

```c
__int64 __fastcall CSWbemPropertySet::CPropertySetDispatchHelp::HandleError(
        CSWbemPropertySet::CPropertySetDispatchHelp *this,
        int a2,
        __int16 a3,
        struct tagDISPPARAMS *a4,
        struct tagVARIANT *a5,
        unsigned int *a6,
        unsigned int a7)
{
  unsigned int v7; // ebx
  int (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v13; // [rsp+30h] [rbp-40h] BYREF
  __int64 v14; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG pvargDest; // [rsp+40h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF

  v7 = a7;
  if ( !a2 && a7 == -2147352573 && a4->cArgs == 2 && a3 == 4 )
  {
    v9 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
    v14 = 0;
    if ( (**v9)(v9, &IID_ISWbemPropertySet, &v14) >= 0 )
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
            v13 = 0;
            if ( (*(int (__fastcall **)(__int64, LONGLONG, _QWORD, __int64 *))(*(_QWORD *)v14 + 64LL))(
                   v14,
                   pvargDest.llVal,
                   0,
                   &v13) >= 0 )
            {
              v10 = v13;
              if ( v13
                && (v11 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v13 + 64LL))(v13, &pvarg),
                    v10 = v13,
                    v11 >= 0) )
              {
                v7 = 0;
              }
              else
              {
                v7 = -2147352571;
                if ( a6 )
                  *a6 = 0;
              }
              if ( v10 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
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
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180021e70  mov     [rsp-8+arg_0], rbx
0x180021e75  mov     [rsp-8+arg_8], rdi
0x180021e7a  push    rbp
0x180021e7b  mov     rbp, rsp
0x180021e7e  sub     rsp, 70h
0x180021e82  mov     ebx, [rbp+arg_30]
0x180021e85  mov     rdi, r9
0x180021e88  test    edx, edx
0x180021e8a  jnz     loc_180021FF0
0x180021e90  cmp     ebx, 80020003h
0x180021e96  jnz     loc_180021FF0
0x180021e9c  cmp     dword ptr [r9+10h], 2
0x180021ea1  jnz     loc_180021FF0
0x180021ea7  lea     eax, [rdx+4]
0x180021eaa  cmp     ax, r8w
0x180021eae  jnz     loc_180021FF0
0x180021eb4  mov     rcx, [rcx+28h]
0x180021eb8  lea     r8, [rbp+var_38]
0x180021ebc  mov     [rbp+var_38], 0
0x180021ec4  lea     rdx, IID_ISWbemPropertySet
0x180021ecb  mov     rax, [rcx]
0x180021ece  mov     rax, [rax]
0x180021ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ed6  test    eax, eax
0x180021ed8  js      loc_180021FF0
0x180021ede  xorps   xmm0, xmm0
0x180021ee1  lea     rcx, [rbp+pvarg]; pvarg
0x180021ee5  xor     eax, eax
0x180021ee7  movups  xmmword ptr [rbp+pvarg], xmm0
0x180021eeb  mov     qword ptr [rbp+pvarg+10h], rax
0x180021eef  call    cs:__imp_VariantInit
0x180021ef5  mov     rdx, [rdi]; pvargSrc
0x180021ef8  lea     rcx, [rbp+pvarg]; pvargDest
0x180021efc  call    cs:__imp_VariantCopy
0x180021f02  test    eax, eax
0x180021f04  js      loc_180021FE0
0x180021f0a  xorps   xmm0, xmm0
0x180021f0d  lea     rcx, [rbp+pvargDest]; pvarg
0x180021f11  xor     eax, eax
0x180021f13  movups  xmmword ptr [rbp+pvargDest], xmm0
0x180021f17  mov     qword ptr [rbp+pvargDest+10h], rax
0x180021f1b  call    cs:__imp_VariantInit
0x180021f21  mov     rdx, [rdi]
0x180021f24  lea     rcx, [rbp+pvargDest]; pvargDest
0x180021f28  add     rdx, 18h; pvargSrc
0x180021f2c  call    cs:__imp_VariantCopy
0x180021f32  test    eax, eax
0x180021f34  js      loc_180021FD6
0x180021f3a  mov     eax, 8
0x180021f3f  cmp     ax, word ptr [rbp+pvargDest]
0x180021f43  jnz     short loc_180021FB8
0x180021f45  mov     rcx, [rbp+var_38]
0x180021f49  lea     r9, [rbp+var_40]
0x180021f4d  mov     rdx, qword ptr [rbp+pvargDest+8]
0x180021f51  xor     r8d, r8d
0x180021f54  mov     [rbp+var_40], 0
0x180021f5c  mov     rax, [rcx]
0x180021f5f  mov     rax, [rax+40h]
0x180021f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f68  test    eax, eax
0x180021f6a  js      short loc_180021FCC
0x180021f6c  mov     rcx, [rbp+var_40]
0x180021f70  test    rcx, rcx
0x180021f73  jz      short loc_180021F91
0x180021f75  mov     rax, [rcx]
0x180021f78  lea     rdx, [rbp+pvarg]
0x180021f7c  mov     rax, [rax+40h]
0x180021f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f85  mov     rcx, [rbp+var_40]
0x180021f89  test    eax, eax
0x180021f8b  js      short loc_180021F91
0x180021f8d  xor     ebx, ebx
0x180021f8f  jmp     short loc_180021FA5
0x180021f91  mov     rax, [rbp+arg_28]
0x180021f95  mov     ebx, 80020005h
0x180021f9a  test    rax, rax
0x180021f9d  jz      short loc_180021FA5
0x180021f9f  mov     dword ptr [rax], 0
0x180021fa5  test    rcx, rcx
0x180021fa8  jz      short loc_180021FCC
0x180021faa  mov     rax, [rcx]
0x180021fad  mov     rax, [rax+10h]
0x180021fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fb6  jmp     short loc_180021FCC
0x180021fb8  mov     rax, [rbp+arg_28]
0x180021fbc  mov     ebx, 80020005h
0x180021fc1  test    rax, rax
0x180021fc4  jz      short loc_180021FCC
0x180021fc6  mov     dword ptr [rax], 1
0x180021fcc  lea     rcx, [rbp+pvargDest]; pvarg
0x180021fd0  call    cs:__imp_VariantClear
0x180021fd6  lea     rcx, [rbp+pvarg]; pvarg
0x180021fda  call    cs:__imp_VariantClear
0x180021fe0  mov     rcx, [rbp+var_38]
0x180021fe4  mov     rax, [rcx]
0x180021fe7  mov     rax, [rax+10h]
0x180021feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ff0  lea     r11, [rsp+70h+var_s0]
0x180021ff5  mov     eax, ebx
0x180021ff7  mov     rbx, [r11+10h]
0x180021ffb  mov     rdi, [r11+18h]
0x180021fff  mov     rsp, r11
0x180022002  pop     rbp
0x180022003  retn
```
