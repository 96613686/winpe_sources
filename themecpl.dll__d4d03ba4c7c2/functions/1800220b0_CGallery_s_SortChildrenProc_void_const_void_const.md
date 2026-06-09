# CGallery::s_SortChildrenProc(void const *,void const *)

- ea: `0x1800220b0`
- end: `0x1800221cc`
- name: `?s_SortChildrenProc@CGallery@@CAHPEBX0@Z`
- size: `284`
- prototype: `__int64 __fastcall(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800220b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002217d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002217d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800220de`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180022135`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800220de`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180022135`
- `DUI70!StrToID` at `0x1800220cc`
- `DUI70!StrToID` at `0x180022123`
- `DUI70!StrToID` at `0x1800220cc`
- `DUI70!StrToID` at `0x180022123`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180022102`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180022153`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180022102`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180022153`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002219c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800221ad`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002219c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800221ad`

## pseudocode

```c
__int64 __fastcall CGallery::s_SortChildrenProc(DirectUI::Element **a1, DirectUI::Element **a2)
{
  DirectUI::Element *v2; // rbx
  DirectUI::Element *v3; // rsi
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // rax
  unsigned int v6; // ebx
  const WCHAR *ContentString; // rdi
  unsigned __int16 v8; // ax
  DirectUI::Element *v9; // rax
  const WCHAR *v10; // rax
  int v11; // eax
  struct DirectUI::Value *v13; // [rsp+40h] [rbp+8h] BYREF
  struct DirectUI::Value *v14; // [rsp+48h] [rbp+10h] BYREF

  v2 = *a1;
  v3 = *a2;
  v4 = StrToID(L"Name");
  Descendent = DirectUI::Element::FindDescendent(v2, v4);
  v6 = 0;
  if ( Descendent )
  {
    v14 = 0;
    ContentString = DirectUI::Element::GetContentString(Descendent, &v14);
    if ( v14 )
    {
      v8 = StrToID(L"Name");
      v9 = DirectUI::Element::FindDescendent(v3, v8);
      if ( v9 )
      {
        v13 = 0;
        v10 = DirectUI::Element::GetContentString(v9, &v13);
        if ( v13 )
        {
          v6 = 1;
          v11 = CompareStringOrdinal(ContentString, -1, v10, -1, 1);
          if ( v11 == 2 )
          {
            v6 = 0;
          }
          else if ( v11 == 1 )
          {
            v6 = -1;
          }
          DirectUI::Value::Release(v13);
        }
      }
      DirectUI::Value::Release(v14);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800220b0  mov     [rsp+arg_10], rbx
0x1800220b5  mov     [rsp+arg_18], rsi
0x1800220ba  push    rdi
0x1800220bb  sub     rsp, 30h
0x1800220bf  mov     rbx, [rcx]
0x1800220c2  lea     rcx, aName; "Name"
0x1800220c9  mov     rsi, [rdx]
0x1800220cc  call    cs:__imp_StrToID
0x1800220d3  nop     dword ptr [rax+rax+00h]
0x1800220d8  movzx   edx, ax
0x1800220db  mov     rcx, rbx
0x1800220de  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800220e5  nop     dword ptr [rax+rax+00h]
0x1800220ea  xor     ebx, ebx
0x1800220ec  test    rax, rax
0x1800220ef  jz      loc_1800221B9
0x1800220f5  lea     rdx, [rsp+38h+arg_8]
0x1800220fa  mov     [rsp+38h+arg_8], rbx
0x1800220ff  mov     rcx, rax
0x180022102  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x180022109  nop     dword ptr [rax+rax+00h]
0x18002210e  mov     rdi, rax
0x180022111  cmp     [rsp+38h+arg_8], rbx
0x180022116  jz      loc_1800221B9
0x18002211c  lea     rcx, aName; "Name"
0x180022123  call    cs:__imp_StrToID
0x18002212a  nop     dword ptr [rax+rax+00h]
0x18002212f  movzx   edx, ax
0x180022132  mov     rcx, rsi
0x180022135  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18002213c  nop     dword ptr [rax+rax+00h]
0x180022141  test    rax, rax
0x180022144  jz      short loc_1800221A8
0x180022146  lea     rdx, [rsp+38h+arg_0]
0x18002214b  mov     [rsp+38h+arg_0], rbx
0x180022150  mov     rcx, rax
0x180022153  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x18002215a  nop     dword ptr [rax+rax+00h]
0x18002215f  cmp     [rsp+38h+arg_0], rbx
0x180022164  jz      short loc_1800221A8
0x180022166  or      esi, 0FFFFFFFFh
0x180022169  mov     ebx, 1
0x18002216e  mov     r9d, esi; cchCount2
0x180022171  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x180022175  mov     edx, esi; cchCount1
0x180022177  mov     r8, rax; lpString2
0x18002217a  mov     rcx, rdi; lpString1
0x18002217d  call    cs:__imp_CompareStringOrdinal
0x180022184  nop     dword ptr [rax+rax+00h]
0x180022189  cmp     eax, 2
0x18002218c  jnz     short loc_180022192
0x18002218e  xor     ebx, ebx
0x180022190  jmp     short loc_180022197
0x180022192  cmp     eax, ebx
0x180022194  cmovz   ebx, esi
0x180022197  mov     rcx, [rsp+38h+arg_0]
0x18002219c  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800221a3  nop     dword ptr [rax+rax+00h]
0x1800221a8  mov     rcx, [rsp+38h+arg_8]
0x1800221ad  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800221b4  nop     dword ptr [rax+rax+00h]
0x1800221b9  mov     rsi, [rsp+38h+arg_18]
0x1800221be  mov     eax, ebx
0x1800221c0  mov     rbx, [rsp+38h+arg_10]
0x1800221c5  add     rsp, 30h
0x1800221c9  pop     rdi
0x1800221ca  retn
```
