# GetAllEmailAddresses(int,IMAPIProp *,_DPA * *)

- ea: `0x180064494`
- end: `0x1800646ae`
- name: `?GetAllEmailAddresses@@YAJHPEAUIMAPIProp@@PEAPEAU_DPA@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(int, struct IMAPIProp *, struct _DPA **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18003d110`
- `0x180067c08`

## callees

- `0x180006f7c`
- `0x180009aec`
- `0x180064494`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x180064598`
- `SHLWAPI!StrCmpIW` at `0x180064598`
- `OLEAUT32!__imp_SysAllocString` at `0x180064619`
- `OLEAUT32!__imp_SysAllocString` at `0x180064619`
- `OLEAUT32!__imp_SysFreeString` at `0x180064660`
- `OLEAUT32!__imp_SysFreeString` at `0x180064660`
- `iertutil!__imp_DPA_Create` at `0x180064561`
- `iertutil!__imp_DPA_Create` at `0x180064561`
- `iertutil!__imp_DPA_DestroyCallback` at `0x18006467f`
- `iertutil!__imp_DPA_DestroyCallback` at `0x18006467f`
- `iertutil!__imp_DPA_InsertPtr` at `0x180064648`
- `iertutil!__imp_DPA_InsertPtr` at `0x180064648`

## pseudocode

```c
__int64 __fastcall GetAllEmailAddresses(__int64 a1, struct IMAPIProp *a2, struct _DPA **a3)
{
  struct IMAPIPropVtbl *lpVtbl; // rax
  OLECHAR *v4; // r14
  HRESULT (__stdcall *GetProps)(IMAPIProp *, LPSPropTagArray, ULONG, ULONG *, LPSPropValue *); // rax
  struct _DPA *v7; // rdi
  int v8; // ebx
  unsigned int i; // esi
  int v10; // eax
  int v11; // r12d
  const OLECHAR *v12; // rcx
  __int64 v14; // [rsp+30h] [rbp-50h] BYREF
  int v15; // [rsp+38h] [rbp-48h] BYREF
  int v16; // [rsp+40h] [rbp-40h] BYREF
  OLECHAR *psz[2]; // [rsp+48h] [rbp-38h] BYREF
  int v18; // [rsp+58h] [rbp-28h]
  _DWORD v19[4]; // [rsp+60h] [rbp-20h] BYREF

  lpVtbl = a2->lpVtbl;
  v4 = 0;
  v19[0] = 3;
  v19[1] = 805503007;
  GetProps = lpVtbl->GetProps;
  v19[2] = 978718751;
  v19[3] = 978587679;
  v15 = 0;
  v14 = 0;
  v7 = 0;
  v8 = ((__int64 (__fastcall *)(struct IMAPIProp *, _DWORD *, __int64, int *, __int64 *))GetProps)(
         a2,
         v19,
         0x80000000LL,
         &v15,
         &v14);
  if ( v8 >= 0
    && *(_WORD *)v14 != 10
    && *(_QWORD *)(v14 + 8)
    && *(_WORD *)(v14 + 24) != 10
    && *(_QWORD *)(v14 + 40)
    && *(_WORD *)(v14 + 48) != 10
    && *(_QWORD *)(v14 + 64) )
  {
    v7 = DPA_Create(*(_DWORD *)(v14 + 32));
    if ( v7 )
    {
      for ( i = 0; i < *(_DWORD *)(v14 + 32); ++i )
      {
        v10 = StrCmpIW(*(PCWSTR *)(*(_QWORD *)(v14 + 40) + 8LL * i), *(PCWSTR *)(v14 + 8));
        psz[1] = 0;
        v11 = v10 != 0 ? 0x7FFFFFFF : 0;
        psz[0] = 0;
        v18 = 0;
        v16 = 0;
        v8 = STRW::Append((STRW *)&v16, *(const unsigned __int16 **)(*(_QWORD *)(v14 + 64) + 8LL * i));
        if ( v8 >= 0 )
        {
          v8 = STRW::Append((STRW *)&v16, L":");
          if ( v8 >= 0 )
          {
            v8 = STRW::Append((STRW *)&v16, *(const unsigned __int16 **)(*(_QWORD *)(v14 + 40) + 8LL * i));
            if ( v8 >= 0 )
            {
              v12 = &Str;
              if ( v16 )
                v12 = psz[0];
              v4 = SysAllocString(v12);
            }
          }
        }
        v16 = 0;
        BUFFER::ReleaseStorage((BUFFER *)psz);
        if ( v8 < 0 )
          goto LABEL_24;
        if ( !v4 )
          goto LABEL_9;
        if ( DPA_InsertPtr(v7, v11, v4) == -1 )
        {
          SysFreeString(v4);
          goto LABEL_9;
        }
        v4 = 0;
      }
      *a3 = v7;
      v7 = 0;
    }
    else
    {
LABEL_9:
      v8 = -2147024882;
    }
  }
LABEL_24:
  DPA_DestroyCallback(v7, _DPACallback_SysFreeString, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180064494  mov     [rsp-38h+arg_0], rbx
0x180064499  push    rbp
0x18006449a  push    rsi
0x18006449b  push    rdi
0x18006449c  push    r12
0x18006449e  push    r13
0x1800644a0  push    r14
0x1800644a2  push    r15
0x1800644a4  mov     rbp, rsp
0x1800644a7  sub     rsp, 80h
0x1800644ae  mov     rax, cs:__security_cookie
0x1800644b5  xor     rax, rsp
0x1800644b8  mov     [rbp+var_10], rax
0x1800644bc  mov     rax, [rdx]
0x1800644bf  lea     rcx, [rbp+var_50]
0x1800644c3  mov     r10, rdx
0x1800644c6  mov     [rsp+80h+var_60], rcx
0x1800644cb  xor     r14d, r14d
0x1800644ce  mov     [rbp+var_20], 3
0x1800644d5  mov     r13, r8
0x1800644d8  mov     [rbp+var_1C], 3003001Fh
0x1800644df  mov     rax, [rax+28h]
0x1800644e3  lea     r9, [rbp+var_48]
0x1800644e7  mov     r8d, 80000000h
0x1800644ed  mov     [rbp+var_18], 3A56101Fh
0x1800644f4  lea     rdx, [rbp+var_20]
0x1800644f8  mov     [rbp+var_14], 3A54101Fh
0x1800644ff  mov     rcx, r10
0x180064502  mov     [rbp+var_48], r14d
0x180064506  mov     [rbp+var_50], r14
0x18006450a  mov     edi, r14d
0x18006450d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064512  mov     ebx, eax
0x180064514  test    eax, eax
0x180064516  js      loc_180064672
0x18006451c  mov     rcx, [rbp+var_50]
0x180064520  cmp     word ptr [rcx], 0Ah
0x180064524  jz      loc_180064672
0x18006452a  cmp     [rcx+8], r14
0x18006452e  jz      loc_180064672
0x180064534  cmp     word ptr [rcx+18h], 0Ah
0x180064539  jz      loc_180064672
0x18006453f  cmp     [rcx+28h], r14
0x180064543  jz      loc_180064672
0x180064549  cmp     word ptr [rcx+30h], 0Ah
0x18006454e  jz      loc_180064672
0x180064554  cmp     [rcx+40h], r14
0x180064558  jz      loc_180064672
0x18006455e  mov     ecx, [rcx+20h]; cItemGrow
0x180064561  call    cs:__imp_DPA_Create
0x180064567  mov     rdi, rax
0x18006456a  test    rax, rax
0x18006456d  jnz     short loc_180064579
0x18006456f  mov     ebx, 8007000Eh
0x180064574  jmp     loc_180064672
0x180064579  mov     esi, r14d
0x18006457c  mov     rdx, [rbp+var_50]
0x180064580  cmp     esi, [rdx+20h]
0x180064583  jnb     loc_18006466B
0x180064589  mov     rcx, [rdx+28h]
0x18006458d  mov     rdx, [rdx+8]; psz2
0x180064591  mov     r15d, esi
0x180064594  mov     rcx, [rcx+r15*8]; psz1
0x180064598  call    cs:__imp_StrCmpIW
0x18006459e  mov     ecx, r14d
0x1800645a1  sub     ecx, eax
0x1800645a3  neg     ecx
0x1800645a5  lea     rcx, [rbp+var_40]; this
0x1800645a9  sbb     r12d, r12d
0x1800645ac  xor     eax, eax
0x1800645ae  mov     [rbp+var_30], rax
0x1800645b2  btr     r12d, 1Fh
0x1800645b7  mov     [rbp+psz], rax
0x1800645bb  mov     [rbp+var_28], eax
0x1800645be  mov     [rbp+var_40], eax
0x1800645c1  mov     rax, [rbp+var_50]
0x1800645c5  mov     rdx, [rax+40h]
0x1800645c9  mov     rdx, [rdx+r15*8]; unsigned __int16 *
0x1800645cd  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x1800645d2  mov     ebx, eax
0x1800645d4  test    eax, eax
0x1800645d6  js      short loc_180064622
0x1800645d8  lea     rdx, asc_18009D9D8; ":"
0x1800645df  lea     rcx, [rbp+var_40]; this
0x1800645e3  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x1800645e8  mov     ebx, eax
0x1800645ea  test    eax, eax
0x1800645ec  js      short loc_180064622
0x1800645ee  mov     rax, [rbp+var_50]
0x1800645f2  lea     rcx, [rbp+var_40]; this
0x1800645f6  mov     rdx, [rax+28h]
0x1800645fa  mov     rdx, [rdx+r15*8]; unsigned __int16 *
0x1800645fe  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180064603  mov     ebx, eax
0x180064605  test    eax, eax
0x180064607  js      short loc_180064622
0x180064609  cmp     [rbp+var_40], 0
0x18006460d  lea     rcx, Str
0x180064614  cmovnz  rcx, [rbp+psz]; psz
0x180064619  call    cs:__imp_SysAllocString
0x18006461f  mov     r14, rax
0x180064622  lea     rcx, [rbp+psz]; this
0x180064626  mov     [rbp+var_40], 0
0x18006462d  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x180064632  test    ebx, ebx
0x180064634  js      short loc_180064672
0x180064636  test    r14, r14
0x180064639  jz      loc_18006456F
0x18006463f  mov     r8, r14; p
0x180064642  mov     edx, r12d; i
0x180064645  mov     rcx, rdi; hdpa
0x180064648  call    cs:__imp_DPA_InsertPtr
0x18006464e  cmp     eax, 0FFFFFFFFh
0x180064651  jz      short loc_18006465D
0x180064653  inc     esi
0x180064655  xor     r14d, r14d
0x180064658  jmp     loc_18006457C
0x18006465d  mov     rcx, r14; bstrString
0x180064660  call    cs:__imp_SysFreeString
0x180064666  jmp     loc_18006456F
0x18006466b  mov     [r13+0], rdi
0x18006466f  mov     rdi, r14
0x180064672  xor     r8d, r8d; pData
0x180064675  lea     rdx, ?_DPACallback_SysFreeString@@YAHPEAX0@Z; pfnCB
0x18006467c  mov     rcx, rdi; hdpa
0x18006467f  call    cs:__imp_DPA_DestroyCallback
0x180064685  mov     eax, ebx
0x180064687  mov     rcx, [rbp+var_10]
0x18006468b  xor     rcx, rsp; StackCookie
0x18006468e  call    __security_check_cookie
0x180064693  mov     rbx, [rsp+80h+arg_0]
0x18006469b  add     rsp, 80h
0x1800646a2  pop     r15
0x1800646a4  pop     r14
0x1800646a6  pop     r13
0x1800646a8  pop     r12
0x1800646aa  pop     rdi
0x1800646ab  pop     rsi
0x1800646ac  pop     rbp
0x1800646ad  retn
```
