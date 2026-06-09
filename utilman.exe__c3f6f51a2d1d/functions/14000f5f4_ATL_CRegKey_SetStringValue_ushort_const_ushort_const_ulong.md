# ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)

- ea: `0x14000f5f4`
- end: `0x14000f647`
- name: `?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z`
- size: `83`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140012f54`
- `0x14001443c`
- `0x140015720`
- `0x140016e8c`
- `0x140017e18`
- `0x14001cfa0`

## callees

- `0x14000d678`
- `0x14000f5f4`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14000f635`
- `ADVAPI32!RegSetValueExW` at `0x14000f635`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetStringValue(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData)
{
  __int64 v3; // rax

  if ( !lpData )
  {
    ATL::AtlThrowImpl(-2147467259);
    __debugbreak();
  }
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&lpData[2 * v3] );
  return RegSetValueExW(*this, a2, 0, 1u, lpData, 2 * v3 + 2);
}

```

## disassembly

```asm
0x14000f5f4  sub     rsp, 38h
0x14000f5f8  xor     r9d, r9d
0x14000f5fb  test    r8, r8
0x14000f5fe  jnz     short loc_14000F60B
0x14000f600  mov     ecx, 80004005h; int
0x14000f605  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000f60a  int     3; Trap to Debugger
0x14000f60b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f60f  inc     rax
0x14000f612  cmp     [r8+rax*2], r9w
0x14000f617  jnz     short loc_14000F60F
0x14000f619  mov     rcx, [rcx]; hKey
0x14000f61c  lea     eax, ds:2[rax*2]
0x14000f623  mov     [rsp+38h+cbData], eax; cbData
0x14000f627  mov     r9d, 1; dwType
0x14000f62d  mov     [rsp+38h+lpData], r8; lpData
0x14000f632  xor     r8d, r8d; Reserved
0x14000f635  call    cs:__imp_RegSetValueExW
0x14000f63c  nop     dword ptr [rax+rax+00h]
0x14000f641  add     rsp, 38h
0x14000f645  retn
```
