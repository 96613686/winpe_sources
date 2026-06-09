# BbSetDword(_BLACKBOARD *,ushort const *,ushort const *,ulong)

- ea: `0x1800087cc`
- end: `0x18000883d`
- name: `?BbSetDword@@YAHPEAU_BLACKBOARD@@PEBG1K@Z`
- size: `113`
- prototype: `__int64 __fastcall(struct _BLACKBOARD *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002730`
- `0x180006570`

## import_xrefs

- `WDSCORE!WdsInitializeDataUInt32` at `0x1800087ec`
- `WDSCORE!WdsInitializeDataUInt32` at `0x1800087ec`
- `WDSCORE!WdsSetBlackboardValue` at `0x18000880a`
- `WDSCORE!WdsSetBlackboardValue` at `0x18000880a`
- `WDSCORE!WdsFreeData` at `0x180008823`
- `WDSCORE!WdsFreeData` at `0x180008823`

## string_xrefs

- `0x180008800`: `Diagnostics\Dword\SetupCompliance`

## pseudocode

```c
__int64 __fastcall BbSetDword(
        struct _BLACKBOARD *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  __int128 v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = 0;
  WdsInitializeDataUInt32(&v7, a4);
  LODWORD(a3) = WdsSetBlackboardValue(a1, L"Diagnostics\\Dword\\SetupCompliance", a3, &v7) == 1;
  WdsFreeData(&v7);
  return (unsigned int)a3;
}

```

## disassembly

```asm
0x1800087cc  mov     [rsp+arg_0], rbx
0x1800087d1  push    rdi
0x1800087d2  sub     rsp, 30h
0x1800087d6  mov     rdi, rcx
0x1800087d9  xorps   xmm0, xmm0
0x1800087dc  lea     rcx, [rsp+38h+var_18]
0x1800087e1  mov     edx, r9d
0x1800087e4  movups  [rsp+38h+var_18], xmm0
0x1800087e9  mov     rbx, r8
0x1800087ec  call    cs:__imp_WdsInitializeDataUInt32
0x1800087f3  nop     dword ptr [rax+rax+00h]
0x1800087f8  lea     r9, [rsp+38h+var_18]
0x1800087fd  mov     r8, rbx
0x180008800  lea     rdx, aDiagnosticsDwo; "Diagnostics\\Dword\\SetupCompliance"
0x180008807  mov     rcx, rdi
0x18000880a  call    cs:__imp_WdsSetBlackboardValue
0x180008811  nop     dword ptr [rax+rax+00h]
0x180008816  xor     ebx, ebx
0x180008818  lea     rcx, [rsp+38h+var_18]
0x18000881d  cmp     eax, 1
0x180008820  setz    bl
0x180008823  call    cs:__imp_WdsFreeData
0x18000882a  nop     dword ptr [rax+rax+00h]
0x18000882f  mov     eax, ebx
0x180008831  mov     rbx, [rsp+38h+arg_0]
0x180008836  add     rsp, 30h
0x18000883a  pop     rdi
0x18000883b  retn
```
