# IASTemplatesRoot::GetTemplatesHelper(ATL::CComPtr<IIASItemsCollection> &,long,_ITEMTYPE,IIASItemsCollection * *)

- ea: `0x180040928`
- end: `0x1800409ed`
- name: `?GetTemplatesHelper@IASTemplatesRoot@@AEAAJAEAV?$CComPtr@UIIASItemsCollection@@@ATL@@JW4_ITEMTYPE@@PEAPEAUIIASItemsCollection@@@Z`
- size: `197`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180040a30`
- `0x180040a60`
- `0x180040a90`
- `0x180040ac0`

## callees

- `0x18002f14c`
- `0x18002f434`
- `0x180040928`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x180040997`: `SdoHelper failed to get templates collection (%d), 0x%x`

## pseudocode

```c
__int64 __fastcall IASTemplatesRoot::GetTemplatesHelper(
        __int64 a1,
        __int64 *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 *a5)
{
  int ItemsCollection; // ebx
  __int64 v8; // rcx

  if ( !a5 )
    return 2147500035LL;
  ItemsCollection = 0;
  *a5 = 0;
  if ( *a2 || (ItemsCollection = IASItem::GetItemsCollection(a1 + 16, a3, a4, a2), ItemsCollection >= 0) )
  {
    v8 = *a2;
    *a5 = *a2;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("SdoHelper failed to get templates collection (%d), 0x%x");
    WPP_SF_sdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_428e26f2a3d93e6ce2309ac2b77eba4e_Traceguids);
  }
  return (unsigned int)ItemsCollection;
}

```

## disassembly

```asm
0x180040928  push    rbx
0x18004092a  push    rbp
0x18004092b  push    rsi
0x18004092c  push    rdi
0x18004092d  sub     rsp, 38h
0x180040931  mov     rdi, [rsp+58h+arg_20]
0x180040939  mov     eax, r9d
0x18004093c  mov     ebp, r8d
0x18004093f  mov     rsi, rdx
0x180040942  test    rdi, rdi
0x180040945  jnz     short loc_180040951
0x180040947  mov     eax, 80004003h
0x18004094c  jmp     loc_1800409E4
0x180040951  xor     ebx, ebx
0x180040953  mov     [rdi], rbx
0x180040956  cmp     [rdx], rbx
0x180040959  jnz     short loc_1800409CB
0x18004095b  add     rcx, 10h
0x18004095f  mov     r9, rsi
0x180040962  mov     r8d, eax
0x180040965  mov     edx, ebp
0x180040967  call    ?GetItemsCollection@IASItem@@IEAAJKW4_ITEMTYPE@@PEAPEAUIIASItemsCollection@@@Z; IASItem::GetItemsCollection(ulong,_ITEMTYPE,IIASItemsCollection * *)
0x18004096c  mov     ebx, eax
0x18004096e  test    eax, eax
0x180040970  jns     short loc_1800409CB
0x180040972  mov     rax, cs:WPP_GLOBAL_Control
0x180040979  lea     rcx, WPP_GLOBAL_Control
0x180040980  cmp     rax, rcx
0x180040983  jz      short loc_1800409E2
0x180040985  cmp     byte ptr [rax+19h], 2
0x180040989  jb      short loc_1800409E2
0x18004098b  test    dword ptr [rax+1Ch], 400h
0x180040992  jz      short loc_1800409E2
0x180040994  mov     r8d, ebx
0x180040997  lea     rcx, aSdohelperFaile; "SdoHelper failed to get templates colle"...
0x18004099e  mov     edx, ebp
0x1800409a0  call    WppDbgPrint
0x1800409a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800409ac  lea     r8, WPP_428e26f2a3d93e6ce2309ac2b77eba4e_Traceguids
0x1800409b3  mov     edx, 0Ah
0x1800409b8  mov     [rsp+58h+var_30], ebx
0x1800409bc  mov     [rsp+58h+var_38], ebp
0x1800409c0  mov     rcx, [rcx+10h]
0x1800409c4  call    WPP_SF_sdD
0x1800409c9  jmp     short loc_1800409E2
0x1800409cb  mov     rcx, [rsi]
0x1800409ce  mov     [rdi], rcx
0x1800409d1  test    rcx, rcx
0x1800409d4  jz      short loc_1800409E2
0x1800409d6  mov     rax, [rcx]
0x1800409d9  mov     rax, [rax+8]
0x1800409dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409e2  mov     eax, ebx
0x1800409e4  add     rsp, 38h
0x1800409e8  pop     rdi
0x1800409e9  pop     rsi
0x1800409ea  pop     rbp
0x1800409eb  pop     rbx
0x1800409ec  retn
```
