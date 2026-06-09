# CShellPropertyThunk::RefIDSearchThunk(CdsBinaryOpQuery const *,IHMEMediaContainer *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)

- ea: `0x140082280`
- end: `0x140082344`
- name: `?RefIDSearchThunk@CShellPropertyThunk@@CAJPEBVCdsBinaryOpQuery@@PEAUIHMEMediaContainer@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x140015100`
- `0x140081c6c`
- `0x140082280`
- `0x140082504`
- `0x14009e010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14008231a`
- `ole32!CoTaskMemFree` at `0x140082325`
- `ole32!CoTaskMemFree` at `0x14008231a`
- `ole32!CoTaskMemFree` at `0x140082325`

## pseudocode

```c
__int64 __fastcall CShellPropertyThunk::RefIDSearchThunk(__int64 a1, __int64 a2, __int64 *a3)
{
  unsigned __int16 *v5; // rcx
  int ItemIDFromObjectID; // ebx
  const unsigned __int16 *v7; // rax
  const wchar_t *v8; // rdx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v11; // [rsp+48h] [rbp+20h] BYREF

  if ( *(_DWORD *)(a1 + 36) == 1 )
  {
    v5 = *(unsigned __int16 **)(a1 + 40);
    pv = 0;
    v11 = 0;
    ItemIDFromObjectID = CShellPropertyThunk::GetItemIDFromObjectID(v5, &pv, &v11);
    if ( ItemIDFromObjectID >= 0 )
    {
      if ( CShellPropertyThunk::ShouldGenerateRefID((const unsigned __int16 *)pv)
        || (v7 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 56LL))(a2),
            !CShellPropertyThunk::ShouldGenerateRefID(v7)) )
      {
        v8 = L"System.Search.EntryID IS NULL";
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::Append(
          a3,
          L"System.Search.EntryID IS NOT NULL AND System.Search.EntryID = ");
        v8 = (const wchar_t *)v11;
      }
      ATL::CSimpleStringT<unsigned short,0>::Append(a3, v8);
    }
    CoTaskMemFree(pv);
    CoTaskMemFree(v11);
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
0x140082280  mov     rax, rsp
0x140082283  mov     [rax+10h], rbx
0x140082287  mov     [rax+18h], rsi
0x14008228b  push    rdi
0x14008228c  sub     rsp, 20h
0x140082290  cmp     dword ptr [rcx+24h], 1
0x140082294  mov     rdi, r8
0x140082297  mov     rsi, rdx
0x14008229a  jnz     loc_14008232D
0x1400822a0  mov     rcx, [rcx+28h]; unsigned __int16 *
0x1400822a4  lea     r8, [rax+20h]; unsigned __int16 **
0x1400822a8  lea     rdx, [rax+8]; unsigned __int16 **
0x1400822ac  mov     qword ptr [rax+8], 0
0x1400822b4  mov     qword ptr [rax+20h], 0
0x1400822bc  call    ?GetItemIDFromObjectID@CShellPropertyThunk@@SAJPEBGPEAPEAG1@Z; CShellPropertyThunk::GetItemIDFromObjectID(ushort const *,ushort * *,ushort * *)
0x1400822c1  mov     ebx, eax
0x1400822c3  test    eax, eax
0x1400822c5  js      short loc_140082315
0x1400822c7  mov     rcx, [rsp+28h+pv]; unsigned __int16 *
0x1400822cc  call    ?ShouldGenerateRefID@CShellPropertyThunk@@SA_NPEBG@Z; CShellPropertyThunk::ShouldGenerateRefID(ushort const *)
0x1400822d1  test    al, al
0x1400822d3  jnz     short loc_140082306
0x1400822d5  mov     rcx, [rsi]
0x1400822d8  mov     rax, [rcx+38h]
0x1400822dc  mov     rcx, rsi
0x1400822df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400822e4  mov     rcx, rax; unsigned __int16 *
0x1400822e7  call    ?ShouldGenerateRefID@CShellPropertyThunk@@SA_NPEBG@Z; CShellPropertyThunk::ShouldGenerateRefID(ushort const *)
0x1400822ec  test    al, al
0x1400822ee  jz      short loc_140082306
0x1400822f0  lea     rdx, aSystemSearchEn_4; "System.Search.EntryID IS NOT NULL AND S"...
0x1400822f7  mov     rcx, rdi
0x1400822fa  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1400822ff  mov     rdx, [rsp+28h+arg_18]
0x140082304  jmp     short loc_14008230D
0x140082306  lea     rdx, aSystemSearchEn; "System.Search.EntryID IS NULL"
0x14008230d  mov     rcx, rdi
0x140082310  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x140082315  mov     rcx, [rsp+28h+pv]; pv
0x14008231a  call    cs:__imp_CoTaskMemFree
0x140082320  mov     rcx, [rsp+28h+arg_18]; pv
0x140082325  call    cs:__imp_CoTaskMemFree
0x14008232b  jmp     short loc_140082332
0x14008232d  mov     ebx, 8004036Ch
0x140082332  mov     rsi, [rsp+28h+arg_10]
0x140082337  mov     eax, ebx
0x140082339  mov     rbx, [rsp+28h+arg_8]
0x14008233e  add     rsp, 20h
0x140082342  pop     rdi
0x140082343  retn
```
