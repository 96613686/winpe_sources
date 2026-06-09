# CShellPropertyThunk::ObjectIDSearchThunk(CdsBinaryOpQuery const *,IHMEMediaContainer *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)

- ea: `0x140082150`
- end: `0x140082224`
- name: `?ObjectIDSearchThunk@CShellPropertyThunk@@CAJPEBVCdsBinaryOpQuery@@PEAUIHMEMediaContainer@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x140015100`
- `0x140081c6c`
- `0x140082150`
- `0x14009e010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400821fa`
- `ole32!CoTaskMemFree` at `0x140082205`
- `ole32!CoTaskMemFree` at `0x1400821fa`
- `ole32!CoTaskMemFree` at `0x140082205`

## pseudocode

```c
__int64 __fastcall CShellPropertyThunk::ObjectIDSearchThunk(__int64 a1, __int64 a2, __int64 *a3)
{
  unsigned __int16 *v5; // rcx
  int ItemIDFromObjectID; // ebx
  __int64 v7; // rax
  char *v8; // r8
  int v9; // edx
  int v10; // ecx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v13; // [rsp+48h] [rbp+20h] BYREF

  if ( *(_DWORD *)(a1 + 36) == 1 )
  {
    v5 = *(unsigned __int16 **)(a1 + 40);
    pv = 0;
    v13 = 0;
    ItemIDFromObjectID = CShellPropertyThunk::GetItemIDFromObjectID(v5, &pv, &v13);
    if ( ItemIDFromObjectID < 0 )
      goto LABEL_8;
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 56LL))(a2);
    v8 = (char *)pv - v7;
    do
    {
      v9 = *(unsigned __int16 *)&v8[v7];
      v10 = *(unsigned __int16 *)v7 - v9;
      if ( v10 )
        break;
      v7 += 2;
    }
    while ( v9 );
    if ( v10 )
    {
LABEL_8:
      ATL::CSimpleStringT<unsigned short,0>::Append(a3, L"System.Search.EntryID IS NULL");
      ItemIDFromObjectID = 0;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::Append(
        a3,
        L"System.Search.EntryID IS NOT NULL AND System.Search.EntryID = ");
      ATL::CSimpleStringT<unsigned short,0>::Append(a3, v13);
    }
    CoTaskMemFree(pv);
    CoTaskMemFree(v13);
  }
  else
  {
    return (unsigned int)-2147220628;
  }
  return (unsigned int)ItemIDFromObjectID;
}

```

## disassembly

```asm
0x140082150  mov     rax, rsp
0x140082153  mov     [rax+10h], rbx
0x140082157  mov     [rax+18h], rsi
0x14008215b  push    rdi
0x14008215c  sub     rsp, 20h
0x140082160  cmp     dword ptr [rcx+24h], 1
0x140082164  mov     rdi, r8
0x140082167  mov     rsi, rdx
0x14008216a  jnz     loc_14008220D
0x140082170  mov     rcx, [rcx+28h]; unsigned __int16 *
0x140082174  lea     r8, [rax+20h]; unsigned __int16 **
0x140082178  lea     rdx, [rax+8]; unsigned __int16 **
0x14008217c  mov     qword ptr [rax+8], 0
0x140082184  mov     qword ptr [rax+20h], 0
0x14008218c  call    ?GetItemIDFromObjectID@CShellPropertyThunk@@SAJPEBGPEAPEAG1@Z; CShellPropertyThunk::GetItemIDFromObjectID(ushort const *,ushort * *,ushort * *)
0x140082191  mov     ebx, eax
0x140082193  test    eax, eax
0x140082195  js      short loc_1400821E4
0x140082197  mov     rcx, [rsi]
0x14008219a  mov     rax, [rcx+38h]
0x14008219e  mov     rcx, rsi
0x1400821a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400821a6  mov     r8, [rsp+28h+pv]
0x1400821ab  sub     r8, rax
0x1400821ae  movzx   ecx, word ptr [rax]
0x1400821b1  movzx   edx, word ptr [rax+r8]
0x1400821b6  sub     ecx, edx
0x1400821b8  jnz     short loc_1400821C2
0x1400821ba  add     rax, 2
0x1400821be  test    edx, edx
0x1400821c0  jnz     short loc_1400821AE
0x1400821c2  test    ecx, ecx
0x1400821c4  jnz     short loc_1400821E4
0x1400821c6  lea     rdx, aSystemSearchEn_4; "System.Search.EntryID IS NOT NULL AND S"...
0x1400821cd  mov     rcx, rdi
0x1400821d0  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1400821d5  mov     rdx, [rsp+28h+arg_18]
0x1400821da  mov     rcx, rdi
0x1400821dd  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1400821e2  jmp     short loc_1400821F5
0x1400821e4  lea     rdx, aSystemSearchEn; "System.Search.EntryID IS NULL"
0x1400821eb  mov     rcx, rdi
0x1400821ee  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1400821f3  xor     ebx, ebx
0x1400821f5  mov     rcx, [rsp+28h+pv]; pv
0x1400821fa  call    cs:__imp_CoTaskMemFree
0x140082200  mov     rcx, [rsp+28h+arg_18]; pv
0x140082205  call    cs:__imp_CoTaskMemFree
0x14008220b  jmp     short loc_140082212
0x14008220d  mov     ebx, 8004036Ch
0x140082212  mov     rsi, [rsp+28h+arg_10]
0x140082217  mov     eax, ebx
0x140082219  mov     rbx, [rsp+28h+arg_8]
0x14008221e  add     rsp, 20h
0x140082222  pop     rdi
0x140082223  retn
```
