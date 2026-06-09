# RegistrationInfoImpl::put_SecurityDescriptor(tagVARIANT)

- ea: `0x18002f7e0`
- end: `0x18002f9b4`
- name: `?put_SecurityDescriptor@RegistrationInfoImpl@@UEAAJUtagVARIANT@@@Z`
- size: `468`
- prototype: `int(RegistrationInfoImpl *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002f7e0`
- `0x18003c664`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f8ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f946`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f8ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f946`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f849`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f849`
- `OLEAUT32!__imp_VariantClear` at `0x18002f867`
- `OLEAUT32!__imp_VariantClear` at `0x18002f8d9`
- `OLEAUT32!__imp_VariantClear` at `0x18002f915`
- `OLEAUT32!__imp_VariantClear` at `0x18002f958`
- `OLEAUT32!__imp_VariantClear` at `0x18002f867`
- `OLEAUT32!__imp_VariantClear` at `0x18002f8d9`
- `OLEAUT32!__imp_VariantClear` at `0x18002f915`
- `OLEAUT32!__imp_VariantClear` at `0x18002f958`
- `OLEAUT32!__imp_VariantCopy` at `0x18002f80f`
- `OLEAUT32!__imp_VariantCopy` at `0x18002f890`
- `OLEAUT32!__imp_VariantCopy` at `0x18002f80f`
- `OLEAUT32!__imp_VariantCopy` at `0x18002f890`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002f8f3`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002f8f3`

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
0x18002f7e0  mov     rax, rsp
0x18002f7e3  mov     [rax+8], rbx
0x18002f7e7  mov     [rax+10h], rsi
0x18002f7eb  push    rdi
0x18002f7ec  push    r12
0x18002f7ee  push    r13
0x18002f7f0  push    r14
0x18002f7f2  push    r15
0x18002f7f4  sub     rsp, 50h
0x18002f7f8  mov     rbx, rdx
0x18002f7fb  mov     r13, rcx
0x18002f7fe  xor     esi, esi
0x18002f800  mov     [rax+18h], esi
0x18002f803  xor     eax, eax
0x18002f805  mov     word ptr [rsp+78h+pvargDest], ax
0x18002f80a  lea     rcx, [rsp+78h+pvargDest]; pvargDest
0x18002f80f  call    cs:__imp_VariantCopy
0x18002f816  nop     dword ptr [rax+rax+00h]
0x18002f81b  test    eax, eax
0x18002f81d  js      loc_18002F981
0x18002f823  lea     edi, [rsi+0Ah]
0x18002f826  cmp     word ptr [rbx], 2
0x18002f82a  jnb     loc_18002F8BB
0x18002f830  mov     rax, r13
0x18002f833  lea     rcx, [r13+8]
0x18002f837  neg     rax
0x18002f83a  sbb     rbx, rbx
0x18002f83d  and     rbx, rcx
0x18002f840  lea     r15, [rbx+8]
0x18002f844  jz      short loc_18002F855
0x18002f846  mov     rcx, r15; lpCriticalSection
0x18002f849  call    cs:__imp_EnterCriticalSection
0x18002f850  nop     dword ptr [rax+rax+00h]
0x18002f855  mov     [rsp+78h+arg_18], rbx
0x18002f85d  lea     r14, [r13+90h]
0x18002f864  mov     rcx, r14; pvarg
0x18002f867  call    cs:__imp_VariantClear
0x18002f86e  nop     dword ptr [rax+rax+00h]
0x18002f873  mov     r12d, eax
0x18002f876  test    eax, eax
0x18002f878  js      loc_18002F93E
0x18002f87e  lea     rax, [rsp+78h+pvargDest]
0x18002f883  cmp     r14, rax
0x18002f886  jz      short loc_18002F8A4
0x18002f888  lea     rdx, [rsp+78h+pvargDest]; pvargSrc
0x18002f88d  mov     rcx, r14; pvargDest
0x18002f890  call    cs:__imp_VariantCopy
0x18002f897  nop     dword ptr [rax+rax+00h]
0x18002f89c  test    eax, eax
0x18002f89e  js      loc_18002F997
0x18002f8a4  test    rbx, rbx
0x18002f8a7  jz      short loc_18002F8B9
0x18002f8a9  mov     rcx, r15; lpCriticalSection
0x18002f8ac  call    cs:__imp_LeaveCriticalSection
0x18002f8b3  nop     dword ptr [rax+rax+00h]
0x18002f8b8  nop
0x18002f8b9  jmp     short loc_18002F910
0x18002f8bb  cmp     [rbx], di
0x18002f8be  jz      loc_18002F969
0x18002f8c4  mov     r14d, 8
0x18002f8ca  cmp     r14w, [rbx]
0x18002f8ce  jz      loc_18002F830
0x18002f8d4  lea     rcx, [rsp+78h+pvargDest]; pvarg
0x18002f8d9  call    cs:__imp_VariantClear
0x18002f8e0  nop     dword ptr [rax+rax+00h]
0x18002f8e5  mov     r9d, r14d; vt
0x18002f8e8  xor     r8d, r8d; wFlags
0x18002f8eb  mov     rdx, rbx; pvarSrc
0x18002f8ee  lea     rcx, [rsp+78h+pvargDest]; pvargDest
0x18002f8f3  call    cs:__imp_VariantChangeType
0x18002f8fa  nop     dword ptr [rax+rax+00h]
0x18002f8ff  mov     esi, eax
0x18002f901  mov     [rsp+78h+arg_10], eax
0x18002f908  test    eax, eax
0x18002f90a  jns     loc_18002F830
0x18002f910  lea     rcx, [rsp+78h+pvargDest]; pvarg
0x18002f915  call    cs:__imp_VariantClear
0x18002f91c  nop     dword ptr [rax+rax+00h]
0x18002f921  mov     eax, esi
0x18002f923  lea     r11, [rsp+78h+var_28]
0x18002f928  mov     rbx, [r11+30h]
0x18002f92c  mov     rsi, [r11+38h]
0x18002f930  mov     rsp, r11
0x18002f933  pop     r15
0x18002f935  pop     r14
0x18002f937  pop     r13
0x18002f939  pop     r12
0x18002f93b  pop     rdi
0x18002f93c  retn
0x18002f93e  test    rbx, rbx
0x18002f941  jz      short loc_18002F953
0x18002f943  mov     rcx, r15; lpCriticalSection
0x18002f946  call    cs:__imp_LeaveCriticalSection
0x18002f94d  nop     dword ptr [rax+rax+00h]
0x18002f952  nop
0x18002f953  lea     rcx, [rsp+78h+pvargDest]; pvarg
0x18002f958  call    cs:__imp_VariantClear
0x18002f95f  nop     dword ptr [rax+rax+00h]
0x18002f964  mov     eax, r12d
0x18002f967  jmp     short loc_18002F923
0x18002f969  cmp     dword ptr [rbx+8], 80020004h
0x18002f970  jz      loc_18002F830
0x18002f976  mov     r14d, 8
0x18002f97c  jmp     loc_18002F8D4
0x18002f981  mov     edi, 0Ah
0x18002f986  mov     word ptr [rsp+78h+pvargDest], di
0x18002f98b  mov     dword ptr [rsp+78h+pvargDest+8], eax
0x18002f98f  mov     ecx, eax; int
0x18002f991  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002f997  mov     [r14], di
0x18002f99b  mov     [r14+8], eax
0x18002f99f  mov     ecx, eax; int
0x18002f9a1  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002f9a7  mov     esi, [rsp+78h+arg_10]
0x18002f9ae  jmp     loc_18002F910
```
