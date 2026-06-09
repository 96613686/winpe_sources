# DataStoreClient::GetTemplates(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>> &)

- ea: `0x1800547f0`
- end: `0x1800548b1`
- name: `?GetTemplates@DataStoreClient@@UEBAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@@Z`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18002cca4`
- `0x180042a80`
- `0x18005102c`
- `0x1800547f0`
- `0x180058010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180054849`
- `ole32!CoTaskMemFree` at `0x180054849`

## string_xrefs

- `0x180054875`: `GetTemplates() is called on a machine that doesn't support templates`

## pseudocode

```c
__int64 __fastcall DataStoreClient::GetTemplates(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rcx
  int v5; // ebx
  int v7; // [rsp+40h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp+20h] BYREF

  v3 = *(_QWORD *)(a1 + 64);
  v7 = 0;
  pv = 0;
  if ( v3 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, int *, LPVOID *))(*(_QWORD *)v3 + 64LL))(v3, a2, &v7, &pv);
    if ( v5 >= 0 )
    {
      std::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>::assign(
        a3,
        pv,
        v7);
      CoTaskMemFree(pv);
    }
  }
  else
  {
    v5 = -2147467262;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("GetTemplates() is called on a machine that doesn't support templates");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_bc84e2600b1038389a22987ce46afadc_Traceguids, "NPSDS");
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800547f0  mov     r11, rsp
0x1800547f3  mov     [r11+10h], rbx
0x1800547f7  push    rdi
0x1800547f8  sub     rsp, 30h
0x1800547fc  mov     rcx, [rcx+40h]
0x180054800  mov     rdi, r8
0x180054803  mov     [rsp+38h+arg_0], 0
0x18005480b  mov     qword ptr [r11+20h], 0
0x180054813  test    rcx, rcx
0x180054816  jz      short loc_180054851
0x180054818  mov     rax, [rcx]
0x18005481b  lea     r9, [r11+20h]
0x18005481f  lea     r8, [r11+8]
0x180054823  mov     rax, [rax+40h]
0x180054827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005482c  mov     ebx, eax
0x18005482e  test    eax, eax
0x180054830  js      short loc_1800548A4
0x180054832  movsxd  r8, [rsp+38h+arg_0]
0x180054837  mov     rcx, rdi
0x18005483a  mov     rdx, [rsp+38h+pv]
0x18005483f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@QEAAAEAV12@PEBG_K@Z; std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180054844  mov     rcx, [rsp+38h+pv]; pv
0x180054849  call    cs:__imp_CoTaskMemFree
0x18005484f  jmp     short loc_1800548A4
0x180054851  mov     rax, cs:WPP_GLOBAL_Control
0x180054858  lea     rcx, WPP_GLOBAL_Control
0x18005485f  mov     ebx, 80004002h
0x180054864  cmp     rax, rcx
0x180054867  jz      short loc_1800548A4
0x180054869  cmp     byte ptr [rax+19h], 2
0x18005486d  jb      short loc_1800548A4
0x18005486f  test    byte ptr [rax+1Ch], 10h
0x180054873  jz      short loc_1800548A4
0x180054875  lea     rcx, aGettemplatesIs; "GetTemplates() is called on a machine t"...
0x18005487c  call    WppDbgPrint
0x180054881  mov     rcx, cs:WPP_GLOBAL_Control
0x180054888  lea     r9, aNpsds; "NPSDS"
0x18005488f  mov     edx, 0Ch
0x180054894  lea     r8, WPP_bc84e2600b1038389a22987ce46afadc_Traceguids
0x18005489b  mov     rcx, [rcx+10h]
0x18005489f  call    WPP_SF_s
0x1800548a4  mov     eax, ebx
0x1800548a6  mov     rbx, [rsp+38h+arg_8]
0x1800548ab  add     rsp, 30h
0x1800548af  pop     rdi
0x1800548b0  retn
```
