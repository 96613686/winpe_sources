# GetFeedURLFromEnclosurePathFeedCB(IXFeed *,void *)

- ea: `0x18004e6c8`
- end: `0x18004e775`
- name: `?GetFeedURLFromEnclosurePathFeedCB@@YAHPEAUIXFeed@@PEAX@Z`
- size: `173`
- prototype: `__int64 __fastcall(struct IXFeed *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004e540`

## callees

- `0x18004e6c8`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004e714`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004e714`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e756`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e756`

## pseudocode

```c
__int64 __fastcall GetFeedURLFromEnclosurePathFeedCB(struct IXFeed *a1, LPCWCH *a2)
{
  struct IXFeedVtbl *lpVtbl; // rax
  unsigned int v5; // ebx
  struct IXFeedVtbl *v6; // rax
  LPCWCH lpString2; // [rsp+40h] [rbp+8h] BYREF
  const WCHAR *v9; // [rsp+48h] [rbp+10h] BYREF

  lpVtbl = a1->lpVtbl;
  lpString2 = 0;
  v5 = 1;
  if ( ((int (__fastcall *)(struct IXFeed *, LPCWCH *))lpVtbl->LocalEnclosurePath)(a1, &lpString2) >= 0 )
  {
    if ( CompareStringOrdinal(*a2, -1, lpString2, -1, 1) == 2 )
    {
      v6 = a1->lpVtbl;
      v9 = 0;
      if ( ((int (__fastcall *)(struct IXFeed *, const WCHAR **))v6->Url)(a1, &v9) >= 0 )
        a2[1] = v9;
      v5 = 0;
    }
    CoTaskMemFree((LPVOID)lpString2);
  }
  return v5;
}

```

## disassembly

```asm
0x18004e6c8  mov     r11, rsp
0x18004e6cb  mov     [r11+18h], rbx
0x18004e6cf  mov     [r11+20h], rsi
0x18004e6d3  push    rdi
0x18004e6d4  sub     rsp, 30h
0x18004e6d8  mov     rax, [rcx]
0x18004e6db  mov     rsi, rdx
0x18004e6de  lea     rdx, [r11+8]
0x18004e6e2  mov     qword ptr [r11+8], 0
0x18004e6ea  mov     rdi, rcx
0x18004e6ed  mov     ebx, 1
0x18004e6f2  mov     rax, [rax+0B0h]
0x18004e6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6fe  test    eax, eax
0x18004e700  js      short loc_18004E762
0x18004e702  mov     r8, [rsp+38h+lpString2]; lpString2
0x18004e707  or      edx, 0FFFFFFFFh; cchCount1
0x18004e70a  mov     rcx, [rsi]; lpString1
0x18004e70d  mov     r9d, edx; cchCount2
0x18004e710  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x18004e714  call    cs:__imp_CompareStringOrdinal
0x18004e71b  nop     dword ptr [rax+rax+00h]
0x18004e720  cmp     eax, 2
0x18004e723  jnz     short loc_18004E751
0x18004e725  mov     rax, [rdi]
0x18004e728  lea     rdx, [rsp+38h+arg_8]
0x18004e72d  mov     rcx, rdi
0x18004e730  mov     [rsp+38h+arg_8], 0
0x18004e739  mov     rax, [rax+30h]
0x18004e73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e742  test    eax, eax
0x18004e744  js      short loc_18004E74F
0x18004e746  mov     rax, [rsp+38h+arg_8]
0x18004e74b  mov     [rsi+8], rax
0x18004e74f  xor     ebx, ebx
0x18004e751  mov     rcx, [rsp+38h+lpString2]; pv
0x18004e756  call    cs:__imp_CoTaskMemFree
0x18004e75d  nop     dword ptr [rax+rax+00h]
0x18004e762  mov     rsi, [rsp+38h+arg_18]
0x18004e767  mov     eax, ebx
0x18004e769  mov     rbx, [rsp+38h+arg_10]
0x18004e76e  add     rsp, 30h
0x18004e772  pop     rdi
0x18004e773  retn
```
