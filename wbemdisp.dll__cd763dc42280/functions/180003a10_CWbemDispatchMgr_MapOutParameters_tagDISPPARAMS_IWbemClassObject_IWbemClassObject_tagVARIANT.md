# CWbemDispatchMgr::MapOutParameters(tagDISPPARAMS *,IWbemClassObject *,IWbemClassObject *,tagVARIANT *)

- ea: `0x180003a10`
- end: `0x180003ca1`
- name: `?MapOutParameters@CWbemDispatchMgr@@AEAAJPEAUtagDISPPARAMS@@PEAUIWbemClassObject@@1PEAUtagVARIANT@@@Z`
- size: `657`
- prototype: `__int64 __usercall@<rax>(CWbemDispatchMgr *__hidden this@<rcx>, struct tagDISPPARAMS *@<rdx>, struct IWbemClassObject *@<r8>, struct IWbemClassObject *@<r9>, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x1800028b0`

## callees

- `0x1800019a0`
- `0x180002258`
- `0x180003a10`
- `0x180005bf0`
- `0x180024720`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003b09`
- `msvcrt!_wcsicmp` at `0x180003b09`
- `OLEAUT32!__imp_SysAllocString` at `0x180003a83`
- `OLEAUT32!__imp_SysAllocString` at `0x180003a83`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c45`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c53`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c45`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c53`
- `OLEAUT32!__imp_VariantInit` at `0x180003acb`
- `OLEAUT32!__imp_VariantInit` at `0x180003b4d`
- `OLEAUT32!__imp_VariantInit` at `0x180003bc8`
- `OLEAUT32!__imp_VariantInit` at `0x180003acb`
- `OLEAUT32!__imp_VariantInit` at `0x180003b4d`
- `OLEAUT32!__imp_VariantInit` at `0x180003bc8`
- `OLEAUT32!__imp_VariantClear` at `0x180003c10`
- `OLEAUT32!__imp_VariantClear` at `0x180003c21`
- `OLEAUT32!__imp_VariantClear` at `0x180003c3b`
- `OLEAUT32!__imp_VariantClear` at `0x180003c10`
- `OLEAUT32!__imp_VariantClear` at `0x180003c21`
- `OLEAUT32!__imp_VariantClear` at `0x180003c3b`
- `OLEAUT32!__imp_VariantCopy` at `0x180003be5`
- `OLEAUT32!__imp_VariantCopy` at `0x180003be5`

## pseudocode

```c
__int64 __fastcall CWbemDispatchMgr::MapOutParameters(
        struct CSWbemServices **this,
        struct tagDISPPARAMS *a2,
        struct IWbemClassObject *a3,
        struct IWbemClassObject *a4,
        struct tagVARIANT *a5)
{
  CWbemDispatchMgr *v8; // rsi
  __int64 result; // rax
  int v10; // ebx
  OLECHAR *v11; // r15
  struct IWbemClassObjectVtbl *lpVtbl; // rax
  struct IWbemClassObjectVtbl *v13; // rax
  signed int v14; // esi
  VARIANTARG *rgvarg; // r14
  HRESULT v16; // eax
  __int64 v17; // [rsp+40h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-29h] BYREF
  VARIANTARG pvargDest; // [rsp+60h] [rbp-11h] BYREF
  VARIANTARG v20; // [rsp+78h] [rbp+7h] BYREF
  wchar_t *String1; // [rsp+E0h] [rbp+6Fh] BYREF

  v8 = (CWbemDispatchMgr *)this;
  result = 0;
  if ( a3 )
  {
    if ( a4 )
    {
      result = ((__int64 (__fastcall *)(struct IWbemClassObject *, __int64))a3->lpVtbl->BeginEnumeration)(a3, 64);
      v10 = result;
      if ( (int)result >= 0 )
      {
        v11 = SysAllocString(L"id");
        while ( 1 )
        {
          lpVtbl = a3->lpVtbl;
          String1 = 0;
          if ( v10 != ((unsigned int (__fastcall *)(struct IWbemClassObject *, _QWORD, wchar_t **, _QWORD, _QWORD, _QWORD))lpVtbl->Next)(
                        a3,
                        0,
                        &String1,
                        0,
                        0,
                        0) )
            break;
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          if ( ((int (__fastcall *)(struct IWbemClassObject *, wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a4->lpVtbl->Get)(
                 a4,
                 String1,
                 0,
                 &pvarg,
                 0,
                 0) >= 0 )
          {
            if ( _wcsicmp(String1, L"ReturnValue") )
            {
              v13 = a3->lpVtbl;
              v17 = 0;
              v10 = ((__int64 (__fastcall *)(struct IWbemClassObject *, wchar_t *, __int64 *))v13->GetPropertyQualifierSet)(
                      a3,
                      String1,
                      &v17);
              if ( v10 >= 0 )
              {
                memset(&v20, 0, sizeof(v20));
                VariantInit(&v20);
                v10 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, VARIANTARG *))(*(_QWORD *)v17 + 24LL))(
                        v17,
                        v11,
                        0,
                        &v20);
                if ( v10 >= 0 )
                {
                  v14 = a2->cArgs - v20.lVal - 1;
                  if ( v14 >= 0 && v14 < (signed int)a2->cArgs )
                  {
                    rgvarg = a2->rgvarg;
                    v10 = MapFromCIMOMObject(this[4], &pvarg, 0, 0, 0);
                    if ( v10 >= 0 )
                    {
                      memset(&pvargDest, 0, sizeof(pvargDest));
                      VariantInit(&pvargDest);
                      if ( (pvarg.vt & 0x2000) != 0 )
                        v16 = ConvertArrayRev(&pvargDest, &pvarg);
                      else
                        v16 = VariantCopy(&pvargDest, &pvarg);
                      v10 = v16;
                      if ( v16 >= 0 )
                        v10 = VariantChangeByValToByRef(&rgvarg[v14], &pvargDest, rgvarg[v14].vt);
                      VariantClear(&pvargDest);
                    }
                  }
                  v8 = (CWbemDispatchMgr *)this;
                }
                VariantClear(&v20);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              }
            }
            else if ( a5 )
            {
              v10 = CWbemDispatchMgr::MapReturnValue(v8, a5, &pvarg);
            }
          }
          VariantClear(&pvarg);
          SysFreeString(String1);
        }
        SysFreeString(v11);
        return (unsigned int)v10;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003a10  mov     [rsp-8+arg_0], rcx
0x180003a15  push    rbp
0x180003a16  push    rsi
0x180003a17  push    rdi
0x180003a18  push    r12
0x180003a1a  push    r13
0x180003a1c  push    r14
0x180003a1e  lea     rbp, [rsp-27h]
0x180003a23  sub     rsp, 98h
0x180003a2a  xor     r14d, r14d
0x180003a2d  mov     r12, r9
0x180003a30  mov     rdi, r8
0x180003a33  mov     r13, rdx
0x180003a36  mov     rsi, rcx
0x180003a39  mov     eax, r14d
0x180003a3c  test    r8, r8
0x180003a3f  jz      loc_180003C6B
0x180003a45  test    r9, r9
0x180003a48  jz      loc_180003C6B
0x180003a4e  mov     rax, [r8]
0x180003a51  mov     edx, 40h ; '@'
0x180003a56  mov     rcx, r8
0x180003a59  mov     [rsp+0C0h+arg_8], rbx
0x180003a61  mov     rax, [rax+40h]
0x180003a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a6a  mov     ebx, eax
0x180003a6c  test    eax, eax
0x180003a6e  js      loc_180003C63
0x180003a74  lea     rcx, aId; "id"
0x180003a7b  mov     [rsp+0C0h+var_30], r15
0x180003a83  call    cs:__imp_SysAllocString
0x180003a89  mov     r15, rax
0x180003a8c  mov     rax, [rdi]
0x180003a8f  lea     r8, [rbp+4Fh+String1]
0x180003a93  mov     [rsp+0C0h+var_98], r14
0x180003a98  xor     r9d, r9d
0x180003a9b  xor     edx, edx
0x180003a9d  mov     [rbp+4Fh+String1], r14
0x180003aa1  mov     rcx, rdi
0x180003aa4  mov     qword ptr [rsp+0C0h+var_A0], r14
0x180003aa9  mov     rax, [rax+48h]
0x180003aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab2  cmp     ebx, eax
0x180003ab4  jnz     loc_180003C50
0x180003aba  xorps   xmm0, xmm0
0x180003abd  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180003ac1  xor     eax, eax
0x180003ac3  movups  xmmword ptr [rbp+4Fh+pvarg], xmm0
0x180003ac7  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x180003acb  call    cs:__imp_VariantInit
0x180003ad1  mov     rax, [r12]
0x180003ad5  lea     r9, [rbp+4Fh+pvarg]
0x180003ad9  mov     rdx, [rbp+4Fh+String1]
0x180003add  xor     r8d, r8d
0x180003ae0  mov     [rsp+0C0h+var_98], r14
0x180003ae5  mov     rcx, r12
0x180003ae8  mov     qword ptr [rsp+0C0h+var_A0], r14
0x180003aed  mov     rax, [rax+20h]
0x180003af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003af6  test    eax, eax
0x180003af8  js      loc_180003C37
0x180003afe  mov     rcx, [rbp+4Fh+String1]; String1
0x180003b02  lea     rdx, aReturnvalue; "ReturnValue"
0x180003b09  call    cs:__imp__wcsicmp
0x180003b0f  test    eax, eax
0x180003b11  jz      loc_180003C7C
0x180003b17  mov     rax, [rdi]
0x180003b1a  lea     r8, [rbp+4Fh+var_80]
0x180003b1e  mov     rdx, [rbp+4Fh+String1]
0x180003b22  mov     rcx, rdi
0x180003b25  mov     [rbp+4Fh+var_80], r14
0x180003b29  mov     rax, [rax+58h]
0x180003b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b32  mov     ebx, eax
0x180003b34  test    eax, eax
0x180003b36  js      loc_180003C37
0x180003b3c  xorps   xmm0, xmm0
0x180003b3f  lea     rcx, [rbp+4Fh+var_48]; pvarg
0x180003b43  xor     eax, eax
0x180003b45  movups  xmmword ptr [rbp+4Fh+var_48], xmm0
0x180003b49  mov     qword ptr [rbp+4Fh+var_48+10h], rax
0x180003b4d  call    cs:__imp_VariantInit
0x180003b53  mov     rcx, [rbp+4Fh+var_80]
0x180003b57  lea     r9, [rbp+4Fh+var_48]
0x180003b5b  xor     r8d, r8d
0x180003b5e  mov     qword ptr [rsp+0C0h+var_A0], r14; int
0x180003b63  mov     rdx, r15
0x180003b66  mov     rax, [rcx]
0x180003b69  mov     rax, [rax+18h]
0x180003b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b72  mov     ebx, eax
0x180003b74  test    eax, eax
0x180003b76  js      loc_180003C1D
0x180003b7c  mov     ecx, [r13+10h]
0x180003b80  mov     esi, ecx
0x180003b82  sub     esi, dword ptr [rbp+4Fh+var_48+8]
0x180003b85  sub     esi, 1
0x180003b88  js      loc_180003C19
0x180003b8e  cmp     esi, ecx
0x180003b90  jge     loc_180003C19
0x180003b96  mov     rcx, [rbp+4Fh+arg_0]
0x180003b9a  lea     rdx, [rbp+4Fh+pvarg]; struct tagVARIANT *
0x180003b9e  mov     r14, [r13+0]
0x180003ba2  xor     r9d, r9d; unsigned __int16 *
0x180003ba5  xor     r8d, r8d; struct ISWbemInternalObject *
0x180003ba8  mov     rcx, [rcx+20h]; struct CSWbemServices *
0x180003bac  call    ?MapFromCIMOMObject@@YAJPEAVCSWbemServices@@PEAUtagVARIANT@@PEAUISWbemInternalObject@@PEAGJ@Z; MapFromCIMOMObject(CSWbemServices *,tagVARIANT *,ISWbemInternalObject *,ushort *,long)
0x180003bb1  mov     ebx, eax
0x180003bb3  test    eax, eax
0x180003bb5  js      short loc_180003C16
0x180003bb7  xorps   xmm0, xmm0
0x180003bba  lea     rcx, [rbp+4Fh+pvargDest]; pvarg
0x180003bbe  xor     eax, eax
0x180003bc0  movups  xmmword ptr [rbp+4Fh+pvargDest], xmm0
0x180003bc4  mov     qword ptr [rbp+4Fh+pvargDest+10h], rax
0x180003bc8  call    cs:__imp_VariantInit
0x180003bce  mov     eax, 2000h
0x180003bd3  lea     rdx, [rbp+4Fh+pvarg]; struct tagVARIANT *
0x180003bd7  lea     rcx, [rbp+4Fh+pvargDest]; struct tagVARIANT *
0x180003bdb  test    word ptr [rbp+4Fh+pvarg], ax
0x180003bdf  jnz     loc_180003C97
0x180003be5  call    cs:__imp_VariantCopy
0x180003beb  mov     ebx, eax
0x180003bed  test    eax, eax
0x180003bef  js      short loc_180003C0C
0x180003bf1  movsxd  rax, esi
0x180003bf4  lea     rdx, [rbp+4Fh+pvargDest]; struct tagVARIANT *
0x180003bf8  lea     rcx, [rax+rax*2]
0x180003bfc  movzx   r8d, word ptr [r14+rcx*8]; unsigned __int16
0x180003c01  lea     rcx, [r14+rcx*8]; struct tagVARIANT *
0x180003c05  call    ?VariantChangeByValToByRef@@YAJPEAUtagVARIANT@@0G@Z; VariantChangeByValToByRef(tagVARIANT *,tagVARIANT *,ushort)
0x180003c0a  mov     ebx, eax
0x180003c0c  lea     rcx, [rbp+4Fh+pvargDest]; pvarg
0x180003c10  call    cs:__imp_VariantClear
0x180003c16  xor     r14d, r14d
0x180003c19  mov     rsi, [rbp+4Fh+arg_0]
0x180003c1d  lea     rcx, [rbp+4Fh+var_48]; pvarg
0x180003c21  call    cs:__imp_VariantClear
0x180003c27  mov     rcx, [rbp+4Fh+var_80]
0x180003c2b  mov     rax, [rcx]
0x180003c2e  mov     rax, [rax+10h]
0x180003c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c37  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180003c3b  call    cs:__imp_VariantClear
0x180003c41  mov     rcx, [rbp+4Fh+String1]; bstrString
0x180003c45  call    cs:__imp_SysFreeString
0x180003c4b  jmp     loc_180003A8C
0x180003c50  mov     rcx, r15; bstrString
0x180003c53  call    cs:__imp_SysFreeString
0x180003c59  mov     r15, [rsp+0C0h+var_30]
0x180003c61  mov     eax, ebx
0x180003c63  mov     rbx, [rsp+0C0h+arg_8]
0x180003c6b  add     rsp, 98h
0x180003c72  pop     r14
0x180003c74  pop     r13
0x180003c76  pop     r12
0x180003c78  pop     rdi
0x180003c79  pop     rsi
0x180003c7a  pop     rbp
0x180003c7b  retn
0x180003c7c  cmp     [rbp+4Fh+arg_20], 0
0x180003c81  jz      short loc_180003C37
0x180003c83  mov     rdx, [rbp+4Fh+arg_20]; struct tagVARIANT *
0x180003c87  lea     r8, [rbp+4Fh+pvarg]; struct tagVARIANT *
0x180003c8b  mov     rcx, rsi; this
0x180003c8e  call    ?MapReturnValue@CWbemDispatchMgr@@AEAAJPEAUtagVARIANT@@0@Z; CWbemDispatchMgr::MapReturnValue(tagVARIANT *,tagVARIANT *)
0x180003c93  mov     ebx, eax
0x180003c95  jmp     short loc_180003C37
0x180003c97  call    ?ConvertArrayRev@@YAJPEAUtagVARIANT@@0@Z; ConvertArrayRev(tagVARIANT *,tagVARIANT *)
0x180003c9c  jmp     loc_180003BEB
```
