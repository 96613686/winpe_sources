# SavedStateRepository::GetNode(ushort const *,tagVARIANT &)

- ea: `0x1401dac10`
- end: `0x1401daebe`
- name: `?GetNode@SavedStateRepository@@UEBAJPEBGAEAUtagVARIANT@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(SavedStateRepository *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1401daec4`

## callees

- `0x14003d828`
- `0x14011ea40`
- `0x1401dac10`
- `0x1401db1f0`
- `0x1402cb010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1401dae2d`
- `OLEAUT32!__imp_SysAllocString` at `0x1401dae2d`
- `OLEAUT32!__imp_SysStringLen` at `0x1401dae40`
- `OLEAUT32!__imp_SysStringLen` at `0x1401dae40`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1401dacf9`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1401dacf9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1401dad60`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1401dad60`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401dad20`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401dad20`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401dad44`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401dad44`

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
0x1401dac10  mov     [rsp-28h+arg_18], rbx
0x1401dac15  push    rbp
0x1401dac16  push    rsi
0x1401dac17  push    rdi
0x1401dac18  push    r14
0x1401dac1a  push    r15
0x1401dac1c  mov     rbp, rsp
0x1401dac1f  sub     rsp, 60h
0x1401dac23  mov     rax, cs:__security_cookie
0x1401dac2a  xor     rax, rsp
0x1401dac2d  mov     [rbp+var_8], rax
0x1401dac31  mov     rdi, r8
0x1401dac34  mov     r15, rdx
0x1401dac37  mov     r14, rcx
0x1401dac3a  mov     eax, [rcx+80h]
0x1401dac40  test    al, 1
0x1401dac42  jnz     short loc_1401DAC55
0x1401dac44  test    eax, 0FFFFFFFCh
0x1401dac49  ja      short loc_1401DAC55
0x1401dac4b  mov     ebx, 8000FFFFh
0x1401dac50  jmp     loc_1401DAE9B
0x1401dac55  xor     eax, eax
0x1401dac57  mov     [rbp+var_40], ax
0x1401dac5b  mov     rcx, [rcx+68h]
0x1401dac5f  mov     rax, [rcx]
0x1401dac62  lea     r8, [rbp+var_40]
0x1401dac66  mov     rax, [rax+0B0h]
0x1401dac6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401dac72  mov     ebx, eax
0x1401dac74  test    eax, eax
0x1401dac76  js      loc_1401DAE9B
0x1401dac7c  movzx   eax, [rbp+var_40]
0x1401dac80  cmp     eax, 5
0x1401dac83  jz      loc_1401DAE65
0x1401dac89  cmp     eax, 8
0x1401dac8c  jz      loc_1401DADE5
0x1401dac92  cmp     eax, 0Bh
0x1401dac95  jz      loc_1401DADA7
0x1401dac9b  cmp     eax, 14h
0x1401dac9e  jz      loc_1401DAD71
0x1401daca4  cmp     eax, 2011h
0x1401daca9  jz      short loc_1401DACB5
0x1401dacab  mov     ebx, 80070057h
0x1401dacb0  jmp     loc_1401DAE9B
0x1401dacb5  mov     [rbp+var_3C], 0
0x1401dacbc  mov     rcx, [r14+68h]
0x1401dacc0  mov     rax, [rcx]
0x1401dacc3  lea     r8, [rbp+var_3C]
0x1401dacc7  mov     rdx, r15
0x1401dacca  mov     rax, [rax+0A0h]
0x1401dacd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401dacd6  mov     ebx, eax
0x1401dacd8  test    eax, eax
0x1401dacda  js      loc_1401DAE9B
0x1401dace0  mov     eax, [rbp+var_3C]
0x1401dace3  mov     [rbp+rgsabound.cElements], eax
0x1401dace6  mov     [rbp+rgsabound.lLbound], 0
0x1401daced  mov     ecx, 11h; vt
0x1401dacf2  lea     r8, [rbp+rgsabound]; rgsabound
0x1401dacf6  lea     edx, [rcx-10h]; cDims
0x1401dacf9  call    cs:__imp_SafeArrayCreate
0x1401dad00  nop     dword ptr [rax+rax+00h]
0x1401dad05  mov     rsi, rax
0x1401dad08  test    rax, rax
0x1401dad0b  jz      loc_1401DAE94
0x1401dad11  mov     [rbp+ppvData], 0
0x1401dad19  lea     rdx, [rbp+ppvData]; ppvData
0x1401dad1d  mov     rcx, rax; psa
0x1401dad20  call    cs:__imp_SafeArrayAccessData
0x1401dad27  nop     dword ptr [rax+rax+00h]
0x1401dad2c  mov     r9d, [rbp+var_3C]; unsigned int
0x1401dad30  mov     r8, [rbp+ppvData]; void *
0x1401dad34  mov     rdx, r15; unsigned __int16 *
0x1401dad37  mov     rcx, r14; this
0x1401dad3a  call    ?ReadArray@SavedStateRepository@@UEBAJPEBGPEAXI@Z; SavedStateRepository::ReadArray(ushort const *,void *,uint)
0x1401dad3f  mov     ebx, eax
0x1401dad41  mov     rcx, rsi; psa
0x1401dad44  call    cs:__imp_SafeArrayUnaccessData
0x1401dad4b  nop     dword ptr [rax+rax+00h]
0x1401dad50  test    ebx, ebx
0x1401dad52  js      short loc_1401DAD5D
0x1401dad54  mov     [rdi+8], rsi
0x1401dad58  jmp     loc_1401DAE94
0x1401dad5d  mov     rcx, rsi; psa
0x1401dad60  call    cs:__imp_SafeArrayDestroy
0x1401dad67  nop     dword ptr [rax+rax+00h]
0x1401dad6c  jmp     loc_1401DAE9B
0x1401dad71  mov     [rbp+ppvData], 0
0x1401dad79  mov     rcx, [r14+68h]
0x1401dad7d  mov     rax, [rcx]
0x1401dad80  lea     r8, [rbp+ppvData]
0x1401dad84  mov     rdx, r15
0x1401dad87  mov     rax, [rax+50h]
0x1401dad8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401dad90  mov     ebx, eax
0x1401dad92  test    eax, eax
0x1401dad94  js      loc_1401DAE9B
0x1401dad9a  mov     rax, [rbp+ppvData]
0x1401dad9e  mov     [rdi+8], rax
0x1401dada2  jmp     loc_1401DAE94
0x1401dada7  mov     [rbp+var_3C], 0
0x1401dadae  mov     rcx, [r14+68h]
0x1401dadb2  mov     rax, [rcx]
0x1401dadb5  lea     r8, [rbp+var_3C]
0x1401dadb9  mov     rdx, r15
0x1401dadbc  mov     rax, [rax+68h]
0x1401dadc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401dadc5  mov     ebx, eax
0x1401dadc7  test    eax, eax
0x1401dadc9  js      loc_1401DAE9B
0x1401dadcf  cmp     [rbp+var_3C], 0
0x1401dadd3  jz      short loc_1401DADDA
0x1401dadd5  or      eax, 0FFFFFFFFh
0x1401dadd8  jmp     short loc_1401DADDC
0x1401dadda  xor     eax, eax
0x1401daddc  mov     [rdi+8], ax
0x1401dade0  jmp     loc_1401DAE94
0x1401dade5  xorps   xmm0, xmm0
0x1401dade8  movups  xmmword ptr [rbp+psz], xmm0
0x1401dadec  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1401dadf4  movdqu  [rbp+var_20], xmm1
0x1401dadf9  xor     eax, eax
0x1401dadfb  mov     word ptr [rbp+psz], ax
0x1401dadff  mov     rcx, [r14+68h]
0x1401dae03  mov     rax, [rcx]
0x1401dae06  lea     r8, [rbp+psz]
0x1401dae0a  mov     rdx, r15
0x1401dae0d  mov     rax, [rax+88h]
0x1401dae14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401dae19  mov     ebx, eax
0x1401dae1b  test    eax, eax
0x1401dae1d  js      short loc_1401DAE56
0x1401dae1f  lea     rcx, [rbp+psz]
0x1401dae23  cmp     qword ptr [rbp+var_20+8], 7
0x1401dae28  cmova   rcx, [rbp+psz]; psz
0x1401dae2d  call    cs:__imp_SysAllocString
0x1401dae34  nop     dword ptr [rax+rax+00h]
0x1401dae39  mov     [rdi+8], rax
0x1401dae3d  mov     rcx, rax; pbstr
0x1401dae40  call    cs:__imp_SysStringLen
0x1401dae47  nop     dword ptr [rax+rax+00h]
0x1401dae4c  mov     ecx, 8007000Eh
0x1401dae51  test    eax, eax
0x1401dae53  cmovz   ebx, ecx
0x1401dae56  lea     rcx, [rbp+psz]
0x1401dae5a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1401dae5f  test    ebx, ebx
0x1401dae61  js      short loc_1401DAE9B
0x1401dae63  jmp     short loc_1401DAE94
0x1401dae65  xorps   xmm0, xmm0
0x1401dae68  movsd   [rbp+ppvData], xmm0
0x1401dae6d  mov     rcx, [r14+68h]
0x1401dae71  mov     rax, [rcx]
0x1401dae74  lea     r8, [rbp+ppvData]
0x1401dae78  mov     rdx, r15
0x1401dae7b  mov     rax, [rax+78h]
0x1401dae7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401dae84  mov     ebx, eax
0x1401dae86  test    eax, eax
0x1401dae88  js      short loc_1401DAE9B
0x1401dae8a  movsd   xmm0, [rbp+ppvData]
0x1401dae8f  movsd   qword ptr [rdi+8], xmm0
0x1401dae94  movzx   eax, [rbp+var_40]
0x1401dae98  mov     [rdi], ax
0x1401dae9b  mov     eax, ebx
0x1401dae9d  mov     rcx, [rbp+var_8]
0x1401daea1  xor     rcx, rsp; StackCookie
0x1401daea4  call    __security_check_cookie
0x1401daea9  mov     rbx, [rsp+60h+arg_18]
0x1401daeb1  add     rsp, 60h
0x1401daeb5  pop     r15
0x1401daeb7  pop     r14
0x1401daeb9  pop     rdi
0x1401daeba  pop     rsi
0x1401daebb  pop     rbp
0x1401daebc  retn
```
