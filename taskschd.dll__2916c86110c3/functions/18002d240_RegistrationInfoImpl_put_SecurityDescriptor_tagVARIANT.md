# RegistrationInfoImpl::put_SecurityDescriptor(tagVARIANT)

- ea: `0x18002d240`
- end: `0x18002d3d3`
- name: `?put_SecurityDescriptor@RegistrationInfoImpl@@UEAAJUtagVARIANT@@@Z`
- size: `403`
- prototype: `int(RegistrationInfoImpl *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002d240`
- `0x180039524`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d2f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d371`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d2f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d371`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d29f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d29f`
- `OLEAUT32!__imp_VariantClear` at `0x18002d2b7`
- `OLEAUT32!__imp_VariantClear` at `0x18002d317`
- `OLEAUT32!__imp_VariantClear` at `0x18002d347`
- `OLEAUT32!__imp_VariantClear` at `0x18002d37d`
- `OLEAUT32!__imp_VariantClear` at `0x18002d2b7`
- `OLEAUT32!__imp_VariantClear` at `0x18002d317`
- `OLEAUT32!__imp_VariantClear` at `0x18002d347`
- `OLEAUT32!__imp_VariantClear` at `0x18002d37d`
- `OLEAUT32!__imp_VariantCopy` at `0x18002d26f`
- `OLEAUT32!__imp_VariantCopy` at `0x18002d2da`
- `OLEAUT32!__imp_VariantCopy` at `0x18002d26f`
- `OLEAUT32!__imp_VariantCopy` at `0x18002d2da`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002d32b`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002d32b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegistrationInfoImpl::put_SecurityDescriptor(VARIANTARG *this, struct tagVARIANT *a2)
{
  HRESULT v4; // esi
  HRESULT v5; // eax
  unsigned __int64 v6; // rbx
  VARIANTARG *v7; // r14
  HRESULT v8; // r12d
  HRESULT v9; // eax
  tsched *v11; // rcx
  int v12; // r8d
  char *v13; // r9
  char *v14; // rdx
  int *v15; // [rsp+28h] [rbp-50h]
  __int64 v16; // [rsp+0h] [rbp-78h] BYREF
  VARIANTARG pvargDest; // [rsp+30h] [rbp-48h] BYREF

  v4 = 0;
  pvargDest.vt = 0;
  v5 = VariantCopy(&pvargDest, a2);
  if ( v5 < 0 )
  {
    pvargDest.vt = 10;
    pvargDest.lVal = v5;
    ATL::PrivateAtlThrow(v5);
  }
  if ( a2->vt >= 2u )
  {
    if ( a2->vt == 10 )
    {
      if ( a2->lVal == -2147352572 )
        goto LABEL_3;
    }
    else if ( a2->vt == 8 )
    {
      goto LABEL_3;
    }
    VariantClear(&pvargDest);
    v4 = VariantChangeType(&pvargDest, a2, 0, 8u);
    if ( v4 < 0 )
    {
LABEL_14:
      VariantClear(&pvargDest);
      return (unsigned int)v4;
    }
  }
LABEL_3:
  v6 = (unsigned __int64)&this->ullVal & -(__int64)(this != 0);
  if ( v6 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
  v7 = this + 6;
  v8 = VariantClear(this + 6);
  if ( v8 >= 0 )
  {
    if ( v7 != &pvargDest )
    {
      v9 = VariantCopy(this + 6, &pvargDest);
      if ( v9 < 0 )
      {
        v7->vt = 10;
        this[6].lVal = v9;
        try
        {
          ATL::PrivateAtlThrow(v9);
        }
        catch ( ... )
        {
          v14 = (char *)&v16;
          tsched::KnownExceptionToHResult(v11, v14, v12, v13, (_BYTE)v14 - 112, v15);
        }
      }
    }
    if ( v6 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
    goto LABEL_14;
  }
  if ( v6 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
  VariantClear(&pvargDest);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002d240  mov     rax, rsp
0x18002d243  mov     [rax+8], rbx
0x18002d247  mov     [rax+10h], rsi
0x18002d24b  push    rdi
0x18002d24c  push    r12
0x18002d24e  push    r13
0x18002d250  push    r14
0x18002d252  push    r15
0x18002d254  sub     rsp, 50h
0x18002d258  mov     rbx, rdx
0x18002d25b  mov     r13, rcx
0x18002d25e  xor     esi, esi
0x18002d260  mov     [rax+18h], esi
0x18002d263  xor     eax, eax
0x18002d265  mov     word ptr [rsp+78h+pvargDest], ax
0x18002d26a  lea     rcx, [rsp+78h+pvargDest]; pvargDest
0x18002d26f  call    cs:__imp_VariantCopy
0x18002d275  test    eax, eax
0x18002d277  js      loc_18002D3A0
0x18002d27d  lea     edi, [rsi+0Ah]
0x18002d280  cmp     word ptr [rbx], 2
0x18002d284  jnb     short loc_18002D2F9
0x18002d286  mov     rax, r13
0x18002d289  lea     rcx, [r13+8]
0x18002d28d  neg     rax
0x18002d290  sbb     rbx, rbx
0x18002d293  and     rbx, rcx
0x18002d296  lea     r15, [rbx+8]
0x18002d29a  jz      short loc_18002D2A5
0x18002d29c  mov     rcx, r15; lpCriticalSection
0x18002d29f  call    cs:__imp_EnterCriticalSection
0x18002d2a5  mov     [rsp+78h+arg_18], rbx
0x18002d2ad  lea     r14, [r13+90h]
0x18002d2b4  mov     rcx, r14; pvarg
0x18002d2b7  call    cs:__imp_VariantClear
0x18002d2bd  mov     r12d, eax
0x18002d2c0  test    eax, eax
0x18002d2c2  js      loc_18002D369
0x18002d2c8  lea     rax, [rsp+78h+pvargDest]
0x18002d2cd  cmp     r14, rax
0x18002d2d0  jz      short loc_18002D2E8
0x18002d2d2  lea     rdx, [rsp+78h+pvargDest]; pvargSrc
0x18002d2d7  mov     rcx, r14; pvargDest
0x18002d2da  call    cs:__imp_VariantCopy
0x18002d2e0  test    eax, eax
0x18002d2e2  js      loc_18002D3B6
0x18002d2e8  test    rbx, rbx
0x18002d2eb  jz      short loc_18002D2F7
0x18002d2ed  mov     rcx, r15; lpCriticalSection
0x18002d2f0  call    cs:__imp_LeaveCriticalSection
0x18002d2f6  nop
0x18002d2f7  jmp     short loc_18002D342
0x18002d2f9  cmp     [rbx], di
0x18002d2fc  jz      loc_18002D388
0x18002d302  mov     r14d, 8
0x18002d308  cmp     r14w, [rbx]
0x18002d30c  jz      loc_18002D286
0x18002d312  lea     rcx, [rsp+78h+pvargDest]; pvarg
0x18002d317  call    cs:__imp_VariantClear
0x18002d31d  mov     r9d, r14d; vt
0x18002d320  xor     r8d, r8d; wFlags
0x18002d323  mov     rdx, rbx; pvarSrc
0x18002d326  lea     rcx, [rsp+78h+pvargDest]; pvargDest
0x18002d32b  call    cs:__imp_VariantChangeType
0x18002d331  mov     esi, eax
0x18002d333  mov     [rsp+78h+arg_10], eax
0x18002d33a  test    eax, eax
0x18002d33c  jns     loc_18002D286
0x18002d342  lea     rcx, [rsp+78h+pvargDest]; pvarg
0x18002d347  call    cs:__imp_VariantClear
0x18002d34d  mov     eax, esi
0x18002d34f  lea     r11, [rsp+78h+var_28]
0x18002d354  mov     rbx, [r11+30h]
0x18002d358  mov     rsi, [r11+38h]
0x18002d35c  mov     rsp, r11
0x18002d35f  pop     r15
0x18002d361  pop     r14
0x18002d363  pop     r13
0x18002d365  pop     r12
0x18002d367  pop     rdi
0x18002d368  retn
0x18002d369  test    rbx, rbx
0x18002d36c  jz      short loc_18002D378
0x18002d36e  mov     rcx, r15; lpCriticalSection
0x18002d371  call    cs:__imp_LeaveCriticalSection
0x18002d377  nop
0x18002d378  lea     rcx, [rsp+78h+pvargDest]; pvarg
0x18002d37d  call    cs:__imp_VariantClear
0x18002d383  mov     eax, r12d
0x18002d386  jmp     short loc_18002D34F
0x18002d388  cmp     dword ptr [rbx+8], 80020004h
0x18002d38f  jz      loc_18002D286
0x18002d395  mov     r14d, 8
0x18002d39b  jmp     loc_18002D312
0x18002d3a0  mov     edi, 0Ah
0x18002d3a5  mov     word ptr [rsp+78h+pvargDest], di
0x18002d3aa  mov     dword ptr [rsp+78h+pvargDest+8], eax
0x18002d3ae  mov     ecx, eax; int
0x18002d3b0  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002d3b6  mov     [r14], di
0x18002d3ba  mov     [r14+8], eax
0x18002d3be  mov     ecx, eax; int
0x18002d3c0  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002d3c6  mov     esi, [rsp+78h+arg_10]
0x18002d3cd  jmp     loc_18002D342
```
