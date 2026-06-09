# CControlPanelPage::OnNavigateAway(void)

- ea: `0x180018790`
- end: `0x1800187b9`
- name: `?OnNavigateAway@CControlPanelPage@@UEAAJXZ`
- size: `41`
- prototype: `__int64 __fastcall(CControlPanelPage *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800137e0`

## callees

- `0x180018790`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x1800187ac`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x1800187ac`

## pseudocode

```c
__int64 __fastcall CControlPanelPage::OnNavigateAway(CControlPanelPage *this)
{
  if ( *((_DWORD *)this + 2) )
    IUnknown_ProfferService(*((_QWORD *)this - 1), &IID_IShellSearchTargetServices, 0, (char *)this + 8);
  return 0;
}

```

## disassembly

```asm
0x180018790  sub     rsp, 28h
0x180018794  lea     r9, [rcx+8]
0x180018798  cmp     dword ptr [r9], 0
0x18001879c  jz      short loc_1800187B2
0x18001879e  mov     rcx, [rcx-8]
0x1800187a2  lea     rdx, IID_IShellSearchTargetServices
0x1800187a9  xor     r8d, r8d
0x1800187ac  call    cs:__imp_IUnknown_ProfferService
0x1800187b2  xor     eax, eax
0x1800187b4  add     rsp, 28h
0x1800187b8  retn
```
