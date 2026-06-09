# COfflineSync::GetHandlerInfo(_tagSYNCMGRHANDLERINFO * *)

- ea: `0x180011180`
- end: `0x1800111ff`
- name: `?GetHandlerInfo@COfflineSync@@UEAAJPEAPEAU_tagSYNCMGRHANDLERINFO@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(COfflineSync *__hidden this, struct _tagSYNCMGRHANDLERINFO **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180011180`

## import_xrefs

- `USER32!LoadIconW` at `0x1800111ba`
- `USER32!LoadIconW` at `0x1800111ba`
- `USER32!LoadStringW` at `0x1800111ea`
- `USER32!LoadStringW` at `0x1800111ea`
- `ole32!CoTaskMemAlloc` at `0x18001119a`
- `ole32!CoTaskMemAlloc` at `0x18001119a`

## pseudocode

```c
__int64 __fastcall COfflineSync::GetHandlerInfo(COfflineSync *this, struct _tagSYNCMGRHANDLERINFO **a2)
{
  struct _tagSYNCMGRHANDLERINFO *v4; // rax
  HINSTANCE v5; // rcx
  HINSTANCE v6; // rcx

  if ( !a2 )
    return 2147942487LL;
  v4 = (struct _tagSYNCMGRHANDLERINFO *)CoTaskMemAlloc(0x58u);
  *a2 = v4;
  if ( !v4 )
    return 2147942414LL;
  v5 = g_hInst;
  v4->cbSize = 88;
  (*a2)->hIcon = LoadIconW(v5, (LPCWSTR)0x72);
  v6 = g_hinstMUI;
  (*a2)->SyncMgrHandlerFlags = 0;
  LoadStringW(v6, 0x1FFEu, (*a2)->wszHandlerName, 32);
  return 0;
}

```

## disassembly

```asm
0x180011180  push    rbx
0x180011182  sub     rsp, 20h
0x180011186  mov     rbx, rdx
0x180011189  test    rdx, rdx
0x18001118c  jnz     short loc_180011195
0x18001118e  mov     eax, 80070057h
0x180011193  jmp     short loc_1800111F9
0x180011195  mov     ecx, 58h ; 'X'; cb
0x18001119a  call    cs:__imp_CoTaskMemAlloc
0x1800111a0  mov     [rbx], rax
0x1800111a3  test    rax, rax
0x1800111a6  jz      short loc_1800111F4
0x1800111a8  mov     rcx, cs:g_hInst; hInstance
0x1800111af  mov     edx, 72h ; 'r'; lpIconName
0x1800111b4  mov     dword ptr [rax], 58h ; 'X'
0x1800111ba  call    cs:__imp_LoadIconW
0x1800111c0  mov     rcx, [rbx]
0x1800111c3  mov     edx, 1FFEh; uID
0x1800111c8  mov     r9d, 20h ; ' '; cchBufferMax
0x1800111ce  mov     [rcx+8], rax
0x1800111d2  mov     rax, [rbx]
0x1800111d5  mov     rcx, cs:g_hinstMUI; hInstance
0x1800111dc  mov     dword ptr [rax+10h], 0
0x1800111e3  mov     r8, [rbx]
0x1800111e6  add     r8, 14h; lpBuffer
0x1800111ea  call    cs:__imp_LoadStringW
0x1800111f0  xor     eax, eax
0x1800111f2  jmp     short loc_1800111F9
0x1800111f4  mov     eax, 8007000Eh
0x1800111f9  add     rsp, 20h
0x1800111fd  pop     rbx
0x1800111fe  retn
```
