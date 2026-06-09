# SavedStateRepository::GetNode(ushort const *,tagVARIANT &)

- ea: `0x1401eb220`
- end: `0x1401eb4ce`
- name: `?GetNode@SavedStateRepository@@UEBAJPEBGAEAUtagVARIANT@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(SavedStateRepository *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1401eb4d4`

## callees

- `0x140031ca8`
- `0x140132960`
- `0x1401eb220`
- `0x1401eb800`
- `0x1402c2010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1401eb43d`
- `OLEAUT32!__imp_SysAllocString` at `0x1401eb43d`
- `OLEAUT32!__imp_SysStringLen` at `0x1401eb450`
- `OLEAUT32!__imp_SysStringLen` at `0x1401eb450`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1401eb309`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1401eb309`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1401eb370`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1401eb370`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401eb330`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401eb330`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401eb354`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401eb354`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SavedStateRepository::GetNode(
        SavedStateRepository *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  int v6; // eax
  int Array; // ebx
  SAFEARRAY *v8; // rax
  SAFEARRAY *v9; // rsi
  SHORT v10; // ax
  const OLECHAR *v11; // rcx
  OLECHAR *v12; // rax
  VARTYPE v14[2]; // [rsp+20h] [rbp-40h] BYREF
  unsigned int v15; // [rsp+24h] [rbp-3Ch] BYREF
  void *ppvData; // [rsp+28h] [rbp-38h] BYREF
  OLECHAR *psz[2]; // [rsp+30h] [rbp-30h] BYREF
  __m128i si128; // [rsp+40h] [rbp-20h]
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp-10h] BYREF

  v6 = *((_DWORD *)this + 32);
  if ( (v6 & 1) == 0 && (v6 & 0xFFFFFFFC) == 0 )
    return (unsigned int)-2147418113;
  v14[0] = 0;
  Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, VARTYPE *))(**((_QWORD **)this + 13) + 176LL))(
            *((_QWORD *)this + 13),
            a2,
            v14);
  if ( Array < 0 )
    return (unsigned int)Array;
  if ( v14[0] == 5 )
  {
    ppvData = 0;
    Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, void **))(**((_QWORD **)this + 13) + 120LL))(
              *((_QWORD *)this + 13),
              a2,
              &ppvData);
    if ( Array < 0 )
      return (unsigned int)Array;
    a3->llVal = (LONGLONG)ppvData;
    goto LABEL_32;
  }
  if ( v14[0] != 8 )
  {
    switch ( v14[0] )
    {
      case 0xBu:
        v15 = 0;
        Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 13)
                                                                                            + 104LL))(
                  *((_QWORD *)this + 13),
                  a2,
                  &v15);
        if ( Array < 0 )
          return (unsigned int)Array;
        if ( v15 )
          v10 = -1;
        else
          v10 = 0;
        a3->iVal = v10;
        break;
      case 0x14u:
        ppvData = 0;
        Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, void **))(**((_QWORD **)this + 13) + 80LL))(
                  *((_QWORD *)this + 13),
                  a2,
                  &ppvData);
        if ( Array < 0 )
          return (unsigned int)Array;
        a3->llVal = (LONGLONG)ppvData;
        break;
      case 0x2011u:
        v15 = 0;
        Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 13)
                                                                                            + 160LL))(
                  *((_QWORD *)this + 13),
                  a2,
                  &v15);
        if ( Array < 0 )
          return (unsigned int)Array;
        rgsabound.cElements = v15;
        rgsabound.lLbound = 0;
        v8 = SafeArrayCreate(0x11u, 1u, &rgsabound);
        v9 = v8;
        if ( v8 )
        {
          ppvData = 0;
          SafeArrayAccessData(v8, &ppvData);
          Array = SavedStateRepository::ReadArray(this, a2, ppvData, v15);
          SafeArrayUnaccessData(v9);
          if ( Array < 0 )
          {
            SafeArrayDestroy(v9);
            return (unsigned int)Array;
          }
          a3->llVal = (LONGLONG)v9;
        }
        break;
      default:
        return (unsigned int)-2147024809;
    }
LABEL_32:
    a3->vt = v14[0];
    return (unsigned int)Array;
  }
  *(_OWORD *)psz = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(psz[0]) = 0;
  Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, OLECHAR **))(**((_QWORD **)this + 13) + 136LL))(
            *((_QWORD *)this + 13),
            a2,
            psz);
  if ( Array >= 0 )
  {
    v11 = (const OLECHAR *)psz;
    if ( si128.m128i_i64[1] > 7uLL )
      v11 = psz[0];
    v12 = SysAllocString(v11);
    a3->llVal = (LONGLONG)v12;
    if ( !SysStringLen(v12) )
      Array = -2147024882;
  }
  std::wstring::_Tidy_deallocate(psz);
  if ( Array >= 0 )
    goto LABEL_32;
  return (unsigned int)Array;
}

```

## disassembly

```asm
0x1401eb220  mov     [rsp-28h+arg_18], rbx
0x1401eb225  push    rbp
0x1401eb226  push    rsi
0x1401eb227  push    rdi
0x1401eb228  push    r14
0x1401eb22a  push    r15
0x1401eb22c  mov     rbp, rsp
0x1401eb22f  sub     rsp, 60h
0x1401eb233  mov     rax, cs:__security_cookie
0x1401eb23a  xor     rax, rsp
0x1401eb23d  mov     [rbp+var_8], rax
0x1401eb241  mov     rdi, r8
0x1401eb244  mov     r15, rdx
0x1401eb247  mov     r14, rcx
0x1401eb24a  mov     eax, [rcx+80h]
0x1401eb250  test    al, 1
0x1401eb252  jnz     short loc_1401EB265
0x1401eb254  test    eax, 0FFFFFFFCh
0x1401eb259  ja      short loc_1401EB265
0x1401eb25b  mov     ebx, 8000FFFFh
0x1401eb260  jmp     loc_1401EB4AB
0x1401eb265  xor     eax, eax
0x1401eb267  mov     [rbp+var_40], ax
0x1401eb26b  mov     rcx, [rcx+68h]
0x1401eb26f  mov     rax, [rcx]
0x1401eb272  lea     r8, [rbp+var_40]
0x1401eb276  mov     rax, [rax+0B0h]
0x1401eb27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401eb282  mov     ebx, eax
0x1401eb284  test    eax, eax
0x1401eb286  js      loc_1401EB4AB
0x1401eb28c  movzx   eax, [rbp+var_40]
0x1401eb290  cmp     eax, 5
0x1401eb293  jz      loc_1401EB475
0x1401eb299  cmp     eax, 8
0x1401eb29c  jz      loc_1401EB3F5
0x1401eb2a2  cmp     eax, 0Bh
0x1401eb2a5  jz      loc_1401EB3B7
0x1401eb2ab  cmp     eax, 14h
0x1401eb2ae  jz      loc_1401EB381
0x1401eb2b4  cmp     eax, 2011h
0x1401eb2b9  jz      short loc_1401EB2C5
0x1401eb2bb  mov     ebx, 80070057h
0x1401eb2c0  jmp     loc_1401EB4AB
0x1401eb2c5  mov     [rbp+var_3C], 0
0x1401eb2cc  mov     rcx, [r14+68h]
0x1401eb2d0  mov     rax, [rcx]
0x1401eb2d3  lea     r8, [rbp+var_3C]
0x1401eb2d7  mov     rdx, r15
0x1401eb2da  mov     rax, [rax+0A0h]
0x1401eb2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401eb2e6  mov     ebx, eax
0x1401eb2e8  test    eax, eax
0x1401eb2ea  js      loc_1401EB4AB
0x1401eb2f0  mov     eax, [rbp+var_3C]
0x1401eb2f3  mov     [rbp+rgsabound.cElements], eax
0x1401eb2f6  mov     [rbp+rgsabound.lLbound], 0
0x1401eb2fd  mov     ecx, 11h; vt
0x1401eb302  lea     r8, [rbp+rgsabound]; rgsabound
0x1401eb306  lea     edx, [rcx-10h]; cDims
0x1401eb309  call    cs:__imp_SafeArrayCreate
0x1401eb310  nop     dword ptr [rax+rax+00h]
0x1401eb315  mov     rsi, rax
0x1401eb318  test    rax, rax
0x1401eb31b  jz      loc_1401EB4A4
0x1401eb321  mov     [rbp+ppvData], 0
0x1401eb329  lea     rdx, [rbp+ppvData]; ppvData
0x1401eb32d  mov     rcx, rax; psa
0x1401eb330  call    cs:__imp_SafeArrayAccessData
0x1401eb337  nop     dword ptr [rax+rax+00h]
0x1401eb33c  mov     r9d, [rbp+var_3C]; unsigned int
0x1401eb340  mov     r8, [rbp+ppvData]; void *
0x1401eb344  mov     rdx, r15; unsigned __int16 *
0x1401eb347  mov     rcx, r14; this
0x1401eb34a  call    ?ReadArray@SavedStateRepository@@UEBAJPEBGPEAXI@Z; SavedStateRepository::ReadArray(ushort const *,void *,uint)
0x1401eb34f  mov     ebx, eax
0x1401eb351  mov     rcx, rsi; psa
0x1401eb354  call    cs:__imp_SafeArrayUnaccessData
0x1401eb35b  nop     dword ptr [rax+rax+00h]
0x1401eb360  test    ebx, ebx
0x1401eb362  js      short loc_1401EB36D
0x1401eb364  mov     [rdi+8], rsi
0x1401eb368  jmp     loc_1401EB4A4
0x1401eb36d  mov     rcx, rsi; psa
0x1401eb370  call    cs:__imp_SafeArrayDestroy
0x1401eb377  nop     dword ptr [rax+rax+00h]
0x1401eb37c  jmp     loc_1401EB4AB
0x1401eb381  mov     [rbp+ppvData], 0
0x1401eb389  mov     rcx, [r14+68h]
0x1401eb38d  mov     rax, [rcx]
0x1401eb390  lea     r8, [rbp+ppvData]
0x1401eb394  mov     rdx, r15
0x1401eb397  mov     rax, [rax+50h]
0x1401eb39b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401eb3a0  mov     ebx, eax
0x1401eb3a2  test    eax, eax
0x1401eb3a4  js      loc_1401EB4AB
0x1401eb3aa  mov     rax, [rbp+ppvData]
0x1401eb3ae  mov     [rdi+8], rax
0x1401eb3b2  jmp     loc_1401EB4A4
0x1401eb3b7  mov     [rbp+var_3C], 0
0x1401eb3be  mov     rcx, [r14+68h]
0x1401eb3c2  mov     rax, [rcx]
0x1401eb3c5  lea     r8, [rbp+var_3C]
0x1401eb3c9  mov     rdx, r15
0x1401eb3cc  mov     rax, [rax+68h]
0x1401eb3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401eb3d5  mov     ebx, eax
0x1401eb3d7  test    eax, eax
0x1401eb3d9  js      loc_1401EB4AB
0x1401eb3df  cmp     [rbp+var_3C], 0
0x1401eb3e3  jz      short loc_1401EB3EA
0x1401eb3e5  or      eax, 0FFFFFFFFh
0x1401eb3e8  jmp     short loc_1401EB3EC
0x1401eb3ea  xor     eax, eax
0x1401eb3ec  mov     [rdi+8], ax
0x1401eb3f0  jmp     loc_1401EB4A4
0x1401eb3f5  xorps   xmm0, xmm0
0x1401eb3f8  movups  xmmword ptr [rbp+psz], xmm0
0x1401eb3fc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1401eb404  movdqu  [rbp+var_20], xmm1
0x1401eb409  xor     eax, eax
0x1401eb40b  mov     word ptr [rbp+psz], ax
0x1401eb40f  mov     rcx, [r14+68h]
0x1401eb413  mov     rax, [rcx]
0x1401eb416  lea     r8, [rbp+psz]
0x1401eb41a  mov     rdx, r15
0x1401eb41d  mov     rax, [rax+88h]
0x1401eb424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401eb429  mov     ebx, eax
0x1401eb42b  test    eax, eax
0x1401eb42d  js      short loc_1401EB466
0x1401eb42f  lea     rcx, [rbp+psz]
0x1401eb433  cmp     qword ptr [rbp+var_20+8], 7
0x1401eb438  cmova   rcx, [rbp+psz]; psz
0x1401eb43d  call    cs:__imp_SysAllocString
0x1401eb444  nop     dword ptr [rax+rax+00h]
0x1401eb449  mov     [rdi+8], rax
0x1401eb44d  mov     rcx, rax; pbstr
0x1401eb450  call    cs:__imp_SysStringLen
0x1401eb457  nop     dword ptr [rax+rax+00h]
0x1401eb45c  mov     ecx, 8007000Eh
0x1401eb461  test    eax, eax
0x1401eb463  cmovz   ebx, ecx
0x1401eb466  lea     rcx, [rbp+psz]
0x1401eb46a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1401eb46f  test    ebx, ebx
0x1401eb471  js      short loc_1401EB4AB
0x1401eb473  jmp     short loc_1401EB4A4
0x1401eb475  xorps   xmm0, xmm0
0x1401eb478  movsd   [rbp+ppvData], xmm0
0x1401eb47d  mov     rcx, [r14+68h]
0x1401eb481  mov     rax, [rcx]
0x1401eb484  lea     r8, [rbp+ppvData]
0x1401eb488  mov     rdx, r15
0x1401eb48b  mov     rax, [rax+78h]
0x1401eb48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401eb494  mov     ebx, eax
0x1401eb496  test    eax, eax
0x1401eb498  js      short loc_1401EB4AB
0x1401eb49a  movsd   xmm0, [rbp+ppvData]
0x1401eb49f  movsd   qword ptr [rdi+8], xmm0
0x1401eb4a4  movzx   eax, [rbp+var_40]
0x1401eb4a8  mov     [rdi], ax
0x1401eb4ab  mov     eax, ebx
0x1401eb4ad  mov     rcx, [rbp+var_8]
0x1401eb4b1  xor     rcx, rsp; StackCookie
0x1401eb4b4  call    __security_check_cookie
0x1401eb4b9  mov     rbx, [rsp+60h+arg_18]
0x1401eb4c1  add     rsp, 60h
0x1401eb4c5  pop     r15
0x1401eb4c7  pop     r14
0x1401eb4c9  pop     rdi
0x1401eb4ca  pop     rsi
0x1401eb4cb  pop     rbp
0x1401eb4cc  retn
```
