# CWorkItemHandler::OnRequestCompletion(ulong,ulong,_OVERLAPPED *)

- ea: `0x180013e70`
- end: `0x180013ee0`
- name: `?OnRequestCompletion@CWorkItemHandler@@UEAAXKKPEAU_OVERLAPPED@@@Z`
- size: `112`
- prototype: `void __fastcall(CWorkItemHandler *this, DWORD, DWORD, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180013e70`
- `0x18001d010`

## import_xrefs

- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180013ece`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180013ece`

## pseudocode

```c
void __fastcall CWorkItemHandler::OnRequestCompletion(
        CWorkItemHandler *this,
        DWORD a2,
        DWORD a3,
        struct _OVERLAPPED *a4)
{
  bool v4; // zf

  v4 = (a4[1].Internal & 2) == 0;
  a4[1].Offset = a3;
  a4[1].OffsetHigh = a2;
  if ( v4 )
  {
    if ( (a4[1].Internal & 1) != 0 )
      (**(void (__fastcall ***)(ULONG_PTR, struct _OVERLAPPED *))a4[1].InternalHigh)(a4[1].InternalHigh, a4);
    else
      WdsAssert("base\\eco\\wds\\wdssrv\\server\\src\\workitem.cpp", 0xCBu, "0", 1, 0);
  }
  else
  {
    ((void (__fastcall *)(struct _OVERLAPPED *))a4[1].InternalHigh)(a4);
  }
}

```

## disassembly

```asm
0x180013e70  sub     rsp, 38h
0x180013e74  test    byte ptr [r9+20h], 2
0x180013e79  mov     [r9+30h], r8d
0x180013e7d  mov     [r9+34h], edx
0x180013e81  jz      short loc_180013E93
0x180013e83  mov     rax, [r9+28h]
0x180013e87  mov     rcx, r9
0x180013e8a  add     rsp, 38h
0x180013e8e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180013e93  test    byte ptr [r9+20h], 1
0x180013e98  jz      short loc_180013EB0
0x180013e9a  mov     rcx, [r9+28h]
0x180013e9e  mov     rdx, r9
0x180013ea1  mov     rax, [rcx]
0x180013ea4  mov     rax, [rax]
0x180013ea7  add     rsp, 38h
0x180013eab  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180013eb0  and     [rsp+38h+var_18], 0
0x180013eb5  lea     r8, a0; "0"
0x180013ebc  mov     r9d, 1
0x180013ec2  lea     rcx, aBaseEcoWdsWdss_12; "base\\eco\\wds\\wdssrv\\server\\src\\wo"...
0x180013ec9  mov     edx, 0CBh
0x180013ece  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180013ed5  nop     dword ptr [rax+rax+00h]
0x180013eda  add     rsp, 38h
0x180013ede  retn
```
