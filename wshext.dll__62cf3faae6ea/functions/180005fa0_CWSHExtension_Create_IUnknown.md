# CWSHExtension::Create(IUnknown *)

- ea: `0x180005fa0`
- end: `0x18000605c`
- name: `?Create@CWSHExtension@@SAPEAUIUnknown@@PEAU2@@Z`
- size: `188`
- prototype: `struct IUnknown *__fastcall(struct IUnknown *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003200`
- `0x180005fa0`

## pseudocode

```c
struct IUnknown *__fastcall CWSHExtension::Create(struct IUnknownVtbl *a1)
{
  struct IUnknown *v2; // rax
  struct IUnknown *v3; // r8

  v2 = (struct IUnknown *)operator new(0x160u);
  v3 = v2;
  if ( v2 )
  {
    v2[5].lpVtbl = (struct IUnknownVtbl *)&CUnknown::`vftable';
    if ( !a1 )
      a1 = (struct IUnknownVtbl *)&v2[8];
    LODWORD(v2[9].lpVtbl) = 1;
    v2[8].lpVtbl = (struct IUnknownVtbl *)&CUnknown::InnerUnknown::`vftable';
    v2[7].lpVtbl = (struct IUnknownVtbl *)&TaUser_DescCWSHExtension;
    v2[6].lpVtbl = a1;
    _InterlockedIncrement(&Global::g_cObjects);
    v2->lpVtbl = (struct IUnknownVtbl *)&CWSHExtension::`vftable'{for `IWSHExtension'};
    v2[1].lpVtbl = (struct IUnknownVtbl *)&CWSHExtension::`vftable'{for `IShellExtInit'};
    v2[2].lpVtbl = (struct IUnknownVtbl *)&CWSHExtension::`vftable'{for `IShellPropSheetExt'};
    v2[3].lpVtbl = (struct IUnknownVtbl *)&CWSHExtension::`vftable'{for `IDropTarget'};
    v2[4].lpVtbl = (struct IUnknownVtbl *)&CWSHExtension::`vftable'{for `IPersistFile'};
    v2[5].lpVtbl = (struct IUnknownVtbl *)&CWSHExtension::`vftable'{for `CUnkObj'};
    _InterlockedCompareExchange((volatile signed __int32 *)&g_cRefPropSheet, 0, 0);
    v2[10].lpVtbl = 0;
  }
  else
  {
    v3 = 0;
  }
  return v3 + 8;
}

```

## disassembly

```asm
0x180005fa0  push    rbx
0x180005fa2  sub     rsp, 20h
0x180005fa6  mov     rbx, rcx
0x180005fa9  mov     ecx, 160h; Size
0x180005fae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005fb3  mov     r8, rax
0x180005fb6  test    rax, rax
0x180005fb9  jz      loc_18000604F
0x180005fbf  lea     rdx, [r8+40h]
0x180005fc3  test    rbx, rbx
0x180005fc6  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x180005fcd  mov     [r8+28h], rax
0x180005fd1  cmovz   rbx, rdx
0x180005fd5  lea     rax, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x180005fdc  mov     dword ptr [rdx+8], 1
0x180005fe3  mov     [rdx], rax
0x180005fe6  lea     rax, ?TaUser_DescCWSHExtension@@3UTaDescUnknown@@A; TaDescUnknown TaUser_DescCWSHExtension
0x180005fed  mov     [r8+38h], rax
0x180005ff1  mov     [r8+30h], rbx
0x180005ff5  lock inc cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x180005ffc  lea     rax, ??_7CWSHExtension@@6BIWSHExtension@@@; const CWSHExtension::`vftable'{for `IWSHExtension'}
0x180006003  xor     ecx, ecx
0x180006005  mov     [r8], rax
0x180006008  lea     rax, ??_7CWSHExtension@@6BIShellExtInit@@@; const CWSHExtension::`vftable'{for `IShellExtInit'}
0x18000600f  mov     [r8+8], rax
0x180006013  lea     rax, ??_7CWSHExtension@@6BIShellPropSheetExt@@@; const CWSHExtension::`vftable'{for `IShellPropSheetExt'}
0x18000601a  mov     [r8+10h], rax
0x18000601e  lea     rax, ??_7CWSHExtension@@6BIDropTarget@@@; const CWSHExtension::`vftable'{for `IDropTarget'}
0x180006025  mov     [r8+18h], rax
0x180006029  lea     rax, ??_7CWSHExtension@@6BIPersistFile@@@; const CWSHExtension::`vftable'{for `IPersistFile'}
0x180006030  mov     [r8+20h], rax
0x180006034  lea     rax, ??_7CWSHExtension@@6BCUnkObj@@@; const CWSHExtension::`vftable'{for `CUnkObj'}
0x18000603b  mov     [r8+28h], rax
0x18000603f  xor     eax, eax
0x180006041  lock cmpxchg cs:?g_cRefPropSheet@@3IA, ecx; uint g_cRefPropSheet
0x180006049  mov     [r8+50h], rcx
0x18000604d  jmp     short loc_180006052
0x18000604f  xor     r8d, r8d
0x180006052  lea     rax, [r8+40h]
0x180006056  add     rsp, 20h
0x18000605a  pop     rbx
0x18000605b  retn
```
