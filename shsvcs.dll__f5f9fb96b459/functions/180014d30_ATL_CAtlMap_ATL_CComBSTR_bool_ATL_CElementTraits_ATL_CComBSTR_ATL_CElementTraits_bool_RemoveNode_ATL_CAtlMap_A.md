# ATL::CAtlMap<ATL::CComBSTR,bool,ATL::CElementTraits<ATL::CComBSTR>,ATL::CElementTraits<bool>>::RemoveNode(ATL::CAtlMap<ATL::CComBSTR,bool,ATL::CElementTraits<ATL::CComBSTR>,ATL::CElementTraits<bool>>::CNode *,ATL::CAtlMap<ATL::CComBSTR,bool,ATL::CElementTraits<ATL::CComBSTR>,ATL::CElementTraits<bool>>::CNode *)

- ea: `0x180014d30`
- end: `0x180014dcb`
- name: `?RemoveNode@?$CAtlMap@VCComBSTR@ATL@@_NV?$CElementTraits@VCComBSTR@ATL@@@2@V?$CElementTraits@_N@2@@ATL@@AEAAXPEAVCNode@12@0@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006750`

## callees

- `0x180014d30`
- `0x1800194ec`
- `0x18002ef9c`
- `0x18002f380`
- `0x18002f56c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180014d60`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d60`

## pseudocode

```c
void __fastcall ATL::CAtlMap<ATL::CComBSTR,bool,ATL::CElementTraits<ATL::CComBSTR>,ATL::CElementTraits<bool>>::RemoveNode(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  unsigned __int64 v5; // rdx
  unsigned int v6; // eax

  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  if ( a3 )
    *(_QWORD *)(a3 + 16) = *(_QWORD *)(a2 + 16);
  else
    *(_QWORD *)(*(_QWORD *)a1 + 8LL * (unsigned int)(*(_DWORD *)(a2 + 24) % *(_DWORD *)(a1 + 16))) = *(_QWORD *)(a2 + 16);
  SysFreeString(*(BSTR *)a2);
  *(_QWORD *)(a2 + 16) = *(_QWORD *)(a1 + 64);
  v5 = --*(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 64) = a2;
  if ( v5 < *(_QWORD *)(a1 + 40) && !*(_DWORD *)(a1 + 48) )
  {
    v6 = ATL::CAtlMap<_GUID,HDEVQUERY__ *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<HDEVQUERY__ *>>::PickSize(
           a1,
           v5);
    ATL::CAtlMap<ATL::CComBSTR,bool,ATL::CElementTraits<ATL::CComBSTR>,ATL::CElementTraits<bool>>::Rehash(a1, v6);
  }
  if ( !*(_QWORD *)(a1 + 8) )
    ATL::CAtlMap<ATL::CComBSTR,bool,ATL::CElementTraits<ATL::CComBSTR>,ATL::CElementTraits<bool>>::FreePlexes(a1);
}

```

## disassembly

```asm
0x180014d30  mov     [rsp+arg_0], rbx
0x180014d35  push    rdi
0x180014d36  sub     rsp, 20h
0x180014d3a  mov     rdi, rdx
0x180014d3d  mov     rbx, rcx
0x180014d40  test    rdx, rdx
0x180014d43  jz      short loc_180014D92
0x180014d45  test    r8, r8
0x180014d48  jnz     short loc_180014D9D
0x180014d4a  mov     eax, [rdi+18h]
0x180014d4d  xor     edx, edx
0x180014d4f  div     dword ptr [rcx+10h]
0x180014d52  mov     rcx, [rcx]
0x180014d55  mov     rax, [rdi+10h]
0x180014d59  mov     [rcx+rdx*8], rax
0x180014d5d  mov     rcx, [rdi]; bstrString
0x180014d60  call    cs:__imp_SysFreeString
0x180014d66  mov     rax, [rbx+40h]
0x180014d6a  mov     [rdi+10h], rax
0x180014d6e  dec     qword ptr [rbx+8]
0x180014d72  mov     rdx, [rbx+8]
0x180014d76  mov     [rbx+40h], rdi
0x180014d7a  cmp     rdx, [rbx+28h]
0x180014d7e  jb      short loc_180014DA7
0x180014d80  cmp     qword ptr [rbx+8], 0
0x180014d85  jz      short loc_180014DC1
0x180014d87  mov     rbx, [rsp+28h+arg_0]
0x180014d8c  add     rsp, 20h
0x180014d90  pop     rdi
0x180014d91  retn
0x180014d92  mov     ecx, 80004005h; int
0x180014d97  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180014d9d  mov     rax, [rdx+10h]
0x180014da1  mov     [r8+10h], rax
0x180014da5  jmp     short loc_180014D5D
0x180014da7  cmp     dword ptr [rbx+30h], 0
0x180014dab  jnz     short loc_180014D80
0x180014dad  mov     rcx, rbx
0x180014db0  call    ?PickSize@?$CAtlMap@U_GUID@@PEAUHDEVQUERY__@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAUHDEVQUERY__@@@4@@ATL@@AEBAI_K@Z; ATL::CAtlMap<_GUID,HDEVQUERY__ *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<HDEVQUERY__ *>>::PickSize(unsigned __int64)
0x180014db5  mov     edx, eax
0x180014db7  mov     rcx, rbx
0x180014dba  call    ?Rehash@?$CAtlMap@VCComBSTR@ATL@@_NV?$CElementTraits@VCComBSTR@ATL@@@2@V?$CElementTraits@_N@2@@ATL@@QEAAXI@Z; ATL::CAtlMap<ATL::CComBSTR,bool,ATL::CElementTraits<ATL::CComBSTR>,ATL::CElementTraits<bool>>::Rehash(uint)
0x180014dbf  jmp     short loc_180014D80
0x180014dc1  mov     rcx, rbx
0x180014dc4  call    ?FreePlexes@?$CAtlMap@VCComBSTR@ATL@@_NV?$CElementTraits@VCComBSTR@ATL@@@2@V?$CElementTraits@_N@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CComBSTR,bool,ATL::CElementTraits<ATL::CComBSTR>,ATL::CElementTraits<bool>>::FreePlexes(void)
0x180014dc9  jmp     short loc_180014D87
```
