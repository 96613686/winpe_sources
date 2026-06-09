# ATL::CComSafeArray<ushort *,8>::Add(ushort * const &,int)

- ea: `0x1800764bc`
- end: `0x18007659e`
- name: `?Add@?$CComSafeArray@PEAG$07@ATL@@QEAAJAEBQEAGH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180076620`

## callees

- `0x180007598`
- `0x1800764bc`
- `0x1800765a4`
- `0x180076890`
- `0x180076b50`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800764ec`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800764ec`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180076507`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18007656c`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180076507`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18007656c`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18007654d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18007654d`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18007655f`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18007655f`

## pseudocode

```c
HRESULT __fastcall ATL::CComSafeArray<unsigned short *,8>::Add(SAFEARRAY **a1, __int64 a2)
{
  SAFEARRAY *v4; // rax
  HRESULT result; // eax
  LONG LowerBound; // edi
  int Count; // eax
  SAFEARRAY *v8; // rcx
  int v9; // eax
  SAFEARRAYBOUND psaboundNew; // [rsp+30h] [rbp+8h] BYREF

  if ( *a1 )
    goto LABEL_5;
  psaboundNew = 0;
  v4 = SafeArrayCreate(8u, 1u, &psaboundNew);
  *a1 = v4;
  if ( !v4 )
    return -2147024882;
  result = SafeArrayLock(v4);
  if ( result >= 0 )
  {
LABEL_5:
    LowerBound = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(a1);
    Count = ATL::CComSafeArray<unsigned short *,8>::GetCount(a1);
    v8 = *a1;
    psaboundNew.cElements = Count + 1;
    psaboundNew.lLbound = LowerBound;
    if ( !v8 )
      ATL::AtlThrowImpl(-2147467259);
    if ( (v8->fFeatures & 0x10) != 0 )
    {
      return -2147467259;
    }
    else
    {
      result = SafeArrayUnlock(v8);
      if ( result >= 0 )
      {
        result = SafeArrayRedim(*a1, &psaboundNew);
        if ( result >= 0 )
        {
          result = SafeArrayLock(*a1);
          if ( result >= 0 )
          {
            v9 = ATL::CComSafeArray<unsigned short *,8>::GetCount(a1);
            return ATL::CComSafeArray<unsigned short *,8>::SetAt(a1, (unsigned int)(LowerBound + v9 - 1), a2);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800764bc  mov     rax, rsp
0x1800764bf  mov     [rax+10h], rbx
0x1800764c3  mov     [rax+18h], rsi
0x1800764c7  push    rdi
0x1800764c8  sub     rsp, 20h
0x1800764cc  cmp     qword ptr [rcx], 0
0x1800764d0  mov     rsi, rdx
0x1800764d3  mov     rbx, rcx
0x1800764d6  jnz     short loc_180076511
0x1800764d8  mov     ecx, 8; vt
0x1800764dd  mov     qword ptr [rax+8], 0
0x1800764e5  lea     r8, [rax+8]; rgsabound
0x1800764e9  lea     edx, [rcx-7]; cDims
0x1800764ec  call    cs:__imp_SafeArrayCreate
0x1800764f2  mov     [rbx], rax
0x1800764f5  test    rax, rax
0x1800764f8  jnz     short loc_180076504
0x1800764fa  mov     eax, 8007000Eh
0x1800764ff  jmp     loc_18007658E
0x180076504  mov     rcx, rax; psa
0x180076507  call    cs:__imp_SafeArrayLock
0x18007650d  test    eax, eax
0x18007650f  js      short loc_18007658E
0x180076511  mov     rcx, rbx
0x180076514  call    ?GetLowerBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetLowerBound(uint)
0x180076519  mov     rcx, rbx
0x18007651c  mov     edi, eax
0x18007651e  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x180076523  mov     rcx, [rbx]; psa
0x180076526  inc     eax
0x180076528  mov     [rsp+28h+psaboundNew.cElements], eax
0x18007652c  mov     [rsp+28h+psaboundNew.lLbound], edi
0x180076530  test    rcx, rcx
0x180076533  jnz     short loc_180076540
0x180076535  mov     ecx, 80004005h; int
0x18007653a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180076540  test    byte ptr [rcx+2], 10h
0x180076544  jz      short loc_18007654D
0x180076546  mov     eax, 80004005h
0x18007654b  jmp     short loc_18007658E
0x18007654d  call    cs:__imp_SafeArrayUnlock
0x180076553  test    eax, eax
0x180076555  js      short loc_18007658E
0x180076557  mov     rcx, [rbx]; psa
0x18007655a  lea     rdx, [rsp+28h+psaboundNew]; psaboundNew
0x18007655f  call    cs:__imp_SafeArrayRedim
0x180076565  test    eax, eax
0x180076567  js      short loc_18007658E
0x180076569  mov     rcx, [rbx]; psa
0x18007656c  call    cs:__imp_SafeArrayLock
0x180076572  test    eax, eax
0x180076574  js      short loc_18007658E
0x180076576  mov     rcx, rbx
0x180076579  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18007657e  mov     r8, rsi
0x180076581  mov     rcx, rbx
0x180076584  lea     edx, [rax-1]
0x180076587  add     edx, edi
0x180076589  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x18007658e  mov     rbx, [rsp+28h+arg_8]
0x180076593  mov     rsi, [rsp+28h+arg_10]
0x180076598  add     rsp, 20h
0x18007659c  pop     rdi
0x18007659d  retn
```
