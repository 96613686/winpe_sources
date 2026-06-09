# CdsValues::TransformAtomName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)

- ea: `0x14000b824`
- end: `0x14000ba63`
- name: `?TransformAtomName@CdsValues@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@AEAV23@@Z`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000b5c4`

## callees

- `0x140007020`
- `0x14000b824`
- `0x14000c780`
- `0x14003e5f4`
- `0x140047798`
- `0x140054534`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14000b87e`
- `KERNEL32!CompareStringW` at `0x14000b8a9`
- `KERNEL32!CompareStringW` at `0x14000b8d4`
- `KERNEL32!CompareStringW` at `0x14000b8ff`
- `KERNEL32!CompareStringW` at `0x14000b92a`
- `KERNEL32!CompareStringW` at `0x14000b955`
- `KERNEL32!CompareStringW` at `0x14000b87e`
- `KERNEL32!CompareStringW` at `0x14000b8a9`
- `KERNEL32!CompareStringW` at `0x14000b8d4`
- `KERNEL32!CompareStringW` at `0x14000b8ff`
- `KERNEL32!CompareStringW` at `0x14000b92a`
- `KERNEL32!CompareStringW` at `0x14000b955`

## pseudocode

```c
__int64 __fastcall CdsValues::TransformAtomName(PCNZWCH *a1, __int64 *a2)
{
  unsigned int v4; // esi
  const wchar_t *v6; // rdx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_81d09b2d3d4339b10b2aaeca9bc79c32_Traceguids, *a1);
  }
  ATL::CSimpleStringT<unsigned short,0>::Empty(a2);
  if ( CompareStringW(0x7Fu, 1u, *a1, -1, L"object@ID", -1) == 2 )
  {
    v6 = L"@ID";
  }
  else if ( CompareStringW(0x7Fu, 1u, *a1, -1, L"item@refID", -1) == 2 )
  {
    v6 = L"@refID";
  }
  else if ( CompareStringW(0x7Fu, 1u, *a1, -1, L"object@parentID", -1) == 2 )
  {
    v6 = L"@parentID";
  }
  else if ( CompareStringW(0x7Fu, 1u, *a1, -1, L"Container@ChildCount", -1) == 2 )
  {
    v6 = L"@ChildCount";
  }
  else if ( CompareStringW(0x7Fu, 1u, *a1, -1, L"Container@Searchable", -1) == 2 )
  {
    v6 = L"@Searchable";
  }
  else
  {
    if ( CompareStringW(0x7Fu, 1u, *a1, -1, L"Object@restricted", -1) != 2 )
    {
      v4 = -2147023728;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_81d09b2d3d4339b10b2aaeca9bc79c32_Traceguids);
      return v4;
    }
    v6 = L"@restricted";
  }
  v4 = 0;
  ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v6);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), *a2);
  }
  return v4;
}

```

## disassembly

```asm
0x14000b824  push    rbx
0x14000b826  push    rsi
0x14000b827  push    rdi
0x14000b828  push    r12
0x14000b82a  push    r14
0x14000b82c  push    r15
0x14000b82e  sub     rsp, 38h
0x14000b832  mov     rbx, rdx
0x14000b835  mov     rdi, rcx
0x14000b838  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b83f  lea     r12, WPP_GLOBAL_Control
0x14000b846  cmp     rcx, r12
0x14000b849  jnz     loc_14000B989
0x14000b84f  mov     rcx, rbx
0x14000b852  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14000b857  mov     r8, [rdi]; lpString1
0x14000b85a  lea     rax, aObjectId; "object@ID"
0x14000b861  or      esi, 0FFFFFFFFh
0x14000b864  mov     [rsp+68h+cchCount2], esi; cchCount2
0x14000b868  mov     r9d, esi; cchCount1
0x14000b86b  mov     [rsp+68h+lpString2], rax; lpString2
0x14000b870  lea     r14d, [rsi+2]
0x14000b874  lea     r15d, [r14+7Eh]
0x14000b878  mov     edx, r14d; dwCmpFlags
0x14000b87b  mov     ecx, r15d; Locale
0x14000b87e  call    cs:__imp_CompareStringW
0x14000b884  cmp     eax, 2
0x14000b887  jz      loc_14000B9BA
0x14000b88d  mov     r8, [rdi]; lpString1
0x14000b890  lea     rax, aItemRefid; "item@refID"
0x14000b897  mov     [rsp+68h+cchCount2], esi; cchCount2
0x14000b89b  mov     r9d, esi; cchCount1
0x14000b89e  mov     edx, r14d; dwCmpFlags
0x14000b8a1  mov     [rsp+68h+lpString2], rax; lpString2
0x14000b8a6  mov     ecx, r15d; Locale
0x14000b8a9  call    cs:__imp_CompareStringW
0x14000b8af  cmp     eax, 2
0x14000b8b2  jz      loc_14000B9C3
0x14000b8b8  mov     r8, [rdi]; lpString1
0x14000b8bb  lea     rax, aObjectParentid; "object@parentID"
0x14000b8c2  mov     [rsp+68h+cchCount2], esi; cchCount2
0x14000b8c6  mov     r9d, esi; cchCount1
0x14000b8c9  mov     edx, r14d; dwCmpFlags
0x14000b8cc  mov     [rsp+68h+lpString2], rax; lpString2
0x14000b8d1  mov     ecx, r15d; Locale
0x14000b8d4  call    cs:__imp_CompareStringW
0x14000b8da  cmp     eax, 2
0x14000b8dd  jz      loc_14000B9CC
0x14000b8e3  mov     r8, [rdi]; lpString1
0x14000b8e6  lea     rax, aContainerChild; "Container@ChildCount"
0x14000b8ed  mov     [rsp+68h+cchCount2], esi; cchCount2
0x14000b8f1  mov     r9d, esi; cchCount1
0x14000b8f4  mov     edx, r14d; dwCmpFlags
0x14000b8f7  mov     [rsp+68h+lpString2], rax; lpString2
0x14000b8fc  mov     ecx, r15d; Locale
0x14000b8ff  call    cs:__imp_CompareStringW
0x14000b905  cmp     eax, 2
0x14000b908  jz      loc_14000B9D5
0x14000b90e  mov     r8, [rdi]; lpString1
0x14000b911  lea     rax, aContainerSearc; "Container@Searchable"
0x14000b918  mov     [rsp+68h+cchCount2], esi; cchCount2
0x14000b91c  mov     r9d, esi; cchCount1
0x14000b91f  mov     edx, r14d; dwCmpFlags
0x14000b922  mov     [rsp+68h+lpString2], rax; lpString2
0x14000b927  mov     ecx, r15d; Locale
0x14000b92a  call    cs:__imp_CompareStringW
0x14000b930  cmp     eax, 2
0x14000b933  jz      loc_14000B9DE
0x14000b939  mov     r8, [rdi]; lpString1
0x14000b93c  lea     rax, aObjectRestrict; "Object@restricted"
0x14000b943  mov     [rsp+68h+cchCount2], esi; cchCount2
0x14000b947  mov     r9d, esi; cchCount1
0x14000b94a  mov     edx, r14d; dwCmpFlags
0x14000b94d  mov     [rsp+68h+lpString2], rax; lpString2
0x14000b952  mov     ecx, r15d; Locale
0x14000b955  call    cs:__imp_CompareStringW
0x14000b95b  cmp     eax, 2
0x14000b95e  jz      loc_14000B9E7
0x14000b964  mov     esi, 80070490h
0x14000b969  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b970  cmp     rcx, r12
0x14000b973  jnz     loc_14000BA3F
0x14000b979  mov     eax, esi
0x14000b97b  add     rsp, 38h
0x14000b97f  pop     r15
0x14000b981  pop     r14
0x14000b983  pop     r12
0x14000b985  pop     rdi
0x14000b986  pop     rsi
0x14000b987  pop     rbx
0x14000b988  retn
0x14000b989  test    byte ptr [rcx+1Ch], 2
0x14000b98d  jz      loc_14000B84F
0x14000b993  cmp     byte ptr [rcx+19h], 5
0x14000b997  jb      loc_14000B84F
0x14000b99d  mov     r9, [rdi]
0x14000b9a0  lea     r8, WPP_81d09b2d3d4339b10b2aaeca9bc79c32_Traceguids
0x14000b9a7  mov     rcx, [rcx+10h]
0x14000b9ab  mov     edx, 20h ; ' '
0x14000b9b0  call    WPP_SF_S
0x14000b9b5  jmp     loc_14000B84F
0x14000b9ba  lea     rdx, aId_0; "@ID"
0x14000b9c1  jmp     short loc_14000B9EE
0x14000b9c3  lea     rdx, aRefid_0; "@refID"
0x14000b9ca  jmp     short loc_14000B9EE
0x14000b9cc  lea     rdx, aParentid; "@parentID"
0x14000b9d3  jmp     short loc_14000B9EE
0x14000b9d5  lea     rdx, aChildcount_0; "@ChildCount"
0x14000b9dc  jmp     short loc_14000B9EE
0x14000b9de  lea     rdx, aSearchable_0; "@Searchable"
0x14000b9e5  jmp     short loc_14000B9EE
0x14000b9e7  lea     rdx, aRestricted_0; "@restricted"
0x14000b9ee  mov     rcx, rbx
0x14000b9f1  xor     esi, esi
0x14000b9f3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x14000b9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b9ff  cmp     rcx, r12
0x14000ba02  jz      loc_14000B979
0x14000ba08  test    byte ptr [rcx+1Ch], 2
0x14000ba0c  jz      loc_14000B979
0x14000ba12  cmp     byte ptr [rcx+19h], 5
0x14000ba16  jb      loc_14000B979
0x14000ba1c  mov     rax, [rbx]
0x14000ba1f  lea     edx, [rsi+21h]
0x14000ba22  mov     r9, [rdi]
0x14000ba25  lea     r8, WPP_81d09b2d3d4339b10b2aaeca9bc79c32_Traceguids
0x14000ba2c  mov     rcx, [rcx+10h]; LoggerHandle
0x14000ba30  mov     [rsp+68h+lpString2], rax; __int64
0x14000ba35  call    WPP_SF_SS
0x14000ba3a  jmp     loc_14000B979
0x14000ba3f  test    byte ptr [rcx+1Ch], 2
0x14000ba43  jz      loc_14000B979
0x14000ba49  mov     rcx, [rcx+10h]
0x14000ba4d  lea     r8, WPP_81d09b2d3d4339b10b2aaeca9bc79c32_Traceguids
0x14000ba54  mov     edx, 22h ; '"'
0x14000ba59  call    WPP_SF_
0x14000ba5e  jmp     loc_14000B979
```
