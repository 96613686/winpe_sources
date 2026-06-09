# ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(unsigned __int64,int)

- ea: `0x180011418`
- end: `0x1800114b7`
- name: `?SetCount@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAA_N_KH@Z`
- size: `159`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000fd20`
- `0x1800105cc`
- `0x180014840`
- `0x18002e24d`

## callees

- `0x18000d5d0`
- `0x18000d60c`
- `0x18000fa90`
- `0x180011418`

## import_xrefs

- `msvcrt!free` at `0x180011441`
- `msvcrt!free` at `0x180011441`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(
        __int64 a1,
        size_t a2)
{
  size_t v2; // rdi
  void *v4; // rcx
  size_t v5; // r8
  size_t v6; // rdx
  __int64 v7; // rcx
  char result; // al
  __int64 v9; // rcx

  v2 = a2;
  if ( a2 )
  {
    if ( a2 > *(_QWORD *)(a1 + 16) )
    {
      result = ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::GrowBuffer(
                 a1,
                 a2);
      if ( !result )
        return result;
      v9 = *(_QWORD *)(a1 + 8);
      v6 = v2 - v9;
      v7 = *(_QWORD *)a1 + 8 * v9;
    }
    else
    {
      v5 = *(_QWORD *)(a1 + 8);
      if ( a2 <= v5 )
      {
        if ( a2 < v5 )
          ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::CallDestructors(
            *(_QWORD *)a1 + 8 * a2,
            v5 - a2);
        goto LABEL_13;
      }
      v6 = a2 - v5;
      v7 = *(_QWORD *)a1 + 8 * v5;
    }
    ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::CallConstructors(v7, v6);
  }
  else
  {
    v4 = *(void **)a1;
    if ( v4 )
    {
      ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::CallDestructors(
        v4,
        *(_QWORD *)(a1 + 8));
      free(*(void **)a1);
      *(_QWORD *)a1 = 0;
    }
    *(_QWORD *)(a1 + 16) = 0;
    v2 = 0;
  }
LABEL_13:
  *(_QWORD *)(a1 + 8) = v2;
  return 1;
}

```

## disassembly

```asm
0x180011418  mov     [rsp+arg_0], rbx
0x18001141d  push    rdi
0x18001141e  sub     rsp, 20h
0x180011422  mov     rdi, rdx
0x180011425  mov     rbx, rcx
0x180011428  test    rdx, rdx
0x18001142b  jnz     short loc_180011456
0x18001142d  mov     rcx, [rcx]
0x180011430  test    rcx, rcx
0x180011433  jz      short loc_18001144A
0x180011435  mov     rdx, [rbx+8]
0x180011439  call    ?CallDestructors@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@CAXPEAV?$CComPtr@VCUICommand@@@2@_K@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::CallDestructors(ATL::CComPtr<CUICommand> *,unsigned __int64)
0x18001143e  mov     rcx, [rbx]; Block
0x180011441  call    cs:__imp_free
0x180011447  mov     [rbx], rdi
0x18001144a  mov     qword ptr [rbx+10h], 0
0x180011452  xor     edi, edi
0x180011454  jmp     short loc_1800114A6
0x180011456  cmp     rdi, [rcx+10h]
0x18001145a  ja      short loc_180011487
0x18001145c  mov     r8, [rcx+8]
0x180011460  cmp     rdi, r8
0x180011463  jbe     short loc_180011471
0x180011465  mov     rax, [rcx]
0x180011468  sub     rdx, r8
0x18001146b  lea     rcx, [rax+r8*8]
0x18001146f  jmp     short loc_1800114A1
0x180011471  jnb     short loc_1800114A6
0x180011473  mov     rax, [rcx]
0x180011476  sub     r8, rdi
0x180011479  lea     rcx, [rax+rdx*8]
0x18001147d  mov     rdx, r8
0x180011480  call    ?CallDestructors@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@CAXPEAV?$CComPtr@VCUICommand@@@2@_K@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::CallDestructors(ATL::CComPtr<CUICommand> *,unsigned __int64)
0x180011485  jmp     short loc_1800114A6
0x180011487  call    ?GrowBuffer@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::GrowBuffer(unsigned __int64)
0x18001148c  test    al, al
0x18001148e  jz      short loc_1800114AC
0x180011490  mov     rcx, [rbx+8]
0x180011494  mov     rdx, rdi
0x180011497  mov     rax, [rbx]
0x18001149a  sub     rdx, rcx
0x18001149d  lea     rcx, [rax+rcx*8]
0x1800114a1  call    ?CallConstructors@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@CAXPEAV?$CComPtr@VCUICommand@@@2@_K@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::CallConstructors(ATL::CComPtr<CUICommand> *,unsigned __int64)
0x1800114a6  mov     [rbx+8], rdi
0x1800114aa  mov     al, 1
0x1800114ac  mov     rbx, [rsp+28h+arg_0]
0x1800114b1  add     rsp, 20h
0x1800114b5  pop     rdi
0x1800114b6  retn
```
